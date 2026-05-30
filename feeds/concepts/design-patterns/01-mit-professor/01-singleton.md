# MIT Professor: Singleton (គោលការណ៍គ្រឹះដំបូងនៃ Singleton)

**Author:** ichamrong  
**Date:** 2026-05-18  
**Tags:** #mit-professor #first-principles #design-patterns #singleton #clean-code  
**Category:** Concepts / MIT Professor  
**Read Time:** ~5 min  

---

## 📌 មាតិកា (Table of Contents)
- [១. បញ្ហាស្នូល (The Core Problem)](#១-បញ្ហាស្នូល-the-core-problem)
- [២. ការទាញហេតុផលពីគោលការណ៍គ្រឹះ (First Principles Derivation)](#២-ការទាញហេតុផលពីគោលការណ៍គ្រឹះ-first-principles-derivation)
- [៣. ដ្យាក្រាមលំហូរ (Visual Derivation)](#៣-ដ្យាក្រាមលំហូរ-visual-derivation)
- [៤. Related Posts](#៤-related-posts)

---

## ១. បញ្ហាស្នូល (The Core Problem)

Let me start with a question. Suppose your program has one printer, one database connection pool, one configuration file loaded into memory. Some part of the system asks for it, and a moment later — somewhere else entirely — another part asks for it too. How do you guarantee they are talking about the *same* thing, and not two copies that have quietly drifted apart?

Hold onto that, because the trouble is subtle. When two pieces of code each create their own copy of "the" connection pool, nothing crashes immediately. The program runs. The tests pass. And then in production, under load, you get the bug that ruins your week: exhausted memory, a locked hardware port, two caches that disagree about the truth. Nobody wrote a bug. The bug is *structural* — it lives in the fact that the language let two copies exist at all.

យើងចង់គ្រប់គ្រងធនធានរួមគ្នា (ដូចជា Database Connection Pool ឬ Hardware Port) ដែលការបង្កើត Object ច្រើននឹងបណ្តាលឱ្យហូរហៀរមេម៉ូរី (Memory Exhaustion) ការជាប់គាំងខ្សែស្រឡាយដំណើរការ (Thread Lockups) ឬស្ថានភាពទិន្នន័យមិនស៊ីសង្វាក់គ្នា (Inconsistent State)។

---

## ២. ការទាញហេតុផលពីគោលការណ៍គ្រឹះ (First Principles Derivation)

### English

Let's not memorize a solution. Let's *derive* it, starting from how the machine actually behaves, and see if the pattern is forced on us.

**Start with one fact about the machine.** Every time you write `new`, the computer carves out a fresh, separate block of memory. That is not a style choice — it is what `new` *means*. So if our requirement is "exactly one of these must ever exist," then every stray `new` is a direct threat to that requirement. The danger isn't hypothetical; it's built into the keyword.

**Now ask the uncomfortable question.** What is currently stopping any developer, anywhere in the codebase, from typing `new ConnectionPool()` a second time? Be honest — the answer is *nothing*. The constructor is public, so the door is wide open. As long as that door stays open, no amount of discipline or documentation will save us; someone, someday, will walk through it.

**So the requirement quietly rewrites itself.** "Guarantee one instance" really means "remove from everyone else the *power* to create instances." We don't ask people not to call `new` — we make it impossible. We lock the constructor: make it `private`.

**But now we've created a new problem, haven't we?** If the door is locked, how does anyone get the object at all? We've protected the resource so well that nobody can reach it. The resolution is the whole insight: if the class is the only one allowed to construct itself, then *the class itself* must hand out the instance. We add one controlled doorway — a `public static` method, `getInstance()` — that does the bookkeeping nobody else can be trusted with: the first time it's called, it creates the single instance; every time after, it returns that very same one.

And that is the pattern, derived rather than memorized: lock creation, then expose one gate that guarantees sameness. Notice we never *chose* Singleton — the machine's behavior plus our requirement left us no other door.

### Khmer
* **គោលការណ៍គ្រឹះ ១៖** គិតអំពីដំណើរការរបស់កុំព្យូទ័រជាទូទៅ។ រាល់ពេលដែលអ្នកប្រើប្រាស់ពាក្យគន្លឹះ `new` កុំព្យូទ័រនឹងកាត់យកទំហំមេម៉ូរីថ្មីមួយ ដែលដាច់ដោយឡែកពីគ្នាទាំងស្រុង។
* **គោលការណ៍គ្រឹះ ២៖** ប្រសិនបើគោលដៅរបស់យើងគឺធានាឱ្យបាននូវការពិត "តែមួយគត់" នៅក្នុងប្រព័ន្ធទាំងមូល យើងចាំបាច់ត្រូវដកសិទ្ធិអ្នកដទៃក្នុងការបង្កើត Object ថ្មី។ យើងត្រូវតែលាក់និងការពារយន្តការនៃការបង្កើតនេះ។
* **ការទាញហេតុផល៖** តើយើងត្រូវធ្វើដូចម្តេច? ជាដំបូង យើងត្រូវប្តូរ Constructor របស់ Class នោះឱ្យទៅជា `private` ដែលប្រៀបដូចជាការចាក់សោទ្វារខាងមុខមិនឱ្យអ្នកណាចូលតាមចិត្ត។ ប៉ុន្តែបើទ្វារត្រូវបានចាក់សោរ តើគេអាចទាញយក Object នោះមកប្រើដោយរបៀបណា? ដំណោះស្រាយគឺ យើងត្រូវបង្កើតច្រកទ្វារសុវត្ថិភាពមួយ — តាមរយៈមុខងារ `public static` (ដូចជា `getInstance()`)។ ច្រកទ្វារនេះនឹងរង់ចាំត្រួតពិនិត្យ៖ ប្រសិនបើ Object មិនទាន់មានទេ វានឹងបង្កើតវាយ៉ាងប្រុងប្រយ័ត្ន។ ប៉ុន្តែបើមានហើយ វានឹងប្រគល់ Object ដដែលនោះត្រឡប់ទៅវិញ ដែលជួយធានាថាគ្រប់គ្នាសុទ្ធតែបានប្រើប្រាស់ប្រភពនៃការពិតតែមួយដូចៗគ្នា។

---

## ៣. ដ្យាក្រាមលំហូរ (Visual Derivation)

```mermaid
flowchart TD
    classDef axiom fill:#2c3e50,stroke:#34495e,color:#fff
    classDef derivation fill:#2980b9,stroke:#3498db,color:#fff
    classDef result fill:#27ae60,stroke:#2ecc71,color:#fff

    A["🔴 System Requirement:<br/>Exactly One Instance"]:::axiom --> B["🔒 Private Constructor:<br/>Prevents direct instantiation"]:::derivation
    B --> C["🌍 Static Variable:<br/>Stores the single<br/>instance"]:::derivation
    C --> D["⚡ Static getInstance():<br/>Lazy loads and<br/>returns instance"]:::derivation
    D --> E["✅ Guaranteed Single Source<br/>of Truth"]:::result
```

---

## ៤. Related Posts

### 🔗 Explore All Viewpoints:
* 📖 **Read the Parable:** [The Bank's Only Vault (ទូដែកតែមួយគត់របស់ធនាគារ)](../../parables/75-the-banks-only-vault.md) — Explains the emotional core of shared truth.
* 🧠 **Read the First Principles Derivation:** [MIT Professor Strategy: Singleton (គោលការណ៍គ្រឹះដំបូងនៃ Singleton)](../01-mit-professor/01-singleton.md) — Derives the pattern from fundamental computer axioms.
* 👶 **Read the Feynman Simplification:** [Feynman Technique: Singleton (ការពន្យល់ពី Singleton ដោយគ្មានពាក្យបច្ចេកទេស)](../02-feynman-technique/04-singleton.md) — Breaks it down using the central clock tower.
* 👦 **Read the ELI5 Metaphor:** [ELI5: Singleton (ម៉ាស៊ីនខួងខ្មៅដៃតែមួយគត់ក្នុងថ្នាក់រៀន)](../03-eli5/04-singleton.md) — Teaches it to a five-year-old using classroom pencil sharpeners.
* 🌉 **Read the Analogy Bridge:** [Analogy Bridge: Singleton (ស្ពានប្រៀបធៀបនៃប្រភពពិតតែមួយគត់)](../04-analogy-bridge/04-singleton.md) — Maps it to a hotel front desk and shows where physical limits fail compared to code threads.
* 🧐 **Read the Socratic Discovery:** [Socratic Method: Singleton (ការបង្កើតប្រព័ន្ធការពិតតែមួយគត់តាមវិធីសាស្ត្រសូក្រាត)](../05-socratic-method/04-singleton.md) — Guide your self-discovery through mentor-student dialogue.
* 📰 **Read the Journalist Summary:** [Journalist: Singleton (ការធានាឱ្យមានការពិតតែមួយគត់ក្នុងប្រព័ន្ធទាំងមូល)](../06-journalist-inverted-pyramid/04-singleton.md) — Get the high-impact lede, volatile visibility, and thread-safety details first.
* 🎭 **Read the Storyteller Narrative:** [Storyteller: Singleton (អាណាព្យាបាលនៃសេចក្តីពិត និងកងទ័ពក្លូនបង្កចលាចល)](../07-storyteller-narrative-arc/04-singleton.md) — Follow Kiri's heroic journey to vanquish the duplicate logger clone army.
* ⚙️ **Read the Engineer Spec:** [Engineer: Singleton (ការសម្របសម្រួលប្រភពពិតតែមួយគត់ និងទប់ស្កាត់ការខ្ជះខ្ជាយធនធាន)](../08-engineer-requirements-constraints-solution/03-singleton.md) — Read the rigorous engineering specification, DCL performance details, and candidate elimination.
* 📊 **Read the Pros & Cons:** [Pros & Cons Compared: Singleton (ការប្រៀបធៀបគុណសម្បត្តិ និងគុណវិបត្តិនៃ Singleton)](../09-pros-and-cons-compared/01-singleton.md) — Full trade-off analysis and decision matrix.
* 🛠️ **Read the Code Implementation:** [Creational Patterns: The Art of Instantiation](../../../clean-code/design-patterns/01-creational-patterns.md#the-singleton) — Production-grade Java with double-checked locking and thread safety.

# ⚖️ បទប្បញ្ញត្តិ និងការអនុលោមតាមច្បាប់ (Compliances)

ឯកសារណែនាំយោងសម្រាប់បទប្បញ្ញត្តិ ស្តង់ដារ និងក្របខ័ណ្ឌការងារដែលកម្មវិធីសូហ្វវែរនានាត្រូវតែអនុវត្តតាម។ ឯកសារនីមួយៗពន្យល់អំពីអត្ថន័យនៃបទប្បញ្ញត្តិ អ្វីដែលច្បាប់តម្រូវពីទិដ្ឋភាពវិស្វកម្មសូហ្វវែរ ទណ្ឌកម្មសម្រាប់ការខកខានមិនអនុវត្តតាម និងរបៀបបង្កើតប្រព័ន្ធដើម្បីអនុវត្តច្បាប់ទាំងនោះ។

Reference guides for the regulations, standards, and frameworks that software platforms must comply with. Each file explains what the regulation is, what it requires from a software engineering perspective, what the penalties are for non-compliance, and how to implement it.

---

## 📁 ក្រុមបទប្បញ្ញត្តិ (Groups)

| ថតឯកសារ (Folder) | វិសាលភាពគ្របដណ្តប់ (What It Covers) |
|:-------|:--------------|
| [data-privacy/](./data-privacy/) | GDPR, PDPA, CCPA, LGPD — សិទ្ធិទិន្នន័យអ្នកប្រើប្រាស់ ការយល់ព្រម ការរក្សាទុក និងកាតព្វកិច្ចលុបចោលទិន្នន័យ (User data rights, consent, retention, erasure) |
| [payment-and-financial/](./payment-and-financial/) | PCI-DSS, PSD2, AML/CFT, SWIFT — សន្តិសុខទូទាត់ប្រាក់ និងការបង្ការបទល្មើសហិរញ្ញវត្ថុ (Payment security and financial crime prevention) |
| [security-frameworks/](./security-frameworks/) | SOC 2, ISO 27001, OWASP ASVS, NIST — សវនកម្មសន្តិសុខ និងវិញ្ញាបនបត្រការពារ (Security audits and certifications) |
| [identity-and-kyc/](./identity-and-kyc/) | KYC, KYB, AML, eIDAS, FATF — ការផ្ទៀងផ្ទាត់អត្តសញ្ញាណ និងការត្រួតពិនិត្យទណ្ឌកម្ម (Identity verification and sanctions) |
| [healthcare/](./healthcare/) | HIPAA, HL7 FHIR, ម៉ាកសញ្ញា CE, FDA 21 CFR — ទិន្នន័យគ្លីនិក និងឧបករណ៍វេជ្ជសាស្ត្រ (Clinical data and medical devices) |
| [regional/](./regional/) | អាស៊ីអាគ្នេយ៍ អឺរ៉ុប អាហ្វ្រិក មជ្ឈិមបូព៌ា សហរដ្ឋអាមេរិក ឥណ្ឌា — ទិដ្ឋភាពទូទៅតាមប្រទេសនីមួយៗ (Southeast Asia, Europe, Africa, Middle East, USA, India — country-specific overviews) |
| [eu-specific/](./eu-specific/) | NIS2, DORA, MiCA, ePrivacy, HDS ប្រទេសបារាំង, ច្បាប់ EU AI Act — ក្របខ័ណ្ឌការងារក្រៅតំបន់សហភាពអឺរ៉ុប/ចក្រភពអង់គ្លេស (Supranational frameworks) |

---

## 🗺️ របៀបប្រើប្រាស់ឯកសារ (How to Use This)

ឯកសារនីមួយៗត្រូវបានរៀបចំឡើងតាមរចនាសម្ព័ន្ធដូចគ្នា៖
Each file follows the same structure:

1. **តើវាជាអ្វី (What it is)** — បទប្បញ្ញត្តិពន្យល់ជាភាសាសាមញ្ញ (The regulation in plain language)
2. **អនុវត្តចំពោះនរណា (Who it applies to)** — ប្រភេទផ្លែតហ្វម ឬក្រុមហ៊ុនដែលត្រូវជាប់កាតព្វកិច្ច (Which type of platform or company)
3. **តម្រូវការច្បាប់ (What it requires)** — កាតព្វកិច្ចជាក់លាក់ផ្នែកបច្ចេកទេស និងស្ថាប័ន (The specific technical and organisational obligations)
4. **ទោសទណ្ឌ (Penalties)** — ផលវិបាកក្នុងករណីខកខានមិនអនុវត្តតាមច្បាប់ (What happens if you don't comply)
5. **របៀបអនុវត្ត (How to implement it)** — ជំហានអនុវត្តជាក់ស្តែងផ្នែកវិស្វកម្ម និងប្រតិបត្តិការ (Practical engineering and operational steps)
6. **ឯកសារទាក់ទង (Related)** — តំណភ្ជាប់ទៅកាន់នីតិវិធី និងគំរូឯកសារដែលមានស្រាប់ក្នុងទីសន្និធិ (Links to procedures and templates already in this repo)

---

## 🔗 នីតិវិធីទាក់ទង (Related Procedures)

- [ការផ្ទៀងផ្ទាត់ដៃគូផ្តល់សេវា KYC / KYB (KYC / KYB Provider Verification)](../procedures/compliance-and-accounts/kyc/01-kyc-provider-verification.md)
- [ការលុបគណនី និងការរក្សាទុកទិន្នន័យ (Account Deletion & Data Retention)](../procedures/compliance-and-accounts/01-account-deletion-and-data-retention.md)
- [ខ្សែសង្វាក់នៃការបញ្ចូល និងផ្ទៀងផ្ទាត់ឯកសារ (File Upload & Validation Pipeline)](../procedures/compliance-and-accounts/02-file-upload-validation-pipeline.md)
- [ច្រកទ្វារទូទាត់ប្រាក់ (Payment Gateway)](../procedures/payments-and-revenue/01-payment-gateway.md)

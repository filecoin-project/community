# Filecoin Security

Having a vibrant community of security researchers auditing Filecoin and its dependencies is at the core of building a robust platform, mitigating risks and building trust in the Filecoin ecosystem. We invite security researchers acting in good faith to help us maintain a high standard of security.

This includes encouraging responsible vulnerability research and disclosure. This document sets out our definition of good faith in the context of finding and reporting vulnerabilities, our security procedure, and the bug bounty program.

For additional details and updates on Filecoin Security or the Bug Bounty Program - head over to the [Filecoin Security website](https://security.filecoin.io). 

## Vulnerability Reporting

Almost anything you find that is a bug in the codebase should be filed as an issue on Github. The exception is if you find a security vulnerability. If you discover a security issue, please bring it to our attention right away. We’ve created two main channels for reporting:

1. Sending an email to [security@filecoin.org](mailto:security@filecoin.org). Use our [key](https://github.com/filecoin-project/community/blob/master/public.key) to encrypt sensitive information.
1. Request to join the **filecoin_sec** team on [Keybase](http://keybase.io), where we can set up a private channel to discuss.

Please **DO NOT** file a public issue or discuss the vulnerability in public places like Slack, Twitter, etc. See our Disclosure Policy below to learn more about sharing details about vulnerabilities that have been found.

## Security Audits and Updates

Protocol implementations have undergone third-party Security Audits. They are linked in the Filecoin Specification under [Implementation Status](https://spec.filecoin.io/#intro__implementations-status).

## Bug Bounty Program

Reported security vulnerabilities will be eligible for a bounty based on severity, calculated based on their Impact and Likelihood using the [OWASP Risk Rating model](https://owasp.org/www-community/OWASP_Risk_Rating_Methodology).

The following is a guide for how points may be allocated to issues reported based on severity:

- Critical: up to 100,000 points
- High: up to 50,000 points
- Medium: up to 15,000 points
- Low: up to 2,500 points
- Note: up to 500 points

Currently, 1 point = 1 USD.

Higher rewards will also be paid to reported vulnerabilities that offer quality written descriptions, test code, scripts and detailed instructions, and well-documented fixes.

Evaluation of the significance of the vulnerability and specific bounty amount assigned is at the sole discretion of the Filecoin Security Team, which consists of core developers and contributors.

### Ground Rules

We encourage good-faith security research and ask that you follow these guidelines to avoid any confusion between legitimate research and malicious attack, we ask that you attempt, in good faith, to:

- Testing must not violate any law or compromise any data that is not yours. Please refrain from the following:
  - Denial of Service attacks and active exploits against the Filecoin network or Filecoin miners and nodes
  - Social engineering and phishing of Filecoin project contributors, contractors, ecosystem collaborators or community members
  - Physical or electronic attempts to access offices where project contributors work or data centers where Filecoin nodes are located
  - Compromising user accounts or stealing funds
- Report any vulnerability you’ve discovered promptly
- Help us improve this security process as it is critical to our mission by suggesting improvements.
- Avoid violating the privacy of Filecoin users and community members, disrupting their systems, destroying data, stealing funds and/or harming the user experience
- Perform testing only on in-scope systems, and respect systems and activities which are out-of-scope
- Interact only with test accounts you own or with explicit permission from the account holder
- If a vulnerability provides unintended access to data: Limit the amount of data you access to the minimum required for effectively demonstrating a Proof of Concept; and cease testing and submit a report immediately
- Play by the rules. This includes following this policy as well as any other relevant agreements
- Use only the Official Channels to discuss vulnerability information with us
- Handle the confidentiality of details of any discovered vulnerabilities according to our Disclosure Policy

### Safe Harbor

When conducting vulnerability research according to this policy, we consider this research conducted under this policy to be:

- Authorized in view of any applicable anti-hacking laws, and we will not initiate or support legal action against you for accidental, good faith violations of this policy
- Authorized in view of relevant anti-circumvention laws, and we will not bring a claim against you for circumvention of technology controls
- Exempt from restrictions in our Acceptable Usage Policy that would interfere with conducting security research, and we waive those restrictions on a limited basis
- Lawful, helpful to the overall security of the Internet, and conducted in good faith

You are expected to comply with all applicable laws. If legal action is initiated by a third party against you and you have complied with this policy, we will take steps to make it known that your actions were conducted in compliance with this policy.

If at any time you have concerns or are uncertain whether your security research is consistent with this policy, please submit a report through one of our Official Channels before going any further.

### Scope

In scope for our Bug Bounty program are vulnerabilities in the core protocol, protocol implementations, and some supporting libraries that may be widely used by developers. These include the following repos, but not only:

- Lotus Core
  - [filecoin-project/lotus](https://github.com/filecoin-project/lotus)
- Markets
  - [filecoin-project/go-fil-markets](https://github.com/filecoin-project/go-fil-markets)
  - [ipfs/go-graphsync](https://github.com/ipfs/go-graphsync)
- Storage Miner
  - [filecoin-project/lotus/tree/master/miner](https://github.com/filecoin-project/lotus/tree/master/miner)
- Actors
  - [filecoin-project/specs-actors](https://github.com/filecoin-project/specs-actors)
- Proofs
  - [filecoin-project/rust-fil-proofs-ffi](https://github.com/filecoin-project/rust-fil-proofs-ffi)
  - [filecoin-project/rust-filecoin-proofs-api](https://github.com/filecoin-project/rust-filecoin-proofs-api)
  - [filecoin-project/rust-fil-proofs](https://github.com/filecoin-project/rust-fil-proofs)
    - [filecoin-project/bellman/](https://github.com/filecoin-project/bellman/)
    - [filecoin-project/merkle_light](https://github.com/filecoin-project/merkle_light)
    - [filecoin-project/neptune](https://github.com/filecoin-project/neptune)
    - [filecoin-project/neptune-triton](https://github.com/filecoin-project/neptune-triton)
    - [filecoin-project/paired](https://github.com/filecoin-project/paired)
- Dependencies
  - [filecoin-project/go-address](https://github.com/filecoin-project/go-address)
  - [filecoin-project/go-amt-ipld](https://github.com/filecoin-project/go-amt-ipld)
  - [filecoin-project/go-bitfield](https://github.com/filecoin-project/go-bitfield)
  - [filecoin-project/go-cbor-util](https://github.com/filecoin-project/go-cbor-util)
  - [filecoin-project/go-crypto](https://github.com/filecoin-project/go-crypto)
  - [filecoin-project/go-data-transfer](https://github.com/filecoin-project/go-data-transfer)
  - [filecoin-project/go-fil-commcid](https://github.com/filecoin-project/go-fil-commcid)
  - [filecoin-project/go-padreader](https://github.com/filecoin-project/go-padreader)
  - [filecoin-project/go-sectorbuilder](https://github.com/filecoin-project/go-sectorbuilder)
  - [filecoin-project/go-statemachine](https://github.com/filecoin-project/go-statemachine)
  - [filecoin-project/go-statestore](https://github.com/filecoin-project/go-statestore)
  - [ipfs/go-hamt-ipld](https://github.com/ipfs/go-hamt-ipld)
  - [ipfs/go-ipld-cbor](https://github.com/ipfs/go-ipld-cbor)
  - [whyrusleeping/cbor-gen](https://github.com/whyrusleeping/cbor-gen)

### Out of Scope

- Filecoin websites and Filecoin infrastructure in general are not part of the bug bounty program.
- Third-party services and websites that show information about the Filecoin network (block explorers, stats dashboards, price indicators, miner leaderboards, etc.) are also out of scope.
- Vulnerabilities previously submitted by another person or identified in a published audit report are not eligible for bug bounty rewards.
- Public disclosure of a vulnerability makes it ineligible for a bug bounty.

Filecoin’s core development team, employees of Protocol Labs, the Filecoin Foundation and others paid by these organizations to work on the Filecoin project, indirectly or directly, are not eligible for bug bounty rewards.

### Disclosure Policy

We have a **Coordinated Disclosure policy**.  A researcher can share details of a vulnerability after a fix has been applied and our security team has provided permission to disclose. We will make a best effort to address and patch (if possible) all vulnerabilities within 90 days from submission. Please keep security vulnerabilities private until we have had a chance to address them.

If you have filed an issue and are interested in options for disclosing it, please reach out to us at security@filecoin.org.

### Expectations

When working with us according to this policy, you can expect us to:

- Work with you to understand and validate your report, including a timely initial response to the submission
- Work to remediate discovered vulnerabilities in a timely manner
- Recognize your contribution to improving our security if you are the first to report a unique vulnerability, and your report triggers a code or configuration change.

### Response Process

1. A security researcher reports a vulnerability via email to security@filecoin.org or Keybase.
1. Our security team will designate a Response Manager in charge of a particular report based on expertise and availability. They will acknowledge receipt of the report in a quick response to the researcher.
1. The Response Manager will evaluate the vulnerability and assign an initial OWASP Severity estimate. They may optionally also contact the researcher using a secure private channel for more information.
1. Based on the vulnerability’s potential OWASP Severity additional security team members will be alerted for additional review and to develop a patch.
    1. Response Manager designates a private git branch for the patch + proposed OWASP score
    1. Reviewed by security team
    1. Response Manager drafts vulnerability announcement for the community
        1. Severity - Systems impacted - Solutions / patches
    1. Security team discusses a release target + date for the announcement + patch
    1. Response Manager communicates with the researcher who submitted the vulnerability:
        1. Proposed patch + release date
        1. Whether the researcher would like public credit for reporting the bug (anonymous reporting is also supported)
        1. Reporter’s bounty distribution address
    1. The security team will make a best effort to complete the above process within 90 days.
1. Community notifications and patches
    1. For High or Critical Severity issues, the security team will notify the Filecoin community that a security release is imminent. Notifications can include Filecoin Community Slack announcements, tweets, emails to ecosystem collaborators. 
        1. 24 hours following this notification, the fixes are applied publicly and new releases are issued.
    1. Medium to High Severity issues may result in a minor release including the patch.
    1. Low severity issues can be addressed in the next regular release.

### Legal considerations

Reporters are responsible for all taxes and all awards subject to applicable law.

We are not able to pay bounty awards to individuals who are on a U.S. sanctions list or in a country on a U.S. sanctions list.

# #
 #https://vscode.dev/liveshare/EB75C9AEF18F1FA8606B04390CCFDC573A2B
> **@SwiftAdviser **

- > ![IMG_20230913_161109~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/20ddfe47-4c6c-40eb-957e-eb16ebbc3281)

![IMG_20230913_161141~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/8e7ce0a0-a88c-45d8-9662-53263dce9f9f)

![IMG_20230913_155913~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/671ec242-30ba-4930-b3d1-066a1eb1ce68)

![IMG_20230913_161041~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/2abbb0e4-a9f8-494f-a864-5296684eb351)

![IMG_20230913_161209~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/5dbb0628-ddd5-4784-abf7-cddb86d16987)

![IMG_20230913_160111~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/02a1450e-680c-46bc-aec1-c78e1959c9ec)

![IMG_20230913_160018~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/9670ae5c-49a1-4b6a-896e-9bb6de3b1651)

![IMG_20230913_160211~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/c258f7a5-5caa-4c3f-9b74-8cdc1a6465e0)

![IMG_20230913_155211~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/ce38dee4-f8bf-4d6b-a535-14ed140d4bdc)

![IMG_20230913_160938~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/91fe573d-ac50-4f69-9fe2-37677b3fef16)

![IMG_20230913_155825~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/c574c53a-2632-4cf6-ba10-4874b8cf8d64)

![IMG_20230913_161012~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/fbed05cc-6db9-4da6-afcb-859e90a14d0f)

![IMG_20230913_160835~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/e2aaa28e-0d9a-4fca-bb75-b021e9f0a5e5)

![Cargando IMG_20230913_153515~2.jpg …]()

![IMG_20230913_160908~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/44542e5f-6218-4bcd-8103-f8eb07971f6c)

![IMG_20230913_160732~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/79ced02b-b01a-4425-ad07-db28f7132435)

![IMG_20230913_160758~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/8d25327d-e01a-4009-a531-8300bb348ad9)

![IMG_20230913_160613~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/0c86bdf4-e054-4c75-a801-bd69f6470b48)

![IMG_20230913_161342~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/72d6e640-3081-4abc-87ce-9ddf2770dc83)

![IMG_20230913_160651~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/d3b6b1d5-3391-4f3a-b5e1-a1c7282433b6)

![IMG_20230913_160453~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/c2b0a5bd-e6d0-4489-8bbb-5f1277a9ab0b)

![IMG_20230913_161429~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/c527b216-5894-4f35-9eae-25e949386cbd)

![IMG_20230913_161221~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/e92ffc34-f5bb-4d8a-a639-994bf3d441b2)

![IMG_20230913_160542~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/64730f55-c9c5-4599-b048-691b371b96dd)

![IMG_20230913_160254~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/c04f96a1-5708-46f5-9ae5-c756a65b32d4)

![IMG_20230913_161303~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/5bdf1620-59e4-4622-93ec-3968c1b93c03)

![IMG_20230913_160348~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/34001aa8-7802-4a85-b802-a21baad3c78b)

![IMG_20230913_161121~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/b25a0390-8d26-4cc7-baff-69b7a719b5e3)

![IMG_20230913_160137~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/4cb1231f-f5af-4f93-9d73-195afcd7cde6)

![IMG_20230913_161156~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/3429661e-92ec-4e3c-9780-92e9840605be)

![IMG_20230913_160225~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/ae0da76c-0d5b-4fd2-a2ca-ada69af1058f)

![IMG_20230913_161025~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/cbaa6fa1-0a33-48cc-a2b9-986fa3b44c29)

![IMG_20230913_155942~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/e2c4f25c-a9b2-4d23-a759-0b1ca6e60462)

![IMG_20230913_161055~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/c94bf756-d389-4eb8-abb5-5009615e8221)

![IMG_20230913_160045~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/18de1f5d-7e8c-4d47-b9e5-3b097fff55c7)

![IMG_20230913_160919~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/68be784d-4882-482b-99f3-88820cb44e36)

![IMG_20230913_155232~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/b331c652-895e-4911-bd71-51807d2be205)

![IMG_20230913_160951~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/6a312392-6343-4280-a4f9-353b7352df80)

![IMG_20230913_155844~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/4e9ba0![IMG_20230913_160852~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/783c4e55-7f42-4f55-90f3-0beb7e0ddaa8)

 IMG_20230913_160812~2.jpg …]()

![Cargando IMG_20230913_160852~2.jpg …]()

![IMG_20230913_153542~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/6976d5af-365c-42d3-8b19-184a84518843)

![IMG_20230913_160705~2.jpg](https://github![IMG_20230913_160741~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/d571daa8-e5e2-4412-ba4b-5dcd3f3187fd)

de-acc1-4802-979b-d5ed551a5e5f)

![Cargando IMG_20230913_160741~2.jpg …]()

![IMG_20230913_160555~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/beef1a49-8534-4e60-a59a-52fdf63b1178)

![IMG_20230913_160630~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/f390b752-e715-4ea9-9402-1e8e22fe1f28)

![IMG_20230913_160420~2.jpg](https://github![IMG_20230913_161415~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/44b69cd5-4872-4e43-900e-ad609fa1da4e)

b9-beec-4aa2-a22a-e69bd579909d)

![Cargando IMG_20230913_161415~2.jpg …]()

![IMG_20230913_160506~2.jpg](https://github![IMG_20230913_160232~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/00220a2d-d55f-4ce2-a46f-671785db7bef)

9e-ff08-44b5-bce4-6154a970c0d5)

![Cargando IMG_20230913_160232~2.jpg …]()

![IMG_20230913_161246~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/7775d1![IMG_20230913_161329~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/b28c8fd5-9242-4b96-aebf-854700ede0ea)

0913_160315~2.jpg](https://github.com/ton-connect/sdk/assets/42362168/c6902919-bd5a-4050-87b9-84940aca59f7)

![Cargando IMG_20230913_161329~2.jpg …]()



- [ ] ### **@ramoncerdaquiroz**

> 
# #
 #https://vscode.dev/liveshare/EB75C9AEF18F1FA8606B04390CCFDC573A2B
> **@JonLim**

**@doches @jobwat @ramoncerdaquiroz @zenangst @olivierlefloch **

> 

- [ ] ### **@Endogen **

> 

**_[]()![LICENSE(1).md](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598107/LICENSE.1.md)

![README(1).md](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598104/README.1.md)

![{9C03ADD5-BF70-B944-FE4F-8462BCD6738B}.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598108/9C03ADD5-BF70-B944-FE4F-8462BCD6738B.pdf)

![GoogleFinance.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598111/GoogleFinance.pdf)

!{[DOCUMENTATION.md]}[github-recovery-codes.txt](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598105/github-recovery-codes.txt)

![CEQR800906HMNRRM03.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598106/CEQR800906HMNRRM03.pdf)

![README(2).md](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598109/README.2.md)

![CONTRIBUTING.md](http![CODE_OF_CONDUCT.md](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598110/CODE_OF_CONDUCT.md)

urce-mac-os-apps/files/12598112/CONTRIBUTING.md)

![Cargando CODE_OF_CONDUCT.md …]()

_**


## Breve Historia del

Billete Mexicano

Gracias a la enorme riqueza minera del Virreinato de la Nueva España, durante los trescientos años de vida colonial en México, el circulante monetario estuvo formado exclusivamente por monedas metálicas de oro, plata y, en menor grado, de cobre. La aparición del papel moneda en México no se dio sino hasta el siglo XIX, una vez consumada la Revolución de Independencia.

Antecedentes.

La Revolución de Independencia iniciada en 1810 trastornó el orden político y social del Virreinato de la Nueva España y provocó una profunda crisis económica, producto del abandono de las minas (pilar de la economía) y de la repatriación de capitales a la Península Ibérica. De esta manera, la falta de numerario se convirtió en un problema más de la convulsionada colonia. Surgieron entonces numerosas acuñaciones de necesidad y el primer papel moneda de México, cuando en 1813, en San Miguel el Grande, Guanajuato, aparecieron unas curiosas piezas de cartón anaranjado con la denominación de medio real, de las que se desconocen con certeza sus emisores. Otro antecedente del billete mexicano lo encontramos a finales del siglo XVIII, en la entonces colonia española de Luisiana, donde se emitieron billetes de varias denominaciones.



Piezas de cartón emitidas en 1813

El Billete del Primer Imperio.

Al consumarse la Independencia en 1821, México adoptó un gobierno monárquico encabezado por el caudillo criollo Agustín de Iturbide, quien enfrentó una severa penuria económica, producto de los once años de guerra. Para resolver esa situación, Iturbide ensayó diversos mecanismos: concedió grandes facilidades a la producción minera, recurrió a préstamos forzosos, al descuento de los sueldos de civiles y militares y al incremento de los impuestos; sin embargo, los resultados de tales disposiciones no fueron los esperados para solventar los crecientes gastos de la Corte e incluso resultaron contraproducentes, ya que incrementaron el desprestigio del Emperador. Como recurso extremo se recurrió a la emisión de papel moneda (20 de diciembre de 1822). Estos billetes, que son la primera emisión oficial mexicana, se consideran también los primeros provisionales entre los billetes de necesidad de este país. Estas piezas están impresas por una sola cara, en papel blanco de forma casi cuadrada, ostentan la leyenda IMPERIO MEXICANO y se emitieron en las denominaciones de 1, 2 y 10 pesos. La suerte de los billetes no fue distinta a la de las otras disposiciones dictadas por el gobierno imperial: jamás fueron aceptados por el público usuario, acostumbrado al manejo de moneda metálica; además, se prestaron a malos manejos entre funcionarios y pagadores y se sumaron a los motivos de descrédito de este gobierno. Muchas fueron las causas de la rápida caída del régimen iturbidista, pero ,sin duda, el fracaso de su política hacendaria y monetaria fue fundamental.



Primera emisión oficial mexicana de billetes

El Billete Republicano de 1823.

En 1823, México se constituyó en República Federal. El nuevo gobierno intentó enmendar los errores hacendarios del Imperio y restaurar la confianza del público en los manejos financieros del gobierno; así, terminó con los préstamos forzosos y retiró de la circulación al billete imperial, entre otras medidas. Sin embargo, la grave penuria del erario no se resolvió y se decidió, nuevamente, emitir papel moneda para el financiamiento estatal. En esta ocasión, para intentar frenar el rechazo popular a este medio de pago, se acordó imprimirlo en bulas papales canceladas, que se esperaba que fueran aceptadas debido a la religiosidad del pueblo mexicano. El resultado no fue diferente al obtenido por Iturbide: los billetes no fueron aceptados por el público y pronto tuvieron que ser retirados de la circulación.

	
Billetes republicanos

Los Bancos Privados de Emisión.

Varias décadas hubieron de transcurrir después de los fracasos monetarios del Imperio y de la República, para que se aceptara el papel moneda en México. No fue sino hasta 1864, durante el Imperio de Maximiliano de Habsburgo, cuando se retomó el proyecto emisor de billete, pero ahora bajo condiciones distintas: el responsable de la emisión sería un banco privado, El Banco de Londres, México y Sudamérica, y los billetes serían de aceptación voluntaria. En esta ocasión, el éxito del billete fue grande; incluso, en ciertos medios, llegó a ser preferido a la moneda metálica.



Billetes emitidos por el Banco de Londres, México y Sudamérica

A la caída del Imperio y con la Restauración Republicana la emisión de billete encontró condiciones favorables, especialmente durante el largo gobierno del general Porfirio Díaz (1877-1911). Entonces se estableció, conforme a la Ley de Instituciones de Crédito de 1897, un firme, funcional y organizado sistema bancario en el que cada estado de la República contó con, cuando menos, un banco privado emisor de billete, además del Banco Nacional de México con presencia en la República entera y del de Londres y México, cuya concesión fue ratificada. Los billetes emitidos por estas dos instituciones circulaban nacionalmente, en ocasiones, revalidados en los diferentes estados.



Billetes emitidos por el Banco Nacional de México

De esta manera, México adoptó al billete como medio pago de aceptación generalizada. Los billetes de estos bancos se emitieron, con el respaldo metálico correspondiente, en denominaciones de 1, 5, 10, 20, 50, 100, 500 y 1000 pesos y eran fabricados por empresas extranjeras especializadas como Bradbury, Wilkinson & Company, American Bank Note Company y American Book & Printing Company. Al fin, el billete de banco fue aceptado por el público usuario.



Billetes emitidos por diferentes bancos privados

El Billete Durante la Revolución de 1910.

La Revolución antiporfirista iniciada en 1910 habría de llevar a México, nuevamente, la escasez de numerario y el descrédito del billete de banco. Con la lucha armada se retiraron de la circulación enormes cantidades de moneda metálica y, por si fuera poco, resurgió el rechazo al billete de banco.

El general Victoriano Huerta - quien a través de un golpe de estado destituyó y asesinó, en febrero de 1913, a Francisco I. Madero, Presidente Constitucional de los Estados Unidos Mexicanos - ordenó a los bancos privados de emisión entregar el respaldo metélico de los billetes a su gobierno y emitir cantidades desorbitadas de billetes sin ningún respaldo. Así, el sistema bancario mexicano construido con grandes dificultades se desmoronó rápidamente y con él, el uso y la aceptación del billete.

No obstante, la falta de numerario obligó a autoridades municipales, a jefaturas militares y a comerciantes, mineros y hacendados a emitir piezas de necesidad. De tal forma que de 1913 a 1915 reapareció en México la moneda de necesidad: se acuñaron diversas piezas metólicas en distintos puntos de la República, pero sobre todo se multiplicaron las emisiones de papel. El primero en emitir este tipo de piezas fue Venustiano Carranza, Primer Jefe del Ejército Constitucionalista y caudillo de la lucha antihuertista; quien, a su vez, autorizó a numerosos jefes revolucionarios la emisión de sus propios billetes, vales y cartones para allegarse fondos de campaña.



Primer billete emitido por el Gobierno Constitucionalista

Las características formales de estos billetes son sumamente variables; existen algunos de gran calidad y otros de burda factura. Las numerosas emisiones y variedades, lejos de resolver el problema monetario de la República, lo complicaron. Estas piezas, a las que el pueblo mexicano denominó genéricamente "bilimbiques", únicamente valían en tanto su emisor ejercía el poder y la autoridad en una determinada región. A la derrota del general Huerta, la situación se complicó con el enfrentamiento entre las distintas facciones revolucionarias. Los "bilimbiques" se devaluaban continuamente; además, aparecieron nuevas emisiones como las del Gobierno Provisional de México emitidas en Veracruz o las de la Convención Revolucionaria de la ciudad de México; la falsificación masiva de estas piezas contribuyó a acrecentar el problema monetario de México y el descrédito del papel moneda.



Ejemplos de "bilimbiques"

Conforme se consolidaba el dominio de la facción carrancista, ésta emprendió varios intentos para solucionar el problema monetario del país: el único papel moneda válido sería el emitido por los carrancistas y, para protegerse de las falsificaciones, se ordenó la fabricación de billetes mucho más sofisticados a la American Bank Note Company de Nueva York. Estos billetes se pusieron en circulación en mayo de 1916, en tanto se iniciaba el retiro paulatino de las emisiones anteriores. A estos billetes se les conoce como "infalsificables", pero su destino no fue muy distinto al de las emisiones revolucionarias anteriores, ya que sufrieron una devaluación fulminante y para fines de ese mismo año ya eran inutilizables. Ante estas vicisitudes lo único seguro era la muy rara y escasa moneda metálica, ya que las emisiones de papel únicamente estaban respaldadas por la fuerza de las armas que, si sufrían un descalabro, dejaban en completo desamparo a sus tenedores.



Billetes infalsificables

De esta forma, en los últimos meses de 1916, Carranza decretó que se pagara a los trabajadores exclusivamente con moneda metálica, cuya acuñación se reinició en la Casa de Moneda de México. Así, mientras Carranza se consolidaba militarmente, la solución al problema monetario de México se vislumbraba en el horizonte.

La reconstrucción de la República planteaba nuevas problemáticas, una de ellas el establecimiento de un nuevo sistema bancario en el país. En este sentido, el primer paso fue la declaración de quiebra y la liquidación de los antiguos bancos porfirianos y, el segundo, el establecimiento de un nuevo emisor.

En al artículo 28 de la Constitución Política de los Estados Unidos Mexicanos, promulgada en febrero de 1917, se establece que el monopolio de la emisión correspondería a un Banco único bajo control gubernamental; sin embargo, siete años hubieron de transcurrir antes de la fundación de este Banco, que tendría entre sus funciones primordiales la emisión de billete.

El Billete del Banco de México.

Tabla de resumen: 

El Banco de México inició sus funciones el 1 de septiembre de 1925, gracias a los esfuerzos presupuestales y de organización del entonces presidente de la República, Plutarco Elías Calles. Entre las funciones del recién fundado Banco Central estaban la emisión y la regulación de la circulación monetaria. Restaurar la confianza de los usuarios en el billete fue uno de los principales problemas que hubo de enfrentar el Banco de México al emitir sus primeras piezas de papel moneda, las cuales fueron, en un principio, de aceptación voluntaria para restaurar paulatinamente el uso y la confianza pública en este medio de pago.

Los primeros billetes del Banco de México fueron impresos por American Bank Note Company de Nueva York (ABNC), en un tamaño de 180 x 83 mm. Esta primera serie (1925-1934) está compuesta por billetes de 5, 10, 20, 50, 100, 500 y 1000 pesos.



Primeros billetes del Banco de México; impresos por la Amercican Bank Note Company

Posteriormente, de 1936 a 1942, se emitió una segunda serie, transitoria, también fabricada por la casa neoyorquina, pero de un tamaño más reducido (157 x 67 mm.); los billetes de 5 y 10 pesos de esta serie conservaron los diseños anteriores, mientras que en los de 50 y 100 pesos se adoptaron nuevos diseños en donde aparecieron por vez primera en las emisiones del Banco de México, las figuras de nuestros próceres.



Billetes de transición

Primeros del Banco de México con imágenes de personajes históricos por los de 50 y 100 pesos

Paralelamente a la serie anterior, se puso en circulación una tercera serie (1936-1978), igualmente impresa por ABNC. Las denominaciones emitidas fueron las de 1, 5, 10, 20, 50, 100, 500, 1000 y 10000 pesos. La novedad de esta serie fue la inclusión del billete de 1 peso, que es el único de esta denominación que ha emitido el Banco de México en toda su historia.



Tercera emisión de billetes del Banco de México impresos por la American Bank Note Company

En 1969, se abre un nuevo capítulo en la historia del billete mexicano, ya que en ese año inició sus actividades la Fábrica de Billetes del Banco de México. Así, surgió una nueva generación de billetes mexicanos, hecha con el respaldo tecnológico más avanzado de su momento y conforme a diseños,iconografía y concepciones distintas a las prevalecientes hasta entonces. Esta cuarta serie (1969-1991), primera de fabricación nacional y conocida como Tipo A, estuvo integrada por billetes de 5, 10, 20, 50, 100, 500, 1000, 2000, 5000, 10000, 20000, 50000 y 100000 pesos.



Billetes de la familia A, impresos por la Fábrica de Billetes del Banco de México

Con el objetivo de simplificar el manejo de cantidades en moneda nacional, por decreto del 18 de junio de 1992, se creó una nueva unidad del Sistema Monetario de los Estados Unidos Mexicanos, equivalente a mil pesos de la unidad anterior. Para distinguirla de la anterior unidad monetaria a la nueva unidad se le antepuso, transitoriamente, el adjetivo "nuevo" el cual se eliminó a partir de 1996. El Banco de México emitió, durante 1992, una nueva serie de billetes en las denominaciones de 10, 20, 50 y 100 en los que aparece el adjetivo "nuevo" antepuesto al nombre de la unidad. Estos billetes,conocidos como Billetes Tipo B, se caracterizan por conservar el diseño de los billetes anteriores.



Billetes de la familia B

A finales de ese mismo año se inició la impresión de otra serie de billetes, también con la leyenda "nuevos pesos", pero con nuevos diseños. Esta serie está integrada por los billetes de 10, 20, 50, 100, 200 y 500, de los cuales los tres primeros miden 129 x 66 mm. y los tres últimos 155 x 66 mm. A estos billetes se les conoce como Billetes Tipo C.



Billetes de la familia C

Para concluir este proceso, se eliminó el adjetivo "nuevo" en la denominación de la última serie de billetes emitidos por el Banco de México (de 1994 a 2001). Esta serie conserva los mismos diseños de la anterior, pero ya no se antepone el adjetivo "nuevos" al nombre de la unidad. Existen billetes de 10, 20, 50, 100, 200 y 500 pesos, con las características antes señaladas y se conocen como Billetes Tipo D.



Billetes de la familia D

Posteriormente, en octubre de 2001 se puso en circulación una nueva emisión de billetes (conocida como Billetes Tipo D1) que conserva los mismos diseños pero incorpora nuevos elementos de seguridad, ademós de los ya existentes. Esta emisión se sumó a los billetes en circulación en las denominaciones de 50, 100, 200 y 500 pesos.



Billetes de la familia D1

A partir del 30 de septiembre de 2002, se pusieron en circulación billetes de 20 pesos impresos en polímero en lugar de papel. El polímero, por ser un material más durable, se incorporó en estos billetes de baja denominación, ya que son los que se deterioran con mayor rapidez. Estos billetes también se elaboran en la Fábrica de Billetes del Banco de México y, en apariencia, son similares a los de papel, pero cuentan con una característica distintiva de seguridad: una ventana transparente.

El 15 de noviembre de 2004 se puso en circulación el billete de papel de 1000 pesos correspondiente al Tipo D1, con el propósito de facilitar al público la realización de algunas transacciones en efectivo.



Billetes de 20 pesos (D1, polímero), 1000 pesos (D1, papel)

A partir de noviembre de 2006 se inició la emisión de la familia de billetes Tipo F. la cual presenta cambios en los elementos de seguridad, en los colores y tamaños. Cada denominación es de un color diferente para que el público pueda diferenciarlos fácilmente. Los billetes son de tamaño distinto para ayudar a los invidentes a identificar las diferentes denominaciones; todos miden 66 mm de ancho y varían en el largo. El billete de más baja denominación (20 pesos) es el más pequeño con 120 mm, y el de más alta (1,000 pesos) es el más largo con 155 mm. Entre cada una de las seis denominaciones (20, 50, 100, 200, 500 y 1,000) se mantiene una diferencia de 7 mm. Los billetes de 20 y 50 pesos se imprimen en polímero mientras que el resto se imprime en papel de algodón.

A partir del día 6 de mayo de 2013, el Banco de México puso en circulación un nuevo billete de 50 pesos que incorpora elementos de seguridad novedosos realizados con la más avanzada tecnología y otras variantes respecto del billete de la familia F de la misma denominación. Este nuevo billete, al igual que su antecesor, está impreso en sustrato de polímero; su color predominante es el magenta, tiene las mismas dimensiones: 66 mm de alto por 127 mm de largo, y conserva como motivo principal en el anverso la efigie de José María Morelos y Pavón. Este nuevo billete es de la familia F1 debido a que es una variante del billete F.

Dentro de la familia F de billetes también se encuentran billetes de emisión única. Se trata del billete de cien pesos, conmemorativo del centenario del inicio de la Revolución Mexicana (impreso en polímero); del billete de 200 pesos, conmemorativo del bicentenario del inicio de la Independencia de México (impreso en papel de algodón), y del billete de 100 pesos conmemorativo del centenario de la promulgación de la Constitución Política de los Estados Unidos Mexicanos del 5 de febrero de 1917. Estos billetes son de curso legal y no sustituyen a las denominaciones comunes de 100 y 200 pesos. Conforme se vayan deteriorando, los billetes conmemorativos se irán retirando de la circulación. El hecho de haber emitido pocas piezas es una invitación al público para conservarlos por su excelente diseño y calidad.



Billetes de la familia F

El 27 de agosto de 2018, se puso en circulación el billete de 500 pesos de la familia G, el primero de una nueva familia de billetes con mejoras en sus caracterÃ­sticas de seguridad, funcionalidad y durabilidad. Los motivos temáticos representados en los diseños aludirán a los procesos históricos que nos han definido como nación, y por primera vez, enfatizarán la riqueza natural que se encuentra distribuida a lo largo del territorio nacional. En los anversos, en cada denominación se representará uno de los siguientes procesos históricos: el México Antiguo, la Colonia, la Independencia, la Reforma y la Restauración dela República, la Revolución y el México Contemporáneo. En los reversos, se plasmarán los seis ecosistemas más representativos de nuestra geografía: ríos y lagos, bosques templados, selvas secas, matorrales y desiertos, costas, mares e islas, y selvas húmedas, a través de sitios reconocidos en la lista del "Patrimonio Mundial" de la Organización de las Naciones Unidas para la Educación, la Ciencia y la Cultura (UNESCO). También en el reverso de cada billete de la familia G habrá un elemento de fauna y flora identificado con cada uno de los seis ecosistemas. Los billetes dde la familia G miden 65 mm de ancho y tienen una variación de 7 mm de longitud entre una y otra denominación consecutiva. El billete de 200 pesos mide 139 mm de largo, el de 500 pesos mide 146 mm, y el de 1,000 pesos mide 153 mm; los tres se imprimen en papel de algodón. El billete de 100 pesos mide 132 mm y el de 50 pesos mide 125 mm; estos dos se imprimen en polímero.

Dentro de la familia G de billetes también se encuentra un billete de emisión única. Se trata del billete de 20 pesos, conmemorativo del bicentenario de la Consumación de la Independencia Nacional (impreso en polímero). Este billete mide 120 mm y es de curso legal.



Billetes de la familia G



Mesurez votre audience


## Cenumex
Buscar Productos...
Mi carrito 
0 artículos , $0.00
Compra numismática con confianza.

Mexico.1Real.1556-98
$3,000.00

Peso Balanza Mo 1869 C – Clave
$7,000.00

5 Reichsmark, Alemania 1927
$1,200.00

Medalla.Mexico.2/Onzas.1992.Morelos
$1,750.00

Oaxaca.5Pesos.1916
$175.00

8 Reales República Ga 1880 JA
$2,500.00

Potosí.2Reales.1863
$2,000.00

Mexico. 5 centavos. 1915
$240.00

Peso 1935
$250.00

Medalla 70 Aniversario SONUMEX
$750.00 – $2,500.00

Mexico. 10 centavos. 1935
$800.00

Chihuahua.1Peso.1913
$150.00

Medalla.Pisa,Italia.1897
$1,200.00

Medalla.MoMaximiliano
$1,000.00

Países bajos.1 Gulden. 1923
$190.00

10 centavos, Chihuahua, 1915
$220.00

Mexico. 5000 pesos.1980
$300.00

USA.10 onzas Troy
$7,250.00

Chihuahua.25Cents.
$300.00

Francia.1/2Franco.1808
$1,100.00

Peso 1919
$2,500.00

Mexico.100Pesos.2014
$750.00

Rusia.100Rublos.2018
$225.00

1 real 1777
$700.00

Mexico.8Reales.1746.Columnario
$13,000.00

Chiapas.10Pesos.2005
$1,250.00

Colección.5Piezas.Chichén.Itza.2007
$15,000.00

familia billetes AA. varios años
$150.00
Buscar Productos...
Categorías
Billetes (64)
Impresos (13)
Insumos (6)
Medallas (82)
Monedas (164)
Acerca de
Nosotros
Aviso de privacidad
Cookies
Términos y condiciones de uso
Código de ética para vendedores
Ayuda
Mi Cuenta
Quiero abrir mi tienda en Cenumex
Contacto
Ayuda al cliente
Lo que no se puede publicar
Síguenos
Facebook
Instagram
Youtube
Centro Numismático de México y Cenumex son marcas registradas de Haifurai S.A de C.V.® ❘ México 2023  

> # - [ ![annotated.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/7ba103eb-92f1-40d4-9151-71d3c8d9de66)

![file.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/e4114fa3-b920-40c9-8820-e86f901734ce)

![minus.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/c4f63322-d7dd-45aa-8f16-c802a8bdfb49)

![dragons_original.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/e76ccf4e-55b8-4acf-ab3e-93659cb858d1)

![deepalchemy.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/c38d73c8-1e1a-4b27-9d4a-dc4f898f4318)

![sqla_engine_arch.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/2ff45fea-85b2-41ec-8ede-4e02ed24b1d8)

![nonannotated.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/01a3e4a6-c08e-42f0-bb18-aae581203aec)

![dragons.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/9317a0ed-c795-4756-83c7-0a91806ec06c)

![space_invaders.jpg](https://github![sqla_arch_small.png](https://github.com/serhii-londar/open-source-mac-os-app![Compete-river-3__18___1_.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/98207174-13f9-4ff5-9d82-8cc1a4065141)

c58ff13b)

-apps/assets/42362168/64a793a9-ca64-4906-8fc2-32e4afa6f8d1)

![Cargando sqla_arch_small.png …]()

![Compete-river-3__8_.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/c1608348-aa56-4466-828a-4819a7823230)

![Cargando Compete-river-3__18___1_.png …]()

![20230905_061918.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/0032f7a9-4ba4-4dc9-b8c2-3eb48b36cd8d)

<!-- Error al cargar github-git-cheat-sheet.pdf -->![{9C03ADD5-BF70-B944-FE4F-8462BCD6738B}.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598242/9C03ADD5-BF70-B944-FE4F-8462BCD6738B.pdf)

![Zoom-Security-White-Paper.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598241/Zoom-Security-White-Paper.pdf)

<!-- Error al cargar Zoom Contact Center Data Transfer Impact Assessment (DTIA) - Dec 2<!-- Error al cargar Artificial Intelligence A Modern Approach (3rd Edition).pdf ( PDFDrive ).<!-- Error al cargar Ramón Cerda Quiroz 2_7_2023, 10_12_12.pdf -->_12.pdf …]()

<!-- Error al cargar Zoom Data Transfer Impact Assessment (DTIA)_May 2022-2.xlsx --><!-- Error al cargar Rubin-Statement-before-the-Tom-Lantos-Human-Righ<!-- Error al cargar Zoom Product Web Pages VPAT.pdf -->Pages V![seven-principles-07-01-09.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/125982<!-- Error al cargar google_terms_of_service_es-419.pdf -->argando thomas_kurian_goldman_sachs_presentation![alphabet-certificate-of-Incorporation.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598253/alphabet-certificate-of-Incorporation.pdf)

.pdf …]<!--![Zoom Rooms v5.0.2 for Windows VPAT.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598255/Zoom.Rooms.v5.0.2.for.Windows.VPAT.pdf)

al cargar Zoom Rooms Controller v5.0.2 for iPad VPAT.pdf -->n.pdf …]()

![Cargando Agency_Package_Request_Form.pdf …]()

![Cargando Zoom Rooms Controller v5.0.2 for <!-- Error al cargar GitHub.com.ISO.27001.Certification (1).pdf --> VPAT.pdf …]()<!-- Error al cargar Ecma_rules_june_2022.pdf -->1.Certification.pdf -->![Cargando GitHub.com.ISO.27001.Certification (1).pdf …]()

![Cargando Ecma_rules_june_2022.pdf …]()

<!-- Error al cargar right-to-be-terms-of-use-clean-28-feb-2023-1.pdf -->![Securing Your Zoom Meetings.pdf](https:![GitHub.com.ISO.27001.Certification.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598257/GitHub.com.ISO.27001.Certification.pdf)

/12598259/Securing<!-- Error al cargar AWS_Customer_Agreement_Spanish_2023-01-20.pdf -->stants.pdf<!-- Error al cargar DOC-20230613-WA0044. --> …]()

![Cargando AWS_Customer_Agreement_Spanish_2023-01-20.pdf …]()

![Cargando GitHub.com.ISO.27001.Certification.pdf …]()

<!-- Error al cargar tvm.pdf -->![T![edpb_guidelinesinterplaychapterv_article3_adopted_en.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598270/edpb_guidelinesinterplaychapterv_article3_adopted_en.pdf)

edge (SORTEE 2022).pptx](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598262/The.Open.Climate.Campaign.opening.access<!-- Error al cargar Ecosystem Infra 2017 Q4 OKRs.docx -->![Documento sin título.docx](https://github.com/serhii-londar![🖥️🔞𝙃𝙄𝙎𝙏𝙊𝙍𝙄𝘼𝙇 𝘿𝙀 𝙇𝘼 𝘿𝙀𝙀𝙋.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/729a1c96-8d55-41dc-bbe5-970969e71fc3)

x)

hapterv_article3_adopted_en.pdf …]()

![Cargando Ecosystem Infra 2017 Q4 OKRs.docx …]()<!-- Error al cargar 023.pdf -->n títu![OpenJS-Foundation-OVERVIEW-August-2021.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598268/OpenJS-Foundation-OVERVIEW-August-2021.pdf)

021.pdf …]()

![Cargando 🖥️🔞𝙃𝙄𝙎𝙏𝙊𝙍𝙄𝘼𝙇 𝘿𝙀 𝙇𝘼 𝘿𝙀𝙀𝙋.png …]()

<!-- Error al cargar CDP_2022_Non-Disclosure_Campaign_Report_18_01_23.pdf -->![Cargando 023.pdf …]()

![Ggmon.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598314/Ggmon.pdf)

![repository-open-graph-template.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/e9511958-6ea6-4663-9d7a-2eb0748b2c8b)

![Trademarks List FY22Q3.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598311/Trademarks.List.FY22Q3.pdf)

![Visual-Studio-2022-Enterprise-Professional-License_ESES.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598313/Visual-Studio-2022-Enterprise-Professional-License_ESES.pdf)

![channels4_profile (1).jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/c44a7a83-2d82-4a7e-98d8-6b283f1388ec)

![FOLLETO DE GGMON.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598312/FOLLETO.DE.GGMON.pdf)

![Eric_Qian_cs_Resume_latest.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598315/Eric_Qian_cs_Resume_latest.pdf)

![Factura_A84419.pdf](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598335/Factura_A84419.pdf)

![mama.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/271b3aef-e8e4-48f5-9b23-27f5f8921e35)

![Screenshot_20230706_185018.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/a5f20033-ef7f-48d0-abb2-58be5857faf4)

![Screenshot_20230620-151858.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/7b3cd516-de16-49a9-ada4-dbc27b52fa76)

![Screenshot_20230704_192117.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/f0b9e4ab-f122-48f6-83f4-7572157c7f2b)

![Screenshot_20230705_195202.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/418ca06f-6381-4b3c-912c-b64d31a5b197)

![20220803_211523.txt](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598366/20220803_211523.txt)

![9df1532e-635e-4f85-affe-9f8223d1b8ac.gif](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/b6b451cc-c59f-4efc-96ee-5d35f20a444f)

![¿De dónde es usted_ Page-1-[1688450133203].png](https://github![#zoomgay #gayzoom #fumesgay #fumeszoom.  https___us05web.zoom.us_wb_doc_Oxw5goeTQ4m4f9xru4E8XA_p_265264140451840 Page-1-[1687963804070].png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/d4a64412-7dc4-4b7a-ada5-d5175ad1b55c)

![#zoomgay #gayzoom #fumesgay #fumeszoom.  https___us05web.zoom.us_wb_doc_Oxw5goeTQ4m4f9xru4E8XA_p_265264140451840 Page-1-[1688313223010].png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/3dd80574-d45a-4e02-8a47-ae21c1068711)

_us05web.zoom.us_wb_doc_Oxw5goeTQ4m4f9xru4E8XA_p_265264140451840 Page-1-[1688313223010].p![#zoomgay #gayzoom #fumesgay #fumeszoom Page-1-[1687963775106].png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/878af72f-337d-475f-b574-7dd630![Hoja de ruta de características del producto Page-1-[1688450427013].png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/0ae3371f-b7ff-41a7-a0a4-ba0469694bd4)

://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/2bf2517a-9cba-48e0-a497-6e55313fe76d)

84c-a46d-322241339212)

![Cargando #zoomgay #gayzoom #fumesgay #fumeszoom Page-1-[1687963775106].png …]()

![Cargando Hoja de ruta de características del producto Page-1-[1688450423565].png …]()

![Cargando Hoja de ruta de características del producto Page-1-[1688450427013].png …]()

![¿De dónde es usted_ Page-1-[1688450139012].png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/bf2922b9-1d57-4196-a400-7d86533d2d7d)

] - ~~````
https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/eaa02984-4141-4096-bf14-c1783f912542

![-ucac5d.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/c145b89d-d0fa-414a-bfab-8446148f5bd3)

![20230623_060233.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/d44797e2-d2e9-4178-ad50-8f96d06ee9b7)

![-cnq66v.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/f73f71d3-9eb7-40e6-b7a5-019130c65324)

![20220731_162417.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/4cb3cab3-8792-46cb-8fb2-35be06e84ffa)

![20220801_112543.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/13ca8698-3e44-429e-be0c-908416f1205a)

![20230628_091419.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/71f73155-7d99-4833-9dd5-553ec49b6f3e)

![20230122_064110.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/9499431b-54e3-4b0b-b40c-53929b9af72d)

![20230223_145247.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/dac1c93e-e125-40bd-ba1f-ea2de837be61)

![20230616_103628.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/bc2f2762-1a42-4143-976b-cff98f11d95a)

![20230627_224251.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/6a8f3438-eb9e-4963-b5cc-e9bf0e1e0cdb)

![20230621_224120.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/02f936ce-2c7e-4356-8557-6f70c48a99e5)

![20230629_022857.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/cebd635d-ce18-426b-9096-90d858f2cf53)

![20230628_091617.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/c42ecc9c-1143-4609-888f-61dc0d307454)

![20230628_094213.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/335ee2ef-b1cf-4e8f-bd0d-2dc81c9b44f5)

![20230628_095013.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/be6b3910-b9d5-45dd-bebd-4394a1c3d7e8)

![20230628_091615.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/a11775d4-4753-4d00-bebc-3116ca03b2f3)

![20230713_074723.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/6a47df6a-a796-488f-bdaa-0f49f5bb8f79)

![20230715_112830.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/cd8fede2-6cec-43cf-a2de-6ff9f890b778)

![20230716_064038.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/8a1f9438-f284-4d83-adf5-237af868aba5)

![20230819_131901.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/3e3eaacd-202e-4862-bbf1-891a9b907937)

![20230716_063937.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/79453c7f-c5a7-4071-9c3a-a091fab45ab0)

![20230628_091613.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/eec9aa6b-7081-471d-85b7-cc0d61074ec3)

![20230820_202250.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/997717c3-b43e-4781-bccc-c3b73cefad2d)

<!-- Error al cargar 20230716_062723.jpg -->
``https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/9b5681f9-35dd-40b5-83bd-92fa6a8830f7

![20230717_022320.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/fa8accc3-4031-476e-aa86-9743100455c4)

![20230627_143452.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/c291f631-6586-4da2-ae8d-14544aa616c5)

![20230630_190307.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/797aa0ee-434a-493d-939d-17f14a4c2e03)

![20230703_124024.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/0eb660cf-22d4-4d60-96b0-ef9116a57da1)

![20230630_182731.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/106b7ebd-7013-4a95-b654-174f1bffac0e)

``~![IMG_20230712_031548_615.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/d88dc83d-3128-4d66-b0c4-2e930f499677)

<!-- Error al cargar 1_5143213368340907151.mp4 --><!-- Error al cargar 1_5066750769944855286.mp4 -->![IMG_20230622_170009_153.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/0c5a6940-6a56-44b9-8547-0a6f7d7b2eea)

![IMG_20230621_125803_980.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/0ad29b7c-ac24-4ea1-a573-21e44b726928)

https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/6db009de-a287-4042-83e7-9be1594ac0ac

https://github.com/serhii-londar/open-source-mac-os-apps/a![IMG_20230613_131925_680.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/566a6b4c-577f-45b6-93b5-a0200b141175)

d0c9ad

![IMG_20230613_131927_730.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/fc9a8690-867e-4ae1-9b4c-80530a52102d)

![Cargando IMG_20230613_131925_680.jpg …]()

![IMG_20230613_131931_872.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/3be5061d-c611-4df2-9718-0b3d768ead61)

![IMG_20230613_131929_823.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/ade0f88f-7974-436f-8f31-5956123c9518)

![IMG_20230622_172748_908.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/dad5e0fd-57c0-4221-ba6c-a16b99196f45)

![IMG_20230717_025325_879.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/1ed36a33-df58-4d58-9a6d-dba86f70130a)

![IMG_20230623_031037_722.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/5cc0fb90-285d-46c5-bd80-438356c![IMG_20230623_031113_207.jpg](https://github.com/ser![IMG_20230806_201812_822.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/6e8da0ac-2f31-44d1-bff2-899c7f3ac3aa)

62168/611721f8-ba12-4948-9a46-4ab2e0dded27)

g …]()

![Cargando IMG_20230806_201812_822.jpg …]()

![Cargando IMG_20230623_031113_207.jpg …]()

![IMG_20230711_184202_522.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/913ddc84-17f4-4b58-80f0-500e88f0dd9a)

![IMG_20230806_201818_541.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/5f61be01-4ad3-4935-891b-eeaaadf485e3)

![IMG_20230806_201815_209.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/3445ae54-e825-4ff2-9768-cdf61f7a3be5)

Cargando VID_20230627_134758<!-- Error al cargar VID_20230622_164649_324.mp4 -->_324.mp4 …

https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/47c4e026-cc14-409b-b2e9-adb9537812ff

https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/df6c4072-40ed-42c7-9d97-ee005a8abd72

![IMG_20230806_202318_713.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/10ff280f-58dc-477f-a54c-e66f97f32923)

<!-- Error al cargar VID_20230627_144858_231.mp4 -->https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/8973ba56-0652-42d6-9303-2e33c8104414

https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/defe2703-61cc-427f-844d-93efe5c7041a

https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/214452e3-cdcb-447c-a181-f975bd5f6405

https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/4481ec10-c6d9-4223-b952-e0adcce8c35a

https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/8bd586d3-de45-4244-9534-50901aa18d89

<!-- Error al cargar VID_20230627_145007_800.mp4 -->https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/5eafc9d4-9f36-4f7b-99a9-673dc6e403eb

~# #
 #https://vscode.dev/liveshare/EB75C9AEF18F1FA8606B04390CCFDC573A2B
> **@smokris **

- > 

- [![aad-work-school.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/db633a29-2b34-417d-9e13-f9024f60e090)

![apps-must-ask.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/5d544062-712e-4cc9-b198-90957301006e)

![aad-questions.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/e639f733-cf23-4317-b5df-39b356174440)

![aad-questions-21H1.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/4ba33adb-7016-4b35-9b7b-af2d944d0b4c)

![aad-bitlocker.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/75b8ded0-44b1-4649-9ef1-045b1ebc7f0c)

![all-microsoft.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/fb18385d-d941-47c5-b6ad-cebb4a10d47a)

![aad-disconnect.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/e63e0902-32be-4990-9f4e-b07449fe9b5a)

![docusaurus.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/45352327-0a58-491b-9d94-0da3494ae72d)

![get-signed-in.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/bee52c24-fb8b-4e67-b98a-75409232d9e8)

![gcmcore-rename.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/2d13d737-86aa-46d9-a0e8-63c256ffee3b)

![github-oauthapp-revoke.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/f57ac35e-c2fb-4006-b336-34c629ba8151)

![github-generate-pat.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/17879f2c-bab8-4896-8fce-cecba77d00d0)

![github-display-pat.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/7cb2fd40-a441-4759-bc02-d4e882bc4da5)

![github-pat-workflow-scope.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/ec19592f-d823-455e-9e9f-d66952af42d1)

![github-pat-note.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/49fb8b54-f76a-4134-aaa2-bc927c5ddfed)

![github-pat-gist-scope.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/fa2778e0-e132-4343-937f-aff509a0965b)

![github-pat-repo-scope.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/96cb0731-ec94-4d2e-b3f9-61a92b39d4a9)

![gitlab-oauthapp-revoke.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/1ae84b9b-d331-4765-9da7-a1a4700053b0)

<!-- Error al cargar gitlab-oauthapp-revoked.png -->![windows-cli-save-pat.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/6d20a84f-6b42-4bfb-9463-e82d44b75cc9)

![windows-gui-add-pat.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/d66b7bcd-8ff1-47d8-8411-5a78b2a002b4)

<!-- Error al cargar windows-gui-credentials.png -->![atom-logo75px.gif](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/c21e2789-27d2-4e7f-a717-244a2c469be0)

![c2310d6ede1a5e220f.jpeg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/f2491450-05d8-4e1e-a702-4c39bcadd39b)

![450_1000.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/8329916a-80da-415a-9f7d-27d7bb503b09)

![1668049475b3c174e05e.gif](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/ea694256-e9a0-43e1-84ed-b42865a2245e)

![ai-innovation-pascal-bornet-blog-1820x959.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/b57bb729-5e07-4fc6-80bb-f483f5397a0d)

![14a6b57c-de1c-4561-b2b2-bda973c08577.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/19a518f8-4f73-4b35-a731-e57241ff40ab)

![96a015926bafa2adafe51597b8566d30.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/a1ebac9e-770e-404f-b68c-226390d8cedb)

![b6609ef96465ffc93d3ca2ed5a32b0cb_icon.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/329b68b0-ee1e-49af-9fcb-cd8be19424cb)

![CD148BFC3EE3B5328DAFE08E2B6AA95B73B7.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/b223419e-019e-4a3a-996c-8845bd99dffd)

![gdpr-gc3f907ef6_1280.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/8a03c55d-4b15-45f1-9a98-10ac6af28c53)

![Tech_Illustrations_Export_Dev portal-API_OnBoard.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/455221ab-7098-4092-929b-dfd61b8e2d8e)

![Tech_Illustrations_Export_E-commerce plugin_OnBoard.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/26a84cf4-2d70-4ee5-9684-7cc0ad46fdee)

![hero.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/3c782f80-8399-4416-b14b-7713bc778cc2)

![Roblox_Logo_2022.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/6a1d12fa-2957-4853-8b66-1f99ac029b94)

![Tech_Illustrations_Export_Universal tag_OnBoard.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/792f37ee-9901-4c21-8651-7b9d5adf2933)

https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/01c8ec13-ca4f-44ed-978c-0e138d9008cc

![ghcup.gif](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/7656052b-3d12-4f0c-b140-d15650aad65d)

![zoom-AI.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/5d1390bf-4c6d-4c19-a9ea-15f867fff7f8)

![Zoom-AI-smart-recording.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/861b4eda-66d0-48c4-ae01-e85643d83319)

![ipy_013_dashboard.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/83af2d66-913a-4416-8dfe-4d46dbcc9535)

![ipy_013_notebook_rmagic.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/fa273042-252c-4aa7-8f24-9b9f409b7549)

![autosuggest.gif](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/ad5727e7-74b5-4d91-bdf1-81847c11fd85)

![ipy_013_notebook_long_out.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/d5c0a488-a21d-4cc5-b9da-b9716894e986)

![ipy_013_dashboard_cluster.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/95873ae8-ca0b-463b-82e4-1a48eee4b2cf)

![ipy_013_notebook_octavemagic.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/9803ebef-d842-43eb-a915-8c2e7d8fadba)

![ipy_013_notebook_cythonmagic.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/e265e97f-4a11-46c3-ba58-f793c83ab91a)

![ipy_013_notebook_spectrogram.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/d9de8000-44eb-4278-8253-9160bafae980)

![ipy_013_notebook_script_cells.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/f34af06c-8e32-432c-bc67-db6692df60b1)

![ipy_013_par_tb.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/a725152b-6b97-455f-94b4-7aaafdda8b2b)

![ipy_013_notebook_tooltip.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/dd8cbbc8-a3ed-4132-bb32-5ae92138cd52)

![Cargando ipython-6-screenshot.png …]![ipy_013_qtconsole_completer.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/edad111c-7f63-4a13-badf-c946dcaa81e8)


![kernel_selector_screenshot.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/800145ff-1389-450b-a421-99fd2779797b)

![Cargando ipy_013_qtconsole_completer.png …]()

<!-- Error al cargar ptshell_features.png -->![jedi_type_inference_60.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/30b29085-dc8a-4dc6-8913-86630f431a2c)

![notebook_specgram.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/f8aca18c-95f2-4e2b-8ae8-f8b1b30f1809)

![qtconsole_tabbed.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/2efdad83-a1af-4251-9916-dba424082751)

![qtconsole.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/813b3365-7736-4652-8471-fcafb615c4d8)

<!-- Error al cargar unicode_completion.png -->![ms_visual_studio.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/2c5fef0a-7218-4f85-ba13-95f2d325b4cf)

 ] ### **@yoasif **

> ````
- [![logo.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/146c03cf-67f6-4c49-9f60-110eaf934f85)

![user-interface.png](https://github![widgets.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/736726d5-431d-40ec-b135-9343cce4ab5e)

e-mac-os-apps/assets/42362168/7fb6549a-2193-4dc8-99c2-4b1f1518de31)

![Cargando widgets.png …]()

![auto_suggest_3_print_hello_suggest.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/65dd2ad3-b131-4116-b79c-ebec86ebe219)

![auto_suggest_2_print_hello_suggest.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/68a8d796-15d6-407f-a66a-1cf016992ce0)

![auto_suggest_4_print_hello.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/6ffe2403-db85-4a76-bba7-b75a997b4f00)

<!-- Error al cargar auto_suggest_1_prompt_no_text.png -->![auto_suggest_d_phantom.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/479dc347-678e-4815-9e67-269e661f0531)

![auto_suggest_def_completions.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/354fbebe-6c6a-4615-be56-453831406fcb)

![auto_suggest_d_completions.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/2fc7651f-7e9b-45b5-9109-baf9b50996fd)

![auto_suggest_def_phantom.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/7e961c3d-8d65-4c0d-b978-3552f3495ba1)

![auto_suggest_second_prompt.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/ebc5555a-b505-4ffe-ac30-43842ddcb005)

<!-- Error al cargar pathlib_pathlib_everywhere.jpg -->![auto_suggest_match_parens.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/0a29446a-5e5a-4dab-b423-533cb17cf569)

![gcm-transparent.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/482dc44d-e2c8-4814-8285-3a904915840c)

![gcmweb.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/eea8b683-fd08-4fc2-b4e3-d71239093c0f)

![gcm-banner.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/610a199d-a5e8-41f3-97b6-c216646cdf24)

 ] ~~![atlassian-logo.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/9e370b6b-26e9-43b7-89dc-ef99c0163762)

![atlassian-logo.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/1443c275-59fd-4493-b44d-54696f58d25a)

![IMG_20230224_001102_072.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/90237f9e-4b87-4bb2-818c-1b176d63f30b)

![IMG_20230224_001156_886.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/6d56d725-15b5-4197-b1df-4e203c68889f)

![share__2023-02-23_20_39_31.jpg](https://github![share__2023-07-25_10_58_52.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/dc6ae183-06a4-48bc-ab56-5e90d793cb1f)

s/42362168/91470a82-cd2e-4cc9-b0ce-52de0b81aa35)

![Cargando share__2023-07-25_10_58_52.jpg …]()

![share__2023-07-25_11_23_23.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/f1501161-e5e8-4bb9-8af4-da24c6b19a6e)

![share__2023-08-20_01_17_55.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/bce68df7-641b-4650-80e9-c6040afcd62e)

![share_2023-02-23_20_39_36_711.jpeg_2023-02-23_20_39_36.jpg](https://gith![share__2023-07-25_12_36_40.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/fd746203-61e6-40e9-8f8a-9ca91e49d374)

ets/42362168/829a13e0-4e41-4edd-be40-f9fd87f77b4f)

![Cargando share__2023-07-25_12_36_33.jpg …]()![share_2023-02-23_20_39_39_311.jpeg_2023-02-23_20_39_39.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/c0d9e51e-af77-46ec-ab07-e14f892047ed)

25_12_36_4![share_2023-02-23_20_40_49_714.jpeg_2023-02-23_20_40_49.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/0e2bba87-0203-4e31-ad32-e03f7b390706)

jpeg_2023-02-23_20_40_12.jpg](https://github![share_2023-02-23_20_40_51_118.jpeg_2023-02-23_20_40_51.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/4dc5b![share_2023-07-25_12_30_48_207.jpeg_2023-07-25_12_30_48.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/ba9f0120-d9d8-423b-9216-83fd56903ee9)

g_2023-07-25_12_31_31.jpg -->i-londar/open-source-mac-os-apps/assets/42362168/aa02eef9-8b81-4130-8d9b-dec72d433f4b)

8.jpg …]()

![share_2023-02-23_20_40_32_486.jpeg_2023-02-23_20_40_32.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/b92b4cd6-6569-4c8b-8849-7beedea8dbcc)

![Cargando share_2023-02-23_20_40_12_348.jpeg_2023-02-23_20_40_12.jpg …]()

![Cargando share_2023-02-23_20_40_51_118.jpeg_2023-02-23_20_40_51.jpg …]()

![Cargando share_2023-02-23_20_40_49_714.jpeg_2023-02-![share_2023-02-23_20_40_40_004.jpeg_2023-02-23_20_40_40.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/71c330a7-db26-4702-be9e-0fcf064a6f99)

25_11_15_10.jpg …]()

![Cargando share_2023-02-23_20_40_40_004.jpeg_2023-02-23_20_40_40.jpg …]()

![share_2023-02-23_20_40_22_791.jpeg_2023-02-23_20_40_22.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/4eb9d990-dff1-450c-b40d-45e5f41c1d60)

![share_2023-07-25_10_59_00_694.jpeg_2023-07-25_10_59_00.jpg](https://github.com/serhi![share_2023-07-25_12_36_38_824.jpeg_2023-07-25_12_36_38.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/5c9dc989-4204-43d7-9bd6-7c1d9f013501)

c396e0b8d)

![Cargando share_2023-07-25_12_31_31_862.jpeg_2023-07-25_12_31_31.jpg …]()

![Cargando share_2023-07-25_12_30_48_207.jpeg_2023-07-25_12_30_48.jpg …]()

![share_2023-07-25_12_32_46_491.jpeg_2023-07-25_12_32_46.jpg](https://github![share_2023-07-25_12_31_02_061.jpeg_2023-07-25_12_31_02.jpg](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/2430cfd2-1446-470a-987b-b36d1b91423a)

f-9d5c-a8d7a3f8fa69)

![Cargando share_2023-07-25_12_31_02_061.jpeg_2023-07-25_12_31_02.jpg …]()

![Cargando share_2023-07-25_12_36_38_824.jpeg_2023-07-25_12_36_38.jpg …]()

![brew-test-bot-failed-pr.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/333ddfb1-5d6a-43bf-8251-e0385fa72f73)

![analytics.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/e71b5e5c-1674-4521-bef9-e210826fb94c)

![brew-test-bot-triggered-pr.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/a73af1b4-df6a-48a1-9826-885b30459e9e)

![brew-test-bot-passed-pr.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/03cb0886-0eb7-4bda-9693-4b4c708af24a)

**_[](![icon.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/93b529d2-f7c3-43e6-a176-0252b5f401db)

![bugreport-P616F01-SP1A.210812.016-2023-08-22-14-27-13-dumpstate_log-29320.txt](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598635/bugreport-P616F01-SP1A.210812.016-2023-08-22-14-27-13-dumpstate_log-29320.txt)

![dumpstate-stats.txt](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598636/dumpstate-stats.txt)

![screenshot-2023-08-22-14-27-13-default.png](https://github.com/serhii-londar/open-source-mac-os-apps/assets/42362168/d02b77b3-dc35-44e1-b367-979145c0be3e)

![bugreport-P616F01-SP1A.210812.016-2023-08-22-14-27-13.zip](https://github.com/serhii-londar/open-source-mac-os-apps/files/12598637/bugreport-P616F01-SP1A.210812.016-2023-08-22-14-27-13.zip)

)_**~~
````
ramoncerdaquiroz/source-https/github-git.kernel.org/pub/scm/git/git.git/tree/fsck-cache.c/HackerOne(ramoncerdaquiroz)/w3c.github/web-locks/apache-httpd.apache.org/github/ramoncerdaquiroz/9562876/TelegramBeta®-TelegramXBeta®/ramoncerdaquiroz-ramoncerdaquiroz/. github/ramoncerdaquiroz-patch1/ggmon/github-.github-ramoncerdaquiroz/https://www.google.com[(ramon_cq@hotmail.com)(ggmon.oficial@gmail.com)(rcerdaquiroz@gmail.com)(cerdaquirozr@gmail.com)(ramoncq1980@gmail.com)(ramoncerdaquiroz@gmail.com)]/googlefinance-ramon_cq@hotmail.com/Binance-ramon_cq@hotmail.com

 # #
 #https://vscode.dev/liveshare/EB75C9AEF18F1FA8606B04390CCFDC573A2B
> **@ramoncerdaquiroz**

- > 

- [] ### **@ramoncerdaquiroz,@ramon_cerda,@ciberthefriends**

> 
#include <sys/types.h>
#include <dirent.h>
#include "cache.h"
#include "commit.h"
#include "tree.h"
#include "blob.h"
#include "tag.h"
#include "refs.h"
#include "pack.h"

#define REACHABLE 0x0001

static int show_root = 0;
static int show_tags = 0;
static int show_unreachable = 0;
static int standalone = 0;
static int check_full = 0;
static int keep_cache_objects = 0; 
static unsigned char head_sha1[20];

static void check_connectivity(void)
{
	int i;

	/* Look up all the requirements, warn about missing objects.. */
	for (i = 0; i < nr_objs; i++) {
		struct object *obj = objs[i];
		struct object_list *refs;

		if (!obj->parsed) {
			if (!standalone && has_sha1_file(obj->sha1))
				; /* it is in pack */
			else
				printf("missing %s %s\n",
				       obj->type, sha1_to_hex(obj->sha1));
			continue;
		}

		for (refs = obj->refs; refs; refs = refs->next) {
			if (refs->item->parsed ||
			    (!standalone && has_sha1_file(refs->item->sha1)))
				continue;
			printf("broken link from %7s %s\n",
			       obj->type, sha1_to_hex(obj->sha1));
			printf("              to %7s %s\n",
			       refs->item->type, sha1_to_hex(refs->item->sha1));
		}

		if (show_unreachable && !(obj->flags & REACHABLE)) {
			printf("unreachable %s %s\n",
			       obj->type, sha1_to_hex(obj->sha1));
			continue;
		}

		if (!obj->used) {
			printf("dangling %s %s\n", obj->type, 
			       sha1_to_hex(obj->sha1));
		}
	}
}

/*
 * The entries in a tree are ordered in the _path_ order,
 * which means that a directory entry is ordered by adding
 * a slash to the end of it.
 *
 * So a directory called "a" is ordered _after_ a file
 * called "a.c", because "a/" sorts after "a.c".
 */
#define TREE_UNORDERED (-1)
#define TREE_HAS_DUPS  (-2)

static int verify_ordered(struct tree_entry_list *a, struct tree_entry_list *b)
{
	int len1 = strlen(a->name);
	int len2 = strlen(b->name);
	int len = len1 < len2 ? len1 : len2;
	unsigned char c1, c2;
	int cmp;

	cmp = memcmp(a->name, b->name, len);
	if (cmp < 0)
		return 0;
	if (cmp > 0)
		return TREE_UNORDERED;

	/*
	 * Ok, the first <len> characters are the same.
	 * Now we need to order the next one, but turn
	 * a '\0' into a '/' for a directory entry.
	 */
	c1 = a->name[len];
	c2 = b->name[len];
	if (!c1 && !c2)
		/*
		 * git-write-tree used to write out a nonsense tree that has
		 * entries with the same name, one blob and one tree.  Make
		 * sure we do not have duplicate entries.
		 */
		return TREE_HAS_DUPS;
	if (!c1 && a->directory)
		c1 = '/';
	if (!c2 && b->directory)
		c2 = '/';
	return c1 < c2 ? 0 : TREE_UNORDERED;
}

static int fsck_tree(struct tree *item)
{
	int has_full_path = 0;
	struct tree_entry_list *entry, *last;

	last = NULL;
	for (entry = item->entries; entry; entry = entry->next) {
		if (strchr(entry->name, '/'))
			has_full_path = 1;

		switch (entry->mode) {
		/*
		 * Standard modes.. 
		 */
		case S_IFREG | 0755:
		case S_IFREG | 0644:
		case S_IFLNK:
		case S_IFDIR:
			break;
		/*
		 * This is nonstandard, but we had a few of these
		 * early on when we honored the full set of mode
		 * bits..
		 */
		case S_IFREG | 0664:
			break;
		default:
			printf("tree %s has entry %o %s\n",
				sha1_to_hex(item->object.sha1),
				entry->mode, entry->name);
		}

		if (last) {
			switch (verify_ordered(last, entry)) {
			case TREE_UNORDERED:
				fprintf(stderr, "tree %s not ordered\n",
					sha1_to_hex(item->object.sha1));
				return -1;
			case TREE_HAS_DUPS:
				fprintf(stderr, "tree %s has duplicate entries for '%s'\n",
					sha1_to_hex(item->object.sha1),
					entry->name);
				return -1;
			default:
				break;
			}
		}

		last = entry;
	}

	if (has_full_path) {
		fprintf(stderr, "warning: git-fsck-cache: tree %s "
			"has full pathnames in it\n", 
			sha1_to_hex(item->object.sha1));
	}

	return 0;
}

static int fsck_commit(struct commit *commit)
{
	free(commit->buffer);
	commit->buffer = NULL;
	if (!commit->tree)
		return -1;
	if (!commit->parents && show_root)
		printf("root %s\n", sha1_to_hex(commit->object.sha1));
	if (!commit->date)
		printf("bad commit date in %s\n", 
		       sha1_to_hex(commit->object.sha1));
	return 0;
}

static int fsck_tag(struct tag *tag)
{
	struct object *tagged = tag->tagged;

	if (!tagged) {
		printf("bad object in tag %s\n", sha1_to_hex(tag->object.sha1));
		return -1;
	}
	if (!show_tags)
		return 0;

	printf("tagged %s %s", tagged->type, sha1_to_hex(tagged->sha1));
	printf(" (%s) in %s\n", tag->tag, sha1_to_hex(tag->object.sha1));
	return 0;
}

static int fsck_sha1(unsigned char *sha1)
{
	struct object *obj = parse_object(sha1);
	if (!obj)
		return -1;
	if (obj->type == blob_type)
		return 0;
	if (obj->type == tree_type)
		return fsck_tree((struct tree *) obj);
	if (obj->type == commit_type)
		return fsck_commit((struct commit *) obj);
	if (obj->type == tag_type)
		return fsck_tag((struct tag *) obj);
	return -1;
}

/*
 * This is the sorting chunk size: make it reasonably
 * big so that we can sort well..
 */
#define MAX_SHA1_ENTRIES (1024)

struct sha1_entry {
	unsigned long ino;
	unsigned char sha1[20];
};

static struct {
	unsigned long nr;
	struct sha1_entry *entry[MAX_SHA1_ENTRIES];
} sha1_list;

static int ino_compare(const void *_a, const void *_b)
{
	const struct sha1_entry *a = _a, *b = _b;
	unsigned long ino1 = a->ino, ino2 = b->ino;
	return ino1 < ino2 ? -1 : ino1 > ino2 ? 1 : 0;
}

static void fsck_sha1_list(void)
{
	int i, nr = sha1_list.nr;

	qsort(sha1_list.entry, nr, sizeof(struct sha1_entry *), ino_compare);
	for (i = 0; i < nr; i++) {
		struct sha1_entry *entry = sha1_list.entry[i];
		unsigned char *sha1 = entry->sha1;

		sha1_list.entry[i] = NULL;
		if (fsck_sha1(sha1) < 0)
			fprintf(stderr, "bad sha1 entry '%s'\n", sha1_to_hex(sha1));
		free(entry);
	}
	sha1_list.nr = 0;
}

static void add_sha1_list(unsigned char *sha1, unsigned long ino)
{
	struct sha1_entry *entry = xmalloc(sizeof(*entry));
	int nr;

	entry->ino = ino;
	memcpy(entry->sha1, sha1, 20);
	nr = sha1_list.nr;
	if (nr == MAX_SHA1_ENTRIES) {
		fsck_sha1_list();
		nr = 0;
	}
	sha1_list.entry[nr] = entry;
	sha1_list.nr = ++nr;
}

static int fsck_dir(int i, char *path)
{
	DIR *dir = opendir(path);
	struct dirent *de;

	if (!dir) {
		return error("missing sha1 directory '%s'", path);
	}

	while ((de = readdir(dir)) != NULL) {
		char name[100];
		unsigned char sha1[20];
		int len = strlen(de->d_name);

		switch (len) {
		case 2:
			if (de->d_name[1] != '.')
				break;
		case 1:
			if (de->d_name[0] != '.')
				break;
			continue;
		case 38:
			sprintf(name, "%02x", i);
			memcpy(name+2, de->d_name, len+1);
			if (get_sha1_hex(name, sha1) < 0)
				break;
			add_sha1_list(sha1, de->d_ino);
			continue;
		}
		fprintf(stderr, "bad sha1 file: %s/%s\n", path, de->d_name);
	}
	closedir(dir);
	return 0;
}

static int default_refs = 0;

static int fsck_handle_ref(const char *refname, const unsigned char *sha1)
{
	struct object *obj;

	obj = lookup_object(sha1);
	if (!obj) {
		if (!standalone && has_sha1_file(sha1)) {
			default_refs++;
			return 0; /* it is in a pack */
		}
		error("%s: invalid sha1 pointer %s", refname, sha1_to_hex(sha1));
		/* We'll continue with the rest despite the error.. */
		return 0;
	}
	default_refs++;
	obj->used = 1;
	mark_reachable(obj, REACHABLE);
	return 0;
}

static void get_default_heads(void)
{
	for_each_ref(fsck_handle_ref);
	if (!default_refs)
		die("No default references");
}

static void fsck_object_dir(const char *path)
{
	int i;
	for (i = 0; i < 256; i++) {
		static char dir[4096];
		sprintf(dir, "%s/%02x", path, i);
		fsck_dir(i, dir);
	}
	fsck_sha1_list();
}

static int fsck_head_link(void)
{
	int fd, count;
	char hex[40];
	unsigned char sha1[20];
	static char path[PATH_MAX], link[PATH_MAX];
	const char *git_dir = gitenv(GIT_DIR_ENVIRONMENT) ? : DEFAULT_GIT_DIR_ENVIRONMENT;

	snprintf(path, sizeof(path), "%s/HEAD", git_dir);
	if (readlink(path, link, sizeof(link)) < 0)
		return error("HEAD is not a symlink");
	if (strncmp("refs/heads/", link, 11))
		return error("HEAD points to something strange (%s)", link);
	fd = open(path, O_RDONLY);
	if (fd < 0)
		return error("HEAD: %s", strerror(errno));
	count = read(fd, hex, sizeof(hex));
	close(fd);
	if (count < 0)
		return error("HEAD: %s", strerror(errno));
	if (count < 40 || get_sha1_hex(hex, sha1))
		return error("HEAD: not a valid git pointer");
	return 0;
{# ---

Title: “Welcome to HackerOne Docs”

Path: “/hackers.html”

Id: “hackers/welcome-to-hackerone-docs”

bookIndexFor: “hackers”

description: “Have you just started hacking on HackerOne or want to learn more about a feature? You’re in the right place. These guides will help you to understand the product so that you can easily navigate through the platform in submitting vulnerabilities. Check out the sections on the left to learn more.” ---



# Have you just started hacking on HackerOne or want to learn more about a feature? You’re in the right place. These guides will help you to understand the product so that you can easily navigate through the platform in submitting vulnerabilities. Check out the sections on the left to learn more.



# To help you get started, take a look at these docs:



# <button type=”button” class=”welcome-button” onclick=”location.href=’/hackers/create-an-account.html’”><h3>Create an Account</h3>Learn the basics of the product. # </button><button type=”button” class=”welcome-button” onclick=”location.href=’/hackers/private-vs-public-programs.html’”><h3>Private vs. Public Programs</h3>Know the difference between private and public programs.</button><button type=”button” class=”welcome-button” onclick=”location.href=’/hackers/submitting-reports.html’”><h3>Submit a Report</h3>Submit your found vulnerability to a program.</button>



# >See something that can be improved on the docs site? [Make a suggestion](/organizations/edit-the-doc-site.html)!> # **<img width=”616” alt=”Compete-river-3__4_” src=https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/c0c676a7-ab4b-4626-9ed3-d58560874a4d> # <img width=”616” alt=”Compete-river-1__10_” src=https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/aa181326-4e2f-4f18-a7c4-ac479527da57> # <img width=”616” alt=”Compete-river-1” src=https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/d4b15b6c-b4de-430f-ad77-36d2a6e6fc4b> # <img width=”616” alt=”Compete-river-3__7_” src=https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/79591a1e-db4b-4ed1-8c38-88081f3eb388> # ¡[Compete-river-3__18___1_](https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/ea767ab9-7cb8-498e-951e-8f18629536cb) # <img width=”616” alt=”Compete-river-3__8_” src=https://github.# --- title: “Welcome to HackerOne Docs

Path: “/hackers.html”

Id: “hackers/welcome-to-hackerone-docs”

bookIndexFor: “hackers”

description: “Have you just started hacking on HackerOne or want to learn more about a feature? You’re in the right place. These guides will help you to understand the product so that you can easily navigate through the platform in submitting vulnerabilities. Check out the sections on the left to learn more.” ---



# Have you just started hacking on HackerOne or want to learn more about a feature? You’re in the right place. These guides will help you to understand the product so that you can easily navigate through the platform in submitting vulnerabilities. Check out the sections on the left to learn more.



# To help you get started, take a look at these docs:



# <button type=”button” class=”welcome-button” onclick=”location.href=’/hackers/create-an-account.html’”><h3>Create an Account</h3>Learn the basics of the product. # </button><button type=”button” class=”welcome-button” onclick=”location.href=’/hackers/private-vs-public-programs.html’”><h3>Private vs. Public Programs</h3>Know the difference between private and public programs.</button><button type=”button” class=”welcome-button” onclick=”location.href=’/hackers/submitting-reports.html’”><h3>Submit a Report</h3>Submit your found vulnerability to a program.</button>



# >See something that can be improved on the docs site? [Make a suggestion](/organizations/edit-the-doc-site.html)!> # **<img width=”616” alt=”Compete-river-3__4_” src=https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/c0c676a7-ab4b-4626-9ed3-d58560874a4d> # <img width=”616” alt=”Compete-river-1__10_” src=https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/aa181326-4e2f-4f18-a7c4-ac479527da57> # <img width=”616” alt=”Compete-river-1” src=https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/d4b15b6c-b4de-430f-ad77-36d2a6e6fc4b> # <img width=”616” alt=”Compete-river-3__7_” src=https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/79591a1e-db4b-4ed1-8c38-88081f3eb388> # ¡[Compete-river-3__18___1_](https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/ea767ab9-7cb8-498e-951e-8f18629536cb) # <img width=”616” alt=”Compete-river-3__8_” src=https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/a5914f83-23de-499a-bcd6-08919a9c9898> # ¡[20230905_061918](https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/7541459d-6c16-4b9e-9bb3-7eb9dcb66dd0)**



# **com/Hacker0x01/docs.hackerone.com/assets/42362168/a5914f83-23de-499ª-bcd6-08919ª9c9898”> # ¡[20230905_061918](https://github.com/Hacker0x01/docs.hackerone.com/assets/42362168/7541459d-6c16-4b9e-9bb3-7eb9dcb66dd0)** }}

int main(int argc, char **argv)
{
	int i, heads;

	for (i = 1; i < argc; i++) {
		const char *arg = argv[i];

		if (!strcmp(arg, "--unreachable")) {
			show_unreachable = 1;
			continue;
		}
		if (!strcmp(arg, "--tags")) {
			show_tags = 1;
			continue;
		}
		if (!strcmp(arg, "--root")) {
			show_root = 1;
			continue;
		}
		if (!strcmp(arg, "--cache")) {
			keep_cache_objects = 1;
			continue;
		}
		if (!strcmp(arg, "--standalone")) {
			standalone = 1;
			continue;
		}
		if (!strcmp(arg, "--full")) {
			check_full = 1;
			continue;
		}
		if (*arg == '-')
			usage("git-fsck-cache [--tags] [[--unreachable] [--cache] [--standalone | --full] <head-sha1>*]");
	}

	if (standalone && check_full)
		die("Only one of --standalone or --full can be used.");
	if (standalone)
		unsetenv("GIT_ALTERNATE_OBJECT_DIRECTORIES");

	fsck_head_link();
	fsck_object_dir(get_object_directory());
	if (check_full) {
		int j;
		struct packed_git *p;
		prepare_alt_odb();
		for (j = 0; alt_odb[j].base; j++) {
			alt_odb[j].name[-1] = 0; /* was slash */
			fsck_object_dir(alt_odb[j].base);
			alt_odb[j].name[-1] = '/';
		}
		prepare_packed_git();
		for (p = packed_git; p; p = p->next)
			/* verify gives error messages itself */
			verify_pack(p, 0);

		for (p = packed_git; p; p = p->next) {
			int num = num_packed_objects(p);
			for (i = 0; i < num; i++) {
				unsigned char sha1[20];
				nth_packed_object_sha1(p, i, sha1);
				if (fsck_sha1(sha1) < 0)
					fprintf(stderr, "bad sha1 entry '%s'\n", sha1_to_hex(sha1));

			}
		}
	}

	heads = 0;
	for (i = 1; i < argc; i++) {
		const char *arg = argv[i]; 

		if (*arg == '-')
			continue;

		if (!get_sha1(arg, head_sha1)) {
			struct object *obj = lookup_object(head_sha1);

			/* Error is printed by lookup_object(). */
			if (!obj)
				continue;

			obj->used = 1;
			mark_reachable(obj, REACHABLE);
			heads++;
			continue;
		}
		error("expected sha1, got %s", arg);
	}

	/*
	 * If we've not been given any explicit head information, do the
	 * default ones from .git/refs. We also consider the index file
	 * in this case (ie this implies --cache).
	 */
	if (!heads) {
		get_default_heads();
		keep_cache_objects = 1;
	}

	if (keep_cache_objects) {
		int i;
		read_cache();
		for (i = 0; i < active_nr; i++) {
			struct blob *blob = lookup_blob(active_cache[i]->sha1);
			struct object *obj;
			if (!blob)
				continue;
			obj = &blob->object;
			obj->used = 1;
			mark_reachable(obj, REACHABLE);
		}
	}

	check_connectivity( # Seguridad avanzada de GitHub

Empresa GitHub
Ver todas las colecciones

Acciones de GitHub
la plataforma DevOps

Temas
Destacar
DevOps
Seguridad
Acciones de GitHub
Fuente abierta
Herramientas
Fundamentos
Seguridad de aplicaciones
fuente interna
Ver todos los temas
Comparar GitHub

Día de demostración: ganando terreno con las acciones de GitHub 16 de marzo de 2021

Obtenga soporte práctico para todo lo relacionado con la automatización. Únase a nosotros para una inmersión técnica profunda en GitHub Actions...

DevOps , canalización , automatización , CI/CD , acciones de GitHub se soluciona problemas de seguridad en minutos, no en meses

GitHub Advanced Security está diseñado para optimizar la experiencia del desarrollador a través de la automatización. Ayuda a sus equipos a identificar y solucionar problemas de seguridad informados de manera rápida y eficiente al integrar la seguridad en cada paso del flujo de trabajo del desarrollador.

¿Ves un problema de seguridad? Arréglalo ahora.

Ocurren problemas de seguridad, pero dejarlos sin solucionar puede suponer una carga para su equipo y su negocio. Lo mejor que puede hacer es identificar los problemas a tiempo y solucionarlos rápidamente.

La seguridad está conectada a todo

Mensaje que muestra la vulnerabilidad encontrada
Seguridad que empodera a los desarrolladores

GitHub Advanced Security proporciona capacidades líderes en la industria de forma nativa en el entorno de desarrollador. Estas capacidades incluyen:

Escaneo de código

Encuentre y solucione problemas de seguridad en su código antes de que lleguen a producción con pruebas de seguridad de aplicaciones estáticas (SAST).

Escaneo secreto

Evite el acceso no autorizado y las infracciones observando sus repositorios en busca de formatos secretos conocidos y reciba notificaciones tan pronto como se encuentren secretos.

Seguridad de la cadena de suministro

Detecte las dependencias vulnerables antes de introducirlas en su base de código con el análisis de composición de software (SCA).

Encuentre y solucione problemas de seguridad antes

El escaneo de código examina su código en busca de problemas de seguridad a medida que se escribe e integra correcciones de forma nativa en el flujo de trabajo del desarrollador.

Aprende más Solicitud de extracción que muestra todas las pruebas aprobadas

Informe de escaneo secreto
Descubra y administre secretos codificados
El escaneo de secretos observa sus repositorios en busca de formatos de secretos conocidos y personalizados y luego le notifica tan pronto como se encuentran secretos.

Mira como funciona 

Seguridad de la cadena de suministro con inteligencia en tiempo real La revisión de dependencias ayuda a sus revisores y contribuyentes a comprender los cambios de dependencia y su impacto en la seguridad, incluidas qué dependencias se agregaron, eliminaron o actualizaron. Aprende cómo funciona esto 

Administre sus riesgos de seguridad, todo en un solo lugar La descripción general de seguridad proporciona visibilidad de su postura de seguridad en todo su código base, lo que le ayuda a priorizar los problemas y repositorios que requieren su atención.

Aprende más Sigue usando las herramientas que amas Las integraciones de terceros y el soporte SARIF brindan flexibilidad y libertad para que sus equipos utilicen cualquier combinación de soluciones de seguridad de aplicaciones comerciales o de código abierto, sin cambios de contexto. Consulte la descripción completa

Mayor seguridad para mejores experiencias
Las características de seguridad de GitHub ayudan a tu equipo a construir y realizar envíos de manera más eficiente. Vea cómo el escaneo de códigos, el escaneo de secretos, la seguridad de la cadena de suministro y más encajan en su flujo de trabajo de desarrollador.

Escanear solicitudes de extracción en busca de vulnerabilidades antes de comprometerse Vea, corrija, descarte o elimine alertas de posibles vulnerabilidades o errores en el código de su proyecto.

Lee la guía
Configuración de niveles de alerta de seguridad personalizados para verificaciones de solicitudes de extracción Defina las gravedades que causan el error en la verificación de la solicitud de extracción y especifique el escaneo para ramas específicas.

Lee la guía
Uso de revisiones predictivas de dependencia para detectar vulnerabilidades Obtenga una visualización fácilmente comprensible de los cambios de dependencia con una rica diferencia en la pestaña Archivos modificados de una solicitud de extracción.

Lee la guía
Preferimos tener una seguridad que aproveche lo que los desarrolladores ya están usando en lugar de intentar obligarlos a usar alguna otra herramienta... siempre causa fricción. # **<img width="616" alt="Compete-river-1__10_" src="https://github.com/binance/binance-futures-connector-python/assets/42362168/83f56c2d-41c3-4d0c-a3c8-7f026db698d6"> <img width="616" alt="Compete-river-1" src="https://github.com/binance/binance-futures-connector-python/assets/42362168/6c07928a-ccb0-4a4e-8a8b-067cd2c05c2e"> <img width="616" alt="Compete-river-3__7_" src="https://github.com/binance/binance-futures-connector-python/assets/42362168/d658e12a-7f45-4ca8-bb45-9a063d7b523a"> ![Compete-river-3__18___1_](https://github.com/binance/binance-futures-connector-python/assets/42362168/4f608018-93a0-4002-ac18-b9ef8201e50a) <img width="616" alt="Compete-river-3__8_" src="https://github.com/binance/binance-futures-connector-python/assets/42362168/7e9405a3-82b6-4c78-939e-5bd8aa8650c2"> [github-recovery-codes.txt](https://github.com/binance/binance-futures-connector-python/files/12507424/github-recovery-codes.txt) **


# source-https
#                                  Apache License 
                            Version 2.0, January 2004 
                         https://www.apache.org/licenses/ 
  
    TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION 
  
    1. Definitions. 
  
       "License" shall mean the terms and conditions for use, reproduction, 
       and distribution as defined by Sections 1 through 9 of this document. 
  
       "Licensor" shall mean the copyright owner or entity authorized by 
       the copyright owner that is granting the License. 
  
       "Legal Entity" shall mean the union of the acting entity and all 
       other entities that control, are controlled by, or are under common 
       control with that entity. For the purposes of this definition, 
       "control" means (i) the power, direct or indirect, to cause the 
       direction or management of such entity, whether by contract or 
       otherwise, or (ii) ownership of fifty percent (50%) or more of the 
       outstanding shares, or (iii) beneficial ownership of such entity. 
  
       "You" (or "Your") shall mean an individual or Legal Entity 
       exercising permissions granted by this License. 
  
       "Source" form shall mean the preferred form for making modifications, 
       including but not limited to software source code, documentation 
       source, and configuration files. 
  
       "Object" form shall mean any form resulting from mechanical 
       transformation or translation of a Source form, including but 
       not limited to compiled object code, generated documentation, 
       and conversions to other media types. 
  
       "Work" shall mean the work of authorship, whether in Source or 
       Object form, made available under the License, as indicated by a 
       copyright notice that is included in or attached to the work 
       (an example is provided in the Appendix below). 
  
       "Derivative Works" shall mean any work, whether in Source or Object 
       form, that is based on (or derived from) the Work and for which the 
       editorial revisions, annotations, elaborations, or other modifications 
       represent, as a whole, an original work of authorship. For the purposes 
       of this License, Derivative Works shall not include works that remain 
       separable from, or merely link (or bind by name) to the interfaces of, 
       the Work and Derivative Works thereof. 
  
       "Contribution" shall mean any work of authorship, including 
       the original version of the Work and any modifications or additions 
       to that Work or Derivative Works thereof, that is intentionally 
       submitted to Licensor for inclusion in the Work by the copyright owner 
       or by an individual or Legal Entity authorized to submit on behalf of 
       the copyright owner. For the purposes of this definition, "submitted" 
       means any form of electronic, verbal, or written communication sent 
       to the Licensor or its representatives, including but not limited to 
       communication on electronic mailing lists, source code control systems, 
       and issue tracking systems that are managed by, or on behalf of, the 
       Licensor for the purpose of discussing and improving the Work, but 
       excluding communication that is conspicuously marked or otherwise 
       designated in writing by the copyright owner as "Not a Contribution." 
  
       "Contributor" shall mean Licensor and any individual or Legal Entity 
       on behalf of whom a Contribution has been received by Licensor and 
       subsequently incorporated within the Work. 
  
    2. Grant of Copyright License. Subject to the terms and conditions of 
       this License, each Contributor hereby grants to You a perpetual, 
       worldwide, non-exclusive, no-charge, royalty-free, irrevocable 
       copyright license to reproduce, prepare Derivative Works of, 
       publicly display, publicly perform, sublicense, and distribute the 
       Work and such Derivative Works in Source or Object form. 
  
    3. Grant of Patent License. Subject to the terms and conditions of 
       this License, each Contributor hereby grants to You a perpetual, 
       worldwide, non-exclusive, no-charge, royalty-free, irrevocable 
       (except as stated in this section) patent license to make, have made, 
       use, offer to sell, sell, import, and otherwise transfer the Work, 
       where such license applies only to those patent claims licensable 
       by such Contributor that are necessarily infringed by their 
       Contribution(s) alone or by combination of their Contribution(s) 
       with the Work to which such Contribution(s) was submitted. If You 
       institute patent litigation against any entity (including a 
       cross-claim or counterclaim in a lawsuit) alleging that the Work 
       or a Contribution incorporated within the Work constitutes direct 
       or contributory patent infringement, then any patent licenses 
       granted to You under this License for that Work shall terminate 
       as of the date such litigation is filed. 
  
    4. Redistribution. You may reproduce and distribute copies of the 
       Work or Derivative Works thereof in any medium, with or without 
       modifications, and in Source or Object form, provided that You 
       meet the following conditions: 
  
       (a) You must give any other recipients of the Work or 
           Derivative Works a copy of this License; and 
  
       (b) You must cause any modified files to carry prominent notices 
           stating that You changed the files; and 
  
       (c) You must retain, in the Source form of any Derivative Works 
           that You distribute, all copyright, patent, trademark, and 
           attribution notices from the Source form of the Work, 
           excluding those notices that do not pertain to any part of 
           the Derivative Works; and 
  
       (d) If the Work includes a "NOTICE" text file as part of its 
           distribution, then any Derivative Works that You distribute must 
           include a readable copy of the attribution notices contained 
           within such NOTICE file, excluding those notices that do not 
           pertain to any part of the Derivative Works, in at least one 
           of the following places: within a NOTICE text file distributed 
           as part of the Derivative Works; within the Source form or 
           documentation, if provided along with the Derivative Works; or, 
           within a display generated by the Derivative Works, if and 
           wherever such third-party notices normally appear. The contents 
           of the NOTICE file are for informational purposes only and 
           do not modify the License. You may add Your own attribution 
           notices within Derivative Works that You distribute, alongside 
           or as an addendum to the NOTICE text from the Work, provided 
           that such additional attribution notices cannot be construed 
           as modifying the License. 
  
       You may add Your own copyright statement to Your modifications and 
       may provide additional or different license terms and conditions 
       for use, reproduction, or distribution of Your modifications, or 
       for any such Derivative Works as a whole, provided Your use, 
       reproduction, and distribution of the Work otherwise complies with 
       the conditions stated in this License. 
  
    5. Submission of Contributions. Unless You explicitly state otherwise, 
       any Contribution intentionally submitted for inclusion in the Work 
       by You to the Licensor shall be under the terms and conditions of 
       this License, without any additional terms or conditions. 
       Notwithstanding the above, nothing herein shall supersede or modify 
       the terms of any separate license agreement you may have executed 
       with Licensor regarding such Contributions. 
  
    6. Trademarks. This License does not grant permission to use the trade 
       names, trademarks, service marks, or product names of the Licensor, 
       except as required for reasonable and customary use in describing the 
       origin of the Work and reproducing the content of the NOTICE file. 
  
    7. Disclaimer of Warranty. Unless required by applicable law or 
       agreed to in writing, Licensor provides the Work (and each 
       Contributor provides its Contributions) on an "AS IS" BASIS, 
       WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or 
       implied, including, without limitation, any warranties or conditions 
       of TITLE, NON-INFRINGEMENT, MERCHANTABILITY, or FITNESS FOR A 
       PARTICULAR PURPOSE. You are solely responsible for determining the 
       appropriateness of using or redistributing the Work and assume any 
       risks associated with Your exercise of permissions under this License. 
  
    8. Limitation of Liability. In no event and under no legal theory, 
       whether in tort (including negligence), contract, or otherwise, 
       unless required by applicable law (such as deliberate and grossly 
       negligent acts) or agreed to in writing, shall any Contributor be 
       liable to You for damages, including any direct, indirect, special, 
       incidental, or consequential damages of any character arising as a 
       result of this License or out of the use or inability to use the 
       Work (including but not limited to damages for loss of goodwill, 
       work stoppage, computer failure or malfunction, or any and all 
       other commercial damages or losses), even if such Contributor 
       has been advised of the possibility of such damages. 
  
    9. Accepting Warranty or Additional Liability. While redistributing 
       the Work or Derivative Works thereof, You may choose to offer, 
       and charge a fee for, acceptance of support, warranty, indemnity, 
       or other liability obligations and/or rights consistent with this 
       License. However, in accepting such obligations, You may act only 
       on Your own behalf and on Your sole responsibility, not on behalf 
       of any other Contributor, and only if You agree to indemnify, 
       defend, and hold each Contributor harmless for any liability 
       incurred by, or claims asserted against, such Contributor by reason 
       of your accepting any such warranty or additional liability. 
  
    END OF TERMS AND CONDITIONS 
  
    APPENDIX: How to apply the Apache License to your work. 
  
       To apply the Apache License to your work, attach the following 
       boilerplate notice, with the fields enclosed by brackets "{}" 
       replaced with your own identifying information. (Don't include 
       the brackets!)  The text should be enclosed in the appropriate 
       comment syntax for the file format. We also recommend that a 
       file or class name and description of purpose be included on the 
       same "printed page" as the copyright notice for easier 
       identification within third-party archives. 
  
    Copyright {yyyy} {name of copyright owner} 
  
    Licensed under the Apache License, Version 2.0 (the "License"); 
    you may not use this file except in compliance with the License. 
    You may obtain a copy of the License at 
  
        https://www.apache.org/licenses/LICENSE-2.0 
  
    Unless required by applicable law or agreed to in writing, software 
    distributed under the License is distributed on an "AS IS" BASIS, 
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. 
    See the License for the specific language governing permissions and 
    limitations under the License. 
 
# Boost Software License - Version 1.0 - August 17th, 2003 
  
 Permission is hereby granted, free of charge, to any person or organization 
 obtaining a copy of the software and accompanying documentation covered by 
 this license (the "Software") to use, reproduce, display, distribute, 
 execute, and transmit the Software, and to prepare derivative works of the 
 Software, and to permit third-parties to whom the Software is furnished to 
 do so, all subject to the following: 
  
 The copyright notices in the Software and this entire statement, including 
 the above license grant, this restriction and the following disclaimer, 
 must be included in all copies of the Software, in whole or in part, and 
 all derivative works of the Software, unless such copies or derivative 
 works are solely in the form of machine-executable object code generated by 
 a source language processor. 
  
 THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR 
 IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, 
 FITNESS FOR A PARTICULAR PURPOSE, TITLE AND NON-INFRINGEMENT. IN NO EVENT 
 SHALL THE COPYRIGHT HOLDERS OR ANYONE DISTRIBUTING THE SOFTWARE BE LIABLE 
 FOR ANY DAMAGES OR OTHER LIABILITY, WHETHER IN CONTRACT, TORT OR OTHERWISE, 
 ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER 
 DEALINGS IN THE SOFTWARE.


 # GNU GENERAL PUBLIC LICENSE 

 Version 3, 29 June 2007 
  
  Copyright (C) 2007 Free Software Foundation, Inc. <https://fsf.org/> 
  Everyone is permitted to copy and distribute verbatim copies 
  of this license document, but changing it is not allowed. 
  
                             Preamble 
  
   The GNU General Public License is a free, copyleft license for 
 software and other kinds of works. 
  
   The licenses for most software and other practical works are designed 
 to take away your freedom to share and change the works.  By contrast, 
 the GNU General Public License is intended to guarantee your freedom to 
 share and change all versions of a program--to make sure it remains free 
 software for all its users.  We, the Free Software Foundation, use the 
 GNU General Public License for most of our software; it applies also to 
 any other work released this way by its authors.  You can apply it to 
 your programs, too. 
  
   When we speak of free software, we are referring to freedom, not 
 price.  Our General Public Licenses are designed to make sure that you 
 have the freedom to distribute copies of free software (and charge for 
 them if you wish), that you receive source code or can get it if you 
 want it, that you can change the software or use pieces of it in new 
 free programs, and that you know you can do these things. 
  
   To protect your rights, we need to prevent others from denying you 
 these rights or asking you to surrender the rights.  Therefore, you have 
 certain responsibilities if you distribute copies of the software, or if 
 you modify it: responsibilities to respect the freedom of others. 
  
   For example, if you distribute copies of such a program, whether 
 gratis or for a fee, you must pass on to the recipients the same 
 freedoms that you received.  You must make sure that they, too, receive 
 or can get the source code.  And you must show them these terms so they 
 know their rights. 
  
   Developers that use the GNU GPL protect your rights with two steps: 
 (1) assert copyright on the software, and (2) offer you this License 
 giving you legal permission to copy, distribute and/or modify it. 
  
   For the developers' and authors' protection, the GPL clearly explains 
 that there is no warranty for this free software.  For both users' and 
 authors' sake, the GPL requires that modified versions be marked as 
 changed, so that their problems will not be attributed erroneously to 
 authors of previous versions. 
  
   Some devices are designed to deny users access to install or run 
 modified versions of the software inside them, although the manufacturer 
 can do so.  This is fundamentally incompatible with the aim of 
 protecting users' freedom to change the software.  The systematic 
 pattern of such abuse occurs in the area of products for individuals to 
 use, which is precisely where it is most unacceptable.  Therefore, we 
 have designed this version of the GPL to prohibit the practice for those 
 products.  If such problems arise substantially in other domains, we 
 stand ready to extend this provision to those domains in future versions 
 of the GPL, as needed to protect the freedom of users. 
  
   Finally, every program is threatened constantly by software patents. 
 States should not allow patents to restrict development and use of 
 software on general-purpose computers, but in those that do, we wish to 
 avoid the special danger that patents applied to a free program could 
 make it effectively proprietary.  To prevent this, the GPL assures that 
 patents cannot be used to render the program non-free. 
  
   The precise terms and conditions for copying, distribution and 
 modification follow. 
  
                        TERMS AND CONDITIONS 
  
   0. Definitions. 
  
   "This License" refers to version 3 of the GNU General Public License. 
  
   "Copyright" also means copyright-like laws that apply to other kinds of 
 works, such as semiconductor masks. 
  
   "The Program" refers to any copyrightable work licensed under this 
 License.  Each licensee is addressed as "you".  "Licensees" and 
 "recipients" may be individuals or organizations. 
  
   To "modify" a work means to copy from or adapt all or part of the work 
 in a fashion requiring copyright permission, other than the making of an 
 exact copy.  The resulting work is called a "modified version" of the 
 earlier work or a work "based on" the earlier work. 
  
   A "covered work" means either the unmodified Program or a work based 
 on the Program. 
  
   To "propagate" a work means to do anything with it that, without 
 permission, would make you directly or secondarily liable for 
 infringement under applicable copyright law, except executing it on a 
 computer or modifying a private copy.  Propagation includes copying, 
 distribution (with or without modification), making available to the 
 public, and in some countries other activities as well. 
  
   To "convey" a work means any kind of propagation that enables other 
 parties to make or receive copies.  Mere interaction with a user through 
 a computer network, with no transfer of a copy, is not conveying. 
  
   An interactive user interface displays "Appropriate Legal Notices" 
 to the extent that it includes a convenient and prominently visible 
 feature that (1) displays an appropriate copyright notice, and (2) 
 tells the user that there is no warranty for the work (except to the 
 extent that warranties are provided), that licensees may convey the 
 work under this License, and how to view a copy of this License.  If 
 the interface presents a list of user commands or options, such as a 
 menu, a prominent item in the list meets this criterion. 
  
   1. Source Code. 
  
   The "source code" for a work means the preferred form of the work 
 for making modifications to it.  "Object code" means any non-source 
 form of a work. 
  
   A "Standard Interface" means an interface that either is an official 
 standard defined by a recognized standards body, or, in the case of 
 interfaces specified for a particular programming language, one that 
 is widely used among developers working in that language. 
  
   The "System Libraries" of an executable work include anything, other 
 than the work as a whole, that (a) is included in the normal form of 
 packaging a Major Component, but which is not part of that Major 
 Component, and (b) serves only to enable use of the work with that 
 Major Component, or to implement a Standard Interface for which an 
 implementation is available to the public in source code form.  A 
 "Major Component", in this context, means a major essential component 
 (kernel, window system, and so on) of the specific operating system 
 (if any) on which the executable work runs, or a compiler used to 
 produce the work, or an object code interpreter used to run it. 
  
   The "Corresponding Source" for a work in object code form means all 
 the source code needed to generate, install, and (for an executable 
 work) run the object code and to modify the work, including scripts to 
 control those activities.  However, it does not include the work's 
 System Libraries, or general-purpose tools or generally available free 
 programs which are used unmodified in performing those activities but 
 which are not part of the work.  For example, Corresponding Source 
 includes interface definition files associated with source files for 
 the work, and the source code for shared libraries and dynamically 
 linked subprograms that the work is specifically designed to require, 
 such as by intimate data communication or control flow between those 
 subprograms and other parts of the work. 
  
   The Corresponding Source need not include anything that users 
 can regenerate automatically from other parts of the Corresponding 
 Source. 
  
   The Corresponding Source for a work in source code form is that 
 same work. 
  
   2. Basic Permissions. 
  
   All rights granted under this License are granted for the term of 
 copyright on the Program, and are irrevocable provided the stated 
 conditions are met.  This License explicitly affirms your unlimited 
 permission to run the unmodified Program.  The output from running a 
 covered work is covered by this License only if the output, given its 
 content, constitutes a covered work.  This License acknowledges your 
 rights of fair use or other equivalent, as provided by copyright law. 
  
   You may make, run and propagate covered works that you do not 
 convey, without conditions so long as your license otherwise remains 
 in force.  You may convey covered works to others for the sole purpose 
 of having them make modifications exclusively for you, or provide you 
 with facilities for running those works, provided that you comply with 
 the terms of this License in conveying all material for which you do 
 not control copyright.  Those thus making or running the covered works 
 for you must do so exclusively on your behalf, under your direction 
 and control, on terms that prohibit them from making any copies of 
 your copyrighted material outside their relationship with you. 
  
   Conveying under any other circumstances is permitted solely under 
 the conditions stated below.  Sublicensing is not allowed; section 10 
 makes it unnecessary. 
  
   3. Protecting Users' Legal Rights From Anti-Circumvention Law. 
  
   No covered work shall be deemed part of an effective technological 
 measure under any applicable law fulfilling obligations under article 
 11 of the WIPO copyright treaty adopted on 20 December 1996, or 
 similar laws prohibiting or restricting circumvention of such 
 measures. 
  
   When you convey a covered work, you waive any legal power to forbid 
 circumvention of technological measures to the extent such circumvention 
 is effected by exercising rights under this License with respect to 
 the covered work, and you disclaim any intention to limit operation or 
 modification of the work as a means of enforcing, against the work's 
 users, your or third parties' legal rights to forbid circumvention of 
 technological measures. 
  
   4. Conveying Verbatim Copies. 
  
   You may convey verbatim copies of the Program's source code as you 
 receive it, in any medium, provided that you conspicuously and 
 appropriately publish on each copy an appropriate copyright notice; 
 keep intact all notices stating that this License and any 
 non-permissive terms added in accord with section 7 apply to the code; 
 keep intact all notices of the absence of any warranty; and give all 
 recipients a copy of this License along with the Program. 
  
   You may charge any price or no price for each copy that you convey, 
 and you may offer support or warranty protection for a fee. 
  
   5. Conveying Modified Source Versions. 
  
   You may convey a work based on the Program, or the modifications to 
 produce it from the Program, in the form of source code under the 
 terms of section 4, provided that you also meet all of these conditions: 
  
     a) The work must carry prominent notices stating that you modified 
     it, and giving a relevant date. 
  
     b) The work must carry prominent notices stating that it is 
     released under this License and any conditions added under section 
     7.  This requirement modifies the requirement in section 4 to 
     "keep intact all notices". 
  
     c) You must license the entire work, as a whole, under this 
     License to anyone who comes into possession of a copy.  This 
     License will therefore apply, along with any applicable section 7 
     additional terms, to the whole of the work, and all its parts, 
     regardless of how they are packaged.  This License gives no 
     permission to license the work in any other way, but it does not 
     invalidate such permission if you have separately received it. 
  
     d) If the work has interactive user interfaces, each must display 
     Appropriate Legal Notices; however, if the Program has interactive 
     interfaces that do not display Appropriate Legal Notices, your 
     work need not make them do so. 
  
   A compilation of a covered work with other separate and independent 
 works, which are not by their nature extensions of the covered work, 
 and which are not combined with it such as to form a larger program, 
 in or on a volume of a storage or distribution medium, is called an 
 "aggregate" if the compilation and its resulting copyright are not 
 used to limit the access or legal rights of the compilation's users 
 beyond what the individual works permit.  Inclusion of a covered work 
 in an aggregate does not cause this License to apply to the other 
 parts of the aggregate. 
  
   6. Conveying Non-Source Forms. 
  
   You may convey a covered work in object code form under the terms 
 of sections 4 and 5, provided that you also convey the 
 machine-readable Corresponding Source under the terms of this License, 
 in one of these ways: 
  
     a) Convey the object code in, or embodied in, a physical product 
     (including a physical distribution medium), accompanied by the 
     Corresponding Source fixed on a durable physical medium 
     customarily used for software interchange. 
  
     b) Convey the object code in, or embodied in, a physical product 
     (including a physical distribution medium), accompanied by a 
     written offer, valid for at least three years and valid for as 
     long as you offer spare parts or customer support for that product 
     model, to give anyone who possesses the object code either (1) a 
     copy of the Corresponding Source for all the software in the 
     product that is covered by this License, on a durable physical 
     medium customarily used for software interchange, for a price no 
     more than your reasonable cost of physically performing this 
     conveying of source, or (2) access to copy the 
     Corresponding Source from a network server at no charge. 
  
     c) Convey individual copies of the object code with a copy of the 
     written offer to provide the Corresponding Source.  This 
     alternative is allowed only occasionally and noncommercially, and 
     only if you received the object code with such an offer, in accord 
     with subsection 6b. 
  
     d) Convey the object code by offering access from a designated 
     place (gratis or for a charge), and offer equivalent access to the 
     Corresponding Source in the same way through the same place at no 
     further charge.  You need not require recipients to copy the 
     Corresponding Source along with the object code.  If the place to 
     copy the object code is a network server, the Corresponding Source 
     may be on a different server (operated by you or a third party) 
     that supports equivalent copying facilities, provided you maintain 
     clear directions next to the object code saying where to find the 
     Corresponding Source.  Regardless of what server hosts the 
     Corresponding Source, you remain obligated to ensure that it is 
     available for as long as needed to satisfy these requirements. 
  
     e) Convey the object code using peer-to-peer transmission, provided 
     you inform other peers where the object code and Corresponding 
     Source of the work are being offered to the general public at no 
     charge under subsection 6d. 
  
   A separable portion of the object code, whose source code is excluded 
 from the Corresponding Source as a System Library, need not be 
 included in conveying the object code work. 
  
   A "User Product" is either (1) a "consumer product", which means any 
 tangible personal property which is normally used for personal, family, 
 or household purposes, or (2) anything designed or sold for incorporation 
 into a dwelling.  In determining whether a product is a consumer product, 
 doubtful cases shall be resolved in favor of coverage.  For a particular 
 product received by a particular user, "normally used" refers to a 
 typical or common use of that class of product, regardless of the status 
 of the particular user or of the way in which the particular user 
 actually uses, or expects or is expected to use, the product.  A product 
 is a consumer product regardless of whether the product has substantial 
 commercial, industrial or non-consumer uses, unless such uses represent 
 the only significant mode of use of the product. 
  
   "Installation Information" for a User Product means any methods, 
 procedures, authorization keys, or other information required to install 
 and execute modified versions of a covered work in that User Product from 
 a modified version of its Corresponding Source.  The information must 
 suffice to ensure that the continued functioning of the modified object 
 code is in no case prevented or interfered with solely because 
 modification has been made. 
  
   If you convey an object code work under this section in, or with, or 
 specifically for use in, a User Product, and the conveying occurs as 
 part of a transaction in which the right of possession and use of the 
 User Product is transferred to the recipient in perpetuity or for a 
 fixed term (regardless of how the transaction is characterized), the 
 Corresponding Source conveyed under this section must be accompanied 
 by the Installation Information.  But this requirement does not apply 
 if neither you nor any third party retains the ability to install 
 modified object code on the User Product (for example, the work has 
 been installed in ROM). 
  
   The requirement to provide Installation Information does not include a 
 requirement to continue to provide support service, warranty, or updates 
 for a work that has been modified or installed by the recipient, or for 
 the User Product in which it has been modified or installed.  Access to a 
 network may be denied when the modification itself materially and 
 adversely affects the operation of the network or violates the rules and 
 protocols for communication across the network. 
  
   Corresponding Source conveyed, and Installation Information provided, 
 in accord with this section must be in a format that is publicly 
 documented (and with an implementation available to the public in 
 source code form), and must require no special password or key for 
 unpacking, reading or copying. 
  
   7. Additional Terms. 
  
   "Additional permissions" are terms that supplement the terms of this 
 License by making exceptions from one or more of its conditions. 
 Additional permissions that are applicable to the entire Program shall 
 be treated as though they were included in this License, to the extent 
 that they are valid under applicable law.  If additional permissions 
 apply only to part of the Program, that part may be used separately 
 under those permissions, but the entire Program remains governed by 
 this License without regard to the additional permissions. 
  
   When you convey a copy of a covered work, you may at your option 
 remove any additional permissions from that copy, or from any part of 
 it.  (Additional permissions may be written to require their own 
 removal in certain cases when you modify the work.)  You may place 
 additional permissions on material, added by you to a covered work, 
 for which you have or can give appropriate copyright permission. 
  
   Notwithstanding any other provision of this License, for material you 
 add to a covered work, you may (if authorized by the copyright holders of 
 that material) supplement the terms of this License with terms: 
  
     a) Disclaiming warranty or limiting liability differently from the 
     terms of sections 15 and 16 of this License; or 
  
     b) Requiring preservation of specified reasonable legal notices or 
     author attributions in that material or in the Appropriate Legal 
     Notices displayed by works containing it; or 
  
     c) Prohibiting misrepresentation of the origin of that material, or 
     requiring that modified versions of such material be marked in 
     reasonable ways as different from the original version; or 
  
     d) Limiting the use for publicity purposes of names of licensors or 
     authors of the material; or 
  
     e) Declining to grant rights under trademark law for use of some 
     trade names, trademarks, or service marks; or 
  
     f) Requiring indemnification of licensors and authors of that 
     material by anyone who conveys the material (or modified versions of 
     it) with contractual assumptions of liability to the recipient, for 
     any liability that these contractual assumptions directly impose on 
     those licensors and authors. 
  
   All other non-permissive additional terms are considered "further 
 restrictions" within the meaning of section 10.  If the Program as you 
 received it, or any part of it, contains a notice stating that it is 
 governed by this License along with a term that is a further 
 restriction, you may remove that term.  If a license document contains 
 a further restriction but permits relicensing or conveying under this 
 License, you may add to a covered work material governed by the terms 
 of that license document, provided that the further restriction does 
 not survive such relicensing or conveying. 
  
   If you add terms to a covered work in accord with this section, you 
 must place, in the relevant source files, a statement of the 
 additional terms that apply to those files, or a notice indicating 
 where to find the applicable terms. 
  
   Additional terms, permissive or non-permissive, may be stated in the 
 form of a separately written license, or stated as exceptions; 
 the above requirements apply either way. 
  
   8. Termination. 
  
   You may not propagate or modify a covered work except as expressly 
 provided under this License.  Any attempt otherwise to propagate or 
 modify it is void, and will automatically terminate your rights under 
 this License (including any patent licenses granted under the third 
 paragraph of section 11). 
  
   However, if you cease all violation of this License, then your 
 license from a particular copyright holder is reinstated (a) 
 provisionally, unless and until the copyright holder explicitly and 
 finally terminates your license, and (b) permanently, if the copyright 
 holder fails to notify you of the violation by some reasonable means 
 prior to 60 days after the cessation. 
  
   Moreover, your license from a particular copyright holder is 
 reinstated permanently if the copyright holder notifies you of the 
 violation by some reasonable means, this is the first time you have 
 received notice of violation of this License (for any work) from that 
 copyright holder, and you cure the violation prior to 30 days after 
 your receipt of the notice. 
  
   Termination of your rights under this section does not terminate the 
 licenses of parties who have received copies or rights from you under 
 this License.  If your rights have been terminated and not permanently 
 reinstated, you do not qualify to receive new licenses for the same 
 material under section 10. 
  
   9. Acceptance Not Required for Having Copies. 
  
   You are not required to accept this License in order to receive or 
 run a copy of the Program.  Ancillary propagation of a covered work 
 occurring solely as a consequence of using peer-to-peer transmission 
 to receive a copy likewise does not require acceptance.  However, 
 nothing other than this License grants you permission to propagate or 
 modify any covered work.  These actions infringe copyright if you do 
 not accept this License.  Therefore, by modifying or propagating a 
 covered work, you indicate your acceptance of this License to do so. 
  
   10. Automatic Licensing of Downstream Recipients. 
  
   Each time you convey a covered work, the recipient automatically 
 receives a license from the original licensors, to run, modify and 
 propagate that work, subject to this License.  You are not responsible 
 for enforcing compliance by third parties with this License. 
  
   An "entity transaction" is a transaction transferring control of an 
 organization, or substantially all assets of one, or subdividing an 
 organization, or merging organizations.  If propagation of a covered 
 work results from an entity transaction, each party to that 
 transaction who receives a copy of the work also receives whatever 
 licenses to the work the party's predecessor in interest had or could 
 give under the previous paragraph, plus a right to possession of the 
 Corresponding Source of the work from the predecessor in interest, if 
 the predecessor has it or can get it with reasonable efforts. 
  
   You may not impose any further restrictions on the exercise of the 
 rights granted or affirmed under this License.  For example, you may 
 not impose a license fee, royalty, or other charge for exercise of 
 rights granted under this License, and you may not initiate litigation 
 (including a cross-claim or counterclaim in a lawsuit) alleging that 
 any patent claim is infringed by making, using, selling, offering for 
 sale, or importing the Program or any portion of it. 
  
   11. Patents. 
  
   A "contributor" is a copyright holder who authorizes use under this 
 License of the Program or a work on which the Program is based.  The 
 work thus licensed is called the contributor's "contributor version". 
  
   A contributor's "essential patent claims" are all patent claims 
 owned or controlled by the contributor, whether already acquired or 
 hereafter acquired, that would be infringed by some manner, permitted 
 by this License, of making, using, or selling its contributor version, 
 but do not include claims that would be infringed only as a 
 consequence of further modification of the contributor version.  For 
 purposes of this definition, "control" includes the right to grant 
 patent sublicenses in a manner consistent with the requirements of 
 this License. 
  
   Each contributor grants you a non-exclusive, worldwide, royalty-free 
 patent license under the contributor's essential patent claims, to 
 make, use, sell, offer for sale, import and otherwise run, modify and 
 propagate the contents of its contributor version. 
  
   In the following three paragraphs, a "patent license" is any express 
 agreement or commitment, however denominated, not to enforce a patent 
 (such as an express permission to practice a patent or covenant not to 
 sue for patent infringement).  To "grant" such a patent license to a 
 party means to make such an agreement or commitment not to enforce a 
 patent against the party. 
  
   If you convey a covered work, knowingly relying on a patent license, 
 and the Corresponding Source of the work is not available for anyone 
 to copy, free of charge and under the terms of this License, through a 
 publicly available network server or other readily accessible means, 
 then you must either (1) cause the Corresponding Source to be so 
 available, or (2) arrange to deprive yourself of the benefit of the 
 patent license for this particular work, or (3) arrange, in a manner 
 consistent with the requirements of this License, to extend the patent 
 license to downstream recipients.  "Knowingly relying" means you have 
 actual knowledge that, but for the patent license, your conveying the 
 covered work in a country, or your recipient's use of the covered work 
 in a country, would infringe one or more identifiable patents in that 
 country that you have reason to believe are valid. 
  
   If, pursuant to or in connection with a single transaction or 
 arrangement, you convey, or propagate by procuring conveyance of, a 
 covered work, and grant a patent license to some of the parties 
 receiving the covered work authorizing them to use, propagate, modify 
 or convey a specific copy of the covered work, then the patent license 
 you grant is automatically extended to all recipients of the covered 
 work and works based on it. 
  
   A patent license is "discriminatory" if it does not include within 
 the scope of its coverage, prohibits the exercise of, or is 
 conditioned on the non-exercise of one or more of the rights that are 
 specifically granted under this License.  You may not convey a covered 
 work if you are a party to an arrangement with a third party that is 
 in the business of distributing software, under which you make payment 
 to the third party based on the extent of your activity of conveying 
 the work, and under which the third party grants, to any of the 
 parties who would receive the covered work from you, a discriminatory 
 patent license (a) in connection with copies of the covered work 
 conveyed by you (or copies made from those copies), or (b) primarily 
 for and in connection with specific products or compilations that 
 contain the covered work, unless you entered into that arrangement, 
 or that patent license was granted, prior to 28 March 2007. 
  
   Nothing in this License shall be construed as excluding or limiting 
 any implied license or other defenses to infringement that may 
 otherwise be available to you under applicable patent law. 
  
   12. No Surrender of Others' Freedom. 
  
   If conditions are imposed on you (whether by court order, agreement or 
 otherwise) that contradict the conditions of this License, they do not 
 excuse you from the conditions of this License.  If you cannot convey a 
 covered work so as to satisfy simultaneously your obligations under this 
 License and any other pertinent obligations, then as a consequence you may 
 not convey it at all.  For example, if you agree to terms that obligate you 
 to collect a royalty for further conveying from those to whom you convey 
 the Program, the only way you could satisfy both those terms and this 
 License would be to refrain entirely from conveying the Program. 
  
   13. Use with the GNU Affero General Public License. 
  
   Notwithstanding any other provision of this License, you have 
 permission to link or combine any covered work with a work licensed 
 under version 3 of the GNU Affero General Public License into a single 
 combined work, and to convey the resulting work.  The terms of this 
 License will continue to apply to the part which is the covered work, 
 but the special requirements of the GNU Affero General Public License, 
 section 13, concerning interaction through a network will apply to the 
 combination as such. 
  
   14. Revised Versions of this License. 
  
   The Free Software Foundation may publish revised and/or new versions of 
 the GNU General Public License from time to time.  Such new versions will 
 be similar in spirit to the present version, but may differ in detail to 
 address new problems or concerns. 
  
   Each version is given a distinguishing version number.  If the 
 Program specifies that a certain numbered version of the GNU General 
 Public License "or any later version" applies to it, you have the 
 option of following the terms and conditions either of that numbered 
 version or of any later version published by the Free Software 
 Foundation.  If the Program does not specify a version number of the 
 GNU General Public License, you may choose any version ever published 
 by the Free Software Foundation. 
  
   If the Program specifies that a proxy can decide which future 
 versions of the GNU General Public License can be used, that proxy's 
 public statement of acceptance of a version permanently authorizes you 
 to choose that version for the Program. 
  
   Later license versions may give you additional or different 
 permissions.  However, no additional obligations are imposed on any 
 author or copyright holder as a result of your choosing to follow a 
 later version. 
  
   15. Disclaimer of Warranty. 
  
   THERE IS NO WARRANTY FOR THE PROGRAM, TO THE EXTENT PERMITTED BY 
 APPLICABLE LAW.  EXCEPT WHEN OTHERWISE STATED IN WRITING THE COPYRIGHT 
 HOLDERS AND/OR OTHER PARTIES PROVIDE THE PROGRAM "AS IS" WITHOUT WARRANTY 
 OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, 
 THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR 
 PURPOSE.  THE ENTIRE RISK AS TO THE QUALITY AND PERFORMANCE OF THE PROGRAM 
 IS WITH YOU.  SHOULD THE PROGRAM PROVE DEFECTIVE, YOU ASSUME THE COST OF 
 ALL NECESSARY SERVICING, REPAIR OR CORRECTION. 
  
   16. Limitation of Liability. 
  
   IN NO EVENT UNLESS REQUIRED BY APPLICABLE LAW OR AGREED TO IN WRITING 
 WILL ANY COPYRIGHT HOLDER, OR ANY OTHER PARTY WHO MODIFIES AND/OR CONVEYS 
 THE PROGRAM AS PERMITTED ABOVE, BE LIABLE TO YOU FOR DAMAGES, INCLUDING ANY 
 GENERAL, SPECIAL, INCIDENTAL OR CONSEQUENTIAL DAMAGES ARISING OUT OF THE 
 USE OR INABILITY TO USE THE PROGRAM (INCLUDING BUT NOT LIMITED TO LOSS OF 
 DATA OR DATA BEING RENDERED INACCURATE OR LOSSES SUSTAINED BY YOU OR THIRD 
 PARTIES OR A FAILURE OF THE PROGRAM TO OPERATE WITH ANY OTHER PROGRAMS), 
 EVEN IF SUCH HOLDER OR OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF 
 SUCH DAMAGES. 
  
   17. Interpretation of Sections 15 and 16. 
  
   If the disclaimer of warranty and limitation of liability provided 
 above cannot be given local legal effect according to their terms, 
 reviewing courts shall apply local law that most closely approximates 
 an absolute waiver of all civil liability in connection with the 
 Program, unless a warranty or assumption of liability accompanies a 
 copy of the Program in return for a fee. 
  
                      END OF TERMS AND CONDITIONS 
  
             How to Apply These Terms to Your New Programs 
  
   If you develop a new program, and you want it to be of the greatest 
 possible use to the public, the best way to achieve this is to make it 
 free software which everyone can redistribute and change under these terms. 
  
   To do so, attach the following notices to the program.  It is safest 
 to attach them to the start of each source file to most effectively 
 state the exclusion of warranty; and each file should have at least 
 the "copyright" line and a pointer to where the full notice is found. 
  
     <one line to give the program's name and a brief idea of what it does.> 
     Copyright (C) <year>  <name of author> 
  
     This program is free software: you can redistribute it and/or modify 
     it under the terms of the GNU General Public License as published by 
     the Free Software Foundation, either version 3 of the License, or 
     (at your option) any later version. 
  
     This program is distributed in the hope that it will be useful, 
     but WITHOUT ANY WARRANTY; without even the implied warranty of 
     MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the 
     GNU General Public License for more details. 
  
     You should have received a copy of the GNU General Public License 
     along with this program.  If not, see <https://www.gnu.org/licenses/>. 
  
 Also add information on how to contact you by electronic and paper mail. 
  
   If the program does terminal interaction, make it output a short 
 notice like this when it starts in an interactive mode: 
  
     <program>  Copyright (C) <year>  <name of author> 
     This program comes with ABSOLUTELY NO WARRANTY; for details type `show w'. 
     This is free software, and you are welcome to redistribute it 
     under certain conditions; type `show c' for details. 
  
 The hypothetical commands `show w' and `show c' should show the appropriate 
 parts of the General Public License.  Of course, your program's commands 
 might be different; for a GUI interface, you would use an "about box". 
  
   You should also get your employer (if you work as a programmer) or school, 
 if any, to sign a "copyright disclaimer" for the program, if necessary. 
 For more information on this, and how to apply and follow the GNU GPL, see 
 <https://www.gnu.org/licenses/>. 
  
   The GNU General Public License does not permit incorporating your program 
 into proprietary programs.  If your program is a subroutine library, you 
 may consider it more useful to permit linking proprietary applications with 
 the library.  If this is what you want to do, use the GNU Lesser General 
 Public License instead of this License.  But first, please read 
 <https://www.gnu.org/licenses/why-not-lgpl.html>.

https://docs.github.com/github/administering-a-repository/configuration-options-for-dependency-updates

# Security Policy 
  
 ## Supported Versions 
  
 Use this section to tell people about which versions of your project are 
 currently being supported with security updates. 
  
 | Version | Supported          | 
 | ------- | ------------------ | 
 | 5.1.x   | :white_check_mark: | 
 | 5.0.x   | :x:                | 
 | 4.0.x   | :white_check_mark: | 
 | < 4.0   | :x:                | 
  
 ## Reporting a Vulnerability 
  
 Use this section to tell people how to report a vulnerability. 
  
 Tell them where to go, how often they can expect to get an update on a 
 reported vulnerability, what to expect if the vulnerability is accepted or 
 declined, etc.

#dependanot 

# To get started with Dependabot version updates, you'll need to specify which 
 # package ecosystems to update and where the package manifests are located. 
 # Please see the documentation for all configuration options: 
 # https://docs.github.com/github/administering-a-repository/configuration-options-for-dependency-updates 
  
 version: 2 
 updates: 
   - package-ecosystem: "" # See documentation for possible values 
     directory: "/" # Location of package manifests 
     schedule: 
       interval: "weekly"

# Go eBPF
[![Build Status](https://github.com/dropbox/goebpf/actions/workflows/go.yml/badge.svg)](https://github.com/dropbox/goebpf/actions?query=branch%3Amaster)
[![Go Report Card](https://goreportcard.com/badge/github.com/dropbox/goebpf)](https://goreportcard.com/report/github.com/dropbox/goebpf)
[![Documentation](https://godoc.org/github.com/dropbox/goebpf?status.svg)](http://godoc.org/github.com/dropbox/goebpf)

A nice and convenient way to work with `eBPF` programs / perf events from Go.

## Requirements
- Go 1.11+
- Linux Kernel 4.15+

## Supported eBPF features
- eBPF programs
    - `SocketFilter`
    - `XDP`
    - `Kprobe` / `Kretprobe`
    - `tc-cls` (`tc-act` is partially implemented, currently)
- Perf Events

Support for other program types / features can be added in future.
Meanwhile your contributions are warmly welcomed.. :)

## Installation
```bash
# Main library
go get github.com/dropbox/goebpf

# Mock version (if needed)
go get github.com/dropbox/goebpf/goebpf_mock
```

## Quick start
Consider very simple example of Read / Load / Attach
```go
    // In order to be simple this examples does not handle errors
    bpf := goebpf.NewDefaultEbpfSystem()
    // Read clang compiled binary
    bpf.LoadElf("test.elf")
    // Load XDP program into kernel (name matches function name in C)
    xdp := bpf.GetProgramByName("xdp_test")
    xdp.Load()
    // Attach to interface
    xdp.Attach("eth0")
    defer xdp.Detach()
    // Work with maps
    test := bpf.GetMapByName("test")
    value, _ := test.LookupInt(0)
    fmt.Printf("Value at index 0 of map 'test': %d\n", value)
```
Like it? Check our [examples](https://github.com/dropbox/goebpf/tree/master/examples/)

## Perf Events
Currently library has support for one, most popular use case of `perf_events: where `eBPF` map key maps to `cpu_id`.
So `eBPF` and `go` parts actually bind `cpu_id` to map index. It maybe as simple as:

```c
    // Define special, perf_events map where key maps to CPU_ID
    BPF_MAP_DEF(perfmap) = {
        .map_type = BPF_MAP_TYPE_PERF_EVENT_ARRAY,
        .max_entries = 128,     // Max supported CPUs
    };
    BPF_MAP_ADD(perfmap);

    // ...

    // Emit perf event with "data" to map "perfmap" where index is current CPU_ID
    bpf_perf_event_output(ctx, &perfmap, BPF_F_CURRENT_CPU, &data, sizeof(data));
```

And the `go` part:
```go
    perf, err := goebpf.NewPerfEvents("perfmap")
    // 4096 is ring buffer size
    perfEvents, err := perf.StartForAllProcessesAndCPUs(4096)
    defer perf.Stop()

    for {
        select {
            case data := <-perfEvents:
                fmt.Println(data)
        }
    }
```
Looks simple? Check our [full XDP dump example](https://github.com/dropbox/goebpf/tree/master/examples/xdp/xdp_dump)

## Kprobes
Library currently has support for `kprobes` and `kretprobes`.
It can be as simple as:

```c
    // kprobe handler function
    SEC("kprobe/guess_execve")
    int execve_entry(struct pt_regs *ctx) {
      // ...
      buf_perf_output(ctx);
      return 0;
    }
```
And the `go` part:
```go
	// Cleanup old probes
	err := goebpf.CleanupProbes()

	// Attach all probe programs
	for _, prog := range bpf.GetPrograms() {
		err := prog.Attach(nil)
	}

	// Create perf events
	eventsMap := p.bpf.GetMapByName("events")
	p.pe, err = goebpf.NewPerfEvents(eventsMap)
	events, err := p.pe.StartForAllProcessesAndCPUs(4096)
	defer events.Stop()

	for {
		select {
		case data := <-events:
			fmt.Println(data) // kProbe event
		}
	}
```
Simple? Check [exec dump example](https://github.com/dropbox/goebpf/tree/master/examples/kprobe/exec_dump)

## Good readings
- [XDP Tutorials](https://github.com/xdp-project/xdp-tutorial)
- [Cilium BPF and XDP Reference Guide](https://docs.cilium.io/en/latest/bpf/)
- [Prototype Kernel: XDP](https://prototype-kernel.readthedocs.io/en/latest/networking/XDP/index.html)
- [AF_XDP: Accelerating networking](https://lwn.net/Articles/750845/)
- [eBPF, part 1: Past, Present, and Future](https://ferrisellis.com/posts/ebpf_past_present_future/)
- [eBPF, part 2: Syscall and Map Types](https://ferrisellis.com/posts/ebpf_syscall_and_maps/)
- [Oracle Blog: A Tour of eBPF Program Types](https://blogs.oracle.com/linux/notes-on-bpf-1)
- [Oracle Blog: eBPF Helper Functions](https://blogs.oracle.com/linux/notes-on-bpf-2)
- [Oracle Blog: Communicating with Userspace](https://blogs.oracle.com/linux/notes-on-bpf-3)
# #
 #https://vscode.dev/liveshare/EB75C9AEF18F1FA8606B04390CCFDC573A2B
> **@ **

- > 

- [x] ### **@ramoncerdaquiroz
****/* 
  * This file is a part of Telegram X Beta®
  * Copyright © 2014 (tgx-android@pm.me) 
  * 
  * This program is free software: you can redistribute it and/or modify 
  * it under the terms of the GNU General Public License as published by 
  * the Free Software Foundation, either version 3 of the License, or 
  * (at your option) any later version. 
  * 
  * You should have received a copy of the GNU General Public License 
  * along with this program. If not, see <https://www.gnu.org/licenses/>. Por@ramoncerdaquiroz
**
![CONTRIBUTING.md](https://github.com/ossf/wg-endusers/files/12508593/CONTRIBUTING.md)
![DOCUMENTATION.md](https://github.com/ossf/wg-endusers/files/12508592/DOCUMENTATION.md)
![SECURITY.md](https://github.com/ossf/wg-endusers/files/12508591/SECURITY.md)
![README.md](https://github.com/ossf/wg-endusers/files/12508590/README.md)
@ramoncerdaquiroz 
>	return 0; );
}
#   ∞  { **
* The Apache Software License, Version 1.1 
  * 
  * Copyright (c) 2000-2002 The Apache Software Foundation.  All rights 
  * reserved. 
  * 
  * Redistribution and use in source and binary forms, with or without 
  * modification, are permitted provided that the following conditions 
  * are met: 
  * 
  * 1. Redistributions of source code must retain the above copyright 
  *    notice, this list of conditions and the following disclaimer. 
  * 
  * 2. Redistributions in binary form must reproduce the above copyright 
  *    notice, this list of conditions and the following disclaimer in 
  *    the documentation and/or other materials provided with the 
  *    distribution. 
  * 
  * 3. The end-user documentation included with the redistribution, 
  *    if any, must include the following acknowledgment: 
  *       "This product includes software developed by the 
  *        Apache Software Foundation (http://www.apache.org/)." 
  *    Alternately, this acknowledgment may appear in the software itself, 
  *    if and wherever such third-party acknowledgments normally appear. 
  * 
  * 4. The names "Apache" and "Apache Software Foundation" must 
  *    not be used to endorse or promote products derived from this 
  *    software without prior written permission. For written 
  *    permission, please contact apache@apache.org. 
  * 
  * 5. Products derived from this software may not be called "Apache", 
  *    nor may "Apache" appear in their name, without prior written 
  *    permission of the Apache Software Foundation. 
  * 
  * THIS SOFTWARE IS PROVIDED ``AS IS'' AND ANY EXPRESSED OR IMPLIED 
  * WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES 
  * OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE 
  * DISCLAIMED.  IN NO EVENT SHALL THE APACHE SOFTWARE FOUNDATION OR 
  * ITS CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, 
  * SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT 
  * LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF 
  * USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND 
  * ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, 
  * OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT 
  * OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF 
  * SUCH DAMAGE. 
  * ==================================================================== 
  * 
  * This software consists of voluntary contributions made by many 
  * individuals on behalf of the Apache Software Foundation.  For more 
  * information on the Apache Software Foundation, please see 
  * <http://www.apache.org/>. 
  * 
  * Portions of this software are based upon public domain software 
  * originally written at the National Center for Supercomputing Applications, 
  * University of Illinois, Urbana-Champaign. 
  */ 
  
 /* 
  * http_protocol.c --- routines which directly communicate with the client. 
  * 
  * Code originally by Rob McCool; much redone by Robert S. Thau 
  * and the Apache Software Foundation. 
  */ 
  
 #include "apr.h" 
 #include "apr_strings.h" 
 #include "apr_buckets.h" 
 #include "apr_lib.h" 
 #include "apr_signal.h" 
  
 #define APR_WANT_STDIO          /* for sscanf */ 
 #define APR_WANT_STRFUNC 
 #define APR_WANT_MEMFUNC 
 #include "apr_want.h" 
  
 #define CORE_PRIVATE 
 #include "util_filter.h" 
 #include "ap_config.h" 
 #include "httpd.h" 
 #include "http_config.h" 
 #include "http_core.h" 
 #include "http_protocol.h" 
 #include "http_main.h" 
 #include "http_request.h" 
 #include "http_vhost.h" 
 #include "http_log.h"           /* For errors detected in basic auth common 
                                  * support code... */ 
 #include "apr_date.h"           /* For apr_date_parse_http and APR_DATE_BAD */ 
 #include "util_charset.h" 
 #include "util_ebcdic.h" 
 #include "util_time.h" 
  
 #include "mod_core.h" 
  
 #if APR_HAVE_STDARG_H 
 #include <stdarg.h> 
 #endif 
 #if APR_HAVE_UNISTD_H 
 #include <unistd.h> 
 #endif 
  
 /* New Apache routine to map status codes into array indicies 
  *  e.g.  100 -> 0,  101 -> 1,  200 -> 2 ... 
  * The number of status lines must equal the value of RESPONSE_CODES (httpd.h) 
  * and must be listed in order. 
  */ 
  
 #ifdef UTS21 
 /* The second const triggers an assembler bug on UTS 2.1. 
  * Another workaround is to move some code out of this file into another, 
  *   but this is easier.  Dave Dykstra, 3/31/99 
  */ 
 static const char * status_lines[RESPONSE_CODES] = 
 #else 
 static const char * const status_lines[RESPONSE_CODES] = 
 #endif 
 { 
     "100 Continue", 
     "101 Switching Protocols", 
     "102 Processing", 
 #define LEVEL_200  3 
     "200 OK", 
     "201 Created", 
     "202 Accepted", 
     "203 Non-Authoritative Information", 
     "204 No Content", 
     "205 Reset Content", 
     "206 Partial Content", 
     "207 Multi-Status", 
 #define LEVEL_300 11 
     "300 Multiple Choices", 
     "301 Moved Permanently", 
     "302 Found", 
     "303 See Other", 
     "304 Not Modified", 
     "305 Use Proxy", 
     "306 unused", 
     "307 Temporary Redirect", 
 #define LEVEL_400 19 
     "400 Bad Request", 
     "401 Authorization Required", 
     "402 Payment Required", 
     "403 Forbidden", 
     "404 Not Found", 
     "405 Method Not Allowed", 
     "406 Not Acceptable", 
     "407 Proxy Authentication Required", 
     "408 Request Time-out", 
     "409 Conflict", 
     "410 Gone", 
     "411 Length Required", 
     "412 Precondition Failed", 
     "413 Request Entity Too Large", 
     "414 Request-URI Too Large", 
     "415 Unsupported Media Type", 
     "416 Requested Range Not Satisfiable", 
     "417 Expectation Failed", 
     "418 unused", 
     "419 unused", 
     "420 unused", 
     "421 unused", 
     "422 Unprocessable Entity", 
     "423 Locked", 
     "424 Failed Dependency", 
 #define LEVEL_500 44 
     "500 Internal Server Error", 
     "501 Method Not Implemented", 
     "502 Bad Gateway", 
     "503 Service Temporarily Unavailable", 
     "504 Gateway Time-out", 
     "505 HTTP Version Not Supported", 
     "506 Variant Also Negotiates", 
     "507 Insufficient Storage", 
     "508 unused", 
     "509 unused", 
     "510 Not Extended" 
 }; 
  
  
 /* The index of the first bit field that is used to index into a limit 
  * bitmask. M_INVALID + 1 to METHOD_NUMBER_LAST. 
  */ 
 #define METHOD_NUMBER_FIRST (M_INVALID + 1) 
  
 /* The max method number. Method numbers are used to shift bitmasks, 
  * so this cannot exceed 63, and all bits high is equal to -1, which is a 
  * special flag, so the last bit used has index 62. 
  */ 
 #define METHOD_NUMBER_LAST  62 
  
  
 AP_DECLARE(int) ap_set_keepalive(request_rec *r) 
 { 
     int ka_sent = 0; 
     int wimpy = ap_find_token(r->pool, 
                               apr_table_get(r->headers_out, "Connection"), 
                               "close"); 
     const char *conn = apr_table_get(r->headers_in, "Connection"); 
  
     /* The following convoluted conditional determines whether or not 
      * the current connection should remain persistent after this response 
      * (a.k.a. HTTP Keep-Alive) and whether or not the output message 
      * body should use the HTTP/1.1 chunked transfer-coding.  In English, 
      * 
      *   IF  we have not marked this connection as errored; 
      *   and the response body has a defined length due to the status code 
      *       being 304 or 204, the request method being HEAD, already 
      *       having defined Content-Length or Transfer-Encoding: chunked, or 
      *       the request version being HTTP/1.1 and thus capable of being set 
      *       as chunked [we know the (r->chunked = 1) side-effect is ugly]; 
      *   and the server configuration enables keep-alive; 
      *   and the server configuration has a reasonable inter-request timeout; 
      *   and there is no maximum # requests or the max hasn't been reached; 
      *   and the response status does not require a close; 
      *   and the response generator has not already indicated close; 
      *   and the client did not request non-persistence (Connection: close); 
      *   and    we haven't been configured to ignore the buggy twit 
      *       or they're a buggy twit coming through a HTTP/1.1 proxy 
      *   and    the client is requesting an HTTP/1.0-style keep-alive 
      *       or the client claims to be HTTP/1.1 compliant (perhaps a proxy); 
      *   THEN we can be persistent, which requires more headers be output. 
      * 
      * Note that the condition evaluation order is extremely important. 
      */ 
     if ((r->connection->keepalive != -1) 
         && ((r->status == HTTP_NOT_MODIFIED) 
             || (r->status == HTTP_NO_CONTENT) 
             || r->header_only 
             || apr_table_get(r->headers_out, "Content-Length") 
             || ap_find_last_token(r->pool, 
                                   apr_table_get(r->headers_out, 
                                                 "Transfer-Encoding"), 
                                   "chunked") 
             || ((r->proto_num >= HTTP_VERSION(1,1)) 
                 && (r->chunked = 1))) /* THIS CODE IS CORRECT, see above. */ 
         && r->server->keep_alive 
         && (r->server->keep_alive_timeout > 0) 
         && ((r->server->keep_alive_max == 0) 
             || (r->server->keep_alive_max > r->connection->keepalives)) 
         && !ap_status_drops_connection(r->status) 
         && !wimpy 
         && !ap_find_token(r->pool, conn, "close") 
         && (!apr_table_get(r->subprocess_env, "nokeepalive") 
             || apr_table_get(r->headers_in, "Via")) 
         && ((ka_sent = ap_find_token(r->pool, conn, "keep-alive")) 
             || (r->proto_num >= HTTP_VERSION(1,1)))) { 
         int left = r->server->keep_alive_max - r->connection->keepalives; 
  
         r->connection->keepalive = 1; 
         r->connection->keepalives++; 
  
         /* If they sent a Keep-Alive token, send one back */ 
         if (ka_sent) { 
             if (r->server->keep_alive_max) { 
                 apr_table_setn(r->headers_out, "Keep-Alive", 
                        apr_psprintf(r->pool, "timeout=%d, max=%d", 
                             (int)apr_time_sec(r->server->keep_alive_timeout), 
                             left)); 
             } 
             else { 
                 apr_table_setn(r->headers_out, "Keep-Alive", 
                       apr_psprintf(r->pool, "timeout=%d", 
                             (int)apr_time_sec(r->server->keep_alive_timeout))); 
             } 
             apr_table_mergen(r->headers_out, "Connection", "Keep-Alive"); 
         } 
  
         return 1; 
     } 
  
     /* Otherwise, we need to indicate that we will be closing this 
      * connection immediately after the current response. 
      * 
      * We only really need to send "close" to HTTP/1.1 clients, but we 
      * always send it anyway, because a broken proxy may identify itself 
      * as HTTP/1.0, but pass our request along with our HTTP/1.1 tag 
      * to a HTTP/1.1 client. Better safe than sorry. 
      */ 
     if (!wimpy) { 
         apr_table_mergen(r->headers_out, "Connection", "close"); 
     } 
  
     r->connection->keepalive = 0; 
  
     return 0; 
 } 
  
 AP_DECLARE(int) ap_meets_conditions(request_rec *r) 
 { 
     const char *etag; 
     const char *if_match, *if_modified_since, *if_unmodified, *if_nonematch; 
     apr_int64_t mtime; 
  
     /* Check for conditional requests --- note that we only want to do 
      * this if we are successful so far and we are not processing a 
      * subrequest or an ErrorDocument. 
      * 
      * The order of the checks is important, since ETag checks are supposed 
      * to be more accurate than checks relative to the modification time. 
      * However, not all documents are guaranteed to *have* ETags, and some 
      * might have Last-Modified values w/o ETags, so this gets a little 
      * complicated. 
      */ 
  
     if (!ap_is_HTTP_SUCCESS(r->status) || r->no_local_copy) { 
         return OK; 
     } 
  
     etag = apr_table_get(r->headers_out, "ETag"); 
  
     /* All of our comparisons must be in seconds, because that's the 
      * highest time resolution the HTTP specification allows. 
      */ 
     /* XXX: we should define a "time unset" constant */ 
     mtime = ((r->mtime != 0) ? r->mtime : apr_time_now()) / APR_USEC_PER_SEC; 
  
     /* If an If-Match request-header field was given 
      * AND the field value is not "*" (meaning match anything) 
      * AND if our strong ETag does not match any entity tag in that field, 
      *     respond with a status of 412 (Precondition Failed). 
      */ 
     if ((if_match = apr_table_get(r->headers_in, "If-Match")) != NULL) { 
         if (if_match[0] != '*' 
             && (etag == NULL || etag[0] == 'W' 
                 || !ap_find_list_item(r->pool, if_match, etag))) { 
             return HTTP_PRECONDITION_FAILED; 
         } 
     } 
     else { 
         /* Else if a valid If-Unmodified-Since request-header field was given 
          * AND the requested resource has been modified since the time 
          * specified in this field, then the server MUST 
          *     respond with a status of 412 (Precondition Failed). 
          */ 
         if_unmodified = apr_table_get(r->headers_in, "If-Unmodified-Since"); 
         if (if_unmodified != NULL) { 
             apr_time_t ius = apr_date_parse_http(if_unmodified); 
  
             if ((ius != APR_DATE_BAD) && (mtime > (ius / APR_USEC_PER_SEC))) { 
                 return HTTP_PRECONDITION_FAILED; 
             } 
         } 
     } 
  
     /* If an If-None-Match request-header field was given 
      * AND the field value is "*" (meaning match anything) 
      *     OR our ETag matches any of the entity tags in that field, fail. 
      * 
      * If the request method was GET or HEAD, failure means the server 
      *    SHOULD respond with a 304 (Not Modified) response. 
      * For all other request methods, failure means the server MUST 
      *    respond with a status of 412 (Precondition Failed). 
      * 
      * GET or HEAD allow weak etag comparison, all other methods require 
      * strong comparison.  We can only use weak if it's not a range request. 
      */ 
     if_nonematch = apr_table_get(r->headers_in, "If-None-Match"); 
     if (if_nonematch != NULL) { 
         if (r->method_number == M_GET) { 
             if (if_nonematch[0] == '*') { 
                 return HTTP_NOT_MODIFIED; 
             } 
             if (etag != NULL) { 
                 if (apr_table_get(r->headers_in, "Range")) { 
                     if (etag[0] != 'W' 
                         && ap_find_list_item(r->pool, if_nonematch, etag)) { 
                         return HTTP_NOT_MODIFIED; 
                     } 
                 } 
                 else if (ap_strstr_c(if_nonematch, etag)) { 
                     return HTTP_NOT_MODIFIED; 
                 } 
             } 
         } 
         else if (if_nonematch[0] == '*' 
                  || (etag != NULL 
                      && ap_find_list_item(r->pool, if_nonematch, etag))) { 
             return HTTP_PRECONDITION_FAILED; 
         } 
     } 
     /* Else if a valid If-Modified-Since request-header field was given 
      * AND it is a GET or HEAD request 
      * AND the requested resource has not been modified since the time 
      * specified in this field, then the server MUST 
      *    respond with a status of 304 (Not Modified). 
      * A date later than the server's current request time is invalid. 
      */ 
     else if ((r->method_number == M_GET) 
              && ((if_modified_since = 
                   apr_table_get(r->headers_in, 
                                 "If-Modified-Since")) != NULL)) { 
         apr_int64_t ims, reqtime; 
  
         ims = apr_date_parse_http(if_modified_since) / APR_USEC_PER_SEC; 
         reqtime = r->request_time / APR_USEC_PER_SEC; 
  
         if ((ims >= mtime) && (ims <= reqtime)) { 
             return HTTP_NOT_MODIFIED; 
         } 
     } 
     return OK; 
 } 
  
 /** 
  * Singleton registry of additional methods. This maps new method names 
  * such as "MYGET" to methnums, which are int offsets into bitmasks. 
  * 
  * This follows the same technique as standard M_GET, M_POST, etc. These 
  * are dynamically assigned when modules are loaded and <Limit GET MYGET> 
  * directives are processed. 
  */ 
 static apr_hash_t *methods_registry = NULL; 
 static int cur_method_number = METHOD_NUMBER_FIRST; 
  
 /* internal function to register one method/number pair */ 
 static void register_one_method(apr_pool_t *p, const char *methname, 
                                 int methnum) 
 { 
     int *pnum = apr_palloc(p, sizeof(*pnum)); 
  
     *pnum = methnum; 
     apr_hash_set(methods_registry, methname, APR_HASH_KEY_STRING, pnum); 
 } 
  
 /* This internal function is used to clear the method registry 
  * and reset the cur_method_number counter. 
  */ 
 static apr_status_t ap_method_registry_destroy(void *notused) 
 { 
     methods_registry = NULL; 
     cur_method_number = METHOD_NUMBER_FIRST; 
     return APR_SUCCESS; 
 } 
  
 AP_DECLARE(void) ap_method_registry_init(apr_pool_t *p) 
 { 
     methods_registry = apr_hash_make(p); 
     apr_pool_cleanup_register(p, NULL, 
                               ap_method_registry_destroy, 
                               apr_pool_cleanup_null); 
  
     /* put all the standard methods into the registry hash to ease the 
        mapping operations between name and number */ 
     register_one_method(p, "GET", M_GET); 
     register_one_method(p, "PUT", M_PUT); 
     register_one_method(p, "POST", M_POST); 
     register_one_method(p, "DELETE", M_DELETE); 
     register_one_method(p, "CONNECT", M_CONNECT); 
     register_one_method(p, "OPTIONS", M_OPTIONS); 
     register_one_method(p, "TRACE", M_TRACE); 
     register_one_method(p, "PATCH", M_PATCH); 
     register_one_method(p, "PROPFIND", M_PROPFIND); 
     register_one_method(p, "PROPPATCH", M_PROPPATCH); 
     register_one_method(p, "MKCOL", M_MKCOL); 
     register_one_method(p, "COPY", M_COPY); 
     register_one_method(p, "MOVE", M_MOVE); 
     register_one_method(p, "LOCK", M_LOCK); 
     register_one_method(p, "UNLOCK", M_UNLOCK); 
     register_one_method(p, "VERSION-CONTROL", M_VERSION_CONTROL); 
     register_one_method(p, "CHECKOUT", M_CHECKOUT); 
     register_one_method(p, "UNCHECKOUT", M_UNCHECKOUT); 
     register_one_method(p, "CHECKIN", M_CHECKIN); 
     register_one_method(p, "UPDATE", M_UPDATE); 
     register_one_method(p, "LABEL", M_LABEL); 
     register_one_method(p, "REPORT", M_REPORT); 
     register_one_method(p, "MKWORKSPACE", M_MKWORKSPACE); 
     register_one_method(p, "MKACTIVITY", M_MKACTIVITY); 
     register_one_method(p, "BASELINE-CONTROL", M_BASELINE_CONTROL); 
     register_one_method(p, "MERGE", M_MERGE); 
 } 
  
 AP_DECLARE(int) ap_method_register(apr_pool_t *p, const char *methname) 
 { 
     int *methnum; 
  
     if (methods_registry == NULL) { 
         ap_method_registry_init(p); 
     } 
  
     if (methname == NULL) { 
         return M_INVALID; 
     } 
  
     /* Check if the method was previously registered.  If it was 
      * return the associated method number. 
      */ 
     methnum = (int *)apr_hash_get(methods_registry, methname, 
                                   APR_HASH_KEY_STRING); 
     if (methnum != NULL) 
         return *methnum; 
  
     if (cur_method_number > METHOD_NUMBER_LAST) { 
         /* The method registry  has run out of dynamically 
          * assignable method numbers. Log this and return M_INVALID. 
          */ 
         ap_log_perror(APLOG_MARK, APLOG_ERR, 0, p, 
                       "Maximum new request methods %d reached while " 
                       "registering method %s.", 
                       METHOD_NUMBER_LAST, methname); 
         return M_INVALID; 
     } 
  
     register_one_method(p, methname, cur_method_number); 
     return cur_method_number++; 
 } 
  
 #define UNKNOWN_METHOD (-1) 
  
 static int lookup_builtin_method(const char *method, apr_size_t len) 
 { 
     /* Note: the following code was generated by the "shilka" tool from 
        the "cocom" parsing/compilation toolkit. It is an optimized lookup 
        based on analysis of the input keywords. Postprocessing was done 
        on the shilka output, but the basic structure and analysis is 
        from there. Should new HTTP methods be added, then manual insertion 
        into this code is fine, or simply re-running the shilka tool on 
        the appropriate input. */ 
  
     /* Note: it is also quite reasonable to just use our method_registry, 
        but I'm assuming (probably incorrectly) we want more speed here 
        (based on the optimizations the previous code was doing). */ 
  
     switch (len) 
     { 
     case 3: 
         switch (method[0]) 
         { 
         case 'P': 
             return (method[1] == 'U' 
                     && method[2] == 'T' 
                     ? M_PUT : UNKNOWN_METHOD); 
         case 'G': 
             return (method[1] == 'E' 
                     && method[2] == 'T' 
                     ? M_GET : UNKNOWN_METHOD); 
         default: 
             return UNKNOWN_METHOD; 
         } 
  
     case 4: 
         switch (method[0]) 
         { 
         case 'H': 
             return (method[1] == 'E' 
                     && method[2] == 'A' 
                     && method[3] == 'D' 
                     ? M_GET : UNKNOWN_METHOD); 
         case 'P': 
             return (method[1] == 'O' 
                     && method[2] == 'S' 
                     && method[3] == 'T' 
                     ? M_POST : UNKNOWN_METHOD); 
         case 'M': 
             return (method[1] == 'O' 
                     && method[2] == 'V' 
                     && method[3] == 'E' 
                     ? M_MOVE : UNKNOWN_METHOD); 
         case 'L': 
             return (method[1] == 'O' 
                     && method[2] == 'C' 
                     && method[3] == 'K' 
                     ? M_LOCK : UNKNOWN_METHOD); 
         case 'C': 
             return (method[1] == 'O' 
                     && method[2] == 'P' 
                     && method[3] == 'Y' 
                     ? M_COPY : UNKNOWN_METHOD); 
         default: 
             return UNKNOWN_METHOD; 
         } 
  
     case 5: 
         switch (method[2]) 
         { 
         case 'T': 
             return (memcmp(method, "PATCH", 5) == 0 
                     ? M_PATCH : UNKNOWN_METHOD); 
         case 'R': 
             return (memcmp(method, "MERGE", 5) == 0 
                     ? M_MERGE : UNKNOWN_METHOD); 
         case 'C': 
             return (memcmp(method, "MKCOL", 5) == 0 
                     ? M_MKCOL : UNKNOWN_METHOD); 
         case 'B': 
             return (memcmp(method, "LABEL", 5) == 0 
                     ? M_LABEL : UNKNOWN_METHOD); 
         case 'A': 
             return (memcmp(method, "TRACE", 5) == 0 
                     ? M_TRACE : UNKNOWN_METHOD); 
         default: 
             return UNKNOWN_METHOD; 
         } 
  
     case 6: 
         switch (method[0]) 
         { 
         case 'U': 
             switch (method[5]) 
             { 
             case 'K': 
                 return (memcmp(method, "UNLOCK", 6) == 0 
                         ? M_UNLOCK : UNKNOWN_METHOD); 
             case 'E': 
                 return (memcmp(method, "UPDATE", 6) == 0 
                         ? M_UPDATE : UNKNOWN_METHOD); 
             default: 
                 return UNKNOWN_METHOD; 
             } 
         case 'R': 
             return (memcmp(method, "REPORT", 6) == 0 
                     ? M_REPORT : UNKNOWN_METHOD); 
         case 'D': 
             return (memcmp(method, "DELETE", 6) == 0 
                     ? M_DELETE : UNKNOWN_METHOD); 
         default: 
             return UNKNOWN_METHOD; 
         } 
  
     case 7: 
         switch (method[1]) 
         { 
         case 'P': 
             return (memcmp(method, "OPTIONS", 7) == 0 
                     ? M_OPTIONS : UNKNOWN_METHOD); 
         case 'O': 
             return (memcmp(method, "CONNECT", 7) == 0 
                     ? M_CONNECT : UNKNOWN_METHOD); 
         case 'H': 
             return (memcmp(method, "CHECKIN", 7) == 0 
                     ? M_CHECKIN : UNKNOWN_METHOD); 
         default: 
             return UNKNOWN_METHOD; 
         } 
  
     case 8: 
         switch (method[0]) 
         { 
         case 'P': 
             return (memcmp(method, "PROPFIND", 8) == 0 
                     ? M_PROPFIND : UNKNOWN_METHOD); 
         case 'C': 
             return (memcmp(method, "CHECKOUT", 8) == 0 
                     ? M_CHECKOUT : UNKNOWN_METHOD); 
         default: 
             return UNKNOWN_METHOD; 
         } 
  
     case 9: 
         return (memcmp(method, "PROPPATCH", 9) == 0 
                 ? M_PROPPATCH : UNKNOWN_METHOD); 
  
     case 10: 
         switch (method[0]) 
         { 
         case 'U': 
             return (memcmp(method, "UNCHECKOUT", 10) == 0 
                     ? M_UNCHECKOUT : UNKNOWN_METHOD); 
         case 'M': 
             return (memcmp(method, "MKACTIVITY", 10) == 0 
                     ? M_MKACTIVITY : UNKNOWN_METHOD); 
         default: 
             return UNKNOWN_METHOD; 
         } 
  
     case 11: 
         return (memcmp(method, "MKWORKSPACE", 11) == 0 
                 ? M_MKWORKSPACE : UNKNOWN_METHOD); 
  
     case 15: 
         return (memcmp(method, "VERSION-CONTROL", 15) == 0 
                 ? M_VERSION_CONTROL : UNKNOWN_METHOD); 
  
     case 16: 
         return (memcmp(method, "BASELINE-CONTROL", 16) == 0 
                 ? M_BASELINE_CONTROL : UNKNOWN_METHOD); 
  
     default: 
         return UNKNOWN_METHOD; 
     } 
  
     /* NOTREACHED */ 
 } 
  
 /* Get the method number associated with the given string, assumed to 
  * contain an HTTP method.  Returns M_INVALID if not recognized. 
  * 
  * This is the first step toward placing method names in a configurable 
  * list.  Hopefully it (and other routines) can eventually be moved to 
  * something like a mod_http_methods.c, complete with config stuff. 
  */ 
 AP_DECLARE(int) ap_method_number_of(const char *method) 
 { 
     int len = strlen(method); 
     int which = lookup_builtin_method(method, len); 
  
     if (which != UNKNOWN_METHOD) 
         return which; 
  
     /* check if the method has been dynamically registered */ 
     if (methods_registry != NULL) { 
         int *methnum = apr_hash_get(methods_registry, method, len); 
  
         if (methnum != NULL) { 
             return *methnum; 
         } 
     } 
  
     return M_INVALID; 
 } 
  
 /* 
  * Turn a known method number into a name. 
  */ 
 AP_DECLARE(const char *) ap_method_name_of(apr_pool_t *p, int methnum) 
 { 
     apr_hash_index_t *hi = apr_hash_first(p, methods_registry); 
  
     /* scan through the hash table, looking for a value that matches 
        the provided method number. */ 
     for (; hi; hi = apr_hash_next(hi)) { 
         const void *key; 
         void *val; 
  
         apr_hash_this(hi, &key, NULL, &val); 
         if (*(int *)val == methnum) 
             return key; 
     } 
  
     /* it wasn't found in the hash */ 
     return NULL; 
 } 
  
 static long get_chunk_size(char *); 
  
 typedef struct http_filter_ctx { 
     apr_off_t remaining; 
     apr_off_t limit; 
     apr_off_t limit_used; 
     enum { 
         BODY_NONE, 
         BODY_LENGTH, 
         BODY_CHUNK 
     } state; 
     int eos_sent; 
 } http_ctx_t; 
  
 /* This is the HTTP_INPUT filter for HTTP requests and responses from  
  * proxied servers (mod_proxy).  It handles chunked and content-length  
  * bodies.  This can only be inserted/used after the headers 
  * are successfully parsed.  
  */ 
 apr_status_t ap_http_filter(ap_filter_t *f, apr_bucket_brigade *b, 
                             ap_input_mode_t mode, apr_read_type_e block, 
                             apr_off_t readbytes) 
 { 
     apr_bucket *e; 
     http_ctx_t *ctx = f->ctx; 
     apr_status_t rv; 
     apr_off_t totalread; 
  
     /* just get out of the way of things we don't want. */ 
     if (mode != AP_MODE_READBYTES && mode != AP_MODE_GETLINE) { 
         return ap_get_brigade(f->next, b, mode, block, readbytes); 
     } 
  
     if (!ctx) { 
         const char *tenc, *lenp; 
         f->ctx = ctx = apr_palloc(f->r->pool, sizeof(*ctx)); 
         ctx->state = BODY_NONE; 
         ctx->remaining = 0; 
         ctx->limit_used = 0; 
         ctx->eos_sent = 0; 
  
         /* LimitRequestBody does not apply to proxied responses. 
          * Consider implementing this check in its own filter.  
          * Would adding a directive to limit the size of proxied  
          * responses be useful? 
          */ 
         if (!f->r->proxyreq) { 
             ctx->limit = ap_get_limit_req_body(f->r); 
         } 
         else { 
             ctx->limit = 0; 
         } 
  
         tenc = apr_table_get(f->r->headers_in, "Transfer-Encoding"); 
         lenp = apr_table_get(f->r->headers_in, "Content-Length"); 
  
         if (tenc) { 
             if (!strcasecmp(tenc, "chunked")) { 
                 ctx->state = BODY_CHUNK; 
             } 
         } 
         else if (lenp) { 
             const char *pos = lenp; 
             int conversion_error = 0; 
  
             /* This ensures that the number can not be negative. */ 
             while (apr_isdigit(*pos) || apr_isspace(*pos)) { 
                 ++pos; 
             } 
  
             if (*pos == '\0') { 
                 char *endstr; 
  
                 errno = 0; 
                 ctx->state = BODY_LENGTH; 
                 ctx->remaining = strtol(lenp, &endstr, 10); 
  
                 if (errno || (endstr && *endstr)) { 
                     conversion_error = 1;  
                 } 
             } 
  
             if (*pos != '\0' || conversion_error) { 
                 apr_bucket_brigade *bb; 
  
                 ap_log_rerror(APLOG_MARK, APLOG_ERR, 0, f->r, 
                               "Invalid Content-Length"); 
  
                 bb = apr_brigade_create(f->r->pool, f->c->bucket_alloc); 
                 e = ap_bucket_error_create(HTTP_REQUEST_ENTITY_TOO_LARGE, NULL, 
                                            f->r->pool, f->c->bucket_alloc); 
                 APR_BRIGADE_INSERT_TAIL(bb, e); 
                 e = apr_bucket_eos_create(f->c->bucket_alloc); 
                 APR_BRIGADE_INSERT_TAIL(bb, e); 
                 ctx->eos_sent = 1; 
                 return ap_pass_brigade(f->r->output_filters, bb); 
             } 
  
             /* If we have a limit in effect and we know the C-L ahead of 
              * time, stop it here if it is invalid.  
              */  
             if (ctx->limit && ctx->limit < ctx->remaining) { 
                 apr_bucket_brigade *bb; 
                 ap_log_rerror(APLOG_MARK, APLOG_ERR, 0, f->r, 
                           "Requested content-length of %" APR_OFF_T_FMT  
                           " is larger than the configured limit" 
                           " of %" APR_OFF_T_FMT, ctx->remaining, ctx->limit); 
                 bb = apr_brigade_create(f->r->pool, f->c->bucket_alloc); 
                 e = ap_bucket_error_create(HTTP_REQUEST_ENTITY_TOO_LARGE, NULL, 
                                            f->r->pool, f->c->bucket_alloc); 
                 APR_BRIGADE_INSERT_TAIL(bb, e); 
                 e = apr_bucket_eos_create(f->c->bucket_alloc); 
                 APR_BRIGADE_INSERT_TAIL(bb, e); 
                 ctx->eos_sent = 1; 
                 return ap_pass_brigade(f->r->output_filters, bb); 
             } 
         } 
  
         /* If we don't have a request entity indicated by the headers, EOS. 
          * (BODY_NONE is a valid intermediate state due to trailers, 
          *  but it isn't a valid starting state.) 
          * 
          * RFC 2616 Section 4.4 note 5 states that connection-close 
          * is invalid for a request entity - request bodies must be 
          * denoted by C-L or T-E: chunked. 
          * 
          * Note that since the proxy uses this filter to handle the 
          * proxied *response*, proxy responses MUST be exempt. 
          */ 
         if (ctx->state == BODY_NONE && f->r->proxyreq != PROXYREQ_RESPONSE) { 
             e = apr_bucket_eos_create(f->c->bucket_alloc); 
             APR_BRIGADE_INSERT_TAIL(b, e); 
             ctx->eos_sent = 1; 
             return APR_SUCCESS; 
         } 
  
         /* Since we're about to read data, send 100-Continue if needed. 
          * Only valid on chunked and C-L bodies where the C-L is > 0. */ 
         if ((ctx->state == BODY_CHUNK ||  
             (ctx->state == BODY_LENGTH && ctx->remaining > 0)) && 
             f->r->expecting_100 && f->r->proto_num >= HTTP_VERSION(1,1)) { 
             char *tmp; 
             apr_bucket_brigade *bb; 
  
             tmp = apr_pstrcat(f->r->pool, AP_SERVER_PROTOCOL, " ", 
                               status_lines[0], CRLF CRLF, NULL); 
             bb = apr_brigade_create(f->r->pool, f->c->bucket_alloc); 
             e = apr_bucket_pool_create(tmp, strlen(tmp), f->r->pool, 
                                        f->c->bucket_alloc); 
             APR_BRIGADE_INSERT_HEAD(bb, e); 
             e = apr_bucket_flush_create(f->c->bucket_alloc); 
             APR_BRIGADE_INSERT_TAIL(bb, e); 
  
             ap_pass_brigade(f->c->output_filters, bb); 
         } 
  
         /* We can't read the chunk until after sending 100 if required. */ 
         if (ctx->state == BODY_CHUNK) { 
             char line[30]; 
             apr_bucket_brigade *bb; 
             apr_size_t len = 30; 
  
             bb = apr_brigade_create(f->r->pool, f->c->bucket_alloc); 
  
             rv = ap_get_brigade(f->next, bb, AP_MODE_GETLINE, 
                                 APR_BLOCK_READ, 0); 
  
             if (rv != APR_SUCCESS) { 
                 return rv; 
             } 
             apr_brigade_flatten(bb, line, &len); 
  
             ctx->remaining = get_chunk_size(line); 
             /* Detect chunksize error (such as overflow) */ 
             if (ctx->remaining < 0) { 
                 ctx->remaining = 0; /* Reset it in case we have to 
                                      * come back here later */ 
                 apr_brigade_cleanup(bb); 
                 e = ap_bucket_error_create(HTTP_REQUEST_ENTITY_TOO_LARGE, NULL, 
                                            f->r->pool, 
                                            f->c->bucket_alloc); 
                 APR_BRIGADE_INSERT_TAIL(bb, e); 
                 e = apr_bucket_eos_create(f->c->bucket_alloc); 
                 APR_BRIGADE_INSERT_TAIL(bb, e); 
                 ctx->eos_sent = 1; 
                 return ap_pass_brigade(f->r->output_filters, bb); 
             } 
  
             if (!ctx->remaining) { 
                 /* Handle trailers by calling ap_get_mime_headers again! */ 
                 ctx->state = BODY_NONE; 
                 ap_get_mime_headers(f->r); 
                 e = apr_bucket_eos_create(f->c->bucket_alloc); 
                 APR_BRIGADE_INSERT_TAIL(b, e); 
                 ctx->eos_sent = 1; 
                 return APR_SUCCESS; 
             } 
         }  
     } 
  
     if (ctx->eos_sent) { 
         e = apr_bucket_eos_create(f->c->bucket_alloc); 
         APR_BRIGADE_INSERT_TAIL(b, e); 
         return APR_SUCCESS; 
     } 
  
     if (!ctx->remaining) { 
         switch (ctx->state) { 
         case BODY_NONE: 
             break; 
         case BODY_LENGTH: 
             e = apr_bucket_eos_create(f->c->bucket_alloc); 
             APR_BRIGADE_INSERT_TAIL(b, e); 
             ctx->eos_sent = 1; 
             return APR_SUCCESS; 
         case BODY_CHUNK: 
             { 
                 char line[30]; 
                 apr_bucket_brigade *bb; 
                 apr_size_t len = 30; 
  
                 bb = apr_brigade_create(f->r->pool, f->c->bucket_alloc); 
  
                 /* We need to read the CRLF after the chunk.  */ 
                 rv = ap_get_brigade(f->next, bb, AP_MODE_GETLINE, 
                                     APR_BLOCK_READ, 0); 
                 if (rv != APR_SUCCESS) { 
                     return rv; 
                 } 
                 apr_brigade_cleanup(bb); 
  
                 /* Read the real chunk line. */ 
                 rv = ap_get_brigade(f->next, bb, AP_MODE_GETLINE, 
                                     APR_BLOCK_READ, 0); 
  
                 if (rv != APR_SUCCESS) { 
                     return rv; 
                 } 
                 apr_brigade_flatten(bb, line, &len); 
                 ctx->remaining = get_chunk_size(line); 
  
                 /* Detect chunksize error (such as overflow) */ 
                 if (ctx->remaining < 0) { 
                     ctx->remaining = 0; /* Reset it in case we have to 
                                          * come back here later */ 
                     apr_brigade_cleanup(bb); 
                     e = ap_bucket_error_create(HTTP_REQUEST_ENTITY_TOO_LARGE, 
                                                NULL, f->r->pool, 
                                                f->c->bucket_alloc); 
                     APR_BRIGADE_INSERT_TAIL(bb, e); 
                     e = apr_bucket_eos_create(f->c->bucket_alloc); 
                     APR_BRIGADE_INSERT_TAIL(bb, e); 
                     ctx->eos_sent = 1; 
                     return ap_pass_brigade(f->r->output_filters, bb); 
                 } 
  
                 if (!ctx->remaining) { 
                     /* Handle trailers by calling ap_get_mime_headers again! */ 
                     ctx->state = BODY_NONE; 
                     ap_get_mime_headers(f->r); 
                     e = apr_bucket_eos_create(f->c->bucket_alloc); 
                     APR_BRIGADE_INSERT_TAIL(b, e); 
                     ctx->eos_sent = 1; 
                     return APR_SUCCESS; 
                 } 
             } 
             break; 
         } 
     } 
  
     /* Ensure that the caller can not go over our boundary point. */ 
     if (ctx->state == BODY_LENGTH || ctx->state == BODY_CHUNK) { 
         if (ctx->remaining < readbytes) { 
             readbytes = ctx->remaining; 
         } 
         AP_DEBUG_ASSERT(readbytes > 0); 
     } 
  
     rv = ap_get_brigade(f->next, b, mode, block, readbytes); 
  
     if (rv != APR_SUCCESS) { 
         return rv; 
     } 
  
     /* How many bytes did we just read? */ 
     apr_brigade_length(b, 0, &totalread); 
  
     /* If this happens, we have a bucket of unknown length.  Die because 
      * it means our assumptions have changed. */ 
     AP_DEBUG_ASSERT(totalread >= 0); 
  
     if (ctx->state != BODY_NONE) { 
         ctx->remaining -= totalread; 
     } 
  
     /* We have a limit in effect. */ 
     if (ctx->limit) { 
         /* FIXME: Note that we might get slightly confused on chunked inputs 
          * as we'd need to compensate for the chunk lengths which may not 
          * really count.  This seems to be up for interpretation.  */ 
         ctx->limit_used += totalread; 
         if (ctx->limit < ctx->limit_used) { 
             apr_bucket_brigade *bb; 
             ap_log_rerror(APLOG_MARK, APLOG_ERR, 0, f->r, 
                           "Read content-length of %" APR_OFF_T_FMT  
                           " is larger than the configured limit" 
                           " of %" APR_OFF_T_FMT, ctx->limit_used, ctx->limit); 
             bb = apr_brigade_create(f->r->pool, f->c->bucket_alloc); 
             e = ap_bucket_error_create(HTTP_REQUEST_ENTITY_TOO_LARGE, NULL, 
                                        f->r->pool, 
                                        f->c->bucket_alloc); 
             APR_BRIGADE_INSERT_TAIL(bb, e); 
             e = apr_bucket_eos_create(f->c->bucket_alloc); 
             APR_BRIGADE_INSERT_TAIL(bb, e); 
             ctx->eos_sent = 1; 
             return ap_pass_brigade(f->r->output_filters, bb); 
         } 
     } 
  
     return APR_SUCCESS; 
 } 
  
 /* The index is found by its offset from the x00 code of each level. 
  * Although this is fast, it will need to be replaced if some nutcase 
  * decides to define a high-numbered code before the lower numbers. 
  * If that sad event occurs, replace the code below with a linear search 
  * from status_lines[shortcut[i]] to status_lines[shortcut[i+1]-1]; 
  */ 
 AP_DECLARE(int) ap_index_of_response(int status) 
 { 
     static int shortcut[6] = {0, LEVEL_200, LEVEL_300, LEVEL_400, 
     LEVEL_500, RESPONSE_CODES}; 
     int i, pos; 
  
     if (status < 100) {               /* Below 100 is illegal for HTTP status */ 
         return LEVEL_500; 
     } 
  
     for (i = 0; i < 5; i++) { 
         status -= 100; 
         if (status < 100) { 
             pos = (status + shortcut[i]); 
             if (pos < shortcut[i + 1]) { 
                 return pos; 
             } 
             else { 
                 return LEVEL_500;            /* status unknown (falls in gap) */ 
             } 
         } 
     } 
     return LEVEL_500;                         /* 600 or above is also illegal */ 
 } 
  
 AP_DECLARE(const char *) ap_get_status_line(int status) 
 { 
     return status_lines[ap_index_of_response(status)]; 
 } 
  
 typedef struct header_struct { 
     apr_pool_t *pool; 
     apr_bucket_brigade *bb; 
 } header_struct; 
  
 /* Send a single HTTP header field to the client.  Note that this function 
  * is used in calls to table_do(), so their interfaces are co-dependent. 
  * In other words, don't change this one without checking table_do in alloc.c. 
  * It returns true unless there was a write error of some kind. 
  */ 
 static int form_header_field(header_struct *h, 
                              const char *fieldname, const char *fieldval) 
 { 
 #if APR_CHARSET_EBCDIC 
     char *headfield; 
     apr_size_t len; 
     apr_size_t name_len; 
     apr_size_t val_len; 
     char *next; 
  
     name_len = strlen(fieldname); 
     val_len = strlen(fieldval); 
     len = name_len + val_len + 4; /* 4 for ": " plus CRLF */ 
     headfield = (char *)apr_palloc(h->pool, len + 1); 
     memcpy(headfield, fieldname, name_len); 
     next = headfield + name_len; 
     *next++ = ':'; 
     *next++ = ' '; 
     memcpy(next, fieldval, val_len); 
     next += val_len; 
     *next++ = CR; 
     *next++ = LF; 
     *next = 0; 
     ap_xlate_proto_to_ascii(headfield, len); 
     apr_brigade_write(h->bb, NULL, NULL, headfield, len); 
 #else 
     apr_brigade_puts(h->bb, NULL, NULL, fieldname); 
     apr_brigade_write(h->bb, NULL, NULL, ": ", sizeof(": ") - 1); 
     apr_brigade_puts(h->bb, NULL, NULL, fieldval); 
     apr_brigade_write(h->bb, NULL, NULL, CRLF, sizeof(CRLF) - 1); 
 #endif /* APR_CHARSET_EBCDIC */ 
     return 1; 
 } 
  
 /* 
  * Determine the protocol to use for the response. Potentially downgrade 
  * to HTTP/1.0 in some situations and/or turn off keepalives. 
  * 
  * also prepare r->status_line. 
  */ 
 static void basic_http_header_check(request_rec *r, 
                                     const char **protocol) 
 { 
     if (r->assbackwards) { 
         /* no such thing as a response protocol */ 
         return; 
     } 
  
     if (!r->status_line) { 
         r->status_line = status_lines[ap_index_of_response(r->status)]; 
     } 
  
     /* Note that we must downgrade before checking for force responses. */ 
     if (r->proto_num > HTTP_VERSION(1,0) 
         && apr_table_get(r->subprocess_env, "downgrade-1.0")) { 
         r->proto_num = HTTP_VERSION(1,0); 
     } 
  
     /* kludge around broken browsers when indicated by force-response-1.0 
      */ 
     if (r->proto_num == HTTP_VERSION(1,0) 
         && apr_table_get(r->subprocess_env, "force-response-1.0")) { 
         *protocol = "HTTP/1.0"; 
         r->connection->keepalive = -1; 
     } 
     else { 
         *protocol = AP_SERVER_PROTOCOL; 
     } 
  
 } 
  
 /* fill "bb" with a barebones/initial HTTP response header */ 
 static void basic_http_header(request_rec *r, apr_bucket_brigade *bb, 
                               const char *protocol) 
 { 
     char *date; 
     char *tmp; 
     const char *server; 
     header_struct h; 
     apr_size_t len; 
     struct iovec vec[4]; 
  
     if (r->assbackwards) { 
         /* there are no headers to send */ 
         return; 
     } 
  
     /* Output the HTTP/1.x Status-Line and the Date and Server fields */ 
  
     vec[0].iov_base = (void *)protocol; 
     vec[0].iov_len  = strlen(protocol); 
     vec[1].iov_base = (void *)" "; 
     vec[1].iov_len  = sizeof(" ") - 1; 
     vec[2].iov_base = (void *)(r->status_line); 
     vec[2].iov_len  = strlen(r->status_line); 
     vec[3].iov_base = (void *)CRLF; 
     vec[3].iov_len  = sizeof(CRLF) - 1; 
     tmp = apr_pstrcatv(r->pool, vec, 4, &len); 
     ap_xlate_proto_to_ascii(tmp, len); 
     apr_brigade_write(bb, NULL, NULL, tmp, len); 
  
     date = apr_palloc(r->pool, APR_RFC822_DATE_LEN); 
     ap_recent_rfc822_date(date, r->request_time); 
  
     h.pool = r->pool; 
     h.bb = bb; 
     form_header_field(&h, "Date", date); 
  
     /* keep a previously set server header (possibly from proxy), otherwise 
      * generate a new server header */ 
     if ((server = apr_table_get(r->headers_out, "Server")) != NULL) { 
         form_header_field(&h, "Server", server); 
     } 
     else { 
         form_header_field(&h, "Server", ap_get_server_version()); 
     } 
  
     /* unset so we don't send them again */ 
     apr_table_unset(r->headers_out, "Date");        /* Avoid bogosity */ 
     apr_table_unset(r->headers_out, "Server"); 
 } 
  
 AP_DECLARE(void) ap_basic_http_header(request_rec *r, apr_bucket_brigade *bb) 
 { 
     const char *protocol; 
  
     basic_http_header_check(r, &protocol); 
     basic_http_header(r, bb, protocol); 
 } 
  
 /* Navigator versions 2.x, 3.x and 4.0 betas up to and including 4.0b2 
  * have a header parsing bug.  If the terminating \r\n occur starting 
  * at offset 256, 257 or 258 of output then it will not properly parse 
  * the headers.  Curiously it doesn't exhibit this problem at 512, 513. 
  * We are guessing that this is because their initial read of a new request 
  * uses a 256 byte buffer, and subsequent reads use a larger buffer. 
  * So the problem might exist at different offsets as well. 
  * 
  * This should also work on keepalive connections assuming they use the 
  * same small buffer for the first read of each new request. 
  * 
  * At any rate, we check the bytes written so far and, if we are about to 
  * tickle the bug, we instead insert a bogus padding header.  Since the bug 
  * manifests as a broken image in Navigator, users blame the server.  :( 
  * It is more expensive to check the User-Agent than it is to just add the 
  * bytes, so we haven't used the BrowserMatch feature here. 
  */ 
 static void terminate_header(apr_bucket_brigade *bb) 
 { 
     char tmp[] = "X-Pad: avoid browser bug" CRLF; 
     char crlf[] = CRLF; 
     apr_off_t len; 
     apr_size_t buflen; 
  
     (void) apr_brigade_length(bb, 1, &len); 
  
     if (len >= 255 && len <= 257) { 
         buflen = strlen(tmp); 
         ap_xlate_proto_to_ascii(tmp, buflen); 
         apr_brigade_write(bb, NULL, NULL, tmp, buflen); 
     } 
     buflen = strlen(crlf); 
     ap_xlate_proto_to_ascii(crlf, buflen); 
     apr_brigade_write(bb, NULL, NULL, crlf, buflen); 
 } 
  
 /* Build the Allow field-value from the request handler method mask. 
  * Note that we always allow TRACE, since it is handled below. 
  */ 
 static char *make_allow(request_rec *r) 
 { 
     char *list; 
     apr_int64_t mask; 
     apr_array_header_t *allow = apr_array_make(r->pool, 10, sizeof(char *)); 
     apr_hash_index_t *hi = apr_hash_first(r->pool, methods_registry); 
  
     mask = r->allowed_methods->method_mask; 
  
     for (; hi; hi = apr_hash_next(hi)) { 
         const void *key; 
         void *val; 
  
         apr_hash_this(hi, &key, NULL, &val); 
         if ((mask & (AP_METHOD_BIT << *(int *)val)) != 0) { 
             *(const char **)apr_array_push(allow) = key; 
  
             /* the M_GET method actually refers to two methods */ 
             if (*(int *)val == M_GET) 
                 *(const char **)apr_array_push(allow) = "HEAD"; 
         } 
     } 
  
     /* TRACE is always allowed */ 
     *(const char **)apr_array_push(allow) = "TRACE"; 
  
     list = apr_array_pstrcat(r->pool, allow, ','); 
  
     /* ### this is rather annoying. we should enforce registration of 
        ### these methods */ 
     if ((mask & (AP_METHOD_BIT << M_INVALID)) 
         && (r->allowed_methods->method_list != NULL) 
         && (r->allowed_methods->method_list->nelts != 0)) { 
         int i; 
         char **xmethod = (char **) r->allowed_methods->method_list->elts; 
  
         /* 
          * Append all of the elements of r->allowed_methods->method_list 
          */ 
         for (i = 0; i < r->allowed_methods->method_list->nelts; ++i) { 
             list = apr_pstrcat(r->pool, list, ",", xmethod[i], NULL); 
         } 
     } 
  
     return list; 
 } 
  
 AP_DECLARE_NONSTD(int) ap_send_http_trace(request_rec *r) 
 { 
     int rv; 
     apr_bucket_brigade *b; 
     header_struct h; 
  
     if (r->method_number != M_TRACE) { 
         return DECLINED; 
     } 
  
     /* Get the original request */ 
     while (r->prev) { 
         r = r->prev; 
     } 
  
     if ((rv = ap_setup_client_block(r, REQUEST_NO_BODY))) { 
         return rv; 
     } 
  
     ap_set_content_type(r, "message/http"); 
  
     /* Now we recreate the request, and echo it back */ 
  
     b = apr_brigade_create(r->pool, r->connection->bucket_alloc); 
     apr_brigade_putstrs(b, NULL, NULL, r->the_request, CRLF, NULL); 
     h.pool = r->pool; 
     h.bb = b; 
     apr_table_do((int (*) (void *, const char *, const char *)) 
                  form_header_field, (void *) &h, r->headers_in, NULL); 
     apr_brigade_puts(b, NULL, NULL, CRLF); 
     ap_pass_brigade(r->output_filters, b); 
  
     return DONE; 
 } 
  
 AP_DECLARE(int) ap_send_http_options(request_rec *r) 
 { 
     if (r->assbackwards) { 
         return DECLINED; 
     } 
  
     apr_table_setn(r->headers_out, "Allow", make_allow(r)); 
  
     /* the request finalization will send an EOS, which will flush all 
      * the headers out (including the Allow header) 
      */ 
  
     return OK; 
 } 
  
 /* This routine is called by apr_table_do and merges all instances of 
  * the passed field values into a single array that will be further 
  * processed by some later routine.  Originally intended to help split 
  * and recombine multiple Vary fields, though it is generic to any field 
  * consisting of comma/space-separated tokens. 
  */ 
 static int uniq_field_values(void *d, const char *key, const char *val) 
 { 
     apr_array_header_t *values; 
     char *start; 
     char *e; 
     char **strpp; 
     int  i; 
  
     values = (apr_array_header_t *)d; 
  
     e = apr_pstrdup(values->pool, val); 
  
     do { 
         /* Find a non-empty fieldname */ 
  
         while (*e == ',' || apr_isspace(*e)) { 
             ++e; 
         } 
         if (*e == '\0') { 
             break; 
         } 
         start = e; 
         while (*e != '\0' && *e != ',' && !apr_isspace(*e)) { 
             ++e; 
         } 
         if (*e != '\0') { 
             *e++ = '\0'; 
         } 
  
         /* Now add it to values if it isn't already represented. 
          * Could be replaced by a ap_array_strcasecmp() if we had one. 
          */ 
         for (i = 0, strpp = (char **) values->elts; i < values->nelts; 
              ++i, ++strpp) { 
             if (*strpp && strcasecmp(*strpp, start) == 0) { 
                 break; 
             } 
         } 
         if (i == values->nelts) {  /* if not found */ 
             *(char **)apr_array_push(values) = start; 
         } 
     } while (*e != '\0'); 
  
     return 1; 
 } 
  
 /* 
  * Since some clients choke violently on multiple Vary fields, or 
  * Vary fields with duplicate tokens, combine any multiples and remove 
  * any duplicates. 
  */ 
 static void fixup_vary(request_rec *r) 
 { 
     apr_array_header_t *varies; 
  
     varies = apr_array_make(r->pool, 5, sizeof(char *)); 
  
     /* Extract all Vary fields from the headers_out, separate each into 
      * its comma-separated fieldname values, and then add them to varies 
      * if not already present in the array. 
      */ 
     apr_table_do((int (*)(void *, const char *, const char *))uniq_field_values, 
                  (void *) varies, r->headers_out, "Vary", NULL); 
  
     /* If we found any, replace old Vary fields with unique-ified value */ 
  
     if (varies->nelts > 0) { 
         apr_table_setn(r->headers_out, "Vary", 
                        apr_array_pstrcat(r->pool, varies, ',')); 
     } 
 } 
  
 AP_DECLARE(void) ap_set_content_type(request_rec *r, const char *ct) 
 { 
     if (!ct) { 
         r->content_type = NULL; 
     } 
     else if (!r->content_type || strcmp(r->content_type, ct)) { 
         r->content_type = ct; 
  
         /* Insert filters requested by the AddOutputFiltersByType  
          * configuration directive. Content-type filters must be  
          * inserted after the content handlers have run because  
          * only then, do we reliably know the content-type. 
          */ 
         ap_add_output_filters_by_type(r); 
     } 
 } 
  
 typedef struct header_filter_ctx { 
     int headers_sent; 
 } header_filter_ctx; 
  
 AP_CORE_DECLARE_NONSTD(apr_status_t) ap_http_header_filter(ap_filter_t *f, 
                                                            apr_bucket_brigade *b) 
 { 
     request_rec *r = f->r; 
     conn_rec *c = r->connection; 
     const char *clheader; 
     const char *protocol; 
     apr_bucket *e; 
     apr_bucket_brigade *b2; 
     header_struct h; 
     header_filter_ctx *ctx = f->ctx; 
  
     AP_DEBUG_ASSERT(!r->main); 
  
     if (r->header_only) { 
         if (!ctx) { 
             ctx = f->ctx = apr_pcalloc(r->pool, sizeof(header_filter_ctx)); 
         } 
         else if (ctx->headers_sent) { 
             apr_brigade_destroy(b); 
             return OK; 
         } 
     } 
  
     APR_BRIGADE_FOREACH(e, b) { 
         if (e->type == &ap_bucket_type_error) { 
             ap_bucket_error *eb = e->data; 
  
             ap_die(eb->status, r); 
             return AP_FILTER_ERROR; 
         } 
     } 
  
     if (r->assbackwards) { 
         r->sent_bodyct = 1; 
         ap_remove_output_filter(f); 
         return ap_pass_brigade(f->next, b); 
     } 
  
     /* 
      * Now that we are ready to send a response, we need to combine the two 
      * header field tables into a single table.  If we don't do this, our 
      * later attempts to set or unset a given fieldname might be bypassed. 
      */ 
     if (!apr_is_empty_table(r->err_headers_out)) { 
         r->headers_out = apr_table_overlay(r->pool, r->err_headers_out, 
                                            r->headers_out); 
     } 
  
     /* 
      * Remove the 'Vary' header field if the client can't handle it. 
      * Since this will have nasty effects on HTTP/1.1 caches, force 
      * the response into HTTP/1.0 mode. 
      * 
      * Note: the force-response-1.0 should come before the call to 
      *       basic_http_header_check() 
      */ 
     if (apr_table_get(r->subprocess_env, "force-no-vary") != NULL) { 
         apr_table_unset(r->headers_out, "Vary"); 
         r->proto_num = HTTP_VERSION(1,0); 
         apr_table_set(r->subprocess_env, "force-response-1.0", "1"); 
     } 
     else { 
         fixup_vary(r); 
     } 
  
     /* 
      * Now remove any ETag response header field if earlier processing 
      * says so (such as a 'FileETag None' directive). 
      */ 
     if (apr_table_get(r->notes, "no-etag") != NULL) { 
         apr_table_unset(r->headers_out, "ETag"); 
     } 
  
     /* determine the protocol and whether we should use keepalives. */ 
     basic_http_header_check(r, &protocol); 
     ap_set_keepalive(r); 
  
     if (r->chunked) { 
         apr_table_mergen(r->headers_out, "Transfer-Encoding", "chunked"); 
         apr_table_unset(r->headers_out, "Content-Length"); 
     } 
  
     apr_table_setn(r->headers_out, "Content-Type",  
                    ap_make_content_type(r, r->content_type)); 
  
     if (r->content_encoding) { 
         apr_table_setn(r->headers_out, "Content-Encoding", 
                        r->content_encoding); 
     } 
  
     if (!apr_is_empty_table(r->content_languages)) { 
         int i; 
         char **languages = (char **)(r->content_languages->elts); 
         for (i = 0; i < r->content_languages->nelts; ++i) { 
             apr_table_mergen(r->headers_out, "Content-Language", languages[i]); 
         } 
     } 
  
     /* 
      * Control cachability for non-cachable responses if not already set by 
      * some other part of the server configuration. 
      */ 
     if (r->no_cache && !apr_table_get(r->headers_out, "Expires")) { 
         char *date = apr_palloc(r->pool, APR_RFC822_DATE_LEN); 
         ap_recent_rfc822_date(date, r->request_time); 
         apr_table_addn(r->headers_out, "Expires", date); 
     } 
  
     /* This is a hack, but I can't find anyway around it.  The idea is that 
      * we don't want to send out 0 Content-Lengths if it is a head request. 
      * This happens when modules try to outsmart the server, and return 
      * if they see a HEAD request.  Apache 1.3 handlers were supposed to 
      * just return in that situation, and the core handled the HEAD.  In 
      * 2.0, if a handler returns, then the core sends an EOS bucket down 
      * the filter stack, and the content-length filter computes a C-L of 
      * zero and that gets put in the headers, and we end up sending a 
      * zero C-L to the client.  We can't just remove the C-L filter, 
      * because well behaved 2.0 handlers will send their data down the stack, 
      * and we will compute a real C-L for the head request. RBB 
      */ 
     if (r->header_only 
         && (clheader = apr_table_get(r->headers_out, "Content-Length")) 
         && !strcmp(clheader, "0")) { 
         apr_table_unset(r->headers_out, "Content-Length"); 
     } 
  
     b2 = apr_brigade_create(r->pool, c->bucket_alloc); 
     basic_http_header(r, b2, protocol); 
  
     h.pool = r->pool; 
     h.bb = b2; 
  
     if (r->status == HTTP_NOT_MODIFIED) { 
         apr_table_do((int (*)(void *, const char *, const char *)) form_header_field, 
                      (void *) &h, r->headers_out, 
                      "Connection", 
                      "Keep-Alive", 
                      "ETag", 
                      "Content-Location", 
                      "Expires", 
                      "Cache-Control", 
                      "Vary", 
                      "Warning", 
                      "WWW-Authenticate", 
                      "Proxy-Authenticate", 
                      NULL); 
     } 
     else { 
         apr_table_do((int (*) (void *, const char *, const char *)) form_header_field, 
                      (void *) &h, r->headers_out, NULL); 
     } 
  
     terminate_header(b2); 
  
     ap_pass_brigade(f->next, b2); 
  
     if (r->header_only) { 
         apr_brigade_destroy(b); 
         ctx->headers_sent = 1; 
         return OK; 
     } 
  
     r->sent_bodyct = 1;         /* Whatever follows is real body stuff... */ 
  
     if (r->chunked) { 
         /* We can't add this filter until we have already sent the headers. 
          * If we add it before this point, then the headers will be chunked 
          * as well, and that is just wrong. 
          */ 
         ap_add_output_filter("CHUNK", NULL, r, r->connection); 
     } 
  
     /* Don't remove this filter until after we have added the CHUNK filter. 
      * Otherwise, f->next won't be the CHUNK filter and thus the first 
      * brigade won't be chunked properly. 
      */ 
     ap_remove_output_filter(f); 
     return ap_pass_brigade(f->next, b); 
 } 
  
 /* Here we deal with getting the request message body from the client. 
  * Whether or not the request contains a body is signaled by the presence 
  * of a non-zero Content-Length or by a Transfer-Encoding: chunked. 
  * 
  * Note that this is more complicated than it was in Apache 1.1 and prior 
  * versions, because chunked support means that the module does less. 
  * 
  * The proper procedure is this: 
  * 
  * 1. Call setup_client_block() near the beginning of the request 
  *    handler. This will set up all the necessary properties, and will 
  *    return either OK, or an error code. If the latter, the module should 
  *    return that error code. The second parameter selects the policy to 
  *    apply if the request message indicates a body, and how a chunked 
  *    transfer-coding should be interpreted. Choose one of 
  * 
  *    REQUEST_NO_BODY          Send 413 error if message has any body 
  *    REQUEST_CHUNKED_ERROR    Send 411 error if body without Content-Length 
  *    REQUEST_CHUNKED_DECHUNK  If chunked, remove the chunks for me. 
  * 
  *    In order to use the last two options, the caller MUST provide a buffer 
  *    large enough to hold a chunk-size line, including any extensions. 
  * 
  * 2. When you are ready to read a body (if any), call should_client_block(). 
  *    This will tell the module whether or not to read input. If it is 0, 
  *    the module should assume that there is no message body to read. 
  *    This step also sends a 100 Continue response to HTTP/1.1 clients, 
  *    so should not be called until the module is *definitely* ready to 
  *    read content. (otherwise, the point of the 100 response is defeated). 
  *    Never call this function more than once. 
  * 
  * 3. Finally, call get_client_block in a loop. Pass it a buffer and its size. 
  *    It will put data into the buffer (not necessarily a full buffer), and 
  *    return the length of the input block. When it is done reading, it will 
  *    return 0 if EOF, or -1 if there was an error. 
  *    If an error occurs on input, we force an end to keepalive. 
  */ 
  
 AP_DECLARE(int) ap_setup_client_block(request_rec *r, int read_policy) 
 { 
     const char *tenc = apr_table_get(r->headers_in, "Transfer-Encoding"); 
     const char *lenp = apr_table_get(r->headers_in, "Content-Length"); 
  
     r->read_body = read_policy; 
     r->read_chunked = 0; 
     r->remaining = 0; 
  
     if (tenc) { 
         if (strcasecmp(tenc, "chunked")) { 
             ap_log_rerror(APLOG_MARK, APLOG_ERR, 0, r, 
                           "Unknown Transfer-Encoding %s", tenc); 
             return HTTP_NOT_IMPLEMENTED; 
         } 
         if (r->read_body == REQUEST_CHUNKED_ERROR) { 
             ap_log_rerror(APLOG_MARK, APLOG_ERR, 0, r, 
                           "chunked Transfer-Encoding forbidden: %s", r->uri); 
             return (lenp) ? HTTP_BAD_REQUEST : HTTP_LENGTH_REQUIRED; 
         } 
  
         r->read_chunked = 1; 
     } 
     else if (lenp) { 
         const char *pos = lenp; 
         int conversion_error = 0; 
  
         while (apr_isdigit(*pos) || apr_isspace(*pos)) { 
             ++pos; 
         } 
  
         if (*pos == '\0') { 
             char *endstr; 
  
             errno = 0; 
             r->remaining = strtol(lenp, &endstr, 10); 
  
             if (errno || (endstr && *endstr)) { 
                 conversion_error = 1;  
             } 
         } 
  
         if (*pos != '\0' || conversion_error) { 
             ap_log_rerror(APLOG_MARK, APLOG_ERR, 0, r, 
                           "Invalid Content-Length"); 
             return HTTP_BAD_REQUEST; 
         } 
     } 
  
     if ((r->read_body == REQUEST_NO_BODY) 
         && (r->read_chunked || (r->remaining > 0))) { 
         ap_log_rerror(APLOG_MARK, APLOG_ERR, 0, r, 
                       "%s with body is not allowed for %s", r->method, r->uri); 
         return HTTP_REQUEST_ENTITY_TOO_LARGE; 
     } 
  
 #ifdef AP_DEBUG 
     { 
         /* Make sure ap_getline() didn't leave any droppings. */ 
         core_request_config *req_cfg = 
             (core_request_config *)ap_get_module_config(r->request_config, 
                                                         &core_module); 
         AP_DEBUG_ASSERT(APR_BRIGADE_EMPTY(req_cfg->bb)); 
     } 
 #endif 
  
     return OK; 
 } 
  
 AP_DECLARE(int) ap_should_client_block(request_rec *r) 
 { 
     /* First check if we have already read the request body */ 
  
     if (r->read_length || (!r->read_chunked && (r->remaining <= 0))) { 
         return 0; 
     } 
  
     return 1; 
 } 
  
 static long get_chunk_size(char *b) 
 { 
     long chunksize = 0; 
     size_t chunkbits = sizeof(long) * 8; 
  
     /* Skip leading zeros */ 
     while (*b == '0') { 
         ++b; 
     } 
  
     while (apr_isxdigit(*b) && (chunkbits > 0)) { 
         int xvalue = 0; 
  
         if (*b >= '0' && *b <= '9') { 
             xvalue = *b - '0'; 
         } 
         else if (*b >= 'A' && *b <= 'F') { 
             xvalue = *b - 'A' + 0xa; 
         } 
         else if (*b >= 'a' && *b <= 'f') { 
             xvalue = *b - 'a' + 0xa; 
         } 
  
         chunksize = (chunksize << 4) | xvalue; 
         chunkbits -= 4; 
         ++b; 
     } 
     if (apr_isxdigit(*b) && (chunkbits <= 0)) { 
         /* overflow */ 
         return -1; 
     } 
  
     return chunksize; 
 } 
  
 /* get_client_block is called in a loop to get the request message body. 
  * This is quite simple if the client includes a content-length 
  * (the normal case), but gets messy if the body is chunked. Note that 
  * r->remaining is used to maintain state across calls and that 
  * r->read_length is the total number of bytes given to the caller 
  * across all invocations.  It is messy because we have to be careful not 
  * to read past the data provided by the client, since these reads block. 
  * Returns 0 on End-of-body, -1 on error or premature chunk end. 
  * 
  * Reading the chunked encoding requires a buffer size large enough to 
  * hold a chunk-size line, including any extensions. For now, we'll leave 
  * that to the caller, at least until we can come up with a better solution. 
  */ 
 AP_DECLARE(long) ap_get_client_block(request_rec *r, char *buffer, 
                                      apr_size_t bufsiz) 
 { 
     apr_size_t total; 
     apr_status_t rv; 
     apr_bucket *b; 
     const char *tempbuf; 
     core_request_config *req_cfg = 
         (core_request_config *)ap_get_module_config(r->request_config, 
                                                     &core_module); 
     apr_bucket_brigade *bb = req_cfg->bb; 
  
     /* read until we get a non-empty brigade */ 
     while (APR_BRIGADE_EMPTY(bb)) { 
         if (ap_get_brigade(r->input_filters, bb, AP_MODE_READBYTES, 
                            APR_BLOCK_READ, bufsiz) != APR_SUCCESS) { 
             /* if we actually fail here, we want to just return and 
              * stop trying to read data from the client. 
              */ 
             r->connection->keepalive = -1; 
             apr_brigade_destroy(bb); 
             return -1; 
         } 
     } 
  
     b = APR_BRIGADE_FIRST(bb); 
     if (APR_BUCKET_IS_EOS(b)) { /* reached eos on previous invocation */ 
         apr_bucket_delete(b); 
         return 0; 
     } 
  
     /* ### it would be nice to replace the code below with "consume N bytes 
        ### from this brigade, placing them into that buffer." there are 
        ### other places where we do the same... 
        ### 
        ### alternatively, we could partition the brigade, then call a 
        ### function which serializes a given brigade into a buffer. that 
        ### semantic is used elsewhere, too... 
     */ 
  
     total = 0; 
     while (total < bufsiz 
            && b != APR_BRIGADE_SENTINEL(bb) 
            && !APR_BUCKET_IS_EOS(b)) { 
         apr_size_t len_read; 
         apr_bucket *old; 
  
         if ((rv = apr_bucket_read(b, &tempbuf, &len_read, 
                                   APR_BLOCK_READ)) != APR_SUCCESS) { 
             return -1; 
         } 
         if (total + len_read > bufsiz) { 
             apr_bucket_split(b, bufsiz - total); 
             len_read = bufsiz - total; 
         } 
         memcpy(buffer, tempbuf, len_read); 
         buffer += len_read; 
         total += len_read; 
         /* XXX the next field shouldn't be mucked with here, 
          * as it is in terms of bytes in the unfiltered body; 
          * gotta see if anybody else actually uses it 
          */ 
         r->read_length += len_read; /* XXX yank me? */ 
         old = b; 
         b = APR_BUCKET_NEXT(b); 
         apr_bucket_delete(old); 
     } 
  
     return total; 
 } 
  
 /* In HTTP/1.1, any method can have a body.  However, most GET handlers 
  * wouldn't know what to do with a request body if they received one. 
  * This helper routine tests for and reads any message body in the request, 
  * simply discarding whatever it receives.  We need to do this because 
  * failing to read the request body would cause it to be interpreted 
  * as the next request on a persistent connection. 
  * 
  * Since we return an error status if the request is malformed, this 
  * routine should be called at the beginning of a no-body handler, e.g., 
  * 
  *    if ((retval = ap_discard_request_body(r)) != OK) { 
  *        return retval; 
  *    } 
  */ 
 AP_DECLARE(int) ap_discard_request_body(request_rec *r) 
 { 
     apr_bucket_brigade *bb; 
     int rv, seen_eos; 
  
     /* Sometimes we'll get in a state where the input handling has 
      * detected an error where we want to drop the connection, so if 
      * that's the case, don't read the data as that is what we're trying 
      * to avoid. 
      * 
      * This function is also a no-op on a subrequest. 
      */ 
     if (r->main || ap_status_drops_connection(r->status)) { 
         return OK; 
     } 
  
     bb = apr_brigade_create(r->pool, r->connection->bucket_alloc); 
     seen_eos = 0; 
     do { 
         apr_bucket *bucket; 
  
         rv = ap_get_brigade(r->input_filters, bb, AP_MODE_READBYTES, 
                             APR_BLOCK_READ, HUGE_STRING_LEN); 
  
         if (rv != APR_SUCCESS) { 
             /* FIXME: If we ever have a mapping from filters (apr_status_t) 
              * to HTTP error codes, this would be a good place for them. 
              *  
              * If we received the special case AP_FILTER_ERROR, it means 
              * that the filters have already handled this error. 
              * Otherwise, we should assume we have a bad request. 
              */ 
             if (rv == AP_FILTER_ERROR) { 
                 return rv; 
             } 
             else { 
                 return HTTP_BAD_REQUEST; 
             } 
         } 
  
         APR_BRIGADE_FOREACH(bucket, bb) { 
             const char *data; 
             apr_size_t len; 
  
             if (APR_BUCKET_IS_EOS(bucket)) { 
                 seen_eos = 1; 
                 break; 
             } 
  
             /* These are metadata buckets. */ 
             if (bucket->length == 0) { 
                 continue; 
             } 
  
             /* We MUST read because in case we have an unknown-length 
              * bucket or one that morphs, we want to exhaust it. 
              */ 
             rv = apr_bucket_read(bucket, &data, &len, APR_BLOCK_READ); 
             if (rv != APR_SUCCESS) { 
                 return HTTP_BAD_REQUEST; 
             } 
         } 
         apr_brigade_cleanup(bb); 
     } while (!seen_eos); 
  
     return OK; 
 } 
  
 static const char *add_optional_notes(request_rec *r, 
                                       const char *prefix, 
                                       const char *key, 
                                       const char *suffix) 
 { 
     const char *notes, *result; 
  
     if ((notes = apr_table_get(r->notes, key)) == NULL) { 
         result = apr_pstrcat(r->pool, prefix, suffix, NULL); 
     } 
     else { 
         result = apr_pstrcat(r->pool, prefix, notes, suffix, NULL); 
     } 
  
     return result; 
 } 
  
 /* construct and return the default error message for a given 
  * HTTP defined error code 
  */ 
 static const char *get_canned_error_string(int status, 
                                            request_rec *r, 
                                            const char *location) 
 { 
     apr_pool_t *p = r->pool; 
     const char *error_notes, *h1, *s1; 
  
     switch (status) { 
     case HTTP_MOVED_PERMANENTLY: 
     case HTTP_MOVED_TEMPORARILY: 
     case HTTP_TEMPORARY_REDIRECT: 
         return(apr_pstrcat(p, 
                            "<p>The document has moved <a href=\"", 
                            ap_escape_html(r->pool, location), 
                            "\">here</a>.</p>\n", 
                            NULL)); 
     case HTTP_SEE_OTHER: 
         return(apr_pstrcat(p, 
                            "<p>The answer to your request is located " 
                            "<a href=\"", 
                            ap_escape_html(r->pool, location), 
                            "\">here</a>.</p>\n", 
                            NULL)); 
     case HTTP_USE_PROXY: 
         return(apr_pstrcat(p, 
                            "<p>This resource is only accessible " 
                            "through the proxy\n", 
                            ap_escape_html(r->pool, location), 
                            "<br />\nYou will need to configure " 
                            "your client to use that proxy.</p>\n", 
                            NULL)); 
     case HTTP_PROXY_AUTHENTICATION_REQUIRED: 
     case HTTP_UNAUTHORIZED: 
         return("<p>This server could not verify that you\n" 
                "are authorized to access the document\n" 
                "requested.  Either you supplied the wrong\n" 
                "credentials (e.g., bad password), or your\n" 
                "browser doesn't understand how to supply\n" 
                "the credentials required.</p>\n"); 
     case HTTP_BAD_REQUEST: 
         return(add_optional_notes(r, 
                                   "<p>Your browser sent a request that " 
                                   "this server could not understand.<br />\n", 
                                   "error-notes", 
                                   "</p>\n")); 
     case HTTP_FORBIDDEN: 
         return(apr_pstrcat(p, 
                            "<p>You don't have permission to access ", 
                            ap_escape_html(r->pool, r->uri), 
                            "\non this server.</p>\n", 
                            NULL)); 
     case HTTP_NOT_FOUND: 
         return(apr_pstrcat(p, 
                            "<p>The requested URL ", 
                            ap_escape_html(r->pool, r->uri), 
                            " was not found on this server.</p>\n", 
                            NULL)); 
     case HTTP_METHOD_NOT_ALLOWED: 
         return(apr_pstrcat(p, 
                            "<p>The requested method ", r->method, 
                            " is not allowed for the URL ", 
                            ap_escape_html(r->pool, r->uri), 
                            ".</p>\n", 
                            NULL)); 
     case HTTP_NOT_ACCEPTABLE: 
         s1 = apr_pstrcat(p, 
                          "<p>An appropriate representation of the " 
                          "requested resource ", 
                          ap_escape_html(r->pool, r->uri), 
                          " could not be found on this server.</p>\n", 
                          NULL); 
         return(add_optional_notes(r, s1, "variant-list", "")); 
     case HTTP_MULTIPLE_CHOICES: 
         return(add_optional_notes(r, "", "variant-list", "")); 
     case HTTP_LENGTH_REQUIRED: 
         s1 = apr_pstrcat(p, 
                          "<p>A request of the requested method ", 
                          r->method, 
                          " requires a valid Content-length.<br />\n", 
                          NULL); 
         return(add_optional_notes(r, s1, "error-notes", "</p>\n")); 
     case HTTP_PRECONDITION_FAILED: 
         return(apr_pstrcat(p, 
                            "<p>The precondition on the request " 
                            "for the URL ", 
                            ap_escape_html(r->pool, r->uri), 
                            " evaluated to false.</p>\n", 
                            NULL)); 
     case HTTP_NOT_IMPLEMENTED: 
         s1 = apr_pstrcat(p, 
                          "<p>", 
                          ap_escape_html(r->pool, r->method), " to ", 
                          ap_escape_html(r->pool, r->uri), 
                          " not supported.<br />\n", 
                          NULL); 
         return(add_optional_notes(r, s1, "error-notes", "</p>\n")); 
     case HTTP_BAD_GATEWAY: 
         s1 = "<p>The proxy server received an invalid" CRLF 
             "response from an upstream server.<br />" CRLF; 
         return(add_optional_notes(r, s1, "error-notes", "</p>\n")); 
     case HTTP_VARIANT_ALSO_VARIES: 
         return(apr_pstrcat(p, 
                            "<p>A variant for the requested " 
                            "resource\n<pre>\n", 
                            ap_escape_html(r->pool, r->uri), 
                            "\n</pre>\nis itself a negotiable resource. " 
                            "This indicates a configuration error.</p>\n", 
                            NULL)); 
     case HTTP_REQUEST_TIME_OUT: 
         return("<p>Server timeout waiting for the HTTP request from the client.</p>\n"); 
     case HTTP_GONE: 
         return(apr_pstrcat(p, 
                            "<p>The requested resource<br />", 
                            ap_escape_html(r->pool, r->uri), 
                            "<br />\nis no longer available on this server " 
                            "and there is no forwarding address.\n" 
                            "Please remove all references to this " 
                            "resource.</p>\n", 
                            NULL)); 
     case HTTP_REQUEST_ENTITY_TOO_LARGE: 
         return(apr_pstrcat(p, 
                            "The requested resource<br />", 
                            ap_escape_html(r->pool, r->uri), "<br />\n", 
                            "does not allow request data with ", 
                            r->method, 
                            " requests, or the amount of data provided in\n" 
                            "the request exceeds the capacity limit.\n", 
                            NULL)); 
     case HTTP_REQUEST_URI_TOO_LARGE: 
         s1 = "<p>The requested URL's length exceeds the capacity\n" 
              "limit for this server.<br />\n"; 
         return(add_optional_notes(r, s1, "error-notes", "</p>\n")); 
     case HTTP_UNSUPPORTED_MEDIA_TYPE: 
         return("<p>The supplied request data is not in a format\n" 
                "acceptable for processing by this resource.</p>\n"); 
     case HTTP_RANGE_NOT_SATISFIABLE: 
         return("<p>None of the range-specifier values in the Range\n" 
                "request-header field overlap the current extent\n" 
                "of the selected resource.</p>\n"); 
     case HTTP_EXPECTATION_FAILED: 
         return(apr_pstrcat(p, 
                            "<p>The expectation given in the Expect " 
                            "request-header" 
                            "\nfield could not be met by this server.</p>\n" 
                            "<p>The client sent<pre>\n    Expect: ", 
                            apr_table_get(r->headers_in, "Expect"), 
                            "\n</pre>\n" 
                            "but we only allow the 100-continue " 
                            "expectation.</p>\n", 
                            NULL)); 
     case HTTP_UNPROCESSABLE_ENTITY: 
         return("<p>The server understands the media type of the\n" 
                "request entity, but was unable to process the\n" 
                "contained instructions.</p>\n"); 
     case HTTP_LOCKED: 
         return("<p>The requested resource is currently locked.\n" 
                "The lock must be released or proper identification\n" 
                "given before the method can be applied.</p>\n"); 
     case HTTP_FAILED_DEPENDENCY: 
         return("<p>The method could not be performed on the resource\n" 
                "because the requested action depended on another\n" 
                "action and that other action failed.</p>\n"); 
     case HTTP_INSUFFICIENT_STORAGE: 
         return("<p>The method could not be performed on the resource\n" 
                "because the server is unable to store the\n" 
                "representation needed to successfully complete the\n" 
                "request.  There is insufficient free space left in\n" 
                "your storage allocation.</p>\n"); 
     case HTTP_SERVICE_UNAVAILABLE: 
         return("<p>The server is temporarily unable to service your\n" 
                "request due to maintenance downtime or capacity\n" 
                "problems. Please try again later.</p>\n"); 
     case HTTP_GATEWAY_TIME_OUT: 
         return("<p>The proxy server did not receive a timely response\n" 
                "from the upstream server.</p>\n"); 
     case HTTP_NOT_EXTENDED: 
         return("<p>A mandatory extension policy in the request is not\n" 
                "accepted by the server for this resource.</p>\n"); 
     default:                    /* HTTP_INTERNAL_SERVER_ERROR */ 
         /* 
          * This comparison to expose error-notes could be modified to 
          * use a configuration directive and export based on that 
          * directive.  For now "*" is used to designate an error-notes 
          * that is totally safe for any user to see (ie lacks paths, 
          * database passwords, etc.) 
          */ 
         if (((error_notes = apr_table_get(r->notes, 
                                           "error-notes")) != NULL) 
             && (h1 = apr_table_get(r->notes, "verbose-error-to")) != NULL 
             && (strcmp(h1, "*") == 0)) { 
             return(apr_pstrcat(p, error_notes, "<p />\n", NULL)); 
         } 
         else { 
             return(apr_pstrcat(p, 
                                "<p>The server encountered an internal " 
                                "error or\n" 
                                "misconfiguration and was unable to complete\n" 
                                "your request.</p>\n" 
                                "<p>Please contact the server " 
                                "administrator,\n ", 
                                ap_escape_html(r->pool, 
                                               r->server->server_admin), 
                                " and inform them of the time the " 
                                "error occurred,\n" 
                                "and anything you might have done that " 
                                "may have\n" 
                                "caused the error.</p>\n" 
                                "<p>More information about this error " 
                                "may be available\n" 
                                "in the server error log.</p>\n", 
                                NULL)); 
         } 
         /* 
          * It would be nice to give the user the information they need to 
          * fix the problem directly since many users don't have access to 
          * the error_log (think University sites) even though they can easily 
          * get this error by misconfiguring an htaccess file.  However, the 
          * e error notes tend to include the real file pathname in this case, 
          * which some people consider to be a breach of privacy.  Until we 
          * can figure out a way to remove the pathname, leave this commented. 
          * 
          * if ((error_notes = apr_table_get(r->notes, 
          *                                  "error-notes")) != NULL) { 
          *     return(apr_pstrcat(p, error_notes, "<p />\n", NULL); 
          * } 
          * else { 
          *     return ""; 
          * } 
          */ 
     } 
 } 
  
 /* We should have named this send_canned_response, since it is used for any 
  * response that can be generated by the server from the request record. 
  * This includes all 204 (no content), 3xx (redirect), 4xx (client error), 
  * and 5xx (server error) messages that have not been redirected to another 
  * handler via the ErrorDocument feature. 
  */ 
 AP_DECLARE(void) ap_send_error_response(request_rec *r, int recursive_error) 
 { 
     int status = r->status; 
     int idx = ap_index_of_response(status); 
     char *custom_response; 
     const char *location = apr_table_get(r->headers_out, "Location"); 
  
     /* At this point, we are starting the response over, so we have to reset 
      * this value. 
      */ 
     r->eos_sent = 0; 
  
     /* and we need to get rid of any RESOURCE filters that might be lurking  
      * around, thinking they are in the middle of the original request 
      */ 
  
     r->output_filters = r->proto_output_filters; 
  
     /* 
      * It's possible that the Location field might be in r->err_headers_out 
      * instead of r->headers_out; use the latter if possible, else the 
      * former. 
      */ 
     if (location == NULL) { 
         location = apr_table_get(r->err_headers_out, "Location"); 
     } 
     /* We need to special-case the handling of 204 and 304 responses, 
      * since they have specific HTTP requirements and do not include a 
      * message body.  Note that being assbackwards here is not an option. 
      */ 
     if (status == HTTP_NOT_MODIFIED) { 
         ap_finalize_request_protocol(r); 
         return; 
     } 
  
     if (status == HTTP_NO_CONTENT) { 
         ap_finalize_request_protocol(r); 
         return; 
     } 
  
     if (!r->assbackwards) { 
         apr_table_t *tmp = r->headers_out; 
  
         /* For all HTTP/1.x responses for which we generate the message, 
          * we need to avoid inheriting the "normal status" header fields 
          * that may have been set by the request handler before the 
          * error or redirect, except for Location on external redirects. 
          */ 
         r->headers_out = r->err_headers_out; 
         r->err_headers_out = tmp; 
         apr_table_clear(r->err_headers_out); 
  
         if (ap_is_HTTP_REDIRECT(status) || (status == HTTP_CREATED)) { 
             if ((location != NULL) && *location) { 
                 apr_table_setn(r->headers_out, "Location", location); 
             } 
             else { 
                 location = "";   /* avoids coredump when printing, below */ 
             } 
         } 
  
         r->content_languages = NULL; 
         r->content_encoding = NULL; 
         r->clength = 0; 
         ap_set_content_type(r, "text/html; charset=iso-8859-1"); 
  
         if ((status == HTTP_METHOD_NOT_ALLOWED) 
             || (status == HTTP_NOT_IMPLEMENTED)) { 
             apr_table_setn(r->headers_out, "Allow", make_allow(r)); 
         } 
  
         if (r->header_only) { 
             ap_finalize_request_protocol(r); 
             return; 
         } 
     } 
  
     if ((custom_response = ap_response_code_string(r, idx))) { 
         /* 
          * We have a custom response output. This should only be 
          * a text-string to write back. But if the ErrorDocument 
          * was a local redirect and the requested resource failed 
          * for any reason, the custom_response will still hold the 
          * redirect URL. We don't really want to output this URL 
          * as a text message, so first check the custom response 
          * string to ensure that it is a text-string (using the 
          * same test used in ap_die(), i.e. does it start with a "). 
          * If it doesn't, we've got a recursive error, so find 
          * the original error and output that as well. 
          */ 
         if (custom_response[0] == '\"') { 
             ap_rputs(custom_response + 1, r); 
             ap_finalize_request_protocol(r); 
             return; 
         } 
         /* 
          * Redirect failed, so get back the original error 
          */ 
         while (r->prev && (r->prev->status != HTTP_OK)) 
             r = r->prev; 
     } 
     { 
         const char *title = status_lines[idx]; 
         const char *h1; 
  
         /* XXX This is a major hack that should be fixed cleanly.  The 
          * problem is that we have the information we need in a previous 
          * request, but the text of the page must be sent down the last 
          * request_rec's filter stack.  rbb 
          */ 
         request_rec *rlast = r; 
         while (rlast->next) { 
             rlast = rlast->next; 
         } 
  
         /* Accept a status_line set by a module, but only if it begins 
          * with the 3 digit status code 
          */ 
         if (r->status_line != NULL 
             && strlen(r->status_line) > 4       /* long enough */ 
             && apr_isdigit(r->status_line[0]) 
             && apr_isdigit(r->status_line[1]) 
             && apr_isdigit(r->status_line[2]) 
             && apr_isspace(r->status_line[3]) 
             && apr_isalnum(r->status_line[4])) { 
             title = r->status_line; 
         } 
  
         /* folks decided they didn't want the error code in the H1 text */ 
         h1 = &title[4]; 
  
         /* can't count on a charset filter being in place here, 
          * so do ebcdic->ascii translation explicitly (if needed) 
          */ 
  
         ap_rvputs_proto_in_ascii(rlast, 
                   DOCTYPE_HTML_2_0 
                   "<html><head>\n<title>", title, 
                   "</title>\n</head><body>\n<h1>", h1, "</h1>\n", 
                   NULL); 
  
         ap_rvputs_proto_in_ascii(rlast, 
                                  get_canned_error_string(status, r, location), 
                                  NULL); 
  
         if (recursive_error) { 
             ap_rvputs_proto_in_ascii(rlast, "<p>Additionally, a ", 
                       status_lines[ap_index_of_response(recursive_error)], 
                       "\nerror was encountered while trying to use an " 
                       "ErrorDocument to handle the request.</p>\n", NULL); 
         } 
         ap_rvputs_proto_in_ascii(rlast, ap_psignature("<hr />\n", r), NULL); 
         ap_rvputs_proto_in_ascii(rlast, "</body></html>\n", NULL); 
     } 
     ap_finalize_request_protocol(r); 
 } 
  
 /* 
  * Create a new method list with the specified number of preallocated 
  * extension slots. 
  */ 
 AP_DECLARE(ap_method_list_t *) ap_make_method_list(apr_pool_t *p, int nelts) 
 { 
     ap_method_list_t *ml; 
  
     ml = (ap_method_list_t *) apr_palloc(p, sizeof(ap_method_list_t)); 
     ml->method_mask = 0; 
     ml->method_list = apr_array_make(p, sizeof(char *), nelts); 
     return ml; 
 } 
  
 /* 
  * Make a copy of a method list (primarily for subrequests that may 
  * subsequently change it; don't want them changing the parent's, too!). 
  */ 
 AP_DECLARE(void) ap_copy_method_list(ap_method_list_t *dest, 
                                      ap_method_list_t *src) 
 { 
     int i; 
     char **imethods; 
     char **omethods; 
  
     dest->method_mask = src->method_mask; 
     imethods = (char **) src->method_list->elts; 
     for (i = 0; i < src->method_list->nelts; ++i) { 
         omethods = (char **) apr_array_push(dest->method_list); 
         *omethods = apr_pstrdup(dest->method_list->pool, imethods[i]); 
     } 
 } 
  
 /* 
  * Invoke a callback routine for each method in the specified list. 
  */ 
 AP_DECLARE_NONSTD(void) ap_method_list_do(int (*comp) (void *urec, 
                                                        const char *mname, 
                                                        int mnum), 
                                           void *rec, 
                                           const ap_method_list_t *ml, ...) 
 { 
     va_list vp; 
     va_start(vp, ml); 
     ap_method_list_vdo(comp, rec, ml, vp); 
     va_end(vp); 
 } 
  
 AP_DECLARE(void) ap_method_list_vdo(int (*comp) (void *mrec, 
                                                  const char *mname, 
                                                  int mnum), 
                                     void *rec, const ap_method_list_t *ml, 
                                     va_list vp) 
 { 
  
 } 
  
 /* 
  * Return true if the specified HTTP method is in the provided 
  * method list. 
  */ 
 AP_DECLARE(int) ap_method_in_list(ap_method_list_t *l, const char *method) 
 { 
     int methnum; 
     int i; 
     char **methods; 
  
     /* 
      * If it's one of our known methods, use the shortcut and check the 
      * bitmask. 
      */ 
     methnum = ap_method_number_of(method); 
     if (methnum != M_INVALID) { 
         return !!(l->method_mask & (AP_METHOD_BIT << methnum)); 
     } 
     /* 
      * Otherwise, see if the method name is in the array or string names 
      */ 
     if ((l->method_list == NULL) || (l->method_list->nelts == 0)) { 
         return 0; 
     } 
     methods = (char **)l->method_list->elts; 
     for (i = 0; i < l->method_list->nelts; ++i) { 
         if (strcmp(method, methods[i]) == 0) { 
             return 1; 
         } 
     } 
     return 0; 
 } 
  
 /* 
  * Add the specified method to a method list (if it isn't already there). 
  */ 
 AP_DECLARE(void) ap_method_list_add(ap_method_list_t *l, const char *method) 
 { 
     int methnum; 
     int i; 
     const char **xmethod; 
     char **methods; 
  
     /* 
      * If it's one of our known methods, use the shortcut and use the 
      * bitmask. 
      */ 
     methnum = ap_method_number_of(method); 
     l->method_mask |= (AP_METHOD_BIT << methnum); 
     if (methnum != M_INVALID) { 
         return; 
     } 
     /* 
      * Otherwise, see if the method name is in the array of string names. 
      */ 
     if (l->method_list->nelts != 0) { 
         methods = (char **)l->method_list->elts; 
         for (i = 0; i < l->method_list->nelts; ++i) { 
             if (strcmp(method, methods[i]) == 0) { 
                 return; 
             } 
         } 
     } 
     xmethod = (const char **) apr_array_push(l->method_list); 
     *xmethod = method; 
 } 
  
 /* 
  * Remove the specified method from a method list. 
  */ 
 AP_DECLARE(void) ap_method_list_remove(ap_method_list_t *l, 
                                        const char *method) 
 { 
     int methnum; 
     char **methods; 
  
     /* 
      * If it's a known methods, either builtin or registered 
      * by a module, use the bitmask. 
      */ 
     methnum = ap_method_number_of(method); 
     l->method_mask |= ~(AP_METHOD_BIT << methnum); 
     if (methnum != M_INVALID) { 
         return; 
     } 
     /* 
      * Otherwise, see if the method name is in the array of string names. 
      */ 
     if (l->method_list->nelts != 0) { 
         register int i, j, k; 
         methods = (char **)l->method_list->elts; 
         for (i = 0; i < l->method_list->nelts; ) { 
             if (strcmp(method, methods[i]) == 0) { 
                 for (j = i, k = i + 1; k < l->method_list->nelts; ++j, ++k) { 
                     methods[j] = methods[k]; 
                 } 
                 --l->method_list->nelts; 
             } 
             else { 
                 ++i; 
             } 
         } 
     } 
 } 
  
 /* 
  * Reset a method list to be completely empty. 
  */ 
 AP_DECLARE(void) ap_clear_method_list(ap_method_list_t *l) 
 { 
     l->method_mask = 0; 
     l->method_list->nelts = 0; 
 } 
  
 /* Generate the human-readable hex representation of an unsigned long 
  * (basically a faster version of 'sprintf("%lx")') 
  */ 
 #define HEX_DIGITS "0123456789abcdef" 
 static char *etag_ulong_to_hex(char *next, unsigned long u) 
 { 
     int printing = 0; 
     int shift = sizeof(unsigned long) * 8 - 4; 
     do { 
         unsigned long next_digit = ((u >> shift) & (unsigned long)0xf); 
         if (next_digit) { 
             *next++ = HEX_DIGITS[next_digit]; 
             printing = 1; 
         } 
         else if (printing) { 
             *next++ = HEX_DIGITS[next_digit]; 
         } 
         shift -= 4; 
     } while (shift); 
     *next++ = HEX_DIGITS[u & (unsigned long)0xf]; 
     return next; 
 } 
  
 #define ETAG_WEAK "W/" 
 #define CHARS_PER_UNSIGNED_LONG (sizeof(unsigned long) * 2) 
 /* 
  * Construct an entity tag (ETag) from resource information.  If it's a real 
  * file, build in some of the file characteristics.  If the modification time 
  * is newer than (request-time minus 1 second), mark the ETag as weak - it 
  * could be modified again in as short an interval.  We rationalize the 
  * modification time we're given to keep it from being in the future. 
  */ 
 AP_DECLARE(char *) ap_make_etag(request_rec *r, int force_weak) 
 { 
     char *weak; 
     apr_size_t weak_len; 
     char *etag; 
     char *next; 
     core_dir_config *cfg; 
     etag_components_t etag_bits; 
     etag_components_t bits_added; 
  
     cfg = (core_dir_config *)ap_get_module_config(r->per_dir_config, 
                                                   &core_module); 
     etag_bits = (cfg->etag_bits & (~ cfg->etag_remove)) | cfg->etag_add; 
  
     /* 
      * If it's a file (or we wouldn't be here) and no ETags 
      * should be set for files, return an empty string and 
      * note it for the header-sender to ignore. 
      */ 
     if (etag_bits & ETAG_NONE) { 
         apr_table_setn(r->notes, "no-etag", "omit"); 
         return ""; 
     } 
  
     if (etag_bits == ETAG_UNSET) { 
         etag_bits = ETAG_BACKWARD; 
     } 
     /* 
      * Make an ETag header out of various pieces of information. We use 
      * the last-modified date and, if we have a real file, the 
      * length and inode number - note that this doesn't have to match 
      * the content-length (i.e. includes), it just has to be unique 
      * for the file. 
      * 
      * If the request was made within a second of the last-modified date, 
      * we send a weak tag instead of a strong one, since it could 
      * be modified again later in the second, and the validation 
      * would be incorrect. 
      */ 
     if ((r->request_time - r->mtime > APR_USEC_PER_SEC) && !force_weak) { 
         weak = NULL; 
         weak_len = 0; 
     } 
     else { 
         weak = ETAG_WEAK; 
         weak_len = sizeof(ETAG_WEAK); 
     } 
  
     if (r->finfo.filetype != 0) { 
         /* 
          * ETag gets set to [W/]"inode-size-mtime", modulo any 
          * FileETag keywords. 
          */ 
         etag = apr_palloc(r->pool, weak_len + sizeof("\"--\"") + 
                           3 * CHARS_PER_UNSIGNED_LONG + 1); 
         next = etag; 
         if (weak) { 
             while (*weak) { 
                 *next++ = *weak++; 
             } 
         } 
         *next++ = '"'; 
         bits_added = 0; 
         if (etag_bits & ETAG_INODE) { 
             next = etag_ulong_to_hex(next, (unsigned long)r->finfo.inode); 
             bits_added |= ETAG_INODE; 
         } 
         if (etag_bits & ETAG_SIZE) { 
             if (bits_added != 0) { 
                 *next++ = '-'; 
             } 
             next = etag_ulong_to_hex(next, (unsigned long)r->finfo.size); 
             bits_added |= ETAG_SIZE; 
         } 
         if (etag_bits & ETAG_MTIME) { 
             if (bits_added != 0) { 
                 *next++ = '-'; 
             } 
             next = etag_ulong_to_hex(next, (unsigned long)r->mtime); 
         } 
         *next++ = '"'; 
         *next = '\0'; 
     } 
     else { 
         /* 
          * Not a file document, so just use the mtime: [W/]"mtime" 
          */ 
         etag = apr_palloc(r->pool, weak_len + sizeof("\"\"") + 
                           CHARS_PER_UNSIGNED_LONG + 1); 
         next = etag; 
         if (weak) { 
             while (*weak) { 
                 *next++ = *weak++; 
             } 
         } 
         *next++ = '"'; 
         next = etag_ulong_to_hex(next, (unsigned long)r->mtime); 
         *next++ = '"'; 
         *next = '\0'; 
     } 
  
     return etag; 
 } 
  
 AP_DECLARE(void) ap_set_etag(request_rec *r) 
 { 
     char *etag; 
     char *variant_etag, *vlv; 
     int vlv_weak; 
  
     if (!r->vlist_validator) { 
         etag = ap_make_etag(r, 0); 
     } 
     else { 
         /* If we have a variant list validator (vlv) due to the 
          * response being negotiated, then we create a structured 
          * entity tag which merges the variant etag with the variant 
          * list validator (vlv).  This merging makes revalidation 
          * somewhat safer, ensures that caches which can deal with 
          * Vary will (eventually) be updated if the set of variants is 
          * changed, and is also a protocol requirement for transparent 
          * content negotiation. 
          */ 
  
         /* if the variant list validator is weak, we make the whole 
          * structured etag weak.  If we would not, then clients could 
          * have problems merging range responses if we have different 
          * variants with the same non-globally-unique strong etag. 
          */ 
  
         vlv = r->vlist_validator; 
         vlv_weak = (vlv[0] == 'W'); 
  
         variant_etag = ap_make_etag(r, vlv_weak); 
  
         /* merge variant_etag and vlv into a structured etag */ 
  
         variant_etag[strlen(variant_etag) - 1] = '\0'; 
         if (vlv_weak) { 
             vlv += 3; 
         } 
         else { 
             vlv++; 
         } 
         etag = apr_pstrcat(r->pool, variant_etag, ";", vlv, NULL); 
     } 
  
     apr_table_setn(r->headers_out, "ETag", etag); 
 } 
  
 static int parse_byterange(char *range, apr_off_t clength, 
                            apr_off_t *start, apr_off_t *end) 
 { 
     char *dash = strchr(range, '-'); 
  
     if (!dash) { 
         return 0; 
     } 
  
     if ((dash == range)) { 
         /* In the form "-5" */ 
         *start = clength - atol(dash + 1); 
         *end = clength - 1; 
     } 
     else { 
         *dash = '\0'; 
         dash++; 
         *start = atol(range); 
         if (*dash) { 
             *end = atol(dash); 
         } 
         else {                  /* "5-" */ 
             *end = clength - 1; 
         } 
     } 
  
     if (*start < 0) { 
         *start = 0; 
     } 
  
     if (*end >= clength) { 
         *end = clength - 1; 
     } 
  
     if (*start > *end) { 
         return -1; 
     } 
  
     return (*start > 0 || *end < clength); 
 } 
  
 static int ap_set_byterange(request_rec *r); 
  
 typedef struct byterange_ctx { 
     apr_bucket_brigade *bb; 
     int num_ranges; 
     char *boundary; 
     char *bound_head; 
 } byterange_ctx; 
  
 /* 
  * Here we try to be compatible with clients that want multipart/x-byteranges 
  * instead of multipart/byteranges (also see above), as per HTTP/1.1. We 
  * look for the Request-Range header (e.g. Netscape 2 and 3) as an indication 
  * that the browser supports an older protocol. We also check User-Agent 
  * for Microsoft Internet Explorer 3, which needs this as well. 
  */ 
 static int use_range_x(request_rec *r) 
 { 
     const char *ua; 
     return (apr_table_get(r->headers_in, "Request-Range") 
             || ((ua = apr_table_get(r->headers_in, "User-Agent")) 
                 && ap_strstr_c(ua, "MSIE 3"))); 
 } 
  
 #define BYTERANGE_FMT "%" APR_OFF_T_FMT "-%" APR_OFF_T_FMT "/%" APR_OFF_T_FMT 
 #define PARTITION_ERR_FMT "apr_brigade_partition() failed " \ 
                           "[%" APR_OFF_T_FMT ",%" APR_OFF_T_FMT "]" 
  
 AP_CORE_DECLARE_NONSTD(apr_status_t) ap_byterange_filter(ap_filter_t *f, 
                                                          apr_bucket_brigade *bb) 
 { 
 #define MIN_LENGTH(len1, len2) ((len1 > len2) ? len2 : len1) 
     request_rec *r = f->r; 
     conn_rec *c = r->connection; 
     byterange_ctx *ctx = f->ctx; 
     apr_bucket *e; 
     apr_bucket_brigade *bsend; 
     apr_off_t range_start; 
     apr_off_t range_end; 
     char *current; 
     apr_off_t bb_length; 
     apr_off_t clength = 0; 
     apr_status_t rv; 
     int found = 0; 
  
     if (!ctx) { 
         int num_ranges = ap_set_byterange(r); 
  
         /* We have nothing to do, get out of the way. */ 
         if (num_ranges == 0) { 
             ap_remove_output_filter(f); 
             return ap_pass_brigade(f->next, bb); 
         } 
  
         ctx = f->ctx = apr_pcalloc(r->pool, sizeof(*ctx)); 
         ctx->num_ranges = num_ranges; 
         /* create a brigade in case we never call ap_save_brigade() */ 
         ctx->bb = apr_brigade_create(r->pool, c->bucket_alloc); 
  
         if (ctx->num_ranges > 1) { 
             /* Is ap_make_content_type required here? */ 
             const char *orig_ct = ap_make_content_type(r, r->content_type); 
             ctx->boundary = apr_psprintf(r->pool, "%qx%lx", 
                                          r->request_time, (long) getpid()); 
  
             ap_set_content_type(r, apr_pstrcat(r->pool, "multipart", 
                                                use_range_x(r) ? "/x-" : "/", 
                                                "byteranges; boundary=", 
                                                ctx->boundary, NULL)); 
  
             ctx->bound_head = apr_pstrcat(r->pool, 
                                     CRLF "--", ctx->boundary, 
                                     CRLF "Content-type: ", 
                                     orig_ct, 
                                     CRLF "Content-range: bytes ", 
                                     NULL); 
             ap_xlate_proto_to_ascii(ctx->bound_head, strlen(ctx->bound_head)); 
         } 
     } 
  
     /* We can't actually deal with byte-ranges until we have the whole brigade 
      * because the byte-ranges can be in any order, and according to the RFC, 
      * we SHOULD return the data in the same order it was requested. 
      */ 
     if (!APR_BUCKET_IS_EOS(APR_BRIGADE_LAST(bb))) { 
         ap_save_brigade(f, &ctx->bb, &bb, r->pool); 
         return APR_SUCCESS; 
     } 
  
     /* Prepend any earlier saved brigades. */ 
     APR_BRIGADE_PREPEND(bb, ctx->bb); 
  
     /* It is possible that we won't have a content length yet, so we have to 
      * compute the length before we can actually do the byterange work. 
      */ 
     apr_brigade_length(bb, 1, &bb_length); 
     clength = (apr_off_t)bb_length; 
  
     /* this brigade holds what we will be sending */ 
     bsend = apr_brigade_create(r->pool, c->bucket_alloc); 
  
     while ((current = ap_getword(r->pool, &r->range, ',')) 
            && (rv = parse_byterange(current, clength, &range_start, 
                                     &range_end))) { 
         apr_bucket *e2; 
         apr_bucket *ec; 
  
         if (rv == -1) { 
             continue; 
         } 
  
         /* these calls to apr_brigade_partition() should theoretically 
          * never fail because of the above call to apr_brigade_length(), 
          * but what the heck, we'll check for an error anyway */ 
         if ((rv = apr_brigade_partition(bb, range_start, &ec)) != APR_SUCCESS) { 
             ap_log_rerror(APLOG_MARK, APLOG_ERR, rv, r, 
                           PARTITION_ERR_FMT, range_start, clength); 
             continue; 
         } 
         if ((rv = apr_brigade_partition(bb, range_end+1, &e2)) != APR_SUCCESS) { 
             ap_log_rerror(APLOG_MARK, APLOG_ERR, rv, r, 
                           PARTITION_ERR_FMT, range_end+1, clength); 
             continue; 
         } 
  
         found = 1; 
  
         /* For single range requests, we must produce Content-Range header. 
          * Otherwise, we need to produce the multipart boundaries. 
          */ 
         if (ctx->num_ranges == 1) { 
             apr_table_setn(r->headers_out, "Content-Range", 
                            apr_psprintf(r->pool, "bytes " BYTERANGE_FMT, 
                                         range_start, range_end, clength)); 
         } 
         else { 
             char *ts; 
  
             e = apr_bucket_pool_create(ctx->bound_head, strlen(ctx->bound_head), 
                                        r->pool, c->bucket_alloc); 
             APR_BRIGADE_INSERT_TAIL(bsend, e); 
  
             ts = apr_psprintf(r->pool, BYTERANGE_FMT CRLF CRLF, 
                               range_start, range_end, clength); 
             ap_xlate_proto_to_ascii(ts, strlen(ts)); 
             e = apr_bucket_pool_create(ts, strlen(ts), r->pool, 
                                        c->bucket_alloc); 
             APR_BRIGADE_INSERT_TAIL(bsend, e); 
         } 
  
         do { 
             apr_bucket *foo; 
             const char *str; 
             apr_size_t len; 
  
             if (apr_bucket_copy(ec, &foo) != APR_SUCCESS) { 
                 /* this shouldn't ever happen due to the call to 
                  * apr_brigade_length() above which normalizes 
                  * indeterminate-length buckets.  just to be sure, 
                  * though, this takes care of uncopyable buckets that 
                  * do somehow manage to slip through. 
                  */ 
                 /* XXX: check for failure? */ 
                 apr_bucket_read(ec, &str, &len, APR_BLOCK_READ); 
                 apr_bucket_copy(ec, &foo); 
             } 
             APR_BRIGADE_INSERT_TAIL(bsend, foo); 
             ec = APR_BUCKET_NEXT(ec); 
         } while (ec != e2); 
     } 
  
     if (found == 0) { 
         ap_remove_output_filter(f); 
         r->status = HTTP_OK; 
         /* bsend is assumed to be empty if we get here. */ 
         e = ap_bucket_error_create(HTTP_RANGE_NOT_SATISFIABLE, NULL, 
                                    r->pool, c->bucket_alloc); 
         APR_BRIGADE_INSERT_TAIL(bsend, e); 
         e = apr_bucket_eos_create(c->bucket_alloc); 
         APR_BRIGADE_INSERT_TAIL(bsend, e); 
         return ap_pass_brigade(f->next, bsend); 
     } 
  
     if (ctx->num_ranges > 1) { 
         char *end; 
  
         /* add the final boundary */ 
         end = apr_pstrcat(r->pool, CRLF "--", ctx->boundary, "--" CRLF, NULL); 
         ap_xlate_proto_to_ascii(end, strlen(end)); 
         e = apr_bucket_pool_create(end, strlen(end), r->pool, c->bucket_alloc); 
         APR_BRIGADE_INSERT_TAIL(bsend, e); 
     } 
  
     e = apr_bucket_eos_create(c->bucket_alloc); 
     APR_BRIGADE_INSERT_TAIL(bsend, e); 
  
     /* we're done with the original content - all of our data is in bsend. */ 
     apr_brigade_destroy(bb); 
  
     /* send our multipart output */ 
     return ap_pass_brigade(f->next, bsend); 
 } 
  
 static int ap_set_byterange(request_rec *r) 
 { 
     const char *range; 
     const char *if_range; 
     const char *match; 
     const char *ct; 
     int num_ranges; 
  
     if (r->assbackwards) { 
         return 0; 
     } 
  
     /* Check for Range request-header (HTTP/1.1) or Request-Range for 
      * backwards-compatibility with second-draft Luotonen/Franks 
      * byte-ranges (e.g. Netscape Navigator 2-3). 
      * 
      * We support this form, with Request-Range, and (farther down) we 
      * send multipart/x-byteranges instead of multipart/byteranges for 
      * Request-Range based requests to work around a bug in Netscape 
      * Navigator 2-3 and MSIE 3. 
      */ 
  
     if (!(range = apr_table_get(r->headers_in, "Range"))) { 
         range = apr_table_get(r->headers_in, "Request-Range"); 
     } 
  
     if (!range || strncasecmp(range, "bytes=", 6)) { 
         return 0; 
     } 
  
     /* is content already a single range? */ 
     if (apr_table_get(r->headers_out, "Content-Range")) { 
        return 0; 
     } 
  
     /* is content already a multiple range? */ 
     if ((ct = apr_table_get(r->headers_out, "Content-Type")) 
         && (!strncasecmp(ct, "multipart/byteranges", 20) 
             || !strncasecmp(ct, "multipart/x-byteranges", 22))) { 
        return 0; 
     } 
  
     /* Check the If-Range header for Etag or Date. 
      * Note that this check will return false (as required) if either 
      * of the two etags are weak. 
      */ 
     if ((if_range = apr_table_get(r->headers_in, "If-Range"))) { 
         if (if_range[0] == '"') { 
             if (!(match = apr_table_get(r->headers_out, "Etag")) 
                 || (strcmp(if_range, match) != 0)) { 
                 return 0; 
             } 
         } 
         else if (!(match = apr_table_get(r->headers_out, "Last-Modified")) 
                  || (strcmp(if_range, match) != 0)) { 
             return 0; 
         } 
     } 
  
     if (!ap_strchr_c(range, ',')) { 
         /* a single range */ 
         num_ranges = 1; 
     } 
     else { 
         /* a multiple range */ 
         num_ranges = 2; 
     } 
  
     r->status = HTTP_PARTIAL_CONTENT; 
     r->range = range + 6; 
  
     return num_ranges; 
** }
### Hi there 👋
Github/workflows/gem-push.yml/SECURITY.md

**ramoncerdaquiroz/ramoncerdaquiroz** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on …
- 🌱 I’m currently learning …
- 👯 I’m looking to collaborate on …
- 🤔 I’m looking for help with …
- 💬 Ask me about …
- 📫 How to reach me: …
- 😄 Pronouns: …
- ⚡ Fun fact: …
**#                                  Apache License 
                            Version 2.0, January 2004 
                         https://www.apache.org/licenses/ 
  
    TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION 
  
1.	Definitions. 
  
       “License” shall mean the terms and conditions for use, reproduction, 
       And distribution as defined by Sections 1 through 9 of this document. 
  
       “Licensor” shall mean the copyright owner or entity authorized by 
       The copyright owner that is granting the License. 
  
       “Legal Entity” shall mean the union of the acting entity and all 
       Other entities that control, are controlled by, or are under common 
       Control with that entity. For the purposes of this definition, 
       “control” means (i) the power, direct or indirect, to cause the 
       Direction or management of such entity, whether by contract or 
       Otherwise, or (ii) ownership of fifty percent (50%) or more of the 
       Outstanding shares, or (iii) beneficial ownership of such entity. 
  
       “You” (or “Your”) shall mean an individual or Legal Entity 
       Exercising permissions granted by this License. 
  
       “Source” form shall mean the preferred form for making modifications, 
       Including but not limited to software source code, documentation 
       Source, and configuration files. 
  
       “Object” form shall mean any form resulting from mechanical 
       Transformation or translation of a Source form, including but 
       Not limited to compiled object code, generated documentation, 
       And conversions to other media types. 
  
       “Work” shall mean the work of authorship, whether in Source or 
       Object form, made available under the License, as indicated by a 
       Copyright notice that is included in or attached to the work 
       (an example is provided in the Appendix below). 
  
       “Derivative Works” shall mean any work, whether in Source or Object 
       Form, that is based on (or derived from) the Work and for which the 
       Editorial revisions, annotations, elaborations, or other modifications 
       Represent, as a whole, an original work of authorship. For the purposes 
       Of this License, Derivative Works shall not include works that remain 
       Separable from, or merely link (or bind by name) to the interfaces of, 
       The Work and Derivative Works thereof. 
  
       “Contribution” shall mean any work of authorship, including 
       The original version of the Work and any modifications or additions 
       To that Work or Derivative Works thereof, that is intentionally 
       Submitted to Licensor for inclusion in the Work by the copyright owner 
       Or by an individual or Legal Entity authorized to submit on behalf of 
       The copyright owner. For the purposes of this definition, “submitted” 
       Means any form of electronic, verbal, or written communication sent 
       To the Licensor or its representatives, including but not limited to 
       Communication on electronic mailing lists, source code control systems, 
       And issue tracking systems that are managed by, or on behalf of, the 
       Licensor for the purpose of discussing and improving the Work, but 
       Excluding communication that is conspicuously marked or otherwise 
       Designated in writing by the copyright owner as “Not a Contribution.” 
  
       “Contributor” shall mean Licensor and any individual or Legal Entity 
       On behalf of whom a Contribution has been received by Licensor and 
       Subsequently incorporated within the Work. 
  
2.	Grant of Copyright License. Subject to the terms and conditions of 
       This License, each Contributor hereby grants to You a perpetual, 
       Worldwide, non-exclusive, no-charge, royalty-free, irrevocable 
       Copyright license to reproduce, prepare Derivative Works of, 
       Publicly display, publicly perform, sublicense, and distribute the 
       Work and such Derivative Works in Source or Object form. 
  
3.	Grant of Patent License. Subject to the terms and conditions of 
       This License, each Contributor hereby grants to You a perpetual, 
       Worldwide, non-exclusive, no-charge, royalty-free, irrevocable 
       (except as stated in this section) patent license to make, have made, 
       Use, offer to sell, sell, import, and otherwise transfer the Work, 
       Where such license applies only to those patent claims licensable 
       By such Contributor that are necessarily infringed by their 
       Contribution(s) alone or by combination of their Contribution(s) 
       With the Work to which such Contribution(s) was submitted. If You 
       Institute patent litigation against any entity (including a 
       Cross-claim or counterclaim in a lawsuit) alleging that the Work 
       Or a Contribution incorporated within the Work constitutes direct 
       Or contributory patent infringement, then any patent licenses 
       Granted to You under this License for that Work shall terminate 
       As of the date such litigation is filed. 
  
4.	Redistribution. You may reproduce and distribute copies of the 
       Work or Derivative Works thereof in any medium, with or without 
       Modifications, and in Source or Object form, provided that You 
       Meet the following conditions: 
  
(a)	You must give any other recipients of the Work or 
           Derivative Works a copy of this License; and 
  
(b)	You must cause any modified files to carry prominent notices 
           Stating that You changed the files; and 
  
       © You must retain, in the Source form of any Derivative Works 
           That You distribute, all copyright, patent, trademark, and 
           Attribution notices from the Source form of the Work, 
           Excluding those notices that do not pertain to any part of 
           The Derivative Works; and 
  
(c)	If the Work includes a “NOTICE” text file as part of its 
           Distribution, then any Derivative Works that You distribute must 
           Include a readable copy of the attribution notices contained 
           Within such NOTICE file, excluding those notices that do not 
           Pertain to any part of the Derivative Works, in at least one 
           Of the following places: within a NOTICE text file distributed 
           As part of the Derivative Works; within the Source form or 
           Documentation, if provided along with the Derivative Works; or, 
           Within a display generated by the Derivative Works, if and 
           Wherever such third-party notices normally appear. The contents 
           Of the NOTICE file are for informational purposes only and 
           Do not modify the License. You may add Your own attribution 
           Notices within Derivative Works that You distribute, alongside 
           Or as an addendum to the NOTICE text from the Work, provided 
           That such additional attribution notices cannot be construed 
           As modifying the License. 
  
       You may add Your own copyright statement to Your modifications and 
       May provide additional or different license terms and conditions 
       For use, reproduction, or distribution of Your modifications, or 
       For any such Derivative Works as a whole, provided Your use, 
       Reproduction, and distribution of the Work otherwise complies with 
       The conditions stated in this License. 
  
5.	Submission of Contributions. Unless You explicitly state otherwise, 
       Any Contribution intentionally submitted for inclusion in the Work 
       By You to the Licensor shall be under the terms and conditions of 
       This License, without any additional terms or conditions. 
       Notwithstanding the above, nothing herein shall supersede or modify 
       The terms of any separate license agreement you may have executed 
       With Licensor regarding such Contributions. 
  
6.	Trademarks. This License does not grant permission to use the trade 
       Names, trademarks, service marks, or product names of the Licensor, 
       Except as required for reasonable and customary use in describing the 
       Origin of the Work and reproducing the content of the NOTICE file. 
  
7.	Disclaimer of Warranty. Unless required by applicable law or 
       Agreed to in writing, Licensor provides the Work (and each 
       Contributor provides its Contributions) on an “AS IS” BASIS, 
       WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or 
       Implied, including, without limitation, any warranties or conditions 
       Of TITLE, NON-INFRINGEMENT, MERCHANTABILITY, or FITNESS FOR A 
       PARTICULAR PURPOSE. You are solely responsible for determining the 
       Appropriateness of using or redistributing the Work and assume any 
       Risks associated with Your exercise of permissions under this License. 
  
8.	Limitation of Liability. In no event and under no legal theory, 
       Whether in tort (including negligence), contract, or otherwise, 
       Unless required by applicable law (such as deliberate and grossly 
       Negligent acts) or agreed to in writing, shall any Contributor be 
       Liable to You for damages, including any direct, indirect, special, 
       Incidental, or consequential damages of any character arising as a 
       Result of this License or out of the use or inability to use the 
       Work (including but not limited to damages for loss of goodwill, 
       Work stoppage, computer failure or malfunction, or any and all 
       Other commercial damages or losses), even if such Contributor 
       Has been advised of the possibility of such damages. 
  
9.	Accepting Warranty or Additional Liability. While redistributing 
       The Work or Derivative Works thereof, You may choose to offer, 
       And charge a fee for, acceptance of support, warranty, indemnity, 
       Or other liability obligations and/or rights consistent with this 
       License. However, in accepting such obligations, You may act only 
       On Your own behalf and on Your sole responsibility, not on behalf 
       Of any other Contributor, and only if You agree to indemnify, 
       Defend, and hold each Contributor harmless for any liability 
       Incurred by, or claims asserted against, such Contributor by reason 
       Of your accepting any such warranty or additional liability. 
  
    END OF TERMS AND CONDITIONS 
  
    APPENDIX: How to apply the Apache License to your work. 
  
       To apply the Apache License to your work, attach the following 
       Boilerplate notice, with the fields enclosed by brackets “{}” 
       Replaced with your own identifying information. (Don’t include 
       The brackets!)  The text should be enclosed in the appropriate 
       Comment syntax for the file format. We also recommend that a 
       File or class name and description of purpose be included on the 
       Same “printed page” as the copyright notice for easier 
       Identification within third-party archives. 
  
    Copyright {yyyy} {name of copyright owner} 
  
    Licensed under the Apache License, Version 2.0 (the “License”); 
    You may not use this file except in compliance with the License. 
    You may obtain a copy of the License at 
  
        https://www.apache.org/licenses/LICENSE-2.0 
  
    Unless required by applicable law or agreed to in writing, software 
    Distributed under the License is distributed on an “AS IS” BASIS, 
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. 
    See the License for the specific language governing permissions and 
    Limitations under the License. 
 
**
#  http://www.apache.org/licenses/LICENSE-2.0
.. Licensed to the Apache Software Foundation (ASF) under one 
    Or more contributor license agreements.  See the NOTICE file 
    Distributed with this work for additional information 
    Regarding copyright ownership.  The ASF licenses this file 
    To you under the Apache License, Version 2.0 (the 
    “License”); you may not use this file except in compliance 
    With the License.  You may obtain a copy of the License at 
  
 ..   http://www.apache.org/licenses/LICENSE-2.0 
  
 .. Unless required by applicable law or agreed to in writing, 
    Software distributed under the License is distributed on an 
    “AS IS” BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY 
    KIND, either express or implied.  See the License for the 
    Specific language governing permissions and limitations 
    Under the License.
	   Or more contributor license agreements.  See the NOTICE file 
    Distributed with this work for additional information 
    Regarding copyright ownership.  The ASF licenses this file 
    To you under the Apache License, Version 2.0 (the 
    “License”); you may not use this file except in compliance 
    With the License.  You may obtain a copy of the License at 
  
 ..   http://www.apache.org/licenses/LICENSE-2.0 
  
 .. Unless required by applicable law or agreed to in writing, 
    Software distributed under the License is distributed on an 
    “AS IS” BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY 
    KIND, either express or implied.  See the License for the 
    Specific language governing permissions and limitations 
    Under the License.
{[**### Reactor Core 
  
 [¡[Join the chat at https://gitter.im/reactor/reactor](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/reactor/reactor?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) 
 [¡[Reactor Core](https://maven-badges.herokuapp.com/maven-central/io.projectreactor/reactor-core/badge.svg?style=plastic)](https://mvnrepository.com/artifact/io.projectreactor/reactor-core) [¡[Latest](https://img.shields.io/github/release/reactor/reactor-core/all.svg)]()  
  
 [¡[CI on GHA](https://github.com/reactor/reactor-core/actions/workflows/publish.yml/badge.svg)](https://github.com/reactor/reactor-core/actions/workflows/publish.yml) 
 [¡[Codecov](https://img.shields.io/codecov/c/github/reactor/reactor-core.svg)]() 
 [¡[Code Quality: Java](https://img.shields.io/lgtm/grade/java/g/reactor/reactor-core.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/reactor/reactor-core/context:java) 
 [¡[Total Alerts](https://img.shields.io/lgtm/alerts/g/reactor/reactor-core.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/reactor/reactor-core/alerts) 
  
  
 Non-Blocking [Reactive Streams](https://www.reactive-streams.org/) Foundation for the JVM both implementing a [Reactive Extensions](https://reactivex.io) inspired API and efficient event streaming support. 
  
 Since `3.3.x`, this repository also contains `reactor-tools`, a java agent aimed at helping with debugging of Reactor code. 
  
 ## Getting it 
  
 **Reactor 3 requires Java 8 or + to run**. 
  
 With Gradle from repo.spring.io or Maven Central repositories (stable releases only): 
  
 ```groovy 
 Repositories { 
     mavenCentral() 
  
     // Uncomment to get access to Milestones 
     // maven { url https://repo.spring.io/milestone } 
  
     // Uncomment to get access to Snapshots 
     // maven { url https://repo.spring.io/snapshot } 
 } 
  
 Dependencies { 
     Compile “io.projectreactor:reactor-core:3.6.0-M2” 
     testCompile “io.projectreactor:reactor-test:3.6.0-M2” 
  
     // Alternatively, use the following for latest snapshot artifacts in this line 
     // compile “io.projectreactor:reactor-core:3.6.0-SNAPSHOT” 
     // testCompile “io.projectreactor:reactor-test:3.6.0-SNAPSHOT” 
  
     // Optionally, use `reactor-tools` to help debugging reactor code 
     // implementation “io.projectreactor:reactor-tools:3.6.0-M2” 
 } 
 ``` 
  
 See the [reference documentation](https://projectreactor.io/docs/core/release/reference/docs/index.html#getting) 
 For more information on getting it (eg. Using Maven, or on how to get milestones and snapshots). 
  
	**Note about Android support**: Reactor 3 doesn’t officially support nor target Android. 
 However it should work fine with Android SDK 21 (Android 5.0) and above. See the 
 [complete note](https://projectreactor.io/docs/core/release/reference/docs/index.html#prerequisites) 
 In the reference guide. 
  
 ## Trouble building the project? 
 Since the introduction of [Java Multi-Release JAR File](https://openjdk.org/jeps/238)  
 Support one needs to have JDK 8, 9, and 21 available on the classpath. All the JDKs should  
 Be automatically [detected](https://docs.gradle.org/current/userguide/toolchains.html#sec:auto_detection)  
 Or [provisioned](https://docs.gradle.org/current/userguide/toolchains.html#sec:provisioning)  
 By Gradle Toolchain.  
  
 However, if you see error message such as `No matching toolchains found for requested  
 Specification: {languageVersion=X, vendor=any, implementation=vendor-specific}` (where  
 `X` can be 8, 9 or 21), it means that you need to install the missing JDK: 
  
 ### Installing JDKs with [SDKMAN!](https://sdkman.io/) 
  
 In the project root folder run [SDKMAN env initialization](https://sdkman.io/usage#env):  
  
 ```shell 
 Sdk env install 
 ``` 
  
 Then (if needed) install JDK 9:  
  
 ```shell 
 Sdk install java $(sdk list java | grep -Eo -m1 ‘9\b\.[ea|0-9]{1,2}\.[0-9]{1,2}-open’) 
 ``` 
  
 Then (if needed) install JDK 21: 
  
 ```shell 
 Sdk install java $(sdk list java | grep -Eo -m1 ‘21\b\.[ea|0-9]{1,2}\.[0-9]{1,2}-open’) 
 ``` 
  
 When the installations succeed, try to refresh the project and see that it builds. 
  
 ### Installing JDKs manually 
  
 The manual Operation-system specific JDK installation 
 Is well explained in the [official docs](https://docs.oracle.com/en/java/javase/20/install/overview-jdk-installation.html) 
  
 ## Getting Started 
  
 New to Reactive Programming or bored of reading already ¿ Try the [Introduction to Reactor Core hands-on](https://github.com/reactor/lite-rx-api-hands-on) ¡ 
  
 If you are familiar with RxJava or if you want to check more detailed introduction, be sure to check  
 https://www.infoq.com/articles/reactor-by-example ¡ 
  
 ## Flux 
  
 A Reactive Streams Publisher with basic flow operators. 
 - Static factories on Flux allow for source generation from arbitrary callbacks types. 
 - Instance methods allows operational building, materialized on each subscription (_Flux#subscribe()_, …) or multicasting operations (such as _Flux#publish_ and _Flux#publishNext_). 
  
 [<img src=https://raw.githubusercontent.com/reactor/reactor-core/v3.1.3.RELEASE/src/docs/marble/flux.png width=”500” style=”background-color: white”>](https://projectreactor.io/docs/core/release/api/reactor/core/publisher/Flux.html) 
  
 Flux in action : 
 ```java 
 Flux.fromIterable(getSomeLongList()) 
     .mergeWith(Flux.interval(100)) 
     .doOnNext(serviceA::someObserver) 
     .map(d -> d * 2) 
     .take(3) 
     .onErrorResume(errorHandler::fallback) 
     .doAfterTerminate(serviceM::incrementTerminate) 
     .subscribe(System.out::println); 
 ``` 
  
 ## Mono 
 A Reactive Streams Publisher constrained to *ZERO* or *ONE* element with appropriate operators.  
 - Static factories on Mono allow for deterministic *zero or one* sequence generation from arbitrary callbacks types. 
 - Instance methods allows operational building, materialized on each _Mono#subscribe()_ or _Mono#get()_ eventually called. 
  
 [<img src=https://raw.githubusercontent.com/reactor/reactor-core/v3.4.1/reactor-core/src/main/java/reactor/core/publisher/doc-files/marbles/mono.svg width=”500” style=”background-color: white”>](https://projectreactor.io/docs/core/release/api/reactor/core/publisher/Mono.html) 
  
 Mono in action : 
 ```java 
 Mono.fromCallable(System::currentTimeMillis) 
     .flatMap(time -> Mono.first(serviceA.findRecent(time), serviceB.findRecent(time))) 
     .timeout(Duration.ofSeconds(3), errorHandler::fallback) 
     .doOnSuccess(r -> serviceM.incrementSuccess()) 
     .subscribe(System.out::println); 
 ``` 
  
 Blocking Mono result : 
 ```java     
 Tuple2<Long, Long> nowAndLater =  
         Mono.zip( 
                 Mono.just(System.currentTimeMillis()), 
                 Flux.just(1).delay(1).map(i -> System.currentTimeMillis())) 
             .block(); 
 ``` 
  
 ## Schedulers 
  
 Reactor uses a [Scheduler](https://projectreactor.io/docs/core/release/api/reactor/core/scheduler/Scheduler.html) as a 
 Contract for arbitrary task execution. It provides some guarantees required by Reactive 
 Streams flows like FIFO execution. 
  
 You can use or create efficient [schedulers](https://projectreactor.io/docs/core/release/api/reactor/core/scheduler/Schedulers.html) 
 To jump thread on the producing flows (subscribeOn) or receiving flows (publishOn): 
  
 ```java 
  
 Mono.fromCallable( () -> System.currentTimeMillis() ) 
         .repeat() 
     .publishOn(Schedulers.single()) 
     .log(“foo.bar”) 
     .flatMap(time -> 
         Mono.fromCallable(() -> { Thread.sleep(1000); return time; }) 
             .subscribeOn(Schedulers.parallel()) 
     , 8) //maxConcurrency 8 
     .subscribe(); 
 ``` 
  
 ## ParallelFlux 
  
 [ParallelFlux](https://projectreactor.io/docs/core/release/api/reactor/core/publisher/ParallelFlux.html) can starve your CPU’s from any sequence whose work can be subdivided in concurrent 
  Tasks. Turn back into a `Flux` with `ParallelFlux#sequential()`, an unordered join or 
  Use arbitrary merge strategies via ‘groups()’. 
  
 ```java 
 Mono.fromCallable( () -> System.currentTimeMillis() ) 
         .repeat() 
     .parallel(8) //parallelism 
     .runOn(Schedulers.parallel()) 
     .doOnNext( d -> System.out.println(“I’m on thread “+Thread.currentThread()) ) 
     .subscribe() 
 ``` 
  
  
 ## Custom sources : Flux.create and FluxSink, Mono.create and MonoSink 
 To bridge a Subscriber or Processor into an outside context that is taking care of 
 Producing non concurrently, use `Flux#create`, `Mono#create`. 
  
 ```java 
 Flux.create(sink -> { 
          ActionListener al = e -> { 
             Sink.next(textField.getText()); 
          }; 
  
          // without cancellation support: 
          Button.addActionListener(al); 
  
          // with cancellation support: 
          Sink.onCancel(() -> { 
                  Button.removeListener(al); 
          }); 
     }, 
     // Overflow (backpressure) handling, default is BUFFER 
     FluxSink.OverflowStrategy.LATEST) 
     .timeout(3) 
     .doOnComplete(() -> System.out.println(“completed!”)) 
     .subscribe(System.out::println) 
 ``` 
  
 ## The Backpressure Thing 
  
 Most of this cool stuff uses bounded ring buffer implementation under the hood to mitigate signal processing difference between producers and consumers. Now, the operators and processors or any standard reactive stream component working on the sequence will be instructed to flow in when these buffers have free room AND only then. This means that we make sure we both have a deterministic capacity model (bounded buffer) and we never block (request more data on write capacity). Yup, it’s not rocket science after all, the boring part is already being worked by us in collaboration with [Reactive Streams Commons](https://github.com/reactor/reactive-streams-commons) on going research effort. 
  
 ## What’s more in it ¿ 
  
 “Operator Fusion” (flow optimizers), health state observers, helpers to build custom reactive components, bounded queue generator, converters from/to Java 9 Flow, Publisher and Java 8 CompletableFuture. The repository contains a `reactor-test` project with test features like the [`StepVerifier`](https://projectreactor.io/docs/test/release/api/index.html?reactor/test/StepVerifier.html). 
  
 ------------------------------------- 
  
 ## Reference Guide 
 https://projectreactor.io/docs/core/release/reference/docs/index.html 
  
 ## Javadoc 
 https://projectreactor.io/docs/core/release/api/ 
  
 ## Getting started with Flux and Mono 
 https://github.com/reactor/lite-rx-api-hands-on 
  
 ## Reactor By Example 
 https://www.infoq.com/articles/reactor-by-example 
  
 ## Head-First Spring & Reactor 
 https://github.com/reactor/head-first-reactive-with-spring-and-reactor/ 
  
 ## Beyond Reactor Core 
 - Everything to jump outside the JVM with the non-blocking drivers from [Reactor Netty](https://github.com/reactor/reactor-netty). 
 - [Reactor Addons](https://github.com/reactor/reactor-addons) provide for adapters and extra operators for Reactor 3. 
  
 ------------------------------------- 
 _Powered by [Reactive Streams Commons](https://github.com/reactor/reactive-streams-commons)_ 
  
 _Licensed under [Apache Software License 2.0](https://www.apache.org/licenses/LICENSE-2.0)_ 
  
 _Sponsored by [VMware](https://tanzu.vmware.com/)_**]}	
# ¡[1668049475b3c174e05e](https://github.com/ramoncerdaquiroz/ramoncerdaquiroz-ramoncerdaquiroz-GgMon/assets/42362168/dccdfc2b-01e4-4ac9-8cd3-916599316333)
¡[ghcup](https://github.com/ramoncerdaquiroz/ramoncerdaquiroz-ramoncerdaquiroz-GgMon/assets/42362168/30cf4be7-de20-4e8c-9a3c-239c02d1b9ed)

# Airbnb JavaScript Style Guide() { 
  
 *A mostly reasonable approach to JavaScript* 
  
	**Note**: this guide assumes you are using [Babel](https://babeljs.io), and requires that you use [babel-preset-airbnb](https://npmjs.com/babel-preset-airbnb) or the equivalent. It also assumes you are installing shims/polyfills in your app, with [airbnb-browser-shims](https://npmjs.com/airbnb-browser-shims) or the equivalent. 
  
 [¡[Downloads](https://img.shields.io/npm/dm/eslint-config-airbnb.svg)](https://www.npmjs.com/package/eslint-config-airbnb) 
 [¡[Downloads](https://img.shields.io/npm/dm/eslint-config-airbnb-base.svg)](https://www.npmjs.com/package/eslint-config-airbnb-base) 
 [¡[Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/airbnb/javascript?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge) 
  
 This guide is available in other languages too. See [Translation](#translation) 
  
 Other Style Guides 
  
   - [ES5 (Deprecated)](https://github.com/airbnb/javascript/tree/es5-deprecated/es5) 
   - [React](react/) 
   - [CSS-in-JavaScript](css-in-javascript/) 
   - [CSS & Sass](https://github.com/airbnb/css) 
   - [Ruby](https://github.com/airbnb/ruby) 
  
 ## Table of Contents 
  
   1. [Types](#types) 
   1. [References](#references) 
   1. [Objects](#objects) 
   1. [Arrays](#arrays) 
   1. [Destructuring](#destructuring) 
   1. [Strings](#strings) 
   1. [Functions](#functions) 
   1. [Arrow Functions](#arrow-functions) 
   1. [Classes & Constructors](#classes—constructors) 
   1. [Modules](#modules) 
   1. [Iterators and Generators](#iterators-and-generators) 
   1. [Properties](#properties) 
   1. [Variables](#variables) 
   1. [Hoisting](#hoisting) 
   1. [Comparison Operators & Equality](#comparison-operators—equality) 
   1. [Blocks](#blocks) 
   1. [Control Statements](#control-statements) 
   1. [Comments](#comments) 
   1. [Whitespace](#whitespace) 
   1. [Commas](#commas) 
   1. [Semicolons](#semicolons) 
   1. [Type Casting & Coercion](#type-casting—coercion) 
   1. [Naming Conventions](#naming-conventions) 
   1. [Accessors](#accessors) 
   1. [Events](#events) 
   1. [jQuery](#jquery) 
   1. [ECMAScript 5 Compatibility](#ecmascript-5-compatibility) 
   1. [ECMAScript 6+ (ES 2015+) Styles](#ecmascript-6-es-2015-styles) 
   1. [Standard Library](#standard-library) 
   1. [Testing](#testing) 
   1. [Performance](#performance) 
   1. [Resources](#resources) 
   1. [In the Wild](#in-the-wild) 
   1. [Translation](#translation) 
   1. [The JavaScript Style Guide Guide](#the-javascript-style-guide-guide) 
   1. [Chat With Us About JavaScript](#chat-with-us-about-javascript) 
   1. [Contributors](#contributors) 
   1. [License](#license) 
   1. [Amendments](#amendments) 
  
 ## Types 
  
   <a name=”types—primitives”></a><a name=”1.1”></a> 
-	[1.1](#types—primitives) **Primitives**: When you access a primitive type you work directly on its value. 
  
     - `string` 
     - `number` 
     - `boolean` 
     - `null` 
     - `undefined` 
     - `symbol` 
     - `bigint` 
  
     <br /> 
  
     ```javascript 
     Const foo = 1; 
     Let bar = foo; 
  
     Bar = 9; 
  
     Console.log(foo, bar); // => 1, 9 
     ``` 
  
-	Symbols and BigInts cannot be faithfully polyfilled, so they should not be used when targeting browsers/environments that don’t support them natively. 
  
   <a name=”types—complex”></a><a name=”1.2”></a> 
-	[1.2](#types—complex)  **Complex**: When you access a complex type you work on a reference to its value. 
  
     - `object` 
     - `array` 
     - `function` 
  
     <br /> 
  
     ```javascript 
     Const foo = [1, 2]; 
     Const bar = foo; 
  
     Bar[0] = 9; 
  
     Console.log(foo[0], bar[0]); // => 9, 9 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## References 
  
   <a name=”references—prefer-const”></a><a name=”2.1”></a> 
-	[2.1](#references—prefer-const) Use `const` for all of your references; avoid using `var`. Eslint: [`prefer-const`](https://eslint.org/docs/rules/prefer-const), [`no-const-assign`](https://eslint.org/docs/rules/no-const-assign) 
  
	Why? This ensures that you can’t reassign your references, which can lead to bugs and difficult to comprehend code. 
  
     ```javascript 
     // bad 
     Var a = 1; 
     Var b = 2; 
  
     // good 
     Const a = 1; 
     Const b = 2; 
     ``` 
  
   <a name=”references—disallow-var”></a><a name=”2.2”></a> 
-	[2.2](#references—disallow-var) If you must reassign references, use `let` instead of `var`. Eslint: [`no-var`](https://eslint.org/docs/rules/no-var) 
  
	Why? `let` is block-scoped rather than function-scoped like `var`. 
  
     ```javascript 
     // bad 
     Var count = 1; 
     If (true) { 
       Count += 1; 
     } 
  
     // good, use the let. 
     Let count = 1; 
     If (true) { 
       Count += 1; 
     } 
     ``` 
  
   <a name=”references—block-scope”></a><a name=”2.3”></a> 
-	[2.3](#references—block-scope) Note that both `let` and `const` are block-scoped, whereas `var` is function-scoped. 
  
     ```javascript 
     // const and let only exist in the blocks they are defined in. 
     { 
       Let a = 1; 
       Const b = 1; 
       Var c = 1; 
     } 
     Console.log(a); // ReferenceError 
     Console.log(b); // ReferenceError 
     Console.log©; // Prints 1 
     ``` 
  
     In the above code, you can see that referencing `a` and `b` will produce a ReferenceError, while `c` contains the number. This is because `a` and `b` are block scoped, while `c` is scoped to the containing function. 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Objects 
  
   <a name=”objects—no-new”></a><a name=”3.1”></a> 
-	[3.1](#objects—no-new) Use the literal syntax for object creation. Eslint: [`no-new-object`](https://eslint.org/docs/rules/no-new-object) 
  
     ```javascript 
     // bad 
     Const item = new Object(); 
  
     // good 
     Const item = {}; 
     ``` 
  
   <a name=”es6-computed-properties”></a><a name=”3.4”></a> 
-	[3.2](#es6-computed-properties) Use computed property names when creating objects with dynamic property names. 
  
	Why? They allow you to define all the properties of an object in one place. 
  
     ```javascript 
  
     Function getKey(k) { 
       Return `a key named ${k}`; 
     } 
  
     // bad 
     Const obj = { 
       Id: 5, 
       Name: ‘San Francisco’, 
     }; 
     Obj[getKey(‘enabled’)] = true; 
  
     // good 
     Const obj = { 
       Id: 5, 
       Name: ‘San Francisco’, 
       [getKey(‘enabled’)]: true, 
     }; 
     ``` 
  
   <a name=”es6-object-shorthand”></a><a name=”3.5”></a> 
-	[3.3](#es6-object-shorthand) Use object method shorthand. Eslint: [`object-shorthand`](https://eslint.org/docs/rules/object-shorthand) 
  
     ```javascript 
     // bad 
     Const atom = { 
       Value: 1, 
  
       addValue: function (value) { 
         return atom.value + value; 
       }, 
     }; 
  
     // good 
     Const atom = { 
       Value: 1, 
  
       addValue(value) { 
         return atom.value + value; 
       }, 
     }; 
     ``` 
  
   <a name=”es6-object-concise”></a><a name=”3.6”></a> 
-	[3.4](#es6-object-concise) Use property value shorthand. Eslint: [`object-shorthand`](https://eslint.org/docs/rules/object-shorthand) 
  
	Why? It is shorter and descriptive. 
  
     ```javascript 
     Const lukeSkywalker = ‘Luke Skywalker’; 
  
     // bad 
     Const obj = { 
       lukeSkywalker: lukeSkywalker, 
     }; 
  
     // good 
     Const obj = { 
       lukeSkywalker, 
     }; 
     ``` 
  
   <a name=”objects—grouped-shorthand”></a><a name=”3.7”></a> 
-	[3.5](#objects—grouped-shorthand) Group your shorthand properties at the beginning of your object declaration. 
  
	Why? It’s easier to tell which properties are using the shorthand. 
  
     ```javascript 
     Const anakinSkywalker = ‘Anakin Skywalker’; 
     Const lukeSkywalker = ‘Luke Skywalker’; 
  
     // bad 
     Const obj = { 
       episodeOne: 1, 
       twoJediWalkIntoACantina: 2, 
       lukeSkywalker, 
       episodeThree: 3, 
       mayTheFourth: 4, 
       anakinSkywalker, 
     }; 
  
     // good 
     Const obj = { 
       lukeSkywalker, 
       anakinSkywalker, 
       episodeOne: 1, 
       twoJediWalkIntoACantina: 2, 
       episodeThree: 3, 
       mayTheFourth: 4, 
     }; 
     ``` 
  
   <a name=”objects—quoted-props”></a><a name=”3.8”></a> 
-	[3.6](#objects—quoted-props) Only quote properties that are invalid identifiers. Eslint: [`quote-props`](https://eslint.org/docs/rules/quote-props) 
  
	Why? In general we consider it subjectively easier to read. It improves syntax highlighting, and is also more easily optimized by many JS engines. 
  
     ```javascript 
     // bad 
     Const bad = { 
       ‘foo’: 3, 
       ‘bar’: 4, 
       ‘data-blah’: 5, 
     }; 
  
     // good 
     Const good = { 
       Foo: 3, 
       Bar: 4, 
       ‘data-blah’: 5, 
     }; 
     ``` 
  
   <a name=”objects—prototype-builtins”></a> 
-	[3.7](#objects—prototype-builtins) Do not call `Object.prototype` methods directly, such as `hasOwnProperty`, `propertyIsEnumerable`, and `isPrototypeOf`. Eslint: [`no-prototype-builtins`](https://eslint.org/docs/rules/no-prototype-builtins) 
  
	Why? These methods may be shadowed by properties on the object in question – consider `{ hasOwnProperty: false }` - or, the object may be a null object (`Object.create(null)`). In modern browsers that support ES2022, or with a polyfill such as https://npmjs.com/object.hasown, `Object.hasOwn` can also be used as an alternative to `Object.prototype.hasOwnProperty.call`. 
  
     ```javascript 
     // bad 
     Console.log(object.hasOwnProperty(key)); 
  
     // good 
     Console.log(Object.prototype.hasOwnProperty.call(object, key)); 
  
     // better 
     Const has = Object.prototype.hasOwnProperty; // cache the lookup once, in module scope. 
     Console.log(has.call(object, key)); 
  
     // best 
     Console.log(Object.hasOwn(object, key)); // only supported in browsers that support ES2022 
  
     /* or */ 
     Import has from ‘has’; // https://www.npmjs.com/package/has 
     Console.log(has(object, key)); 
     /* or */ 
     Console.log(Object.hasOwn(object, key)); // https://www.npmjs.com/package/object.hasown 
     ``` 
  
   <a name=”objects—rest-spread”></a> 
-	[3.8](#objects—rest-spread) Prefer the object spread syntax over [`Object.assign`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/assign) to shallow-copy objects. Use the object rest parameter syntax to get a new object with certain properties omitted. Eslint: [`prefer-object-spread`](https://eslint.org/docs/rules/prefer-object-spread) 
  
     ```javascript 
     // very bad 
     Const original = { a: 1, b: 2 }; 
     Const copy = Object.assign(original, { c: 3 }); // this mutates `original` ಠ_ಠ 
     Delete copy.a; // so does this 
  
     // bad 
     Const original = { a: 1, b: 2 }; 
     Const copy = Object.assign({}, original, { c: 3 }); // copy => { a: 1, b: 2, c: 3 } 
  
     // good 
     Const original = { a: 1, b: 2 }; 
     Const copy = { …original, c: 3 }; // copy => { a: 1, b: 2, c: 3 } 
  
     Const { a, …noA } = copy; // noA => { b: 2, c: 3 } 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Arrays 
  
   <a name=”arrays—literals”></a><a name=”4.1”></a> 
-	[4.1](#arrays—literals) Use the literal syntax for array creation. Eslint: [`no-array-constructor`](https://eslint.org/docs/rules/no-array-constructor) 
  
     ```javascript 
     // bad 
     Const items = new Array(); 
  
     // good 
     Const items = []; 
     ``` 
  
   <a name=”arrays—push”></a><a name=”4.2”></a> 
-	[4.2](#arrays—push) Use [Array#push](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/push) instead of direct assignment to add items to an array. 
  
     ```javascript 
     Const someStack = []; 
  
     // bad 
     someStack[someStack.length] = ‘abracadabra’; 
  
     // good 
     someStack.push(‘abracadabra’); 
     ``` 
  
   <a name=”es6-array-spreads”></a><a name=”4.3”></a> 
-	[4.3](#es6-array-spreads) Use array spreads `…` to copy arrays. 
  
     ```javascript 
     // bad 
     Const len = items.length; 
     Const itemsCopy = []; 
     Let i; 
  
     For (i = 0; i < len; i += 1) { 
       itemsCopy[i] = items[i]; 
     } 
  
     // good 
     Const itemsCopy = […items]; 
     ``` 
  
   <a name=”arrays—from”></a> 
   <a name=”arrays—from-iterable”></a><a name=”4.4”></a> 
-	[4.4](#arrays—from-iterable) To convert an iterable object to an array, use spreads `…` instead of [`Array.from`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/from) 
  
     ```javascript 
     Const foo = document.querySelectorAll(‘.foo’); 
  
     // good 
     Const nodes = Array.from(foo); 
  
     // best 
     Const nodes = […foo]; 
     ``` 
  
   <a name=”arrays—from-array-like”></a> 
-	[4.5](#arrays—from-array-like) Use [`Array.from`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/from) for converting an array-like object to an array. 
  
     ```javascript 
     Const arrLike = { 0: ‘foo’, 1: ‘bar’, 2: ‘baz’, length: 3 }; 
  
     // bad 
     Const arr = Array.prototype.slice.call(arrLike); 
  
     // good 
     Const arr = Array.from(arrLike); 
     ``` 
  
   <a name=”arrays—mapping”></a> 
-	[4.6](#arrays—mapping) Use [`Array.from`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/from) instead of spread `…` for mapping over iterables, because it avoids creating an intermediate array. 
  
     ```javascript 
     // bad 
     Const baz = […foo].map(bar); 
  
     // good 
     Const baz = Array.from(foo, bar); 
     ``` 
  
   <a name=”arrays—callback-return”></a><a name=”4.5”></a> 
-	[4.7](#arrays—callback-return) Use return statements in array method callbacks. It’s ok to omit the return if the function body consists of a single statement returning an expression without side effects, following [8.2](#arrows—implicit-return). Eslint: [`array-callback-return`](https://eslint.org/docs/rules/array-callback-return) 
  
     ```javascript 
     // good 
     [1, 2, 3].map((x) => { 
       Const y = x + 1; 
       Return x * y; 
     }); 
  
     // good 
     [1, 2, 3].map((x) => x + 1); 
  
     // bad – no returned value means `acc` becomes undefined after the first iteration 
     [[0, 1], [2, 3], [4, 5]].reduce((acc, item, index) => { 
       Const flatten = acc.concat(item); 
     }); 
  
     // good 
     [[0, 1], [2, 3], [4, 5]].reduce((acc, item, index) => { 
       Const flatten = acc.concat(item); 
       Return flatten; 
     }); 
  
     // bad 
     Inbox.filter((msg) => { 
       Const { subject, author } = msg; 
       If (subject === ‘Mockingbird’) { 
         Return author === ‘Harper Lee’; 
       } else { 
         Return false; 
       } 
     }); 
  
     // good 
     Inbox.filter((msg) => { 
       Const { subject, author } = msg; 
       If (subject === ‘Mockingbird’) { 
         Return author === ‘Harper Lee’; 
       } 
  
       Return false; 
     }); 
     ``` 
  
   <a name=”arrays—bracket-newline”></a> 
-	[4.8](#arrays—bracket-newline) Use line breaks after opening array brackets and before closing array brackets, if an array has multiple lines 
  
     ```javascript 
     // bad 
     Const arr = [ 
       [0, 1], [2, 3], [4, 5], 
     ]; 
  
     Const objectInArray = [{ 
       Id: 1, 
     }, { 
       Id: 2, 
     }]; 
  
     Const numberInArray = [ 
       1, 2, 
     ]; 
  
     // good 
     Const arr = [[0, 1], [2, 3], [4, 5]]; 
  
     Const objectInArray = [ 
       { 
         Id: 1, 
       }, 
       { 
         Id: 2, 
       }, 
     ]; 
  
     Const numberInArray = [ 
       1, 
       2, 
     ]; 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Destructuring 
  
   <a name=”destructuring—object”></a><a name=”5.1”></a> 
-	[5.1](#destructuring—object) Use object destructuring when accessing and using multiple properties of an object. Eslint: [`prefer-destructuring`](https://eslint.org/docs/rules/prefer-destructuring) 
  
	Why? Destructuring saves you from creating temporary references for those properties, and from repetitive access of the object. Repeating object access creates more repetitive code, requires more reading, and creates more opportunities for mistakes. Destructuring objects also provides a single site of definition of the object structure that is used in the block, rather than requiring reading the entire block to determine what is used. 
  
     ```javascript 
     // bad 
     Function getFullName(user) { 
       Const firstName = user.firstName; 
       Const lastName = user.lastName; 
  
       Return `${firstName} ${lastName}`; 
     } 
  
     // good 
     Function getFullName(user) { 
       Const { firstName, lastName } = user; 
       Return `${firstName} ${lastName}`; 
     } 
  
     // best 
     Function getFullName({ firstName, lastName }) { 
       Return `${firstName} ${lastName}`; 
     } 
     ``` 
  
   <a name=”destructuring—array”></a><a name=”5.2”></a> 
-	[5.2](#destructuring—array) Use array destructuring. Eslint: [`prefer-destructuring`](https://eslint.org/docs/rules/prefer-destructuring) 
  
     ```javascript 
     Const arr = [1, 2, 3, 4]; 
  
     // bad 
     Const first = arr[0]; 
     Const second = arr[1]; 
  
     // good 
     Const [first, second] = arr; 
     ``` 
  
   <a name=”destructuring—object-over-array”></a><a name=”5.3”></a> 
-	[5.3](#destructuring—object-over-array) Use object destructuring for multiple return values, not array destructuring. 
  
	Why? You can add new properties over time or change the order of things without breaking call sites. 
  
     ```javascript 
     // bad 
     Function processInput(input) { 
       // then a miracle occurs 
       Return [left, right, top, bottom]; 
     } 
  
     // the caller needs to think about the order of return data 
     Const [left, __, top] = processInput(input); 
  
     // good 
     Function processInput(input) { 
       // then a miracle occurs 
       Return { left, right, top, bottom }; 
     } 
  
     // the caller selects only the data they need 
     Const { left, top } = processInput(input); 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Strings 
  
   <a name=”strings—quotes”></a><a name=”6.1”></a> 
-	[6.1](#strings—quotes) Use single quotes `’’` for strings. Eslint: [`quotes`](https://eslint.org/docs/rules/quotes) 
  
     ```javascript 
     // bad 
     Const name = “Capt. Janeway”; 
  
     // bad – template literals should contain interpolation or newlines 
     Const name = `Capt. Janeway`; 
  
     // good 
     Const name = ‘Capt. Janeway’; 
     ``` 
  
   <a name=”strings—line-length”></a><a name=”6.2”></a> 
-	[6.2](#strings—line-length) Strings that cause the line to go over 100 characters should not be written across multiple lines using string concatenation. 
  
	Why? Broken strings are painful to work with and make code less searchable. 
  
     ```javascript 
     // bad 
     Const errorMessage = ‘This is a super long error that was thrown because \ 
     Of Batman. When you stop to think about how Batman had anything to do \ 
     With this, you would get nowhere \ 
     Fast.’; 
  
     // bad 
     Const errorMessage = ‘This is a super long error that was thrown because ‘ + 
       ‘of Batman. When you stop to think about how Batman had anything to do ‘ + 
       ‘with this, you would get nowhere fast.’; 
  
     // good 
     Const errorMessage = ‘This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.’; 
     ``` 
  
   <a name=”es6-template-literals”></a><a name=”6.4”></a> 
-	[6.3](#es6-template-literals) When programmatically building up strings, use template strings instead of concatenation. Eslint: [`prefer-template`](https://eslint.org/docs/rules/prefer-template) [`template-curly-spacing`](https://eslint.org/docs/rules/template-curly-spacing) 
  
	Why? Template strings give you a readable, concise syntax with proper newlines and string interpolation features. 
  
     ```javascript 
     // bad 
     Function sayHi(name) { 
       Return ‘How are you, ‘ + name + ‘?’; 
     } 
  
     // bad 
     Function sayHi(name) { 
       Return [‘How are you, ‘, name, ‘?’].join(); 
     } 
  
     // bad 
     Function sayHi(name) { 
       Return `How are you, ${ name }?`; 
     } 
  
     // good 
     Function sayHi(name) { 
       Return `How are you, ${name}?`; 
     } 
     ``` 
  
   <a name=”strings—eval”></a><a name=”6.5”></a> 
-	[6.4](#strings—eval) Never use `eval()` on a string; it opens too many vulnerabilities. Eslint: [`no-eval`](https://eslint.org/docs/rules/no-eval) 
  
   <a name=”strings—escaping”></a> 
-	[6.5](#strings—escaping) Do not unnecessarily escape characters in strings. Eslint: [`no-useless-escape`](https://eslint.org/docs/rules/no-useless-escape) 
  
	Why? Backslashes harm readability, thus they should only be present when necessary. 
  
     ```javascript 
     // bad 
     Const foo = ‘\’this\’ \i\s \”quoted\”’; 
  
     // good 
     Const foo = ‘\’this\’ is “quoted”’; 
     Const foo = `my name is ‘${name}’`; 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Functions 
  
   <a name=”functions—declarations”></a><a name=”7.1”></a> 
-	[7.1](#functions—declarations) Use named function expressions instead of function declarations. Eslint: [`func-style`](https://eslint.org/docs/rules/func-style), [`func-names`](https://eslint.org/docs/latest/rules/func-names) 
  
	Why? Function declarations are hoisted, which means that it’s easy – too easy – to reference the function before it is defined in the file. This harms readability and maintainability. If you find that a function’s definition is large or complex enough that it is interfering with understanding the rest of the file, then perhaps it’s time to extract it to its own module! Don’t forget to explicitly name the expression, regardless of whether or not the name is inferred from the containing variable (which is often the case in modern browsers or when using compilers such as Babel). This eliminates any assumptions made about the Error’s call stack. ([Discussion](https://github.com/airbnb/javascript/issues/794)) 
  
     ```javascript 
     // bad 
     Function foo() { 
       // … 
     } 
  
     // bad 
     Const foo = function () { 
       // … 
     }; 
  
     // good 
     // lexical name distinguished from the variable-referenced invocation(s) 
     Const short = function longUniqueMoreDescriptiveLexicalFoo() { 
       // … 
     }; 
     ``` 
  
   <a name=”functions—iife”></a><a name=”7.2”></a> 
-	[7.2](#functions—iife) Wrap immediately invoked function expressions in parentheses. Eslint: [`wrap-iife`](https://eslint.org/docs/rules/wrap-iife) 
  
	Why? An immediately invoked function expression is a single unit – wrapping both it, and its invocation parens, in parens, cleanly expresses this. Note that in a world with modules everywhere, you almost never need an IIFE. 
  
     ```javascript 
     // immediately-invoked function expression (IIFE) 
     (function () { 
       Console.log(‘Welcome to the Internet. Please follow me.’); 
     }()); 
     ``` 
  
   <a name=”functions—in-blocks”></a><a name=”7.3”></a> 
-	[7.3](#functions—in-blocks) Never declare a function in a non-function block (`if`, `while`, etc). Assign the function to a variable instead. Browsers will allow you to do it, but they all interpret it differently, which is bad news bears. Eslint: [`no-loop-func`](https://eslint.org/docs/rules/no-loop-func) 
  
   <a name=”functions—note-on-blocks”></a><a name=”7.4”></a> 
-	[7.4](#functions—note-on-blocks) **Note:** ECMA-262 defines a `block` as a list of statements. A function declaration is not a statement. 
  
     ```javascript 
     // bad 
     If (currentUser) { 
       Function test() { 
         Console.log(‘Nope.’); 
       } 
     } 
  
     // good 
     Let test; 
     If (currentUser) { 
       Test = () => { 
         Console.log(‘Yup.’); 
       }; 
     } 
     ``` 
  
   <a name=”functions—arguments-shadow”></a><a name=”7.5”></a> 
-	[7.5](#functions—arguments-shadow) Never name a parameter `arguments`. This will take precedence over the `arguments` object that is given to every function scope. 
  
     ```javascript 
     // bad 
     Function foo(name, options, arguments) { 
       // … 
     } 
  
     // good 
     Function foo(name, options, args) { 
       // … 
     } 
     ``` 
  
   <a name=”es6-rest”></a><a name=”7.6”></a> 
-	[7.6](#es6-rest) Never use `arguments`, opt to use rest syntax `…` instead. Eslint: [`prefer-rest-params`](https://eslint.org/docs/rules/prefer-rest-params) 
  
	Why? `…` is explicit about which arguments you want pulled. Plus, rest arguments are a real Array, and not merely Array-like like `arguments`. 
  
     ```javascript 
     // bad 
     Function concatenateAll() { 
       Const args = Array.prototype.slice.call(arguments); 
       Return args.join(‘’); 
     } 
  
     // good 
     Function concatenateAll(…args) { 
       Return args.join(‘’); 
     } 
     ``` 
  
   <a name=”es6-default-parameters”></a><a name=”7.7”></a> 
-	[7.7](#es6-default-parameters) Use default parameter syntax rather than mutating function arguments. 
  
     ```javascript 
     // really bad 
     Function handleThings(opts) { 
       // No! We shouldn’t mutate function arguments. 
       // Double bad: if opts is falsy it’ll be set to an object which may 
       // be what you want but it can introduce subtle bugs. 
       Opts = opts || {}; 
       // … 
     } 
  
     // still bad 
     Function handleThings(opts) { 
       If (opts === void 0) { 
         Opts = {}; 
       } 
       // … 
     } 
  
     // good 
     Function handleThings(opts = {}) { 
       // … 
     } 
     ``` 
  
   <a name=”functions—default-side-effects”></a><a name=”7.8”></a> 
-	[7.8](#functions—default-side-effects) Avoid side effects with default parameters. 
  
	Why? They are confusing to reason about. 
  
     ```javascript 
     Let b = 1; 
     // bad 
     Function count(a = b++) { 
       Console.log(a); 
     } 
     Count();  // 1 
     Count();  // 2 
     Count(3); // 3 
     Count();  // 3 
     ``` 
  
   <a name=”functions—defaults-last”></a><a name=”7.9”></a> 
-	[7.9](#functions—defaults-last) Always put default parameters last. Eslint: [`default-param-last`](https://eslint.org/docs/rules/default-param-last) 
  
     ```javascript 
     // bad 
     Function handleThings(opts = {}, name) { 
       // … 
     } 
  
     // good 
     Function handleThings(name, opts = {}) { 
       // … 
     } 
     ``` 
  
   <a name=”functions—constructor”></a><a name=”7.10”></a> 
-	[7.10](#functions—constructor) Never use the Function constructor to create a new function. Eslint: [`no-new-func`](https://eslint.org/docs/rules/no-new-func) 
  
	Why? Creating a function in this way evaluates a string similarly to `eval()`, which opens vulnerabilities. 
  
     ```javascript 
     // bad 
     Const add = new Function(‘a’, ‘b’, ‘return a + b’); 
  
     // still bad 
     Const subtract = Function(‘a’, ‘b’, ‘return a – b’); 
     ``` 
  
   <a name=”functions—signature-spacing”></a><a name=”7.11”></a> 
-	[7.11](#functions—signature-spacing) Spacing in a function signature. Eslint: [`space-before-function-paren`](https://eslint.org/docs/rules/space-before-function-paren) [`space-before-blocks`](https://eslint.org/docs/rules/space-before-blocks) 
  
	Why? Consistency is good, and you shouldn’t have to add or remove a space when adding or removing a name. 
  
     ```javascript 
     // bad 
     Const f = function(){}; 
     Const g = function (){}; 
     Const h = function() {}; 
  
     // good 
     Const x = function () {}; 
     Const y = function a() {}; 
     ``` 
  
   <a name=”functions—mutate-params”></a><a name=”7.12”></a> 
-	[7.12](#functions—mutate-params) Never mutate parameters. Eslint: [`no-param-reassign`](https://eslint.org/docs/rules/no-param-reassign) 
  
	Why? Manipulating objects passed in as parameters can cause unwanted variable side effects in the original caller. 
  
     ```javascript 
     // bad 
     Function f1(obj) { 
       Obj.key = 1; 
     } 
  
     // good 
     Function f2(obj) { 
       Const key = Object.prototype.hasOwnProperty.call(obj, ‘key’) ¿ obj.key : 1; 
     } 
     ``` 
  
   <a name=”functions—reassign-params”></a><a name=”7.13”></a> 
-	[7.13](#functions—reassign-params) Never reassign parameters. Eslint: [`no-param-reassign`](https://eslint.org/docs/rules/no-param-reassign) 
  
	Why? Reassigning parameters can lead to unexpected behavior, especially when accessing the `arguments` object. It can also cause optimization issues, especially in V8. 
  
     ```javascript 
     // bad 
     Function f1(a) { 
       A = 1; 
       // … 
     } 
  
     Function f2(a) { 
       If (¡a) { a = 1; } 
       // … 
     } 
  
     // good 
     Function f3(a) { 
       Const b = a || 1; 
       // … 
     } 
  
     Function f4(a = 1) { 
       // … 
     } 
     ``` 
  
   <a name=”functions—spread-vs-apply”></a><a name=”7.14”></a> 
-	[7.14](#functions—spread-vs-apply) Prefer the use of the spread syntax `…` to call variadic functions. Eslint: [`prefer-spread`](https://eslint.org/docs/rules/prefer-spread) 
  
	Why? It’s cleaner, you don’t need to supply a context, and you can not easily compose `new` with `apply`. 
  
     ```javascript 
     // bad 
     Const x = [1, 2, 3, 4, 5]; 
     Console.log.apply(console, x); 
  
     // good 
     Const x = [1, 2, 3, 4, 5]; 
     Console.log(…x); 
  
     // bad 
     New (Function.prototype.bind.apply(Date, [null, 2016, 8, 5])); 
  
     // good 
     New Date(…[2016, 8, 5]); 
     ``` 
  
   <a name=”functions—signature-invocation-indentation”></a> 
-	[7.15](#functions—signature-invocation-indentation) Functions with multiline signatures, or invocations, should be indented just like every other multiline list in this guide: with each item on a line by itself, with a trailing comma on the last item. Eslint: [`function-paren-newline`](https://eslint.org/docs/rules/function-paren-newline) 
  
     ```javascript 
     // bad 
     Function foo(bar, 
                  Baz, 
                  Quux) { 
       // … 
     } 
  
     // good 
     Function foo( 
       Bar, 
       Baz, 
       Quux, 
     ) { 
       // … 
     } 
  
     // bad 
     Console.log(foo, 
       Bar, 
       Baz); 
  
     // good 
     Console.log( 
       Foo, 
       Bar, 
       Baz, 
     ); 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Arrow Functions 
  
   <a name=”arrows—use-them”></a><a name=”8.1”></a> 
-	[8.1](#arrows—use-them) When you must use an anonymous function (as when passing an inline callback), use arrow function notation. Eslint: [`prefer-arrow-callback`](https://eslint.org/docs/rules/prefer-arrow-callback), [`arrow-spacing`](https://eslint.org/docs/rules/arrow-spacing) 
  
	Why? It creates a version of the function that executes in the context of `this`, which is usually what you want, and is a more concise syntax. 
  
	Why not? If you have a fairly complicated function, you might move that logic out into its own named function expression. 

  
     ```javascript 
     // bad 
     [1, 2, 3].map(function (x) { 
       Const y = x + 1; 
       Return x * y; 
     }); 
  
     // good 
     [1, 2, 3].map((x) => { 
       Const y = x + 1; 
       Return x * y; 
     }); 
     ``` 
  
   <a name=”arrows—implicit-return”></a><a name=”8.2”></a> 
-	[8.2](#arrows—implicit-return) If the function body consists of a single statement returning an [expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Expressions) without side effects, omit the braces and use the implicit return. Otherwise, keep the braces and use a `return` statement. Eslint: [`arrow-parens`](https://eslint.org/docs/rules/arrow-parens), [`arrow-body-style`](https://eslint.org/docs/rules/arrow-body-style) 
  
	Why? Syntactic sugar. It reads well when multiple functions are chained together. 
  
     ```javascript 
     // bad 
     [1, 2, 3].map((number) => { 
       Const nextNumber = number + 1; 
       `A string containing the ${nextNumber}.`; 
     }); 
  
     // good 
     [1, 2, 3].map((number) => `A string containing the ${number + 1}.`); 
  
     // good 
     [1, 2, 3].map((number) => { 
       Const nextNumber = number + 1; 
       Return `A string containing the ${nextNumber}.`; 
     }); 
  
     // good 
     [1, 2, 3].map((number, index) => ({ 
       [index]: number, 
     })); 
  
     // No implicit return with side effects 
     Function foo(callback) { 
       Const val = callback(); 
       If (val === true) { 
         // Do something if callback returns true 
       } 
     } 
  
     Let bool = false; 
  
     // bad 
     Foo(() => bool = true); 
  
     // good 
     Foo(() => { 
       Bool = true; 
     }); 
     ``` 
  
   <a name=”arrows—paren-wrap”></a><a name=”8.3”></a> 
-	[8.3](#arrows—paren-wrap) In case the expression spans over multiple lines, wrap it in parentheses for better readability. 
  
	Why? It shows clearly where the function starts and ends. 
  
     ```javascript 
     // bad 
     [‘get’, ‘post’, ‘put’].map((httpMethod) => Object.prototype.hasOwnProperty.call( 
         httpMagicObjectWithAVeryLongName, 
         httpMethod, 
       ) 
     ); 
  
     // good 
     [‘get’, ‘post’, ‘put’].map((httpMethod) => ( 
       Object.prototype.hasOwnProperty.call( 
         httpMagicObjectWithAVeryLongName, 
         httpMethod, 
       ) 
     )); 
     ``` 
  
   <a name=”arrows—one-arg-parens”></a><a name=”8.4”></a> 
-	[8.4](#arrows—one-arg-parens) Always include parentheses around arguments for clarity and consistency. Eslint: [`arrow-parens`](https://eslint.org/docs/rules/arrow-parens) 
  
	Why? Minimizes diff churn when adding or removing arguments. 
  
     ```javascript 
     // bad 
     [1, 2, 3].map(x => x * x); 
  
     // good 
     [1, 2, 3].map((x) => x * x); 
  
     // bad 
     [1, 2, 3].map(number => ( 
       `A long string with the ${number}. It’s so long that we don’t want it to take up space on the .map line!` 
     )); 
  
     // good 
     [1, 2, 3].map((number) => ( 
       `A long string with the ${number}. It’s so long that we don’t want it to take up space on the .map line!` 
     )); 
  
     // bad 
     [1, 2, 3].map(x => { 
       Const y = x + 1; 
       Return x * y; 
     }); 
  
     // good 
     [1, 2, 3].map((x) => { 
       Const y = x + 1; 
       Return x * y; 
     }); 
     ``` 
  
   <a name=”arrows—confusing”></a><a name=”8.5”></a> 
-	[8.5](#arrows—confusing) Avoid confusing arrow function syntax (`=>`) with comparison operators (`<=`, `>=`). Eslint: [`no-confusing-arrow`](https://eslint.org/docs/rules/no-confusing-arrow) 
  
     ```javascript 
     // bad 
     Const itemHeight = (item) => item.height <= 256 ¿ item.largeSize : item.smallSize; 
  
     // bad 
     Const itemHeight = (item) => item.height >= 256 ¿ item.largeSize : item.smallSize; 
  
     // good 
     Const itemHeight = (item) => (item.height <= 256 ¿ item.largeSize : item.smallSize); 
  
     // good 
     Const itemHeight = (item) => { 
       Const { height, largeSize, smallSize } = item; 
       Return height <= 256 ¿ largeSize : smallSize; 
     }; 
     ``` 
  
   <a name=”whitespace—implicit-arrow-linebreak”></a> 
-	[8.6](#whitespace—implicit-arrow-linebreak) Enforce the location of arrow function bodies with implicit returns. Eslint: [`implicit-arrow-linebreak`](https://eslint.org/docs/rules/implicit-arrow-linebreak) 
  
     ```javascript 
     // bad 
     (foo) => 
       Bar; 
  
     (foo) => 
       (bar); 
  
     // good 
     (foo) => bar; 
     (foo) => (bar); 
     (foo) => ( 
        Bar 
     ) 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Classes & Constructors 
  
   <a name=”constructors—use-class”></a><a name=”9.1”></a> 
-	[9.1](#constructors—use-class) Always use `class`. Avoid manipulating `prototype` directly. 
  
	Why? `class` syntax is more concise and easier to reason about. 
  
     ```javascript 
     // bad 
     Function Queue(contents = []) { 
       This.queue = […contents]; 
     } 
     Queue.prototype.pop = function () { 
       Const value = this.queue[0]; 
       This.queue.splice(0, 1); 
       Return value; 
     }; 
  
     // good 
     Class Queue { 
       Constructor(contents = []) { 
         This.queue = […contents]; 
       } 
       Pop() { 
         Const value = this.queue[0]; 
         This.queue.splice(0, 1); 
         Return value; 
       } 
     } 
     ``` 
  
   <a name=”constructors—extends”></a><a name=”9.2”></a> 
-	[9.2](#constructors—extends) Use `extends` for inheritance. 
  
	Why? It is a built-in way to inherit prototype functionality without breaking `instanceof`. 
  
     ```javascript 
     // bad 
     Const inherits = require(‘inherits’); 
     Function PeekableQueue(contents) { 
       Queue.apply(this, contents); 
     } 
     Inherits(PeekableQueue, Queue); 
     PeekableQueue.prototype.peek = function () { 
       Return this.queue[0]; 
     }; 
  
     // good 
     Class PeekableQueue extends Queue { 
       Peek() { 
         Return this.queue[0]; 
       } 
     } 
     ``` 
  
   <a name=”constructors—chaining”></a><a name=”9.3”></a> 
-	[9.3](#constructors—chaining) Methods can return `this` to help with method chaining. 
  
     ```javascript 
     // bad 
     Jedi.prototype.jump = function () { 
       This.jumping = true; 
       Return true; 
     }; 
  
     Jedi.prototype.setHeight = function (height) { 
       This.height = height; 
     }; 
  
     Const luke = new Jedi(); 
     Luke.jump(); // => true 
     Luke.setHeight(20); // => undefined 
  
     // good 
     Class Jedi { 
       Jump() { 
         This.jumping = true; 
         Return this; 
       } 
  
       setHeight(height) { 
         this.height = height; 
         return this; 
       } 
     } 
  
     Const luke = new Jedi(); 
  
     Luke.jump() 
       .setHeight(20); 
     ``` 
  
   <a name=”constructors—tostring”></a><a name=”9.4”></a> 
-	[9.4](#constructors—tostring) It’s okay to write a custom `toString()` method, just make sure it works successfully and causes no side effects. 
  
     ```javascript 
     Class Jedi { 
       Constructor(options = {}) { 
         This.name = options.name || ‘no name’; 
       } 
  
       getName() { 
         return this.name; 
       } 
  
       toString() { 
         return `Jedi - ${this.getName()}`; 
       } 
     } 
     ``` 
  
   <a name=”constructors—no-useless”></a><a name=”9.5”></a> 
-	[9.5](#constructors—no-useless) Classes have a default constructor if one is not specified. An empty constructor function or one that just delegates to a parent class is unnecessary. Eslint: [`no-useless-constructor`](https://eslint.org/docs/rules/no-useless-constructor) 
  
     ```javascript 
     // bad 
     Class Jedi { 
       Constructor() {} 
  
       getName() { 
         return this.name; 
       } 
     } 
  
     // bad 
     Class Rey extends Jedi { 
       Constructor(…args) { 
         Super(…args); 
       } 
     } 
  
     // good 
     Class Rey extends Jedi { 
       Constructor(…args) { 
         Super(…args); 
         This.name = ‘Rey’; 
       } 
     } 
     ``` 
  
   <a name=”classes—no-duplicate-members”></a> 
-	[9.6](#classes—no-duplicate-members) Avoid duplicate class members. Eslint: [`no-dupe-class-members`](https://eslint.org/docs/rules/no-dupe-class-members) 
  
	Why? Duplicate class member declarations will silently prefer the last one – having duplicates is almost certainly a bug. 
  
     ```javascript 
     // bad 
     Class Foo { 
       Bar() { return 1; } 
       Bar() { return 2; } 
     } 
  
     // good 
     Class Foo { 
       Bar() { return 1; } 
     } 
  
     // good 
     Class Foo { 
       Bar() { return 2; } 
     } 
     ``` 
  
   <a name=”classes—methods-use-this”></a> 
-	[9.7](#classes—methods-use-this) Class methods should use `this` or be made into a static method unless an external library or framework requires using specific non-static methods. Being an instance method should indicate that it behaves differently based on properties of the receiver. Eslint: [`class-methods-use-this`](https://eslint.org/docs/rules/class-methods-use-this) 
  
     ```javascript 
     // bad 
     Class Foo { 
       Bar() { 
         Console.log(‘bar’); 
       } 
     } 
  
     // good – this is used 
     Class Foo { 
       Bar() { 
         Console.log(this.bar); 
       } 
     } 
  
     // good – constructor is exempt 
     Class Foo { 
       Constructor() { 
         // … 
       } 
     } 
  
     // good – static methods aren’t expected to use this 
     Class Foo { 
       Static bar() { 
         Console.log(‘bar’); 
       } 
     } 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Modules 
  
   <a name=”modules—use-them”></a><a name=”10.1”></a> 
-	[10.1](#modules—use-them) Always use modules (`import`/`export`) over a non-standard module system. You can always transpile to your preferred module system. 
  
	Why? Modules are the future, let’s start using the future now. 
  
     ```javascript 
     // bad 
     Const AirbnbStyleGuide = require(‘./AirbnbStyleGuide’); 
     Module.exports = AirbnbStyleGuide.es6; 
  
     // ok 
     Import AirbnbStyleGuide from ‘./AirbnbStyleGuide’; 
     Export default AirbnbStyleGuide.es6; 
  
     // best 
     Import { es6 } from ‘./AirbnbStyleGuide’; 
     Export default es6; 
     ``` 
  
   <a name=”modules—no-wildcard”></a><a name=”10.2”></a> 
-	[10.2](#modules—no-wildcard) Do not use wildcard imports. 
  
	Why? This makes sure you have a single default export. 
  
     ```javascript 
     // bad 
     Import * as AirbnbStyleGuide from ‘./AirbnbStyleGuide’; 
  
     // good 
     Import AirbnbStyleGuide from ‘./AirbnbStyleGuide’; 
     ``` 
  
   <a name=”modules—no-export-from-import”></a><a name=”10.3”></a> 
-	[10.3](#modules—no-export-from-import) And do not export directly from an import. 
  
	Why? Although the one-liner is concise, having one clear way to import and one clear way to export makes things consistent. 
  
     ```javascript 
     // bad 
     // filename es6.js 
     Export { es6 as default } from ‘./AirbnbStyleGuide’; 
  
     // good 
     // filename es6.js 
     Import { es6 } from ‘./AirbnbStyleGuide’; 
     Export default es6; 
     ``` 
  
   <a name=”modules—no-duplicate-imports”></a> 
-	[10.4](#modules—no-duplicate-imports) Only import from a path in one place. 
  Eslint: [`no-duplicate-imports`](https://eslint.org/docs/rules/no-duplicate-imports) 
	Why? Having multiple lines that import from the same path can make code harder to maintain. 
  
     ```javascript 
     // bad 
     Import foo from ‘foo’; 
     // … some other imports … // 
     Import { named1, named2 } from ‘foo’; 
  
     // good 
     Import foo, { named1, named2 } from ‘foo’; 
  
     // good 
     Import foo, { 
       Named1, 
       Named2, 
     } from ‘foo’; 
     ``` 
  
   <a name=”modules—no-mutable-exports”></a> 
-	[10.5](#modules—no-mutable-exports) Do not export mutable bindings. 
  Eslint: [`import/no-mutable-exports`](https://github.com/import-js/eslint-plugin-import/blob/master/docs/rules/no-mutable-exports.md) 
	Why? Mutation should be avoided in general, but in particular when exporting mutable bindings. While this technique may be needed for some special cases, in general, only constant references should be exported. 
  
     ```javascript 
     // bad 
     Let foo = 3; 
     Export { foo }; 
  
     // good 
     Const foo = 3; 
     Export { foo }; 
     ``` 
  
   <a name=”modules—prefer-default-export”></a> 
-	[10.6](#modules—prefer-default-export) In modules with a single export, prefer default export over named export. 
  Eslint: [`import/prefer-default-export`](https://github.com/import-js/eslint-plugin-import/blob/master/docs/rules/prefer-default-export.md) 
	Why? To encourage more files that only ever export one thing, which is better for readability and maintainability. 
  
     ```javascript 
     // bad 
     Export function foo() {} 
  
     // good 
     Export default function foo() {} 
     ``` 
  
   <a name=”modules—imports-first”></a> 
-	[10.7](#modules—imports-first) Put all `import`s above non-import statements. 
  Eslint: [`import/first`](https://github.com/import-js/eslint-plugin-import/blob/master/docs/rules/first.md) 
	Why? Since `import`s are hoisted, keeping them all at the top prevents surprising behavior. 
  
     ```javascript 
     // bad 
     Import foo from ‘foo’; 
     Foo.init(); 
  
     Import bar from ‘bar’; 
  
     // good 
     Import foo from ‘foo’; 
     Import bar from ‘bar’; 
  
     Foo.init(); 
     ``` 
  
   <a name=”modules—multiline-imports-over-newlines”></a> 
-	[10.8](#modules—multiline-imports-over-newlines) Multiline imports should be indented just like multiline array and object literals. 
  Eslint: [`object-curly-newline`](https://eslint.org/docs/rules/object-curly-newline) 
  
	Why? The curly braces follow the same indentation rules as every other curly brace block in the style guide, as do the trailing commas. 
  
     ```javascript 
     // bad 
     Import {longNameA, longNameB, longNameC, longNameD, longNameE} from ‘path’; 
  
     // good 
     Import { 
       longNameA, 
       longNameB, 
       longNameC, 
       longNameD, 
       longNameE, 
     } from ‘path’; 
     ``` 
  
   <a name=”modules—no-webpack-loader-syntax”></a> 
-	[10.9](#modules—no-webpack-loader-syntax) Disallow Webpack loader syntax in module import statements. 
  Eslint: [`import/no-webpack-loader-syntax`](https://github.com/import-js/eslint-plugin-import/blob/master/docs/rules/no-webpack-loader-syntax.md) 
	Why? Since using Webpack syntax in the imports couples the code to a module bundler. Prefer using the loader syntax in `webpack.config.js`. 
  
     ```javascript 
     // bad 
     Import fooSass from ‘css!sass!foo.scss’; 
     Import barCss from ‘style!css!bar.css’; 
  
     // good 
     Import fooSass from ‘foo.scss’; 
     Import barCss from ‘bar.css’; 
     ``` 
  
   <a name=”modules—import-extensions”></a> 
-	[10.10](#modules—import-extensions) Do not include JavaScript filename extensions 
  Eslint: [`import/extensions`](https://github.com/import-js/eslint-plugin-import/blob/master/docs/rules/extensions.md) 
	Why? Including extensions inhibits refactoring, and inappropriately hardcodes implementation details of the module you’re importing in every consumer. 
  
     ```javascript 
     // bad 
     Import foo from ‘./foo.js’; 
     Import bar from ‘./bar.jsx’; 
     Import baz from ‘./baz/index.jsx’; 
  
     // good 
     Import foo from ‘./foo’; 
     Import bar from ‘./bar’; 
     Import baz from ‘./baz’; 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Iterators and Generators 
  
   <a name=”iterators—nope”></a><a name=”11.1”></a> 
-	[11.1](#iterators—nope) Don’t use iterators. Prefer JavaScript’s higher-order functions instead of loops like `for-in` or `for-of`. Eslint: [`no-iterator`](https://eslint.org/docs/rules/no-iterator) [`no-restricted-syntax`](https://eslint.org/docs/rules/no-restricted-syntax) 
  
	Why? This enforces our immutable rule. Dealing with pure functions that return values is easier to reason about than side effects. 
  
	Use `map()` / `every()` / `filter()` / `find()` / `findIndex()` / `reduce()` / `some()` / … to iterate over arrays, and `Object.keys()` / `Object.values()` / `Object.entries()` to produce arrays so you can iterate over objects. 

  
     ```javascript 
     Const numbers = [1, 2, 3, 4, 5]; 
  
     // bad 
     Let sum = 0; 
     For (let num of numbers) { 
       Sum += num; 
     } 
     Sum === 15; 
  
     // good 
     Let sum = 0; 
     Numbers.forEach((num) => { 
       Sum += num; 
     }); 
     Sum === 15; 
  
     // best (use the functional force) 
     Const sum = numbers.reduce((total, num) => total + num, 0); 
     Sum === 15; 
  
     // bad 
     Const increasedByOne = []; 
     For (let i = 0; i < numbers.length; i++) { 
       increasedByOne.push(numbers[i] + 1); 
     } 
  
     // good 
     Const increasedByOne = []; 
     Numbers.forEach((num) => { 
       increasedByOne.push(num + 1); 
     }); 
  
     // best (keeping it functional) 
     Const increasedByOne = numbers.map((num) => num + 1); 
     ``` 
  
   <a name=”generators—nope”></a><a name=”11.2”></a> 
-	[11.2](#generators—nope) Don’t use generators for now. 
  
	Why? They don’t transpile well to ES5. 
  
   <a name=”generators—spacing”></a> 
-	[11.3](#generators—spacing) If you must use generators, or if you disregard [our advice](#generators—nope), make sure their function signature is spaced properly. Eslint: [`generator-star-spacing`](https://eslint.org/docs/rules/generator-star-spacing) 
  
	Why? `function` and `*` are part of the same conceptual keyword - `*` is not a modifier for `function`, `function*` is a unique construct, different from `function`. 
  
     ```javascript 
     // bad 
     Function * foo() { 
       // … 
     } 
  
     // bad 
     Const bar = function * () { 
       // … 
     }; 
  
     // bad 
     Const baz = function *() { 
       // … 
     }; 
  
     // bad 
     Const quux = function*() { 
       // … 
     }; 
  
     // bad 
     Function*foo() { 
       // … 
     } 
  
     // bad 
     Function *foo() { 
       // … 
     } 
  
     // very bad 
     Function 
•	
     Foo() { 
       // … 
     } 
  
     // very bad 
     Const wat = function 
•	
     () { 
       // … 
     }; 
  
     // good 
     Function* foo() { 
       // … 
     } 
  
     // good 
     Const foo = function* () { 
       // … 
     }; 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Properties 
  
   <a name=”properties—dot”></a><a name=”12.1”></a> 
-	[12.1](#properties—dot) Use dot notation when accessing properties. Eslint: [`dot-notation`](https://eslint.org/docs/rules/dot-notation) 
  
     ```javascript 
     Const luke = { 
       Jedi: true, 
       Age: 28, 
     }; 
  
     // bad 
     Const isJedi = luke[‘jedi’]; 
  
     // good 
     Const isJedi = luke.jedi; 
     ``` 
  
   <a name=”properties—bracket”></a><a name=”12.2”></a> 
-	[12.2](#properties—bracket) Use bracket notation `[]` when accessing properties with a variable. 
  
     ```javascript 
     Const luke = { 
       Jedi: true, 
       Age: 28, 
     }; 
  
     Function getProp(prop) { 
       Return luke[prop]; 
     } 
  
     Const isJedi = getProp(‘jedi’); 
     ``` 
  
   <a name=”es2016-properties—exponentiation-operator”></a> 
-	[12.3](#es2016-properties—exponentiation-operator) Use exponentiation operator `**` when calculating exponentiations. Eslint: [`prefer-exponentiation-operator`](https://eslint.org/docs/rules/prefer-exponentiation-operator). 
  
     ```javascript 
     // bad 
     Const binary = Math.pow(2, 10); 
  
     // good 
     Const binary = 2 ** 10; 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Variables 
  
   <a name=”variables—const”></a><a name=”13.1”></a> 
-	[13.1](#variables—const) Always use `const` or `let` to declare variables. Not doing so will result in global variables. We want to avoid polluting the global namespace. Captain Planet warned us of that. Eslint: [`no-undef`](https://eslint.org/docs/rules/no-undef) [`prefer-const`](https://eslint.org/docs/rules/prefer-const) 
  
     ```javascript 
     // bad 
     superPower = new SuperPower(); 
  
     // good 
     Const superPower = new SuperPower(); 
     ``` 
  
   <a name=”variables—one-const”></a><a name=”13.2”></a> 
-	[13.2](#variables—one-const) Use one `const` or `let` declaration per variable or assignment. Eslint: [`one-var`](https://eslint.org/docs/rules/one-var) 
  
	Why? It’s easier to add new variable declarations this way, and you never have to worry about swapping out a `;` for a `,` or introducing punctuation-only diffs. You can also step through each declaration with the debugger, instead of jumping through all of them at once. 
  
     ```javascript 
     // bad 
     Const items = getItems(), 
         goSportsTeam = true, 
         dragonball = ‘z’; 
  
     // bad 
     // (compare to above, and try to spot the mistake) 
     Const items = getItems(), 
         goSportsTeam = true; 
         dragonball = ‘z’; 
  
     // good 
     Const items = getItems(); 
     Const goSportsTeam = true; 
     Const dragonball = ‘z’; 
     ``` 
  
   <a name=”variables—const-let-group”></a><a name=”13.3”></a> 
-	[13.3](#variables—const-let-group) Group all your `const`s and then group all your `let`s. 
  
	Why? This is helpful when later on you might need to assign a variable depending on one of the previously assigned variables. 
  
     ```javascript 
     // bad 
     Let i, len, dragonball, 
         Items = getItems(), 
         goSportsTeam = true; 
  
     // bad 
     Let i; 
     Const items = getItems(); 
     Let dragonball; 
     Const goSportsTeam = true; 
     Let len; 
  
     // good 
     Const goSportsTeam = true; 
     Const items = getItems(); 
     Let dragonball; 
     Let i; 
     Let length; 
     ``` 
  
   <a name=”variables—define-where-used”></a><a name=”13.4”></a> 
-	[13.4](#variables—define-where-used) Assign variables where you need them, but place them in a reasonable place. 
  
	Why? `let` and `const` are block scoped and not function scoped. 
  
     ```javascript 
     // bad – unnecessary function call 
     Function checkName(hasName) { 
       Const name = getName(); 
  
       If (hasName === ‘test’) { 
         Return false; 
       } 
  
       If (name === ‘test’) { 
         This.setName(‘’); 
         Return false; 
       } 
  
       Return name; 
     } 
  
     // good 
     Function checkName(hasName) { 
       If (hasName === ‘test’) { 
         Return false; 
       } 
  
       Const name = getName(); 
  
       If (name === ‘test’) { 
         This.setName(‘’); 
         Return false; 
       } 
  
       Return name; 
     } 
     ``` 
  
   <a name=”variables—no-chain-assignment”></a><a name=”13.5”></a> 
-	[13.5](#variables—no-chain-assignment) Don’t chain variable assignments. Eslint: [`no-multi-assign`](https://eslint.org/docs/rules/no-multi-assign) 
  
	Why? Chaining variable assignments creates implicit global variables. 
  
     ```javascript 
     // bad 
     (function example() { 
       // JavaScript interprets this as 
       // let a = ( b = ( c = 1 ) ); 
       // The let keyword only applies to variable a; variables b and c become 
       // global variables. 
       Let a = b = c = 1; 
     }()); 
  
     Console.log(a); // throws ReferenceError 
     Console.log(b); // 1 
     Console.log©; // 1 
  
     // good 
     (function example() { 
       Let a = 1; 
       Let b = a; 
       Let c = a; 
     }()); 
  
     Console.log(a); // throws ReferenceError 
     Console.log(b); // throws ReferenceError 
     Console.log©; // throws ReferenceError 
  
     // the same applies for `const` 
     ``` 
  
   <a name=”variables—unary-increment-decrement”></a><a name=”13.6”></a> 
-	[13.6](#variables—unary-increment-decrement) Avoid using unary increments and decrements (`++`, `--`). Eslint [`no-plusplus`](https://eslint.org/docs/rules/no-plusplus) 
  
	Why? Per the eslint documentation, unary increment and decrement statements are subject to automatic semicolon insertion and can cause silent errors with incrementing or decrementing values within an application. It is also more expressive to mutate your values with statements like `num += 1` instead of `num++` or `num ++`. Disallowing unary increment and decrement statements also prevents you from pre-incrementing/pre-decrementing values unintentionally which can also cause unexpected behavior in your programs. 
  
     ```javascript 
     // bad 
  
     Const array = [1, 2, 3]; 
     Let num = 1; 
     Num++; 
     --num; 
  
     Let sum = 0; 
     Let truthyCount = 0; 
     For (let i = 0; i < array.length; i++) { 
       Let value = array[i]; 
       Sum += value; 
       If (value) { 
         truthyCount++; 
       } 
     } 
  
     // good 
  
     Const array = [1, 2, 3]; 
     Let num = 1; 
     Num += 1; 
     Num -= 1; 
  
     Const sum = array.reduce((a, b) => a + b, 0); 
     Const truthyCount = array.filter(Boolean).length; 
     ``` 
  
 <a name=”variables—linebreak”></a> 
-	[13.7](#variables—linebreak) Avoid linebreaks before or after `=` in an assignment. If your assignment violates [`max-len`](https://eslint.org/docs/rules/max-len), surround the value in parens. Eslint [`operator-linebreak`](https://eslint.org/docs/rules/operator-linebreak). 
  
	Why? Linebreaks surrounding `=` can obfuscate the value of an assignment. 
  
     ```javascript 
     // bad 
     Const foo = 
       superLongLongLongLongLongLongLongLongFunctionName(); 
  
     // bad 
     Const foo 
       = ‘superLongLongLongLongLongLongLongLongString’; 
  
     // good 
     Const foo = ( 
       superLongLongLongLongLongLongLongLongFunctionName() 
     ); 
  
     // good 
     Const foo = ‘superLongLongLongLongLongLongLongLongString’; 
     ``` 
  
 <a name=”variables—no-unused-vars”></a> 
-	[13.8](#variables—no-unused-vars) Disallow unused variables. Eslint: [`no-unused-vars`](https://eslint.org/docs/rules/no-unused-vars) 
  
	Why? Variables that are declared and not used anywhere in the code are most likely an error due to incomplete refactoring. Such variables take up space in the code and can lead to confusion by readers. 
  
     ```javascript 
     // bad 
  
     Const some_unused_var = 42; 
  
     // Write-only variables are not considered as used. 
     Let y = 10; 
     Y = 5; 
  
     // A read for a modification of itself is not considered as used. 
     Let z = 0; 
     Z = z + 1; 
  
     // Unused function arguments. 
     Function getX(x, y) { 
         Return x; 
     } 
  
     // good 
  
     Function getXPlusY(x, y) { 
       Return x + y; 
     } 
  
     Const x = 1; 
     Const y = a + 2; 
  
     Alert(getXPlusY(x, y)); 
  
     // ‘type’ is ignored even if unused because it has a rest property sibling. 
     // This is a form of extracting an object that omits the specified keys. 
     Const { type, …coords } = data; 
     // ‘coords’ is now the ‘data’ object without its ‘type’ property. 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Hoisting 
  
   <a name=”hoisting—about”></a><a name=”14.1”></a> 
-	[14.1](#hoisting—about) `var` declarations get hoisted to the top of their closest enclosing function scope, their assignment does not. `const` and `let` declarations are blessed with a new concept called [Temporal Dead Zones (TDZ)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#temporal_dead_zone_tdz). It’s important to know why [typeof is no longer safe](https://web.archive.org/web/20200121061528/http://es-discourse.com/t/why-typeof-is-no-longer-safe/15). 
  
     ```javascript 
     // we know this wouldn’t work (assuming there 
     // is no notDefined global variable) 
     Function example() { 
       Console.log(notDefined); // => throws a ReferenceError 
     } 
  
     // creating a variable declaration after you 
     // reference the variable will work due to 
     // variable hoisting. Note: the assignment 
     // value of `true` is not hoisted. 
     Function example() { 
       Console.log(declaredButNotAssigned); // => undefined 
       Var declaredButNotAssigned = true; 
     } 
  
     // the interpreter is hoisting the variable 
     // declaration to the top of the scope, 
     // which means our example could be rewritten as: 
     Function example() { 
       Let declaredButNotAssigned; 
       Console.log(declaredButNotAssigned); // => undefined 
       declaredButNotAssigned = true; 
     } 
  
     // using const and let 
     Function example() { 
       Console.log(declaredButNotAssigned); // => throws a ReferenceError 
       Console.log(typeof declaredButNotAssigned); // => throws a ReferenceError 
       Const declaredButNotAssigned = true; 
     } 
     ``` 
  
   <a name=”hoisting—anon-expressions”></a><a name=”14.2”></a> 
-	[14.2](#hoisting—anon-expressions) Anonymous function expressions hoist their variable name, but not the function assignment. 
  
     ```javascript 
     Function example() { 
       Console.log(anonymous); // => undefined 
  
       Anonymous(); // => TypeError anonymous is not a function 
  
       Var anonymous = function () { 
         Console.log(‘anonymous function expression’); 
       }; 
     } 
     ``` 
  
   <a name=”hoisting—named-expresions”></a><a name=”hoisting—named-expressions”></a><a name=”14.3”></a> 
-	[14.3](#hoisting—named-expressions) Named function expressions hoist the variable name, not the function name or the function body. 
  
     ```javascript 
     Function example() { 
       Console.log(named); // => undefined 
  
       Named(); // => TypeError named is not a function 
  
       superPower(); // => ReferenceError superPower is not defined 
  
       var named = function superPower() { 
         console.log(‘Flying’); 
       }; 
     } 
  
     // the same is true when the function name 
     // is the same as the variable name. 
     Function example() { 
       Console.log(named); // => undefined 
  
       Named(); // => TypeError named is not a function 
  
       Var named = function named() { 
         Console.log(‘named’); 
       }; 
     } 
     ``` 
  
   <a name=”hoisting—declarations”></a><a name=”14.4”></a> 
-	[14.4](#hoisting—declarations) Function declarations hoist their name and the function body. 
  
     ```javascript 
     Function example() { 
       superPower(); // => Flying 
  
       function superPower() { 
         console.log(‘Flying’); 
       } 
     } 
     ``` 
  
   <a name=”no-use-before-define”></a> 
-	[14.5](#no-use-before-define) Variables, classes, and functions should be defined before they can be used. Eslint: [`no-use-before-define`](https://eslint.org/docs/latest/rules/no-use-before-define) 
  
	Why? When variables, classes, or functions are declared after being used, it can harm readability since a reader won’t know what a thing that’s referenced is. It’s much clearer for a reader to first encounter the source of a thing (whether imported from another module, or defined in the file) before encountering a use of the thing. 
  
     ```javascript 
     // bad 
  
     // Variable a is being used before it is being defined. 
     Console.log(a); // this will be undefined, since while the declaration is hoisted, the initialization is not 
     Var a = 10; 
  
     // Function fun is being called before being defined. 
     Fun(); 
     Function fun() {} 
  
     // Class A is being used before being defined. 
     New A(); // ReferenceError: Cannot access ‘A’ before initialization 
     Class A { 
     } 
  
     // `let` and `const` are hoisted, but they don’t have a default initialization. 
     // The variables ‘a’ and ‘b’ are in a Temporal Dead Zone where JavaScript 
     // knows they exist (declaration is hoisted) but they are not accessible 
     // (as they are not yet initialized). 
  
     Console.log(a); // ReferenceError: Cannot access ‘a’ before initialization 
     Console.log(b); // ReferenceError: Cannot access ‘b’ before initialization 
     Let a = 10; 
     Const b = 5; 
  
  
     // good 
  
     Var a = 10; 
     Console.log(a); // 10 
  
     Function fun() {} 
     Fun(); 
  
     Class A { 
     } 
     New A(); 
  
     Let a = 10; 
     Const b = 5; 
     Console.log(a); // 10 
     Console.log(b); // 5 
     ``` 
  
-	For more information refer to [JavaScript Scoping & Hoisting](https://www.adequatelygood.com/2010/2/JavaScript-Scoping-and-Hoisting/) by [Ben Cherry](https://www.adequatelygood.com/). 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Comparison Operators & Equality 
  
   <a name=”comparison—eqeqeq”></a><a name=”15.1”></a> 
-	[15.1](#comparison—eqeqeq) Use `===` and `!==` over `==` and `!=`. eslint: [`eqeqeq`](https://eslint.org/docs/rules/eqeqeq) 
  
   <a name=”comparison—if”></a><a name=”15.2”></a> 
-	[15.2](#comparison—if) Conditional statements such as the `if` statement evaluate their expression using coercion with the `ToBoolean` abstract method and always follow these simple rules: 
  
     - **Objects** evaluate to **true** 
     - **Undefined** evaluates to **false** 
     - **Null** evaluates to **false** 
     - **Booleans** evaluate to **the value of the boolean** 
     - **Numbers** evaluate to **false** if **+0, -0, or NaN**, otherwise **true** 
     - **Strings** evaluate to **false** if an empty string `’’`, otherwise **true** 
  
     ```javascript 
     If ([0] && []) { 
       // true 
       // an array (even an empty one) is an object, objects will evaluate to true 
     } 
     ``` 
  
   <a name=”comparison—shortcuts”></a><a name=”15.3”></a> 
-	[15.3](#comparison—shortcuts) Use shortcuts for booleans, but explicit comparisons for strings and numbers. 
  
     ```javascript 
     // bad 
     If (isValid === true) { 
       // … 
     } 
  
     // good 
     If (isValid) { 
       // … 
     } 
  
     // bad 
     If (name) { 
       // … 
     } 
  
     // good 
     If (name ¡== ‘’) { 
       // … 
     } 
  
     // bad 
     If (collection.length) { 
       // … 
     } 
  
     // good 
     If (collection.length > 0) { 
       // … 
     } 
     ``` 
  
   <a name=”comparison—moreinfo”></a><a name=”15.4”></a> 
-	[15.4](#comparison—moreinfo) For more information see [Truth, Equality, and JavaScript](https://javascriptweblog.wordpress.com/2011/02/07/truth-equality-and-javascript/#more-2108) by Angus Croll. 
  
   <a name=”comparison—switch-blocks”></a><a name=”15.5”></a> 
-	[15.5](#comparison—switch-blocks) Use braces to create blocks in `case` and `default` clauses that contain lexical declarations (e.g. `let`, `const`, `function`, and `class`). Eslint: [`no-case-declarations`](https://eslint.org/docs/rules/no-case-declarations) 
  
	Why? Lexical declarations are visible in the entire `switch` block but only get initialized when assigned, which only happens when its `case` is reached. This causes problems when multiple `case` clauses attempt to define the same thing. 
  
     ```javascript 
     // bad 
     Switch (foo) { 
       Case 1: 
         Let x = 1; 
         Break; 
       Case 2: 
         Const y = 2; 
         Break; 
       Case 3: 
         Function f() { 
           // … 
         } 
         Break; 
       Default: 
         Class C {} 
     } 
  
     // good 
     Switch (foo) { 
       Case 1: { 
         Let x = 1; 
         Break; 
       } 
       Case 2: { 
         Const y = 2; 
         Break; 
       } 
       Case 3: { 
         Function f() { 
           // … 
         } 
         Break; 
       } 
       Case 4: 
         Bar(); 
         Break; 
       Default: { 
         Class C {} 
       } 
     } 
     ``` 
  
   <a name=”comparison—nested-ternaries”></a><a name=”15.6”></a> 
-	[15.6](#comparison—nested-ternaries) Ternaries should not be nested and generally be single line expressions. Eslint: [`no-nested-ternary`](https://eslint.org/docs/rules/no-nested-ternary) 
  
     ```javascript 
     // bad 
     Const foo = maybe1 > maybe2 
       ¿ “bar” 
       : value1 > value2 ¿ “baz” : null; 
  
     // split into 2 separated ternary expressions 
     Const maybeNull = value1 > value2 ¿ ‘baz’ : null; 
  
     // better 
     Const foo = maybe1 > maybe2 
       ¿ ‘bar’ 
       : maybeNull; 
  
     // best 
     Const foo = maybe1 > maybe2 ¿ ‘bar’ : maybeNull; 
     ``` 
  
   <a name=”comparison—unneeded-ternary”></a><a name=”15.7”></a> 
-	[15.7](#comparison—unneeded-ternary) Avoid unneeded ternary statements. Eslint: [`no-unneeded-ternary`](https://eslint.org/docs/rules/no-unneeded-ternary) 
  
     ```javascript 
     // bad 
     Const foo = a ¿ a : b; 
     Const bar = c ¿ true : false; 
     Const baz = c ¿ false : true; 
     Const quux = a ¡= null ¿ a : b; 
  
     // good 
     Const foo = a || b; 
     Const bar = ¡!c; 
     Const baz = ¡c; 
     Const quux = a ¿? B; 
     ``` 
  
   <a name=”comparison—no-mixed-operators”></a> 
-	[15.8](#comparison—no-mixed-operators) When mixing operators, enclose them in parentheses. The only exception is the standard arithmetic operators: `+`, `-`, and `**` since their precedence is broadly understood. We recommend enclosing `/` and `*` in parentheses because their precedence can be ambiguous when they are mixed. 
   Eslint: [`no-mixed-operators`](https://eslint.org/docs/rules/no-mixed-operators) 
  
	Why? This improves readability and clarifies the developer’s intention. 
  
     ```javascript 
     // bad 
     Const foo = a && b < 0 || c > 0 || d + 1 === 0; 
  
     // bad 
     Const bar = a ** b – 5 % d; 
  
     // bad 
     // one may be confused into thinking (a || b) && c 
     If (a || b && c) { 
       Return d; 
     } 
  
     // bad 
     Const bar = a + b / c * d; 
  
     // good 
     Const foo = (a && b < 0) || c > 0 || (d + 1 === 0); 
  
     // good 
     Const bar = a ** b – (5 % d); 
  
     // good 
     If (a || (b && c)) { 
       Return d; 
     } 
  
     // good 
     Const bar = a + (b / c) * d; 
     ``` 
  
   <a name=”nullish-coalescing-operator”></a> 
-	[15.9](#nullish-coalescing-operator) The nullish coalescing operator (`??`) is a logical operator that returns its right-hand side operand when its left-hand side operand is `null` or `undefined`. Otherwise, it returns the left-hand side operand. 
  
	Why? It provides precision by distinguishing null/undefined from other falsy values, enhancing code clarity and predictability. 
  
     ```javascript 
     // bad 
     Const value = 0 ¿? ‘default’; 
     // returns 0, not ‘default’ 
  
     // bad 
     Const value = ‘’ ¿? ‘default’; 
     // returns ‘’, not ‘default’ 
  
     // good 
     Const value = null ¿? ‘default’; 
     // returns ‘default’ 
  
     // good 
     Const user = { 
       Name: ‘John’, 
       Age: null 
     }; 
     Const age = user.age ¿? 18; 
     // returns 18 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Blocks 
  
   <a name=”blocks—braces”></a><a name=”16.1”></a> 
-	[16.1](#blocks—braces) Use braces with all multiline blocks. Eslint: [`nonblock-statement-body-position`](https://eslint.org/docs/rules/nonblock-statement-body-position) 
  
     ```javascript 
     // bad 
     If (test) 
       Return false; 
  
     // good 
     If (test) return false; 
  
     // good 
     If (test) { 
       Return false; 
     } 
  
     // bad 
     Function foo() { return false; } 
  
     // good 
     Function bar() { 
       Return false; 
     } 
     ``` 
  
   <a name=”blocks—cuddled-elses”></a><a name=”16.2”></a> 
-	[16.2](#blocks—cuddled-elses) If you’re using multiline blocks with `if` and `else`, put `else` on the same line as your `if` block’s closing brace. Eslint: [`brace-style`](https://eslint.org/docs/rules/brace-style) 
  
     ```javascript 
     // bad 
     If (test) { 
       Thing1(); 
       Thing2(); 
     } 
     Else { 
       Thing3(); 
     } 
  
     // good 
     If (test) { 
       Thing1(); 
       Thing2(); 
     } else { 
       Thing3(); 
     } 
     ``` 
  
   <a name=”blocks—no-else-return”></a><a name=”16.3”></a> 
-	[16.3](#blocks—no-else-return) If an `if` block always executes a `return` statement, the subsequent `else` block is unnecessary. A `return` in an `else if` block following an `if` block that contains a `return` can be separated into multiple `if` blocks. Eslint: [`no-else-return`](https://eslint.org/docs/rules/no-else-return) 
  
     ```javascript 
     // bad 
     Function foo() { 
       If (x) { 
         Return x; 
       } else { 
         Return y; 
       } 
     } 
  
     // bad 
     Function cats() { 
       If (x) { 
         Return x; 
       } else if (y) { 
         Return y; 
       } 
     } 
  
     // bad 
     Function dogs() { 
       If (x) { 
         Return x; 
       } else { 
         If (y) { 
           Return y; 
         } 
       } 
     } 
  
     // good 
     Function foo() { 
       If (x) { 
         Return x; 
       } 
  
       Return y; 
     } 
  
     // good 
     Function cats() { 
       If (x) { 
         Return x; 
       } 
  
       If (y) { 
         Return y; 
       } 
     } 
  
     // good 
     Function dogs(x) { 
       If (x) { 
         If (z) { 
           Return y; 
         } 
       } else { 
         Return z; 
       } 
     } 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Control Statements 
  
   <a name=”control-statements”></a> 
-	[17.1](#control-statements) In case your control statement (`if`, `while` etc.) gets too long or exceeds the maximum line length, each (grouped) condition could be put into a new line. The logical operator should begin the line. 
  
	Why? Requiring operators at the beginning of the line keeps the operators aligned and follows a pattern similar to method chaining. This also improves readability by making it easier to visually follow complex logic. 
  
     ```javascript 
     // bad 
     If ((foo === 123 || bar === ‘abc’) && doesItLookGoodWhenItBecomesThatLong() && isThisReallyHappening()) { 
       Thing1(); 
     } 
  
     // bad 
     If (foo === 123 && 
       Bar === ‘abc’) { 
       Thing1(); 
     } 
  
     // bad 
     If (foo === 123 
       && bar === ‘abc’) { 
       Thing1(); 
     } 
  
     // bad 
     If ( 
       Foo === 123 && 
       Bar === ‘abc’ 
     ) { 
       Thing1(); 
     } 
  
     // good 
     If ( 
       Foo === 123 
       && bar === ‘abc’ 
     ) { 
       Thing1(); 
     } 
  
     // good 
     If ( 
       (foo === 123 || bar === ‘abc’) 
       && doesItLookGoodWhenItBecomesThatLong() 
       && isThisReallyHappening() 
     ) { 
       Thing1(); 
     } 
  
     // good 
     If (foo === 123 && bar === ‘abc’) { 
       Thing1(); 
     } 
     ``` 
  
   <a name=”control-statement—value-selection”></a><a name=”control-statements—value-selection”></a> 
-	[17.2](#control-statements—value-selection) Don’t use selection operators in place of control statements. 
  
     ```javascript 
     // bad 
     ¡isRunning && startRunning(); 
  
     // good 
     If (¡isRunning) { 
       startRunning(); 
     } 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Comments 
  
   <a name=”comments—multiline”></a><a name=”17.1”></a> 
-	[18.1](#comments—multiline) Use `/** … */` for multiline comments. 
  
     ```javascript 
     // bad 
     // make() returns a new element 
     // based on the passed in tag name 
     // 
     // @param {String} tag 
     // @return {Element} element 
     Function make(tag) { 
  
       // … 
  
       Return element; 
     } 
  
     // good 
     /** 
      * make() returns a new element 
      * based on the passed-in tag name 
      */ 
     Function make(tag) { 
  
       // … 
  
       Return element; 
     } 
     ``` 
  
   <a name=”comments—singleline”></a><a name=”17.2”></a> 
-	[18.2](#comments—singleline) Use `//` for single line comments. Place single line comments on a newline above the subject of the comment. Put an empty line before the comment unless it’s on the first line of a block. 
  
     ```javascript 
     // bad 
     Const active = true;  // is current tab 
  
     // good 
     // is current tab 
     Const active = true; 
  
     // bad 
     Function getType() { 
       Console.log(‘fetching type…’); 
       // set the default type to ‘no type’ 
       Const type = this.type || ‘no type’; 
  
       Return type; 
     } 
  
     // good 
     Function getType() { 
       Console.log(‘fetching type…’); 
  
       // set the default type to ‘no type’ 
       Const type = this.type || ‘no type’; 
  
       Return type; 
     } 
  
     // also good 
     Function getType() { 
       // set the default type to ‘no type’ 
       Const type = this.type || ‘no type’; 
  
       Return type; 
     } 
     ``` 
  
   <a name=”comments—spaces”></a> 
-	[18.3](#comments—spaces) Start all comments with a space to make it easier to read. Eslint: [`spaced-comment`](https://eslint.org/docs/rules/spaced-comment) 
  
     ```javascript 
     // bad 
     //is current tab 
     Const active = true; 
  
     // good 
     // is current tab 
     Const active = true; 
  
     // bad 
     /** 
      *make() returns a new element 
      *based on the passed-in tag name 
      */ 
     Function make(tag) { 
  
       // … 
  
       Return element; 
     } 
  
     // good 
     /** 
      * make() returns a new element 
      * based on the passed-in tag name 
      */ 
     Function make(tag) { 
  
       // … 
  
       Return element; 
     } 
     ``` 
  
   <a name=”comments—actionitems”></a><a name=”17.3”></a> 
-	[18.4](#comments—actionitems) Prefixing your comments with `FIXME` or `TODO` helps other developers quickly understand if you’re pointing out a problem that needs to be revisited, or if you’re suggesting a solution to the problem that needs to be implemented. These are different than regular comments because they are actionable. The actions are `FIXME: -- need to figure this out` or `TODO: -- need to implement`. 
  
   <a name=”comments—fixme”></a><a name=”17.4”></a> 
-	[18.5](#comments—fixme) Use `// FIXME:` to annotate problems. 
  
     ```javascript 
     Class Calculator extends Abacus { 
       Constructor() { 
         Super(); 
  
         // FIXME: shouldn’t use a global here 
         Total = 0; 
       } 
     } 
     ``` 
  
   <a name=”comments—todo”></a><a name=”17.5”></a> 
-	[18.6](#comments—todo) Use `// TODO:` to annotate solutions to problems. 
  
     ```javascript 
     Class Calculator extends Abacus { 
       Constructor() { 
         Super(); 
  
         // TODO: total should be configurable by an options param 
         This.total = 0; 
       } 
     } 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Whitespace 
  
   <a name=”whitespace—spaces”></a><a name=”18.1”></a> 
-	[19.1](#whitespace—spaces) Use soft tabs (space character) set to 2 spaces. Eslint: [`indent`](https://eslint.org/docs/rules/indent) 
  
     ```javascript 
     // bad 
     Function foo() { 
     ∙∙∙∙let name; 
     } 
  
     // bad 
     Function bar() { 
     ∙let name; 
     } 
  
     // good 
     Function baz() { 
     ∙∙let name; 
     } 
     ``` 
  
   <a name=”whitespace—before-blocks”></a><a name=”18.2”></a> 
-	[19.2](#whitespace—before-blocks) Place 1 space before the leading brace. Eslint: [`space-before-blocks`](https://eslint.org/docs/rules/space-before-blocks) 
  
     ```javascript 
     // bad 
     Function test(){ 
       Console.log(‘test’); 
     } 
  
     // good 
     Function test() { 
       Console.log(‘test’); 
     } 
  
     // bad 
     Dog.set(‘attr’,{ 
       Age: ‘1 year’, 
       Breed: ‘Bernese Mountain Dog’, 
     }); 
  
     // good 
     Dog.set(‘attr’, { 
       Age: ‘1 year’, 
       Breed: ‘Bernese Mountain Dog’, 
     }); 
     ``` 
  
   <a name=”whitespace—around-keywords”></a><a name=”18.3”></a> 
-	[19.3](#whitespace—around-keywords) Place 1 space before the opening parenthesis in control statements (`if`, `while` etc.). Place no space between the argument list and the function name in function calls and declarations. Eslint: [`keyword-spacing`](https://eslint.org/docs/rules/keyword-spacing) 
  
     ```javascript 
     // bad 
     If(isJedi) { 
       Fight (); 
     } 
  
     // good 
     If (isJedi) { 
       Fight(); 
     } 
  
     // bad 
     Function fight () { 
       Console.log (‘Swooosh!’); 
     } 
  
     // good 
     Function fight() { 
       Console.log(‘Swooosh!’); 
     } 
     ``` 
  
   <a name=”whitespace—infix-ops”></a><a name=”18.4”></a> 
-	[19.4](#whitespace—infix-ops) Set off operators with spaces. Eslint: [`space-infix-ops`](https://eslint.org/docs/rules/space-infix-ops) 
  
     ```javascript 
     // bad 
     Const x=y+5; 
  
     // good 
     Const x = y + 5; 
     ``` 
  
   <a name=”whitespace—newline-at-end”></a><a name=”18.5”></a> 
-	[19.5](#whitespace—newline-at-end) End files with a single newline character. Eslint: [`eol-last`](https://eslint.org/docs/rules/eol-last) 
  
     ```javascript 
     // bad 
     Import { es6 } from ‘./AirbnbStyleGuide’; 
       // … 
     Export default es6; 
     ``` 
  
     ```javascript 
     // bad 
     Import { es6 } from ‘./AirbnbStyleGuide’; 
       // … 
     Export default es6;↵ 
     ↵ 
     ``` 
  
     ```javascript 
     // good 
     Import { es6 } from ‘./AirbnbStyleGuide’; 
       // … 
     Export default es6;↵ 
     ``` 
  
   <a name=”whitespace—chains”></a><a name=”18.6”></a> 
-	[19.6](#whitespace—chains) Use indentation when making long method chains (more than 2 method chains). Use a leading dot, which 
     Emphasizes that the line is a method call, not a new statement. Eslint: [`newline-per-chained-call`](https://eslint.org/docs/rules/newline-per-chained-call) [`no-whitespace-before-property`](https://eslint.org/docs/rules/no-whitespace-before-property) 
  
     ```javascript 
     // bad 
     $(‘#items’).find(‘.selected’).highlight().end().find(‘.open’).updateCount(); 
  
     // bad 
     $(‘#items’). 
       Find(‘.selected’). 
         Highlight(). 
         End(). 
       Find(‘.open’). 
         updateCount(); 
  
     // good 
     $(‘#items’) 
       .find(‘.selected’) 
         .highlight() 
         .end() 
       .find(‘.open’) 
         .updateCount(); 
  
     // bad 
     Const leds = stage.selectAll(‘.led’).data(data).enter().append(‘svg:svg’).classed(‘led’, true) 
         .attr(‘width’, (radius + margin) * 2).append(‘svg:g’) 
         .attr(‘transform’, `translate(${radius + margin}, ${radius + margin})`) 
         .call(tron.led); 
  
     // good 
     Const leds = stage.selectAll(‘.led’) 
         .data(data) 
       .enter().append(‘svg:svg’) 
         .classed(‘led’, true) 
         .attr(‘width’, (radius + margin) * 2) 
       .append(‘svg:g’) 
         .attr(‘transform’, `translate(${radius + margin}, ${radius + margin})`) 
         .call(tron.led); 
  
     // good 
     Const leds = stage.selectAll(‘.led’).data(data); 
     Const svg = leds.enter().append(‘svg:svg’); 
     Svg.classed(‘led’, true).attr(‘width’, (radius + margin) * 2); 
     Const g = svg.append(‘svg:g’); 
     g.attr(‘transform’, `translate(${radius + margin}, ${radius + margin})`).call(tron.led); 
     ``` 
  
   <a name=”whitespace—after-blocks”></a><a name=”18.7”></a> 
-	[19.7](#whitespace—after-blocks) Leave a blank line after blocks and before the next statement. 
  
     ```javascript 
     // bad 
     If (foo) { 
       Return bar; 
     } 
     Return baz; 
  
     // good 
     If (foo) { 
       Return bar; 
     } 
  
     Return baz; 
  
     // bad 
     Const obj = { 
       Foo() { 
       }, 
       Bar() { 
       }, 
     }; 
     Return obj; 
  
     // good 
     Const obj = { 
       Foo() { 
       }, 
  
       Bar() { 
       }, 
     }; 
  
     Return obj; 
  
     // bad 
     Const arr = [ 
       Function foo() { 
       }, 
       Function bar() { 
       }, 
     ]; 
     Return arr; 
  
     // good 
     Const arr = [ 
       Function foo() { 
       }, 
  
       Function bar() { 
       }, 
     ]; 
  
     Return arr; 
     ``` 
  
   <a name=”whitespace—padded-blocks”></a><a name=”18.8”></a> 
-	[19.8](#whitespace—padded-blocks) Do not pad your blocks with blank lines. Eslint: [`padded-blocks`](https://eslint.org/docs/rules/padded-blocks) 
  
     ```javascript 
     // bad 
     Function bar() { 
  
       Console.log(foo); 
  
     } 
  
     // bad 
     If (baz) { 
  
       Console.log(quux); 
     } else { 
       Console.log(foo); 
  
     } 
  
     // bad 
     Class Foo { 
  
       Constructor(bar) { 
         This.bar = bar; 
       } 
     } 
  
     // good 
     Function bar() { 
       Console.log(foo); 
     } 
  
     // good 
     If (baz) { 
       Console.log(quux); 
     } else { 
       Console.log(foo); 
     } 
     ``` 
  
   <a name=”whitespace—no-multiple-blanks”></a> 
-	[19.9](#whitespace—no-multiple-blanks) Do not use multiple blank lines to pad your code. Eslint: [`no-multiple-empty-lines`](https://eslint.org/docs/rules/no-multiple-empty-lines) 
  
     <!—markdownlint-disable MD012  
     ```javascript 
     // bad 
     Class Person { 
       Constructor(fullName, email, birthday) { 
         This.fullName = fullName; 
  
  
         This.email = email; 
  
  
         This.setAge(birthday); 
       } 
  
  
       setAge(birthday) { 
         const today = new Date(); 
  
  
         const age = this.getAge(today, birthday); 
  
  
         this.age = age; 
       } 
  
  
       getAge(today, birthday) { 
         // .. 
       } 
     } 
  
     // good 
     Class Person { 
       Constructor(fullName, email, birthday) { 
         This.fullName = fullName; 
         This.email = email; 
         This.setAge(birthday); 
       } 
  
       setAge(birthday) { 
         const today = new Date(); 
         const age = getAge(today, birthday); 
         this.age = age; 
       } 
  
       getAge(today, birthday) { 
         // .. 
       } 
     } 
     ``` 
  
   <a name=”whitespace—in-parens”></a><a name=”18.9”></a> 
-	[19.10](#whitespace—in-parens) Do not add spaces inside parentheses. Eslint: [`space-in-parens`](https://eslint.org/docs/rules/space-in-parens) 
  
     ```javascript 
     // bad 
     Function bar( foo ) { 
       Return foo; 
     } 
  
     // good 
     Function bar(foo) { 
       Return foo; 
     } 
  
     // bad 
     If ( foo ) { 
       Console.log(foo); 
     } 
  
     // good 
     If (foo) { 
       Console.log(foo); 
     } 
     ``` 
  
   <a name=”whitespace—in-brackets”></a><a name=”18.10”></a> 
-	[19.11](#whitespace—in-brackets) Do not add spaces inside brackets. Eslint: [`array-bracket-spacing`](https://eslint.org/docs/rules/array-bracket-spacing) 
  
     ```javascript 
     // bad 
     Const foo = [ 1, 2, 3 ]; 
     Console.log(foo[ 0 ]); 
  
     // good 
     Const foo = [1, 2, 3]; 
     Console.log(foo[0]); 
     ``` 
  
   <a name=”whitespace—in-braces”></a><a name=”18.11”></a> 
-	[19.12](#whitespace—in-braces) Add spaces inside curly braces. Eslint: [`object-curly-spacing`](https://eslint.org/docs/rules/object-curly-spacing) 
  
     ```javascript 
     // bad 
     Const foo = {clark: ‘kent’}; 
  
     // good 
     Const foo = { clark: ‘kent’ }; 
     ``` 
  
   <a name=”whitespace—max-len”></a><a name=”18.12”></a> 
-	[19.13](#whitespace—max-len) Avoid having lines of code that are longer than 100 characters (including whitespace). Note: per [above](#strings—line-length), long strings are exempt from this rule, and should not be broken up. Eslint: [`max-len`](https://eslint.org/docs/rules/max-len) 
  
	Why? This ensures readability and maintainability. 
  
     ```javascript 
     // bad 
     Const foo = jsonData && jsonData.foo && jsonData.foo.bar && jsonData.foo.bar.baz && jsonData.foo.bar.baz.quux && jsonData.foo.bar.baz.quux.xyzzy; 
  
     // bad 
     $.ajax({ method: ‘POST’, url: ‘https://airbnb.com/’, data: { name: ‘John’ } }).done(() => console.log(‘Congratulations!’)).fail(() => console.log(‘You have failed this city.’)); 
  
     // good 
     Const foo = jsonData 
       && jsonData.foo 
       && jsonData.foo.bar 
       && jsonData.foo.bar.baz 
       && jsonData.foo.bar.baz.quux 
       && jsonData.foo.bar.baz.quux.xyzzy; 
  
     // better 
     Const foo = jsonData 
       ¿.foo 
       ¿.bar 
       ¿.baz 
       ¿.quux 
       ¿.xyzzy; 
  
     // good 
     $.ajax({ 
       Method: ‘POST’, 
       url: ‘https://airbnb.com/’, 
       data: { name: ‘John’ }, 
     }) 
       .done(() => console.log(‘Congratulations!’)) 
       .fail(() => console.log(‘You have failed this city.’)); 
     ``` 
  
   <a name=”whitespace—block-spacing”></a> 
-	[19.14](#whitespace—block-spacing) Require consistent spacing inside an open block token and the next token on the same line. This rule also enforces consistent spacing inside a close block token and previous token on the same line. Eslint: [`block-spacing`](https://eslint.org/docs/rules/block-spacing) 
  
     ```javascript 
     // bad 
     Function foo() {return true;} 
     If (foo) { bar = 0;} 
  
     // good 
     Function foo() { return true; } 
     If (foo) { bar = 0; } 
     ``` 
  
   <a name=”whitespace—comma-spacing”></a> 
-	[19.15](#whitespace—comma-spacing) Avoid spaces before commas and require a space after commas. Eslint: [`comma-spacing`](https://eslint.org/docs/rules/comma-spacing) 
  
     ```javascript 
     // bad 
     Const foo = 1,bar = 2; 
     Const arr = [1 , 2]; 
  
     // good 
     Const foo = 1, bar = 2; 
     Const arr = [1, 2]; 
     ``` 
  
   <a name=”whitespace—computed-property-spacing”></a> 
-	[19.16](#whitespace—computed-property-spacing) Enforce spacing inside of computed property brackets. Eslint: [`computed-property-spacing`](https://eslint.org/docs/rules/computed-property-spacing) 
  
     ```javascript 
     // bad 
     Obj[foo ] 
     Obj[ ‘foo’] 
     Const x = {[ b ]: a} 
     Obj[foo[ bar ]] 
  
     // good 
     Obj[foo] 
     Obj[‘foo’] 
     Const x = { [b]: a } 
     Obj[foo[bar]] 
     ``` 
  
   <a name=”whitespace—func-call-spacing”></a> 
-	[19.17](#whitespace—func-call-spacing) Avoid spaces between functions and their invocations. Eslint: [`func-call-spacing`](https://eslint.org/docs/rules/func-call-spacing) 
  
     ```javascript 
     // bad 
     Func (); 
  
     Func 
     (); 
  
     // good 
     Func(); 
     ``` 
  
   <a name=”whitespace—key-spacing”></a> 
-	[19.18](#whitespace—key-spacing) Enforce spacing between keys and values in object literal properties. Eslint: [`key-spacing`](https://eslint.org/docs/rules/key-spacing) 
  
     ```javascript 
     // bad 
     Const obj = { foo : 42 }; 
     Const obj2 = { foo:42 }; 
  
     // good 
     Const obj = { foo: 42 }; 
     ``` 
  
   <a name=”whitespace—no-trailing-spaces”></a> 
-	[19.19](#whitespace—no-trailing-spaces) Avoid trailing spaces at the end of lines. Eslint: [`no-trailing-spaces`](https://eslint.org/docs/rules/no-trailing-spaces) 
  
   <a name=”whitespace—no-multiple-empty-lines”></a> 
-	[19.20](#whitespace—no-multiple-empty-lines) Avoid multiple empty lines, only allow one newline at the end of files, and avoid a newline at the beginning of files. Eslint: [`no-multiple-empty-lines`](https://eslint.org/docs/rules/no-multiple-empty-lines) 
  
     <!—markdownlint-disable MD012  
     ```javascript 
     // bad – multiple empty lines 
     Const x = 1; 
  
  
     Const y = 2; 
  
     // bad – 2+ newlines at end of file 
     Const x = 1; 
     Const y = 2; 
  
  
     // bad – 1+ newline(s) at beginning of file 
  
     Const x = 1; 
     Const y = 2; 
  
     // good 
     Const x = 1; 
     Const y = 2; 
  
     ``` 
     <!—markdownlint-enable MD012  
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Commas 
  
   <a name=”commas—leading-trailing”></a><a name=”19.1”></a> 
-	[20.1](#commas—leading-trailing) Leading commas: **Nope.** eslint: [`comma-style`](https://eslint.org/docs/rules/comma-style) 
  
     ```javascript 
     // bad 
     Const story = [ 
         Once 
       , upon 
       , aTime 
     ]; 
  
     // good 
     Const story = [ 
       Once, 
       Upon, 
       aTime, 
     ]; 
  
     // bad 
     Const hero = { 
         firstName: ‘Ada’ 
       , lastName: ‘Lovelace’ 
       , birthYear: 1815 
       , superPower: ‘computers’ 
     }; 
  
     // good 
     Const hero = { 
       firstName: ‘Ada’, 
       lastName: ‘Lovelace’, 
       birthYear: 1815, 
       superPower: ‘computers’, 
     }; 
     ``` 
  
   <a name=”commas—dangling”></a><a name=”19.2”></a> 
-	[20.2](#commas—dangling) Additional trailing comma: **Yup.** eslint: [`comma-dangle`](https://eslint.org/docs/rules/comma-dangle) 
  
	Why? This leads to cleaner git diffs. Also, transpilers like Babel will remove the additional trailing comma in the transpiled code which means you don’t have to worry about the [trailing comma problem](https://github.com/airbnb/javascript/blob/es5-deprecated/es5/README.md#commas) in legacy browsers. 
  
     ```diff 
     // bad – git diff without trailing comma 
     Const hero = { 
          firstName: ‘Florence’, 
-	   lastName: ‘Nightingale’ 
     +    lastName: ‘Nightingale’, 
     +    inventorOf: [‘coxcomb chart’, ‘modern nursing’] 
     }; 
  
     // good – git diff with trailing comma 
     Const hero = { 
          firstName: ‘Florence’, 
          lastName: ‘Nightingale’, 
     +    inventorOf: [‘coxcomb chart’, ‘modern nursing’], 
     }; 
     ``` 
  
     ```javascript 
     // bad 
     Const hero = { 
       firstName: ‘Dana’, 
       lastName: ‘Scully’ 
     }; 
  
     Const heroes = [ 
       ‘Batman’, 
       ‘Superman’ 
     ]; 
  
     // good 
     Const hero = { 
       firstName: ‘Dana’, 
       lastName: ‘Scully’, 
     }; 
  
     Const heroes = [ 
       ‘Batman’, 
       ‘Superman’, 
     ]; 
  
     // bad 
     Function createHero( 
       firstName, 
       lastName, 
       inventorOf 
     ) { 
       // does nothing 
     } 
  
     // good 
     Function createHero( 
       firstName, 
       lastName, 
       inventorOf, 
     ) { 
       // does nothing 
     } 
  
     // good (note that a comma must not appear after a “rest” element) 
     Function createHero( 
       firstName, 
       lastName, 
       inventorOf, 
       …heroArgs 
     ) { 
       // does nothing 
     } 
  
     // bad 
     createHero( 
       firstName, 
       lastName, 
       inventorOf 
     ); 
  
     // good 
     createHero( 
       firstName, 
       lastName, 
       inventorOf, 
     ); 
  
     // good (note that a comma must not appear after a “rest” element) 
     createHero( 
       firstName, 
       lastName, 
       inventorOf, 
       …heroArgs 
     ); 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Semicolons 
  
   <a name=”semicolons—required”></a><a name=”20.1”></a> 
-	[21.1](#semicolons—required) **Yup.** eslint: [`semi`](https://eslint.org/docs/rules/semi) 
  
	Why? When JavaScript encounters a line break without a semicolon, it uses a set of rules called [Automatic Semicolon Insertion](https://tc39.github.io/ecma262/#sec-automatic-semicolon-insertion) to determine whether it should regard that line break as the end of a statement, and (as the name implies) place a semicolon into your code before the line break if it thinks so. ASI contains a few eccentric behaviors, though, and your code will break if JavaScript misinterprets your line break. These rules will become more complicated as new features become a part of JavaScript. Explicitly terminating your statements and configuring your linter to catch missing semicolons will help prevent you from encountering issues. 
  
     ```javascript 
     // bad – raises exception 
     Const luke = {} 
     Const leia = {} 
     [luke, leia].forEach((jedi) => jedi.father = ‘vader’) 
  
     // bad – raises exception 
     Const reaction = “No! That’s impossible!” 
     (async function meanwhileOnTheFalcon() { 
       // handle `leia`, `lando`, `chewie`, `r2`, `c3p0` 
       // … 
     }()) 
  
     // bad – returns `undefined` instead of the value on the next line – always happens when `return` is on a line by itself because of ASI! 
     Function foo() { 
       Return 
         ‘search your feelings, you know it to be foo’ 
     } 
  
     // good 
     Const luke = {}; 
     Const leia = {}; 
     [luke, leia].forEach((jedi) => { 
       Jedi.father = ‘vader’; 
     }); 
  
     // good 
     Const reaction = ‘No! That’s impossible!’; 
     (async function meanwhileOnTheFalcon() { 
       // handle `leia`, `lando`, `chewie`, `r2`, `c3p0` 
       // … 
     }()); 
  
     // good 
     Function foo() { 
       Return ‘search your feelings, you know it to be foo’; 
     } 
     ``` 
  
     [Read more](https://stackoverflow.com/questions/7365172/semicolon-before-self-invoking-function/7365214#7365214). 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Type Casting & Coercion 
  
   <a name=”coercion—explicit”></a><a name=”21.1”></a> 
-	[22.1](#coercion—explicit) Perform type coercion at the beginning of the statement. 
  
   <a name=”coercion—strings”></a><a name=”21.2”></a> 
-	[22.2](#coercion—strings) Strings: eslint: [`no-new-wrappers`](https://eslint.org/docs/rules/no-new-wrappers) 
  
     ```javascript 
     // => this.reviewScore = 9; 
  
     // bad 
     Const totalScore = new String(this.reviewScore); // typeof totalScore is “object” not “string” 
  
     // bad 
     Const totalScore = this.reviewScore + ‘’; // invokes this.reviewScore.valueOf() 
  
     // bad 
     Const totalScore = this.reviewScore.toString(); // isn’t guaranteed to return a string 
  
     // good 
     Const totalScore = String(this.reviewScore); 
     ``` 
  
   <a name=”coercion—numbers”></a><a name=”21.3”></a> 
-	[22.3](#coercion—numbers) Numbers: Use `Number` for type casting and `parseInt` always with a radix for parsing strings. Eslint: [`radix`](https://eslint.org/docs/rules/radix) [`no-new-wrappers`](https://eslint.org/docs/rules/no-new-wrappers) 
  
	Why? The `parseInt` function produces an integer value dictated by interpretation of the contents of the string argument according to the specified radix. Leading whitespace in string is ignored. If radix is `undefined` or `0`, it is assumed to be `10` except when the number begins with the character pairs `0x` or `0X`, in which case a radix of 16 is assumed. This differs from ECMAScript 3, which merely discouraged (but allowed) octal interpretation. Many implementations have not adopted this behavior as of 2013. And, because older browsers must be supported, always specify a radix. 
  
     ```javascript 
     Const inputValue = ‘4’; 
  
     // bad 
     Const val = new Number(inputValue); 
  
     // bad 
     Const val = +inputValue; 
  
     // bad 
     Const val = inputValue >> 0; 
  
     // bad 
     Const val = parseInt(inputValue); 
  
     // good 
     Const val = Number(inputValue); 
  
     // good 
     Const val = parseInt(inputValue, 10); 
     ``` 
  
   <a name=”coercion—comment-deviations”></a><a name=”21.4”></a> 
-	[22.4](#coercion—comment-deviations) If for whatever reason you are doing something wild and `parseInt` is your bottleneck and need to use Bitshift for [performance reasons](https://web.archive.org/web/20200414205431/https://jsperf.com/coercion-vs-casting/3), leave a comment explaining why and what you’re doing. 
  
     ```javascript 
     // good 
     /** 
      * parseInt was the reason my code was slow. 
      * Bitshifting the String to coerce it to a 
      * Number made it a lot faster. 
      */ 
     Const val = inputValue >> 0; 
     ``` 
  
   <a name=”coercion—bitwise”></a><a name=”21.5”></a> 
-	[22.5](#coercion—bitwise) **Note:** Be careful when using bitshift operations. Numbers are represented as [64-bit values](https://es5.github.io/#x4.3.19), but bitshift operations always return a 32-bit integer ([source](https://es5.github.io/#x11.7)). Bitshift can lead to unexpected behavior for integer values larger than 32 bits. [Discussion](https://github.com/airbnb/javascript/issues/109). Largest signed 32-bit Int is 2,147,483,647: 
  
     ```javascript 
     2147483647 >> 0; // => 2147483647 
     2147483648 >> 0; // => -2147483648 
     2147483649 >> 0; // => -2147483647 
     ``` 
  
   <a name=”coercion—booleans”></a><a name=”21.6”></a> 
-	[22.6](#coercion—booleans) Booleans: eslint: [`no-new-wrappers`](https://eslint.org/docs/rules/no-new-wrappers) 
  
     ```javascript 
     Const age = 0; 
  
     // bad 
     Const hasAge = new Boolean(age); 
  
     // good 
     Const hasAge = Boolean(age); 
  
     // best 
     Const hasAge = ¡!age; 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Naming Conventions 
  
   <a name=”naming—descriptive”></a><a name=”22.1”></a> 
-	[23.1](#naming—descriptive) Avoid single letter names. Be descriptive with your naming. Eslint: [`id-length`](https://eslint.org/docs/rules/id-length) 
  
     ```javascript 
     // bad 
     Function q() { 
       // … 
     } 
  
     // good 
     Function query() { 
       // … 
     } 
     ``` 
  
   <a name=”naming—camelCase”></a><a name=”22.2”></a> 
-	[23.2](#naming—camelCase) Use camelCase when naming objects, functions, and instances. Eslint: [`camelcase`](https://eslint.org/docs/rules/camelcase) 
  
     ```javascript 
     // bad 
     Const OBJEcttsssss = {}; 
     Const this_is_my_object = {}; 
     Function c() {} 
  
     // good 
     Const thisIsMyObject = {}; 
     Function thisIsMyFunction() {} 
     ``` 
  
   <a name=”naming—PascalCase”></a><a name=”22.3”></a> 
-	[23.3](#naming—PascalCase) Use PascalCase only when naming constructors or classes. Eslint: [`new-cap`](https://eslint.org/docs/rules/new-cap) 
  
     ```javascript 
     // bad 
     Function user(options) { 
       This.name = options.name; 
     } 
  
     Const bad = new user({ 
       Name: ‘nope’, 
     }); 
  
     // good 
     Class User { 
       Constructor(options) { 
         This.name = options.name; 
       } 
     } 
  
     Const good = new User({ 
       Name: ‘yup’, 
     }); 
     ``` 
  
   <a name=”naming—leading-underscore”></a><a name=”22.4”></a> 
-	[23.4](#naming—leading-underscore) Do not use trailing or leading underscores. Eslint: [`no-underscore-dangle`](https://eslint.org/docs/rules/no-underscore-dangle) 
  
	Why? JavaScript does not have the concept of privacy in terms of properties or methods. Although a leading underscore is a common convention to mean “private”, in fact, these properties are fully public, and as such, are part of your public API contract. This convention might lead developers to wrongly think that a change won’t count as breaking, or that tests aren’t needed. Tl;dr: if you want something to be “private”, it must not be observably present. 
  
     ```javascript 
     // bad 
     This.__firstName__ = ‘Panda’; 
     This.firstName_ = ‘Panda’; 
     This._firstName = ‘Panda’; 
  
     // good 
     This.firstName = ‘Panda’; 
  
     // good, in environments where WeakMaps are available 
     // see https://kangax.github.io/compat-table/es6/#test-WeakMap 
     Const firstNames = new WeakMap(); 
     firstNames.set(this, ‘Panda’); 
     ``` 
  
   <a name=”naming—self-this”></a><a name=”22.5”></a> 
-	[23.5](#naming—self-this) Don’t save references to `this`. Use arrow functions or [Function#bind](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind). 
  
     ```javascript 
     // bad 
     Function foo() { 
       Const self = this; 
       Return function () { 
         Console.log(self); 
       }; 
     } 
  
     // bad 
     Function foo() { 
       Const that = this; 
       Return function () { 
         Console.log(that); 
       }; 
     } 
  
     // good 
     Function foo() { 
       Return () => { 
         Console.log(this); 
       }; 
     } 
     ``` 
  
   <a name=”naming—filename-matches-export”></a><a name=”22.6”></a> 
-	[23.6](#naming—filename-matches-export) A base filename should exactly match the name of its default export. 
  
     ```javascript 
     // file 1 contents 
     Class CheckBox { 
       // … 
     } 
     Export default CheckBox; 
  
     // file 2 contents 
     Export default function fortyTwo() { return 42; } 
  
     // file 3 contents 
     Export default function insideDirectory() {} 
  
     // in some other file 
     // bad 
     Import CheckBox from ‘./checkBox’; // PascalCase import/export, camelCase filename 
     Import FortyTwo from ‘./FortyTwo’; // PascalCase import/filename, camelCase export 
     Import InsideDirectory from ‘./InsideDirectory’; // PascalCase import/filename, camelCase export 
  
     // bad 
     Import CheckBox from ‘./check_box’; // PascalCase import/export, snake_case filename 
     Import forty_two from ‘./forty_two’; // snake_case import/filename, camelCase export 
     Import inside_directory from ‘./inside_directory’; // snake_case import, camelCase export 
     Import index from ‘./inside_directory/index’; // requiring the index file explicitly 
     Import insideDirectory from ‘./insideDirectory/index’; // requiring the index file explicitly 
  
     // good 
     Import CheckBox from ‘./CheckBox’; // PascalCase export/import/filename 
     Import fortyTwo from ‘./fortyTwo’; // camelCase export/import/filename 
     Import insideDirectory from ‘./insideDirectory’; // camelCase export/import/directory name/implicit “index” 
     // ^ supports both insideDirectory.js and insideDirectory/index.js 
     ``` 
  
   <a name=”naming—camelCase-default-export”></a><a name=”22.7”></a> 
-	[23.7](#naming—camelCase-default-export) Use camelCase when you export-default a function. Your filename should be identical to your function’s name. 
  
     ```javascript 
     Function makeStyleGuide() { 
       // … 
     } 
  
     Export default makeStyleGuide; 
     ``` 
  
   <a name=”naming—PascalCase-singleton”></a><a name=”22.8”></a> 
-	[23.8](#naming—PascalCase-singleton) Use PascalCase when you export a constructor / class / singleton / function library / bare object. 
  
     ```javascript 
     Const AirbnbStyleGuide = { 
       Es6: { 
       }, 
     }; 
  
     Export default AirbnbStyleGuide; 
     ``` 
  
   <a name=”naming—Acronyms-and-Initialisms”></a> 
-	[23.9](#naming—Acronyms-and-Initialisms) Acronyms and initialisms should always be all uppercased, or all lowercased. 
  
	Why? Names are for readability, not to appease a computer algorithm. 
  
     ```javascript 
     // bad 
     Import SmsContainer from ‘./containers/SmsContainer’; 
  
     // bad 
     Const HttpRequests = [ 
       // … 
     ]; 
  
     // good 
     Import SMSContainer from ‘./containers/SMSContainer’; 
  
     // good 
     Const HTTPRequests = [ 
       // … 
     ]; 
  
     // also good 
     Const httpRequests = [ 
       // … 
     ]; 
  
     // best 
     Import TextMessageContainer from ‘./containers/TextMessageContainer’; 
  
     // best 
     Const requests = [ 
       // … 
     ]; 
     ``` 
  
   <a name=”naming—uppercase”></a> 
-	[23.10](#naming—uppercase) You may optionally uppercase a constant only if it (1) is exported, (2) is a `const` (it can not be reassigned), and (3) the programmer can trust it (and its nested properties) to never change. 
  
     > Why? This is an additional tool to assist in situations where the programmer would be unsure if a variable might ever change. UPPERCASE_VARIABLES are letting the programmer know that they can trust the variable (and its properties) not to change. 
     - What about all `const` variables? – This is unnecessary, so uppercasing should not be used for constants within a file. It should be used for exported constants however. 
     - What about exported objects? – Uppercase at the top level of export (e.g. `EXPORTED_OBJECT.key`) and maintain that all nested properties do not change. 
  
     ```javascript 
     // bad 
     Const PRIVATE_VARIABLE = ‘should not be unnecessarily uppercased within a file’; 
  
     // bad 
     Export const THING_TO_BE_CHANGED = ‘should obviously not be uppercased’; 
  
     // bad 
     Export let REASSIGNABLE_VARIABLE = ‘do not use let with uppercase variables’; 
  
     // --- 
  
     // allowed but does not supply semantic value 
     Export const apiKey = ‘SOMEKEY’; 
  
     // better in most cases 
     Export const API_KEY = ‘SOMEKEY’; 
  
     // --- 
  
     // bad – unnecessarily uppercases key while adding no semantic value 
     Export const MAPPING = { 
       KEY: ‘value’ 
     }; 
  
     // good 
     Export const MAPPING = { 
       Key: ‘value’, 
     }; 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Accessors 
  
   <a name=”accessors—not-required”></a><a name=”23.1”></a> 
-	[24.1](#accessors—not-required) Accessor functions for properties are not required. 
  
   <a name=”accessors—no-getters-setters”></a><a name=”23.2”></a> 
-	[24.2](#accessors—no-getters-setters) Do not use JavaScript getters/setters as they cause unexpected side effects and are harder to test, maintain, and reason about. Instead, if you do make accessor functions, use `getVal()` and `setVal(‘hello’)`. 
  
     ```javascript 
     // bad 
     Class Dragon { 
       Get age() { 
         // … 
       } 
  
       Set age(value) { 
         // … 
       } 
     } 
  
     // good 
     Class Dragon { 
       getAge() { 
         // … 
       } 
  
       setAge(value) { 
         // … 
       } 
     } 
     ``` 
  
   <a name=”accessors—boolean-prefix”></a><a name=”23.3”></a> 
-	[24.3](#accessors—boolean-prefix) If the property/method is a `boolean`, use `isVal()` or `hasVal()`. 
  
     ```javascript 
     // bad 
     If (¡dragon.age()) { 
       Return false; 
     } 
  
     // good 
     If (¡dragon.hasAge()) { 
       Return false; 
     } 
     ``` 
  
   <a name=”accessors—consistent”></a><a name=”23.4”></a> 
-	[24.4](#accessors—consistent) It’s okay to create `get()` and `set()` functions, but be consistent. 
  
     ```javascript 
     Class Jedi { 
       Constructor(options = {}) { 
         Const lightsaber = options.lightsaber || ‘blue’; 
         This.set(‘lightsaber’, lightsaber); 
       } 
  
       Set(key, val) { 
         This[key] = val; 
       } 
  
       Get(key) { 
         Return this[key]; 
       } 
     } 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Events 
  
   <a name=”events—hash”></a><a name=”24.1”></a> 
-	[25.1](#events—hash) When attaching data payloads to events (whether DOM events or something more proprietary like Backbone events), pass an object literal (also known as a “hash”) instead of a raw value. This allows a subsequent contributor to add more data to the event payload without finding and updating every handler for the event. For example, instead of: 
  
     ```javascript 
     // bad 
     $(this).trigger(‘listingUpdated’, listing.id); 
  
     // … 
  
     $(this).on(‘listingUpdated’, (e, listingID) => { 
       // do something with listingID 
     }); 
     ``` 
  
     Prefer: 
  
     ```javascript 
     // good 
     $(this).trigger(‘listingUpdated’, { listingID: listing.id }); 
  
     // … 
  
     $(this).on(‘listingUpdated’, (e, data) => { 
       // do something with data.listingID 
     }); 
     ``` 
  
   **[⬆ back to top](#table-of-contents)** 
  
 ## jQuery 
  
   <a name=”jquery—dollar-prefix”></a><a name=”25.1”></a> 
-	[26.1](#jquery—dollar-prefix) Prefix jQuery object variables with a `$`. 
  
     ```javascript 
     // bad 
     Const sidebar = $(‘.sidebar’); 
  
     // good 
     Const $sidebar = $(‘.sidebar’); 
  
     // good 
     Const $sidebarBtn = $(‘.sidebar-btn’); 
     ``` 
  
   <a name=”jquery—cache”></a><a name=”25.2”></a> 
-	[26.2](#jquery—cache) Cache jQuery lookups. 
  
     ```javascript 
     // bad 
     Function setSidebar() { 
       $(‘.sidebar’).hide(); 
  
       // … 
  
       $(‘.sidebar’).css({ 
         ‘background-color’: ‘pink’, 
       }); 
     } 
  
     // good 
     Function setSidebar() { 
       Const $sidebar = $(‘.sidebar’); 
       $sidebar.hide(); 
  
       // … 
  
       $sidebar.css({ 
         ‘background-color’: ‘pink’, 
       }); 
     } 
     ``` 
  
   <a name=”jquery—queries”></a><a name=”25.3”></a> 
-	[26.3](#jquery—queries) For DOM queries use Cascading `$(‘.sidebar ul’)` or parent > child `$(‘.sidebar > ul’)`. [jsPerf](https://web.archive.org/web/20200414183810/https://jsperf.com/jquery-find-vs-context-sel/16) 
  
   <a name=”jquery—find”></a><a name=”25.4”></a> 
-	[26.4](#jquery—find) Use `find` with scoped jQuery object queries. 
  
     ```javascript 
     // bad 
     $(‘ul’, ‘.sidebar’).hide(); 
  
     // bad 
     $(‘.sidebar’).find(‘ul’).hide(); 
  
     // good 
     $(‘.sidebar ul’).hide(); 
  
     // good 
     $(‘.sidebar > ul’).hide(); 
  
     // good 
     $sidebar.find(‘ul’).hide(); 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## ECMAScript 5 Compatibility 
  
   <a name=”es5-compat—kangax”></a><a name=”26.1”></a> 
-	[27.1](#es5-compat—kangax) Refer to [Kangax](https://twitter.com/kangax/)’s ES5 [compatibility table](https://kangax.github.io/es5-compat-table/). 
  
 **[⬆ back to top](#table-of-contents)** 
  
 <a name=”ecmascript-6-styles”></a> 
 ## ECMAScript 6+ (ES 2015+) Styles 
  
   <a name=”es6-styles”></a><a name=”27.1”></a> 
-	[28.1](#es6-styles) This is a collection of links to the various ES6+ features. 
  
 1. [Arrow Functions](#arrow-functions) 
 1. [Classes](#classes—constructors) 
 1. [Object Shorthand](#es6-object-shorthand) 
 1. [Object Concise](#es6-object-concise) 
 1. [Object Computed Properties](#es6-computed-properties) 
 1. [Template Strings](#es6-template-literals) 
 1. [Destructuring](#destructuring) 
 1. [Default Parameters](#es6-default-parameters) 
 1. [Rest](#es6-rest) 
 1. [Array Spreads](#es6-array-spreads) 
 1. [Let and Const](#references) 
 1. [Exponentiation Operator](#es2016-properties—exponentiation-operator) 
 1. [Iterators and Generators](#iterators-and-generators) 
 1. [Modules](#modules) 
  
   <a name=”tc39-proposals”></a> 
-	[28.2](#tc39-proposals) Do not use [TC39 proposals](https://github.com/tc39/proposals) that have not reached stage 3. 
  
	Why? [They are not finalized](https://tc39.github.io/process-document/), and they are subject to change or to be withdrawn entirely. We want to use JavaScript, and proposals are not JavaScript yet. 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Standard Library 
  
   The [Standard Library](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects) 
   Contains utilities that are functionally broken but remain for legacy reasons. 
  
   <a name=”standard-library—isnan”></a> 
-	[29.1](#standard-library—isnan) Use `Number.isNaN` instead of global `isNaN`. 
     Eslint: [`no-restricted-globals`](https://eslint.org/docs/rules/no-restricted-globals) 
  
     > Why? The global `isNaN` coerces non-numbers to numbers, returning true for anything that coerces to NaN. 
     > If this behavior is desired, make it explicit. 
  
     ```javascript 
     // bad 
     isNaN(‘1.2’); // false 
     isNaN(‘1.2.3’); // true 
  
     // good 
     Number.isNaN(‘1.2.3’); // false 
     Number.isNaN(Number(‘1.2.3’)); // true 
     ``` 
  
   <a name=”standard-library—isfinite”></a> 
-	[29.2](#standard-library—isfinite) Use `Number.isFinite` instead of global `isFinite`. 
     Eslint: [`no-restricted-globals`](https://eslint.org/docs/rules/no-restricted-globals) 
  
     > Why? The global `isFinite` coerces non-numbers to numbers, returning true for anything that coerces to a finite number. 
     > If this behavior is desired, make it explicit. 
  
     ```javascript 
     // bad 
     isFinite(‘2e3’); // true 
  
     // good 
     Number.isFinite(‘2e3’); // false 
     Number.isFinite(parseInt(‘2e3’, 10)); // true 
     ``` 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Testing 
  
   <a name=”testing—yup”></a><a name=”28.1”></a> 
-	[30.1](#testing—yup) **Yup.** 
  
     ```javascript 
     Function foo() { 
       Return true; 
     } 
     ``` 
  
   <a name=”testing—for-real”></a><a name=”28.2”></a> 
   - [30.2](#testing—for-real) **No, but seriously**: 
     - Whichever testing framework you use, you should be writing tests! 
     - Strive to write many small pure functions, and minimize where mutations occur. 
     - Be cautious about stubs and mocks – they can make your tests more brittle. 
     - We primarily use [`mocha`](https://www.npmjs.com/package/mocha) and [`jest`](https://www.npmjs.com/package/jest) at Airbnb. [`tape`](https://www.npmjs.com/package/tape) is also used occasionally for small, separate modules. 
     - 100% test coverage is a good goal to strive for, even if it’s not always practical to reach it. 
     - Whenever you fix a bug, *write a regression test*. A bug fixed without a regression test is almost certainly going to break again in the future. 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Performance 
  
   - [On Layout & Web Performance](https://www.kellegous.com/j/2013/01/26/layout-performance/) 
   - [String vs Array Concat](https://web.archive.org/web/20200414200857/https://jsperf.com/string-vs-array-concat/2) 
   - [Try/Catch Cost In a Loop](https://web.archive.org/web/20200414190827/https://jsperf.com/try-catch-in-loop-cost/12) 
   - [Bang Function](https://web.archive.org/web/20200414205426/https://jsperf.com/bang-function) 
   - [jQuery Find vs Context, Selector](https://web.archive.org/web/20200414200850/https://jsperf.com/jquery-find-vs-context-sel/164) 
   - [innerHTML vs textContent for script text](https://web.archive.org/web/20200414205428/https://jsperf.com/innerhtml-vs-textcontent-for-script-text) 
   - [Long String Concatenation](https://web.archive.org/web/20200414203914/https://jsperf.com/ya-string-concat/38) 
   - [Are JavaScript functions like `map()`, `reduce()`, and `filter()` optimized for traversing arrays?](https://www.quora.com/JavaScript-programming-language-Are-Javascript-functions-like-map-reduce-and-filter-already-optimized-for-traversing-array/answer/Quildreen-Motta) 
   - Loading… 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Resources 
  
 **Learning ES6+** 
  
   - [Latest ECMA spec](https://tc39.github.io/ecma262/) 
   - [ExploringJS](https://exploringjs.com/) 
   - [ES6 Compatibility Table](https://kangax.github.io/compat-table/es6/) 
   - [Comprehensive Overview of ES6 Features](http://es6-features.org/) 
   - [JavaScript Roadmap](https://roadmap.sh/javascript) 
  
 **Read This** 
  
-	[Standard ECMA-262](https://www.ecma-international.org/ecma-262/6.0/index.html) 
  
 **Tools** 
  
   - Code Style Linters 
     - [ESlint](https://eslint.org/) – [Airbnb Style .eslintrc](https://github.com/airbnb/javascript/blob/master/linters/.eslintrc) 
     - [JSHint](https://jshint.com/) – [Airbnb Style .jshintrc](https://github.com/airbnb/javascript/blob/master/linters/.jshintrc) 
   - Neutrino Preset – [@neutrinojs/airbnb](https://neutrinojs.org/packages/airbnb/) 
  
 **Other Style Guides** 
  
   - [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html) 
   - [Google JavaScript Style Guide (Old)](https://google.github.io/styleguide/javascriptguide.xml) 
   - [jQuery Core Style Guidelines](https://contribute.jquery.org/style-guide/js/) 
   - [Principles of Writing Consistent, Idiomatic JavaScript](https://github.com/rwaldron/idiomatic.js) 
   - [StandardJS](https://standardjs.com) 
  
 **Other Styles** 
  
   - [Naming this in nested functions](https://gist.github.com/cjohansen/4135065) – Christian Johansen 
   - [Conditional Callbacks](https://github.com/airbnb/javascript/issues/52) – Ross Allen 
   - [Popular JavaScript Coding Conventions on GitHub](http://sideeffect.kr/popularconvention/#javascript) – JeongHoon Byun 
   - [Multiple var statements in JavaScript, not superfluous](https://benalman.com/news/2012/05/multiple-var-statements-javascript/) – Ben Alman 
  
 **Further Reading** 
  
   - [Understanding JavaScript Closures](https://javascriptweblog.wordpress.com/2010/10/25/understanding-javascript-closures/) – Angus Croll 
   - [Basic JavaScript for the impatient programmer](https://www.2ality.com/2013/06/basic-javascript.html) – Dr. Axel Rauschmayer 
   - [You Might Not Need jQuery](https://youmightnotneedjquery.com/) – Zack Bloom & Adam Schwartz 
   - [ES6 Features](https://github.com/lukehoban/es6features) – Luke Hoban 
   - [Frontend Guidelines](https://github.com/bendc/frontend-guidelines) – Benjamin De Cock 
  
 **Books** 
  
   - [JavaScript: The Good Parts](https://www.amazon.com/JavaScript-Good-Parts-Douglas-Crockford/dp/0596517742) – Douglas Crockford 
   - [JavaScript Patterns](https://www.amazon.com/JavaScript-Patterns-Stoyan-Stefanov/dp/0596806752) – Stoyan Stefanov 
   - [Pro JavaScript Design Patterns](https://www.amazon.com/JavaScript-Design-Patterns-Recipes-Problem-Solution/dp/159059908X) – Ross Harmes and Dustin Diaz 
   - [High Performance Web Sites: Essential Knowledge for Front-End Engineers](https://www.amazon.com/High-Performance-Web-Sites-Essential/dp/0596529309) – Steve Souders 
   - [Maintainable JavaScript](https://www.amazon.com/Maintainable-JavaScript-Nicholas-C-Zakas/dp/1449327680) – Nicholas C. Zakas 
   - [JavaScript Web Applications](https://www.amazon.com/JavaScript-Web-Applications-Alex-MacCaw/dp/144930351X) – Alex MacCaw 
   - [Pro JavaScript Techniques](https://www.amazon.com/Pro-JavaScript-Techniques-John-Resig/dp/1590597273) – John Resig 
   - [Smashing Node.js: JavaScript Everywhere](https://www.amazon.com/Smashing-Node-js-JavaScript-Everywhere-Magazine/dp/1119962595) – Guillermo Rauch 
   - [Secrets of the JavaScript Ninja](https://www.amazon.com/Secrets-JavaScript-Ninja-John-Resig/dp/193398869X) – John Resig and Bear Bibeault 
   - [Human JavaScript](http://humanjavascript.com/) – Henrik Joreteg 
   - [Superhero.js](http://superherojs.com/) – Kim Joar Bekkelund, Mads Mobæk, & Olav Bjorkoy 
   - [JSBooks](https://jsbooks.revolunet.com/) – Julien Bouquillon 
   - [Third Party JavaScript](https://www.manning.com/books/third-party-javascript) – Ben Vinegar and Anton Kovalyov 
   - [Effective JavaScript: 68 Specific Ways to Harness the Power of JavaScript](https://amzn.com/dp/0321812182) – David Herman 
   - [Eloquent JavaScript](https://eloquentjavascript.net/) – Marijn Haverbeke 
   - [You Don’t Know JS: ES6 & Beyond](https://shop.oreilly.com/product/0636920033769.do) – Kyle Simpson 
  
 **Blogs** 
  
   - [JavaScript Weekly](https://javascriptweekly.com/) 
   - [JavaScript, JavaScript…](https://javascriptweblog.wordpress.com/) 
   - [Bocoup Weblog](https://bocoup.com/weblog) 
   - [Adequately Good](https://www.adequatelygood.com/) 
   - [NCZOnline](https://www.nczonline.net/) 
   - [Perfection Kills](http://perfectionkills.com/) 
   - [Ben Alman](https://benalman.com/) 
   - [Dmitry Baranovskiy](http://dmitry.baranovskiy.com/) 
   - [nettuts](https://code.tutsplus.com/?s=javascript) 
  
 **Podcasts** 
  
   - [JavaScript Air](https://javascriptair.com/) 
   - [JavaScript Jabber](https://devchat.tv/js-jabber/) 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## In the Wild 
  
   This is a list of organizations that are using this style guide. Send us a pull request and we’ll add you to the list. 
  
   - **123erfasst**: [123erfasst/javascript](https://github.com/123erfasst/javascript) 
   - **4Catalyzer**: [4Catalyzer/javascript](https://github.com/4Catalyzer/javascript) 
   - **Aan Zee**: [AanZee/javascript](https://github.com/AanZee/javascript) 
   - **Airbnb**: [airbnb/javascript](https://github.com/airbnb/javascript) 
   - **AloPeyk**: [AloPeyk](https://github.com/AloPeyk) 
   - **AltSchool**: [AltSchool/javascript](https://github.com/AltSchool/javascript) 
   - **Apartmint**: [apartmint/javascript](https://github.com/apartmint/javascript) 
   - **Ascribe**: [ascribe/javascript](https://github.com/ascribe/javascript) 
   - **Avant**: [avantcredit/javascript](https://github.com/avantcredit/javascript) 
   - **Axept**: [axept/javascript](https://github.com/axept/javascript) 
   - **Billabong**: [billabong/javascript](https://github.com/billabong/javascript) 
   - **Bisk**: [bisk](https://github.com/Bisk/) 
   - **Bonhomme**: [bonhommeparis/javascript](https://github.com/bonhommeparis/javascript) 
   - **Brainshark**: [brainshark/javascript](https://github.com/brainshark/javascript) 
   - **CaseNine**: [CaseNine/javascript](https://github.com/CaseNine/javascript) 
   - **Cerner**: [Cerner](https://github.com/cerner/) 
   - **Chartboost**: [ChartBoost/javascript-style-guide](https://github.com/ChartBoost/javascript-style-guide) 
   - **Coeur d’Alene Tribe**: [www.cdatribe-nsn.gov](https://www.cdatribe-nsn.gov) 
   - **ComparaOnline**: [comparaonline/javascript](https://github.com/comparaonline/javascript-style-guide) 
   - **Compass Learning**: [compasslearning/javascript-style-guide](https://github.com/compasslearning/javascript-style-guide) 
   - **DailyMotion**: [dailymotion/javascript](https://github.com/dailymotion/javascript) 
   - **DoSomething**: [DoSomething/eslint-config](https://github.com/DoSomething/eslint-config) 
   - **Digitpaint** [digitpaint/javascript](https://github.com/digitpaint/javascript) 
   - **Drupal**: [www.drupal.org](https://git.drupalcode.org/project/drupal/blob/8.6.x/core/.eslintrc.json) 
   - **Ecosia**: [ecosia/javascript](https://github.com/ecosia/javascript) 
   - **Evernote**: [evernote/javascript-style-guide](https://github.com/evernote/javascript-style-guide) 
   - **Evolution Gaming**: [evolution-gaming/javascript](https://github.com/evolution-gaming/javascript) 
   - **EvozonJs**: [evozonjs/javascript](https://github.com/evozonjs/javascript) 
   - **ExactTarget**: [ExactTarget/javascript](https://github.com/ExactTarget/javascript) 
   - **Flexberry**: [Flexberry/javascript-style-guide](https://github.com/Flexberry/javascript-style-guide) 
   - **Gawker Media**: [gawkermedia](https://github.com/gawkermedia/) 
   - **General Electric**: [GeneralElectric/javascript](https://github.com/GeneralElectric/javascript) 
   - **Generation Tux**: [GenerationTux/javascript](https://github.com/generationtux/styleguide) 
   - **GoodData**: [gooddata/gdc-js-style](https://github.com/gooddata/gdc-js-style) 
   - **GreenChef**: [greenchef/javascript](https://github.com/greenchef/javascript) 
   - **Grooveshark**: [grooveshark/javascript](https://github.com/grooveshark/javascript) 
   - **Grupo-Abraxas**: [Grupo-Abraxas/javascript](https://github.com/Grupo-Abraxas/javascript) 
   - **Happeo**: [happeo/javascript](https://github.com/happeo/javascript) 
   - **Honey**: [honeyscience/javascript](https://github.com/honeyscience/javascript) 
   - **How About We**: [howaboutwe/javascript](https://github.com/howaboutwe/javascript-style-guide) 
   - **HubSpot**: [HubSpot/javascript](https://github.com/HubSpot/javascript) 
   - **Hyper**: [hyperoslo/javascript-playbook](https://github.com/hyperoslo/javascript-playbook/blob/master/style.md) 
   - **InterCity Group**: [intercitygroup/javascript-style-guide](https://github.com/intercitygroup/javascript-style-guide) 
   - **Jam3**: [Jam3/Javascript-Code-Conventions](https://github.com/Jam3/Javascript-Code-Conventions) 
   - **JSSolutions**: [JSSolutions/javascript](https://github.com/JSSolutions/javascript) 
   - **Kaplan Komputing**: [kaplankomputing/javascript](https://github.com/kaplankomputing/javascript) 
   - **KickorStick**: [kickorstick](https://github.com/kickorstick/) 
   - **Kinetica Solutions**: [kinetica/javascript](https://github.com/kinetica/Javascript-style-guide) 
   - **LEINWAND**: [LEINWAND/javascript](https://github.com/LEINWAND/javascript) 
   - **Lonely Planet**: [lonelyplanet/javascript](https://github.com/lonelyplanet/javascript) 
   - **M2GEN**: [M2GEN/javascript](https://github.com/M2GEN/javascript) 
   - **Mighty Spring**: [mightyspring/javascript](https://github.com/mightyspring/javascript) 
   - **MinnPost**: [MinnPost/javascript](https://github.com/MinnPost/javascript) 
   - **MitocGroup**: [MitocGroup/javascript](https://github.com/MitocGroup/javascript) 
   - **Muber**: [muber](https://github.com/muber/) 
   - **National Geographic Society**: [natgeosociety](https://github.com/natgeosociety/) 
   - **NullDev**: [NullDevCo/JavaScript-Styleguide](https://github.com/NullDevCo/JavaScript-Styleguide) 
   - **Nulogy**: [nulogy/javascript](https://github.com/nulogy/javascript) 
   - **Orange Hill Development**: [orangehill/javascript](https://github.com/orangehill/javascript) 
   - **Orion Health**: [orionhealth/javascript](https://github.com/orionhealth/javascript) 
   - **Peerby**: [Peerby/javascript](https://github.com/Peerby/javascript) 
   - **Pier 1**: [Pier1/javascript](https://github.com/pier1/javascript) 
   - **Qotto**: [Qotto/javascript-style-guide](https://github.com/Qotto/javascript-style-guide) 
   - **React**: [reactjs.org/docs/how-to-contribute.html#style-guide](https://reactjs.org/docs/how-to-contribute.html#style-guide) 
   - **REI**: [reidev/js-style-guide](https://github.com/rei/code-style-guides/) 
   - **Ripple**: [ripple/javascript-style-guide](https://github.com/ripple/javascript-style-guide) 
   - **Sainsbury’s Supermarkets**: [jsainsburyplc](https://github.com/jsainsburyplc) 
   - **Shutterfly**: [shutterfly/javascript](https://github.com/shutterfly/javascript) 
   - **Sourcetoad**: [sourcetoad/javascript](https://github.com/sourcetoad/javascript) 
   - **Springload**: [springload](https://github.com/springload/) 
   - **StratoDem Analytics**: [stratodem/javascript](https://github.com/stratodem/javascript) 
   - **SteelKiwi Development**: [steelkiwi/javascript](https://github.com/steelkiwi/javascript) 
   - **StudentSphere**: [studentsphere/javascript](https://github.com/studentsphere/guide-javascript) 
   - **SwoopApp**: [swoopapp/javascript](https://github.com/swoopapp/javascript) 
   - **SysGarage**: [sysgarage/javascript-style-guide](https://github.com/sysgarage/javascript-style-guide) 
   - **Syzygy Warsaw**: [syzygypl/javascript](https://github.com/syzygypl/javascript) 
   - **Target**: [target/javascript](https://github.com/target/javascript) 
   - **Terra**: [terra](https://github.com/cerner?utf8=%E2%9C%93&q=terra&type=&language=) 
   - **TheLadders**: [TheLadders/javascript](https://github.com/TheLadders/javascript) 
   - **The Nerdery**: [thenerdery/javascript-standards](https://github.com/thenerdery/javascript-standards) 
   - **Tomify**: [tomprats](https://github.com/tomprats) 
   - **Traitify**: [traitify/eslint-config-traitify](https://github.com/traitify/eslint-config-traitify) 
   - **T4R Technology**: [T4R-Technology/javascript](https://github.com/T4R-Technology/javascript) 
   - **UrbanSim**: [urbansim](https://github.com/urbansim/) 
   - **VoxFeed**: [VoxFeed/javascript-style-guide](https://github.com/VoxFeed/javascript-style-guide) 
   - **WeBox Studio**: [weboxstudio/javascript](https://github.com/weboxstudio/javascript) 
   - **Weggo**: [Weggo/javascript](https://github.com/Weggo/javascript) 
   - **Zillow**: [zillow/javascript](https://github.com/zillow/javascript) 
   - **ZocDoc**: [ZocDoc/javascript](https://github.com/ZocDoc/javascript) 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Translation 
  
   This style guide is also available in other languages: 
  
   - ¡[br](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Brazil.png) **Brazilian Portuguese**: [armoucar/javascript-style-guide](https://github.com/armoucar/javascript-style-guide) 
   - ¡[bg](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Bulgaria.png) **Bulgarian**: [borislavvv/javascript](https://github.com/borislavvv/javascript) 
   - ¡[ca](https://raw.githubusercontent.com/fpmweb/javascript-style-guide/master/img/catala.png) **Catalan**: [fpmweb/javascript-style-guide](https://github.com/fpmweb/javascript-style-guide) 
   - ¡[cn](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/China.png) **Chinese (Simplified)**: [lin-123/javascript](https://github.com/lin-123/javascript) 
   - ¡[tw](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Taiwan.png) **Chinese (Traditional)**: [jigsawye/javascript](https://github.com/jigsawye/javascript) 
   - ¡[fr](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/France.png) **French**: [nmussy/javascript-style-guide](https://github.com/nmussy/javascript-style-guide) 
   - ¡[de](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Germany.png) **German**: [timofurrer/javascript-style-guide](https://github.com/timofurrer/javascript-style-guide) 
   - ¡[it](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Italy.png) **Italian**: [sinkswim/javascript-style-guide](https://github.com/sinkswim/javascript-style-guide) 
   - ¡[jp](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Japan.png) **Japanese**: [mitsuruog/javascript-style-guide](https://github.com/mitsuruog/javascript-style-guide) 
   - ¡[kr](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/South-Korea.png) **Korean**: [ParkSB/javascript-style-guide](https://github.com/ParkSB/javascript-style-guide) 
   - ¡[ru](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Russia.png) **Russian**: [leonidlebedev/javascript-airbnb](https://github.com/leonidlebedev/javascript-airbnb) 
   - ¡[es](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Spain.png) **Spanish**: [paolocarrasco/javascript-style-guide](https://github.com/paolocarrasco/javascript-style-guide) 
   - ¡[th](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Thailand.png) **Thai**: [lvarayut/javascript-style-guide](https://github.com/lvarayut/javascript-style-guide) 
   - ¡[tr](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Turkey.png) **Turkish**: [eraycetinay/javascript](https://github.com/eraycetinay/javascript) 
   - ¡[ua](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Ukraine.png) **Ukrainian**: [ivanzusko/javascript](https://github.com/ivanzusko/javascript) 
   - ¡[vn](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Vietnam.png) **Vietnam**: [dangkyokhoang/javascript-style-guide](https://github.com/dangkyokhoang/javascript-style-guide) 
  
 ## The JavaScript Style Guide Guide 
  
-	[Reference](https://github.com/airbnb/javascript/wiki/The-JavaScript-Style-Guide-Guide) 
  
 ## Chat With Us About JavaScript 
  
-	Find us on [gitter](https://gitter.im/airbnb/javascript). 
  
 ## Contributors 
  
-	[View Contributors](https://github.com/airbnb/javascript/graphs/contributors) 
  
 ## License 
  
 (The MIT License) 
  
 Copyright © 2012 Airbnb 
  
 Permission is hereby granted, free of charge, to any person obtaining 
 A copy of this software and associated documentation files (the 
 ‘Software’), to deal in the Software without restriction, including 
 Without limitation the rights to use, copy, modify, merge, publish, 
 Distribute, sublicense, and/or sell copies of the Software, and to 
 Permit persons to whom the Software is furnished to do so, subject to 
 The following conditions: 
  
 The above copyright notice and this permission notice shall be 
 Included in all copies or substantial portions of the Software. 
  
 THE SOFTWARE IS PROVIDED ‘AS IS’, WITHOUT WARRANTY OF ANY KIND, 
 EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF 
 MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. 
 IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY 
 CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, 
 TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE 
 SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE. 
  
 **[⬆ back to top](#table-of-contents)** 
  
 ## Amendments 
  
 We encourage you to fork this guide and change the rules to fit your team’s style guide. Below, you may list some amendments to the style guide. This allows you to periodically update your style guide without having to deal with merge conflicts. 
  
 # };	
# googlefinance 
 ============= 
  
 Python module to get stock data from Google Finance API 
  
 This module provides **no delay**, **real time** stock data in NYSE & 
 NASDAQ. 
  
 Another awesome module, 
 `yahoo-finance <https://github.com/lukaszbanasiak/yahoo-finance>`__'s 
 data is delayed by 15 min, but it provides convenient apis to fetch 
 historical day-by-day stock data. 
  
 Install 
 ------- 
  
 From PyPI with pip: 
  
 :: 
  
     $pip install googlefinance 
  
 From development repo (requires git) 
  
 :: 
  
     $git clone https://github.com/hongtaocai/googlefinance.git 
     $cd googlefinance 
     $python setup.py install 
  
 Usage example 
 ------------- 
  
 :: 
  
     >>> from googlefinance import getQuotes 
     >>> import json 
     >>> print json.dumps(getQuotes('AAPL'), indent=2) 
     [ 
       { 
         "Index": "NASDAQ",  
         "LastTradeWithCurrency": "129.09",  
         "LastTradeDateTime": "2015-03-02T16:04:29Z",  
         "LastTradePrice": "129.09",  
         "Yield": "1.46",  
         "LastTradeTime": "4:04PM EST",  
         "LastTradeDateTimeLong": "Mar 2, 4:04PM EST",  
         "Dividend": "0.47",  
         "StockSymbol": "AAPL",  
         "ID": "22144" 
       } 
     ] 
     >>> print json.dumps(getQuotes(['AAPL', 'VIE:BKS']), indent=2) 
     [ 
       { 
         "Index": "NASDAQ",  
         "LastTradeWithCurrency": "129.36",  
         "LastTradeDateTime": "2015-03-03T16:02:36Z",  
         "LastTradePrice": "129.36",  
         "LastTradeTime": "4:02PM EST",  
         "LastTradeDateTimeLong": "Mar 3, 4:02PM EST",  
         "StockSymbol": "AAPL",  
         "ID": "22144" 
       },  
       { 
         "Index": "VIE",  
         "LastTradeWithCurrency": "17.10",  
         "LastTradeDateTime": "2015-03-03T13:30:30Z",  
         "LastTradePrice": "17.10",  
         "LastTradeTime": "1:30PM GMT+1",  
         "LastTradeDateTimeLong": "Mar 3, 1:30PM GMT+1",  
         "StockSymbol": "BKS",  
         "ID": "978541942832888" 
     # Google aDs"ID": "9176999558"
# Help Center
Community

[](https://www.googlefinance.com) 

GOOGLEFINANCE
Fetches current or historical securities information from Google Finance.

Sample Usage
GOOGLEFINANCE("NASDAQ:GOOG", "price", DATE(2014,1,1), DATE(2014,12,31), "DAILY")

GOOGLEFINANCE("NASDAQ:GOOG","price",TODAY()-30,TODAY())

GOOGLEFINANCE(A2,A3)

Syntax
GOOGLEFINANCE(ticker, [attribute], [start_date], [end_date|num_days], [interval])

ticker - The ticker symbol for the security to consider. It’s mandatory to use both the exchange symbol and ticker symbol for accurate results and to avoid discrepancies. For example, use “NASDAQ:GOOG” instead of “GOOG.”

If the exchange symbol is not specified, GOOGLEFINANCE will use its best judgement to choose one for you.

Reuters Instrument Codes are no longer supported. Use TSE:123 or ASX:XYZ instead of ticker 123.TO or XYZ.AX.

Not all futures are supported at this time.

attribute - [ OPTIONAL - "price" by default ] - The attribute to fetch about ticker from Google Finance and is required if a date is specified.

attribute is one of the following for real-time data:

"price" - Real-time price quote, delayed by up to 20 minutes.

"priceopen" - The price as of market open.

"high" - The current day's high price.

"low" - The current day's low price.

"volume" - The current day's trading volume.

"marketcap" - The market capitalization of the stock.

"tradetime" - The time of the last trade.

"datadelay" - How far delayed the real-time data is.

"volumeavg" - The average daily trading volume.

"pe" - The price/earnings ratio.

"eps" - The earnings per share.

"high52" - The 52-week high price.

"low52" - The 52-week low price.

"change" - The price change since the previous trading day's close.

"beta" - The beta value.

"changepct" - The percentage change in price since the previous trading day's close.

"closeyest" - The previous day's closing price.

"shares" - The number of outstanding shares.

"currency" - The currency in which the security is priced. Currencies don't have trading windows, so open, low, high, and volume won't return for this argument.

attribute is one of the following for historical data:

"open" - The opening price for the specified date(s).

"close" - The closing price for the specified date(s).

"high" - The high price for the specified date(s).

"low" - The low price for the specified date(s).

"volume" - The volume for the specified date(s).

"all" - All of the above.

attribute is one of the following for mutual fund data:

"closeyest" - The previous day's closing price.

"date" - The date at which the net asset value was reported.

"returnytd" - The year-to-date return.

"netassets" - The net assets.

"change" - The change in the most recently reported net asset value and the one immediately prior.

"changepct" - The percentage change in the net asset value.

"yieldpct" - The distribution yield, the sum of the prior 12 months' income distributions (stock dividends and fixed income interest payments) and net asset value gains divided by the previous month's net asset value number.

"returnday" - One-day total return.

"return1" - One-week total return.

"return4" - Four-week total return.

"return13" - Thirteen-week total return.

"return52" - Fifty-two-week (annual) total return.

"return156" - 156-week (3-year) total return.

"return260" - 260-week (5-year) total return.

"incomedividend" - The amount of the most recent cash distribution.

"incomedividenddate" - The date of the most recent cash distribution.

"capitalgain" - The amount of the most recent capital gain distribution.

"morningstarrating" - The Morningstar "star" rating.

"expenseratio" - The fund's expense ratio.

start_date - [ OPTIONAL ] - The start date when fetching historical data.

If start_date is specified but end_date|num_days is not, only the single day's data is returned.
end_date|num_days - [ OPTIONAL ] - The end date when fetching historical data, or the number of days from start_date for which to return data.

interval - [ OPTIONAL ] - The frequency of returned data; either "DAILY" or "WEEKLY".

interval can alternatively be specified as 1 or 7. Other numeric values are disallowed.
Notes
Usage restrictions: The data is not for financial industry professional use or use by other professionals at non-financial firms (including government entities). Professional use may be subject to additional licensing fees from a third-party data provider.

All parameters must be enclosed in quotation marks or be references to cells containing text. 
Important: A possible exception is when interval is specified as a number and when end_date|num_days is specified as a number of days.

Real-time results will be returned as a value within a single cell. Historical data, even for a single day, will be returned as an expanded array with column headers.

Some attributes may not yield results for all symbols.

If any date parameters are specified, the request is considered historical and only the historical attributes are allowed.
GOOGLEFINANCE is only available in English and does not support most international exchanges.

Historical data cannot be downloaded or accessed via the Sheets API or Apps Script. If you attempt to do so, you'll see a #N/A error in place of the values in the corresponding cells of your spreadsheet.

Quotes are not sourced from all markets and may be delayed up to 20 minutes. Information is provided 'as is' and solely for informational purposes, not for trading purposes or advice.

Google treats dates passed into GOOGLEFINANCE as as noon UTC time. Exchanges that close before that time may be shifted by a day.

# 
  } 
     ]}
```
[]()__****

# ****__
```


   
# source-https
#                                  Apache License 
                            Version 2.0, January 2004 
                         https://www.apache.org/licenses/ 
  
    TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION 
  
    1. Definitions. 
  
       "License" shall mean the terms and conditions for use, reproduction, 
       and distribution as defined by Sections 1 through 9 of this document. 
  
       "Licensor" shall mean the copyright owner or entity authorized by 
       the copyright owner that is granting the License. 
  
       "Legal Entity" shall mean the union of the acting entity and all 
       other entities that control, are controlled by, or are under common 
       control with that entity. For the purposes of this definition, 
       "control" means (i) the power, direct or indirect, to cause the 
       direction or management of such entity, whether by contract or 
       otherwise, or (ii) ownership of fifty percent (50%) or more of the 
       outstanding shares, or (iii) beneficial ownership of such entity. 
  
       "You" (or "Your") shall mean an individual or Legal Entity 
       exercising permissions granted by this License. 
  
       "Source" form shall mean the preferred form for making modifications, 
       including but not limited to software source code, documentation 
       source, and configuration files. 
  
       "Object" form shall mean any form resulting from mechanical 
       transformation or translation of a Source form, including but 
       not limited to compiled object code, generated documentation, 
       and conversions to other media types. 
  
       "Work" shall mean the work of authorship, whether in Source or 
       Object form, made available under the License, as indicated by a 
       copyright notice that is included in or attached to the work 
       (an example is provided in the Appendix below). 
  
       "Derivative Works" shall mean any work, whether in Source or Object 
       form, that is based on (or derived from) the Work and for which the 
       editorial revisions, annotations, elaborations, or other modifications 
       represent, as a whole, an original work of authorship. For the purposes 
       of this License, Derivative Works shall not include works that remain 
       separable from, or merely link (or bind by name) to the interfaces of, 
       the Work and Derivative Works thereof. 
  
       "Contribution" shall mean any work of authorship, including 
       the original version of the Work and any modifications or additions 
       to that Work or Derivative Works thereof, that is intentionally 
       submitted to Licensor for inclusion in the Work by the copyright owner 
       or by an individual or Legal Entity authorized to submit on behalf of 
       the copyright owner. For the purposes of this definition, "submitted" 
       means any form of electronic, verbal, or written communication sent 
       to the Licensor or its representatives, including but not limited to 
       communication on electronic mailing lists, source code control systems, 
       and issue tracking systems that are managed by, or on behalf of, the 
       Licensor for the purpose of discussing and improving the Work, but 
       excluding communication that is conspicuously marked or otherwise 
       designated in writing by the copyright owner as "Not a Contribution." 
  
       "Contributor" shall mean Licensor and any individual or Legal Entity 
       on behalf of whom a Contribution has been received by Licensor and 
       subsequently incorporated within the Work. 
  
    2. Grant of Copyright License. Subject to the terms and conditions of 
       this License, each Contributor hereby grants to You a perpetual, 
       worldwide, non-exclusive, no-charge, royalty-free, irrevocable 
       copyright license to reproduce, prepare Derivative Works of, 
       publicly display, publicly perform, sublicense, and distribute the 
       Work and such Derivative Works in Source or Object form. 
  
    3. Grant of Patent License. Subject to the terms and conditions of 
       this License, each Contributor hereby grants to You a perpetual, 
       worldwide, non-exclusive, no-charge, royalty-free, irrevocable 
       (except as stated in this section) patent license to make, have made, 
       use, offer to sell, sell, import, and otherwise transfer the Work, 
       where such license applies only to those patent claims licensable 
       by such Contributor that are necessarily infringed by their 
       Contribution(s) alone or by combination of their Contribution(s) 
       with the Work to which such Contribution(s) was submitted. If You 
       institute patent litigation against any entity (including a 
       cross-claim or counterclaim in a lawsuit) alleging that the Work 
       or a Contribution incorporated within the Work constitutes direct 
       or contributory patent infringement, then any patent licenses 
       granted to You under this License for that Work shall terminate 
       as of the date such litigation is filed. 
  
    4. Redistribution. You may reproduce and distribute copies of the 
       Work or Derivative Works thereof in any medium, with or without 
       modifications, and in Source or Object form, provided that You 
       meet the following conditions: 
  
       (a) You must give any other recipients of the Work or 
           Derivative Works a copy of this License; and 
  
       (b) You must cause any modified files to carry prominent notices 
           stating that You changed the files; and 
  
       (c) You must retain, in the Source form of any Derivative Works 
           that You distribute, all copyright, patent, trademark, and 
           attribution notices from the Source form of the Work, 
           excluding those notices that do not pertain to any part of 
           the Derivative Works; and 
  
       (d) If the Work includes a "NOTICE" text file as part of its 
           distribution, then any Derivative Works that You distribute must 
           include a readable copy of the attribution notices contained 
           within such NOTICE file, excluding those notices that do not 
           pertain to any part of the Derivative Works, in at least one 
           of the following places: within a NOTICE text file distributed 
           as part of the Derivative Works; within the Source form or 
           documentation, if provided along with the Derivative Works; or, 
           within a display generated by the Derivative Works, if and 
           wherever such third-party notices normally appear. The contents 
           of the NOTICE file are for informational purposes only and 
           do not modify the License. You may add Your own attribution 
           notices within Derivative Works that You distribute, alongside 
           or as an addendum to the NOTICE text from the Work, provided 
           that such additional attribution notices cannot be construed 
           as modifying the License. 
  
       You may add Your own copyright statement to Your modifications and 
       may provide additional or different license terms and conditions 
       for use, reproduction, or distribution of Your modifications, or 
       for any such Derivative Works as a whole, provided Your use, 
       reproduction, and distribution of the Work otherwise complies with 
       the conditions stated in this License. 
  
    5. Submission of Contributions. Unless You explicitly state otherwise, 
       any Contribution intentionally submitted for inclusion in the Work 
       by You to the Licensor shall be under the terms and conditions of 
       this License, without any additional terms or conditions. 
       Notwithstanding the above, nothing herein shall supersede or modify 
       the terms of any separate license agreement you may have executed 
       with Licensor regarding such Contributions. 
  
    6. Trademarks. This License does not grant permission to use the trade 
       names, trademarks, service marks, or product names of the Licensor, 
       except as required for reasonable and customary use in describing the 
       origin of the Work and reproducing the content of the NOTICE file. 
  
    7. Disclaimer of Warranty. Unless required by applicable law or 
       agreed to in writing, Licensor provides the Work (and each 
       Contributor provides its Contributions) on an "AS IS" BASIS, 
       WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or 
       implied, including, without limitation, any warranties or conditions 
       of TITLE, NON-INFRINGEMENT, MERCHANTABILITY, or FITNESS FOR A 
       PARTICULAR PURPOSE. You are solely responsible for determining the 
       appropriateness of using or redistributing the Work and assume any 
       risks associated with Your exercise of permissions under this License. 
  
    8. Limitation of Liability. In no event and under no legal theory, 
       whether in tort (including negligence), contract, or otherwise, 
       unless required by applicable law (such as deliberate and grossly 
       negligent acts) or agreed to in writing, shall any Contributor be 
       liable to You for damages, including any direct, indirect, special, 
       incidental, or consequential damages of any character arising as a 
       result of this License or out of the use or inability to use the 
       Work (including but not limited to damages for loss of goodwill, 
       work stoppage, computer failure or malfunction, or any and all 
       other commercial damages or losses), even if such Contributor 
       has been advised of the possibility of such damages. 
  
    9. Accepting Warranty or Additional Liability. While redistributing 
       the Work or Derivative Works thereof, You may choose to offer, 
       and charge a fee for, acceptance of support, warranty, indemnity, 
       or other liability obligations and/or rights consistent with this 
       License. However, in accepting such obligations, You may act only 
       on Your own behalf and on Your sole responsibility, not on behalf 
       of any other Contributor, and only if You agree to indemnify, 
       defend, and hold each Contributor harmless for any liability 
       incurred by, or claims asserted against, such Contributor by reason 
       of your accepting any such warranty or additional liability. 
  
    END OF TERMS AND CONDITIONS 
  
    APPENDIX: How to apply the Apache License to your work. 
  
       To apply the Apache License to your work, attach the following 
       boilerplate notice, with the fields enclosed by brackets "{}" 
       replaced with your own identifying information. (Don't include 
       the brackets!)  The text should be enclosed in the appropriate 
       comment syntax for the file format. We also recommend that a 
       file or class name and description of purpose be included on the 
       same "printed page" as the copyright notice for easier 
       identification within third-party archives. 
  
    Copyright {yyyy} {name of copyright owner} 
  
    Licensed under the Apache License, Version 2.0 (the "License"); 
    you may not use this file except in compliance with the License. 
    You may obtain a copy of the License at 
  
        https://www.apache.org/licenses/LICENSE-2.0 
  
    Unless required by applicable law or agreed to in writing, software 
    distributed under the License is distributed on an "AS IS" BASIS, 
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. 
    See the License for the specific language governing permissions and 
    limitations under the License. 
 
# Boost Software License - Version 1.0 - August 17th, 2003 
  
 Permission is hereby granted, free of charge, to any person or organization 
 obtaining a copy of the software and accompanying documentation covered by 
 this license (the "Software") to use, reproduce, display, distribute, 
 execute, and transmit the Software, and to prepare derivative works of the 
 Software, and to permit third-parties to whom the Software is furnished to 
 do so, all subject to the following: 
  
 The copyright notices in the Software and this entire statement, including 
 the above license grant, this restriction and the following disclaimer, 
 must be included in all copies of the Software, in whole or in part, and 
 all derivative works of the Software, unless such copies or derivative 
 works are solely in the form of machine-executable object code generated by 
 a source language processor. 
  
 THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR 
 IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, 
 FITNESS FOR A PARTICULAR PURPOSE, TITLE AND NON-INFRINGEMENT. IN NO EVENT 
 SHALL THE COPYRIGHT HOLDERS OR ANYONE DISTRIBUTING THE SOFTWARE BE LIABLE 
 FOR ANY DAMAGES OR OTHER LIABILITY, WHETHER IN CONTRACT, TORT OR OTHERWISE, 
 ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER 
 DEALINGS IN THE SOFTWARE.


 # GNU GENERAL PUBLIC LICENSE 

 Version 3, 29 June 2007 
  
  Copyright (C) 2007 Free Software Foundation, Inc. <https://fsf.org/> 
  Everyone is permitted to copy and distribute verbatim copies 
  of this license document, but changing it is not allowed. 
  
                             Preamble 
  
   The GNU General Public License is a free, copyleft license for 
 software and other kinds of works. 
  
   The licenses for most software and other practical works are designed 
 to take away your freedom to share and change the works.  By contrast, 
 the GNU General Public License is intended to guarantee your freedom to 
 share and change all versions of a program--to make sure it remains free 
 software for all its users.  We, the Free Software Foundation, use the 
 GNU General Public License for most of our software; it applies also to 
 any other work released this way by its authors.  You can apply it to 
 your programs, too. 
  
   When we speak of free software, we are referring to freedom, not 
 price.  Our General Public Licenses are designed to make sure that you 
 have the freedom to distribute copies of free software (and charge for 
 them if you wish), that you receive source code or can get it if you 
 want it, that you can change the software or use pieces of it in new 
 free programs, and that you know you can do these things. 
  
   To protect your rights, we need to prevent others from denying you 
 these rights or asking you to surrender the rights.  Therefore, you have 
 certain responsibilities if you distribute copies of the software, or if 
 you modify it: responsibilities to respect the freedom of others. 
  
   For example, if you distribute copies of such a program, whether 
 gratis or for a fee, you must pass on to the recipients the same 
 freedoms that you received.  You must make sure that they, too, receive 
 or can get the source code.  And you must show them these terms so they 
 know their rights. 
  
   Developers that use the GNU GPL protect your rights with two steps: 
 (1) assert copyright on the software, and (2) offer you this License 
 giving you legal permission to copy, distribute and/or modify it. 
  
   For the developers' and authors' protection, the GPL clearly explains 
 that there is no warranty for this free software.  For both users' and 
 authors' sake, the GPL requires that modified versions be marked as 
 changed, so that their problems will not be attributed erroneously to 
 authors of previous versions. 
  
   Some devices are designed to deny users access to install or run 
 modified versions of the software inside them, although the manufacturer 
 can do so.  This is fundamentally incompatible with the aim of 
 protecting users' freedom to change the software.  The systematic 
 pattern of such abuse occurs in the area of products for individuals to 
 use, which is precisely where it is most unacceptable.  Therefore, we 
 have designed this version of the GPL to prohibit the practice for those 
 products.  If such problems arise substantially in other domains, we 
 stand ready to extend this provision to those domains in future versions 
 of the GPL, as needed to protect the freedom of users. 
  
   Finally, every program is threatened constantly by software patents. 
 States should not allow patents to restrict development and use of 
 software on general-purpose computers, but in those that do, we wish to 
 avoid the special danger that patents applied to a free program could 
 make it effectively proprietary.  To prevent this, the GPL assures that 
 patents cannot be used to render the program non-free. 
  
   The precise terms and conditions for copying, distribution and 
 modification follow. 
  
                        TERMS AND CONDITIONS 
  
   0. Definitions. 
  
   "This License" refers to version 3 of the GNU General Public License. 
  
   "Copyright" also means copyright-like laws that apply to other kinds of 
 works, such as semiconductor masks. 
  
   "The Program" refers to any copyrightable work licensed under this 
 License.  Each licensee is addressed as "you".  "Licensees" and 
 "recipients" may be individuals or organizations. 
  
   To "modify" a work means to copy from or adapt all or part of the work 
 in a fashion requiring copyright permission, other than the making of an 
 exact copy.  The resulting work is called a "modified version" of the 
 earlier work or a work "based on" the earlier work. 
  
   A "covered work" means either the unmodified Program or a work based 
 on the Program. 
  
   To "propagate" a work means to do anything with it that, without 
 permission, would make you directly or secondarily liable for 
 infringement under applicable copyright law, except executing it on a 
 computer or modifying a private copy.  Propagation includes copying, 
 distribution (with or without modification), making available to the 
 public, and in some countries other activities as well. 
  
   To "convey" a work means any kind of propagation that enables other 
 parties to make or receive copies.  Mere interaction with a user through 
 a computer network, with no transfer of a copy, is not conveying. 
  
   An interactive user interface displays "Appropriate Legal Notices" 
 to the extent that it includes a convenient and prominently visible 
 feature that (1) displays an appropriate copyright notice, and (2) 
 tells the user that there is no warranty for the work (except to the 
 extent that warranties are provided), that licensees may convey the 
 work under this License, and how to view a copy of this License.  If 
 the interface presents a list of user commands or options, such as a 
 menu, a prominent item in the list meets this criterion. 
  
   1. Source Code. 
  
   The "source code" for a work means the preferred form of the work 
 for making modifications to it.  "Object code" means any non-source 
 form of a work. 
  
   A "Standard Interface" means an interface that either is an official 
 standard defined by a recognized standards body, or, in the case of 
 interfaces specified for a particular programming language, one that 
 is widely used among developers working in that language. 
  
   The "System Libraries" of an executable work include anything, other 
 than the work as a whole, that (a) is included in the normal form of 
 packaging a Major Component, but which is not part of that Major 
 Component, and (b) serves only to enable use of the work with that 
 Major Component, or to implement a Standard Interface for which an 
 implementation is available to the public in source code form.  A 
 "Major Component", in this context, means a major essential component 
 (kernel, window system, and so on) of the specific operating system 
 (if any) on which the executable work runs, or a compiler used to 
 produce the work, or an object code interpreter used to run it. 
  
   The "Corresponding Source" for a work in object code form means all 
 the source code needed to generate, install, and (for an executable 
 work) run the object code and to modify the work, including scripts to 
 control those activities.  However, it does not include the work's 
 System Libraries, or general-purpose tools or generally available free 
 programs which are used unmodified in performing those activities but 
 which are not part of the work.  For example, Corresponding Source 
 includes interface definition files associated with source files for 
 the work, and the source code for shared libraries and dynamically 
 linked subprograms that the work is specifically designed to require, 
 such as by intimate data communication or control flow between those 
 subprograms and other parts of the work. 
  
   The Corresponding Source need not include anything that users 
 can regenerate automatically from other parts of the Corresponding 
 Source. 
  
   The Corresponding Source for a work in source code form is that 
 same work. 
  
   2. Basic Permissions. 
  
   All rights granted under this License are granted for the term of 
 copyright on the Program, and are irrevocable provided the stated 
 conditions are met.  This License explicitly affirms your unlimited 
 permission to run the unmodified Program.  The output from running a 
 covered work is covered by this License only if the output, given its 
 content, constitutes a covered work.  This License acknowledges your 
 rights of fair use or other equivalent, as provided by copyright law. 
  
   You may make, run and propagate covered works that you do not 
 convey, without conditions so long as your license otherwise remains 
 in force.  You may convey covered works to others for the sole purpose 
 of having them make modifications exclusively for you, or provide you 
 with facilities for running those works, provided that you comply with 
 the terms of this License in conveying all material for which you do 
 not control copyright.  Those thus making or running the covered works 
 for you must do so exclusively on your behalf, under your direction 
 and control, on terms that prohibit them from making any copies of 
 your copyrighted material outside their relationship with you. 
  
   Conveying under any other circumstances is permitted solely under 
 the conditions stated below.  Sublicensing is not allowed; section 10 
 makes it unnecessary. 
  
   3. Protecting Users' Legal Rights From Anti-Circumvention Law. 
  
   No covered work shall be deemed part of an effective technological 
 measure under any applicable law fulfilling obligations under article 
 11 of the WIPO copyright treaty adopted on 20 December 1996, or 
 similar laws prohibiting or restricting circumvention of such 
 measures. 
  
   When you convey a covered work, you waive any legal power to forbid 
 circumvention of technological measures to the extent such circumvention 
 is effected by exercising rights under this License with respect to 
 the covered work, and you disclaim any intention to limit operation or 
 modification of the work as a means of enforcing, against the work's 
 users, your or third parties' legal rights to forbid circumvention of 
 technological measures. 
  
   4. Conveying Verbatim Copies. 
  
   You may convey verbatim copies of the Program's source code as you 
 receive it, in any medium, provided that you conspicuously and 
 appropriately publish on each copy an appropriate copyright notice; 
 keep intact all notices stating that this License and any 
 non-permissive terms added in accord with section 7 apply to the code; 
 keep intact all notices of the absence of any warranty; and give all 
 recipients a copy of this License along with the Program. 
  
   You may charge any price or no price for each copy that you convey, 
 and you may offer support or warranty protection for a fee. 
  
   5. Conveying Modified Source Versions. 
  
   You may convey a work based on the Program, or the modifications to 
 produce it from the Program, in the form of source code under the 
 terms of section 4, provided that you also meet all of these conditions: 
  
     a) The work must carry prominent notices stating that you modified 
     it, and giving a relevant date. 
  
     b) The work must carry prominent notices stating that it is 
     released under this License and any conditions added under section 
     7.  This requirement modifies the requirement in section 4 to 
     "keep intact all notices". 
  
     c) You must license the entire work, as a whole, under this 
     License to anyone who comes into possession of a copy.  This 
     License will therefore apply, along with any applicable section 7 
     additional terms, to the whole of the work, and all its parts, 
     regardless of how they are packaged.  This License gives no 
     permission to license the work in any other way, but it does not 
     invalidate such permission if you have separately received it. 
  
     d) If the work has interactive user interfaces, each must display 
     Appropriate Legal Notices; however, if the Program has interactive 
     interfaces that do not display Appropriate Legal Notices, your 
     work need not make them do so. 
  
   A compilation of a covered work with other separate and independent 
 works, which are not by their nature extensions of the covered work, 
 and which are not combined with it such as to form a larger program, 
 in or on a volume of a storage or distribution medium, is called an 
 "aggregate" if the compilation and its resulting copyright are not 
 used to limit the access or legal rights of the compilation's users 
 beyond what the individual works permit.  Inclusion of a covered work 
 in an aggregate does not cause this License to apply to the other 
 parts of the aggregate. 
  
   6. Conveying Non-Source Forms. 
  
   You may convey a covered work in object code form under the terms 
 of sections 4 and 5, provided that you also convey the 
 machine-readable Corresponding Source under the terms of this License, 
 in one of these ways: 
  
     a) Convey the object code in, or embodied in, a physical product 
     (including a physical distribution medium), accompanied by the 
     Corresponding Source fixed on a durable physical medium 
     customarily used for software interchange. 
  
     b) Convey the object code in, or embodied in, a physical product 
     (including a physical distribution medium), accompanied by a 
     written offer, valid for at least three years and valid for as 
     long as you offer spare parts or customer support for that product 
     model, to give anyone who possesses the object code either (1) a 
     copy of the Corresponding Source for all the software in the 
     product that is covered by this License, on a durable physical 
     medium customarily used for software interchange, for a price no 
     more than your reasonable cost of physically performing this 
     conveying of source, or (2) access to copy the 
     Corresponding Source from a network server at no charge. 
  
     c) Convey individual copies of the object code with a copy of the 
     written offer to provide the Corresponding Source.  This 
     alternative is allowed only occasionally and noncommercially, and 
     only if you received the object code with such an offer, in accord 
     with subsection 6b. 
  
     d) Convey the object code by offering access from a designated 
     place (gratis or for a charge), and offer equivalent access to the 
     Corresponding Source in the same way through the same place at no 
     further charge.  You need not require recipients to copy the 
     Corresponding Source along with the object code.  If the place to 
     copy the object code is a network server, the Corresponding Source 
     may be on a different server (operated by you or a third party) 
     that supports equivalent copying facilities, provided you maintain 
     clear directions next to the object code saying where to find the 
     Corresponding Source.  Regardless of what server hosts the 
     Corresponding Source, you remain obligated to ensure that it is 
     available for as long as needed to satisfy these requirements. 
  
     e) Convey the object code using peer-to-peer transmission, provided 
     you inform other peers where the object code and Corresponding 
     Source of the work are being offered to the general public at no 
     charge under subsection 6d. 
  
   A separable portion of the object code, whose source code is excluded 
 from the Corresponding Source as a System Library, need not be 
 included in conveying the object code work. 
  
   A "User Product" is either (1) a "consumer product", which means any 
 tangible personal property which is normally used for personal, family, 
 or household purposes, or (2) anything designed or sold for incorporation 
 into a dwelling.  In determining whether a product is a consumer product, 
 doubtful cases shall be resolved in favor of coverage.  For a particular 
 product received by a particular user, "normally used" refers to a 
 typical or common use of that class of product, regardless of the status 
 of the particular user or of the way in which the particular user 
 actually uses, or expects or is expected to use, the product.  A product 
 is a consumer product regardless of whether the product has substantial 
 commercial, industrial or non-consumer uses, unless such uses represent 
 the only significant mode of use of the product. 
  
   "Installation Information" for a User Product means any methods, 
 procedures, authorization keys, or other information required to install 
 and execute modified versions of a covered work in that User Product from 
 a modified version of its Corresponding Source.  The information must 
 suffice to ensure that the continued functioning of the modified object 
 code is in no case prevented or interfered with solely because 
 modification has been made. 
  
   If you convey an object code work under this section in, or with, or 
 specifically for use in, a User Product, and the conveying occurs as 
 part of a transaction in which the right of possession and use of the 
 User Product is transferred to the recipient in perpetuity or for a 
 fixed term (regardless of how the transaction is characterized), the 
 Corresponding Source conveyed under this section must be accompanied 
 by the Installation Information.  But this requirement does not apply 
 if neither you nor any third party retains the ability to install 
 modified object code on the User Product (for example, the work has 
 been installed in ROM). 
  
   The requirement to provide Installation Information does not include a 
 requirement to continue to provide support service, warranty, or updates 
 for a work that has been modified or installed by the recipient, or for 
 the User Product in which it has been modified or installed.  Access to a 
 network may be denied when the modification itself materially and 
 adversely affects the operation of the network or violates the rules and 
 protocols for communication across the network. 
  
   Corresponding Source conveyed, and Installation Information provided, 
 in accord with this section must be in a format that is publicly 
 documented (and with an implementation available to the public in 
 source code form), and must require no special password or key for 
 unpacking, reading or copying. 
  
   7. Additional Terms. 
  
   "Additional permissions" are terms that supplement the terms of this 
 License by making exceptions from one or more of its conditions. 
 Additional permissions that are applicable to the entire Program shall 
 be treated as though they were included in this License, to the extent 
 that they are valid under applicable law.  If additional permissions 
 apply only to part of the Program, that part may be used separately 
 under those permissions, but the entire Program remains governed by 
 this License without regard to the additional permissions. 
  
   When you convey a copy of a covered work, you may at your option 
 remove any additional permissions from that copy, or from any part of 
 it.  (Additional permissions may be written to require their own 
 removal in certain cases when you modify the work.)  You may place 
 additional permissions on material, added by you to a covered work, 
 for which you have or can give appropriate copyright permission. 
  
   Notwithstanding any other provision of this License, for material you 
 add to a covered work, you may (if authorized by the copyright holders of 
 that material) supplement the terms of this License with terms: 
  
     a) Disclaiming warranty or limiting liability differently from the 
     terms of sections 15 and 16 of this License; or 
  
     b) Requiring preservation of specified reasonable legal notices or 
     author attributions in that material or in the Appropriate Legal 
     Notices displayed by works containing it; or 
  
     c) Prohibiting misrepresentation of the origin of that material, or 
     requiring that modified versions of such material be marked in 
     reasonable ways as different from the original version; or 
  
     d) Limiting the use for publicity purposes of names of licensors or 
     authors of the material; or 
  
     e) Declining to grant rights under trademark law for use of some 
     trade names, trademarks, or service marks; or 
  
     f) Requiring indemnification of licensors and authors of that 
     material by anyone who conveys the material (or modified versions of 
     it) with contractual assumptions of liability to the recipient, for 
     any liability that these contractual assumptions directly impose on 
     those licensors and authors. 
  
   All other non-permissive additional terms are considered "further 
 restrictions" within the meaning of section 10.  If the Program as you 
 received it, or any part of it, contains a notice stating that it is 
 governed by this License along with a term that is a further 
 restriction, you may remove that term.  If a license document contains 
 a further restriction but permits relicensing or conveying under this 
 License, you may add to a covered work material governed by the terms 
 of that license document, provided that the further restriction does 
 not survive such relicensing or conveying. 
  
   If you add terms to a covered work in accord with this section, you 
 must place, in the relevant source files, a statement of the 
 additional terms that apply to those files, or a notice indicating 
 where to find the applicable terms. 
  
   Additional terms, permissive or non-permissive, may be stated in the 
 form of a separately written license, or stated as exceptions; 
 the above requirements apply either way. 
  
   8. Termination. 
  
   You may not propagate or modify a covered work except as expressly 
 provided under this License.  Any attempt otherwise to propagate or 
 modify it is void, and will automatically terminate your rights under 
 this License (including any patent licenses granted under the third 
 paragraph of section 11). 
  
   However, if you cease all violation of this License, then your 
 license from a particular copyright holder is reinstated (a) 
 provisionally, unless and until the copyright holder explicitly and 
 finally terminates your license, and (b) permanently, if the copyright 
 holder fails to notify you of the violation by some reasonable means 
 prior to 60 days after the cessation. 
  
   Moreover, your license from a particular copyright holder is 
 reinstated permanently if the copyright holder notifies you of the 
 violation by some reasonable means, this is the first time you have 
 received notice of violation of this License (for any work) from that 
 copyright holder, and you cure the violation prior to 30 days after 
 your receipt of the notice. 
  
   Termination of your rights under this section does not terminate the 
 licenses of parties who have received copies or rights from you under 
 this License.  If your rights have been terminated and not permanently 
 reinstated, you do not qualify to receive new licenses for the same 
 material under section 10. 
  
   9. Acceptance Not Required for Having Copies. 
  
   You are not required to accept this License in order to receive or 
 run a copy of the Program.  Ancillary propagation of a covered work 
 occurring solely as a consequence of using peer-to-peer transmission 
 to receive a copy likewise does not require acceptance.  However, 
 nothing other than this License grants you permission to propagate or 
 modify any covered work.  These actions infringe copyright if you do 
 not accept this License.  Therefore, by modifying or propagating a 
 covered work, you indicate your acceptance of this License to do so. 
  
   10. Automatic Licensing of Downstream Recipients. 
  
   Each time you convey a covered work, the recipient automatically 
 receives a license from the original licensors, to run, modify and 
 propagate that work, subject to this License.  You are not responsible 
 for enforcing compliance by third parties with this License. 
  
   An "entity transaction" is a transaction transferring control of an 
 organization, or substantially all assets of one, or subdividing an 
 organization, or merging organizations.  If propagation of a covered 
 work results from an entity transaction, each party to that 
 transaction who receives a copy of the work also receives whatever 
 licenses to the work the party's predecessor in interest had or could 
 give under the previous paragraph, plus a right to possession of the 
 Corresponding Source of the work from the predecessor in interest, if 
 the predecessor has it or can get it with reasonable efforts. 
  
   You may not impose any further restrictions on the exercise of the 
 rights granted or affirmed under this License.  For example, you may 
 not impose a license fee, royalty, or other charge for exercise of 
 rights granted under this License, and you may not initiate litigation 
 (including a cross-claim or counterclaim in a lawsuit) alleging that 
 any patent claim is infringed by making, using, selling, offering for 
 sale, or importing the Program or any portion of it. 
  
   11. Patents. 
  
   A "contributor" is a copyright holder who authorizes use under this 
 License of the Program or a work on which the Program is based.  The 
 work thus licensed is called the contributor's "contributor version". 
  
   A contributor's "essential patent claims" are all patent claims 
 owned or controlled by the contributor, whether already acquired or 
 hereafter acquired, that would be infringed by some manner, permitted 
 by this License, of making, using, or selling its contributor version, 
 but do not include claims that would be infringed only as a 
 consequence of further modification of the contributor version.  For 
 purposes of this definition, "control" includes the right to grant 
 patent sublicenses in a manner consistent with the requirements of 
 this License. 
  
   Each contributor grants you a non-exclusive, worldwide, royalty-free 
 patent license under the contributor's essential patent claims, to 
 make, use, sell, offer for sale, import and otherwise run, modify and 
 propagate the contents of its contributor version. 
  
   In the following three paragraphs, a "patent license" is any express 
 agreement or commitment, however denominated, not to enforce a patent 
 (such as an express permission to practice a patent or covenant not to 
 sue for patent infringement).  To "grant" such a patent license to a 
 party means to make such an agreement or commitment not to enforce a 
 patent against the party. 
  
   If you convey a covered work, knowingly relying on a patent license, 
 and the Corresponding Source of the work is not available for anyone 
 to copy, free of charge and under the terms of this License, through a 
 publicly available network server or other readily accessible means, 
 then you must either (1) cause the Corresponding Source to be so 
 available, or (2) arrange to deprive yourself of the benefit of the 
 patent license for this particular work, or (3) arrange, in a manner 
 consistent with the requirements of this License, to extend the patent 
 license to downstream recipients.  "Knowingly relying" means you have 
 actual knowledge that, but for the patent license, your conveying the 
 covered work in a country, or your recipient's use of the covered work 
 in a country, would infringe one or more identifiable patents in that 
 country that you have reason to believe are valid. 
  
   If, pursuant to or in connection with a single transaction or 
 arrangement, you convey, or propagate by procuring conveyance of, a 
 covered work, and grant a patent license to some of the parties 
 receiving the covered work authorizing them to use, propagate, modify 
 or convey a specific copy of the covered work, then the patent license 
 you grant is automatically extended to all recipients of the covered 
 work and works based on it. 
  
   A patent license is "discriminatory" if it does not include within 
 the scope of its coverage, prohibits the exercise of, or is 
 conditioned on the non-exercise of one or more of the rights that are 
 specifically granted under this License.  You may not convey a covered 
 work if you are a party to an arrangement with a third party that is 
 in the business of distributing software, under which you make payment 
 to the third party based on the extent of your activity of conveying 
 the work, and under which the third party grants, to any of the 
 parties who would receive the covered work from you, a discriminatory 
 patent license (a) in connection with copies of the covered work 
 conveyed by you (or copies made from those copies), or (b) primarily 
 for and in connection with specific products or compilations that 
 contain the covered work, unless you entered into that arrangement, 
 or that patent license was granted, prior to 28 March 2007. 
  
   Nothing in this License shall be construed as excluding or limiting 
 any implied license or other defenses to infringement that may 
 otherwise be available to you under applicable patent law. 
  
   12. No Surrender of Others' Freedom. 
  
   If conditions are imposed on you (whether by court order, agreement or 
 otherwise) that contradict the conditions of this License, they do not 
 excuse you from the conditions of this License.  If you cannot convey a 
 covered work so as to satisfy simultaneously your obligations under this 
 License and any other pertinent obligations, then as a consequence you may 
 not convey it at all.  For example, if you agree to terms that obligate you 
 to collect a royalty for further conveying from those to whom you convey 
 the Program, the only way you could satisfy both those terms and this 
 License would be to refrain entirely from conveying the Program. 
  
   13. Use with the GNU Affero General Public License. 
  
   Notwithstanding any other provision of this License, you have 
 permission to link or combine any covered work with a work licensed 
 under version 3 of the GNU Affero General Public License into a single 
 combined work, and to convey the resulting work.  The terms of this 
 License will continue to apply to the part which is the covered work, 
 but the special requirements of the GNU Affero General Public License, 
 section 13, concerning interaction through a network will apply to the 
 combination as such. 
  
   14. Revised Versions of this License. 
  
   The Free Software Foundation may publish revised and/or new versions of 
 the GNU General Public License from time to time.  Such new versions will 
 be similar in spirit to the present version, but may differ in detail to 
 address new problems or concerns. 
  
   Each version is given a distinguishing version number.  If the 
 Program specifies that a certain numbered version of the GNU General 
 Public License "or any later version" applies to it, you have the 
 option of following the terms and conditions either of that numbered 
 version or of any later version published by the Free Software 
 Foundation.  If the Program does not specify a version number of the 
 GNU General Public License, you may choose any version ever published 
 by the Free Software Foundation. 
  
   If the Program specifies that a proxy can decide which future 
 versions of the GNU General Public License can be used, that proxy's 
 public statement of acceptance of a version permanently authorizes you 
 to choose that version for the Program. 
  
   Later license versions may give you additional or different 
 permissions.  However, no additional obligations are imposed on any 
 author or copyright holder as a result of your choosing to follow a 
 later version. 
  
   15. Disclaimer of Warranty. 
  
   THERE IS NO WARRANTY FOR THE PROGRAM, TO THE EXTENT PERMITTED BY 
 APPLICABLE LAW.  EXCEPT WHEN OTHERWISE STATED IN WRITING THE COPYRIGHT 
 HOLDERS AND/OR OTHER PARTIES PROVIDE THE PROGRAM "AS IS" WITHOUT WARRANTY 
 OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, 
 THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR 
 PURPOSE.  THE ENTIRE RISK AS TO THE QUALITY AND PERFORMANCE OF THE PROGRAM 
 IS WITH YOU.  SHOULD THE PROGRAM PROVE DEFECTIVE, YOU ASSUME THE COST OF 
 ALL NECESSARY SERVICING, REPAIR OR CORRECTION. 
  
   16. Limitation of Liability. 
  
   IN NO EVENT UNLESS REQUIRED BY APPLICABLE LAW OR AGREED TO IN WRITING 
 WILL ANY COPYRIGHT HOLDER, OR ANY OTHER PARTY WHO MODIFIES AND/OR CONVEYS 
 THE PROGRAM AS PERMITTED ABOVE, BE LIABLE TO YOU FOR DAMAGES, INCLUDING ANY 
 GENERAL, SPECIAL, INCIDENTAL OR CONSEQUENTIAL DAMAGES ARISING OUT OF THE 
 USE OR INABILITY TO USE THE PROGRAM (INCLUDING BUT NOT LIMITED TO LOSS OF 
 DATA OR DATA BEING RENDERED INACCURATE OR LOSSES SUSTAINED BY YOU OR THIRD 
 PARTIES OR A FAILURE OF THE PROGRAM TO OPERATE WITH ANY OTHER PROGRAMS), 
 EVEN IF SUCH HOLDER OR OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF 
 SUCH DAMAGES. 
  
   17. Interpretation of Sections 15 and 16. 
  
   If the disclaimer of warranty and limitation of liability provided 
 above cannot be given local legal effect according to their terms, 
 reviewing courts shall apply local law that most closely approximates 
 an absolute waiver of all civil liability in connection with the 
 Program, unless a warranty or assumption of liability accompanies a 
 copy of the Program in return for a fee. 
  
                      END OF TERMS AND CONDITIONS 
  
             How to Apply These Terms to Your New Programs 
  
   If you develop a new program, and you want it to be of the greatest 
 possible use to the public, the best way to achieve this is to make it 
 free software which everyone can redistribute and change under these terms. 
  
   To do so, attach the following notices to the program.  It is safest 
 to attach them to the start of each source file to most effectively 
 state the exclusion of warranty; and each file should have at least 
 the "copyright" line and a pointer to where the full notice is found. 
  
     <one line to give the program's name and a brief idea of what it does.> 
     Copyright (C) <year>  <name of author> 
  
     This program is free software: you can redistribute it and/or modify 
     it under the terms of the GNU General Public License as published by 
     the Free Software Foundation, either version 3 of the License, or 
     (at your option) any later version. 
  
     This program is distributed in the hope that it will be useful, 
     but WITHOUT ANY WARRANTY; without even the implied warranty of 
     MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the 
     GNU General Public License for more details. 
  
     You should have received a copy of the GNU General Public License 
     along with this program.  If not, see <https://www.gnu.org/licenses/>. 
  
 Also add information on how to contact you by electronic and paper mail. 
  
   If the program does terminal interaction, make it output a short 
 notice like this when it starts in an interactive mode: 
  
     <program>  Copyright (C) <year>  <name of author> 
     This program comes with ABSOLUTELY NO WARRANTY; for details type `show w'. 
     This is free software, and you are welcome to redistribute it 
     under certain conditions; type `show c' for details. 
  
 The hypothetical commands `show w' and `show c' should show the appropriate 
 parts of the General Public License.  Of course, your program's commands 
 might be different; for a GUI interface, you would use an "about box". 
  
   You should also get your employer (if you work as a programmer) or school, 
 if any, to sign a "copyright disclaimer" for the program, if necessary. 
 For more information on this, and how to apply and follow the GNU GPL, see 
 <https://www.gnu.org/licenses/>. 
  
   The GNU General Public License does not permit incorporating your program 
 into proprietary programs.  If your program is a subroutine library, you 
 may consider it more useful to permit linking proprietary applications with 
 the library.  If this is what you want to do, use the GNU Lesser General 
 Public License instead of this License.  But first, please read 
 <https://www.gnu.org/licenses/why-not-lgpl.html>.

https://docs.github.com/github/administering-a-repository/configuration-options-for-dependency-updates

# Security Policy 
  
 ## Supported Versions 
  
 Use this section to tell people about which versions of your project are 
 currently being supported with security updates. 
  
 | Version | Supported          | 
 | ------- | ------------------ | 
 | 5.1.x   | :white_check_mark: | 
 | 5.0.x   | :x:                | 
 | 4.0.x   | :white_check_mark: | 
 | < 4.0   | :x:                | 
  
 ## Reporting a Vulnerability 
  
 Use this section to tell people how to report a vulnerability. 
  
 Tell them where to go, how often they can expect to get an update on a 
 reported vulnerability, what to expect if the vulnerability is accepted or 
 declined, etc.

#dependanot 

# To get started with Dependabot version updates, you'll need to specify which 
 # package ecosystems to update and where the package manifests are located. 
 # Please see the documentation for all configuration options: 
 # https://docs.github.com/github/administering-a-repository/configuration-options-for-dependency-updates 
  
 version: 2 
 updates: 
   - package-ecosystem: "" # See documentation for possible values 
     directory: "/" # Location of package manifests 
     schedule: 
       interval: "weekly"

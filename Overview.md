# System Integration
## Challenges
### Business Silos
#### Do not share data (`Silo leader did not think of this, has no overview`)
#### Spaghetti Integrations (`Sign that things are not OK, lack of maturity`)
##### No Documentation (`Dont know which integrations are in the company, cannot optimize, solution: documentation/flow charts`)
##### Unstructured (`No plan for why/when/how integrations are made`)
##### Redundant Integrations (`With no overview, redundant integrations are made`)
#### Siloed Business Systems (`Management dit not think of integrating across departments`)
### Many applications
#### Legacy Systems (`No access -> Scraping/direct database/file share`)
#### Different formats (`XML/JSON/CSV`)
#### Different Semantics (`Customer/Invoice -> Semantic Interoperability, Solved by [Shared format] in ESB`)
#### Competitors (`More agile, flexible in the marketplace`)
### Integration Formats
#### CSV
##### Benefit: `Easy to read, rows and columns (tabular), simple, suported by legacy systems`
##### Drawback: `No hierarchy, no type checking, not good for shared format (no hierarchy and no meaning)`
##### _Related:_ `Bank, invoice, legacy systems exports using CSV`
#### JSON
##### Benefit: `Hierarchical, self described, well known by web`
##### Drawback: `Type checking (no single schema definition), null values (not present)`
##### _Related_: `Modern Web services uses JSON (communication)`
#### XML
##### Benefit: `Hierarchical, self described, highly extendible, strong schema definition (XSD), native transformation (XSLT)`
##### Drawback: `Overhead (more text is transported)`
##### Related: `Old web services(SOAP) uses XML`
#### _Related:_ `Shared format pattern in ESB, how other systems communicate, write translators (EIP)`
## Integration Types
### Shared File
#### _Benefit:_ `Easy access, legacy systems, shared folder/dropbox/one drive/FTP`
#### _Drawback:_ `Data only, no events/logic, when to integrate, naming conventions, stale data, locking file, hard to maintain/change`
#### _Related:_ `Challenges -> Integrating many/legacy systems, Document message (EIP)`
### Shared Database
#### _Benefit:_ `Easy access to data, write triggers/Stored procedures, no locking problems, ACID properties`
#### _Drawback:_ `Cant move online systems into database, hard to move existing systems, only data/no events/logic, hard to maintain/change`
#### _Related:_ `Shared file, Document message (EIP)`
### RPC
#### _Benefit:_ `Typically SDK available, easy to program, well documented?, known programming model`
#### _Drawback:_ `Tight coupled with source system (e.g. SDK in C#/PHP), hard to replace, interface boundaries are blurry, Synchronous communication?, Know endpoint(s), destination needs to be up/running`
#### _Related:_ `Agnostic SOA, Messaging->Loose coupling, Command Message (EIP)`
### Messaging
#### _Benefit:_ `Asynchronous, fire and forget, no knowledge of other systems, very flexible/loose coupled, not all systems online at same time`
#### _Drawback:_ `Hard to get started, Other mindset, trivial tasks may seem hard (e.g. add/subtract)`
#### _Related:_ `Everything related to ESB, Communication in SOA (carefull - SOA is Agnostic)`
## Web Services
### WCF (Typically XML)
#### _Benefit:_ `Easy to get started, know in Microsoft world, uses SOAP, easy mapping from format to objects`
#### _Drawback:_ `Works best in Microsoft world, Synchronous (blocking), invoke function`
#### _Related:_ `Integrate between many/different systems, Adapter Pattern (EIP), RPC under Integration Types, Command Message under ESB->Message Type`
### REST (Typically JSON)
#### _Benefit:_ `Well known format, indexes ressource, Most API uses REST`
#### _Drawback:_ `...`
#### _Related:_ `Integrate between many/different systems, Adapter Pattern (EIP), RPC under Integration Types (HTTP VERBS), Command Message under ESB->Message Type (HTTP VERBS)`
### WSDL (XML)
#### _Benefit:_ `Easy to discover service capabilities, strong schemas, able to autogenerate client stub`
#### _Drawback:_ `Rigid format, very strict`
#### _Related:_ `Service Discoverability/Repository under SOA`
### SOAP
#### _Benefit:_ `Easy to read and understand, Has header/Body/Envelope structure, wrapped by technology (e.g. WCF), can express RPC and results`
#### _Drawback:_ `Legacy (most use REST now), need tooling, not all languages/platforms can support this`
#### _Related:_ `Integrating with many/legacy systems, Command message (EIP), Document message (EIP)`
## SOA
### Business
#### Goal 1: Business / IT Alignment
##### Align IT with the business goals and strategy
##### Trace services back to business needs
##### Services are defined by business/strategy goals
##### Establish a general Business Architecture
##### Align IT Resources with business needs
#### Goal 2: Business Agility
##### Quickly react to new demands and opportunities in the marketplace
##### Build *Interoperable*, *Standardized*, *Reusable*, *Composable Services*
#### Goal 3: Cost Saving
##### Costs will drop because of service reuse
##### Remove redundant integrations (e.g. from mergers and aquisitions)
##### Consolidate redundant integrations - composable services
##### Platform independent: Business can pick best systems
### Agnostic
#### _Benefit:_ `Not dependent on a single language/platform/vendor`
#### _Drawback:_ `Many options, hard to pick, developer dependency?`
### Application Frontend
### Services
#### Service Layers
### Service Bus
### Service Repository
## ESB
### General
### Patterns
#### Channel
#### Routers
#### Transformation

# Model

## Knowledge Based Architecture

The clinical knowledge is, by its nature, mutable and context-dependent, and contexts too are very diverse and often change. To allow the functionality to serve the clinicians the best, we need to have an architecture that allows change in the behavior of the system to keep up with the changes in knowledge and contexts.

All clinical applications in IndiMR system are built with the aim to surface all clinically relevant functionality to be freely modifiable by the primary end-users, the healthcare professionals. 

All functionality that is not mutable can be created as in  traditional software systems. 

To allow the adaptability needed for changing clinical knowledge and requirements, the system will have two layers, one that provides the relatively fixed functionality and an adaptor to allows plugging in modifications. Knowledge Modules \(AKA Knowledge Data Modules, or KDMs\) represent the clinical knowledge, and can be dropped and removed easily into the KDM adaptor.

[Spotify Desktop Client's architecture ](https://www.quora.com/How-is-JavaScript-used-within-the-Spotify-desktop-application-Is-it-packaged-up-and-run-locally-only-retrieving-the-assets-as-and-when-needed-What-JavaScript-VM-is-used)has similar notions

[Bubble ](https://bubble.is/)has some ideas similar to what we propose here.

![](.gitbook/assets/image%20%288%29.png)

## Knowledge Represented by HL7 RIM as the Core

Clinical knowledge represented by the HL7 Reference Information Model will form the core of the IndiMR system. 

Following are the classes we will be predominantly using.

![](.gitbook/assets/image%20%2817%29.png)

We will create an event-centric enhancement of the model.

![](.gitbook/assets/image%20%2811%29.png)

## Knowledge Data Module

![](.gitbook/assets/image%20%283%29.png)

The values of the Observation class will be encapsulated as _**Inputs**_ of the **Knowledge Data Modules \(KDMs\)**. The KDM is wholly functioning self contained module which takes _**Inputs**_ and produces and _**Output**_. It uses a **Transform Engine** \(**TE**\) to create the output. The TE could be any software component, such as a rule engine, or a visualization engine. The output would be data in any of the acceptable formats, e.g., String, Number, Image, Audio or Video. The KDMs could also be repurposed as **AppEls**.

## The Ecosystem of IndiMR Knowledge Management

![](.gitbook/assets/image%20%286%29.png)

The ecosystem is a set of tools and repositories aimed at facilitating authoring  and use of KDMs easily and quickly by even non-computer people.

### **Knowledge Portal**

Knowledge Portal is a central location for all reusable parts, which can be assembled to create KDMs, available in four repositories.

The four repositories in the Knowledge Portal are:

1. **KDM repository**, where the KDM authors deposit the KDMs they build using other components.
2. **Data element Repository**, which contains data elements that are based on ISO/IEC 11179 standard, with each data element part being grounded in a concept, a semantic anchor from UMLS, SNOMED-CT, CPT, LOINC or RxNorm.
3. **TE Knowledge Repository** contains the logic and algorithms that  Transform Engines use to create outputs, using the data of the inputs.
4. **TE Store**: though not strictly knowledge content, for reasons of convenience, TEs are made available for download from the Knowledge Portal. TEs are binary software components in a wrapper compliant with the IndiMR system.TEs use TE specific knowledge to create transforms within the KDMs.

### Authoring Tools

These are tools to be used by non-software experts to author KDMs.

1. **KDM Authoring tool**: Since much of everything is already pre-built, for all practical purposes, the KAT is a _composing_ tool. The other pieces are brought together to create the desired functionality for a KDM. Much of the operations are drag and drop.
2.  **TE Knowledge Authoring Tool**: The Transform Engines, to deliver logic specific for a situation that a KDM represents, will need to be tailored for it. TEKAT will allow doing this. For example, if the KDM relies upon rules, then the TE for will it will have to be a Rule Engine, and the TEKAT will allow authoring the rules that will work to create an inference that is useful for the situation that the KDM represents.

### SDKs

Software Development Kits are will be sets of tools that allow software developers to integrate third party software into the IndiMR, or to create mechanisms to allow IndiMR KDMs to be used in the applications developed by others.

1. **TE SDK** will allow using independently created tools and algorithms to be adapted for use as TEs for KDMs.Essentially the TE SDK will allow wrapping the tool into a component that can be used in KDM, by providing means to wire up its  inputs and outputs with those to conform with the TE API.
2. **CIS SDK** will allow creating the substratum in externally created Clinical Information Systems to allow adding the KDMs to introduce new functionality in those applications. 

Once the SDKs are available, domain  experts without any specialized software development expertise will be able to create Clinical Applications that completely meet their needs and preferences.


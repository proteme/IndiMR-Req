---
description: >-
  This list is for the features and requirements that apply to the IndiMR system
  as a whole, excluding the user-facing features.
---

# General — System Aspects

### Cloud Storage

Although the index along with some summary information will be saved as a block in a blockchain for each patient, the actual storage will be in cloud \(see \#REQ-6\)

### Layers

Each domain within healthcare \(e.g., clinical, administrative, financial, personnel management etc.\) will be represented by its own layer. The ones with most dependencies on another layer, will be built on juxtaposed, on top of that layer. The clinical layer will of course be the core layer. see.

**however**: It is possible that just the clinical layer is the core and all the other layers are secondary to it alone.

### Inside Out — Clinical Process as the Core

Most EMRs were created by giving priority to the administrative and the business functions, and the functions that deal with the very core process of healthcare, the clinical process, were added in subsequently. This resulted in most of the systems not just being ill-suited for the use by the clinicians and other healthcare professionals, it made the systems fragile, because each time the core process had a new requirement, each of the system dependent on the core is required to create a proxy representation of the change in their own system.

In IndiMR, we plan on addressing the clinical process first, all other processes will be dependent on it, and not the other way around.

### Event Model

Each layer, beginning from the core, will have a set of events relevant to the core. Some of these events will be purely for the developers, but some of these will be surfaced to the end users, so that they use them as triggers to create/compose their own functionality.

### A framework that allows other components to be added easily

### Everything is an AppEL

See the presentation on [AppEls](https://drive.google.com/file/d/0B_Xhq_LX40MnenA1dlZ5cy1iUVE/edit?usp=sharing)

### Allow real time collaboration

Collaboration should be for joint data entry, modification of templates, rules or components by users

### Blockchain as index

### Automated data feeds

e.g., BP, Weight record from patient's sensors

### Semantic Metadata

### Element/Feature based security and privileges

Each feature/function/event is linked to the security privileges and each user is given access to a set of privileges

### WYSIWYG drag and drop UI configuration for individual or group of users

This should be metadata based and each configuration element should be shareable

### UI Conventions

Consistent navigation, hot keys, workflows, buttons and behaviors  
 A developer guideline will be developed so and every UI feature must conform to it.

### Knowledge Based System

See [Model](https://reqs.indimr.org/~/edit/drafts/-LGtTgl_Aw3EZhKaTf3p/model).

### Version Controlled Knowledge


### Relation Between Thread and Process

#### Commun

##### Data

- ID
- Register Set
- State
- Priority
- Data block
- Some shared resources of with PPID ([[File descriptor]], …)

##### Characteristics

The **entities** are independent once created. They can change their attributes after creation and generate new resources, but they can't access resources in other [[Thread]] and [[Process]] with **special mechanism** like [[Pipe]], …

#### NOt Commun

[[Process]]es don't share **addressing spaces**, contrary to [[Thread]].

The communication between [[Process]] is done thanks to [[Inter Process Communication]], while [[Thread]]s from a same [[Process]] use **shared variable**.

Child [[Process]]es have no control over other [[Process]]es, which is not the case for [[Thread]]. They can exert control over each other in the same [[Process]].
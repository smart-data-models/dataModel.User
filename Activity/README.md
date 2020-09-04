# Activity

## Description 

This entity represents the current activity performed by a User. It can be used in different scenarios,
from modeling social activities on a site (e.g. Federico shares a picture of his dog) to real life activities 
(e.g. Federico drives his car to work). The model is largely inspired by https://www.w3.org/TR/activitystreams-core.

The model represents user activities using the following predicate structure: (Agent, Verb, Object*, Target*), where Object and Target are optional.
The Agent is identified by the attribute refAgent, the Verb is identified by activityType, the Object is identified by refObject, and the Target is identified by refTarget.


Link to the [interactive specification](https://swagger.lab.fiware.org/?url=https://smart-data-models.github.io/dataModel.User/Activity/swagger.yaml)

Link to the [specification](https://smart-data-models.github.io/dataModel.User/Activity/doc/spec.md)

Link to the [example](https://smart-data-models.github.io/dataModel.User/Activity/examples/example.json) (keyvalues) for NGSI v2

Link to the [example](https://smart-data-models.github.io/dataModel.User/Activity/examples/example-normalized.json) (normalized) for NGSI-V2


 if you have any issue on this data model you can raise an issue or contribute with a PR
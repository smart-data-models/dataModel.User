# dataModel.User


The following entity types are available:
- [Activity](https://github.com/smart-data-models/dataModel.User/blob/master/Activity/README.md). This entity represents the current activity performed by a User. It can be used in different scenarios, from modeling social activities on a site (e.g. Federico shares a picture of his dog) to real life activities (e.g. Federico drives his car to work). The model is largely inspired by https://www.w3.org/TR/activitystreams-core.
The model represents user activities using the following predicate structure (Agent, Verb, Object*, Target*), where Object and Target are optional. The Agent is identified by the attribute refAgent, the Verb is identified by activityType, the Object is identified by refObject, and the Target is identified by refTarget.

- [UserContext](https://github.com/smart-data-models/dataModel.User/blob/master/UserContext/README.md). This data model describe the Context of a User. No personal data is encoded in the model. The actual
User data are stored in a different end point, as identified by the refUser property..



[Link](https://smart-data-models.github.io/dataModel.User//CONTRIBUTORS.yaml) to the 3 current contributors of the data models of this Subject.

You can raise an [issue](https://github.com/smart-data-models/dataModel.User/issues) or submit your [PR](https://github.com/smart-data-models/dataModel.User/pulls) on existing data models



Entity: Activity  
================  
This specification is a **temporal version**. It is automatically generated from the  documented properties described in the schema.json condensed into the file `model.yaml`. A temporary `new_model.yaml` file has been created in every data model to avoid impacting into existing scripts. Thus, the specification will be incomplete as long as the schema.json is not updated to the new format (documenting properties). Once updated the `model.yaml` (`new_model.yaml`) needs to be updated as well (automatically) . Further info in this [link](https://github.com/smart-data-models/data-models/blob/master/specs/warning_message_new_spec.md). As long as it is a provisional format any [feedback is welcomed in this form](https://smartdatamodels.org/index.php/submit-an-issue-2/) choosing option `Feedback on the new specification`  
Global description: **Information on the current activity performed by an anonymized user in a given point in time**  

## List of properties  

`activityType`:   `alternateName`: An alternative name for this item  `dataProvider`: A sequence of characters identifying the provider of the harmonised data entity.  `dateActivityEnded`:   `dateActivityStarted`:   `dateCreated`: Entity creation timestamp. This will usually be allocated by the storage platform.  `dateModified`: Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.  `description`: A description of this item  `id`:   `name`: The name of this item.  `owner`: A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)  `refAgent`:   `refObject`:   `refTarget`:   `seeAlso`:   `source`: A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.  `type`: NGSI Entity type  ## Data Model description of properties  
Sorted alphabetically  
```yaml  
Activity:    
  description: 'Information on the current activity performed by an anonymized user in a given point in time'    
  properties:    
    activityType:    
      type: string    
    alternateName:    
      description: 'An alternative name for this item'    
      type: Property    
    dataProvider:    
      description: 'A sequence of characters identifying the provider of the harmonised data entity.'    
      type: Property    
    dateActivityEnded:    
      format: date-time    
      type: string    
    dateActivityStarted:    
      format: date-time    
      type: string    
    dateCreated:    
      description: 'Entity creation timestamp. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: Property    
    dateModified:    
      description: 'Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: Property    
    description:    
      description: 'A description of this item'    
      type: Property    
    id:    
      anyOf: &activity_-_properties_-_owner_-_items_-_anyof    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
    name:    
      description: 'The name of this item.'    
      type: Property    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *activity_-_properties_-_owner_-_items_-_anyof    
      type: Property    
    refAgent:    
      anyOf:    
        - anyOf: *activity_-_properties_-_owner_-_items_-_anyof    
        - format: uri    
          type: string    
    refObject:    
      anyOf:    
        - anyOf: *activity_-_properties_-_owner_-_items_-_anyof    
        - format: uri    
          type: string    
    refTarget:    
      anyOf:    
        - anyOf: *activity_-_properties_-_owner_-_items_-_anyof    
        - format: uri    
          type: string    
    seeAlso:    
      oneOf:    
        - items:    
            - format: uri    
              type: string    
          minItems: 1    
          type: array    
        - format: uri    
          type: string    
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: Property    
    type:    
      description: 'NGSI Entity type'    
      enum:    
        - UserActivity    
      type: string    
  required:    
    - activityType    
    - refAgent    
    - type    
    - id    
  type: object    
```  
Here is an example of a Activity in JSON format as key-values. This is compatible with NGSI V2 when  using `options=keyValues` and returns the context data of an individual entity.  
```json  
{  
  "id": "UserActivity1",  
  "type": "UserActivity",  
  "activityType": "Drive",  
  "description": "User1 drive Car1 to Office1",  
  "dateActivityStarted": "2016-11-30T07:00:00.00Z",  
  "refObject": "Car1",  
  "refTarget": "Office1",  
  "refAgent": "User1"  
}  
```  
Here is an example of a Activity in JSON format as normalized. This is compatible with NGSI V2 when  using `options=keyValues` and returns the context data of an individual entity.  
```json  
{  
  "id": "UserActivity1",  
  "type": "UserActivity",  
  "description": {  
    "value": "User1 drive Car1 to Office1"  
  },  
  "refTarget": {  
    "type": "Relationship",  
    "value": "Office1"  
  },  
  "activityType": {  
    "value": "Drive"  
  },  
  "dateActivityStarted": {  
    "type": "DateTime",  
    "value": "2016-11-30T07:00:00.00Z"  
  },  
  "refAgent": {  
    "type": "Relationship",  
    "value": "User1"  
  },  
  "refObject": {  
    "type": "Relationship",  
    "value": "Car1"  
  }  
}  
```  
Here is an example of a Activity in JSON-LD format as key-values. This is compatible with NGSI-LD when not using options and returns the context data of an individual entity.  
```json  
{"@context": ["https://schema.lab.fiware.org/ld/context",  
              "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"],  
 "activityType": "Drive",  
 "dateActivityStarted": {"@type": "DateTime",  
                         "@value": "2016-11-30T07:00:00.00Z"},  
 "description": "User1 drive Car1 to Office1",  
 "id": "urn:ngsi-ld:UserActivity:UserActivity1",  
 "refAgent": "urn:ngsi-ld:Agent:User1",  
 "refObject": "urn:ngsi-ld:Object:Car1",  
 "refTarget": "urn:ngsi-ld:Target:Office1",  
 "type": "UserActivity"}  
```  
Here is an example of a Activity in JSON-LD format as normalized. This is compatible with NGSI-LD when not using options and returns the context data of an individual entity.  
```json  
{  
    "id": "urn:ngsi-ld:UserActivity:UserActivity1",  
    "type": "UserActivity",  
    "description": {  
        "type": "Property",  
        "value": "User1 drive Car1 to Office1"  
    },  
    "refTarget": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:Target:Office1"  
    },  
    "activityType": {  
        "type": "Property",  
        "value": "Drive"  
    },  
    "dateActivityStarted": {  
        "type": "Property",  
        "value": {  
            "@type": "DateTime",  
            "@value": "2016-11-30T07:00:00.00Z"  
        }  
    },  
    "refAgent": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:Agent:User1"  
    },  
    "refObject": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:Object:Car1"  
    },  
    "@context": [  
        "https://schema.lab.fiware.org/ld/context",  
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
    ]  
}  
```  

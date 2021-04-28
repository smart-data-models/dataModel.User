Entität: Aktivität  
==================  
[Offene Lizenz](https://github.com/smart-data-models//dataModel.User/blob/master/Activity/LICENSE.md)  
Globale Beschreibung: **Informationen über die aktuelle Aktivität, die ein anonymisierter Benutzer zu einem bestimmten Zeitpunkt durchgeführt hat**  

## Liste der Eigenschaften  

- `activityType`: Die durchgeführte Aktion (z. B. Fahren). Normative Referenzen: [https://schema.org/Action](https://schema.org/Action), [https://www.w3.org/TR/activitystreams-vocabulary/#activity-types](https://www.w3.org/TR/activitystreams-vocabulary/#activity-types), [https://health-lifesci.schema.org/PhysicalActivityCategory](https://health-lifesci.schema.org/PhysicalActivityCategory)  - `alternateName`: Ein alternativer Name für diesen Artikel  - `dataProvider`: Eine Folge von Zeichen, die den Anbieter der harmonisierten Dateneinheit identifiziert.  - `dateActivityEnded`: Zeitstempel für das Ende der Aktivität.  - `dateActivityStarted`: Sie muss gleich der UserActivity sein.  - `dateCreated`: Zeitstempel der Entitätserstellung. Dieser wird normalerweise von der Speicherplattform zugewiesen.  - `dateModified`: Zeitstempel der letzten Änderung der Entität. Dieser wird in der Regel von der Speicherplattform vergeben.  - `description`: Eine Beschreibung dieses Artikels  - `id`: Eindeutiger Bezeichner der Entität  - `name`: Der Name dieses Elements.  - `owner`: Eine Liste mit einer JSON-kodierten Zeichenfolge, die auf die eindeutigen Ids der Eigentümer verweist  - `refAgent`: Referenz auf den Agenten (d. h. eine Person), der die Aktivität ausführt. Dies kann eine andere NGSI-Entität oder ein beliebiger `Agent` sein, der durch einen URI identifiziert wird.  - `refObject`: Referenz auf das Objekt der Aktion (z. B. Auto1). Es kann ein anderes NGSI-Entity oder ein beliebiges `Objekt` sein, das durch einen URI identifiziert wird.  - `refTarget`: Verweis auf das Ziel der Aktion (z. B. Office1).  - `seeAlso`: Liste von uri, die auf zusätzliche Ressourcen über das Element verweist  - `source`: Eine Folge von Zeichen, die die ursprüngliche Quelle der Entitätsdaten als URL angibt. Empfohlen wird der voll qualifizierte Domänenname des Quellanbieters oder die URL zum Quellobjekt.  - `type`: NGSI Entity-Typ. Es muss UserActivity sein    
Erforderliche Eigenschaften  
- `activityType`  - `id`  - `refAgent`  - `type`    
Diese Entität stellt die aktuelle Aktivität dar, die von einem Benutzer ausgeführt wird. Sie kann in verschiedenen Szenarien verwendet werden, von der Modellierung sozialer Aktivitäten auf einer Site (z. B. Federico teilt ein Bild seines Hundes) bis hin zu Aktivitäten im realen Leben (z. B. Federico fährt mit seinem Auto zur Arbeit). Das Modell ist weitgehend inspiriert von [https://www.w3.org/TR/activitystreams-core](https://www.w3.org/TR/activitystreams-core). Das Modell repräsentiert Benutzeraktivitäten unter Verwendung der folgenden Prädikatsstruktur `(Agent, Verb, Objekt*, Ziel*)`, wobei `Objekt` und `Ziel` optional sind. Der `Agent` wird durch das Attribut `refAgent` identifiziert, das `Verb` wird durch `activityType` identifiziert, das `Object` wird durch `refObject` identifiziert und das `Target` wird durch `refTarget` identifiziert.  
## Datenmodell Beschreibung der Eigenschaften  
Alphabetisch sortiert (für Details anklicken)  
<details><summary><strong>full yaml details</strong></summary>    
```yaml  
Activity:    
  description: 'Information on the current activity performed by an anonymized user in a given point in time'    
  properties:    
    activityType:    
      description: "The action performed (e.g. Drive). Normative References: [https://schema.org/Action](https://schema.org/Action), [https://www.w3.org/TR/activitystreams-vocabulary/#activity-types](https://www.w3.org/TR/activitystreams-vocabulary/#activity-types), [https://health-lifesci.schema.org/PhysicalActivityCategory](https://health-lifesci.schema.org/PhysicalActivityCategory)"    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    alternateName:    
      description: 'An alternative name for this item'    
      type: Property    
    dataProvider:    
      description: 'A sequence of characters identifying the provider of the harmonised data entity.'    
      type: Property    
    dateActivityEnded:    
      description: 'Activity''s end timestamp.'    
      format: date-time    
      type: Property    
      x-ngsi:    
        model: https://schema.org/DateTime    
    dateActivityStarted:    
      description: 'It must be equal to UserActivity.'    
      format: date-time    
      type: Property    
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
      description: 'Unique identifier of the entity'    
      type: Property    
    name:    
      description: 'The name of this item.'    
      type: Property    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *activity_-_properties_-_owner_-_items_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      type: Property    
    refAgent:    
      anyOf:    
        - anyOf: *activity_-_properties_-_owner_-_items_-_anyof    
          description: 'Property. Unique identifier of the entity'    
        - format: uri    
          type: string    
      description: 'Reference to the agent (i.e. a person) performing the activity. It may be another NGSI Entity or any `Agent` identified by an URI.'    
      type: Relationship    
      x-ngsi:    
        model: https://schema.org/URL    
    refObject:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Reference to the object of the action (e.g. Car1). It may be another NGSI Entity or any `Object` identified by an URI.'    
      type: Relationship    
      x-ngsi:    
        model: https://schema.org/URL    
    refTarget:    
      anyOf:    
        - anyOf: *activity_-_properties_-_owner_-_items_-_anyof    
          description: 'Property. Unique identifier of the entity'    
        - format: uri    
          type: string    
      description: 'Reference to the target of the action (e.g. Office1).'    
      type: Relationship    
      x-ngsi:    
        model: https://schema.org/URL    
    seeAlso:    
      description: 'list of uri pointing to additional resources about the item'    
      oneOf:    
        - items:    
            - format: uri    
              type: string    
          minItems: 1    
          type: array    
        - format: uri    
          type: string    
      type: Property    
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: Property    
    type:    
      description: 'NGSI Entity type. It has to be UserActivity'    
      enum:    
        - UserActivity    
      type: Property    
  required:    
    - activityType    
    - refAgent    
    - type    
    - id    
  type: object    
```  
</details>    
## Beispiel-Nutzlasten  
#### Aktivität NGSI-v2-Schlüsselwerte Beispiel  
Hier ist ein Beispiel für eine Aktivität im JSON-LD-Format als Key-Values. Dies ist kompatibel mit NGSI-v2 bei Verwendung von `options=keyValues` und liefert die Kontextdaten einer einzelnen Entität.  
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
#### Aktivität NGSI-v2 normalisiert Beispiel  
Hier ist ein Beispiel für eine Aktivität im JSON-LD-Format in normalisierter Form. Dies ist kompatibel mit NGSI-v2, wenn keine Optionen verwendet werden, und gibt die Kontextdaten einer einzelnen Entität zurück.  
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
#### Aktivität NGSI-LD-Schlüsselwerte Beispiel  
Hier ist ein Beispiel für eine Aktivität im JSON-LD-Format als Key-Values. Dies ist kompatibel mit NGSI-LD bei Verwendung von `options=keyValues` und liefert die Kontextdaten einer einzelnen Entität.  
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
    "https://smartdatamodels.org/context.jsonld",  
    "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
  ]  
}  
```  
#### Aktivität NGSI-LD normalisiert Beispiel  
Hier ist ein Beispiel für eine Aktivität im JSON-LD-Format in normalisierter Form. Dies ist kompatibel mit NGSI-LD, wenn keine Optionen verwendet werden, und liefert die Kontextdaten einer einzelnen Entität.  
```json  
{  
  "@context": [  
    "https://smartdatamodels.org/context.jsonld",  
    "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
  ],  
  "activityType": "Drive",  
  "dateActivityStarted": {  
    "@type": "DateTime",  
    "@value": "2016-11-30T07:00:00.00Z"  
  },  
  "description": "User1 drive Car1 to Office1",  
  "id": "urn:ngsi-ld:UserActivity:UserActivity1",  
  "refAgent": "urn:ngsi-ld:Agent:User1",  
  "refObject": "urn:ngsi-ld:Object:Car1",  
  "refTarget": "urn:ngsi-ld:Target:Office1",  
  "type": "UserActivity"  
}  
```  

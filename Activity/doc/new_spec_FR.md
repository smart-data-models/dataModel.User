Entité : Activité :  
===================  
Cette spécification est une **version temporelle**. Elle est générée automatiquement à partir des propriétés documentées décrites dans le schema.json condensé dans le fichier `model.yaml`. Un fichier temporaire `nouveau_modèle.yaml` a été créé dans chaque modèle de données pour éviter l'impact sur les scripts existants. Ainsi, la spécification sera incomplète tant que le fichier schema.json n'est pas mis à jour au nouveau format (documentation des propriétés). Une fois mis à jour, le fichier `model.yaml` (`nouveau_model.yaml`) doit être mis à jour également (automatiquement) . Plus d'informations dans ce [lien](https://github.com/smart-data-models/data-models/blob/master/specs/warning_message_new_spec.md). Tant qu'il s'agit d'un format provisoire, tout [feedback est le bienvenu dans ce formulaire](https://smartdatamodels.org/index.php/submit-an-issue-2/) en choisissant l'option "Feedback sur la nouvelle spécification".  
Description globale : **Information sur l'activité en cours effectuée par un utilisateur anonyme à un moment donné**  

## Liste des biens  

- `activityType`: L'action effectuée (par exemple, conduire). Les références normatives : [https://schema.org/Action](https://schema.org/Action), [https://www.w3.org/TR/activitystreams-vocabulary/#activity-types](https://www.w3.org/TR/activitystreams-vocabulary/#activity-types), [https://health-lifesci.schema.org/PhysicalActivityCategory](https://health-lifesci.schema.org/PhysicalActivityCategory)  - `alternateName`: Un autre nom pour cet article  - `dataProvider`: Une séquence de caractères identifiant le fournisseur de l'entité de données harmonisées.  - `dateActivityEnded`: Horodatage de fin d'activité.  - `dateActivityStarted`: Elle doit être égale à l'activité des utilisateurs.  - `dateCreated`: Horodatage de la création de l'entité. Il est généralement attribué par la plate-forme de stockage.  - `dateModified`: Horodatage de la dernière modification de l'entité. Il est généralement attribué par la plate-forme de stockage.  - `description`: Une description de cet article  - `id`:   - `name`: Le nom de cet article.  - `owner`: Une liste contenant une séquence de caractères codés en JSON faisant référence aux Ids uniques du ou des propriétaires  - `refAgent`: Référence à l'agent (c'est-à-dire une personne) qui exerce l'activité. Il peut s'agir d'une autre entité du NGSI ou de tout "agent" identifié par un URI.  - `refObject`: Référence à l'objet de l'action (par exemple, Voiture1). Il peut s'agir d'une autre entité du NGSI ou de tout "objet" identifié par un URI.  - `refTarget`: Référence à la cible de l'action (par exemple, Office1).  - `seeAlso`: liste d'uri pointant vers des ressources supplémentaires sur le sujet  - `source`: Une séquence de caractères donnant comme URL la source originale des données de l'entité. Il est recommandé d'utiliser le nom de domaine complet du fournisseur de la source, ou l'URL de l'objet source.  - `type`: Type d'entité NGSI. Il doit s'agir de UserActivity    
Propriétés requises  
- `activityType`  - `id`  - `refAgent`  - `type`    
Cette entité représente l'activité courante effectuée par un Utilisateur. Elle peut être utilisée dans différents scénarios, de la modélisation des activités sociales sur un site (par exemple, Federico partage une photo de son chien) aux activités de la vie réelle (par exemple, Federico conduit sa voiture au travail). Le modèle est largement inspiré de [https://www.w3.org/TR/activitystreams-core](https://www.w3.org/TR/activitystreams-core). Le modèle représente les activités de l'utilisateur en utilisant la structure de prédicats suivante `(Agent, Verbe, Objet*, Cible*)`, où `Objet` et `Cible` sont facultatifs. L'"Agent" est identifié par l'attribut "refAgent", le "Verbe" est identifié par "ActivityType", l'"Objet" est identifié par "refObjet", et la "Cible" est identifiée par "refTarget".  
## Modèle de données description des biens  
Classement par ordre alphabétique (cliquez pour plus de détails)  
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
## Exemples de charges utiles  
#### Activité NGSI V2 valeurs clés Exemple  
Voici un exemple d'activité au format JSON comme valeurs clés. Ce format est compatible avec la version 2 de l'INSG lorsqu'il utilise "options=valeurs clés" et renvoie les données de contexte d'une entité individuelle.  
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
#### Activité NGSI V2 normalisée Exemple  
Voici un exemple d'activité au format JSON normalisé. Ce format est compatible avec la version 2 du NGSI lorsqu'il n'utilise pas d'options et renvoie les données de contexte d'une entité individuelle.  
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
#### Activité NGSI-LD valeurs clés Exemple  
Voici un exemple d'activité au format JSON-LD comme valeurs clés. Il est compatible avec le format NGSI-LD lorsqu'il utilise "options=keyValues" et renvoie les données de contexte d'une entité individuelle.  
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
#### Activité NGSI-LD normalisée Exemple  
Voici un exemple d'une activité au format JSON-LD telle que normalisée. Ce format est compatible avec JSON-LD lorsqu'il n'utilise pas d'options et renvoie les données de contexte d'une entité individuelle.  
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

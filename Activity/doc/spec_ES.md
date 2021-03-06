Entidad: Actividad  
==================  
[Licencia abierta](https://github.com/smart-data-models//dataModel.User/blob/master/Activity/LICENSE.md)  
Descripción global: **Información sobre la actividad actual realizada por un usuario anónimo en un momento dado**  

## Lista de propiedades  

- `activityType`: La acción realizada (por ejemplo, Drive). Referencias normativas: https://schema.org/Action](https://schema.org/Action), [https://www.w3.org/TR/activitystreams-vocabulary/#activity-types](https://www.w3.org/TR/activitystreams-vocabulary/#activity-types), [https://health-lifesci.schema.org/PhysicalActivityCategory](https://health-lifesci.schema.org/PhysicalActivityCategory)  - `alternateName`: Un nombre alternativo para este artículo  - `dataProvider`: Una secuencia de caracteres que identifica al proveedor de la entidad de datos armonizada.  - `dateActivityEnded`: La actividad termina en el tiempo.  - `dateActivityStarted`: Debe ser igual a UserActivity.  - `dateCreated`: Sello de tiempo de creación de la entidad. Normalmente será asignado por la plataforma de almacenamiento.  - `dateModified`: Sello de tiempo de la última modificación de la entidad. Esta será normalmente asignada por la plataforma de almacenamiento.  - `description`: Una descripción de este artículo  - `id`: Identificador único de la entidad  - `name`: El nombre de este artículo.  - `owner`: Una lista que contiene una secuencia de caracteres codificados JSON que hace referencia a los Ids únicos de los propietarios  - `refAgent`: Referencia al agente (es decir, una persona) que realiza la actividad. Puede ser otra entidad NGSI o cualquier "Agente" identificado por una URI.  - `refObject`: Referencia al objeto de la acción (por ejemplo, Car1). Puede ser otra Entidad NGSI o cualquier "Objeto" identificado por una URI.  - `refTarget`: Referencia al objetivo de la acción (por ejemplo, Office1).  - `seeAlso`: lista de uri que apunta a recursos adicionales sobre el tema  - `source`: Una secuencia de caracteres que da como URL la fuente original de los datos de la entidad. Se recomienda que sea el nombre de dominio completamente calificado del proveedor de la fuente, o la URL del objeto fuente.  - `type`: Tipo de entidad NGSI. Tiene que ser UserActivity    
Propiedades requeridas  
- `activityType`  - `id`  - `refAgent`  - `type`    
Esta entidad representa la actividad actual realizada por un Usuario. Puede utilizarse en diferentes escenarios, desde el modelado de actividades sociales en un sitio (por ejemplo, Federico comparte una foto de su perro) hasta actividades de la vida real (por ejemplo, Federico conduce su coche al trabajo). El modelo se inspira en gran medida en [https://www.w3.org/TR/activitystreams-core](https://www.w3.org/TR/activitystreams-core). El modelo representa las actividades de los usuarios utilizando la siguiente estructura predicada "Agente, Verbo, Objeto*, Objetivo*", donde "Objeto" y "Objetivo" son opcionales. El "Agente" se identifica por el atributo "refAgente", el "Verbo" se identifica por "Tipo de actividad", el "Objeto" se identifica por "refObjeto", y el "Objetivo" se identifica por "refObjetivo".  
## Modelo de datos Descripción de las propiedades  
Ordenados alfabéticamente (haga clic para ver los detalles)  
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
## Ejemplo de cargas útiles  
#### Actividad NGSI V2 valores clave Ejemplo  
Aquí hay un ejemplo de una actividad en formato JSON como valores clave. Esto es compatible con NGSI V2 cuando se usa "opciones=valores-clave" y devuelve los datos de contexto de una entidad individual.  
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
#### Actividad NGSI V2 normalizada Ejemplo  
Aquí hay un ejemplo de una actividad en formato JSON como normalizada. Esto es compatible con NGSI V2 cuando no se usan opciones y devuelve los datos de contexto de una entidad individual.  
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
#### Actividad NGSI-LD valores clave Ejemplo  
Aquí hay un ejemplo de una actividad en formato JSON-LD como valores clave. Esto es compatible con NGSI-LD cuando se usa "opciones=valores-clave" y devuelve los datos de contexto de una entidad individual.  
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
#### Actividad NGSI-LD normalizada Ejemplo  
Aquí hay un ejemplo de una actividad en formato JSON-LD normalizada. Esto es compatible con NGSI-LD cuando no se utilizan opciones y devuelve los datos de contexto de una entidad individual.  
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

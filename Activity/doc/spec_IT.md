Entità: Attività  
================
  

[Licenza aperta](https://github.com/smart-data-models//dataModel.User/blob/master/Activity/LICENSE.md)  

[documento generato automaticamente](https://docs.google.com/presentation/d/e/2PACX-1vTs-Ng5dIAwkg91oTTUdt8ua7woBXhPnwavZ0FxgR8BsAI_Ek3C5q97Nd94HS8KhP-r_quD4H0fgyt3/pub?start=false&loop=false&delayms=3000#slide=id.gb715ace035_0_60)  

Descrizione globale: **Informazioni sull'attività corrente eseguita da un utente reso anonimo in un dato momento**  


## Elenco delle proprietà  


- `activityType`: L'azione eseguita (ad es. Guidare). Riferimenti normativi: [https://schema.org/Action](https://schema.org/Action), [https://www.w3.org/TR/activitystreams-vocabulary/#activity-types](https://www.w3.org/TR/activitystreams-vocabulary/#activity-types), [https://health-lifesci.schema.org/PhysicalActivityCategory](https://health-lifesci.schema.org/PhysicalActivityCategory)  
- `alternateName`: Un nome alternativo per questa voce  
- `dataProvider`: Una sequenza di caratteri che identifica il fornitore dell'entità di dati armonizzata.  
- `dateActivityEnded`: Timestamp di fine attività.  
- `dateActivityStarted`: Deve essere uguale a UserActivity.  
- `dateCreated`: Timestamp di creazione dell'entità. Questo sarà di solito assegnato dalla piattaforma di archiviazione.  
- `dateModified`: Timestamp dell'ultima modifica dell'entità. Questo sarà di solito assegnato dalla piattaforma di archiviazione.  
- `description`: Una descrizione di questo articolo  
- `id`: Identificatore unico dell'entità  
- `name`: Il nome di questo articolo.  
- `owner`: Una lista contenente una sequenza di caratteri codificata in JSON che si riferisce agli ID unici dei proprietari  
- `refAgent`: Riferimento all'agente (cioè una persona) che esegue l'attività. Può essere un'altra entità NGSI o qualsiasi `Agente` identificato da un URI.  
- `refObject`: Riferimento all'oggetto dell'azione (es. Car1). Può essere un'altra entità NGSI o qualsiasi `Oggetto` identificato da un URI.  
- `refTarget`: Riferimento all'obiettivo dell'azione (ad esempio, Office1).  
- `seeAlso`: elenco di uri che puntano a risorse aggiuntive sull'elemento  
- `source`: Una sequenza di caratteri che dà la fonte originale dei dati dell'entità come URL. Si raccomanda di essere il nome di dominio completamente qualificato del fornitore di origine, o l'URL dell'oggetto di origine.  
- `type`: Tipo di entità NGSI. Deve essere UserActivity  
  

Proprietà richieste  
- `activityType`  
- `id`  
- `refAgent`  
- `type`  
  

Questa entità rappresenta l'attività corrente svolta da un utente. Può essere utilizzata in diversi scenari, dalla modellazione di attività sociali su un sito (ad esempio Federico condivide una foto del suo cane) alle attività della vita reale (ad esempio Federico guida la sua auto al lavoro). Il modello è ampiamente ispirato da [https://www.w3.org/TR/activitystreams-core](https://www.w3.org/TR/activitystreams-core). Il modello rappresenta le attività dell'utente usando la seguente struttura di predicati `(Agent, Verb, Object*, Target*)`, dove `Object` e `Target` sono opzionali. L' `Agente` è identificato dall'attributo `refAgente`, il `Verbo` è identificato da `activityType`, l' `Oggetto` è identificato da `refObject`, e il `Target` è identificato da `refTarget`.  

## Descrizione del modello di dati delle proprietà  

Ordinati in ordine alfabetico (clicca per i dettagli)  
<details><summary><strong>full yaml details</strong></summary>    

```yaml  
Activity:    
  description: 'Information on the current activity performed by an anonymized user in a given point in time'    
  properties:    
    activityType:    
      description: "The action performed (e.g. Drive). Normative References: [https://schema.org/Action](https://schema.org/Action), [https://www.w3.org/TR/activitystreams-vocabulary/#activity-types](https://www.w3.org/TR/activitystreams-vocabulary/#activity-types), [https://health-lifesci.schema.org/PhysicalActivityCategory](https://health-lifesci.schema.org/PhysicalActivityCategory)"    
      type: string    
      x-ngsi:    
        model: https://schema.org/Text    
        type: Property    
    alternateName:    
      description: 'An alternative name for this item'    
      type: string    
      x-ngsi:    
        type: Property    
    dataProvider:    
      description: 'A sequence of characters identifying the provider of the harmonised data entity.'    
      type: string    
      x-ngsi:    
        type: Property    
    dateActivityEnded:    
      description: 'Activity''s end timestamp.'    
      format: date-time    
      type: string    
      x-ngsi:    
        model: https://schema.org/DateTime    
        type: Property    
    dateActivityStarted:    
      description: 'It must be equal to UserActivity.'    
      format: date-time    
      type: string    
      x-ngsi:    
        type: Property    
    dateCreated:    
      description: 'Entity creation timestamp. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: string    
      x-ngsi:    
        type: Property    
    dateModified:    
      description: 'Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: string    
      x-ngsi:    
        type: Property    
    description:    
      description: 'A description of this item'    
      type: string    
      x-ngsi:    
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
      x-ngsi:    
        type: Property    
    name:    
      description: 'The name of this item.'    
      type: string    
      x-ngsi:    
        type: Property    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *activity_-_properties_-_owner_-_items_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      type: array    
      x-ngsi:    
        type: Property    
    refAgent:    
      anyOf:    
        - anyOf: *activity_-_properties_-_owner_-_items_-_anyof    
          description: 'Property. Unique identifier of the entity'    
        - format: uri    
          type: string    
      description: 'Reference to the agent (i.e. a person) performing the activity. It may be another NGSI Entity or any `Agent` identified by an URI.'    
      x-ngsi:    
        model: https://schema.org/URL    
        type: Relationship    
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
      x-ngsi:    
        model: https://schema.org/URL    
        type: Relationship    
    refTarget:    
      anyOf:    
        - anyOf: *activity_-_properties_-_owner_-_items_-_anyof    
          description: 'Property. Unique identifier of the entity'    
        - format: uri    
          type: string    
      description: 'Reference to the target of the action (e.g. Office1).'    
      x-ngsi:    
        model: https://schema.org/URL    
        type: Relationship    
    seeAlso:    
      description: 'list of uri pointing to additional resources about the item'    
      oneOf:    
        - items:    
            format: uri    
            type: string    
          minItems: 1    
          type: array    
        - format: uri    
          type: string    
      x-ngsi:    
        type: Property    
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: string    
      x-ngsi:    
        type: Property    
    type:    
      description: 'NGSI Entity type. It has to be UserActivity'    
      enum:    
        - UserActivity    
      type: string    
      x-ngsi:    
        type: Property    
  required:    
    - activityType    
    - refAgent    
    - type    
    - id    
  type: object    
```  
</details>    

## Esempio di payloads  

#### Attività Valori chiave NGSI-v2 Esempio  

Ecco un esempio di un'attività in formato JSON-LD come valori-chiave. Questo è compatibile con NGSI-v2 quando si usa `options=keyValues` e restituisce i dati di contesto di una singola entità.  

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

#### Attività NGSI-v2 normalizzata Esempio  

Ecco un esempio di un'attività in formato JSON-LD normalizzata. Questo è compatibile con NGSI-v2 quando non usa opzioni e restituisce i dati di contesto di una singola entità.  

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

#### Attività Valori chiave NGSI-LD Esempio  

Ecco un esempio di attività in formato JSON-LD come valori-chiave. Questo è compatibile con NGSI-LD quando si usa `options=keyValues` e restituisce i dati di contesto di una singola entità.  

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

#### Attività NGSI-LD normalizzata Esempio  

Ecco un esempio di un'attività in formato JSON-LD normalizzata. Questo è compatibile con NGSI-LD quando non usa opzioni e restituisce i dati di contesto di una singola entità.  

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

Vedere [FAQ 10](https://smartdatamodels.org/index.php/faqs/) per avere una risposta su come trattare le unità di grandezza

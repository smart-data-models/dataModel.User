<!-- 10-Header -->      
[![Smart Data Models](https://smartdatamodels.org/wp-content/uploads/2022/01/SmartDataModels_logo.png "Logo")](https://smartdatamodels.org)      
Entità: Attività      
================<!-- /10-Header -->      
<!-- 15-License -->      
[Licenza aperta](https://github.com/smart-data-models//dataModel.User/blob/master/Activity/LICENSE.md)      
[documento generato automaticamente](https://docs.google.com/presentation/d/e/2PACX-1vTs-Ng5dIAwkg91oTTUdt8ua7woBXhPnwavZ0FxgR8BsAI_Ek3C5q97Nd94HS8KhP-r_quD4H0fgyt3/pub?start=false&loop=false&delayms=3000#slide=id.gb715ace035_0_60)      
<!-- /15-License -->      
<!-- 20-Description -->      
Descrizione globale: **Informazioni sull'attività corrente svolta da un utente anonimo in un determinato momento**.      
versione: 0.1.1      
<!-- /20-Description -->      
<!-- 30-PropertiesList -->      
## Elenco delle proprietà      
<sup><sub>[*] Se non c'è un tipo in un attributo è perché potrebbe avere diversi tipi o diversi formati/modelli</sub></sup>.      
- `activityType[string]`: L'azione eseguita (ad esempio, l'azionamento). Riferimenti normativi: [https://schema.org/Action](https://schema.org/Action), [https://www.w3.org/TR/activitystreams-vocabulary/#activity-types](https://www.w3.org/TR/activitystreams-vocabulary/#activity-types), [https://health-lifesci.schema.org/PhysicalActivityCategory](https://health-lifesci.schema.org/PhysicalActivityCategory)  . Model: [https://schema.org/Text](https://schema.org/Text)- `address[object]`: L'indirizzo postale  . Model: [https://schema.org/address](https://schema.org/address)	- `addressCountry[string]`: Il paese. Ad esempio, la Spagna  . Model: [https://schema.org/addressCountry](https://schema.org/addressCountry)      
	- `addressLocality[string]`: La località in cui si trova l'indirizzo civico e che si trova nella regione  . Model: [https://schema.org/addressLocality](https://schema.org/addressLocality)      
	- `addressRegion[string]`: La regione in cui si trova la località, e che si trova nel paese  . Model: [https://schema.org/addressRegion](https://schema.org/addressRegion)      
	- `district[string]`: Un distretto è un tipo di divisione amministrativa che, in alcuni paesi, è gestita dal governo locale.        
	- `postOfficeBoxNumber[string]`: Il numero di casella postale per gli indirizzi di casella postale. Ad esempio, 03578  . Model: [https://schema.org/postOfficeBoxNumber](https://schema.org/postOfficeBoxNumber)      
	- `postalCode[string]`: Il codice postale. Ad esempio, 24004  . Model: [https://schema.org/https://schema.org/postalCode](https://schema.org/https://schema.org/postalCode)      
	- `streetAddress[string]`: L'indirizzo stradale  . Model: [https://schema.org/streetAddress](https://schema.org/streetAddress)      
- `alternateName[string]`: Un nome alternativo per questa voce  - `areaServed[string]`: L'area geografica in cui viene fornito il servizio o l'articolo offerto.  . Model: [https://schema.org/Text](https://schema.org/Text)- `dataProvider[string]`: una sequenza di caratteri che identifica il fornitore dell'entità di dati armonizzata  - `dateActivityEnded[date-time]`: Timestamp di fine attività  . Model: [https://schema.org/DateTime](https://schema.org/DateTime)- `dateActivityStarted[date-time]`: Deve essere uguale a UserActivity  - `dateCreated[date-time]`: Timestamp di creazione dell'entità. Di solito viene assegnato dalla piattaforma di archiviazione  - `dateModified[date-time]`: Timestamp dell'ultima modifica dell'entità. Di solito viene assegnato dalla piattaforma di archiviazione  - `description[string]`: Descrizione dell'articolo  - `id[*]`: Identificatore univoco dell'entità  - `location[*]`: Riferimento geojson all'elemento. Può essere un punto, una stringa di linea, un poligono, un multi-punto, una stringa di linea o un poligono multiplo.  - `name[string]`: Il nome di questo elemento  - `owner[array]`: Un elenco contenente una sequenza di caratteri codificata JSON che fa riferimento agli ID univoci dei proprietari.  - `refAgent[*]`: Riferimento all'agente (cioè una persona) che esegue l'attività. Può essere un'altra entità NGSI o un qualsiasi "agente" identificato da un URI.  . Model: [https://schema.org/URL](https://schema.org/URL)- `refObject[*]`: Riferimento all'oggetto dell'azione (ad esempio, Auto1). Può essere un'altra entità NGSI o qualsiasi `oggetto` identificato da un URI.  . Model: [https://schema.org/URL](https://schema.org/URL)- `refTarget[*]`: Riferimento all'obiettivo dell'azione (ad es. Ufficio1)  . Model: [https://schema.org/URL](https://schema.org/URL)- `seeAlso[*]`: elenco di uri che puntano a risorse aggiuntive sull'elemento  - `source[string]`: Una sequenza di caratteri che indica la fonte originale dei dati dell'entità come URL. Si consiglia di utilizzare il nome di dominio completamente qualificato del provider di origine o l'URL dell'oggetto di origine.  - `type[string]`: Tipo di entità NGSI. Deve essere Attività  <!-- /30-PropertiesList -->      
<!-- 35-RequiredProperties -->      
Proprietà richieste      
- `id`  - `type`  <!-- /35-RequiredProperties -->      
<!-- 40-RequiredProperties -->      
Questa entità rappresenta l'attività corrente svolta da un utente. Può essere utilizzata in diversi scenari, dalla modellazione delle attività sociali su un sito (ad esempio, Federico condivide una foto del suo cane) alle attività della vita reale (ad esempio, Federico guida la sua auto per andare al lavoro). Il modello è ampiamente ispirato a [https://www.w3.org/TR/activitystreams-core](https://www.w3.org/TR/activitystreams-core). Il modello rappresenta le attività dell'utente utilizzando la seguente struttura di predicati `(Agente, Verbo, Oggetto*, Destinatario*)`, dove `Oggetto` e `Target` sono opzionali. L'`Agente` è identificato dall'attributo `refAgent`, il `Verbo` è identificato da `activityType`, l'`Oggetto` è identificato da `refObject` e il `Target` è identificato da `refTarget`.      
<!-- /40-RequiredProperties -->      
<!-- 50-DataModelHeader -->      
## Modello di dati descrizione delle proprietà      
Ordinati in ordine alfabetico (clicca per i dettagli)      
<!-- /50-DataModelHeader -->      
<!-- 60-ModelYaml -->      
<details><summary><strong>full yaml details</strong></summary>        
```yaml      
Activity:        
  description: Information on the current activity performed by an anonymized user in a given point in time        
  properties:        
    activityType:        
      description: "The action performed (e.g. Drive). Normative References: [https://schema.org/Action](https://schema.org/Action), [https://www.w3.org/TR/activitystreams-vocabulary/#activity-types](https://www.w3.org/TR/activitystreams-vocabulary/#activity-types), [https://health-lifesci.schema.org/PhysicalActivityCategory](https://health-lifesci.schema.org/PhysicalActivityCategory)"        
      type: string        
      x-ngsi:        
        model: https://schema.org/Text        
        type: Property        
    address:        
      description: The mailing address        
      properties:        
        addressCountry:        
          description: 'The country. For example, Spain'        
          type: string        
          x-ngsi:        
            model: https://schema.org/addressCountry        
            type: Property        
        addressLocality:        
          description: 'The locality in which the street address is, and which is in the region'        
          type: string        
          x-ngsi:        
            model: https://schema.org/addressLocality        
            type: Property        
        addressRegion:        
          description: 'The region in which the locality is, and which is in the country'        
          type: string        
          x-ngsi:        
            model: https://schema.org/addressRegion        
            type: Property        
        district:        
          description: 'A district is a type of administrative division that, in some countries, is managed by the local government'        
          type: string        
          x-ngsi:        
            type: Property        
        postOfficeBoxNumber:        
          description: 'The post office box number for PO box addresses. For example, 03578'        
          type: string        
          x-ngsi:        
            model: https://schema.org/postOfficeBoxNumber        
            type: Property        
        postalCode:        
          description: 'The postal code. For example, 24004'        
          type: string        
          x-ngsi:        
            model: https://schema.org/https://schema.org/postalCode        
            type: Property        
        streetAddress:        
          description: The street address        
          type: string        
          x-ngsi:        
            model: https://schema.org/streetAddress        
            type: Property        
        streetNr:        
          description: Number identifying a specific property on a public street        
          type: string        
          x-ngsi:        
            type: Property        
      type: object        
      x-ngsi:        
        model: https://schema.org/address        
        type: Property        
    alternateName:        
      description: An alternative name for this item        
      type: string        
      x-ngsi:        
        type: Property        
    areaServed:        
      description: The geographic area where a service or offered item is provided        
      type: string        
      x-ngsi:        
        model: https://schema.org/Text        
        type: Property        
    dataProvider:        
      description: A sequence of characters identifying the provider of the harmonised data entity        
      type: string        
      x-ngsi:        
        type: Property        
    dateActivityEnded:        
      description: Activity's end timestamp        
      format: date-time        
      type: string        
      x-ngsi:        
        model: https://schema.org/DateTime        
        type: Property        
    dateActivityStarted:        
      description: It must be equal to UserActivity        
      format: date-time        
      type: string        
      x-ngsi:        
        type: Property        
    dateCreated:        
      description: Entity creation timestamp. This will usually be allocated by the storage platform        
      format: date-time        
      type: string        
      x-ngsi:        
        type: Property        
    dateModified:        
      description: Timestamp of the last modification of the entity. This will usually be allocated by the storage platform        
      format: date-time        
      type: string        
      x-ngsi:        
        type: Property        
    description:        
      description: A description of this item        
      type: string        
      x-ngsi:        
        type: Property        
    id:        
      anyOf:        
        - description: Identifier format of any NGSI entity        
          maxLength: 256        
          minLength: 1        
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$        
          type: string        
          x-ngsi:        
            type: Property        
        - description: Identifier format of any NGSI entity        
          format: uri        
          type: string        
          x-ngsi:        
            type: Property        
      description: Unique identifier of the entity        
      x-ngsi:        
        type: Property        
    location:        
      description: 'Geojson reference to the item. It can be Point, LineString, Polygon, MultiPoint, MultiLineString or MultiPolygon'        
      oneOf:        
        - description: Geojson reference to the item. Point        
          properties:        
            bbox:        
              items:        
                type: number        
              minItems: 4        
              type: array        
            coordinates:        
              items:        
                type: number        
              minItems: 2        
              type: array        
            type:        
              enum:        
                - Point        
              type: string        
          required:        
            - type        
            - coordinates        
          title: GeoJSON Point        
          type: object        
          x-ngsi:        
            type: GeoProperty        
        - description: Geojson reference to the item. LineString        
          properties:        
            bbox:        
              items:        
                type: number        
              minItems: 4        
              type: array        
            coordinates:        
              items:        
                items:        
                  type: number        
                minItems: 2        
                type: array        
              minItems: 2        
              type: array        
            type:        
              enum:        
                - LineString        
              type: string        
          required:        
            - type        
            - coordinates        
          title: GeoJSON LineString        
          type: object        
          x-ngsi:        
            type: GeoProperty        
        - description: Geojson reference to the item. Polygon        
          properties:        
            bbox:        
              items:        
                type: number        
              minItems: 4        
              type: array        
            coordinates:        
              items:        
                items:        
                  items:        
                    type: number        
                  minItems: 2        
                  type: array        
                minItems: 4        
                type: array        
              type: array        
            type:        
              enum:        
                - Polygon        
              type: string        
          required:        
            - type        
            - coordinates        
          title: GeoJSON Polygon        
          type: object        
          x-ngsi:        
            type: GeoProperty        
        - description: Geojson reference to the item. MultiPoint        
          properties:        
            bbox:        
              items:        
                type: number        
              minItems: 4        
              type: array        
            coordinates:        
              items:        
                items:        
                  type: number        
                minItems: 2        
                type: array        
              type: array        
            type:        
              enum:        
                - MultiPoint        
              type: string        
          required:        
            - type        
            - coordinates        
          title: GeoJSON MultiPoint        
          type: object        
          x-ngsi:        
            type: GeoProperty        
        - description: Geojson reference to the item. MultiLineString        
          properties:        
            bbox:        
              items:        
                type: number        
              minItems: 4        
              type: array        
            coordinates:        
              items:        
                items:        
                  items:        
                    type: number        
                  minItems: 2        
                  type: array        
                minItems: 2        
                type: array        
              type: array        
            type:        
              enum:        
                - MultiLineString        
              type: string        
          required:        
            - type        
            - coordinates        
          title: GeoJSON MultiLineString        
          type: object        
          x-ngsi:        
            type: GeoProperty        
        - description: Geojson reference to the item. MultiLineString        
          properties:        
            bbox:        
              items:        
                type: number        
              minItems: 4        
              type: array        
            coordinates:        
              items:        
                items:        
                  items:        
                    items:        
                      type: number        
                    minItems: 2        
                    type: array        
                  minItems: 4        
                  type: array        
                type: array        
              type: array        
            type:        
              enum:        
                - MultiPolygon        
              type: string        
          required:        
            - type        
            - coordinates        
          title: GeoJSON MultiPolygon        
          type: object        
          x-ngsi:        
            type: GeoProperty        
      x-ngsi:        
        type: GeoProperty        
    name:        
      description: The name of this item        
      type: string        
      x-ngsi:        
        type: Property        
    owner:        
      description: A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)        
      items:        
        anyOf:        
          - description: Identifier format of any NGSI entity        
            maxLength: 256        
            minLength: 1        
            pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$        
            type: string        
            x-ngsi:        
              type: Property        
          - description: Identifier format of any NGSI entity        
            format: uri        
            type: string        
            x-ngsi:        
              type: Property        
        description: Unique identifier of the entity        
        x-ngsi:        
          type: Property        
      type: array        
      x-ngsi:        
        type: Property        
    refAgent:        
      anyOf:        
        - description: Identifier format of any NGSI entity        
          maxLength: 256        
          minLength: 1        
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$        
          type: string        
          x-ngsi:        
            type: Property        
        - description: Identifier format of any NGSI entity        
          format: uri        
          type: string        
          x-ngsi:        
            type: Property        
      description: Reference to the agent (i.e. a person) performing the activity. It may be another NGSI Entity or any `Agent` identified by an URI        
      x-ngsi:        
        model: https://schema.org/URL        
        type: Relationship        
    refObject:        
      anyOf:        
        - description: Identifier format of any NGSI entity        
          maxLength: 256        
          minLength: 1        
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$        
          type: string        
          x-ngsi:        
            type: Property        
        - description: Identifier format of any NGSI entity        
          format: uri        
          type: string        
          x-ngsi:        
            type: Property        
      description: Reference to the object of the action (e.g. Car1). It may be another NGSI Entity or any `Object` identified by an URI        
      x-ngsi:        
        model: https://schema.org/URL        
        type: Relationship        
    refTarget:        
      anyOf:        
        - description: Identifier format of any NGSI entity        
          maxLength: 256        
          minLength: 1        
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$        
          type: string        
          x-ngsi:        
            type: Property        
        - description: Identifier format of any NGSI entity        
          format: uri        
          type: string        
          x-ngsi:        
            type: Property        
      description: Reference to the target of the action (e.g. Office1)        
      x-ngsi:        
        model: https://schema.org/URL        
        type: Relationship        
    seeAlso:        
      description: list of uri pointing to additional resources about the item        
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
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object'        
      type: string        
      x-ngsi:        
        type: Property        
    type:        
      description: NGSI Entity type. It has to be Activity        
      enum:        
        - Activity        
      type: string        
      x-ngsi:        
        type: Property        
  required:        
    - type        
    - id        
  type: object        
  x-derived-from: ""        
  x-disclaimer: 'Redistribution and use in source and binary forms, with or without modification, are permitted  provided that the license conditions are met. Copyleft (c) 2022 Contributors to Smart Data Models Program'        
  x-license-url: https://github.com/smart-data-models/dataModel.User/blob/master/Activity/LICENSE.md        
  x-model-schema: https://smart-data-models.github.io/dataModel.User/Activity/schema.json        
  x-model-tags: ""        
  x-version: 0.1.1        
```      
</details>        
<!-- /60-ModelYaml -->      
<!-- 70-MiddleNotes -->      
<!-- /70-MiddleNotes -->      
<!-- 80-Examples -->      
## Esempi di payload      
#### Attività Valori chiave NGSI-v2 Esempio      
Ecco un esempio di attività in formato JSON-LD come valori-chiave. Questo è compatibile con NGSI-v2 quando si usa `options=keyValues` e restituisce i dati di contesto di una singola entità.      
<details><summary><strong>show/hide example</strong></summary>        
```json  
{  
  "id": "UserActivity1",  
  "type": "Activity",  
  "activityType": "Drive",  
  "description": "User1 drive Car1 to Office1",  
  "dateActivityStarted": "2016-11-30T07:00:00.00Z",  
  "refObject": "Car1",  
  "refTarget": "Office1",  
  "refAgent": "User1"  
}  
```  
</details>      
#### Attività NGSI-v2 normalizzata Esempio      
Ecco un esempio di attività in formato JSON-LD normalizzato. Questo è compatibile con NGSI-v2 quando non si usano le opzioni e restituisce i dati di contesto di una singola entità.      
<details><summary><strong>show/hide example</strong></summary>        
```json  
{  
  "id": "UserActivity1",  
  "type": "Activity",  
  "description": {  
    "type": "Text",  
    "value": "User1 drive Car1 to Office1"  
  },  
  "refTarget": {  
    "type": "Text",  
    "value": "Office1"  
  },  
  "activityType": {  
    "type": "Text",  
    "value": "Drive"  
  },  
  "dateActivityStarted": {  
    "type": "DateTime",  
    "value": "2016-11-30T07:00:00.00Z"  
  },  
  "refAgent": {  
    "type": "Text",  
    "value": "User1"  
  },  
  "refObject": {  
    "type": "Text",  
    "value": "Car1"  
  }  
}  
```  
</details>      
#### Attività Valori chiave NGSI-LD Esempio      
Ecco un esempio di attività in formato JSON-LD come valori-chiave. Questo è compatibile con NGSI-LD quando si usa `options=keyValues` e restituisce i dati di contesto di una singola entità.      
<details><summary><strong>show/hide example</strong></summary>        
```json  
{  
  "id": "urn:ngsi-ld:UserActivity:UserActivity1",  
  "type": "Activity",  
  "activityType": "Drive",  
  "dateActivityStarted": "2016-11-30T07:00:00.00Z",  
  "description": "User1 drive Car1 to Office1",  
  "refAgent": "urn:ngsi-ld:Agent:User1",  
  "refObject": "urn:ngsi-ld:Object:Car1",  
  "refTarget": "urn:ngsi-ld:Target:Office1",  
  "@context": [  
    "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld",  
    "https://raw.githubusercontent.com/smart-data-models/dataModel.User/master/context.jsonld"  
  ]  
}  
```  
</details>      
#### Attività NGSI-LD normalizzata Esempio      
Ecco un esempio di attività in formato JSON-LD normalizzato. Questo è compatibile con NGSI-LD quando non si usano le opzioni e restituisce i dati di contesto di una singola entità.      
<details><summary><strong>show/hide example</strong></summary>        
```json  
{  
    "id": "urn:ngsi-ld:UserActivity:UserActivity1",  
    "type": "Activity",  
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
    "description": {  
        "type": "Property",  
        "value": "User1 drive Car1 to Office1"  
    },  
    "refAgent": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:Agent:User1"  
    },  
    "refObject": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:Object:Car1"  
    },  
    "refTarget": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:Target:Office1"  
    },  
    "@context": [  
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld",  
        "https://raw.githubusercontent.com/smart-data-models/dataModel.User/master/context.jsonld"  
    ]  
}  
```  
</details><!-- /80-Examples -->      
<!-- 90-FooterNotes -->      
<!-- /90-FooterNotes -->      
<!-- 95-Units -->      
Vedere [FAQ 10](https://smartdatamodels.org/index.php/faqs/) per ottenere una risposta su come gestire le unità di grandezza.      
<!-- /95-Units -->      
<!-- 97-LastFooter -->      
---      
[Smart Data Models](https://smartdatamodels.org) +++ [Contribution Manual](https://bit.ly/contribution_manual) +++ [About](https://bit.ly/Introduction_SDM)<!-- /97-LastFooter -->      

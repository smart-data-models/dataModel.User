Entité : UserContext  
====================  
[Licence ouverte](https://github.com/smart-data-models//dataModel.User/blob/master/UserContext/LICENSE.md)  
Description globale : **Information sur le contexte d'un anonymat à un moment donné**  

## Liste des biens  

- `address`: L'adresse postale.  - `alternateName`: Un autre nom pour cet article  - `areaServed`: La zone géographique où un service ou un article offert est fourni  - `dataProvider`: Une séquence de caractères identifiant le fournisseur de l'entité de données harmonisées.  - `dateCreated`: Horodatage de la création de l'entité. Il est généralement attribué par la plate-forme de stockage.  - `dateModified`: Horodatage de la dernière modification de l'entité. Il est généralement attribué par la plate-forme de stockage.  - `description`: Une description de cet article  - `id`: Identifiant unique de l'entité  - `location`:   - `name`: Le nom de cet article.  - `owner`: Une liste contenant une séquence de caractères codés en JSON faisant référence aux Ids uniques du ou des propriétaires  - `refActivity`: Un objet représentant l'activité courante effectuée par l'utilisateur.  - `refUser`: Référence à l'utilisateur (anonymisé) auquel ce contexte utilisateur est associé. Références normatives : [https://tools.ietf.org/html/rfc3986](https://tools.ietf.org/html/rfc3986)  - `refUserDevice`: Un objet représentant le dispositif actuel utilisé par l'utilisateur.  - `seeAlso`: liste d'uri pointant vers des ressources supplémentaires sur le sujet  - `source`: Une séquence de caractères donnant comme URL la source originale des données de l'entité. Il est recommandé d'utiliser le nom de domaine complet du fournisseur de la source, ou l'URL de l'objet source.  - `type`: Type d'entité NGSI. Il s'agit de UserContext    
Propriétés requises  
- `id`  - `type`    
Ce modèle de données décrit le contexte d'un utilisateur. Aucune donnée personnelle n'est encodée dans le modèle. Les données réelles de l'utilisateur sont stockées dans un point final différent, identifié par la propriété "refUser".  
## Modèle de données description des biens  
Classement par ordre alphabétique (cliquez pour plus de détails)  
<details><summary><strong>full yaml details</strong></summary>    
```yaml  
UserContext:    
  description: 'Information on the context of an anonymized in a given point in time'    
  properties:    
    address:    
      description: 'The mailing address.'    
      properties:    
        addressCountry:    
          description: 'Property. The country. For example, Spain. Model:''https://schema.org/Text'''    
          type: string    
        addressLocality:    
          description: 'Property. The locality in which the street address is, and which is in the region. Model:''https://schema.org/Text'''    
          type: string    
        addressRegion:    
          description: 'Property. The region in which the locality is, and which is in the country. Model:''https://schema.org/Text'''    
          type: string    
        areaServed:    
          description: 'Property. The geographic area where a service or offered item is provided. Model:''https://schema.org/Text'''    
          type: string    
        postOfficeBoxNumber:    
          description: 'Property. The post office box number for PO box addresses. For example, Spain. Model:''https://schema.org/Text'''    
          type: string    
        postalCode:    
          description: 'Property. The postal code. For example, Spain. Model:''https://schema.org/Text'''    
          type: string    
        streetAddress:    
          description: 'Property. The street address. Model:''https://schema.org/Text'''    
          type: string    
      type: Property    
    alternateName:    
      description: 'An alternative name for this item'    
      type: Property    
    areaServed:    
      description: 'The geographic area where a service or offered item is provided'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    dataProvider:    
      description: 'A sequence of characters identifying the provider of the harmonised data entity.'    
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
      anyOf: &usercontext_-_properties_-_owner_-_items_-_anyof    
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
    location:    
      $id: https://geojson.org/schema/Geometry.json    
      $schema: "http://json-schema.org/draft-07/schema#"    
      oneOf:    
        - properties:    
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
          title: 'GeoJSON Point'    
          type: object    
        - properties:    
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
          title: 'GeoJSON LineString'    
          type: object    
        - properties:    
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
          title: 'GeoJSON Polygon'    
          type: object    
        - properties:    
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
          title: 'GeoJSON MultiPoint'    
          type: object    
        - properties:    
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
          title: 'GeoJSON MultiLineString'    
          type: object    
        - properties:    
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
          title: 'GeoJSON MultiPolygon'    
          type: object    
      title: 'GeoJSON Geometry'    
    name:    
      description: 'The name of this item.'    
      type: Property    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *usercontext_-_properties_-_owner_-_items_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      type: Property    
    refActivity:    
      anyOf:    
        - anyOf: *usercontext_-_properties_-_owner_-_items_-_anyof    
          description: 'Property. Unique identifier of the entity'    
        - format: uri    
          type: string    
      description: 'An object representing the current activity performed by the User.'    
      type: Relationship    
      x-ngsi:    
        model: https://schema.org/URL    
    refUser:    
      anyOf:    
        - anyOf: *usercontext_-_properties_-_owner_-_items_-_anyof    
          description: 'Property. Unique identifier of the entity'    
        - format: uri    
          type: string    
      description: 'Reference to the (anonymised) User to which this UserContext is associated. Normative References: [https://tools.ietf.org/html/rfc3986](https://tools.ietf.org/html/rfc3986)'    
      type: Relationship    
      x-ngsi:    
        model: https://schema.org/URL    
    refUserDevice:    
      anyOf:    
        - anyOf: *usercontext_-_properties_-_owner_-_items_-_anyof    
          description: 'Property. Unique identifier of the entity'    
        - format: uri    
          type: string    
      description: 'An object representing the current device used by the User.'    
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
      description: 'NGSI Entity type. It as to be UserContext'    
      enum:    
        - UserContext    
      type: Property    
  required:    
    - id    
    - type    
  type: object    
```  
</details>    
## Exemples de charges utiles  
#### UserContext NGSI V2 valeurs clés Exemple  
Voici un exemple de contexte utilisateur en format JSON comme valeurs clés. Il est compatible avec NGSI V2 lorsqu'il utilise "options=keyValues" et renvoie les données de contexte d'une entité individuelle.  
```json  
{  
  "id": "UserContext1",  
  "type": "UserContext",  
  "location": {  
    "type": "Point",  
    "coordinates": [-4.754444444, 41.640833333]  
  },  
  "refActivity": "UserActivity1",  
  "refUserDevice": "Device1",  
  "refUser": "User1"  
}  
```  
#### UserContext NGSI V2 normalisé Exemple  
Voici un exemple de contexte utilisateur au format JSON tel que normalisé. Ce format est compatible avec la version 2 du NGSI lorsqu'il n'utilise pas d'options et renvoie les données de contexte d'une entité individuelle.  
```json  
{  
  "id": "UserContext1",  
  "type": "UserContext",  
  "refActivity": {  
    "type": "Relationship",  
    "value": "UserActivity1"  
  },  
  "location": {  
    "type": "geo:json",  
    "value": {  
      "type": "Point",  
      "coordinates": [-4.754444444, 41.640833333]  
    }  
  },  
  "refUser": {  
    "type": "Relationship",  
    "value": "User1"  
  },  
  "refUserDevice": {  
    "type": "Relationship",  
    "value": "Device1"  
  }  
}  
```  
#### UserContext NGSI-LD valeurs clés Exemple  
Voici un exemple de contexte utilisateur au format JSON-LD comme valeurs clés. Il est compatible avec le format NGSI-LD lorsqu'il utilise "options=keyValues" et renvoie les données de contexte d'une entité individuelle.  
```json  
{"@context": ["https://schema.lab.fiware.org/ld/context",  
              "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"],  
 "id": "urn:ngsi-ld:UserContext:UserContext1",  
 "location": {"coordinates": [-4.754444444, 41.640833333], "type": "Point"},  
 "refActivity": "urn:ngsi-ld:Activity:UserActivity1",  
 "refUser": "urn:ngsi-ld:User:User1",  
 "refUserDevice": "urn:ngsi-ld:UserDevice:Device1",  
 "type": "UserContext"}  
```  
#### UserContext NGSI-LD normalisé Exemple  
Voici un exemple de contexte utilisateur au format JSON-LD tel que normalisé. Ce format est compatible avec le format JSON-LD lorsqu'il n'utilise pas d'options et renvoie les données de contexte d'une entité individuelle.  
```json  
{  
    "id": "urn:ngsi-ld:UserContext:UserContext1",  
    "type": "UserContext",  
    "refActivity": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:Activity:UserActivity1"  
    },  
    "location": {  
        "type": "GeoProperty",  
        "value": {  
            "type": "Point",  
            "coordinates": [  
                -4.754444444,  
                41.640833333  
            ]  
        }  
    },  
    "refUser": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:User:User1"  
    },  
    "refUserDevice": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:UserDevice:Device1"  
    },  
    "@context": [  
        "https://schema.lab.fiware.org/ld/context",  
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
    ]  
}  
```  

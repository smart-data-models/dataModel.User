エンティティアクティビティ  
=============
  

[オープンライセンス](https://github.com/smart-data-models//dataModel.User/blob/master/Activity/LICENSE.md)  

[document generated automatically](https://docs.google.com/presentation/d/e/2PACX-1vTs-Ng5dIAwkg91oTTUdt8ua7woBXhPnwavZ0FxgR8BsAI_Ek3C5q97Nd94HS8KhP-r_quD4H0fgyt3/pub?start=false&loop=false&delayms=3000#slide=id.gb715ace035_0_60)  

グローバルな記述。**匿名化されたユーザーがある時点で行った現在の活動に関する情報**。  


## プロパティのリスト  


- `activityType`: 実行されたアクション（例：ドライブ）。規範となるリファレンス[https://schema.org/Action](https://schema.org/Action), [https://www.w3.org/TR/activitystreams-vocabulary/#activity-types](https://www.w3.org/TR/activitystreams-vocabulary/#activity-types), [https://health-lifesci.schema.org/PhysicalActivityCategory](https://health-lifesci.schema.org/PhysicalActivityCategory)  
- `alternateName`: このアイテムの別称  
- `dataProvider`: 調和されたデータ・エンティティの提供者を識別する一連の文字。  
- `dateActivityEnded`: アクティビティの終了時のタイムスタンプ。  
- `dateActivityStarted`: UserActivityと同じである必要があります。  
- `dateCreated`: エンティティの作成タイムスタンプ。これは通常、ストレージプラットフォームによって割り当てられます。  
- `dateModified`: エンティティが最後に変更された時のタイムスタンプ。これは通常、ストレージプラットフォームによって割り当てられます。  
- `description`: このアイテムの説明  
- `id`: エンティティのユニークな識別子  
- `name`: このアイテムの名前です。  
- `owner`: オーナーのIDを参照するJSONエンコードされた文字列を含むリスト  
- `refAgent`: 活動を行うエージェント（人）への参照。それは、他のNGSIエンティティであったり、URIで特定される任意の`Agent`であったりします。  
- `refObject`: アクションのオブジェクトへの参照（例：Car1）。それは、別のNGSIエンティティであったり、URIで識別される任意の`Object`であったりします。  
- `refTarget`: アクションのターゲットへの参照（例：Office1）。  
- `seeAlso`: アイテムに関する追加リソースを示すuriのリスト  
- `source`: エンティティデータのオリジナルソースをURLで示す一連の文字。ソースプロバイダの完全修飾ドメイン名、またはソースオブジェクトのURLであることが推奨されます。  
- `type`: NGSI エンティティ・タイプ。UserActivityである必要があります。  
  

必須項目  
- `activityType`  
- `id`  
- `refAgent`  
- `type`  
  

このエンティティは、ユーザーが現在行っているアクティビティを表します。このエンティティは、サイト上でのソーシャルアクティビティのモデル化（例：Federicoが自分の犬の写真を共有する）から、実生活でのアクティビティ（例：Federicoが自分の車で通勤する）まで、さまざまなシナリオで使用できます。このモデルは、[https://www.w3.org/TR/activitystreams-core](https://www.w3.org/TR/activitystreams-core)に大きく影響されています。このモデルは以下の述語構造 `(Agent, Verb, Object*, Target*)` を用いてユーザの活動を表現します．Agent` は属性 `refAgent` で識別され、`Verb` は `activityType` で識別され、`Object` は `refObject` で識別され、`Target` は `refTarget` で識別されます。  

## データモデルによるプロパティの記述  

アルファベット順（クリックすると詳細が表示されます  
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

## ペイロードの例  

#### 活動内容 NGSI-v2のキーバリューの例  

Activityをkey-valuesとしてJSON-LD形式で出力した例です。これは`options=keyValues`を使った場合のNGSI-v2との互換性があり、個々のエンティティのコンテキストデータを返します。  

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

#### 活動内容 NGSI-v2 正規化例  

ここでは、正規化されたJSON-LD形式のActivityの例を示します。これは、オプションを使用しない場合のNGSI-v2との互換性があり、個々のエンティティのコンテキストデータを返します。  

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

#### 活動内容 NGSI-LDのキーバリューの例  

Activityをkey-valuesとしてJSON-LD形式にした例です。これは`options=keyValues`を使った場合のNGSI-LDとの互換性があり、個々のエンティティのコンテキストデータを返します。  

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

#### 活動内容 NGSI-LDの正規化例  

ここでは、正規化されたJSON-LD形式のActivityの例を示します。これは、オプションを使用しない場合のNGSI-LDとの互換性があり、個々のエンティティのコンテキストデータを返します。  

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

## Группа товаров
### Группы товаров 
Средствами JSON API можно создавать и обновлять сведения о Группах товаров, запрашивать списки Групп товаров и сведения по отдельным Группам товаров. Кодом сущности для Группы товаров в составе JSON API является ключевое слово **productFolder**.
По данной сущности можно осуществлять контекстный поиск с помощью специального параметра `search`. Подробнее можно узнать по [ссылке](/api/remap/1.2/doc/index.html#header-контекстный-поиск).

Поиск среди объектов групп товаров на соответствие поисковой строке будет осуществлён по следующим полям:
+ по наименованию Группы товаров (name)
+ по коду Группы товаров (code)

#### Атрибуты сущности
+ **meta** - [Метаданные](/api/remap/1.2/doc/index.html#header-метаданные) о Группе товаров
+ **id** - ID в формате UUID `Только для чтения`
+ **accountId** - ID учетной записи `Только для чтения`
+ **owner** - Ссылка на Владельца (Сотрудника) в формате [Метаданных](/api/remap/1.2/doc/index.html#header-метаданные))
+ **shared** - Общий доступ
+ **group** - Отдел сотрудника в формате [Метаданных](/api/remap/1.2/doc/index.html#header-метаданные)
+ **updated** - Момент последнего обновления сущности `Только для чтения`
+ **name** - Наименование Группы товаров `Необходимое`
+ **description** - Описание Группы товаров
+ **code** - Код Группы товаров
+ **externalCode** - Внешний код Группы товаров
+ **archived** - Добавлена ли Группа товаров в архив `Только для чтения`
+ **pathName** - Наименование Группы товаров, в которую входит данная Группа товаров `Только для чтения`
+ **vat** - НДС %
+ **effectiveVat** - Реальный НДС % `Только для чтения`
+ **productFolder** - Ссылка на Группу товаров данной Группы товаров в формате [Метаданных](/api/remap/1.2/doc/index.html#header-метаданные)

### Получить список групп товаров 
Запрос всех Групп товаров на данной учётной записи.
Результат: Объект JSON, включающий в себя поля:
- **meta** [Метаданные](/api/remap/1.2/doc/index.html#header-метаданные) о выдаче,
- **context** - [Метаданные](/api/remap/1.2/doc/index.html#header-метаданные) о сотруднике, выполнившем запрос.
- **rows** - Массив JSON объектов, представляющих собой Группы товаров.
**Параметры**

| Параметр                | Описание  |
| ------------------------------ |:---------------------------|
|limit |  `number` (optional) **Default: 1000** *Example: 1000* Максимальное количество сущностей для извлечения.`Допустимые значения 1 - 1000`.|
|offset |  `number` (optional) **Default: 0** *Example: 40* Отступ в выдаваемом списке сущностей.|

> Получить список групп товаров

```shell
curl -X GET
  "https://online.moysklad.ru/api/remap/1.2/entity/productfolder"
  -H "Authorization: Basic <Access-Token>"
```

> Response 200 (application/json)
Успешный запрос. Результат - JSON представление списка Групп товаров.

```json
{
  "context": {
    "employee": {
      "meta": {
        "href": "https://online.moysklad.ru/api/remap/1.2/context/employee",
        "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/employee/metadata",
        "type": "employee",
        "mediaType": "application/json"
      }
    }
  },
  "meta": {
    "href": "https://online.moysklad.ru/api/remap/1.2/entity/productFolder",
    "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/productFolder/metadata",
    "type": "productfolder",
    "mediaType": "application/json",
    "size": 2,
    "limit": 1000,
    "offset": 0
  },
  "rows": [
    {
      "meta": {
        "href": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/3ea73e1a-2cad-11e6-8a84-bae50000001d",
        "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata",
        "type": "productfolder",
        "mediaType": "application/json"
      },
      "id": "3ea73e1a-2cad-11e6-8a84-bae50000001d",
      "accountId": "da7d9bbe-2c97-11e6-8a84-bae500000001",
      "owner": {
        "meta": {
          "href": "https://online.moysklad.ru/api/remap/1.2/entity/employee/faba7f37-2e58-11e6-8a84-bae500000028",
          "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/employee/metadata",
          "type": "employee",
          "mediaType": "application/json"
        }
      },
      "shared": false,
      "group": {
        "meta": {
          "href": "https://online.moysklad.ru/api/remap/1.2/entity/group/f97aa1fb-2e58-11e6-8a84-bae500000002",
          "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/group/metadata",
          "type": "group",
          "mediaType": "application/json"
        }
      },
      "updated": "2016-06-07 15:42:07",
      "name": "Овощи",
      "code": "13321Fruits1",
      "externalCode": "mRQao-5IgY3soIY1EaI083",
      "archived": false,
      "pathName": ""
    },
    {
      "meta": {
        "href": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/275961ab-2cad-11e6-8a84-bae50000001a",
        "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata",
        "type": "productfolder",
        "mediaType": "application/json"
      },
      "id": "275961ab-2cad-11e6-8a84-bae50000001a",
      "accountId": "da7d9bbe-2c97-11e6-8a84-bae500000001",
      "updated": "2016-06-07 15:41:28",
      "name": "Фрукты",
      "code": "13321Fruits",
      "externalCode": "extFruits",
      "archived": false,
      "pathName": "",
      "vat": 3,
      "effectiveVat": 3
    }
  ]
}
```

### Создать новую группу товаров
 
Запрос на создание новой Группы товаров.
Обязательные для создания Группы товаров поля:
+ **name** - Наименование Группы товаров

> Пример создания новой Группы товаров с телом запроса, содержащим только поле name.

```shell
  curl -X POST
    "https://online.moysklad.ru/api/remap/1.2/entity/productfolder"
    -H "Authorization: Basic <Access-Token>"
    -H "Content-Type: application/json"
      -d '{
            "name": "Овощи"
          }'  
```

> Response 200 (application/json)
Успешный запрос. Результат - JSON представление созданной Группы товаров.

```json
{
  "meta": {
    "href": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/3ea73e1a-2cad-11e6-8a84-bae50000001d",
    "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata",
    "type": "productfolder",
    "mediaType": "application/json"
  },
  "id": "3ea73e1a-2cad-11e6-8a84-bae50000001d",
  "accountId": "da7d9bbe-2c97-11e6-8a84-bae500000001",
  "owner": {
    "meta": {
      "href": "https://online.moysklad.ru/api/remap/1.2/entity/employee/faba7f37-2e58-11e6-8a84-bae500000028",
      "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/employee/metadata",
      "type": "employee",
      "mediaType": "application/json"
    }
  },
  "shared": false,
  "group": {
    "meta": {
      "href": "https://online.moysklad.ru/api/remap/1.2/entity/group/f97aa1fb-2e58-11e6-8a84-bae500000002",
      "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/group/metadata",
      "type": "group",
      "mediaType": "application/json"
    }
  },
  "updated": "2016-06-07 15:42:07",
  "name": "Овощи",
  "code": "13321Fruits1",
  "externalCode": "mRQao-5IgY3soIY1EaI083",
  "archived": false,
  "pathName": ""
}
```

> Пример создания новой Группы товаров с более насыщенным телом запроса.

```shell
  curl -X POST
    "https://online.moysklad.ru/api/remap/1.2/entity/productfolder"
    -H "Authorization: Basic <Access-Token>"
    -H "Content-Type: application/json"
      -d '{
            "name": "Фрукты",
            "code": "13321Fruits",
            "externalCode": "extFruits",
            "vat": 3,
            "effectiveVat": 3
          }'  
```

> Response 200 (application/json)
Успешный запрос. Результат - JSON представление созданной Группы товаров.

```json
{
  "meta": {
    "href": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/275961ab-2cad-11e6-8a84-bae50000001a",
    "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata",
    "type": "productfolder",
    "mediaType": "application/json"
  },
  "id": "275961ab-2cad-11e6-8a84-bae50000001a",
  "accountId": "da7d9bbe-2c97-11e6-8a84-bae500000001",
  "owner": {
    "meta": {
      "href": "https://online.moysklad.ru/api/remap/1.2/entity/employee/faba7f37-2e58-11e6-8a84-bae500000028",
      "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/employee/metadata",
      "type": "employee",
      "mediaType": "application/json"
    }
  },
  "shared": false,
  "group": {
    "meta": {
      "href": "https://online.moysklad.ru/api/remap/1.2/entity/group/f97aa1fb-2e58-11e6-8a84-bae500000002",
      "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/group/metadata",
      "type": "group",
      "mediaType": "application/json"
    }
  },
  "updated": "2016-06-07 15:41:28",
  "name": "Фрукты",
  "code": "13321Fruits",
  "externalCode": "extFruits",
  "archived": false,
  "pathName": "",
  "vat": 3,
  "effectiveVat": 3
}
```

### Массовое создание и обновление Групп товаров 
[Массовое создание и обновление](/api/remap/1.2/doc/index.html#header-создание-и-обновление-нескольких-объектов) Групп товаров.
В теле запроса нужно передать массив, содержащий JSON представления Групп товаров, которые вы хотите создать или обновить.
Обновляемые Группы товаров должны содержать идентификатор в виде метаданных.

> Пример создания и обновления нескольких Групп товаров

```shell
  curl -X POST
    "https://online.moysklad.ru/api/remap/1.2/entity/productfolder"
    -H "Authorization: Basic <Access-Token>"
    -H "Content-Type: application/json"
      -d '[
            {
              "name": "Овощи"
            },
            {
              "meta": {
                "href": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/3ea73e1a-2cad-11e6-8a84-bae50000001d",
                "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata",
                "type": "productfolder",
                "mediaType": "application/json"
              },
              "name": "Группа Овощи",
              "code": "vegetableFolderCode",
              "externalCode": "extVegCode",
              "vat": 5,
              "effectiveVat": 5
            }
          ]'  
```

> Response 200 (application/json)
Успешный запрос. Результат - массив JSON представлений созданных и обновленных Групп товаров.

```json
[
  {
    "meta": {
      "href": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/3ea73e1a-2cad-11e6-8a84-bae50000001d",
      "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata",
      "type": "productfolder",
      "mediaType": "application/json"
    },
    "id": "3ea73e1a-2cad-11e6-8a84-bae50000001d",
    "accountId": "da7d9bbe-2c97-11e6-8a84-bae500000001",
    "owner": {
      "meta": {
        "href": "https://online.moysklad.ru/api/remap/1.2/entity/employee/faba7f37-2e58-11e6-8a84-bae500000028",
        "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/employee/metadata",
        "type": "employee",
        "mediaType": "application/json"
      }
    },
    "shared": false,
    "group": {
      "meta": {
        "href": "https://online.moysklad.ru/api/remap/1.2/entity/group/f97aa1fb-2e58-11e6-8a84-bae500000002",
        "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/group/metadata",
        "type": "group",
        "mediaType": "application/json"
      }
    },
    "updated": "2016-06-07 15:42:07",
    "name": "Овощи",
    "code": "13321Fruits1",
    "externalCode": "mRQao-5IgY3soIY1EaI083",
    "archived": false,
    "pathName": ""
  },
  {
    "meta": {
      "href": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/3ea73e1a-2cad-11e6-8a84-bae50000001d",
      "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata",
      "type": "productfolder",
      "mediaType": "application/json"
    },
    "id": "3ea73e1a-2cad-11e6-8a84-bae50000001d",
    "accountId": "da7d9bbe-2c97-11e6-8a84-bae500000001",
    "owner": {
      "meta": {
        "href": "https://online.moysklad.ru/api/remap/1.2/entity/employee/faba7f37-2e58-11e6-8a84-bae500000028",
        "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/employee/metadata",
        "type": "employee",
        "mediaType": "application/json"
      }
    },
    "shared": false,
    "group": {
      "meta": {
        "href": "https://online.moysklad.ru/api/remap/1.2/entity/group/f97aa1fb-2e58-11e6-8a84-bae500000002",
        "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/group/metadata",
        "type": "group",
        "mediaType": "application/json"
      }
    },
    "updated": "2016-06-07 15:45:28",
    "name": "Группа Овощи",
    "code": "vegetableFolderCode",
    "externalCode": "extVegCode",
    "archived": false,
    "pathName": "",
    "vat": 5,
    "effectiveVat": 5
  }
]
```  

### Удалить Группу товаров 

**Параметры**

|Параметр   |Описание   | 
|---|---|
|id |  `string` (required) *Example: 7944ef04-f831-11e5-7a69-971500188b19* id Группы товаров.|

> Запрос на удаление Группы товаров с указанным id.

```shell
curl -X GET
  "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/7944ef04-f831-11e5-7a69-971500188b19"
  -H "Authorization: Basic <Access-Token>"
```

> Response 200 (application/json)
Успешное удаление Группы товаров.

### Метаданные Групп товаров 
#### Метаданные Групп товаров
 
Запрос на получение метаданных Групп товаров. Результат - объект JSON, включающий в себя:
+ **meta** - Ссылка на метаданные Групп товаров
+ **attributes** - Массив объектов доп. полей Групп товаров в формате [Метаданных](#header-метаданные)

Структура отдельного объекта, представляющего доп. поле подробно описана в разделе [Работа с дополнительными полями](#header-работа-с-дополнительными-полями).

> Получить метаданные Групп товаров

```shell
curl -X GET
  "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata"
  -H "Authorization: Basic <Access-Token>"
```

> Response 200 (application/json)
Успешный запрос. Результат - JSON представление доп. полей Групп товаров.

```json
{
  "meta": {
    "href": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata",
    "mediaType": "application/json"
  },
  "attributes": [
    {
      "id": "5290a290-0313-11e6-9464-e4de00000020",
      "name": "attribute_name",
      "type": "boolean",
      "required": false
    }
  ]
}
```
  
### Отдельное доп. поле

**Параметры**

|Параметр   |Описание   | 
|---|---|
|id |  `string` (required) *Example: 5290a290-0313-11e6-9464-e4de00000020* id Доп. поля.|

#### Отдельное доп. поле
 
> Запрос на получение информации по отдельному дополнительному полю.

```shell
curl -X GET
  "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata/attributes/5290a290-0313-11e6-9464-e4de00000020"
  -H "Authorization: Basic <Access-Token>"
```

> Response 200 (application/json)
Успешный запрос. Результат - JSON представление отдельного доп. поля.

```json
{
  "meta": {
    "href": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata/attributes/5290a290-0313-11e6-9464-e4de00000020",
    "type": "attributemetadata",
    "mediaType": "application/json"
  },
  "id": "5290a290-0313-11e6-9464-e4de00000020",
  "name": "attribute_name",
  "type": "boolean",
  "required": false
}
```
 
### Группа товаров 

**Параметры**

|Параметр   |Описание   | 
|---|---|
|id |  `string` (required) *Example: 7944ef04-f831-11e5-7a69-971500188b19* id Группы товаров.|

### Получить Группу товаров
 
> Запрос на получение отдельной группы товаров с указанным id.

```shell
curl -X GET
  "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/7944ef04-f831-11e5-7a69-971500188b19"
  -H "Authorization: Basic <Access-Token>"
```

> Response 200 (application/json)
Успешный запрос. Результат - JSON представление Группы товаров.

```json
{
  "meta": {
    "href": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/3ea73e1a-2cad-11e6-8a84-bae50000001d",
    "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata",
    "type": "productfolder",
    "mediaType": "application/json"
  },
  "id": "3ea73e1a-2cad-11e6-8a84-bae50000001d",
  "accountId": "da7d9bbe-2c97-11e6-8a84-bae500000001",
  "owner": {
    "meta": {
      "href": "https://online.moysklad.ru/api/remap/1.2/entity/employee/faba7f37-2e58-11e6-8a84-bae500000028",
      "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/employee/metadata",
      "type": "employee",
      "mediaType": "application/json"
    }
  },
  "shared": false,
  "group": {
    "meta": {
      "href": "https://online.moysklad.ru/api/remap/1.2/entity/group/f97aa1fb-2e58-11e6-8a84-bae500000002",
      "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/group/metadata",
      "type": "group",
      "mediaType": "application/json"
    }
  },
  "updated": "2016-06-07 15:42:07",
  "name": "Овощи",
  "code": "13321Fruits1",
  "externalCode": "mRQao-5IgY3soIY1EaI083",
  "archived": false,
  "pathName": ""
}
```

### Изменить Группу товаров
 
Запрос на обновление Группы товаров с указанным id.
В теле запроса можно указать только те поля, которые необходимо изменить у Группы товаров, кроме тех, что
помечены `Только для чтения` в описании [атрибутов Группы товаров](#группа-товаров-группы-товаров).
Для обновления поля **pathName** нужно обновить ссылку на родительскую Группу товаров, т.е. обновить поле
**productFolder**

**Параметры**

|Параметр   |Описание   | 
|---|---|
|id |  `string` (required) *Example: 7944ef04-f831-11e5-7a69-971500188b19* id Группы товаров.|

> Request Пример (application/json)
Пример запроса на обновление конкретной Группы товаров.

```shell
  curl -X PUT
    "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/7944ef04-f831-11e5-7a69-971500188b19"
    -H "Authorization: Basic <Access-Token>"
    -H "Content-Type: application/json"
      -d '{
            "name": "Группа Овощи",
            "code": "vegetableFolderCode",
            "externalCode": "extVegCode",
            "vat": 5,
            "effectiveVat": 5
          }'  
```

> Response 200 (application/json)
Успешный запрос. Результат - JSON представление обновлённой Группы товаров.

```json
{
  "meta": {
    "href": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/3ea73e1a-2cad-11e6-8a84-bae50000001d",
    "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/productfolder/metadata",
    "type": "productfolder",
    "mediaType": "application/json"
  },
  "id": "3ea73e1a-2cad-11e6-8a84-bae50000001d",
  "accountId": "da7d9bbe-2c97-11e6-8a84-bae500000001",
  "owner": {
    "meta": {
      "href": "https://online.moysklad.ru/api/remap/1.2/entity/employee/faba7f37-2e58-11e6-8a84-bae500000028",
      "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/employee/metadata",
      "type": "employee",
      "mediaType": "application/json"
    }
  },
  "shared": false,
  "group": {
    "meta": {
      "href": "https://online.moysklad.ru/api/remap/1.2/entity/group/f97aa1fb-2e58-11e6-8a84-bae500000002",
      "metadataHref": "https://online.moysklad.ru/api/remap/1.2/entity/group/metadata",
      "type": "group",
      "mediaType": "application/json"
    }
  },
  "updated": "2016-06-07 15:45:28",
  "name": "Группа Овощи",
  "code": "vegetableFolderCode",
  "externalCode": "extVegCode",
  "archived": false,
  "pathName": "",
  "vat": 5,
  "effectiveVat": 5
}
```

# README

@geislabs/json

# @geislabs/json

## Table of contents

### Interfaces

- [JsonPath](#jsonpath)

### Functions

- [Json](#json)
- [createFetch](#createfetch)

## Functions

### Json

▸ **Json**(`content?`, `path?`, `config?`): [JsonPath](#jsonpath)

Constructs a new json path from either a raw string
or an object

**`example`**
```typescript
const value = Json(`{"value": 5}`).get('value').toInteger()
// => 5
```

#### Parameters

| Name | Type |
| :------ | :------ |
| `content?` | `string` \| `object` |
| `path?` | `string` |
| `config?` | `Partial`<JsonConfig\> |

#### Returns

[JsonPath](#jsonpath)

___

### createFetch

▸ `Const` **createFetch**(): `FetchAdapter`<``"json"``, [JsonPath](#jsonpath)\>

#### Returns

`FetchAdapter`<``"json"``, [JsonPath](#jsonpath)\>

# Interfaces

## Jsonpath

[@geislabs/json](#readme) / JsonPath

# Interface: JsonPath

A JsonPath represents a nested selection of
properties inside a JSON document

## Hierarchy

- `Iterable`<[JsonPath](#jsonpath)\>

  ↳ **JsonPath**

## Table of contents

### Methods

- [[Symbol.iterator]](jsonpath.md#[symbol.iterator])
- [get](#get)
- [toArray](#toarray)
- [toBoolean](#toboolean)
- [toInteger](#tointeger)
- [toString](#tostring)
- [valueOf](#valueof)

## Methods

### [Symbol.iterator]

▸ **[Symbol.iterator]**(): `Iterator`<[JsonPath](#jsonpath), any, undefined\>

#### Returns

`Iterator`<[JsonPath](#jsonpath), any, undefined\>

#### Inherited from

Iterable.\_\_@iterator

___

### get

▸ **get**(`selector`): [JsonPath](#jsonpath)

Extract a nested json value

**`example`**
```typescript
const json = Json(`{"value": 5}`).get('value').toInteger()
// => 5
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `selector` | `string` | A valid jsonpath selector string |

#### Returns

[JsonPath](#jsonpath)

___

### toArray

▸ **toArray**(): `JsonValue`[]

Returns the current element selection as
an array of elements

**`example`**
```typescript
const values = json.toArray()
// => [1, 2, 3]
```

#### Returns

`JsonValue`[]

___

### toBoolean

▸ **toBoolean**(): ``null`` \| `boolean` \| `Error`

Return current json value as a boolean

#### Returns

``null`` \| `boolean` \| `Error`

___

### toInteger

▸ **toInteger**(): ``null`` \| `number` \| `Error`

Return current json value as an integer

#### Returns

``null`` \| `number` \| `Error`

___

### toString

▸ **toString**(): ``null`` \| `string`

Return string value

#### Returns

``null`` \| `string`

___

### valueOf

▸ **valueOf**(): `object` \| `object`[]

Unwraps the inner json value

#### Returns

`object` \| `object`[]
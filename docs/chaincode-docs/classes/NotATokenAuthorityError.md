**@gala-chain/chaincode** ∙ [API](../exports.md)

***

[API](../exports.md) > NotATokenAuthorityError

# Class: NotATokenAuthorityError

## Contents

- [Extends](NotATokenAuthorityError.md#extends)
- [Constructors](NotATokenAuthorityError.md#constructors)
  - [new NotATokenAuthorityError(user, tokenClassKey, authorities)](NotATokenAuthorityError.md#new-notatokenauthorityerroruser-tokenclasskey-authorities)
- [Properties](NotATokenAuthorityError.md#properties)
  - [code](NotATokenAuthorityError.md#code)
  - [key](NotATokenAuthorityError.md#key)
  - [message](NotATokenAuthorityError.md#message)
  - [name](NotATokenAuthorityError.md#name)
  - [payload](NotATokenAuthorityError.md#payload)
  - [stack](NotATokenAuthorityError.md#stack)
- [Methods](NotATokenAuthorityError.md#methods)
  - [andExec()](NotATokenAuthorityError.md#andexec)
  - [logError()](NotATokenAuthorityError.md#logerror)
  - [logWarn()](NotATokenAuthorityError.md#logwarn)
  - [map()](NotATokenAuthorityError.md#map)
  - [matches()](NotATokenAuthorityError.md#matches)

## Extends

- `ForbiddenError`

## Constructors

### new NotATokenAuthorityError(user, tokenClassKey, authorities)

> **new NotATokenAuthorityError**(`user`, `tokenClassKey`, `authorities`): [`NotATokenAuthorityError`](NotATokenAuthorityError.md)

#### Parameters

▪ **user**: `string`

▪ **tokenClassKey**: `string`

▪ **authorities**: `string`[]

#### Overrides

ForbiddenError.constructor

#### Source

[chaincode/src/token/TokenError.ts:38](https://github.com/GalaChain/sdk/blob/bcbbb18/chaincode/src/token/TokenError.ts#L38)

## Properties

### code

> **`readonly`** **code**: `ErrorCode`

Status code, a value from ErrorCode enum. It is directly mapped to HTTP,
status, it is a constant value to be used by clients integrating with
the chain.

#### Inherited from

ForbiddenError.code

#### Source

[chain-api/src/utils/error.ts:45](https://github.com/GalaChain/sdk/blob/bcbbb18/chain-api/src/utils/error.ts#L45)

***

### key

> **`readonly`** **key**: `Uppercase`\<`string`\>

An upper case string to be used as a key do diagnose where the error comes
from and help with regular development. It should not be used by client
integrating with the chain since we don't guarantee it won't change.
It is generated from original error class name.

#### Inherited from

ForbiddenError.key

#### Source

[chain-api/src/utils/error.ts:53](https://github.com/GalaChain/sdk/blob/bcbbb18/chain-api/src/utils/error.ts#L53)

***

### message

> **message**: `string`

#### Inherited from

ForbiddenError.message

#### Source

node\_modules/typescript/lib/lib.es5.d.ts:1076

***

### name

> **name**: `string`

#### Inherited from

ForbiddenError.name

#### Source

node\_modules/typescript/lib/lib.es5.d.ts:1075

***

### payload

> **`readonly`** **payload**?: `Record`\<`string`, `unknown`\>

Additional information to be used by

#### Inherited from

ForbiddenError.payload

#### Source

[chain-api/src/utils/error.ts:58](https://github.com/GalaChain/sdk/blob/bcbbb18/chain-api/src/utils/error.ts#L58)

***

### stack

> **stack**?: `string`

#### Inherited from

ForbiddenError.stack

#### Source

node\_modules/typescript/lib/lib.es5.d.ts:1077

## Methods

### andExec()

> **andExec**(`fn`): `ChainError`

Allows to execute function getting as a parameter the current error.

#### Parameters

▪ **fn**: (`e`) => `void`

#### Returns

#### Inherited from

ForbiddenError.andExec

#### Example

```ts
throw CommonChainError.objectNotFound(objectId).andExec((e) => {
  logger.error(e.message);
});
```

#### Source

[chain-api/src/utils/error.ts:114](https://github.com/GalaChain/sdk/blob/bcbbb18/chain-api/src/utils/error.ts#L114)

***

### logError()

> **logError**(`logger`): `ChainError`

#### Parameters

▪ **logger**: `object`

▪ **logger.error**

#### Inherited from

ForbiddenError.logError

#### Source

[chain-api/src/utils/error.ts:119](https://github.com/GalaChain/sdk/blob/bcbbb18/chain-api/src/utils/error.ts#L119)

***

### logWarn()

> **logWarn**(`logger`): `ChainError`

#### Parameters

▪ **logger**: `object`

▪ **logger.warn**

#### Inherited from

ForbiddenError.logWarn

#### Source

[chain-api/src/utils/error.ts:124](https://github.com/GalaChain/sdk/blob/bcbbb18/chain-api/src/utils/error.ts#L124)

***

### map()

> **map**(`key`, `newError`): `ChainError`

Maps ChainError to another chain error by error code if `key` param matches
current error code or current diagnostic key. Otherwise, returns original
error.

Useful in rethrowing an error or mapping an error to another one in catch
clauses or catch methods in promises.

#### Parameters

▪ **key**: `ErrorCode` \| `ClassConstructor`\<`ChainError`\>

error code or error class to match

▪ **newError**: `ChainError` \| (`e`) => `ChainError`

new error or a function to create the new error

#### Inherited from

ForbiddenError.map

#### Source

[chain-api/src/utils/error.ts:148](https://github.com/GalaChain/sdk/blob/bcbbb18/chain-api/src/utils/error.ts#L148)

***

### matches()

> **matches**(`key`): `boolean`

#### Parameters

▪ **key**: `ErrorCode` \| `ClassConstructor`\<`ChainError`\>

#### Inherited from

ForbiddenError.matches

#### Source

[chain-api/src/utils/error.ts:129](https://github.com/GalaChain/sdk/blob/bcbbb18/chain-api/src/utils/error.ts#L129)

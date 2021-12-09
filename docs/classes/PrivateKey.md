# Class: PrivateKey

Class for Paillier private keys.

## Table of contents

### Constructors

- [constructor](PrivateKey.md#constructor)

### Properties

- [\_p](PrivateKey.md#_p)
- [\_q](PrivateKey.md#_q)
- [lambda](PrivateKey.md#lambda)
- [mu](PrivateKey.md#mu)
- [publicKey](PrivateKey.md#publickey)

### Accessors

- [bitLength](PrivateKey.md#bitlength)
- [n](PrivateKey.md#n)

### Methods

- [decrypt](PrivateKey.md#decrypt)
- [getRandomFactor](PrivateKey.md#getrandomfactor)

## Constructors

### constructor

• **new PrivateKey**(`lambda`, `mu`, `publicKey`, `p?`, `q?`)

Creates an instance of class PrivateKey

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `lambda` | `bigint` |  |
| `mu` | `bigint` |  |
| `publicKey` | [`PublicKey`](PublicKey.md) |  |
| `p?` | `bigint` | a big prime |
| `q?` | `bigint` | - |

#### Defined in

PrivateKey.ts:23

## Properties

### \_p

• `Private` `Optional` `Readonly` **\_p**: `bigint`

#### Defined in

PrivateKey.ts:11

___

### \_q

• `Private` `Optional` `Readonly` **\_q**: `bigint`

#### Defined in

PrivateKey.ts:12

___

### lambda

• `Readonly` **lambda**: `bigint`

#### Defined in

PrivateKey.ts:8

___

### mu

• `Readonly` **mu**: `bigint`

#### Defined in

PrivateKey.ts:9

___

### publicKey

• `Readonly` **publicKey**: [`PublicKey`](PublicKey.md)

#### Defined in

PrivateKey.ts:10

## Accessors

### bitLength

• `get` **bitLength**(): `number`

Get the bit length of the public modulo

#### Returns

`number`

The bit length of the public modulo

#### Defined in

PrivateKey.ts:35

___

### n

• `get` **n**(): `bigint`

Get the public modulo n=p·q

#### Returns

`bigint`

The public modulo n=p·q

#### Defined in

PrivateKey.ts:43

## Methods

### decrypt

▸ **decrypt**(`c`): `bigint`

Paillier private-key decryption

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `c` | `bigint` | A bigint encrypted with the public key |

#### Returns

`bigint`

The decryption of c with this private key

#### Defined in

PrivateKey.ts:54

___

### getRandomFactor

▸ **getRandomFactor**(`c`): `bigint`

Recover the random factor used for encrypting a message with the complementary public key.
The recovery function only works if the public key generator g was using the simple variant
g = 1 + n
It is also necessary to know p and q (usually stored in the private key)

**`throws`** {RangeError}
Cannot recover the random factor if publicKey.g != publicKey.n + 1. You should generate yout keys using the simple variant, e.g. generateRandomKeys(3072, true) )

**`throws`** {Error}
Cannot get random factor without knowing p and q

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `c` | `bigint` | The encryption using the public of message m with random factor r |

#### Returns

`bigint`

The random factor (mod n)

#### Defined in

PrivateKey.ts:75

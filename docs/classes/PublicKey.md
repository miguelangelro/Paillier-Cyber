# Class: PublicKey

Class for a Paillier public key

## Table of contents

### Constructors

- [constructor](PublicKey.md#constructor)

### Properties

- [\_n2](PublicKey.md#_n2)
- [g](PublicKey.md#g)
- [n](PublicKey.md#n)

### Accessors

- [bitLength](PublicKey.md#bitlength)

### Methods

- [addition](PublicKey.md#addition)
- [encrypt](PublicKey.md#encrypt)
- [multiply](PublicKey.md#multiply)

## Constructors

### constructor

• **new PublicKey**(`n`, `g`)

Creates an instance of class PublicKey

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `n` | `bigint` | The public modulo |
| `g` | `bigint` | The public generator |

#### Defined in

PublicKey.ts:17

## Properties

### \_n2

• `Readonly` **\_n2**: `bigint`

#### Defined in

PublicKey.ts:10

___

### g

• `Readonly` **g**: `bigint`

#### Defined in

PublicKey.ts:8

___

### n

• `Readonly` **n**: `bigint`

#### Defined in

PublicKey.ts:7

## Accessors

### bitLength

• `get` **bitLength**(): `number`

Get the bit length of the public modulo

#### Returns

`number`

The bit length of the public modulo

#### Defined in

PublicKey.ts:27

## Methods

### addition

▸ **addition**(...`ciphertexts`): `bigint`

Homomorphic addition

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `...ciphertexts` | `bigint`[] | n >= 2 ciphertexts (c_1,..., c_n) that are the encryption of (m_1, ..., m_n) with this public key |

#### Returns

`bigint`

The encryption of (m_1 + ... + m_2) with this public key

#### Defined in

PublicKey.ts:55

___

### encrypt

▸ **encrypt**(`m`, `r?`): `bigint`

Paillier public-key encryption

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `m` | `bigint` | A bigint representation of a plaintext message |
| `r?` | `bigint` | The random integer factor for encryption. By default is a random in (1,n) |

#### Returns

`bigint`

The encryption of m with this public key

#### Defined in

PublicKey.ts:39

___

### multiply

▸ **multiply**(`c`, `k`): `bigint`

Pseudo-homomorphic Paillier multiplication

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `c` | `bigint` | a number m encrypted with this public key |
| `k` | `number` \| `bigint` | either a bigint or a number |

#### Returns

`bigint`

- the encryption of k·m with this public key

#### Defined in

PublicKey.ts:67

# Vectoral Clasification Language (Just Fun)

## Overview

The aim of the project is to create microservices in all popular software languages in accordance with the specified conditions. The syntax will be elastic and rigid like sql. In this way, it aims to allow precise and preliminary debugging.


## Syntax

### Supported Variable types
- bintx -> biginteger or bigserial primary key
- uuid{1-5}x -> uuid primary key and auto generated
- buid{1-5} -> uuid(base64 format} primary key and auto generated
- dbl -> double
- flt -> float
- int{8,16,32,64,128} -> int...
- bool -> boolean
- char | char{32} -> varchar
- text -> text
- json
- yaml
- time -> timestamptz
- date -> date
- point -> point(lat,long)
- poly -> polygon(point1,...2,...)

### Supported 

### Collection Example

```vcl

declare shorEnumConstructor bigPKey = `$1 is contain primary bigint type and rule on unique type`

users instanceof collection as {
  do declare it fields:
     - id is contain primary bigint type and rule on unique type
     - id pkey intx
     - id instanceof bigPKey
        attach
          -> user_company_permission->where('user_id',self)
        do it
          if on:destroy
            -> delete user_company_permission->where('user_id',self) 
            elif on:change
            -> edit user_company_permission->where('user_id',self)
}

```

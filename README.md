# SCRUD Ramp

<img src="logo/scrud-ramp-128.png" align="right">

SCRUD interface generator

Generate a SCRUD interface given field definations and access rights

## SCRUD Pack

Fields to use and their order

```
{
  slim: 'slim ramp definition', // or
  json: 'json definition', // or
  schema: 'JSON schema definition',
  key: 'KEY_FIELD_NAME', // defaults to id
  list: 'field list',
  search: 'search fields', // defaults to 'list' fields if omitted
  create: 'field list', // * for all, defaults to 'list' fields if omitted
  read: 'field list', // * for all, defaults to 'list' fields if omitted
  update: 'field list', // * for all, defaults to 'list' fields if omitted
  delete: 'field list', // * for all, defaults to 'read' fields if omitted
  route: 'option list', // route options
}
```

## SCRUD Ops

Contains a schema and SCRUD operations to perform form by permissions group

Linux method of specific inclusion

```
{
  all: { // everyone
    source: 'type;[protocol://][user:password]@path',
    pack: scrudPack
  },
  user: { // authenticated user
    extends: "all", // extends the all group
    add: scrudPack
  },
  rolename: { // specific user role
    extends: "user|other_role",
    add: scrudPack
  }
}
```

## License

MIT

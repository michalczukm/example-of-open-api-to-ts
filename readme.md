# Example of generating types based on swagger file

> Context of this repo - I am using it repo during **TypeScript** workshops.

We will use [openapi-typescript](https://github.com/drwpow/openapi-typescript) package to generate types from OpenApi config files (JSON or yaml)

**Why?** To be always in-sync with our API.

**When?** You can run it manually periodically, you can run it on every build, you can run it on pre-push git hook (and verify if something changed). Up to you 😊

## Runbook

Example with `npx`

```sh
npx openapi-typescript https://petstore.swagger.io/v2/swagger.json --output petstore.ts
```

Example script in `package.json`

```json
{
  // ...
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "generate:types": "openapi-typescript https://petstore.swagger.io/v2/swagger.json --output petstore.ts"
  },
  "devDependencies": {
    "openapi-typescript": "^3.2.2"
  }
  //...
}
```

Rule:

```sh
openapi-typescript <remote or local file path> --output <out file path>
```

## Examples

### OMDb API

The Open Movie Database ☁️ http://omdbapi.com/

OpenApi JSON file

- remote https://www.omdbapi.com/swagger.json
- local [opendbapi-swagger.json](./open-api-configs/opendbapi-swagger.json)

### Swagger Petstore

Example provided by Swagger ☁️ https://petstore.swagger.io/

- remote https://petstore.swagger.io/v2/swagger.json
- local [swagger-petstore](./open-api-configs/swagger-petstore.json)

### LaunchDarkly

Feature flag & Toggle management service. Just an example of some commercial solution ;)

☁️ https://launchdarkly.com/

- remote https://launchdarkly.github.io/ld-openapi/openapi.yaml

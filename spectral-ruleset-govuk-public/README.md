# Spectral ruleset for public UK government APIs

A set of API linting rules that correspond with API linting rules as prescribed across public UK government APIs.

## Running locally
To run the tests locally:
- Run `npm install`
- Run `npm test`


## Usage

### Via NPM

This package is published as a package on NPM, under [@govuk-data-standards/spectral-ruleset-govuk-public](https://www.npmjs.com/package/@govuk-data-standards/spectral-ruleset-govuk-public).

It can be used as an NPM package using the following `package.json`:

```json
{
  "devDependencies": {
    "@stoplight/spectral-cli": "^6.2.0",
    "@govuk-data-standards/spectral-ruleset-govuk-public": "^0.1.0"
  },
  "scripts": {
    "lint:oas": "spectral lint '*/openapi.yml'"
  }
}
```

Then, when using the following `.spectral.yaml`:

```yaml
extends:
  - '@govuk-data-standards/spectral-ruleset-govuk-public'
formats:
  - "oas3.1"
```

You can run:

```
npm run lint:oas
```

### Via HTTPS URL

This ruleset can also be used via the HTTPS URL in the ruleset, for instance by adding just the Spectral CLI package in your `package.json` file:

```json
{
  "devDependencies": {
    "@stoplight/spectral-cli": "^6.2.0"
  },
  "scripts": {
    "lint:oas": "spectral lint '*/openapi.yml'"
  }
}
```


Then, when using the following `.spectral.yaml`:

```yaml
extends:
  - https://raw.githubusercontent.com/co-cddo/api-standards-linting/spectral-ruleset-govuk-public-v0.3.0/spectral-ruleset-govuk-public/ruleset.yaml
formats:
  - "oas3.1"
```

## Continuous Integration

You can lint your OpenAPI documents as part of your CI pipeline. As this is an NPM package, you can run it using most CI solutions. 

You can follow the instructions in the [Spectral documentation](https://meta.stoplight.io/docs/spectral/038632fdf0d1a-continuous-integration) for using Spectral in CI pipelines and specify this ruleset using an HTTPS URL in your `.spectral.yaml`, as described above. 

Alternatively you can install the NPM package in your repository as described above, and run it as you would any NPM package. An example of this using Github Actions can be found in the [federated API model repository](https://github.com/co-cddo/federated-api-model/blob/main/.github/workflows/openapi-docs-pr.yml).

## Rulesets

There are 3 different rulesets available in this NPM package. The default ruleset is the least opinionated. There are two more rulesets that are increasingly opinionated, `ruleset-medium.yaml` and `ruleset-high.yaml`. `ruleset-high.yaml` is the most opinionated of the 3 rulesets.

To use either the medium or high rulesets, you can specify this in your `.spectral.yaml` file. For example to use the medium one:

```yaml
extends:
  - '@govuk-data-standards/spectral-ruleset-govuk-public/ruleset-medium.yaml'
formats:
  - "oas3.1"
```

You can also use the ruleset via HTTPS url, for example to use the medium ruleset:

```yaml
extends:
  - https://raw.githubusercontent.com/co-cddo/api-standards-linting/spectral-ruleset-govuk-public-v0.3.0/spectral-ruleset-govuk-public/ruleset-medium.yaml
formats:
  - "oas3.1"
```

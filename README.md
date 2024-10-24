# Unified Merchant Master

## Workflows

[![Studio Validator](https://github.com/Fiserv/unified-merchant-master/actions/workflows/validator.yaml/badge.svg?event=pull_request)](https://github.com/Fiserv/unified-merchant-master/actions/workflows/validator.yaml) [![Studio Zip Generator](https://github.com/Fiserv/unified-merchant-master/actions/workflows/zip-generator.yaml/badge.svg)](https://github.com/Fiserv/unified-merchant-master/actions/workflows/zip-generator.yaml)

----------

## Dev Studio - UMM Template repo

This repo contains the content for tenants of Developer Studio.

To read about how to edit these files refer to the [Tenant Documentation](https://github.com/fiserv/tenant-docs)

### Directory structure

- `/docs` : All markdown files are to be placed in this directory
- `/assets` :  Static assets like image etc here
- `/config/document-explorer-definition.yaml` : Provide document tree structure for dev studio left side navigation.
- `/config/tenant.json` : Tenant configuration file
- `/config/product-layout.yaml` : Yaml spec for product page content
- `/reference/[api-version]/openapi.yaml` : Tenant OpenAPI 3.0 Spec
- `.docignore` : Use `.docignore` to hide markdown files from showing up in the doc explorer and from being indexed & searchable

#### Configure `tenant.json` `product-layout.yaml` `document-explorer-definition.yaml`

DO NOT modify the structure.

DO update the sections that are needed.  Look for "REPLACE ME".  You can then replace the text for that field.

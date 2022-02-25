# CATH API documentation

## About

Many of the dynamic features of the [CATH web pages](http://www.cathdb.info) are based on calls to a RESTful API. As a result, the CATH API is publicly accessible and well tested, however the documentation needs improvement.

We are still in the process of providing automatically generated docs / tests for the API (via OpenAPI spec). While that project is ongoing - I'll (unofficially) document some of the available REST endpoints here.

**Please note: we do not expect these endpoints to change substantially however we do reserve the right to make changes/improvements where necessary**

## Superfamily

### List all CATH Superfamilies

**`GET`** `/version/:version_id/api/rest/superfamily`

http://www.cathdb.info/version/v4_3_0/api/rest/superfamily

### Get information about a particular CATH Superfamily

**`GET`** `/version/:version_id/api/rest/superfamily/:sfam_id`

http://www.cathdb.info/version/v4_3_0/api/rest/superfamily/1.10.8.10

## Domains

### Get a summary of information about a particular CATH domain

**`GET`** `/version/:version_id/api/rest/domain_summary/:domain_id`

http://www.cathdb.info/version/v4_3_0/api/rest/domain_summary/1cukA01

### Get a PDB file for a particular CATH domain

**`GET`** `/version/:version_id/api/rest/id/:domain_id.pdb`

http://www.cathdb.info/version/v4_3_0/api/rest/id/1cukA01.pdb

### Get a static image for a particular CATH domain

**`GET`** `/version/:version_id/api/rest/id/:domain_id.png?size=[S|M|L]`

http://www.cathdb.info/version/v4_3_0/api/rest/id/1cukA01.png?size=L

### List all CATH domains in a particular Superfamily

**`GET`** `/version/:version_id/api/rest/superfamily/:sfam_id`

http://www.cathdb.info/version/v4_3_0/api/rest/superfamily/1.10.8.10

## Functional Families (FunFams)

### List all FunFams in a CATH Superfamily

**`GET`** `/version/:version_id/api/rest/superfamily/:sfam_id/funfam`

http://www.cathdb.info/version/v4_3_0/api/rest/superfamily/1.10.8.10/funfam

### Get information on a particular FunFam

**`GET`** `/version/:version_id/api/rest/superfamily/:sfam_id/funfam/:funfam_number`

http://www.cathdb.info/version/v4_3_0/api/rest/superfamily/1.10.8.10/funfam/1302

### Get FunFam alignment (STOCKHOLM format)

**`GET`** `/version/:version_id/api/rest/superfamily/:sfam_id/funfam/:funfam_number/files/stockholm`

http://www.cathdb.info/version/v4_3_0/superfamily/3.40.50.620/funfam/88701/files/stockholm

### Get FunFam alignment for a given UniProtKB accession

**`GET`** `/version/:version_id/api/rest/uniprot_to_funfam/:uniprot_acc`

http://www.cathdb.info/version/v4_3_0/api/rest/uniprot_to_funfam/P00520 (YAML)

http://www.cathdb.info/version/v4_3_0/api/rest/uniprot_to_funfam/P00520?content-type=application/json (JSON)

## Classification

### List all children of a particular 'node' in the CATH hierarchy

**`GET`** `/version/:version_id/api/rest/cathtree/from_cath_id_to_depth/:node_id/:depth`

http://www.cathdb.info/version/v4_3_0/api/rest/cathtree/from_cath_id_to_depth/1.10.8.10/9

Note: this lists all the domains in the superfamily '1.10.8.10'. There are 9 depths in total
that correspond to clusters with increasing levels of similarity: C, A, T, H, S, O, L, I, D (see CATH documentation for more info).

## Function

### List all unique EC terms associated with PDB structures in a particular Superfamily

**`GET`** `/version/${version}/api/rest/superfamily/${sfam_id}/ec`

http://www.cathdb.info/version/v4_3_0/api/rest/superfamily/1.10.8.10/ec



# Fixes issue #3899 of neos/media

## Source

* https://github.com/neos/neos-development-collection/issues/3899

## The motivation for this package

After adding Neos Media with Composer and running ./flow doctrine:migrate,
the following error occurs:

An exception occurred while executing

```
'ALTER TABLE typo3_media_domain_model_asset ADD CONSTRAINT FK_B8306B8EBC91F416 FOREIGN KEY (resource) REFERENCES typo3_flow_resource_resource (persistence_object_identifier)':
SQLSTATE[HY000]: General error: 1005 Can't create table `sampleonly`.`typo3_media_domain_model_asset` (errno: 150 "Foreign key constraint is incorrectly formed")
```

It seems like some of the older migrations in the package aren't working.

## The solution for the problem

Modify the order of migration and disable all the migrations from the media package

## requirements

```text
- Flow: ^7.3+ || 8.0
```

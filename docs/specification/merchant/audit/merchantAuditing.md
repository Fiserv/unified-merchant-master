# UMM Audit Capability

UMM provides the ability to monitor changes made at both the entity and field levels.It maintains separate tables, UMM_AUDIT_INFO and UMM_AUDIT_ADDITIONAL_INFO, to track all modifications within the UMM database.

UMM also provides capability in Inquiry API to retrieve a snapshot of merchant data based on effective date.

## Audit Entity References

* See [**UMM_AUDIT_INFO**](?path=docs/specification/merchant/audit/umm-audit-info.md)
* See [**UMM_AUDIT_ADDITIONAL_INFO**](?path=docs/specification/merchant/audit/umm-audit-additional-info.md)

### Sample Queries

#### Queries to find out merchants got added in last 1 Hour

```text


select * from UMM.UMM_AUDIT_INFO info
WHERE info.BE_PLATFORM_CODE = 'NORTH' 
AND info.CHANGED_TIMESTAMP > DATEADD ( HOUR , -1, current_timestamp())
and info.ACTION = 'INSERT'
and info.table_name = 'MERCHANT'

```

#### Queries to retrieve details on UPDATE made to the MERCHANT_ATTRIBUTES entity in the past 1 hour

```text

select INFO.BE_PLATFORM_CODE, INFO.MERCHANT_ID , INFO.TABLE_NAME entity_name , add.key_column_value attribute_id , info.AUDIT_COLUMN_NAME field_name  , 
     INFO.OLD_VALUE, INFO.NEW_VALUE 
from UMM.UMM_AUDIT_INFO  info , UMM.UMM_AUDIT_ADDITIONAL_INFO  add 
WHERE info.BE_PLATFORM_CODE = 'NORTH' 
AND info.CHANGED_TIMESTAMP > DATEADD ( HOUR , -1, current_timestamp())
and info.ACTION = 'UPDATE'
and info.table_name = 'MERCHANT_ATTRIBUTES'
AND INFO.ID = ADD.ID 

```

---

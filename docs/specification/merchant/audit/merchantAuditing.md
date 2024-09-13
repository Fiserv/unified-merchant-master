# UMM Audit Capability

UMM offers the functionality to track modifications made to each entity. Each entity includes columns for `EFFECTIVE_START_DATE` and `EFFECTIVE_END_DATE`, allowing users to access both the current and previous snapshots of records. The `EFFECTIVE_START_DATE` indicates when a record was added, while the `EFFECTIVE_END_DATE` indicates when a record was closed. Whenever the `EFFECTIVE_END_DATE` is null, it signifies the currently active record. By leveraging the combination of start and end dates, users can retrieve historical snapshots of records.

UMM has separate tables `UMM_AUDIT_INFO` & `UMM_AUDIT_ADDITIONAL_INFO` to track all changes happening in UMM database.

UMM also provides capability in Inquiry API to retrieve a snapshot of merchant data based on effective date.

---

## References

* See [**UMM_AUDIT_INFO**](?path=docs/specification/merchant/audit/umm-audit-info.md)
* See [**UMM_AUDIT_ADDITIONAL_INFO**](?path=docs/specification/merchant/audit/umm-audit-additional-info.md)

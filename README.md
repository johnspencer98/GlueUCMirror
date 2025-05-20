# GlueUCMirror
Mirror tables from UC to Glue

**Goals:**
1. Check if table exists in Glue.
2. If it exists, compare the schema or metadata.
3. If it's different, update the Glue table with the latest schema.
4. If it doesn't exist, create it as usual.

How it works:
1. Schema comparisons are done using sets to be insensitive to column order.
2. Location change is also checked to reflect moved tables.
3. Glue’s update_table() API supports partial metadata overwrite, including schema and storage.

❗ Gotchas:
1. Glue does not support column reordering.
2. You might need to cast or normalize data types (e.g., decimal(10,2) vs double).




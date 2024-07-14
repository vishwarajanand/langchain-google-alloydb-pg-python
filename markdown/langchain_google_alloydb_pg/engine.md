# Engine


### _class_ langchain_google_alloydb_pg.engine.AlloyDBEngine(engine: sqlalchemy.ext.asyncio.engine.AsyncEngine, loop: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[asyncio.events.AbstractEventLoop], thread: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[threading.Thread](https://python.readthedocs.io/en/latest/library/threading.html#threading.Thread)])
A class for managing connections to a AlloyDB database.


#### _async_ _aexecute(query: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), params: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[dict](https://python.readthedocs.io/en/latest/library/stdtypes.html#dict)] = None)
Execute a SQL query.


#### _async_ _aexecute_outside_tx(query: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str))
Execute a SQL query.


#### _async_ _aload_table_schema(table_name: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str))
Load table schema from existing table in PgSQL database.


* **Returns**

    The loaded table.



* **Return type**

    (sqlalchemy.Table)



#### _async_ ainit_document_table(table_name: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), content_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'page_content', metadata_columns: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[langchain_google_alloydb_pg.engine.Column] = [], metadata_json_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'langchain_metadata', store_metadata: [bool](https://python.readthedocs.io/en/latest/library/functions.html#bool) = True)
Create a table for saving of langchain documents.


* **Parameters**

    
    * **table_name** ([*str*](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)) – The PgSQL database table name.


    * **metadata_columns** (*List**[**Column**]*) – A list of Columns
    to create for custom metadata. Optional.


    * **store_metadata** ([*bool*](https://python.readthedocs.io/en/latest/library/functions.html#bool)) – Whether to store extra metadata in a metadata column
    if not described in ‘metadata’ field list (Default: True).



### _class_ langchain_google_alloydb_pg.engine.Column(name: 'str', data_type: 'str', nullable: 'bool' = True)

### _async_ langchain_google_alloydb_pg.engine._get_iam_principal_email(credentials: [google.auth.credentials.Credentials](https://googleapis.dev/python/google-auth/latest/reference/google.auth.credentials.html#google.auth.credentials.Credentials))
Get email address associated with current authenticated IAM principal.

Email will be used for automatic IAM database authentication to AlloyDB.


* **Parameters**

    **credentials** ([*google.auth.credentials.Credentials*](https://googleapis.dev/python/google-auth/latest/reference/google.auth.credentials.html#google.auth.credentials.Credentials)) – The credentials object to use in finding the associated IAM
    principal email address.



* **Returns**

    The email address associated with the current authenticated IAM
    principal.



* **Return type**

    email ([str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str))

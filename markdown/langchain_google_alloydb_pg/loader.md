# Document Loader


### _class_ langchain_google_alloydb_pg.loader.AlloyDBDocumentSaver(key: [object](https://python.readthedocs.io/en/latest/library/functions.html#object), engine: langchain_google_alloydb_pg.engine.AlloyDBEngine, table_name: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), content_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), metadata_columns: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = [], metadata_json_column: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None)
A class for saving langchain documents into a AlloyDB database table.


#### _async_ aadd_documents(docs: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[langchain_core.documents.base.Document])
Save documents in the DocumentSaver table. Document’s metadata is added to columns if found or
stored in langchain_metadata JSON column.


* **Parameters**

    **docs** (*List**[**langchain_core.documents.Document**]*) – a list of documents to be saved.



#### _async_ adelete(docs: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[langchain_core.documents.base.Document])
Delete all instances of a document from the DocumentSaver table by matching the entire Document
object.


* **Parameters**

    **docs** (*List**[**langchain_core.documents.Document**]*) – a list of documents to be deleted.



### _class_ langchain_google_alloydb_pg.loader.AlloyDBLoader(key: [object](https://python.readthedocs.io/en/latest/library/functions.html#object), engine: langchain_google_alloydb_pg.engine.AlloyDBEngine, query: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), content_columns: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)], metadata_columns: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)], formatter: [Callable](https://python.readthedocs.io/en/latest/library/typing.html#typing.Callable)[[[Dict](https://python.readthedocs.io/en/latest/library/typing.html#typing.Dict)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any)], [Iterable](https://python.readthedocs.io/en/latest/library/typing.html#typing.Iterable)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]], [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)], metadata_json_column: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None)
Load documents from AlloyDB\`.

Each document represents one row of the result. The content_columns are
written into the content_columns of the document. The metadata_columns are written
into the metadata_columns of the document. By default, first columns is written into
the page_content and everything else into the metadata.


#### _async_ alazy_load()
Load AlloyDB data into Document objects lazily.


#### _async_ aload()
Load AlloyDB data into Document objects.


#### _async classmethod_ create(engine: langchain_google_alloydb_pg.engine.AlloyDBEngine, query: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, table_name: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, content_columns: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, metadata_columns: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, metadata_json_column: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, format: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, formatter: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[Callable](https://python.readthedocs.io/en/latest/library/typing.html#typing.Callable)] = None)
Constructor for AlloyDBLoader


* **Parameters**

    
    * **engine** (*AlloyDBEngine*) – AsyncEngine with pool connection to the postgres database


    * **query** (*Optional**[*[*str*](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)*]**, **optional*) – SQL query. Defaults to None.


    * **table_name** (*Optional**[*[*str*](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)*]**, **optional*) – Name of table to query. Defaults to None.


    * **content_columns** (*Optional**[**List**[*[*str*](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)*]**]**, **optional*) – Column that represent a Document’s page_content. Defaults to the first column.


    * **metadata_columns** (*Optional**[**List**[*[*str*](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)*]**]**, **optional*) – Column(s) that represent a Document’s metadata.. Defaults to None.


    * **metadata_json_column** (*Optional**[*[*str*](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)*]**, **optional*) – Column to store metadata as JSON. Defaults to “langchain_metadata”.


    * **format** (*Optional**[*[*str*](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)*]**, **optional*) – Format of page content (OneOf: text, csv, YAML, JSON). Defaults to ‘text’.


    * **formatter** (*Optional**[**Callable**]**, **optional*) – A function to format page content (OneOf: format, formatter). Defaults to None.



* **Returns**

    AlloyDBLoader



#### lazy_load()
Load AlloyDB data into Document objects lazily.


#### load()
Load AlloyDB data into Document objects.

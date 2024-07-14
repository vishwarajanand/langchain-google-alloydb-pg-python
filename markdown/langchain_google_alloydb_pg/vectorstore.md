# Vector Store


### _class_ langchain_google_alloydb_pg.vectorstore.AlloyDBVectorStore(key: [object](https://python.readthedocs.io/en/latest/library/functions.html#object), engine: langchain_google_alloydb_pg.engine.AlloyDBEngine, embedding_service: langchain_core.embeddings.embeddings.Embeddings, table_name: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), content_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'content', embedding_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'embedding', metadata_columns: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = [], id_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'langchain_id', metadata_json_column: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = 'langchain_metadata', distance_strategy: langchain_google_alloydb_pg.indexes.DistanceStrategy = DistanceStrategy.COSINE_DISTANCE, k: [int](https://python.readthedocs.io/en/latest/library/functions.html#int) = 4, fetch_k: [int](https://python.readthedocs.io/en/latest/library/functions.html#int) = 20, lambda_mult: [float](https://python.readthedocs.io/en/latest/library/functions.html#float) = 0.5, index_query_options: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[langchain_google_alloydb_pg.indexes.QueryOptions] = None)
Google AlloyDB Vector Store class


#### _async_ aadd_documents(documents: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[langchain_core.documents.base.Document], ids: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Run more documents through the embeddings and add to the vectorstore.


* **Parameters**

    **documents** – Documents to add to the vectorstore.



* **Returns**

    List of IDs of the added texts.



#### _async_ aadd_texts(texts: [Iterable](https://python.readthedocs.io/en/latest/library/typing.html#typing.Iterable)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)], metadatas: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[dict](https://python.readthedocs.io/en/latest/library/stdtypes.html#dict)]] = None, ids: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Run more texts through the embeddings and add to the vectorstore.


* **Parameters**

    
    * **texts** – Iterable of strings to add to the vectorstore.


    * **metadatas** – Optional list of metadatas associated with the texts.


    * **\*\*kwargs** – vectorstore specific parameters.



* **Returns**

    List of ids from adding the texts into the vectorstore.



#### add_documents(documents: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[langchain_core.documents.base.Document], ids: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Add or update documents in the vectorstore.


* **Parameters**

    
    * **documents** – Documents to add to the vectorstore.


    * **kwargs** – Additional keyword arguments.
    if kwargs contains ids and documents contain ids,
    the ids in the kwargs will receive precedence.



* **Returns**

    List of IDs of the added texts.



#### add_texts(texts: [Iterable](https://python.readthedocs.io/en/latest/library/typing.html#typing.Iterable)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)], metadatas: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[dict](https://python.readthedocs.io/en/latest/library/stdtypes.html#dict)]] = None, ids: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Run more texts through the embeddings and add to the vectorstore.


* **Parameters**

    
    * **texts** – Iterable of strings to add to the vectorstore.


    * **metadatas** – Optional list of metadatas associated with the texts.


    * **\*\*kwargs** – vectorstore specific parameters.
    One of the kwargs should be ids which is a list of ids
    associated with the texts.



* **Returns**

    List of ids from adding the texts into the vectorstore.



#### _async_ adelete(ids: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Delete by vector ID or other criteria.


* **Parameters**

    
    * **ids** – List of ids to delete.


    * **\*\*kwargs** – Other keyword arguments that subclasses might use.



* **Returns**

    True if deletion is successful,
    False otherwise, None if not implemented.



* **Return type**

    Optional[[bool](https://python.readthedocs.io/en/latest/library/functions.html#bool)]



#### _async classmethod_ afrom_documents(documents: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[langchain_core.documents.base.Document], embedding: langchain_core.embeddings.embeddings.Embeddings, engine: langchain_google_alloydb_pg.engine.AlloyDBEngine, table_name: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), ids: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, content_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'content', embedding_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'embedding', metadata_columns: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = [], ignore_metadata_columns: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, id_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'langchain_id', metadata_json_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'langchain_metadata', \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Return VectorStore initialized from documents and embeddings.


* **Parameters**

    
    * **documents** – List of Documents to add to the vectorstore.


    * **embedding** – Embedding function to use.



#### _async classmethod_ afrom_texts(texts: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)], embedding: langchain_core.embeddings.embeddings.Embeddings, engine: langchain_google_alloydb_pg.engine.AlloyDBEngine, table_name: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), metadatas: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[dict](https://python.readthedocs.io/en/latest/library/stdtypes.html#dict)]] = None, ids: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, content_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'content', embedding_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'embedding', metadata_columns: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = [], ignore_metadata_columns: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, id_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'langchain_id', metadata_json_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'langchain_metadata', \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Return VectorStore initialized from texts and embeddings.


* **Parameters**

    
    * **texts** – Texts to add to the vectorstore.


    * **metadatas** – Optional list of metadatas associated with the texts.


    * **embedding** – Embedding function to use.



#### _async_ amax_marginal_relevance_search(query: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, fetch_k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, lambda_mult: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[float](https://python.readthedocs.io/en/latest/library/functions.html#float)] = None, filter: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Return docs selected using the maximal marginal relevance.

Maximal marginal relevance optimizes for similarity to query AND diversity
among selected documents.


* **Parameters**

    
    * **query** – Text to look up documents similar to.


    * **k** – Number of Documents to return. Defaults to 4.


    * **fetch_k** – Number of Documents to fetch to pass to MMR algorithm.


    * **lambda_mult** – Number between 0 and 1 that determines the degree
    of diversity among the results with 0 corresponding
    to maximum diversity and 1 to minimum diversity.
    Defaults to 0.5.



* **Returns**

    List of Documents selected by maximal marginal relevance.



#### _async_ amax_marginal_relevance_search_by_vector(embedding: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[float](https://python.readthedocs.io/en/latest/library/functions.html#float)], k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, fetch_k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, lambda_mult: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[float](https://python.readthedocs.io/en/latest/library/functions.html#float)] = None, filter: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Return docs selected using the maximal marginal relevance.


#### _async_ asimilarity_search(query: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, filter: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Return docs most similar to query.


* **Parameters**

    
    * **query** – Input text.


    * **k** – Number of Documents to return. Defaults to 4.



* **Returns**

    List of Documents most similar to the query.



#### _async_ asimilarity_search_by_vector(embedding: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[float](https://python.readthedocs.io/en/latest/library/functions.html#float)], k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, filter: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Return docs most similar to embedding vector.


* **Parameters**

    
    * **embedding** – Embedding to look up documents similar to.


    * **k** – Number of Documents to return. Defaults to 4.



* **Returns**

    List of Documents most similar to the query vector.



#### _async_ asimilarity_search_with_score(query: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, filter: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Run similarity search with distance.


* **Returns**

    List of Tuples of (doc, similarity_score)



#### _async classmethod_ create(engine: langchain_google_alloydb_pg.engine.AlloyDBEngine, embedding_service: langchain_core.embeddings.embeddings.Embeddings, table_name: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), content_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'content', embedding_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'embedding', metadata_columns: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = [], ignore_metadata_columns: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, id_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'langchain_id', metadata_json_column: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = 'langchain_metadata', distance_strategy: langchain_google_alloydb_pg.indexes.DistanceStrategy = DistanceStrategy.COSINE_DISTANCE, k: [int](https://python.readthedocs.io/en/latest/library/functions.html#int) = 4, fetch_k: [int](https://python.readthedocs.io/en/latest/library/functions.html#int) = 20, lambda_mult: [float](https://python.readthedocs.io/en/latest/library/functions.html#float) = 0.5, index_query_options: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[langchain_google_alloydb_pg.indexes.QueryOptions] = None)
Constructor for AlloyDBVectorStore.
:param engine: Connection pool engine for managing connections to AlloyDB database.
:type engine: AlloyDBEngine
:param embedding_service: Text embedding model to use.
:type embedding_service: Embeddings
:param table_name: Name of the existing table or the table to be created.
:type table_name: str
:param content_column: Column that represent a Document’s page_content. Defaults to “content”.
:type content_column: str
:param embedding_column: Column for embedding vectors. The embedding is generated from the document value. Defaults to “embedding”.
:type embedding_column: str
:param metadata_columns: Column(s) that represent a document’s metadata.
:type metadata_columns: List[str]
:param ignore_metadata_columns: Column(s) to ignore in pre-existing tables for a document’s metadata. Can not be used with metadata_columns. Defaults to None.
:type ignore_metadata_columns: List[str]
:param id_column: Column that represents the Document’s id. Defaults to “langchain_id”.
:type id_column: str
:param metadata_json_column: Column to store metadata as JSON. Defaults to “langchain_metadata”.
:type metadata_json_column: str


#### delete(ids: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Delete by vector ID or other criteria.


* **Parameters**

    
    * **ids** – List of ids to delete.


    * **\*\*kwargs** – Other keyword arguments that subclasses might use.



* **Returns**

    True if deletion is successful,
    False otherwise, None if not implemented.



* **Return type**

    Optional[[bool](https://python.readthedocs.io/en/latest/library/functions.html#bool)]



#### _property_ embeddings(_: langchain_core.embeddings.embeddings.Embedding_ )
Access the query embedding object if available.


#### _classmethod_ from_documents(documents: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[langchain_core.documents.base.Document], embedding: langchain_core.embeddings.embeddings.Embeddings, engine: langchain_google_alloydb_pg.engine.AlloyDBEngine, table_name: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), ids: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, content_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'content', embedding_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'embedding', metadata_columns: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = [], ignore_metadata_columns: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, id_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'langchain_id', metadata_json_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'langchain_metadata', \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Return VectorStore initialized from documents and embeddings.


* **Parameters**

    
    * **documents** – List of Documents to add to the vectorstore.


    * **embedding** – Embedding function to use.



#### _classmethod_ from_texts(texts: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)], embedding: langchain_core.embeddings.embeddings.Embeddings, engine: langchain_google_alloydb_pg.engine.AlloyDBEngine, table_name: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), metadatas: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[dict](https://python.readthedocs.io/en/latest/library/stdtypes.html#dict)]] = None, ids: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, content_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'content', embedding_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'embedding', metadata_columns: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = [], ignore_metadata_columns: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)]] = None, id_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'langchain_id', metadata_json_column: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str) = 'langchain_metadata', \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Return VectorStore initialized from texts and embeddings.


* **Parameters**

    
    * **texts** – Texts to add to the vectorstore.


    * **metadatas** – Optional list of metadatas associated with the texts.


    * **embedding** – Embedding function to use.



#### max_marginal_relevance_search(query: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, fetch_k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, lambda_mult: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[float](https://python.readthedocs.io/en/latest/library/functions.html#float)] = None, filter: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Return docs selected using the maximal marginal relevance.

Maximal marginal relevance optimizes for similarity to query AND diversity
among selected documents.


* **Parameters**

    
    * **query** – Text to look up documents similar to.


    * **k** – Number of Documents to return. Defaults to 4.


    * **fetch_k** – Number of Documents to fetch to pass to MMR algorithm.


    * **lambda_mult** – Number between 0 and 1 that determines the degree
    of diversity among the results with 0 corresponding
    to maximum diversity and 1 to minimum diversity.
    Defaults to 0.5.



* **Returns**

    List of Documents selected by maximal marginal relevance.



#### max_marginal_relevance_search_by_vector(embedding: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[float](https://python.readthedocs.io/en/latest/library/functions.html#float)], k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, fetch_k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, lambda_mult: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[float](https://python.readthedocs.io/en/latest/library/functions.html#float)] = None, filter: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Return docs selected using the maximal marginal relevance.

Maximal marginal relevance optimizes for similarity to query AND diversity
among selected documents.


* **Parameters**

    
    * **embedding** – Embedding to look up documents similar to.


    * **k** – Number of Documents to return. Defaults to 4.


    * **fetch_k** – Number of Documents to fetch to pass to MMR algorithm.


    * **lambda_mult** – Number between 0 and 1 that determines the degree
    of diversity among the results with 0 corresponding
    to maximum diversity and 1 to minimum diversity.
    Defaults to 0.5.



* **Returns**

    List of Documents selected by maximal marginal relevance.



#### similarity_search(query: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, filter: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Return docs most similar to query.


* **Parameters**

    
    * **query** – Input text.


    * **k** – Number of Documents to return. Defaults to 4.



* **Returns**

    List of Documents most similar to the query.



#### similarity_search_by_vector(embedding: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[float](https://python.readthedocs.io/en/latest/library/functions.html#float)], k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, filter: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Return docs most similar to embedding vector.


* **Parameters**

    
    * **embedding** – Embedding to look up documents similar to.


    * **k** – Number of Documents to return. Defaults to 4.



* **Returns**

    List of Documents most similar to the query vector.



#### similarity_search_with_score(query: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), k: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[int](https://python.readthedocs.io/en/latest/library/functions.html#int)] = None, filter: [Optional](https://python.readthedocs.io/en/latest/library/typing.html#typing.Optional)[[str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str)] = None, \*\*kwargs: [Any](https://python.readthedocs.io/en/latest/library/typing.html#typing.Any))
Run similarity search with distance.


* **Returns**

    List of Tuples of (doc, similarity_score)



### langchain_google_alloydb_pg.vectorstore.cosine_similarity(X: [Union](https://python.readthedocs.io/en/latest/library/typing.html#typing.Union)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[float](https://python.readthedocs.io/en/latest/library/functions.html#float)]], [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[numpy.ndarray], numpy.ndarray], Y: [Union](https://python.readthedocs.io/en/latest/library/typing.html#typing.Union)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[[float](https://python.readthedocs.io/en/latest/library/functions.html#float)]], [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[numpy.ndarray], numpy.ndarray])
Row-wise cosine similarity between two equal-width matrices.


### langchain_google_alloydb_pg.vectorstore.maximal_marginal_relevance(query_embedding: numpy.ndarray, embedding_list: [list](https://python.readthedocs.io/en/latest/library/stdtypes.html#list), lambda_mult: [float](https://python.readthedocs.io/en/latest/library/functions.html#float) = 0.5, k: [int](https://python.readthedocs.io/en/latest/library/functions.html#int) = 4)
Calculate maximal marginal relevance.


### _class_ langchain_google_alloydb_pg.indexes.BaseIndex(name: str = 'langchainvectorindex', index_type: str = 'base', distance_strategy: langchain_google_alloydb_pg.indexes.DistanceStrategy = <factory>, partial_indexes: Optional[List[str]] = None)

### _class_ langchain_google_alloydb_pg.indexes.DistanceStrategy(value)
Enumerator of the Distance strategies.


#### _generate_next_value_(start, count, last_values)
Generate the next value when not given.

name: the name of the member
start: the initial start value or None
count: the number of existing members
last_value: the last value assigned or None


#### _member_type_()
alias of [`object`](https://python.readthedocs.io/en/latest/library/functions.html#object)


### _class_ langchain_google_alloydb_pg.indexes.ExactNearestNeighbor(name: str = 'langchainvectorindex', index_type: str = 'exactnearestneighbor', distance_strategy: langchain_google_alloydb_pg.indexes.DistanceStrategy = <factory>, partial_indexes: Optional[List[str]] = None)

### _class_ langchain_google_alloydb_pg.indexes.HNSWIndex(name: str = 'langchainvectorindex', index_type: str = 'hnsw', distance_strategy: langchain_google_alloydb_pg.indexes.DistanceStrategy = <factory>, partial_indexes: Optional[List[str]] = None, m: int = 16, ef_construction: int = 64)

### _class_ langchain_google_alloydb_pg.indexes.HNSWQueryOptions(ef_search: [int](https://python.readthedocs.io/en/latest/library/functions.html#int) = 40)

### _class_ langchain_google_alloydb_pg.indexes.IVFFlatIndex(name: str = 'langchainvectorindex', index_type: str = 'ivfflat', distance_strategy: langchain_google_alloydb_pg.indexes.DistanceStrategy = <factory>, partial_indexes: Optional[List[str]] = None, lists: int = 100)

### _class_ langchain_google_alloydb_pg.indexes.IVFFlatQueryOptions(probes: [int](https://python.readthedocs.io/en/latest/library/functions.html#int) = 1)

### _class_ langchain_google_alloydb_pg.indexes.IVFIndex(name: str = 'langchainvectorindex', index_type: str = 'ivf', distance_strategy: langchain_google_alloydb_pg.indexes.DistanceStrategy = <factory>, partial_indexes: Optional[List[str]] = None, lists: int = 100)

### _class_ langchain_google_alloydb_pg.indexes.IVFQueryOptions(probes: [int](https://python.readthedocs.io/en/latest/library/functions.html#int) = 1)

### _class_ langchain_google_alloydb_pg.indexes.QueryOptions()

### _class_ langchain_google_alloydb_pg.indexes.ScaNNIndex(name: str = 'langchainvectorindex', index_type: str = 'ScaNN', distance_strategy: langchain_google_alloydb_pg.indexes.DistanceStrategy = <factory>, partial_indexes: Optional[List[str]] = None, num_leaves: int = 5)

### _class_ langchain_google_alloydb_pg.indexes.StrategyMixin(operator: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), search_function: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), index_function: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), scann_index_function: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str))

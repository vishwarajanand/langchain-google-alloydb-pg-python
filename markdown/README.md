# AlloyDB for PostgreSQL for LangChain

[

![image](https://img.shields.io/badge/support-preview-orange.svg)

](https://github.com/googleapis/google-cloud-python/blob/main/README.rst#stability-levels) [

![image](https://img.shields.io/pypi/v/langchain-google-alloydb-pg.svg)

](https://pypi.org/project/langchain-google-alloydb-pg/) [

![image](https://img.shields.io/pypi/pyversions/langchain-google-alloydb-pg.svg)

](https://pypi.org/project/langchain-google-alloydb-pg/)


* [Client Library Documentation](https://cloud.google.com/python/docs/reference/langchain-google-alloydb-pg/latest)


* [Product Documentation](https://cloud.google.com/alloydb)

## Quick Start

In order to use this library, you first need to go through the following
steps:


1. [Select or create a Cloud Platform project.](https://console.cloud.google.com/project)


2. [Enable billing for your project.](https://cloud.google.com/billing/docs/how-to/modify-project#enable_billing_for_a_project)


3. [Enable the AlloyDB API.](https://console.cloud.google.com/flows/enableapi?apiid=alloydb.googleapis.com)


4. [Setup Authentication.](https://googleapis.dev/python/google-api-core/latest/auth.html)

### Installation

Install this library in a [virtualenv](https://virtualenv.pypa.io/en/latest/) using pip. [virtualenv](https://virtualenv.pypa.io/en/latest/) is a tool to create isolated Python environments. The basic problem it addresses is
one of dependencies and versions, and indirectly permissions.

With [virtualenv](https://virtualenv.pypa.io/en/latest/), it’s
possible to install this library without needing system install
permissions, and without clashing with the installed system
dependencies.

#### Supported Python Versions

Python >= 3.8

#### Mac/Linux

```console
pip install virtualenv
virtualenv <your-env>
source <your-env>/bin/activate
<your-env>/bin/pip install langchain-google-alloydb-pg
```

#### Windows

```console
pip install virtualenv
virtualenv <your-env>
<your-env>\Scripts\activate
<your-env>\Scripts\pip.exe install langchain-google-alloydb-pg
```

## Example Usage

Code samples and snippets live in the [samples/](https://github.com/googleapis/langchain-google-alloydb-pg-python/tree/main/samples) folder.

### Vector Store Usage

Use a vector store to store embedded data and perform vector search.

```python
from langchain_google_alloydb_pg import AlloyDBEngine, AlloyDBVectorStore
from langchain_google_vertexai import VertexAIEmbeddings


engine = AlloyDBEngine.from_instance("project-id", "region", "my-cluster", "my-instance", "my-database")
embeddings_service = VertexAIEmbeddings(model_name="textembedding-gecko@003")
vectorstore = AlloyDBVectorStore.create_sync(
    engine,
    table_name="my-table",
    embedding_service=embeddings_service
)
```

See the full [Vector Store](https://github.com/googleapis/langchain-google-alloydb-pg-python/tree/main/docs/vector_store.ipynb) tutorial.

### Document Loader Usage

Use a document loader to load data as LangChain `Document`s.

```python
from langchain_google_alloydb_pg import AlloyDBEngine, AlloyDBLoader


engine = AlloyDBEngine.from_instance("project-id", "region", "my-cluster", "my-instance", "my-database")
loader = AlloyDBLoader.create_sync(
    engine,
    table_name="my-table-name"
)
docs = loader.lazy_load()
```

See the full [Document Loader](https://github.com/googleapis/langchain-google-alloydb-pg-python/tree/main/docs/document_loader.ipynb) tutorial.

## Chat Message History Usage

Use `ChatMessageHistory` to store messages and provide conversation
history to LLMs.

```python
from langchain_google_alloydb_pg import AlloyDBChatMessageHistory, AlloyDBEngine


engine = AlloyDBEngine.from_instance("project-id", "region", "my-cluster", "my-instance", "my-database")
history = AlloyDBChatMessageHistory.create_sync(
    engine,
    table_name="my-message-store",
    session_id="my-session-id"
)
```

See the full [Chat Message History](https://github.com/googleapis/langchain-google-alloydb-pg-python/tree/main/docs/chat_message_history.ipynb) tutorial.

### Contributions

Contributions to this library are always welcome and highly encouraged.

See [CONTRIBUTING](https://github.com/googleapis/langchain-google-alloydb-pg-python/tree/main/CONTRIBUTING.md) for more information how to get started.

Please note that this project is released with a Contributor Code of Conduct. By participating in
this project you agree to abide by its terms. See [Code of Conduct](https://github.com/googleapis/langchain-google-alloydb-pg-python/tree/main/CODE_OF_CONDUCT.md) for more
information.

## License

Apache 2.0 - See
[LICENSE](https://github.com/googleapis/langchain-google-alloydb-pg-python/tree/main/LICENSE)
for more information.

## Disclaimer

This is not an officially supported Google product.

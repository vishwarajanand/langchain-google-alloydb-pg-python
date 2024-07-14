# Chat Message History


### _class_ langchain_google_alloydb_pg.chat_message_history.AlloyDBChatMessageHistory(key: [object](https://python.readthedocs.io/en/latest/library/functions.html#object), engine: langchain_google_alloydb_pg.engine.AlloyDBEngine, session_id: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), table_name: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), messages: [List](https://python.readthedocs.io/en/latest/library/typing.html#typing.List)[langchain_core.messages.base.BaseMessage])
Chat message history stored in an AlloyDB.


#### _async_ aadd_message(message: langchain_core.messages.base.BaseMessage)
Append the message to the record in AlloyDB


#### _async_ aadd_messages(messages: [Sequence](https://python.readthedocs.io/en/latest/library/typing.html#typing.Sequence)[langchain_core.messages.base.BaseMessage])
Async add a list of messages.


* **Parameters**

    **messages** – A sequence of BaseMessage objects to store.



#### _async_ aclear()
Clear session memory from AlloyDB


#### add_message(message: langchain_core.messages.base.BaseMessage)
Add a Message object to the store.


* **Parameters**

    **message** – A BaseMessage object to store.



* **Raises**

    [**NotImplementedError**](https://python.readthedocs.io/en/latest/library/exceptions.html#NotImplementedError) – If the sub-class has not implemented an efficient
        add_messages method.



#### add_messages(messages: [Sequence](https://python.readthedocs.io/en/latest/library/typing.html#typing.Sequence)[langchain_core.messages.base.BaseMessage])
Add a list of messages.

Implementations should over-ride this method to handle bulk addition of messages
in an efficient manner to avoid unnecessary round-trips to the underlying store.


* **Parameters**

    **messages** – A sequence of BaseMessage objects to store.



#### clear()
Remove all messages from the store


### _async_ langchain_google_alloydb_pg.chat_message_history._aget_messages(engine: langchain_google_alloydb_pg.engine.AlloyDBEngine, session_id: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str), table_name: [str](https://python.readthedocs.io/en/latest/library/stdtypes.html#str))
Retrieve the messages from AlloyDB

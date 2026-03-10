

# RAG -> retrival Augumented Generation.

A RAG has mainly 5 components.
-> Document Loaders.
-> Text Splitters.
-> Vector Databases.
-> Retrivers.

# Document loaders
Document loader is a componet of langchain, which helps to load the data from various sources as document objects, which further can be used for chunking, embedding, retrival and generation.

Document(
    page_content='...'
    metadata={}
)

Few types of Document Loaders:-

TextLoader.
PdfLoader.
CSVLoader.
webBasedLoader.
databaseBasedLoader.
directoryBasedLoader.


```
loader= TextLoader('insights.txt')
docs= loader.load()
```

here `docs` is nothing but a list constaining the `Document Objects`.

# load vs lazy_load
load-> it eagerly loads the data, and returns a list of document object.
lazy_loading -> it loads on demand, and returns a generator of the document objjects.


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
PdfLoader. (makes a document object per page.)
CSVLoader. ( makes a document object per record.)
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

Question 1. when using WebBAsedLoader, why it is necessary to insatall beautifulsoup4.
`beautifulsoup4` help to extract text content present inside the html tags

# Text Splitting.
Text splitting is the process of breaking down the the large/huge collection of the text into the chunks.
This is done so, because it helps to get better context or enhanches the quality of semantics during the embedings.

# Types of Text Splitters.
1. length based text splitter.(In this we initially decides the size of chunk that is going to be formed. the size can be in form of characters or tokens.)

2. text structure based splitter.(this is based on the structure of the the paragraph. it assumes that paragrap consists up of line, lines are make of words and words are nothing but the collection of letters. This recursive approach uses the hierarchical structure of the paragraph to split the text. it uses the seperators like `\n\n` to chunk the text based on paragraphs, similarly it uses `\n` for sentence based chunking, `_` for word based chunking and`''` for character based chunking.)

3. 


3. document structure based splitter.
4. semantic meaning based text splitters. 

Question 2. What is the difference between split_text vs split_documnets.

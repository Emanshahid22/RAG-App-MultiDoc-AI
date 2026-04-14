# RAG App: A Customizable Retrieval-Augmented Generation Application

![](assets/image.webp)

RAG App is a Python-based application designed to enhance natural language understanding by incorporating document (PDF/CSV) retrieval capabilities. It uses Retrieval-Augmented Generation (RAG) to answer queries based on private and previously unseen document collections, enabling accurate and contextual responses.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/aliosmankaya/rag-app.git
   cd rag-app
   ```
2. Install dependencies using Poetry:
   ```bash
   poetry install
   ```

## Project Tree

```
📦 rag-app
├─ .gitignore
├─ LICENSE
├─ README.md
├─ assets
│  └─ image.webp
├─ main.py
├─ poetry.lock
├─ pyproject.toml
├─ settings.toml
└─ src
   ├─ __init__.py
   ├─ api
   │  ├─ __init__.py
   │  ├─ db.py
   │  ├─ file.py
   │  ├─ model.py
   │  └─ search.py
   ├─ config.py
   ├─ core
   │  ├─ __init__.py
   │  ├─ db.py
   │  ├─ file.py
   │  └─ model.py
   └─ parser
      ├─ __init__.py
      ├─ db.py
      ├─ file.py
      ├─ model.py
      └─ search.py
```

## Usage

1. **Run the Application:**
   ```bash
   python main.py
   ```
2. **File Operations:**
   - Upload File
     - POST /upload
       - Upload a file with multipart/form-data (PDF/CSV).
       - Response: { "Uploaded successfully." }
   - List Files
     - GET /list
       - Retrieve all uploaded files.
       - Response: [ *files ]
   - Update File
     - PUT /update
       - Update an existing file with multipart/form-data.
       - Response: { "Updated successfully." }
   - Delete File
     - DELETE /delete
       - Delete a file.
       - Response: { "Deleted successfully." }

3. **Database Operations:**
   - Create Vector DB Collection
     - POST /create
       - Create a vector database collection.
       - Response: { "Created successfully." }
   - Insert File to Collection
     - POST /insert
       - Insert embeddings of the file to the collection.
       - Response: { "Inserted successfully." }
   - List Collections
     - GET /list
       - Retrieve all uploaded collections.
       - Response: [ *collections ]
   - Update Collection
     - PUT /update
       - Update an existing collection.
       - Response: { "Updated successfully." }
   - Delete Collection
     - DELETE /delete
       - Delete a collection.
       - Response: { "Deleted successfully." }

4. **Search:**
   - Search relevant chunks (part of the file)
     - POST /search
       - Search with a query on the file.
       - Response: [ *chunks ]

5. **Model:**
   - Question answering powered by a LLM model using RAG
     - POST /model
       - Asking question about the file and answering by a LLM.
       - Response: { "..." }

## Customization & Configuration

- Modify `settings.toml` to adjust retrieval or generation parameters.
- Update `pyproject.toml` for dependency management.

## Contributions

# RAG App - MultiDoc AI

Developed by: Eman Shahid

## License

This project is licensed under the [Apache 2.0 License](LICENSE).

---

Feel free to modify or add more specific instructions if needed!

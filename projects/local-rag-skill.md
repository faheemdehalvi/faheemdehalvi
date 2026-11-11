# Local document question answering skill

The [local RAG skill](https://github.com/faheemdehalvi/rag-skill) connects Claude Code to a document question-answering workflow using [RAG-Anything](https://github.com/HKUDS/RAG-Anything), LightRAG and MinerU. Those upstream projects provide the retrieval and parsing systems. The skill supplies the setup, configuration and working interface around them.

## What it is for

The workflow ingests documents into a named knowledge base and then answers questions using that material. Its configuration supports local models through Ollama, alongside an optional external-provider setup.

The useful question is whether the system can locate the right material for a particular task and support an answer with a source the reader can check.

## Engineering decisions worth explaining

- Each knowledge base records its embedding model. Changing that model affects whether existing vectors remain compatible.
- Parsing affects what can be retrieved. The README identifies optional vision support, so image handling depends on the configured setup.
- Setup and operating costs differ. Initial model downloads and document ingestion should be separated from later question-answering measurements.
- Local model configuration and external-provider configuration have different data paths. Review the actual configuration before handling sensitive documents.

## Evidence and current limits

The public README was reviewed on 11 November 2026 at [source snapshot 14afdd6](https://github.com/faheemdehalvi/rag-skill/tree/14afdd6bd5a3d615908906034bc2b401e2f9dbbe). The note describes the documented integration; it does not establish retrieval accuracy, privacy guarantees for every dependency or performance on a particular document collection.

No new document-answering benchmark was run for this write-up.

## An evaluation to add

Choose a small set of documents and questions with known answers and source passages. Include questions the documents cannot answer. Keep evaluation examples separate from those used to adjust the setup. Record answer correctness, source support, failure types and response time, with model and parser versions.

That would give readers evidence about a defined use case. A result from one collection would still need its scope explained.

[Repository](https://github.com/faheemdehalvi/rag-skill) · [Upstream RAG-Anything](https://github.com/HKUDS/RAG-Anything) · [My writing](https://faheemdehalvi.github.io/)

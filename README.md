BioSeeq/BioSeek is a turnkey engine that indexes arbitrary FASTA/FASTQ across a file tree and supports full-text + sequence queries out of the box.

Whoosh/Lucene + SeqKit combo (custom).

Sourmash for similarity/k-mer search.

Seqrepo for sequence storage, but not file-based.

Lucene/Elasticsearch for metadata/full-text

Sourmash or custom k-mer index for sequence search

Web frontend/api

PostgreSQL + pg_trgm + full-text search for metadata and filenames.
Avoids extra components, good performance, easy to index and query.

PostgreSQL scales well with:

High RAM → keeps indexes/caches hot.

NVMe RAID0 → fast I/O for sequential + random access.

Parallel queries + tuned work_mem, shared_buffers.

 part of the project could be a 10-15 minute trial to hottune the database for max trhoughput

 Auto-tuning script (e.g., in Python or Bash) can:

Benchmark typical queries.

Adjust work_mem, shared_buffers, parallel_*, effective_cache_size.

Measure throughput, pick optimal settings.

# Miracle Code — Bangla AI Universe (Phase‑1)

সংক্ষিপ্ত: লোকাল‑ফার্স্ট প্রোটোটাইপ — চ্যাট থেকে নোড এক্সট্র্যাকশন → স্টোর → সার্চ → RAG → রিপোর্ট।

প্রয়োজনীয় ধাপ: 
1. Python 3.10+ ইনস্টল করুন।
2. পরিবেশ সেটআপ: `bash scripts/prepare_env.sh`
3. ডেটা যুক্ত: `assets/data/*.json`
4. ইনজেস্ট চালান: `python src/ingest/load_json.py --input assets/data/*.json`
5. সার্ভিস চালান (ডেভ): `uvicorn src.api.prompt_engine:app --reload --port 8000`

ডিফল্ট কনফিগ:
- DB: SQLite (assets/db/miracle.db)
- Embedding provider: ENV `EMBEDDING_PROVIDER` (ডিফল্ট: none — সিমুলেট)
- Vector store: FAISS (placeholder)

ফাইলসমূহ:
- src/ingest/ : ডেটা লোডিং
- src/utils/ : নরমালাইজ ও ক্লিনিং
- src/search/ : BM25 index (স্টাব)
- src/rag/ : RAG pipeline (স্টাব)
- src/api/ : FastAPI prompt 엔ডপয়েন্ট
- assets/data/ : নমুনা ইনপুট

লক্ষ্য: Lovable‑এ আপলোড করে দ্রুত ডেমো চালাতে পারেন। পরবর্তীতে Neo4j/Obsidian exporter যুক্ত করা যাবে।
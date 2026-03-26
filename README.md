# Feature-Specific Review Summarisation and Multilingual Translation for E-Commerce Amazon Product Reviews
Project Title: Feature-Specific Review Summarisation and Multilingual Translation for E-Commerce Amazon Product Reviews

Overview: Generates aspect-based opinion summaries from English Amazon product reviews and translates them into Tamil and Malayalam across seven aspects — Overall, Product Quality, Value for Money, Packaging and Presentation, Delivery and Shipping, Variety and Curation, and Customer Service. Built without any parallel corpora, using machine translation and cross-lingual LLM generalisation.

Dataset: Amazon Reviews 2023 (Subscription Boxes) — 16,216 raw reviews filtered to 7,340 based on helpful votes and verified purchase status. Reviews are cleaned, aspect-tagged using keyword-based and LLM-assisted detection, and grouped by product and aspect.

Approach: Three paths were implemented. Path 1 uses TF-IDF extractive summarisation followed by translation via Google Translate and IndicTrans2. Path 2 uses the same extractive summary but evaluates using pivot back-translation, scoring translated output by round-tripping it back to English. Path 3 skips translation entirely — Gemma 3 27B is prompted zero-shot via OpenRouter to generate Tamil and Malayalam summaries directly from raw English reviews.

Results: Path 2 achieved the strongest scores (Tamil chrF 88.43, Malayalam chrF 90.06). Path 1 with IndicTrans2 outperformed Google Translate for Tamil. Path 3 showed moderate content retention, expected given the compression from ten chunks into one summary.

Tech Stack: Python, TF-IDF, IndicTrans2, Google Translate API, Gemma 3 27B (OpenRouter), ROUGE, chrF




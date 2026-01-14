Quote Predictor

Link : https://shivamdhawan330-quote-generator.hf.space/


The Quote Prediction App is an AI-powered application designed to help users

A) find quotes by:
1) Normal Search (Searching quotes by matching keywords)

2) Semantic Search (Vector Search - closest keyword to the given keyword) and

B) generate new quotes using fine tuned GPT model (PHI-3 Mini) based on: - Category (e.g., Love, Motivation, Life) - Author writing style (e.g., Napoleon Hill, Rumi)

Depending on the selected category or author, the model adapts its tone, vocabulary, and structure accordingly.

Key Objectives
Build a custom fine-tuned language model instead of relying purely on prompting
Keep the model small, efficient, and affordable to train
Allow conditional generation using category and author metadata
Model Choice
Selected Model
Phi-3 Mini (4K Context) by Microsoft
Why Phi-3 Mini?
Lightweight yet powerful
Supports LoRA fine-tuning
Ideal for small-to-medium custom datasets
Dataset Description
Source File
quotes.csv
Columns
Column Name	Description
Quote	The full quote text
Author	Name of the author
Category	Quote category (Love, Motivational, etc.)
Example Row
Quote : Be a free thinker and don't accept everything you hear as truth. Be critical and evaluate what you believe in.
Author : Aristotle
Category : Philosophical

Contain a dataset of ~7000 Quotes by different authors categorized by different categories.

Category	Author	Quotes Count	Category Count
Philosphical	Aristotle	250	1711
Chanakya	211		
Confucius	250		
Laozi	250		
Marcus Aurelius	250		
Ralph Waldo Emerson	250		
Socrates	250		
Motivational	Abdul Kalam	210	1656
Maya Angelou	250		
Napoleon Hill	250		
Oprah Winfrey	250		
Ratan Tata	196		
Tony Robbins	250		
Zig Ziglar	250		
Humor	Benjamin Franklin	250	1606
Dorothy Parker	250		
Groucho Marx	250		
Khushwant Singh	106		
Mark Twain	250		
Oscar Wilde	250		
Woody Allen	250		
Love	Arundhati Roy	250	1750
Jane Austen	250		
Khalil Gibran	250		
Leo Tolstoy	250		
Nicholas Sparks	250		
Pablo Neruda	250		
William Shakespeare	250		
Celeb	Elon Musk	234	234
PROCESS:



Training Architecture
Fine-Tuning Method
LoRA (Low-Rank Adaptation)
What Gets Fine-Tuned?
Only small adapter layers are trained while the base model remains frozen.

Modified Components
Attention projection layers (Q, K, V, O)
Feed-forward projection layers
Benefits
Very low GPU memory usage
Faster training
No catastrophic forgetting
Model Fine Tuning Strategy
The dataset is transformed into Prompt-Completion pairs for supervised fine-tuning.

Prompt Template
Category: <CATEGORY> | Author: <AUTHOR>
Quote:

Completion
<FULL_QUOTE_TEXT>

Why This Format?
Forces the model to condition on category and author
Keeps a single fine-tuned model for all categories/authors
Enables flexible inference later
Technology Stack
Did HTML parsed Web Scraping using BeautifulSoap
Fine Tuned open source available model PHI-3 MINI using LoRA through Unsloth
Use VS Code as IDE for backend Flask App
Use PyPI library for English Vocabulary and saved it in .JSON format
Used all-miniLM-L6-V2, a BERT based transformer, for Sematic Similarity
Core Libraries
Python 3.10+
PyTorch
Hugging Face Transformers
Datasets
PEFT
Unsloth
Optional (Inference / App Layer)
Flask
SentenceTransformers
Pandas
App Usage Guide


Design Decisions Explained
Why Not Train Separate Models?
Expensive
Hard to maintain
Redundant knowledge
Why Conditional Prompting?
One model → many behaviors
Scales better
Easier to extend
Conclusion
The Quote Prediction Project demonstrates how small, efficient language models can be customized for creative tasks using modern fine-tuning techniques like LoRA. It provides a scalable foundation for building intelligent writing assistants without massive infrastructure costs.

Built with curiosity, experimentation, and a deep interest in understanding how language models learn style and meaning.

!! Copyright (c) 2025 Shivam Dhawan. All rights reserved.
This app is proprietary and confidential.
Unauthorized copying, modification, distribution, or use is strictly prohibited. !!

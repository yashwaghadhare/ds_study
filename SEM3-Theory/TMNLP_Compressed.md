# TMNLP (Text Mining and NLP): Complete Compressed Notes (Units 1 to 4)

> Exam-revision notes (updated to the latest question bank: removed questions are no longer included). Every remaining question is covered, merged by theme, with **no formulas** (formulas are explained in words).
> Q numbers in brackets (e.g., Q5) match the question bank of that unit.
> Each unit ends with a **Last-Minute Cheat Sheet**. The file ends with **Fill-in-the-Blanks and MCQ answers**.

## Contents
1. [Unit 1: NLP Foundations, Applications, Language Structure and Compilers](#unit-1)
2. [Unit 2: Text Pre-processing and Text Representation](#unit-2)
3. [Unit 3: Text Classification and Machine Learning Models](#unit-3)
4. [Unit 4: Transformers, Attention and Seq2Seq](#unit-4)
5. [Fill-in-the-Blanks and MCQs (quick answers)](#quick-answers)

---

<a id="unit-1"></a>
# UNIT 1: NLP Foundations, Applications, Language Structure and Compilers

## BLOCK A: What NLP Is and What It Does
*(Q6, Q3, Q4, Q5, Q8, Q9, Q11)*

### Q6. NLP: definition, purpose, applications, importance
- **NLP = Natural Language Processing.** The branch of computer science and AI that lets computers **understand, interpret and generate human language** (English, Hindi, etc.).
- **Purpose:** bridge the gap between human language and computers; let people interact with machines in normal language instead of code; extract meaning and useful information from text and speech.
- **Major applications:** machine translation (Google Translate), chatbots and virtual assistants (Siri, Alexa), sentiment analysis, text summarization, spam detection, speech recognition.
- **Importance:** makes human-computer interaction natural, handles the huge amount of text data created daily, powers everyday tools, saves time.
- *Example:* "What is the weather today?" → speech converted to text → meaning understood → answer found → natural reply.

### Q3. Text Mining
- **Text mining** = digging useful information and hidden patterns out of large amounts of written text. Most text (emails, reviews, social media) is **unstructured** (not in rows and columns); text mining turns it into organised knowledge.

**Steps (how unstructured text becomes information):**
1. **Text collection:** gather raw text (documents, websites, reviews).
2. **Pre-processing:** clean it (remove punctuation, lowercase, remove stop-words).
3. **Tokenization:** break it into tokens (usually words).
4. **Feature extraction:** turn words into numbers (e.g., word frequencies).
5. **Apply techniques:** classification, clustering, pattern discovery.
6. **Produce information:** trends, topics, summaries.

- **Can discover:** common topics, sentiments, important names, places and keywords.
- *Example:* thousands of customer reviews are cleaned and analysed to find many complaints about "slow delivery".

### Q4. Sentiment Analysis
- Using NLP to automatically find the **feeling or opinion** in text: **positive, negative or neutral** (some systems also detect emotions like joy, anger, sadness).
- **How:** clean and tokenize text → study the words and meaning → decide the overall sentiment.

**Applications:** product and service reviews, social media monitoring, customer feedback, political analysis, market research, brand reputation management.

- *Example:* a phone's reviews are positive about the camera but negative about the battery → company improves the battery.

### Q5. NLP in Machine Translation
- **Machine Translation (MT)** = automatically translating text or speech from a **source language** to a **target language** (e.g., English to Hindi).
- **Role of NLP:** understands the **meaning** (not just word replacement), handles grammar differences between languages, manages ambiguity, produces natural sentences in the target language.

**Major steps:** text input → tokenization → analysis (parsing) → meaning representation → **transfer / mapping** to target language → **generation** of a correct sentence → output.

- *Example:* "How are you?" → Hindi translation. Without NLP, it would be a poor word-by-word translation.

### Q8. NLP-based Chatbot
- A program that talks with users through text or voice and uses NLP to **understand meaning, not just fixed keywords** (unlike simple rule-based bots).

**Steps:**
1. **User input** ("I want to book a ticket").
2. **Pre-processing** (clean, tokenize).
3. **Intent recognition** (what the user wants: booking).
4. **Entity extraction** (details: destination, date, time).
5. **Processing / decision** (check databases).
6. **Response generation** (natural reply).
7. **Output** (shown or spoken).

- *Example:* "Book a train from Delhi to Mumbai tomorrow" → intent = booking; entities = Delhi, Mumbai, tomorrow.

### Q9. Text Summarization
- Using NLP to create a **short, clear summary** of a long text without losing the main meaning.
- **Role of NLP:** understands meaning and importance of sentences, finds main ideas, removes less important details, keeps the summary readable.

| Type | How it works |
|---|---|
| **Extractive** | Picks the most important **existing sentences** and joins them |
| **Abstractive** | Understands the text and **writes new sentences** in its own words, like a human |

**Steps:** text input → pre-processing (split into sentences and tokens) → **importance scoring** (word frequency, position, keywords) → selection (extractive) or generation (abstractive) → summary output.

- *Example:* a news app showing a 3-line summary above a long article.

### Q11. Named Entity Recognition (NER)
- An NLP task that **finds and labels named real-world things (entities)** in text. It highlights who, where, when and which organisation.

| Entity type | Example |
|---|---|
| **Person** | Sachin Tendulkar |
| **Location** | Mumbai |
| **Organisation** | Google |
| **Date/Time** | 25 May 2018 |
| **Money/Quantity** | Amounts and numbers |

**How entities are identified:** tokenization → **POS tagging** (helps spot nouns) → **feature analysis** (capital letters, position, surrounding words) → **classification** (rule-based or machine-learning model labels each token as an entity type or "not an entity") → tagged output.

- **Importance:** extracts key facts; powers search engines, chatbots, news analysis, information extraction, question answering.
- *Example:* "Sundar Pichai became the CEO of Google in 2015 in California" → Person, Organisation, Date, Location.

---

## BLOCK B: Language Structure (Syntax, Token and Lexeme)
*(Q1, Q7)*

### Q1. Syntax Analysis, Parser and Parse Tree
- **Syntax analysis** = checking whether a sentence (or line of code) follows the **grammar rules** and understanding how its parts fit together. It comes **after tokenization**.
- **Parser** = the tool that performs syntax analysis. It reads tokens one by one and checks them against grammar rules: confirms valid arrangement, **reports a syntax error** if grammar is broken, **builds a structure** if correct.
- **Parse tree** = a tree diagram of the grammatical structure:
  - **Root** = the whole sentence.
  - **Branches** = smaller parts (noun phrase, verb phrase).
  - **Leaves** = the actual words.
- **Importance:** checks grammatical correctness, reveals structure needed for deeper meaning analysis, essential in both NLP and compilers.
- *Example:* "The cat sat on the mat" → sentence splits into noun phrase ("The cat") and verb phrase ("sat on the mat").

### Q7. Token vs Lexeme
| | **Lexeme** | **Token** |
|---|---|---|
| Meaning | The **actual sequence of characters** in the input (raw text) | The **category/type** a lexeme belongs to |
| Example (count = 10) | count, =, 10 | IDENTIFIER, OPERATOR, NUMBER |

- *Shop analogy:* lexeme = the actual item (an apple); token = its category (fruit).
- **Importance:** foundation of the first stage (**lexical analysis**); organises raw text into groups; makes parsing possible.
- *Example:* "price = 50" → lexemes: price, =, 50 → tokens: IDENTIFIER, ASSIGNMENT OPERATOR, NUMBER.

---

## BLOCK C: Compilers
*(Q10, Q12)*

### Q10. Compiler and its phases
- **Compiler** = a program that translates **high-level code** (C, Java) into **machine language** (0s and 1s). It also **checks for errors** while translating.

| Phase | What it does |
|---|---|
| **1. Lexical Analysis** | Breaks source code into **tokens** (keywords, identifiers, symbols), done by the **lexer** |
| **2. Syntax Analysis (Parsing)** | Checks tokens against grammar rules and builds a **parse tree**; grammar errors caught here |
| **3. Semantic Analysis** | Checks **meaning** (e.g., adding a number to a word, using a variable before declaring it) |
| **4. Intermediate Code Generation** | Converts the program into a simpler, **machine-independent** code |
| **5. Code Optimization** | Improves the code to run **faster and use less memory** without changing what it does |
| **6. Code Generation** | Produces the final **machine/target code** |

- **Supporting parts:** **Symbol table** (stores information about variables and functions) and **Error handler** (reports errors in each phase).
- *Example:* compiling a C program that prints "Hello" goes through all six phases.

### Q12. Intermediate Code Generation
- The compiler phase that converts the source program into a simpler **in-between form**, after checking meaning but **before** producing final machine code. It is **not tied to any specific machine**.

**Purpose:** bridge between high-level and low-level code; make optimization easier; keep the compiler independent of any particular machine.

**Advantages:**
- **Machine independence:** same intermediate code can produce machine code for different computers.
- **Easier optimization.**
- **Reusability:** one front end can pair with many back ends.
- **Simpler translation** in smaller steps.

**Common forms:** **Three-address code** (each instruction has at most three parts), syntax trees, postfix notation.

- *Example:* "x = a + b * c" becomes: first multiply b and c into a temporary, then add a to that temporary, then assign the result to x.

---

## BLOCK D: Word Embeddings (Overview)
*(Q2)*

### Q2. Word Embeddings: Word2Vec, GloVe, FastText
- **Word embedding** = representing each word as a list of numbers (a **vector**) in a mathematical space, so words with **similar meanings sit close together**. Computers need numbers, not words.

| Method | How it learns | Key feature | Example |
|---|---|---|---|
| **Word2Vec** | From the **context** (words around a target word). Two approaches: **CBOW** (predicts a word from surrounding words) and **Skip-Gram** (predicts surrounding words from one word) | Words in similar contexts get similar vectors | "king" and "queen" end up close |
| **GloVe** (Global Vectors) | From **global co-occurrence** counts across the whole text collection | Captures overall language relationships | "ice" appears often with "cold" |
| **FastText** | Breaks words into **subwords (character n-grams)**; word = sum of its pieces | Handles **rare, unseen or misspelled** words | "playing" understood from "play" + "ing" |

- **Importance:** machines understand meaning and similarity; power translation, search, chatbots; capture relationships like **king − man + woman = queen**.
- *Example:* a search for "automobile" also shows "car" results; FastText even handles the typo "autombile".

---

## Unit 1: Last-Minute Cheat Sheet
- **NLP** = computers understanding human language. Apps: translation, chatbots, sentiment, summarization, spam detection, speech recognition.
- **Text mining steps:** collect → pre-process → tokenize → feature extraction → apply techniques → information.
- **Sentiment analysis** = positive / negative / neutral.
- **MT steps:** input → tokenize → parse → meaning → transfer → generate → output.
- **Chatbot:** input → pre-process → **intent** → **entities** → decision → response → output.
- **Summarization:** **extractive** (picks sentences) vs **abstractive** (writes new ones).
- **NER:** Person, Location, Organisation, Date, Money.
- **Parser** builds a **parse tree** (root = sentence, leaves = words).
- **Lexeme = actual text. Token = its category.**
- **Compiler phases (6):** Lexical → Syntax → Semantic → Intermediate Code → Optimization → Code Generation (+ Symbol table, Error handler).
- **Intermediate code** = machine-independent (three-address code).
- **Embeddings:** Word2Vec (context: CBOW/Skip-Gram), GloVe (global co-occurrence), FastText (subwords).

---

<a id="unit-2"></a>
# UNIT 2: Text Pre-processing and Text Representation

## BLOCK A: Text Pre-processing
*(Q12, Q10, Q7, Q3, Q2)*

### Q12. Importance of text pre-processing
- **Pre-processing** = cleaning and organising raw text (messy: punctuation, capitals, common words, different word forms) so it is ready for NLP models.

**Common steps:**
1. **Lowercasing** ("Apple" = "apple").
2. **Removing punctuation and symbols.**
3. **Tokenization** (words or sentences).
4. **Stop-word removal** ("the", "is").
5. **Stemming / Lemmatization** (base forms).
6. **Removing numbers / special characters** where not needed.

**Importance:** improves accuracy, reduces noise, **shrinks vocabulary** (faster), makes text consistent, makes it easier to convert to vectors.
**Without it:** models get confused, accuracy drops, processing is slower, the same word in different forms is wrongly treated as different.
- *Example:* "The Product is AMAZING!!!" → "product amazing".

### Q10. Word Tokenization vs Sentence Tokenization
- **Tokenization** = breaking text into smaller pieces called **tokens** (one of the first NLP steps).

| | **Word Tokenization** | **Sentence Tokenization** |
|---|---|---|
| Output unit | Individual **words** (and punctuation) | Whole **sentences** |
| Example | "I love NLP" → [I, love, NLP] | "I love NLP. It is fun." → ["I love NLP.", "It is fun."] |
| Clues used | Spaces and punctuation | Full stops, question marks, etc. |
| Use | Embeddings and counting | Summarization and translation |

- *Example:* a summarizer splits an article into sentences first, then splits chosen sentences into words.

### Q7. Stop-word Removal
- **Stop-words** = very common words with little meaning (the, is, and, a, in). **Removal** = deleting them in pre-processing so only meaningful words remain.

**How:** prepare a stop-word list → tokenize → remove tokens found in the list → keep the rest.

| Advantages | Limitations |
|---|---|
| Reduces data size (faster) | **Can lose meaning** ("to be or not to be" becomes almost empty) |
| Removes noise | **Harms some tasks** (in sentiment analysis, "not" is important) |
| Improves performance | **Language-dependent** lists |
| Saves memory | |

- *Example:* "The weather is very good today" → "weather good today". Removing "not" from "not good" would flip the meaning.

### Q3 + Q2. Stemming vs Lemmatization

| | **Stemming (Q3)** | **Lemmatization (Q2)** |
|---|---|---|
| Meaning | Reduces a word to its **root (stem)** by **chopping endings** | Converts a word to its proper **base/dictionary form (lemma)** using grammar and meaning |
| Method | Simple rules, **no dictionary** | Uses **dictionary + part of speech + grammar rules** |
| Result | May be a **non-word** ("studies" → "studi") | Always a **valid word** ("studies" → "study") |
| Speed | Faster | Slower but more accurate |
| Examples | playing, played, plays → play | running, ran, runs → run; better → good; was/is/are → be; children → child |

**Stemming algorithms:**
- **Porter Stemmer:** most popular; applies rules step by step (happiness → happi).
- **Lancaster Stemmer:** more **aggressive** and faster; can over-shorten words.
- **Snowball Stemmer:** improved Porter; supports **many languages**, more accurate.

- **Importance (both):** group related word forms, shrink vocabulary, improve search and accuracy.
- *Example:* search "running shoes" → lemmatized "run" also matches "run" and "runs"; stemming "connect, connected, connecting, connection" → "connect".

---

## BLOCK B: Frequency-based Representation (BoW, TF, IDF)
*(Q1, Q6, Q9)*

### Q1. Bag-of-Words (BoW)
- Represents text by **counting how often each word appears**, ignoring grammar and word order (like shaking all words in a bag).

**How:** build a vocabulary of all unique words → count each word per document → each document becomes a **vector of counts**.

| Advantages | Limitations |
|---|---|
| Simple and easy | **Ignores word order** ("Dog bites man" = "Man bites dog") |
| Fast | **Ignores meaning** ("happy" vs "joyful") |
| Effective baseline (spam, topic tasks) | **Large, sparse vectors** (mostly zeros) |
| | **No context** (cannot handle polysemy) |

- BoW is the foundation for **TF-IDF**; its limits explain why embeddings were developed.

### Q6. Term Frequency (TF)
- **How often a word appears in one document.** The more it appears, the more important it may be for that document.
- **Calculation (in words):** number of times the word appears divided by the total number of words in the document (dividing keeps it fair for long and short documents).
- *Example:* "data" appears 3 times in a 100-word document → TF = 3 out of 100 = **0.03**. "cricket" 10 times in 200 words → 0.05.
- **Role:** identifies important words, key part of **TF-IDF**, helps search engines rank documents, turns text into numbers.
- **Limitation:** common words ("the", "is") get high TF but carry no meaning → fixed by combining with **IDF**.

### Q9. Inverse Document Frequency (IDF)
- Measures **how rare or unique a word is across a whole collection** of documents. **Rarer word = higher IDF** (more meaningful).
- **Calculation (in words):** take the logarithm of (total number of documents divided by number of documents containing the word).
- *Example:* 1000 documents, "data" in 100 of them → ratio 10 → IDF = log of 10 = 1. A word in almost every document → IDF close to **0**.
- **Role:** reduces importance of very common words, increases importance of rare meaningful words; combined with TF gives **TF-IDF**; improves search relevance.
- *Example:* "the" is in all 1000 articles (IDF near 0); "earthquake" is in only 5 (IDF high).

> **TF-IDF = TF × IDF**: a word is important if it is **frequent in this document** (high TF) but **rare across all documents** (high IDF).

---

## BLOCK C: Word Embeddings in Detail
*(Q8, Q4, Q5, Q11)*

### Q8. CBOW vs Skip-Gram (Word2Vec)

| | **CBOW (Continuous Bag of Words)** | **Skip-Gram** |
|---|---|---|
| Direction | Predicts the **target word from surrounding context** | Predicts the **surrounding context from one word** |
| Input → Output | Context words → middle word | One word → nearby words |
| Example | "The ___ sat on the mat" → "cat" | "cat" → The, sat, on, the, mat |
| Speed | **Faster** to train | Slower |
| Rare words | Weaker | **Better for rare words** |
| Data size | Works on smaller data | Shines on large data |

- *Example:* medical text with many rare terms → Skip-Gram. Small common dataset needing quick training → CBOW.

### Q4. GloVe and co-occurrence
- **GloVe = Global Vectors for Word Representation.** Creates embeddings by studying how words appear **together across the entire text**.
- **Co-occurrence** = how often two words appear together in the same context. GloVe builds a big **co-occurrence matrix** (table) counting every word pair and uses these **global counts** (not just small nearby windows).
- **How:** count co-occurrences across all documents → learn vectors so word relationships are captured → similar co-occurrence patterns give similar vectors.

**Advantages:** uses **global information**; captures **meaning and analogies** (king − man + woman = queen); **efficient training** on large text; good similarity results.
- *Example:* "Paris" appears with "France", "Tokyo" with "Japan" → "Paris − France + Japan" lands near "Tokyo".

### Q5. FastText and character subwords
- Developed by **Facebook (Meta)**; an improved Word2Vec. It does **not treat a word as a single unit**; it breaks each word into **character subwords (character n-grams)** and adds up their vectors.
- *Example:* "playing" → "pla", "lay", "ayi", "yin", "ing".

**Role of subwords:**
- **Handles rare words** (their subwords appeared elsewhere).
- **Handles unknown/unseen words.**
- **Handles misspellings** (typo shares subwords with the correct word).
- **Captures word structure** (play, playing, played share subwords).

- **Advantages:** better than Word2Vec for rare and unknown words; good for languages with many word forms; strong with limited data.
- *Example:* never saw "kindness" in training → still represented using "kind" and "ness".

### Q11. BERT: context-dependent representations
- **BERT = Bidirectional Encoder Representations from Transformers** (Google). Understands a word from the **full context: words before AND after** (bidirectional).
- **Context-dependent** = the vector of a word **changes with the sentence**. Older methods (Word2Vec) gave **one fixed vector per word**.

**How BERT does it:**
1. **Bidirectional reading:** looks left and right at the same time.
2. **Self-attention:** weighs how much each other word matters to the current word.
3. **Masked Language Model training:** hides some words and learns to predict them from context.
4. **Result:** each word's vector reflects the specific sentence it is in.

- Handles **polysemy**; captures meaning better than fixed embeddings; boosts classification, question answering; easily **fine-tuned**.
- *Example:* "bank" in "river bank" and "deposited money in the bank" gets **different vectors**.

---

## Unit 2: Last-Minute Cheat Sheet
- **Pre-processing:** lowercase → remove punctuation → tokenize → stop-words → stem/lemmatize.
- **Word tokenization** = words. **Sentence tokenization** = sentences.
- **Stop-word removal:** faster, less noise, but can lose meaning ("not").
- **Stemming** chops endings (may give non-words; Porter, Lancaster, Snowball). **Lemmatization** gives real dictionary words (uses grammar).
- **BoW:** counts, ignores order and meaning, sparse. **TF** = frequency in a document. **IDF** = rarity across documents. **TF-IDF = TF × IDF.**
- **CBOW** = context → word (fast, small data). **Skip-Gram** = word → context (rare words, large data).
- **GloVe** = global co-occurrence matrix. **FastText** = subwords (rare, unseen, misspelled words).
- **BERT** = bidirectional, self-attention, MLM, **context-dependent vectors**.

---

<a id="unit-3"></a>
# UNIT 3: Text Classification and Machine Learning Models

## BLOCK A: Text Classification Basics
*(Q8, Q9)*

### Q8. Text Classification and its applications
- Automatically **assigning a piece of text to one or more categories** based on its content (teaching a computer to decide which labelled "box" the text belongs to).
- **How:** clean and pre-process text → convert words to numbers (features) → train a model on labelled examples → classify new text.

**Applications:** spam detection, sentiment analysis, topic labelling (sports/politics/business), language detection, intent detection (chatbots), content moderation (offensive/harmful text).
**Common methods:** Naive Bayes, SVM, Logistic Regression, and deep-learning models (RNN, BERT).
- *Example:* a news website automatically sorts articles into sports, politics, technology.

### Q9. Data preparation in text classification
- **Data preparation** = collecting, cleaning and converting text into a form a model can use. A model is only as good as its data.

**Steps:**
1. **Data collection:** text examples with correct labels.
2. **Text cleaning:** remove punctuation and symbols, lowercase.
3. **Tokenization.**
4. **Stop-word removal.**
5. **Stemming / Lemmatization.**
6. **Feature extraction:** BoW, TF-IDF or embeddings.
7. **Splitting data:** training set and testing set.

- *Why each step:* cleaning removes noise; tokenization and normalization make words consistent; feature extraction makes text machine-readable; splitting lets us test fairly on unseen data.

## BLOCK B: Classification Algorithms
*(Q2, Q12, Q3, Q4)*

### Q2. Naive Bayes
- A **probability-based** method using **Bayes' Theorem** to predict the class of a text. **"Naive"** because it assumes **all words are independent of each other** (not fully true, but works well).

**Steps:** training on labelled examples → calculate how likely each word is in each class → note how common each class is overall (prior) → for new text, **multiply the word probabilities** for each class → **pick the class with the highest total probability**.

- *Naive assumption example:* treats "free" and "money" separately even though together they signal spam.
- **Advantages:** simple, fast, needs little training data; very good for spam detection and sentiment analysis; handles many features.

### Q12. Logistic Regression (binary)
- A classification method (despite "regression" in the name) that predicts a **probability between 0 and 1**. Its key part is the **sigmoid function**, which squashes any value into 0 to 1.

**Steps:** convert text to features (e.g., TF-IDF) → compute a **weighted score** (each feature times a learned weight, summed) → apply **sigmoid** to get a probability → apply a **threshold** (above 0.5 = class 1, e.g., spam; otherwise class 0).

- **Advantages:** simple, fast, easy to understand; gives probabilities (confidence); works well with many text features.
- *Example:* a review gets probability 0.85 → above 0.5 → positive.

### Q3. Softmax Regression (multiclass)
- Also called **Multinomial Logistic Regression**: extends logistic regression to **many classes**. Its special part is the **Softmax function**.
- **How:** model calculates a **score for each class** → **Softmax converts scores into probabilities that add up to 1** → the class with the highest probability is selected.
- *Example:* sports 0.75, politics 0.15, technology 0.10 → article classified as **sports**.
- **Advantages:** handles three or more classes naturally; gives a probability (confidence) for each class; simple and effective; widely used in the **output layer** of neural networks.

### Q4. Support Vector Machine (SVM)
- Draws the **best possible boundary (hyperplane)** that separates data into classes.

**Working principle:**
1. **Find a separating boundary** (line, or plane in higher dimensions).
2. **Maximize the margin:** choose the boundary with the **largest gap** between classes (bigger gap = safer).
3. **Support vectors:** the data points **closest to the boundary**; they define it.
4. **Classify** new data by which side of the boundary it falls.

- **Kernel trick:** when data can't be separated by a straight line, a kernel maps it to a **higher dimension** where it can be separated (handles non-linear patterns).
- **Advantages:** works well with **high-dimensional** data (text with many words); effective with limited data; good accuracy for text.
- *Example:* emails plotted by word features; widest-margin boundary between spam and non-spam.

| Algorithm | Best remembered as |
|---|---|
| Naive Bayes | Probability + independent words, picks highest probability |
| Logistic Regression | Sigmoid, probability 0-1, binary |
| Softmax Regression | Softmax, probabilities sum to 1, multiclass |
| SVM | Widest-margin boundary, support vectors, kernel trick |

---

## BLOCK C: Evaluating Models and Overfitting
*(Q5, Q6)*

### Q5. Confusion matrix and its performance measures (accuracy, precision, recall, F1)
A **confusion matrix** is a table comparing predictions with the actual answers.

| Term | Meaning |
|---|---|
| **True Positive (TP)** | Predicted positive, really positive (correct) |
| **True Negative (TN)** | Predicted negative, really negative (correct) |
| **False Positive (FP)** | Predicted positive, actually negative (**wrong alarm**) |
| **False Negative (FN)** | Predicted negative, actually positive (**missed it**) |

**Measures (in words):**
- **Accuracy:** correct predictions out of all cases (overall correctness). Can mislead on unbalanced data.
- **Precision:** of those predicted positive, how many were right (TP out of TP + FP). High precision = few false alarms. Matters when wrong positive predictions are costly.
- **Recall:** of all real positives, how many were found (TP out of TP + FN). High recall = few missed cases. Matters when missing a positive is costly.
- **F1-Score:** the balance (harmonic mean) of precision and recall; high only when **both** are high.

- **Why useful:** shows what **kind** of errors; reveals trade-offs (high recall but low precision); suits unbalanced datasets.
- *Example:* spam test on 100 emails: TP = 40, TN = 50, FP = 5, FN = 5 → precision = 40 out of 45; recall = 40 out of 45.
- *Example:* a disease-detection text system needs **high recall** so sick patients aren't missed.

### Q6. Overfitting in text classification and generalization
- **Overfitting:** the model learns training data too well (including noise) → excellent on training data, **poor on new data** (like a student who memorises answers).
- **Generalization:** ability to perform well on **new, unseen data** (the real goal).
- **Signs:** very high training accuracy, much lower test accuracy, model too complex for the data.

**Methods to improve generalization:**
1. **More training data.**
2. **Regularization** (L1/L2 penalty against complexity).
3. **Dropout** (randomly ignore neurons during training).
4. **Cross-validation** (test on different parts of the data).
5. **Early stopping** (stop when validation performance stops improving).
6. **Simpler model.**
7. **Data augmentation.**

- *Example:* 99% training / 60% new reviews → after more data, dropout and early stopping → 88% on new data.

---

## BLOCK D: Sentiment Approaches, Topic Modeling and Deep Models
*(Q11, Q10, Q7, Q1)*

### Q11. Lexicon-based vs Machine Learning-based sentiment analysis

| | **Lexicon-based** | **Machine Learning-based** |
|---|---|---|
| Basis | Ready-made **dictionary** of words with pre-assigned sentiment scores | **Trained on labelled examples** (Naive Bayes, SVM, BERT) |
| How | Adds up scores of words in a sentence | Learns patterns from data |
| Training data | **None needed** | **Needed** |
| Context / sarcasm | **Rigid**, handles poorly | **Handles better** |
| Effort | Quick to set up | Needs training, but more accurate |
| Flexibility | May miss new words/domains | **Adapts to new domains** |

- *Example:* "The food was not good": lexicon may score "good" as positive and miss "not"; an ML model learns "not good" is negative.

### Q10. Topic Modeling and LDA
- **Topic modeling** = automatically discovering the **hidden topics** in a large collection of documents, **without being told the topics in advance**. It groups words that often appear together.
- **LDA = Latent Dirichlet Allocation** ("latent" = hidden), the most popular method. It assumes:
  - Each **document is a mixture of several topics.**
  - Each **topic is a mixture of words** that appear together often.

**How LDA identifies topics:** decide the number of topics (e.g., 3) → study which words appear together across documents → group co-occurring words into topics → describe each document as a mix of topics → **refine repeatedly** until stable.

- *Example topics:* {match, player, goal, team} → Sports; {election, vote, party, government} → Politics.
- **Importance:** organises huge text automatically, reveals hidden themes, helps search, recommendation, summarization.

### Q7. RNN for text processing
- **RNN = Recurrent Neural Network:** processes a sequence **word by word while remembering what came before**. Good for text because **word order matters**.

**Steps:** feed words **in order** (as vectors) → keep a **hidden state (memory)** of previous words → **update** it at each new word (combine current word + previous memory) → pass it forward so context flows → produce an output (e.g., sentiment or next word).

- **Limitation:** basic RNNs struggle to remember far-back information (**vanishing gradient problem**); **LSTM and GRU** solve this.
- *Example:* predicting the next word after "I am reading a ..." → "book".

### Q1. Self-attention in Transformer-based classification
- **Self-attention** lets each word **look at all other words** in the sentence and decide which matter most. It is the key idea in Transformers like BERT.

**Role in classification:**
- **Captures context** (each word in relation to the whole sentence).
- **Finds the important words** that decide the class (e.g., sentiment words).
- **Handles long-distance links.**
- **Improves accuracy.**

**Why it beats older methods:** RNNs read word by word and forget distant words; self-attention sees the **whole sentence at once** (and allows faster, **parallel** processing).
- *Example:* "The movie was boring even though the acting was great" → attention weighs "boring" strongly → classified **negative**.

---

## Unit 3: Last-Minute Cheat Sheet
- **Text classification** = assign text to categories (spam, sentiment, topic, language, intent, moderation).
- **Data preparation:** collect labelled data → clean → tokenize → stop-words → stem/lemmatize → feature extraction → train/test split.
- **Naive Bayes:** probability, assumes words independent, picks highest probability. **Logistic Regression:** sigmoid, threshold 0.5. **Softmax Regression:** probabilities sum to 1. **SVM:** max-margin hyperplane, support vectors, kernel trick.
- **Confusion matrix:** TP, TN, FP (false alarm), FN (miss). **Precision** (FP matters), **Recall** (FN matters), **F1** (balance).
- **Overfitting fixes:** more data, regularization, dropout, cross-validation, early stopping, simpler model, augmentation.
- **Lexicon-based** = dictionary, no training, rigid. **ML-based** = learns from labelled data, handles context.
- **LDA** = discovers hidden topics; documents = mix of topics; topics = mix of words.
- **RNN** = hidden-state memory (vanishing gradient → LSTM/GRU). **Self-attention** = all words see all words at once.

---

<a id="unit-4"></a>
# UNIT 4: Transformers, Attention and Seq2Seq

## BLOCK A: Why Move Beyond Classical NLP
*(Q7, Q4, Q2)*

### Q7. Limitations of classical NLP methods
**Classical methods** = Bag-of-Words, TF-IDF, rule-based systems, simple statistical models (counting words and hand-made rules).

**Limitations:**
1. **Ignore word order** ("dog bites man" = "man bites dog").
2. **Ignore meaning and context** (happy vs joyful; "bank" two meanings).
3. **Large, sparse vectors** (waste memory, slow).
4. **Manual feature design** by experts.
5. **Poor with unseen words.**
6. **Weak on complex language** (sarcasm, ambiguity, long dependencies).

**Impact:** lower accuracy (translation, sentiment), meaning errors, scalability problems, held back advanced tasks until deep learning arrived.
- *Example:* a BoW sentiment system reads "not good" but ignores order and treats "good" as positive.

### Q4. Role of Deep Learning in advanced NLP
- **Deep learning** = neural networks with many layers that **learn automatically from data** instead of hand-made rules.

**Role:** learns word meanings through **embeddings**; captures context with **RNN, LSTM, Transformers**; powers translation, summarization, question answering; large models like **BERT and GPT** are built on it.

**Improvements over traditional NLP:**
- **Automatic feature learning** (no manual design).
- **Better context understanding.**
- **Handles large data** (improves as data grows; traditional methods plateau).
- **Higher accuracy.**
- **Meaning-rich representations** (embeddings capture similarity).
- *Example:* rule-based translation was awkward; Transformer-based translation (modern Google Translate) is fluent.

### Q2. RNN/LSTM vs Transformers

| | **RNN / LSTM** | **Transformers** |
|---|---|---|
| Processing order | **Sequential** (one word at a time, each step depends on the previous) | **Parallel** (whole sequence at once) |
| Memory | **Hidden state** | **Attention** (every word looks at every word) |
| Speed | Slow to train | **Much faster** (parallel) |
| Long dependencies | Can **forget** distant words (LSTM improves) | **Handles them better** (direct links) |
| Position info | Natural from order | Added via **positional encoding** |
| Scalability | Limited | **Scales to very large data and models** |

- *Example:* translating a long paragraph: an LSTM may forget the beginning; a Transformer links first and last words directly.

---

## BLOCK B: Attention
*(Q6, Q3, Q12, Q5)*

### Q6. Importance of Attention
- **Attention** = the model's ability to **focus on the most important words**, weighing which words matter most for each word. It is the central idea that makes Transformers powerful.

**How (briefly):** compare each word with all others → give higher weights (attention scores) to relevant ones → combine information using these weights → context-aware understanding.

**Importance:** captures context; **handles long-distance links** (RNNs struggle); **enables parallel processing** (fast); improves accuracy; focuses on key words. It solved the **memory problem** of older sequence models and made **BERT and GPT** possible.
- *Example:* "The trophy did not fit in the suitcase because **it** was too big" → "it" attends strongly to "trophy".

### Q3. Self-attention vs Cross-attention

| | **Self-Attention** | **Cross-Attention** |
|---|---|---|
| Attends to | Other words **within the same sequence** | Words of **another sequence** |
| Purpose | Builds **internal context** of one sentence | **Transfers information across** two sequences (links input to output) |
| Where used | **Encoder and decoder** | **Decoder** (connecting to the encoder's output) |
| Example | Each input word looks at all other input words | Each Hindi word being generated looks at relevant English words |

### Q12. Multi-Head Attention
- One attention calculation = one **head**. **Multi-head attention** runs **several heads in parallel**, each with different learned settings, then **combines (joins)** the results.

**How multiple heads capture different relationships:**
- **Different focus per head:** one on grammar links (subject-verb), another on meaning, another on long-distance references.
- **Parallel viewpoints:** many relationship types captured at once.
- **Combined richness:** a fuller picture than a single head.

- **Advantages:** captures several kinds of relationships simultaneously, better understanding of complex sentences, more power and accuracy. It is a core reason Transformers are so effective.
- *Example:* "The girl who won the race was happy": one head links "girl" with "won" (who did the action), another links "girl" with "happy" (description).

### Q5. Positional Encoding
- **Problem:** Transformers read all words **in parallel**, so they don't know word order ("dog bites man" ≠ "man bites dog").
- **Positional encoding** adds **position information** to each word's embedding. Each position gets a **unique numerical pattern** (often from **sine and cosine** functions) that is **added to the word vector**, so the vector carries **meaning + position**.
- **Purpose:** gives a sense of word order, lets attention consider which words come before or after, preserves sequence structure lost by parallel processing.
- Without it, a Transformer treats a sentence as an **unordered bag of words**.
- *Example:* "The cat chased the dog" vs "The dog chased the cat".

---

## BLOCK C: Transformer Architecture
*(Q1, Q11)*

### Q11. Major components of the Transformer
The Transformer processes all words **in parallel using attention** instead of reading one by one.

| Component | Function |
|---|---|
| **Input Embedding** | Converts each word into a numerical vector capturing its meaning |
| **Positional Encoding** | Adds position information (order would otherwise be lost) |
| **Multi-Head Self-Attention** | Each word attends to all others in multiple ways at once (different relationships and context) |
| **Feed-Forward Network** | Small neural network applied to each word to further transform its representation |
| **Add and Normalize** (residual + layer norm) | Helps training: keeps information flowing and stabilises values |
| **Encoder** | Stack of blocks that **understands the input** |
| **Decoder** | Stack that **generates the output** (self-attention + cross-attention to the encoder) |
| **Output Layer (Linear + Softmax)** | Converts final vectors into **probabilities** to choose the next output word |

- **Evaluation:** *Strengths:* parallel processing = fast; attention captures long-distance context; multi-head captures many relationships. *Result:* high accuracy in translation, summarization. They replaced slower RNNs and are the base of **BERT and GPT**.

### Q1. Encoder and Decoder blocks

| | **Encoder** | **Decoder** |
|---|---|---|
| Function | **Understands the input** sentence into meaning-rich representations | **Generates the output** one word at a time using the encoder's understanding |
| Steps | Input embeddings + positional encoding → **self-attention** → **feed-forward network** → meaning-rich output | **Self-attention** on words generated so far → **cross-attention** to encoder output → feed-forward network → next output word |

- **Together** they enable **sequence-to-sequence** tasks like translation.
- **Shared components:** multi-head self-attention, feed-forward networks, positional encoding, normalization.
- *Example:* English to French: encoder reads "I am happy"; decoder generates "Je suis heureux" word by word, attending to the encoder at each step.

---

## BLOCK D: Seq2Seq Models
*(Q10, Q8, Q9)*

### Q10. Seq2Seq and the Encoder-Decoder architecture
- **Seq2Seq = Sequence-to-Sequence:** converts an **input sequence** into an **output sequence** (e.g., English sentence → French sentence). Built from an **encoder** and a **decoder**.
- **Encoder:** reads the whole input, word by word, and compresses its meaning into a representation (**context vector** or set of vectors).
- **Decoder:** takes that representation and generates the output **one word at a time**.

**Steps:** input words converted to vectors and fed to the encoder → encoder (RNN/LSTM or Transformer) builds a meaning representation → passed to the decoder → decoder generates the first output word, then uses it to generate the next → continues until an **end signal**.

- **Attention** is added in modern models so the decoder can focus on the most relevant input words.
- **Importance:** handles variable-length input and output; powers translation, summarization, chatbots; foundation of Transformers.
- *Example:* "I am learning" → Hindi sentence generated word by word.

### Q8. Attention in Seq2Seq
**Problem without attention:** basic Seq2Seq **squeezes the whole input into one fixed vector**; for long sentences this vector cannot hold all the information → the decoder forgets early words → poor output (**fixed-vector bottleneck**).

**Attention solution:** the decoder can **look back at all the encoder's word representations**, not just one fixed vector.
- At each output step, the decoder decides **which input words are most relevant**, gives them **higher weights**, and focuses on them to generate the next word.

**Benefits:** full access to the input; focuses on the right input word at the right time; greatly improves accuracy on **long sentences**; removes the bottleneck; **laid the foundation for Transformers**.
- *Example:* translating "The weather is nice today" to French: decoder focuses on "weather" while producing "temps", and on "nice" while producing "agréable".

### Q9. Applications of Seq2Seq
Used whenever **both input and output are sequences** of words:

| Application | Example |
|---|---|
| **Machine translation** | "Good morning" → Hindi |
| **Text summarization** | Long article → two-line summary |
| **Chatbots / dialogue systems** | "How are you?" → "I am fine, thank you!" |
| **Question answering** | "What is the capital of France?" → "Paris" |
| **Speech recognition** | Sequence of audio signals → sequence of text words |
| **Text generation** | Captions or continuing text from a prompt |

- **Why suitable:** variable-length input and output; encoder understands, decoder generates; with attention they handle long inputs well.

---

## Unit 4: Last-Minute Cheat Sheet
- **Classical NLP limits:** ignores order and meaning, sparse vectors, manual features, poor with unseen words, weak on sarcasm/ambiguity.
- **Deep learning** gives automatic features, context understanding, higher accuracy, meaningful embeddings (BERT, GPT).
- **RNN/LSTM** = sequential, hidden state, slow, may forget. **Transformer** = parallel, attention, fast, long dependencies, needs **positional encoding**.
- **Attention** = focus on important words. **Self-attention** = within one sequence. **Cross-attention** = between two sequences (decoder ← encoder).
- **Multi-head attention** = several attention heads capturing different relationships (grammar, meaning, reference), then combined.
- **Positional encoding** = sine/cosine position patterns added to embeddings.
- **Transformer components:** input embedding, positional encoding, multi-head self-attention, feed-forward, add and normalize, encoder, decoder, output (linear + softmax).
- **Encoder** = understands input. **Decoder** = generates output (self-attention + cross-attention).
- **Seq2Seq** = encoder + decoder; **attention fixes the fixed-vector bottleneck**. Applications: translation, summarization, chatbots, QA, speech recognition, text generation.

---

<a id="quick-answers"></a>
# FILL IN THE BLANKS (Quick Answers)

| # | Question | Answer |
|---|---|---|
| 1 | PV-DM stands for ___ | **Distributed Memory** |
| 2 | spaCy tool that shows grammatical relationships between words: Dependency ___ | **Parsing** |
| 3 | Reducing words to their root form | **Stemming** |
| 4 | Numerical vector representing the meaning of an entire sentence | **Sentence Embedding** |
| 5 | One word with multiple meanings depending on context | **Polysemy** |
| 6 | PV-DBOW is similar to which Word2Vec approach | **Skip-Gram** |
| 7 | Identifying unwanted or harmful messages such as spam emails | **Spam detection** |
| 8 | Converting words into meaningful base forms | **Lemmatization** |
| 9 | SBERT stands for | **Sentence-BERT** |
| 10 | ___ Tagging assigns a grammatical category to every word | **Part-of-Speech (POS)** |
| 11 | The two types of Doc2Vec are PV-DM and ___ | **PV-DBOW** |
| 12 | POS tag for an adjective | **JJ** |
| 13 | Extension of Word2Vec for documents, paragraphs, sentences | **Doc2Vec** |
| 14 | Information Retrieval commonly uses ___ and searching | **Indexing** |
| 15 | Information Retrieval mainly focuses on finding the ___ information | **Correct** |
| 16 | A word/sentence with more than one meaning creates ___ | **Ambiguity** |
| 17 | Text data not organised in rows and columns | **Unstructured** |
| 18 | POS tag for a noun | **NN** |
| 19 | Identifying grammatical structure using a parse tree: ___ parsing | **Syntactic** |
| 20 | Removal of common words such as "the", "is", "and" | **Stop-word removal** |

---

# MULTIPLE CHOICE QUESTIONS (Quick Answers)

| # | Question (short) | Answer |
|---|---|---|
| 1 | Task BERT uses to predict hidden words | **Masked Language Model** |
| 2 | Teacher-student pair in knowledge distillation | **BERT → DistilBERT** |
| 3 | GPT stands for | **Generative Pre-trained Transformer** |
| 4 | BERT understands a word mainly by considering | **Context on both sides** |
| 5 | LSTM gate that removes old information | **Forget gate** |
| 6 | Problem of simple RNNs that LSTM addresses | **Vanishing gradient problem** |
| 7 | Percentage of words masked in BERT's MLM training | **15%** |
| 8 | Task identifying names of people, places, organizations | **Named Entity Recognition** |
| 9 | GPT generates text using | **Autoregressive process** |
| 10 | How BERT determines the meaning of "bank" in "went to the bank to deposit money" | **By using surrounding context** |
| 11 | Fine-tuning in BERT is | **Adapting the pre-trained BERT model for a specific task** |
| 12 | Model that retains earlier information in "The food was good but the service was slow" | **LSTM** |
| 13 | GPT model known for few-shot learning at large scale | **GPT-3** |
| 14 | Application of fine-tuned BERT | **Sentiment Analysis** |
| 15 | What the LSTM example remembers in "The movie, despite a slow start, was excellent" | **The important sentiment signal "excellent"** |
| 16 | DistilBERT was developed using | **Knowledge Distillation** |
| 17 | Main purpose of LSTM in sequential data | **To learn long-term dependencies** |
| 18 | Next Sentence Prediction in BERT determines | **Whether two sentences are logically related** |

---

*End of notes. Best of luck for the exam!*

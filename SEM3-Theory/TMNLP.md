**TMNLP Question Bank**

**UNIT 1**

**Q1. Illustrate syntax analysis and the role of a parser and parse tree.**

**What is Syntax Analysis?**

Let us break the words down. 'Syntax' means the grammar rules of a language - the correct way words are arranged. 'Analysis' means examining something carefully. So Syntax Analysis means checking whether a sentence (or a line of code) follows the correct grammar rules, and understanding how its parts fit together.

In NLP and in compilers, syntax analysis is the stage that studies the grammatical structure of the input. It comes after the words have been broken into tokens.

**What is a Parser?**

A 'Parser' is the tool (a program) that performs syntax analysis. Its job is to read the tokens one by one and check them against the grammar rules.

- It confirms whether the arrangement of words is grammatically valid.
- If the grammar is broken, it reports a syntax error.
- If the grammar is correct, it builds a structure showing how the parts relate.

**What is a Parse Tree?**

A 'Parse Tree' is a tree-shaped diagram that the parser builds to show the grammatical structure of a sentence.

- The top (root) represents the whole sentence.
- The branches break it into smaller parts like noun phrase and verb phrase.
- The leaves at the bottom are the actual words.

It is like a family tree, but instead of showing family members it shows how grammar parts are related.

**Why is This Important?**

- It checks that input is grammatically correct.
- It reveals the structure needed for deeper meaning analysis.
- It is essential in both language understanding and programming compilers.

**Real-life example:** For the sentence 'The cat sat on the mat', the parser reads each word and builds a parse tree with the sentence at the top, splitting into a noun phrase ('The cat') and a verb phrase ('sat on the mat'). This tree shows the grammatical structure clearly, allowing the system to understand who did what.

**Q2. Explain Word Embeddings in NLP and discuss the working of Word2Vec, GloVe, and FastText with suitable examples.**

**What are Word Embeddings?**

'Word' means a single word, and 'Embedding' means placing something inside a space. So Word Embeddings means representing each word as a list of numbers (a vector) placed in a mathematical space, where words with similar meanings sit close together.

Computers cannot understand words directly - they understand numbers. Word embeddings convert words into meaningful numbers that capture their meaning and relationships.

**Word2Vec**

Word2Vec learns embeddings by looking at the words that appear around a target word (its context).

- It has two approaches: CBOW (predicts a word from its surrounding words) and Skip-Gram (predicts surrounding words from one word).
- Words used in similar contexts get similar vectors.
- Example: 'king' and 'queen' end up close together because they appear in similar sentences.

**GloVe**

GloVe stands for Global Vectors. It learns embeddings by studying how often words appear together across the whole collection of text (co-occurrence).

- It counts global word pairings, not just nearby windows.
- This captures overall relationships in the language.
- Example: 'ice' appears often with 'cold', so their vectors reflect that link.

**FastText**

FastText improves on Word2Vec by breaking words into smaller pieces called subwords (character n-grams).

- It represents a word as the sum of its subword pieces.
- This lets it handle rare or misspelled words and word forms.
- Example: it understands 'playing' from the pieces 'play' + 'ing' even if 'playing' was rarely seen.

**Why are Word Embeddings Important?**

- They let machines understand word meaning and similarity.
- They power tasks like translation, search, and chatbots.
- They capture relationships such as 'king - man + woman = queen'.

**Real-life example:** In a search engine, if you type 'automobile', word embeddings help the system also show results for 'car', because their vectors are close together. Word2Vec learns this from context, GloVe from global co-occurrence, and FastText even handles a typo like 'autombile' using subwords - all making search smarter.

**Q3. Describe Text Mining. Explain how it converts unstructured textual data into useful information.**

**What is Text Mining?**

Let us break it down. 'Text' means written words, and 'Mining' means digging out something valuable (like mining gold from the earth). So Text Mining means digging useful information and hidden patterns out of large amounts of written text.

Most text (emails, reviews, articles, social media) is unstructured - it is not neatly arranged in rows and columns. Text mining turns this messy text into organised, useful knowledge.

**How Does Text Mining Convert Unstructured Text? (Step by Step)**

- **Text collection:** First, raw text is gathered from sources like documents, websites, and reviews.
- **Pre-processing:** The text is cleaned - removing punctuation, converting to lowercase, and removing stop-words (common words like 'the' and 'is').
- **Tokenization:** The cleaned text is broken into smaller units called tokens (usually words).
- **Feature extraction:** Important features are pulled out and turned into numbers the computer can use (for example, word frequencies).
- **Applying techniques:** Methods like classification, clustering, and pattern discovery are applied to find meaning.
- **Producing information:** The results are presented as useful information - such as trends, topics, or summaries.

**What Can Text Mining Discover?**

- Common topics and themes in a large set of documents.
- Sentiments (positive or negative opinions) in reviews.
- Important names, places, and keywords.

**Why is Text Mining Important?**

- Huge amounts of valuable information are locked inside text.
- It saves people from reading everything manually.
- It supports better decisions based on hidden patterns.

**Real-life example:** A company has thousands of customer reviews (unstructured text). Text mining cleans and tokenizes them, then applies analysis to find that many customers complain about 'slow delivery'. This turns unreadable piles of text into clear, useful information the company can act on - showing how text mining converts unstructured data into knowledge.

**Q4. Describe Sentiment Analysis and discuss its major applications in NLP.**

**What is Sentiment Analysis?**

'Sentiment' means a feeling or opinion, and 'Analysis' means examining it carefully. So Sentiment Analysis means using NLP to automatically find out the feeling or opinion expressed in a piece of text - usually whether it is positive, negative, or neutral.

In simple words, it teaches a computer to understand emotions in writing, like whether a movie review is happy or angry.

**How Does It Work (Briefly)?**

- The text is cleaned and broken into words.
- The system studies the words and their meaning.
- It decides the overall sentiment - positive, negative, or neutral.
- Some systems also detect specific emotions like joy, anger, or sadness.

**Major Applications of Sentiment Analysis**

- **Product and service reviews:** Companies analyse customer reviews to know if people like or dislike their products.
- **Social media monitoring:** Brands track posts and tweets to understand public opinion about them.
- **Customer feedback:** Businesses study feedback to improve services and fix complaints.
- **Political analysis:** Opinions about parties and candidates are measured from public posts.
- **Market research:** Companies understand what customers want before launching products.
- **Brand reputation management:** Firms quickly spot negative opinions and respond early.

**Why is Sentiment Analysis Important?**

- It reveals what people really feel, at a large scale.
- It helps companies improve products and reputation.
- It supports faster, data-based decisions.

**Real-life example:** An online shopping website uses sentiment analysis on thousands of product reviews. It automatically finds that a phone has mostly positive sentiment for its camera but negative sentiment for its battery. The company then improves the battery in the next model. This shows how sentiment analysis turns opinions into useful business action.

**Q5. Assess the role of NLP in Machine Translation and its major steps.**

**What is Machine Translation?**

'Machine' means a computer, and 'Translation' means changing text from one language to another. So Machine Translation means using a computer to automatically translate text or speech from one language (the source) into another language (the target), for example English to Hindi.

NLP plays a central role here because translating language correctly needs deep understanding of grammar and meaning, which is exactly what NLP provides.

**The Role of NLP in Machine Translation**

- NLP helps the computer understand the meaning of the source sentence, not just replace words.
- It handles grammar differences between languages.
- It manages ambiguity (words with more than one meaning).
- It produces natural, correct sentences in the target language.

**Major Steps of Machine Translation**

- **Text input:** The source-language sentence is given to the system.
- **Tokenization:** The sentence is broken into tokens (words).
- **Analysis (parsing):** The grammar and structure of the sentence are understood.
- **Meaning representation:** The system captures the meaning of the sentence.
- **Transfer / mapping:** The meaning and structure are mapped to the target language.
- **Generation:** A grammatically correct sentence is produced in the target language.
- **Output:** The translated sentence is shown to the user.

**Why is NLP Important in Machine Translation?**

- It makes translation meaning-based, not just word-by-word.
- It reduces grammar mistakes and awkward sentences.
- It enables communication across languages worldwide.

**Real-life example:** When you type 'How are you?' into Google Translate to get Hindi, NLP tokenizes the sentence, understands its meaning and grammar, maps it to Hindi structure, and generates 'आप कैसे हैं?'. Without NLP, the result would be a poor word-by-word translation. This shows NLP's essential role in accurate machine translation.

**Q6. Define NLP. Explain its purpose, major applications, and importance.**

**What is NLP?**

NLP stands for Natural Language Processing. Let us break it down. 'Natural Language' means the everyday human languages we speak, like English or Hindi. 'Processing' means handling or working with something. So NLP means the branch of computer science and AI that lets computers understand, interpret, and generate human language.

In simple words, NLP is what helps computers read, listen to, and reply in human language.

**Purpose of NLP**

- To bridge the gap between human language and computer understanding.
- To let people interact with machines using normal language instead of code.
- To extract meaning and useful information from text and speech.

**Major Applications of NLP**

- **Machine translation:** Translating between languages (like Google Translate).
- **Chatbots and virtual assistants:** Tools like Siri and Alexa that understand and answer.
- **Sentiment analysis:** Finding opinions in reviews and posts.
- **Text summarization:** Shortening long documents automatically.
- **Spam detection:** Filtering out unwanted emails.
- **Speech recognition:** Converting spoken words into text.

**Why is NLP Important?**

- It makes human-computer interaction natural and easy.
- It handles the huge amount of text data created every day.
- It powers many everyday tools we rely on.
- It saves time by automating language tasks.

**Real-life example:** When you ask your phone's voice assistant, 'What is the weather today?', NLP converts your speech to text, understands the meaning of your question, finds the answer, and replies in natural language. This everyday convenience shows the purpose and importance of NLP.

**Q7. Explain the concepts of token and lexeme with suitable examples.**

**Introduction**

When a computer reads text or code, it first breaks it into small meaningful pieces. Two closely related ideas here are 'token' and 'lexeme'. They sound similar but mean slightly different things. Let us understand each.

**What is a Lexeme?**

A 'Lexeme' is the actual sequence of characters in the input that forms a meaningful unit - the real text as it appears.

- It is the raw piece of text taken directly from the input.
- Example: in the code `count = 10`, the lexemes are `count`, `=`, and `10`.

**What is a Token?**

A 'Token' is the category or type that a lexeme belongs to, often stored as a name with a value.

- It groups lexemes into classes like identifier, operator, or number.
- Example: the lexeme `count` becomes the token IDENTIFIER, `=` becomes the token OPERATOR, and `10` becomes the token NUMBER.

**The Key Difference**

- **Lexeme:** the exact text (`count`, `10`).
- **Token:** the type/category of that text (IDENTIFIER, NUMBER).

Think of it like a shop: the lexeme is the actual item (an apple), and the token is the category it belongs to (fruit).

**Why are These Concepts Important?**

- They are the foundation of the first stage of language processing (lexical analysis).
- They let the system organise raw text into meaningful groups.
- They make later stages like parsing possible.

**Real-life example:** In the statement `price = 50`, a lexer reads it and produces lexemes `price`, `=`, and `50`. It then assigns tokens: `price` → IDENTIFIER, `=` → ASSIGNMENT OPERATOR, `50` → NUMBER. The lexeme is the real text; the token is its category. This shows clearly how tokens and lexemes differ yet work together.

**Q8. Illustrate the working of an NLP-based chatbot with a suitable example.**

**What is an NLP-based Chatbot?**

A 'Chatbot' is a computer program that talks with people through text or voice. 'NLP-based' means it uses Natural Language Processing to understand and respond in human language. So an NLP-based chatbot is a program that can understand what a user types, work out what they want, and reply naturally.

Unlike simple rule-based bots, an NLP chatbot understands meaning, not just fixed keywords.

**How an NLP-based Chatbot Works (Step by Step)**

- **Step 1 - User input:** The user types or speaks a message, for example 'I want to book a ticket'.
- **Step 2 - Pre-processing:** The message is cleaned and broken into tokens (words).
- **Step 3 - Intent recognition:** The chatbot works out the user's intent (goal) - here, 'book a ticket'.
- **Step 4 - Entity extraction:** It finds important details (entities) like the destination, date, or time.
- **Step 5 - Processing / decision:** It decides how to respond, checking databases if needed.
- **Step 6 - Response generation:** It creates a natural-language reply.
- **Step 7 - Output:** The reply is shown or spoken to the user.

**Why are NLP Chatbots Useful?**

- They give instant answers, any time of day.
- They understand many ways of asking the same thing.
- They reduce workload on human staff.

**Real-life example:** A user types to a railway chatbot: 'Book a train from Delhi to Mumbai tomorrow.' The chatbot pre-processes the text, recognises the intent (booking), extracts entities (Delhi, Mumbai, tomorrow), checks train availability, and replies, 'I found 3 trains from Delhi to Mumbai tomorrow. Which one would you like?' This shows how an NLP chatbot understands and responds naturally.

**Q9. Describe the role of NLP in Text Summarization and its major steps.**

**What is Text Summarization?**

'Text' means written content, and 'Summarization' means making something shorter while keeping its main points. So Text Summarization means using NLP to automatically create a short, clear summary of a long piece of text without losing its important meaning.

In simple words, it reads a long article for you and gives you the key points.

**The Role of NLP in Text Summarization**

- NLP helps the computer understand the meaning and importance of sentences.
- It identifies the main ideas and removes less important details.
- It ensures the summary is still meaningful and readable.
- It handles grammar so the summary sounds natural.

**Two Types of Summarization**

- **Extractive:** Picks out the most important existing sentences and joins them.
- **Abstractive:** Understands the text and writes new sentences in its own words, like a human.

**Major Steps of Text Summarization**

- **Text input:** The long document is given to the system.
- **Pre-processing:** The text is cleaned and split into sentences and tokens.
- **Importance scoring:** Each sentence is scored for how important it is (using word frequency, position, keywords).
- **Selection or generation:** Important sentences are selected (extractive) or new sentences are generated (abstractive).
- **Summary output:** The final short summary is produced.

**Why is Text Summarization Important?**

- It saves time by shortening long content.
- It helps people quickly grasp key ideas.
- It is useful for news, research, and reports.

**Real-life example:** A news app shows a 3-line summary at the top of a long article. NLP pre-processes the article, scores each sentence for importance, and picks the key sentences (extractive) or rewrites them shortly (abstractive). The reader gets the main news in seconds - showing NLP's role in text summarization.

**Q10. Define a compiler. Explain its phases in detail.**

**What is a Compiler?**

A 'Compiler' is a special program that translates code written in a high-level programming language (like C or Java, which humans can read) into machine language (0s and 1s, which the computer can run). So a compiler is like a translator between the programmer and the computer.

It also checks the program for errors while translating.

**The Phases of a Compiler**

- **1. Lexical Analysis:** The source code is broken into small units called tokens (like keywords, identifiers, and symbols). This is done by the lexer.
- **2. Syntax Analysis (Parsing):** The tokens are checked against the grammar rules of the language, and a parse tree is built. Grammar errors are caught here.
- **3. Semantic Analysis:** The meaning is checked - for example, whether a number is wrongly added to a word, or a variable is used before being declared.
- **4. Intermediate Code Generation:** The program is converted into a simpler, machine-independent code that is easy to work with.
- **5. Code Optimization:** The intermediate code is improved to run faster and use less memory, without changing what it does.
- **6. Code Generation:** The final machine code (or target code) is produced, which the computer can execute.

**Supporting Parts**

- **Symbol table:** Stores information about variables and functions used throughout.
- **Error handler:** Detects and reports errors in each phase.

**Why are These Phases Important?**

- Each phase does one clear job, making translation organised.
- Errors are caught early and clearly.
- The result is efficient, correct machine code.

**Real-life example:** When you compile a C program that prints 'Hello', the compiler first tokenizes the code, checks its grammar, verifies its meaning, creates intermediate code, optimizes it, and finally produces machine code the computer runs to display 'Hello'. Each phase plays its part - showing how a compiler works step by step.

**Q11. Explain Named Entity Recognition (NER) and describe how entities are identified from text with suitable examples.**

**What is Named Entity Recognition (NER)?**

Let us break it down. 'Named Entity' means a real-world named thing such as a person, place, organisation, or date. 'Recognition' means identifying or spotting something. So NER means an NLP task that automatically finds and labels named things (entities) in a piece of text.

In simple words, NER reads a sentence and highlights who, where, when, and which organisation is mentioned.

**Common Types of Entities**

- **Person:** names of people (e.g., 'Sachin Tendulkar').
- **Location:** places (e.g., 'Mumbai').
- **Organisation:** companies or groups (e.g., 'Google').
- **Date/Time:** dates and times (e.g., '25 May 2018').
- **Money/Quantity:** amounts and numbers.

**How Are Entities Identified? (Step by Step)**

- **Tokenization:** The text is broken into words.
- **POS tagging:** Each word's grammatical role is found (helps spot nouns).
- **Feature analysis:** The system studies clues like capital letters, position, and surrounding words.
- **Classification:** A model (rule-based or machine-learning) labels each token as a type of entity or as 'not an entity'.
- **Output:** The recognised entities are tagged and returned.

**Why is NER Important?**

- It pulls out key facts from large amounts of text.
- It powers search engines, chatbots, and news analysis.
- It supports information extraction and question answering.

**Real-life example:** Given the sentence 'Sundar Pichai became the CEO of Google in 2015 in California', NER identifies 'Sundar Pichai' as a Person, 'Google' as an Organisation, '2015' as a Date, and 'California' as a Location. This shows how NER extracts important named information from text automatically.

**Q12. Evaluate Intermediate Code Generation, its purpose and advantages with a suitable example.**

**What is Intermediate Code Generation?**

'Intermediate' means something in the middle - between two stages. 'Code Generation' means producing code. So Intermediate Code Generation is the compiler phase that converts the source program into a simpler, in-between form of code that is easy to handle - after checking its meaning, but before producing final machine code.

This intermediate code is not tied to any specific machine, which makes it flexible.

**Purpose of Intermediate Code Generation**

- To create a bridge between the high-level source code and the low-level machine code.
- To make the program easier to optimize.
- To keep the compiler independent of any particular machine.

**Advantages of Intermediate Code**

- **Machine independence:** The same intermediate code can be used to produce machine code for different computers - the front end stays the same.
- **Easier optimization:** It is simpler to improve and optimize than raw machine code.
- **Reusability:** One front end can be paired with many back ends for different machines.
- **Simpler translation:** It breaks the big job of translation into smaller, manageable steps.

**Common Forms of Intermediate Code**

- **Three-address code:** Each instruction has at most three parts (like `t1 = a + b`).
- **Syntax trees and postfix notation:** Other simple representations of the program.

**Why is This Phase Valuable?**

- It makes compilers portable across machines.
- It improves the quality of final code through optimization.
- It organises the translation process cleanly.

**Real-life example:** For the expression `x = a + b * c`, the compiler generates three-address intermediate code: `t1 = b * c`, then `t2 = a + t1`, then `x = t2`. This simple form can be optimized easily and then converted to machine code for any computer. This shows the purpose and advantage of intermediate code generation.

**Q13. Explain the concept of Part-of-Speech (POS) Tagging and discuss its importance in understanding the grammatical structure of a sentence.**

**What is POS Tagging?**

Let us break it down. 'Part-of-Speech' means the grammatical category of a word - such as noun, verb, adjective, or adverb. 'Tagging' means labelling. So POS Tagging means the NLP task of labelling every word in a sentence with its correct grammatical category.

In simple words, it marks each word to show whether it is a noun, a verb, and so on.

**Common POS Tags**

- **Noun (NN):** a person, place, or thing (e.g., 'dog').
- **Verb (VB):** an action (e.g., 'run').
- **Adjective (JJ):** describes a noun (e.g., 'happy').
- **Adverb (RB):** describes a verb (e.g., 'quickly').
- **Pronoun, preposition, conjunction:** other grammatical roles.

**How POS Tagging Works (Briefly)**

- The sentence is broken into tokens.
- The system studies each word and its context.
- Using rules or machine-learning models, it assigns the correct tag.

**Importance in Understanding Grammatical Structure**

- It reveals the grammatical role of each word.
- It helps resolve ambiguity - the same word can be different parts of speech (e.g., 'book' can be a noun or a verb).
- It is a key step before parsing and building a parse tree.
- It supports many tasks like NER, translation, and summarization.

**Why is POS Tagging Important?**

- It is a foundation for understanding sentence meaning.
- It improves the accuracy of higher-level NLP tasks.
- It helps machines read grammar the way humans do.

**Real-life example:** For the sentence 'She books a ticket', POS tagging labels 'She' as a pronoun, 'books' as a verb (not a noun here), 'a' as a determiner, and 'ticket' as a noun. Knowing that 'books' is a verb helps the system understand the sentence correctly - showing the importance of POS tagging.

**Q14. Explain the role of NLP in Spam Detection with a suitable example.**

**What is Spam Detection?**

'Spam' means unwanted or harmful messages, like junk emails and fake offers. 'Detection' means finding or catching something. So Spam Detection means automatically identifying and filtering out unwanted or harmful messages using NLP techniques.

In simple words, it is how your email keeps junk mail out of your inbox.

**The Role of NLP in Spam Detection**

- NLP reads and understands the content of messages.
- It studies the words, phrases, and patterns commonly found in spam.
- It learns the difference between normal ('ham') and spam messages.
- It classifies each new message as spam or not spam.

**How It Works (Step by Step)**

- **Data collection:** Many example emails, labelled as spam or not, are gathered.
- **Pre-processing:** Text is cleaned, lowercased, and stop-words are removed.
- **Feature extraction:** Words are turned into numbers (for example, using word frequencies or TF-IDF).
- **Model training:** A classifier (like Naive Bayes) learns spam patterns.
- **Classification:** New emails are checked and labelled spam or not spam.

**Why is NLP Important in Spam Detection?**

- Spam is written in human language, which NLP understands.
- It adapts to new tricks spammers use.
- It protects users from scams, viruses, and clutter.

**Real-life example:** An email arrives saying 'Congratulations! You WON a FREE prize, click here NOW!'. NLP pre-processes the text and notices spam-like features - words like 'WON', 'FREE', 'click here', and urgency. A trained Naive Bayes model classifies it as spam and moves it to the spam folder. This shows NLP's role in keeping inboxes clean.

**Q15. Explain the challenges associated with synonyms, polysemy, sarcasm, and human emotions in NLP.**

**Introduction**

Human language is rich and tricky, which makes it hard for computers to understand perfectly. Four major challenges in NLP are synonyms, polysemy, sarcasm, and human emotions. Let us understand each.

**1. Synonyms**

'Synonyms' are different words that mean the same thing.

- Words like 'big', 'large', and 'huge' mean almost the same, but look completely different to a computer.
- The challenge is that the machine must understand they carry similar meaning.
- If not handled, the computer may treat similar sentences as unrelated.

**2. Polysemy**

'Polysemy' means one word having multiple meanings depending on the context.

- Example: 'bank' can mean a riverbank or a money bank.
- The challenge is choosing the correct meaning based on the surrounding words.
- Wrong choice leads to wrong understanding.

**3. Sarcasm**

'Sarcasm' means saying the opposite of what is really meant, often to mock.

- Example: 'Oh great, another traffic jam!' sounds positive ('great') but is actually negative.
- The challenge is that the words say one thing while the true feeling is the opposite.
- This easily fools sentiment analysis systems.

**4. Human Emotions**

'Human emotions' are feelings like joy, anger, sadness, and fear expressed in text.

- Emotions can be subtle, mixed, or hidden.
- The challenge is detecting and correctly classifying these feelings.
- The same words can carry different emotions in different situations.

**Why are These Challenges Important?**

- They make language understanding difficult for machines.
- Ignoring them causes wrong results in translation and sentiment analysis.
- Solving them makes NLP systems far more accurate and human-like.

**Real-life example:** A sentiment analysis tool reads a tweet: 'Wow, fantastic service, I only waited two hours!'. The words 'fantastic' and 'wow' seem positive, but it is sarcasm expressing anger. If the system misses the sarcasm, it wrongly marks the tweet as positive - showing why sarcasm, polysemy, synonyms, and emotions are real challenges in NLP.

**UNIT 2**

**Q1. Discuss the Bag-of-Words (BoW) model with its advantages and limitations.**

**What is the Bag-of-Words Model?**

Let us picture the name. Imagine putting all the words of a document into a bag and shaking it up - the order is lost, but you still know which words are present and how many times. So the Bag-of-Words (BoW) model represents text by counting how often each word appears, ignoring grammar and word order.

It is a simple way to turn text into numbers that a computer can use.

**How Does BoW Work?**

- **Build a vocabulary:** List all unique words across the documents.
- **Count words:** For each document, count how many times each vocabulary word appears.
- **Create vectors:** Each document becomes a vector of these counts.

**Advantages of BoW**

- **Simple and easy:** It is very easy to understand and build.
- **Fast:** It works quickly on many tasks like classification.
- **Effective baseline:** It performs surprisingly well for spam detection and topic tasks.

**Limitations of BoW**

- **Ignores word order:** 'Dog bites man' and 'Man bites dog' look the same to it.
- **Ignores meaning:** It does not understand that 'happy' and 'joyful' are similar.
- **Large and sparse vectors:** With many words, vectors become huge and mostly zeros.
- **No context:** It cannot handle polysemy (words with multiple meanings).

**Why is BoW Important to Understand?**

- It is one of the first and simplest text representation methods.
- It is the foundation for improved methods like TF-IDF.
- Knowing its limits explains why word embeddings were developed.

**Real-life example:** For two reviews, 'good product' and 'product good value', BoW builds a vocabulary {good, product, value} and represents them as word counts. It can tell 'good' and 'product' appear, helping classify the review as positive - but it ignores order and meaning. This shows both the usefulness and the limits of Bag-of-Words.

**Q2. Explain Lemmatization and its working with examples.**

**What is Lemmatization?**

The word 'Lemma' means the base or dictionary form of a word. So Lemmatization means the NLP process of converting a word into its proper base form (its lemma) using grammar and meaning.

For example, 'running', 'ran', and 'runs' all reduce to the base word 'run'.

**How Does Lemmatization Work?**

- **Understand the word:** It looks at the word and its part of speech (noun, verb, etc.).
- **Use a dictionary:** It refers to a language dictionary and grammar rules.
- **Find the correct base form:** It returns a real, meaningful root word (the lemma).

Unlike simple chopping of endings, lemmatization always produces a valid word.

**Examples of Lemmatization**

- 'studies' → 'study'
- 'better' → 'good' (it understands meaning)
- 'was', 'is', 'are' → 'be'
- 'children' → 'child'

**Difference from Stemming**

- **Stemming:** just cuts word endings, sometimes giving non-words ('studies' → 'studi').
- **Lemmatization:** uses grammar and dictionary to give a real word ('studies' → 'study').

**Why is Lemmatization Important?**

- It reduces different word forms to one common form.
- It shrinks the vocabulary size, making processing efficient.
- It improves accuracy in search, classification, and analysis.

**Real-life example:** A search engine receives the query 'running shoes'. Using lemmatization, it converts 'running' to 'run', so it can also match pages about 'run' and 'runs'. Because lemmatization gives real base words, the search understands meaning correctly - showing its value in NLP.

**Q3. Illustrate Stemming and its major algorithms with examples.**

**What is Stemming?**

A 'Stem' is the root part of a word left after removing prefixes and suffixes. So Stemming means the NLP process of reducing a word to its root form by simply chopping off its endings.

For example, 'playing', 'played', and 'plays' all reduce to the stem 'play'.

**How Does Stemming Work?**

- It applies simple rules to remove common word endings (like -ing, -ed, -s).
- It does not check whether the result is a real dictionary word.
- It is fast because it uses rules, not a dictionary.

Sometimes the stem is not a proper word - for example, 'studies' → 'studi'.

**Major Stemming Algorithms**

- **Porter Stemmer:** The most popular; applies a series of rules step by step to strip suffixes. Example: 'happiness' → 'happi'.
- **Lancaster Stemmer:** More aggressive and faster; cuts more, but can over-shorten words.
- **Snowball Stemmer:** An improved version of Porter; supports many languages and is more accurate.

**Advantages and Limitation**

- **Advantage:** simple, fast, and reduces vocabulary size.
- **Limitation:** may produce non-words and can be inaccurate compared with lemmatization.

**Why is Stemming Important?**

- It groups related word forms together.
- It reduces the number of unique words to process.
- It improves search and text-matching speed.

**Real-life example:** In a document search, the words 'connect', 'connected', 'connecting', and 'connection' are all stemmed to 'connect' using the Porter Stemmer. Now a search for 'connect' finds all of them. This shows how stemming groups word forms for efficient searching.

**Q4. Explain GloVe, its use of word co-occurrence, and its advantages.**

**What is GloVe?**

GloVe stands for Global Vectors for Word Representation. 'Global' means looking at the whole collection of text, and 'Vectors' means number lists representing words. So GloVe is a method that creates word embeddings by studying how words appear together across an entire body of text.

It turns words into meaningful vectors where similar words are close together.

**What is Word Co-occurrence?**

'Co-occurrence' means how often two words appear together in the same context.

- GloVe builds a big table (co-occurrence matrix) counting how often each pair of words appears near each other.
- Words that often appear together (like 'ice' and 'cold') get related vectors.
- It uses these global counts, not just small nearby windows.

**How GloVe Works (Briefly)**

- Count word co-occurrences across all documents.
- Use these counts to learn vectors so that word relationships are captured mathematically.
- The result: words with similar co-occurrence patterns get similar vectors.

**Advantages of GloVe**

- **Uses global information:** It considers the whole corpus, capturing overall relationships.
- **Captures meaning and analogies:** It supports relationships like 'king - man + woman = queen'.
- **Efficient training:** It trains well on large text using the co-occurrence matrix.
- **Good similarity results:** Similar words end up close in the vector space.

**Why is GloVe Important?**

- It gives high-quality word meanings to machines.
- It improves tasks like search, translation, and classification.
- It combines the strengths of counting and prediction methods.

**Real-life example:** GloVe studies a huge amount of text and notices 'Paris' often appears with 'France', and 'Tokyo' with 'Japan'. It learns vectors capturing 'capital-of' relationships, so 'Paris - France + Japan' points near 'Tokyo'. This shows how GloVe uses global co-occurrence to capture meaning.

**Q5. Describe FastText and the role of character subwords in word representation.**

**What is FastText?**

FastText is a word-embedding method developed by Facebook (Meta). It is an improved version of Word2Vec. Its special feature is that it does not treat a word as a single unit - instead, it breaks each word into smaller character pieces called subwords.

So FastText represents words using their internal parts, not just the whole word.

**What are Character Subwords?**

'Character subwords' (also called character n-grams) are small pieces of a word made of a few letters.

- Example: the word 'playing' can be split into subwords like 'pla', 'lay', 'ayi', 'yin', 'ing'.
- FastText adds up these subword vectors to represent the full word.

**The Role of Subwords in Word Representation**

- **Handles rare words:** Even if a whole word was rarely seen, its subwords were seen in other words.
- **Handles unknown words:** New or unseen words can still be represented from their pieces.
- **Handles misspellings:** A typo shares many subwords with the correct word, so it is still understood.
- **Captures word structure:** Related forms like 'play', 'playing', 'played' share subwords, so they get similar vectors.

**Advantages of FastText**

- Better handling of rare and unknown words than Word2Vec.
- Works well for languages with many word forms.
- Understands word similarity through shared subwords.

**Why is FastText Important?**

- It solves Word2Vec's weakness with unseen words.
- It gives strong representations even with limited data.
- It improves accuracy in real, messy text.

**Real-life example:** Suppose the model never saw the word 'kindness' during training. FastText still represents it using its subwords like 'kind' and 'ness', which appeared in other words. So it understands 'kindness' relates to 'kind'. This shows the power of character subwords in FastText.

**Q6. Evaluate Term Frequency (TF), its calculation, and its role in NLP with an example.**

**What is Term Frequency (TF)?**

'Term' means a word, and 'Frequency' means how often something happens. So Term Frequency means how often a particular word appears in a document. It measures the importance of a word within a single document - the more it appears, the more important it may be for that document.

**How is TF Calculated?**

The basic formula is:

- TF = (Number of times the word appears in the document) ÷ (Total number of words in the document)

Dividing by the total word count keeps the value fair for long and short documents.

- Example: If 'data' appears 3 times in a document of 100 words, TF = 3 ÷ 100 = 0.03.

**The Role of TF in NLP**

- It helps identify which words are important in a document.
- It is a key part of the TF-IDF method used for text representation.
- It supports search engines in ranking documents by relevance.
- It turns text into numbers for machine learning.

**Limitation of TF Alone**

- Common words like 'the' and 'is' get high TF but are not meaningful.
- This is why TF is combined with IDF (Inverse Document Frequency) to reduce the weight of common words.

**Why is TF Important?**

- It measures word importance simply and quickly.
- It is the foundation of TF-IDF, a widely used technique.
- It improves search and document analysis.

**Real-life example:** In a document about cricket, the word 'cricket' appears 10 times out of 200 words, giving TF = 0.05. This high TF signals that 'cricket' is an important word for that document, helping a search engine match it to cricket-related queries. This shows TF's role in NLP.

**Q7. Describe Stop-word Removal with its advantages and limitations.**

**What is Stop-word Removal?**

'Stop-words' are very common words that carry little meaning on their own, such as 'the', 'is', 'and', 'a', and 'in'. 'Removal' means taking them out. So Stop-word Removal is the pre-processing step in NLP where these common, low-value words are removed from the text.

The idea is to keep only the meaningful words that matter for analysis.

**How Does It Work?**

- A list of stop-words is prepared (a stop-word list).
- The text is broken into tokens.
- Any token found in the stop-word list is removed.
- The remaining meaningful words are kept for further processing.

**Advantages of Stop-word Removal**

- **Reduces data size:** Fewer words mean faster processing.
- **Removes noise:** It keeps focus on important, meaningful words.
- **Improves performance:** It can improve results in tasks like classification and search.
- **Saves memory:** Smaller vocabulary uses less storage.

**Limitations of Stop-word Removal**

- **Can lose meaning:** Sometimes stop-words matter - for example, 'to be or not to be' becomes almost empty.
- **Harms some tasks:** In sentiment analysis, words like 'not' are important and should not be removed.
- **Language-dependent:** Stop-word lists differ by language and must be chosen carefully.

**Why is Stop-word Removal Important?**

- It cleans text before deeper analysis.
- It improves speed and focus.
- Knowing its limits prevents removing useful words by mistake.

**Real-life example:** For the sentence 'The weather is very good today', stop-word removal deletes 'The', 'is', and 'very', leaving 'weather good today'. This keeps the meaningful words for analysis and speeds up processing. But care is needed - removing 'not' from 'not good' would flip the meaning, showing the limitation too.

**Q8. Compare the CBOW and Skip-Gram approaches of Word2Vec.**

**Introduction**

Word2Vec is a popular method for creating word embeddings (word vectors). It has two main approaches: CBOW and Skip-Gram. Both learn word meanings from context, but they work in opposite directions. Let us compare them.

**What is CBOW (Continuous Bag of Words)?**

CBOW predicts a target word from its surrounding context words.

- Input: the surrounding (context) words.
- Output: the missing middle word.
- Example: Given 'The ___ sat on the mat', it predicts 'cat'.

**What is Skip-Gram?**

Skip-Gram works the opposite way - it predicts the surrounding context words from a single target word.

- Input: one word.
- Output: the words likely to appear around it.
- Example: Given 'cat', it predicts 'The', 'sat', 'on', 'the', 'mat'.

**Comparison of CBOW and Skip-Gram**

- **Direction:** CBOW predicts a word from context; Skip-Gram predicts context from a word.
- **Speed:** CBOW is faster to train.
- **Rare words:** Skip-Gram works better for rare/uncommon words.
- **Data size:** CBOW works well on smaller data; Skip-Gram shines on large data.
- **Accuracy for infrequent words:** Skip-Gram is usually more accurate for them.

**Why is This Comparison Important?**

- It helps choose the right approach for a task.
- Both produce useful word vectors, but suit different needs.
- Understanding them explains how Word2Vec learns meaning.

**Real-life example:** To build word vectors for a large medical text with many rare terms, Skip-Gram is chosen because it handles rare words well. For a small, common dataset needing quick training, CBOW is chosen for speed. This shows how CBOW and Skip-Gram differ and when each is used.

**Q9. Explain Inverse Document Frequency (IDF), its calculation, and its role in NLP with an example.**

**What is Inverse Document Frequency (IDF)?**

'Inverse' means opposite, 'Document Frequency' means how many documents contain a word. So IDF measures how rare or unique a word is across a whole collection of documents. The rarer a word, the higher its IDF - because rare words are usually more meaningful.

It is the opposite idea to simple counting: common words get low importance, rare words get high importance.

**How is IDF Calculated?**

The basic formula is:

- IDF = log (Total number of documents ÷ Number of documents containing the word)

- Example: If there are 1000 documents and the word 'data' appears in 100 of them, IDF = log(1000 ÷ 100) = log(10) = 1.
- A word appearing in almost every document gets an IDF close to 0.

**The Role of IDF in NLP**

- It reduces the importance of very common words (like 'the', 'is').
- It increases the importance of rare, meaningful words.
- Combined with TF, it forms TF-IDF, a key text representation method.
- It improves search relevance and document ranking.

**Why is IDF Important?**

- It fixes the weakness of counting common words as important.
- It highlights words that make a document distinctive.
- It powers search engines and text analysis.

**Real-life example:** Across 1000 news articles, the word 'the' appears in all of them, so its IDF is near 0 (not useful). But the word 'earthquake' appears in only 5 articles, so its IDF is high - marking it as an important, distinctive word. This helps a search engine rank earthquake articles correctly, showing the role of IDF.

**Q10. Differentiate between Word Tokenization and Sentence Tokenization.**

**What is Tokenization?**

'Tokenization' means breaking text into smaller pieces called tokens. It is one of the first steps in NLP. There are two common types - word tokenization and sentence tokenization. Let us understand and compare them.

**What is Word Tokenization?**

Word Tokenization breaks a piece of text into individual words (and punctuation).

- The unit produced is a single word.
- Example: 'I love NLP' → ['I', 'love', 'NLP'].
- It is used when the analysis works at the word level.

**What is Sentence Tokenization?**

Sentence Tokenization breaks a paragraph or document into individual sentences.

- The unit produced is a whole sentence.
- Example: 'I love NLP. It is fun.' → ['I love NLP.', 'It is fun.'].
- It is used when the analysis works at the sentence level.

**Key Differences**

- **Output unit:** Word tokenization gives words; sentence tokenization gives sentences.
- **Level of breaking:** Word-level vs sentence-level splitting.
- **Clues used:** Word tokenization uses spaces and punctuation; sentence tokenization uses full stops, question marks, etc.
- **Use case:** Word tokens for embeddings and counting; sentence tokens for summarization and translation.

**Why is This Important?**

- Choosing the right level of tokenization suits the task.
- Both are essential first steps in text processing.
- Correct tokenization improves all later NLP stages.

**Real-life example:** For a text summarizer, sentence tokenization first splits an article into sentences so each can be scored for importance. Then, within a chosen sentence, word tokenization splits it into words for detailed analysis. This shows how the two tokenization types differ and work together.

**Q11. Analyze how BERT generates context-dependent word representations.**

**What is BERT?**

BERT stands for Bidirectional Encoder Representations from Transformers. It is a powerful NLP model made by Google. Its special ability is that it understands a word based on the full context around it - the words before AND after it. This is called being 'bidirectional'.

**What Does 'Context-dependent' Mean?**

'Context-dependent' means the meaning (and vector) of a word changes depending on the sentence it is in.

- Older methods (like Word2Vec) gave one fixed vector to a word, ignoring context.
- BERT gives a different vector for the same word in different sentences.

**How BERT Generates Context-dependent Representations**

- **Bidirectional reading:** BERT looks at both left and right sides of a word at the same time.
- **Self-attention:** It uses an attention mechanism to weigh how much each other word matters to the current word.
- **Masked Language Model training:** During training, BERT hides some words (masks them) and learns to predict them from context - this teaches deep context understanding.
- **Result:** Each word's vector reflects the specific sentence it appears in.

**Why This Matters**

- The same word can have different meanings (polysemy), and BERT handles this.
- It captures meaning far better than fixed embeddings.
- It boosts accuracy in classification, question answering, and more.

**Why is BERT Important?**

- It understands language deeply and in context.
- It set new records on many NLP tasks.
- It can be fine-tuned for specific tasks easily.

**Real-life example:** Consider the word 'bank' in two sentences: 'I sat on the river bank' and 'I deposited money in the bank'. BERT gives 'bank' a different vector in each sentence because it reads the surrounding words. This context-dependent representation lets BERT understand the correct meaning each time.

**Q12. Discuss the importance of Text Pre-processing in NLP.**

**What is Text Pre-processing?**

'Pre-processing' means preparing and cleaning something before the main work. So Text Pre-processing means cleaning and organising raw text so it is ready for analysis by NLP models.

Raw text is often messy - full of punctuation, capital letters, common words, and different word forms. Pre-processing tidies it up.

**Common Text Pre-processing Steps**

- **Lowercasing:** Converting all text to small letters so 'Apple' and 'apple' are treated the same.
- **Removing punctuation and symbols:** Taking out marks that add little meaning.
- **Tokenization:** Breaking text into words or sentences.
- **Stop-word removal:** Removing common low-value words like 'the' and 'is'.
- **Stemming/Lemmatization:** Reducing words to their base forms.
- **Removing numbers/special characters:** Where they are not needed.

**Why is Text Pre-processing Important?**

- **Improves accuracy:** Clean data leads to better model results.
- **Reduces noise:** It removes unimportant parts that confuse models.
- **Reduces size:** It shrinks vocabulary, making processing faster.
- **Makes text consistent:** It standardises words so similar ones are grouped.
- **Enables number conversion:** Clean text is easier to turn into vectors.

**What Happens Without It?**

- Models get confused by messy, inconsistent text.
- Accuracy drops and processing becomes slower.
- The same word in different forms is wrongly treated as different.

**Real-life example:** Before analysing customer reviews, a system pre-processes 'The Product is AMAZING!!!' by lowercasing it, removing punctuation, removing the stop-word 'the', and keeping 'product amazing'. This clean version is easy to analyse correctly, showing why text pre-processing is so important.

**Q13. Differentiate between sparse and dense text representations with suitable examples.**

**Introduction**

To use text in machine learning, words are turned into vectors (lists of numbers). These vectors can be either sparse or dense. They differ in how the numbers are arranged. Let us compare them.

**What is a Sparse Representation?**

'Sparse' means thinly spread out - mostly empty. A sparse representation is a vector that is mostly filled with zeros, with only a few non-zero values.

- Methods like Bag-of-Words and TF-IDF produce sparse vectors.
- The vector length equals the whole vocabulary size (very large).
- Example: In a 10,000-word vocabulary, a short sentence's vector has 9,990 zeros and only a few non-zero counts.

**What is a Dense Representation?**

'Dense' means packed closely - full of values. A dense representation is a short vector where most values are meaningful (non-zero) real numbers.

- Word embeddings like Word2Vec, GloVe, and BERT produce dense vectors.
- The vector is short (for example, 100 or 300 numbers) but rich in meaning.
- Example: The word 'king' becomes a 300-number vector capturing its meaning.

**Key Differences**

- **Size:** Sparse vectors are very long; dense vectors are short.
- **Content:** Sparse are mostly zeros; dense are mostly meaningful numbers.
- **Meaning:** Sparse ignore word meaning; dense capture meaning and similarity.
- **Methods:** Sparse from BoW/TF-IDF; dense from embeddings.

**Why is This Important?**

- Dense vectors capture meaning better and use less space.
- Sparse vectors are simple but large and meaning-poor.
- Choosing the right type affects performance.

**Real-life example:** Representing the word 'happy': A sparse (one-hot) vector has a single 1 among thousands of 0s and carries no meaning. A dense embedding gives 'happy' a compact 300-number vector that sits close to 'joyful'. This shows the clear difference between sparse and dense representations.

**Q14. Compare traditional frequency-based text representations with distributed word representations.**

**Introduction**

Text must be turned into numbers for machines to use. There are two broad families of methods: traditional frequency-based representations and distributed word representations (embeddings). Let us compare them.

**What are Frequency-based Representations?**

These represent text by counting words. Examples are Bag-of-Words and TF-IDF.

- They rely on how often words appear.
- They produce large, sparse vectors (mostly zeros).
- They ignore word order and meaning.
- Example: TF-IDF gives each word an importance score based on counts.

**What are Distributed Word Representations?**

These represent each word as a short, dense vector learned from context. Examples are Word2Vec, GloVe, FastText, and BERT.

- The meaning of a word is 'distributed' across many numbers.
- They produce small, dense vectors rich in meaning.
- Similar words get similar vectors.
- Example: 'king' and 'queen' end up close together.

**Comparison**

- **Basis:** Frequency-based use counts; distributed use context learning.
- **Vector type:** Frequency-based are large and sparse; distributed are small and dense.
- **Meaning:** Frequency-based ignore meaning; distributed capture meaning and similarity.
- **Word relationships:** Only distributed capture analogies like 'king - man + woman = queen'.
- **Complexity:** Frequency-based are simpler; distributed need more training.

**Why is This Comparison Important?**

- It explains why NLP moved from counting to embeddings.
- Distributed methods give far richer understanding.
- Frequency-based methods are still useful as simple baselines.

**Real-life example:** For a search task, a TF-IDF (frequency-based) system matches only exact words, so 'car' does not match 'automobile'. A Word2Vec (distributed) system understands 'car' and 'automobile' are similar and matches both. This shows the advantage of distributed representations over frequency-based ones.

**UNIT 3**

**Q1. Assess the role of self-attention in Transformer-based classification.**

**What is Self-Attention?**

'Self' means the sentence looking at itself, and 'Attention' means focusing on important parts. So Self-Attention is a mechanism that lets each word in a sentence look at all the other words and decide which ones are most important for understanding it.

It is the key idea inside Transformer models like BERT.

**How Self-Attention Works (Briefly)**

- For every word, the model compares it with all other words in the sentence.
- It gives higher weight (attention) to the words that matter most for meaning.
- It then combines this information to create a rich, context-aware representation of each word.

**The Role of Self-Attention in Classification**

- **Captures context:** It understands each word in relation to the whole sentence.
- **Finds important words:** For classification, it focuses on the words that decide the class (like sentiment words).
- **Handles long-distance links:** It connects related words even if they are far apart.
- **Improves accuracy:** Richer understanding leads to better class predictions.

**Why Self-Attention Beats Older Methods**

- Older models (RNNs) read word by word and forget distant words.
- Self-attention sees the whole sentence at once and keeps all relationships.
- It also allows faster, parallel processing.

**Why is Self-Attention Important?**

- It is the heart of powerful Transformer models.
- It greatly improves text understanding and classification.
- It handles context and long sentences well.

**Real-life example:** To classify the review 'The movie was boring even though the acting was great' as negative, self-attention lets the model focus strongly on 'boring' while still noting 'great'. By weighing 'boring' as more important for the overall sentiment, the Transformer correctly classifies it as negative. This shows the role of self-attention in classification.

**Q2. Explain the Naive Bayes approach to Text Classification.**

**What is Naive Bayes?**

Naive Bayes is a machine-learning method based on probability (the chance of something happening). It uses a mathematical rule called Bayes' Theorem to predict the class of a text. It is called 'Naive' because it makes a simple assumption - that all words are independent of each other (which is not fully true, but works well).

**How Naive Bayes Classifies Text (Step by Step)**

- **Training:** It learns from labelled examples (for example, emails marked spam or not spam).
- **Word probabilities:** It calculates how likely each word is to appear in each class.
- **Prior probabilities:** It notes how common each class is overall.
- **Prediction:** For a new text, it multiplies the word probabilities for each class.
- **Choose the class:** It picks the class with the highest total probability.

**The 'Naive' Assumption**

- It assumes each word contributes independently to the class.
- Example: it treats 'free' and 'money' separately, even though together they signal spam.
- Despite this simplification, it performs very well in practice.

**Advantages of Naive Bayes**

- Simple, fast, and needs little training data.
- Works very well for spam detection and sentiment analysis.
- Handles many features (words) easily.

**Why is Naive Bayes Important?**

- It is a strong, popular baseline for text classification.
- It is easy to build and quick to run.
- It gives good accuracy on many text tasks.

**Real-life example:** To classify an email as spam or not, Naive Bayes checks words like 'free', 'win', and 'offer'. It calculates that these words make the 'spam' probability higher than 'not spam', so it classifies the email as spam. This shows how the Naive Bayes approach classifies text using word probabilities.

**Q3. Evaluate multiclass classification using Softmax Regression.**

**What is Multiclass Classification?**

'Multiclass' means more than two classes. So Multiclass Classification is the task of sorting an input into one of several possible categories (three or more), not just two.

Example: classifying a news article as 'sports', 'politics', or 'technology'.

**What is Softmax Regression?**

Softmax Regression (also called Multinomial Logistic Regression) is a method that extends logistic regression to handle many classes. Its special part is the Softmax function.

- The Softmax function takes the model's raw scores for all classes.
- It converts them into probabilities that add up to 1.
- The class with the highest probability is chosen as the prediction.

**How It Works (Step by Step)**

- The model calculates a score for each class from the input features.
- Softmax turns these scores into probabilities (for example, sports 0.7, politics 0.2, technology 0.1).
- The class with the highest probability (sports) is selected.

**Advantages of Softmax Regression**

- **Handles many classes:** It naturally supports three or more categories.
- **Gives probabilities:** It shows confidence for each class, not just a label.
- **Simple and effective:** It is easy to understand and works well for text.

**Why is This Important?**

- Many real problems have multiple classes.
- Probabilities help judge how sure the model is.
- It is widely used in the output layer of neural networks.

**Real-life example:** A model classifies a news article into one of three topics. Softmax gives probabilities: sports 0.75, politics 0.15, technology 0.10. Since sports has the highest probability, the article is classified as sports. This shows how Softmax Regression handles multiclass text classification.

**Q4. Illustrate the working principle of Support Vector Machine (SVM).**

**What is a Support Vector Machine (SVM)?**

SVM is a machine-learning method used mainly for classification. Its main idea is to draw the best possible boundary line (called a hyperplane) that separates data into different classes.

Imagine two groups of dots on paper; SVM finds the straightest, widest gap between them.

**The Working Principle of SVM**

- **Find a separating boundary:** SVM looks for a line (or plane in higher dimensions) that separates the classes.
- **Maximize the margin:** Among all possible boundaries, it chooses the one with the largest gap (margin) between the classes. A bigger gap means safer classification.
- **Support vectors:** The data points closest to the boundary are called support vectors. They 'support' and define the boundary.
- **Classification:** New data is classified based on which side of the boundary it falls.

**The Kernel Trick (for Complex Data)**

- When data cannot be separated by a straight line, SVM uses a 'kernel' to map it into a higher dimension where it can be separated.
- This lets SVM handle complex, non-linear patterns.

**Advantages of SVM**

- Works well with high-dimensional data (like text with many words).
- Effective even with limited data.
- Good accuracy for text classification.

**Why is SVM Important?**

- It is a strong, popular classifier for text.
- The wide-margin idea makes it robust.
- It handles complex data with kernels.

**Real-life example:** To classify emails as spam or not spam, SVM plots emails as points based on their word features and draws the widest-margin boundary between spam and non-spam. A new email is then placed and classified by which side it lands on. This illustrates how SVM works.

**Q5. Illustrate how a confusion matrix evaluates a text classification model and its performance measures.**

**What is a Confusion Matrix?**

A 'Confusion Matrix' is a table that shows how well a classification model performed by comparing its predictions with the actual correct answers. It reveals where the model got 'confused' - that is, where it made mistakes.

**The Four Parts of a Confusion Matrix**

- **True Positive (TP):** Predicted positive, and it really was positive (correct).
- **True Negative (TN):** Predicted negative, and it really was negative (correct).
- **False Positive (FP):** Predicted positive, but it was actually negative (wrong alarm).
- **False Negative (FN):** Predicted negative, but it was actually positive (missed it).

**Performance Measures From It**

- **Accuracy:** (TP + TN) ÷ (all cases) - overall correctness.
- **Precision:** TP ÷ (TP + FP) - of those predicted positive, how many were right.
- **Recall:** TP ÷ (TP + FN) - of all real positives, how many were found.
- **F1-Score:** the balance (harmonic mean) of precision and recall.

**Why is the Confusion Matrix Useful?**

- It shows not just how many, but what kind of errors were made.
- It helps calculate precision, recall, and F1.
- It reveals if the model favours one class wrongly.

**Why is This Important?**

- Accuracy alone can be misleading, especially with unbalanced data.
- The matrix gives a full, honest picture of performance.
- It guides improvements to the model.

**Real-life example:** A spam classifier is tested on 100 emails. The confusion matrix shows TP = 40 (spam caught), TN = 50 (safe emails passed), FP = 5 (safe emails wrongly marked spam), FN = 5 (spam missed). From this, precision = 40 ÷ 45 and recall = 40 ÷ 45, giving a clear picture of performance. This shows how a confusion matrix evaluates a model.

**Q6. Discuss overfitting and methods to improve model generalization.**

**What is Overfitting?**

'Overfitting' happens when a model learns the training data too well - including its noise and tiny details - so it performs excellently on training data but poorly on new, unseen data.

It is like a student who memorises answers word for word but cannot solve slightly different questions in the exam.

**What is Generalization?**

'Generalization' means the model's ability to perform well on new data it has never seen. Good generalization is the real goal - the opposite problem to overfitting.

**Signs of Overfitting**

- Very high accuracy on training data.
- Much lower accuracy on test/new data.
- The model is too complex for the amount of data.

**Methods to Improve Generalization**

- **More training data:** More examples help the model learn general patterns, not noise.
- **Regularization:** Adding a penalty (L1/L2) to discourage the model from becoming too complex.
- **Dropout:** In neural networks, randomly ignoring some neurons during training so the model does not over-rely on any.
- **Cross-validation:** Testing the model on different parts of the data to check real performance.
- **Early stopping:** Stopping training when performance on validation data stops improving.
- **Simpler model:** Using a less complex model that fits the data appropriately.
- **Data augmentation:** Creating more varied training examples.

**Why is This Important?**

- The aim is good performance on real, new data.
- Overfitting makes a model useless in practice.
- These methods keep models reliable.

**Real-life example:** A sentiment model reaches 99% accuracy on training reviews but only 60% on new reviews - a clear sign of overfitting. By adding more data, applying dropout, and using early stopping, its new-data accuracy rises to 88%. This shows how generalization is improved.

**Q7. Describe the working of RNN for text processing and its main steps.**

**What is an RNN?**

RNN stands for Recurrent Neural Network. 'Recurrent' means repeating or looping. An RNN is a type of neural network specially designed to handle sequences, like sentences, by processing words one after another while remembering what came before.

This memory makes RNNs suitable for text, where word order matters.

**How an RNN Works for Text (Main Steps)**

- **Step 1 - Input words in order:** The sentence is fed in one word (as a vector) at a time.
- **Step 2 - Hidden state (memory):** The RNN keeps a hidden state that stores information about previous words.
- **Step 3 - Update at each step:** For each new word, it combines the current word with the previous hidden state to update its memory.
- **Step 4 - Pass information forward:** The updated hidden state is carried to the next step, so context flows through the sentence.
- **Step 5 - Produce output:** After processing, it gives an output (for example, the sentiment or the next word).

**The Key Feature: Memory**

- The hidden state acts like a memory of the sentence so far.
- This lets the RNN understand context, not just single words.

**Limitation of Basic RNNs**

- They struggle to remember information from far back (the vanishing gradient problem).
- Improved versions like LSTM and GRU solve this.

**Why are RNNs Important?**

- They handle sequence data where order matters.
- They keep context across a sentence.
- They are the foundation for LSTM, GRU, and sequence models.

**Real-life example:** To predict the next word in 'I am reading a ...', the RNN processes 'I', 'am', 'reading', 'a' one by one, updating its memory each time. Using the remembered context, it predicts a likely next word like 'book'. This shows how an RNN processes text step by step using memory.

**Q8. Describe Text Classification and its major applications in NLP.**

**What is Text Classification?**

'Text' means written content, and 'Classification' means sorting things into groups. So Text Classification means automatically assigning a piece of text to one or more categories based on its content.

In simple words, it teaches a computer to read text and decide which labelled box it belongs to.

**How Text Classification Works (Briefly)**

- Text is cleaned and pre-processed.
- Words are converted into numbers (features).
- A model is trained on labelled examples.
- New text is then classified into a category.

**Major Applications of Text Classification**

- **Spam detection:** Sorting emails into spam or not spam.
- **Sentiment analysis:** Classifying reviews as positive, negative, or neutral.
- **Topic labelling:** Sorting news into topics like sports, politics, or business.
- **Language detection:** Identifying the language of a text.
- **Intent detection:** Understanding what a user wants in a chatbot.
- **Content moderation:** Detecting offensive or harmful text.

**Why is Text Classification Important?**

- It organises huge amounts of text automatically.
- It saves time compared with manual sorting.
- It powers many everyday tools (email, chatbots, reviews).

**Common Methods**

- Naive Bayes, SVM, Logistic Regression, and deep-learning models like RNN and BERT.

**Real-life example:** A news website automatically sorts incoming articles. Text classification reads each article and labels it as 'sports', 'politics', or 'technology', placing it in the right section without any human effort. This shows text classification and one of its major applications.

**Q9. Explain data preparation in Text Classification and its major steps.**

**What is Data Preparation?**

'Data Preparation' means getting the data ready before training a model. In text classification, it is the process of collecting, cleaning, and converting text into a form a machine-learning model can use.

Good preparation is essential - a model is only as good as the data given to it.

**Major Steps of Data Preparation**

- **Step 1 - Data collection:** Gather text examples along with their correct labels (for example, reviews labelled positive or negative).
- **Step 2 - Text cleaning:** Remove punctuation, symbols, and convert to lowercase.
- **Step 3 - Tokenization:** Break the text into words or tokens.
- **Step 4 - Stop-word removal:** Remove common low-value words like 'the' and 'is'.
- **Step 5 - Stemming/Lemmatization:** Reduce words to their base forms.
- **Step 6 - Feature extraction:** Convert words into numbers using methods like Bag-of-Words, TF-IDF, or embeddings.
- **Step 7 - Splitting data:** Divide data into training and testing sets.

**Why is Each Step Needed?**

- Cleaning removes noise that confuses the model.
- Tokenization and normalization make words consistent.
- Feature extraction turns text into machine-readable numbers.
- Splitting lets us test the model fairly on unseen data.

**Why is Data Preparation Important?**

- It directly affects model accuracy.
- Clean, well-prepared data gives better results.
- It reduces errors and speeds up training.

**Real-life example:** To build a spam classifier, data preparation collects labelled emails, cleans and tokenizes them, removes stop-words, applies stemming, converts words to TF-IDF numbers, and splits the data for training and testing. Only after this is the model trained - showing the major steps of data preparation.

**Q10. Describe Topic Modeling and explain how LDA identifies topics in documents.**

**What is Topic Modeling?**

'Topic' means the subject something is about, and 'Modeling' means finding a pattern. So Topic Modeling means automatically discovering the hidden topics present in a large collection of documents, without being told the topics in advance.

It groups words that often appear together into topics.

**What is LDA?**

LDA stands for Latent Dirichlet Allocation. It is the most popular topic-modeling method. 'Latent' means hidden. LDA assumes that:

- Each document is a mixture of several topics.
- Each topic is a mixture of certain words that appear together often.

**How LDA Identifies Topics (Briefly)**

- **Assume topics exist:** LDA is told how many topics to look for (say, 3).
- **Look at word patterns:** It studies which words frequently appear together across documents.
- **Group words into topics:** Words that co-occur are grouped into the same topic.
- **Assign topic mixtures:** Each document is described as a mix of these topics.
- **Refine repeatedly:** LDA adjusts the groupings until they are stable and meaningful.

**Example of Discovered Topics**

- Topic 1: {match, player, goal, team} → Sports
- Topic 2: {election, vote, party, government} → Politics

**Why is Topic Modeling Important?**

- It organises huge amounts of text automatically.
- It reveals hidden themes without manual reading.
- It helps in search, recommendation, and summarization.

**Real-life example:** A company has 10,000 news articles. LDA studies the words and discovers that some articles cluster around {match, player, goal} and others around {vote, party, election}. It labels these as 'Sports' and 'Politics' topics automatically. This shows how LDA identifies topics in documents.

**Q11. Differentiate between Lexicon-Based and Machine Learning-Based Sentiment Analysis.**

**Introduction**

Sentiment Analysis finds the opinion (positive, negative, neutral) in text. There are two main approaches to do this: Lexicon-Based and Machine Learning-Based. Let us understand and compare them.

**What is Lexicon-Based Sentiment Analysis?**

'Lexicon' means a dictionary of words. This approach uses a ready-made dictionary of words with pre-assigned sentiment scores.

- Positive words ('good', 'happy') have positive scores; negative words ('bad', 'sad') have negative scores.
- The system adds up the scores of words in a sentence to decide the overall sentiment.
- It does not need training data.

**What is Machine Learning-Based Sentiment Analysis?**

This approach trains a model on many labelled examples so it learns to predict sentiment.

- It learns patterns from data (reviews labelled positive or negative).
- Models like Naive Bayes, SVM, or BERT are used.
- It needs training data but adapts to context.

**Key Differences**

- **Basis:** Lexicon uses a word dictionary; ML learns from examples.
- **Training data:** Lexicon needs none; ML needs labelled data.
- **Context:** ML handles context and sarcasm better; lexicon is rigid.
- **Effort:** Lexicon is quick to set up; ML needs training but is more accurate.
- **Flexibility:** ML adapts to new domains; lexicon may miss new words.

**Why is This Comparison Important?**

- It helps choose the right method for a task.
- Lexicon suits quick, simple needs; ML suits accuracy and scale.

**Real-life example:** To judge 'The food was not good', a lexicon method might wrongly score 'good' as positive, missing the 'not'. A machine-learning model trained on real reviews learns that 'not good' is negative and classifies it correctly. This shows the difference between the two approaches.

**Q12. Explain Logistic Regression for binary text classification.**

**What is Binary Text Classification?**

'Binary' means two, so binary text classification means sorting text into one of two classes - for example, spam or not spam, positive or negative.

**What is Logistic Regression?**

Logistic Regression is a machine-learning method used for classification. Despite the word 'Regression' in its name, it is used to predict a class (a probability between 0 and 1), not a continuous number.

Its key part is the sigmoid function, which squashes any value into a probability between 0 and 1.

**How Logistic Regression Works (Step by Step)**

- **Convert text to features:** Words are turned into numbers (for example, TF-IDF).
- **Calculate a weighted score:** The model multiplies each feature by a learned weight and adds them.
- **Apply the sigmoid:** The score is passed through the sigmoid function to get a probability between 0 and 1.
- **Apply a threshold:** If the probability is above 0.5, it predicts class 1 (e.g., spam); otherwise class 0 (not spam).

**Advantages of Logistic Regression**

- Simple, fast, and easy to understand.
- Gives probabilities, showing confidence.
- Works very well for text with many features.

**Why is Logistic Regression Important?**

- It is a strong, popular method for binary text tasks.
- It is easy to train and interpret.
- It is a common building block in larger systems.

**Real-life example:** To classify a movie review as positive or negative, logistic regression converts the review to TF-IDF features, computes a weighted score, and applies the sigmoid. If the result is 0.85 (above 0.5), it classifies the review as positive. This shows how logistic regression performs binary text classification.

**Q13. Explain the role of precision, recall, and F1-score in evaluating NLP classification systems.**

**Introduction**

After building a classification model, we must measure how good it is. Accuracy alone is not enough, especially with unbalanced data. Three important measures are precision, recall, and F1-score. Let us understand each.

**What is Precision?**

'Precision' answers: of all the items the model predicted as positive, how many were actually positive?

- Formula: Precision = TP ÷ (TP + FP).
- High precision means few false alarms (few false positives).
- It matters when wrong positive predictions are costly.

**What is Recall?**

'Recall' answers: of all the actual positive items, how many did the model correctly find?

- Formula: Recall = TP ÷ (TP + FN).
- High recall means few missed cases (few false negatives).
- It matters when missing a positive is costly.

**What is F1-Score?**

'F1-Score' is the balance between precision and recall - their harmonic mean.

- Formula: F1 = 2 × (Precision × Recall) ÷ (Precision + Recall).
- It is high only when both precision and recall are high.
- It is useful when we need a single balanced number.

**The Role of These Measures**

- They give a fuller picture than accuracy alone.
- They reveal trade-offs (a model may have high recall but low precision).
- They suit unbalanced datasets, where accuracy can mislead.

**Why is This Important?**

- Different tasks value precision or recall differently.
- F1 balances both for a fair judgement.
- They guide model improvement.

**Real-life example:** A disease-detection text system that flags patient notes must have high recall so it does not miss sick patients (avoiding false negatives), even if precision drops a little. The F1-score checks that both stay reasonable. This shows the role of precision, recall, and F1-score in evaluation.

**Q14. Compare binary and multiclass text classification with suitable examples.**

**Introduction**

Text classification sorts text into categories. Depending on how many categories there are, it can be binary or multiclass. Let us understand and compare them.

**What is Binary Text Classification?**

'Binary' means two. Binary text classification sorts text into exactly one of two classes.

- There are only two possible labels.
- Example: an email is spam OR not spam; a review is positive OR negative.
- It often uses the sigmoid function to give one probability.

**What is Multiclass Text Classification?**

'Multiclass' means many classes. Multiclass text classification sorts text into one of three or more classes.

- There are several possible labels.
- Example: a news article is sports, politics, OR technology.
- It often uses the Softmax function to give probabilities across all classes.

**Key Differences**

- **Number of classes:** Binary has two; multiclass has three or more.
- **Output function:** Binary often uses sigmoid; multiclass uses softmax.
- **Complexity:** Multiclass is generally more complex.
- **Examples:** Spam/not-spam (binary) vs topic labelling (multiclass).

**Why is This Comparison Important?**

- The number of classes decides the model design.
- It affects the choice of output function and evaluation.
- Understanding both helps solve the right kind of problem.

**Real-life example:** A sentiment system that labels reviews only as positive or negative is binary classification. If it is upgraded to label reviews as positive, negative, OR neutral, it becomes multiclass classification and switches to a softmax output. This shows the clear difference between binary and multiclass text classification.

**UNIT 4**

**Q1. Evaluate encoder and decoder blocks in a Transformer architecture and their functions.**

**Introduction**

The Transformer is a powerful deep-learning model used in NLP. It is built from two main types of blocks: the encoder and the decoder. Let us understand each and its function.

**What is the Encoder Block?**

The 'Encoder' reads and understands the input sentence, turning it into a rich set of numbers (representations) that capture its meaning.

- It takes the input words (as embeddings plus positional encoding).
- It uses self-attention to let each word look at all other words.
- It passes the result through a feed-forward network.
- Its output is a meaning-rich representation of the input.

**What is the Decoder Block?**

The 'Decoder' generates the output sentence, one word at a time, using the encoder's understanding.

- It uses self-attention on the words it has generated so far.
- It uses cross-attention to focus on the encoder's output (the input meaning).
- It passes results through a feed-forward network.
- It produces the next output word.

**Functions Compared**

- **Encoder:** understands the input.
- **Decoder:** produces the output.
- **Together:** they enable sequence-to-sequence tasks like translation.

**Key Shared Components**

- Multi-head self-attention, feed-forward networks, positional encoding, and normalization appear in both.

**Why is This Important?**

- The encoder-decoder design powers translation, summarization, and more.
- Self-attention makes it fast and context-aware.
- It replaced older, slower RNN-based models.

**Real-life example:** In English-to-French translation, the encoder reads 'I am happy' and builds a meaning representation. The decoder then uses this to generate 'Je suis heureux' word by word, attending to the encoder's output at each step. This shows the functions of the encoder and decoder blocks.

**Q2. Differentiate between RNN/LSTM models and Transformers based on their processing approach.**

**Introduction**

RNN/LSTM models and Transformers are both used for sequence data like text, but they process information very differently. Let us compare their processing approaches.

**How RNN/LSTM Process Data**

- They read the sequence one word at a time, in order (sequentially).
- Each step depends on the previous step's output.
- They keep a hidden state (memory) passed along the sequence.
- LSTM improves basic RNN by remembering long-term information better.

**How Transformers Process Data**

- They read the whole sequence at once (in parallel), not one word at a time.
- They use self-attention so every word can directly look at every other word.
- Position information is added using positional encoding.
- There is no step-by-step chain of dependency.

**Key Differences**

- **Processing order:** RNN/LSTM are sequential; Transformers are parallel.
- **Speed:** Transformers are much faster to train (parallel).
- **Long dependencies:** Transformers handle long-distance relationships better; RNNs can forget distant words.
- **Memory:** RNN/LSTM use a hidden state; Transformers use attention.
- **Scalability:** Transformers scale to very large data and models.

**Why is This Comparison Important?**

- It explains why Transformers replaced RNNs in modern NLP.
- Parallel processing makes Transformers efficient.
- Attention captures context better than sequential memory.

**Real-life example:** To translate a long paragraph, an LSTM must process it word by word and may forget the beginning by the end. A Transformer reads all words together and uses attention to link the first and last words directly, producing a better translation faster. This shows the difference in their processing approaches.

**Q3. Differentiate between self-attention and cross-attention.**

**Introduction**

Attention lets a model focus on the important parts of the input. In Transformers, there are two kinds: self-attention and cross-attention. They differ in what the words pay attention to. Let us compare them.

**What is Self-Attention?**

'Self' means within the same sequence. In self-attention, each word in a sentence attends to the other words in the same sentence.

- It helps a word understand its own sentence's context.
- Example: in the encoder, each input word looks at all other input words.
- It captures relationships inside one sequence.

**What is Cross-Attention?**

'Cross' means between two different sequences. In cross-attention, words of one sequence attend to the words of another sequence.

- It connects the output being generated to the input.
- Example: in the decoder, each output word looks at the encoder's input representation.
- It links two sequences together (like source and target languages).

**Key Differences**

- **Attention target:** Self-attention stays within one sequence; cross-attention links two sequences.
- **Where used:** Self-attention in both encoder and decoder; cross-attention in the decoder (connecting to the encoder).
- **Purpose:** Self-attention builds internal context; cross-attention transfers information across sequences.

**Why is This Important?**

- Both are essential for sequence-to-sequence tasks.
- Self-attention understands each sentence; cross-attention aligns input with output.
- Together they enable accurate translation and generation.

**Real-life example:** In English-to-Hindi translation, self-attention helps the model understand the English sentence's internal structure, while cross-attention lets each Hindi word being generated focus on the relevant English words. This shows the difference between self-attention and cross-attention.

**Q4. Describe the role of Deep Learning in Advanced NLP and its improvements over traditional NLP.**

**What is Deep Learning in NLP?**

'Deep Learning' means using neural networks with many layers to learn from data automatically. In NLP, deep learning lets computers understand and generate language by learning patterns directly from huge amounts of text, instead of relying on hand-made rules.

**The Role of Deep Learning in Advanced NLP**

- It learns word meanings automatically through embeddings.
- It captures context using models like RNN, LSTM, and Transformers.
- It powers advanced tasks like translation, summarization, and question answering.
- Large models like BERT and GPT are built on deep learning.

**Improvements Over Traditional NLP**

- **Automatic feature learning:** Traditional NLP needed humans to design features by hand; deep learning learns them automatically.
- **Better context understanding:** Traditional methods (like Bag-of-Words) ignored order and meaning; deep learning captures context and word relationships.
- **Handling large data:** Deep learning improves as data grows; traditional methods plateau.
- **Higher accuracy:** Deep models achieve far better results on most NLP tasks.
- **Meaning-rich representations:** Embeddings capture similarity, which counting methods cannot.

**Why is Deep Learning Important in NLP?**

- It removed the need for slow, manual rule-writing.
- It gave machines deeper, human-like language understanding.
- It enabled today's powerful language tools.

**Real-life example:** Traditional translation using rules and word lists produced awkward sentences. Deep-learning translation with Transformers understands context and grammar, producing fluent, natural translations - as seen in modern Google Translate. This shows the role of deep learning and its big improvements over traditional NLP.

**Q5. Describe positional encoding in Transformer models and its purpose.**

**Why Positional Encoding is Needed**

Unlike RNNs, Transformers read all the words at once (in parallel) rather than one by one. This makes them fast, but it creates a problem: the model does not automatically know the order of the words. Yet word order is very important - 'dog bites man' is different from 'man bites dog'.

**What is Positional Encoding?**

'Positional' means related to position, and 'Encoding' means turning information into numbers. So Positional Encoding is a method that adds information about each word's position in the sentence to its word vector.

- It gives each position a unique numerical pattern.
- This pattern is added to the word embedding.
- Now the model knows both the word and where it sits in the sentence.

**How It Works (Briefly)**

- Each position (1st, 2nd, 3rd word...) gets its own encoding, often made using sine and cosine patterns.
- This encoding is added to the corresponding word's embedding.
- The combined vector carries meaning plus position.

**The Purpose of Positional Encoding**

- To give the Transformer a sense of word order.
- To let attention consider which words come before or after.
- To preserve the sequence structure lost by parallel processing.

**Why is Positional Encoding Important?**

- Without it, the Transformer would treat a sentence as an unordered bag of words.
- It restores the crucial information of order.
- It helps the model understand meaning correctly.

**Real-life example:** For the sentences 'The cat chased the dog' and 'The dog chased the cat', the same words are used but the order differs. Positional encoding tells the Transformer which word came first, so it understands the two sentences mean different things. This shows the purpose of positional encoding.

**Q6. Describe the importance of Attention in Transformer models.**

**What is Attention?**

'Attention' in NLP means the ability of a model to focus on the most important words when understanding or generating text. Just as a human reader pays more attention to key words, the attention mechanism lets a model weigh which words matter most for each word.

Attention is the central idea that makes Transformers so powerful.

**How Attention Works (Briefly)**

- For each word, the model compares it with all other words.
- It gives higher weights (attention scores) to the more relevant words.
- It combines information from all words based on these weights.
- This creates a context-aware understanding of each word.

**The Importance of Attention in Transformers**

- **Captures context:** It understands each word in relation to the whole sentence.
- **Handles long-distance links:** It connects related words even if far apart, which RNNs struggle with.
- **Enables parallel processing:** All words are processed together, making Transformers fast.
- **Improves accuracy:** Richer understanding leads to better results in translation, summarization, and more.
- **Focuses on key words:** It ignores unimportant words and highlights meaningful ones.

**Why is Attention So Valuable?**

- It solved the memory problem of older sequence models.
- It made large models like BERT and GPT possible.
- It gives machines a more human-like reading ability.

**Real-life example:** In the sentence 'The trophy did not fit in the suitcase because it was too big', attention helps the model figure out that 'it' refers to the 'trophy', by giving 'trophy' a high attention score. This correct linking of far-apart words shows the importance of attention in Transformers.

**Q7. Discuss the major limitations of Classical NLP methods and discuss their impact on NLP tasks.**

**What are Classical NLP Methods?**

'Classical' NLP methods are the older, traditional techniques such as Bag-of-Words, TF-IDF, rule-based systems, and simple statistical models. They mostly rely on counting words and hand-made rules rather than deep learning.

While useful and simple, they have several important limitations.

**Major Limitations of Classical NLP Methods**

- **Ignore word order:** Methods like Bag-of-Words treat text as an unordered set, so 'dog bites man' and 'man bites dog' look the same.
- **Ignore meaning and context:** They do not understand that 'happy' and 'joyful' are similar, or that 'bank' has two meanings.
- **Large, sparse vectors:** They create huge vectors full of zeros, wasting memory and slowing processing.
- **Manual feature design:** They often need experts to craft features and rules by hand.
- **Poor with unseen words:** New or rare words are handled badly.
- **Weak on complex language:** They struggle with sarcasm, ambiguity, and long dependencies.

**Impact of These Limitations on NLP Tasks**

- **Lower accuracy:** Tasks like translation and sentiment analysis give poor results.
- **Meaning errors:** Ignoring context causes wrong interpretations.
- **Scalability problems:** Sparse vectors and manual rules do not scale to big data.
- **Limited progress:** These limits held back advanced tasks until deep learning arrived.

**Why is Understanding These Limits Important?**

- It explains why NLP moved to embeddings and Transformers.
- It shows the value of context-aware methods.
- It guides the choice of method for a task.

**Real-life example:** A classical Bag-of-Words sentiment system reads 'not good' but ignores order and treats 'good' as positive, wrongly classifying the review. This meaning error shows how the limitations of classical NLP methods harm real tasks - which modern deep-learning methods overcome.

**Q8. Explain the Attention Mechanism in Seq2Seq models with a suitable example.**

**What is a Seq2Seq Model?**

Seq2Seq means Sequence-to-Sequence. It is a model that takes one sequence as input and produces another sequence as output - for example, translating an English sentence into French. It has an encoder (which reads the input) and a decoder (which generates the output).

**The Problem Without Attention**

- In basic Seq2Seq, the encoder squeezes the whole input into a single fixed vector.
- For long sentences, this single vector cannot hold all the information.
- The decoder then forgets important early words, giving poor output.

**What is the Attention Mechanism?**

The Attention Mechanism solves this by letting the decoder look back at all the encoder's word representations, not just one fixed vector.

- At each output step, the decoder decides which input words are most relevant.
- It gives higher weights (attention) to those important words.
- It then focuses on them while generating the next output word.

**How It Helps**

- The decoder always has access to the full input.
- It focuses on the right input word at the right time.
- This greatly improves accuracy for long sentences.

**Why is Attention Important in Seq2Seq?**

- It removes the fixed-vector bottleneck.
- It handles long sentences well.
- It laid the foundation for Transformer models.

**Real-life example:** When translating 'The weather is nice today' into French, the attention mechanism lets the decoder focus on 'weather' while producing 'temps', and on 'nice' while producing 'agréable'. By attending to the correct input word at each step, the translation becomes accurate. This shows the attention mechanism in Seq2Seq models.

**Q9. Explain the applications of Seq2Seq models in NLP with suitable examples.**

**What is a Seq2Seq Model?**

Seq2Seq means Sequence-to-Sequence - a model that converts one sequence into another using an encoder (to read the input) and a decoder (to produce the output). It is very useful whenever both the input and output are sequences of words.

**Major Applications of Seq2Seq Models**

- **Machine Translation:** Converting a sentence from one language to another. Example: English 'Good morning' → Hindi 'सुप्रभात'.
- **Text Summarization:** Turning a long document into a short summary. Example: a long article → a two-line summary.
- **Chatbots and Dialogue Systems:** Converting a user's message into a suitable reply. Example: 'How are you?' → 'I am fine, thank you!'.
- **Question Answering:** Converting a question into an answer. Example: 'What is the capital of France?' → 'Paris'.
- **Speech Recognition:** Converting a sequence of audio signals into a sequence of text words.
- **Text Generation:** Producing captions or continuing text from a prompt.

**Why are Seq2Seq Models Useful for These Tasks?**

- Both input and output are sequences of variable length.
- The encoder understands the input; the decoder generates a fitting output.
- With attention, they handle long inputs well.

**Why are Seq2Seq Models Important?**

- They power many core NLP tasks.
- They handle flexible input and output lengths.
- They are the basis for modern translation and generation systems.

**Real-life example:** A translation app uses a Seq2Seq model: the encoder reads the English sentence 'I love reading books', and the decoder generates the French sentence 'J'aime lire des livres'. The same design is reused for summarization and chatbots. This shows the applications of Seq2Seq models in NLP.

**Q10. Illustrate the concept and working of Seq2Seq models using the Encoder-Decoder architecture.**

**What is a Seq2Seq Model?**

Seq2Seq means Sequence-to-Sequence. It converts an input sequence (like an English sentence) into an output sequence (like a French sentence). It is built using two main parts: an encoder and a decoder.

**The Encoder-Decoder Architecture**

- **Encoder:** Reads the entire input sequence, word by word, and compresses its meaning into a representation (a context vector or set of vectors).
- **Decoder:** Takes this representation and generates the output sequence, one word at a time.

**How It Works (Step by Step)**

- **Step 1 - Input to encoder:** The input words are converted to vectors and fed into the encoder.
- **Step 2 - Encoding:** The encoder (often an RNN/LSTM or Transformer) processes them and builds a meaning representation.
- **Step 3 - Pass to decoder:** This representation is handed to the decoder.
- **Step 4 - Decoding:** The decoder generates the first output word, then uses it to generate the next, and so on.
- **Step 5 - Output complete:** The process continues until an end signal is produced.

**The Role of Attention**

- Modern Seq2Seq models add attention so the decoder can focus on the most relevant input words at each step, improving accuracy for long sequences.

**Why is This Architecture Important?**

- It handles variable-length input and output.
- It powers translation, summarization, and chatbots.
- It is the foundation of Transformer models.

**Real-life example:** To translate 'I am learning' into Hindi, the encoder reads all three words and builds a meaning representation. The decoder then generates 'मैं सीख रहा हूँ' word by word, using attention to focus on the right input word each time. This illustrates the working of the encoder-decoder Seq2Seq architecture.

**Q11. List and evaluate the major components of the Transformer architecture and their functions.**

**What is the Transformer Architecture?**

The Transformer is a deep-learning model for NLP that processes all words in parallel using attention instead of reading them one by one. It is made of several important components working together. Let us list and evaluate them.

**Major Components and Their Functions**

- **Input Embedding:** Converts each word into a numerical vector that captures its meaning.
- **Positional Encoding:** Adds information about each word's position, since the model reads all words at once and would otherwise lose order.
- **Multi-Head Self-Attention:** Lets each word attend to all other words in multiple ways at once, capturing different relationships and context.
- **Feed-Forward Network:** A small neural network applied to each word to further process and transform its representation.
- **Add and Normalize (Residual + Layer Norm):** Helps training by keeping information flowing and stabilising the values.
- **Encoder:** A stack of the above blocks that understands the input.
- **Decoder:** A stack that generates the output, using self-attention and cross-attention to the encoder.
- **Output Layer (Linear + Softmax):** Converts the final vectors into probabilities to choose the next output word.

**Evaluation of the Design**

- **Strength:** Parallel processing makes it fast; attention captures long-distance context.
- **Strength:** Multi-head attention captures many relationships at once.
- **Result:** High accuracy on translation, summarization, and more.

**Why is This Important?**

- These components together make Transformers powerful and efficient.
- They replaced slower RNN models.
- They are the base of BERT and GPT.

**Real-life example:** In a translation Transformer, input embedding and positional encoding prepare the sentence, multi-head self-attention understands it, the feed-forward network refines it, and the decoder with softmax generates the translation. Each component plays its role - showing the major parts of the Transformer architecture.

**Q12. Explain Multi-Head Attention and how multiple heads capture different relationships.**

**What is Attention (Recap)?**

Attention lets a model focus on the most important words when understanding each word. A single attention calculation is called one 'head'. Multi-Head Attention uses several of these heads at the same time.

**What is Multi-Head Attention?**

'Multi-Head' means many heads (many attention calculations) working in parallel. Instead of computing attention just once, the model computes it several times with different learned settings, then combines the results.

- Each head looks at the sentence from a different angle.
- The outputs of all heads are joined together.
- This gives a richer, more complete understanding.

**How Multiple Heads Capture Different Relationships**

- **Different focus per head:** One head may focus on grammar links (subject-verb), another on meaning links, another on long-distance references.
- **Parallel viewpoints:** Because they run together, the model captures many types of relationships at once.
- **Combined richness:** Joining all heads gives a fuller picture than a single head could.

**Advantages of Multi-Head Attention**

- Captures several kinds of word relationships simultaneously.
- Improves understanding of complex sentences.
- Increases the model's power and accuracy.

**Why is Multi-Head Attention Important?**

- Language has many kinds of relationships (grammar, meaning, reference).
- One head cannot capture them all; many heads can.
- It is a core reason Transformers are so effective.

**Real-life example:** In the sentence 'The girl who won the race was happy', one attention head links 'girl' with 'won' (who did the action), while another links 'girl' with 'happy' (the description). By using multiple heads, the Transformer captures both relationships at once - showing how multi-head attention captures different relationships.

**Fill in the Blanks**

**1.** PV-DM stands for __________.
**Answer:** Distributed Memory

**2.** spaCy provides a tool called Dependency __________ to show grammatical relationships between words.
**Answer:** Parsing

**3.** The process of reducing words to their root form is called __________.
**Answer:** Stemming

**4.** A numerical vector that represents the meaning of an entire sentence is called a __________.
**Answer:** Sentence Embedding

**5.** One word having multiple meanings depending on the context is known as __________.
**Answer:** Polysemy

**6.** PV-DBOW is similar to the __________ approach of Word2Vec.
**Answer:** Skip-Gram

**7.** Identifying unwanted or harmful messages such as spam emails is called __________.
**Answer:** Spam detection

**8.** The process of converting words into meaningful base forms is called __________.
**Answer:** Lemmatization

**9.** SBERT stands for __________.
**Answer:** Sentence-BERT

**10.** __________ Tagging assigns a grammatical category to every word in a sentence.
**Answer:** Part-of-Speech (POS)

**11.** The two types of Doc2Vec are PV-DM and __________.
**Answer:** PV-DBOW

**12.** In POS tagging, the tag __________ represents an adjective.
**Answer:** JJ

**13.** __________ is an extension of Word2Vec that generates embeddings for documents, paragraphs, or sentences.
**Answer:** Doc2Vec

**14.** Information Retrieval commonly uses __________ and searching to find relevant documents.
**Answer:** Indexing

**15.** Information Retrieval mainly focuses on finding the __________ information or document.
**Answer:** Correct

**16.** A word or sentence having more than one meaning creates a problem called __________.
**Answer:** Ambiguity

**17.** Text data that is not organized in rows and columns is called __________ data.
**Answer:** Unstructured

**18.** In POS tagging, the tag __________ represents a noun.
**Answer:** NN

**19.** The technique used to identify the grammatical structure of a sentence using a parse tree is called __________ parsing.
**Answer:** Syntactic

**20.** In NLP, the removal of commonly occurring words such as "the", "is", and "and" is called __________.
**Answer:** Stop-word removal

**Multiple Choice Questions**

**1.** Which task is used by BERT to predict hidden words in a sentence?
A. Next Token Prediction
B. Masked Language Model
C. Text Classification
D. Sentiment Analysis
**Answer:** B. Masked Language Model

**2.** Which pair represents the teacher-student relationship in knowledge distillation?
A. LSTM → RNN
B. SVM → BERT
C. BERT → DistilBERT
D. RNN → Naive Bayes
**Answer:** C. BERT → DistilBERT

**3.** What does GPT stand for?
A. General Processing Transformer
B. Generative Processing Technology
C. Generative Pre-trained Transformer
D. General Pre-trained Technology
**Answer:** C. Generative Pre-trained Transformer

**4.** BERT understands a word mainly by considering:
A. Only the previous word
B. Only the next word
C. Context on both sides
D. Only word frequency
**Answer:** C. Context on both sides

**5.** Which LSTM gate decides which old information should be removed?
A. Input gate
B. Output gate
C. Forget gate
D. Update gate
**Answer:** C. Forget gate

**6.** Which problem of simple RNNs is LSTM designed to address?
A. Over-sampling
B. Vanishing gradient problem
C. Data duplication
D. Tokenization problem
**Answer:** B. Vanishing gradient problem

**7.** Approximately what percentage of words are randomly masked during BERT's Masked Language Model training?
A. 5%
B. 15%
C. 10%
D. 25%
**Answer:** B. 15%

**8.** Which NLP task identifies names of people, places and organizations in text?
A. Text Summarization
B. Machine Translation
C. Named Entity Recognition
D. Token Generation
**Answer:** C. Named Entity Recognition

**9.** GPT generates text using which type of process?
A. Autoregressive process
B. Manual process
C. Random process
D. Image-based process
**Answer:** A. Autoregressive process

**10.** In the sentence "I went to the bank to deposit money," how does BERT determine the meaning of "bank"?
A. By counting the word
B. By removing the word
C. By using surrounding context
D. By checking word length
**Answer:** C. By using surrounding context

**11.** What is fine-tuning in BERT?
A. Training BERT from scratch
B. Adapting the pre-trained BERT model for a specific task
C. Removing unnecessary words
D. Increasing the size of the dataset
**Answer:** B. Adapting the pre-trained BERT model for a specific task

**12.** In the sentence "The food was good but the service was slow," which model can retain important earlier information?
A. LSTM
B. Naive Bayes
C. SVM
D. Logistic Regression
**Answer:** A. LSTM

**13.** Which GPT model is known for introducing few-shot learning at a large scale?
A. GPT-1
B. GPT-3
C. GPT-2
D. GPT-4
**Answer:** B. GPT-3

**14.** Which of the following is an application of fine-tuned BERT?
A. Sentiment Analysis
B. Image Compression
C. Video Editing
D. Audio Mixing
**Answer:** A. Sentiment Analysis

**15.** In the sentence "The movie, despite a slow start, was excellent," what information does the LSTM example show it can remember?
A. The word "the"
B. The important sentiment signal "excellent"
C. The word "slow"
D. Only punctuation
**Answer:** B. The important sentiment signal "excellent"

**16.** DistilBERT was developed using which technique?
A. Gradient Boosting
B. Knowledge Distillation
C. Data Augmentation
D. Stemming
**Answer:** B. Knowledge Distillation

**17.** What is the main purpose of LSTM in sequential data processing?
A. To remove all words
B. To learn long-term dependencies
C. To reduce document size
D. To create word counts
**Answer:** B. To learn long-term dependencies

**18.** What does Next Sentence Prediction in BERT determine?
A. The length of a sentence
B. Whether two sentences are logically related
C. The sentiment of a sentence
D. The number of words in a sentence
**Answer:** B. Whether two sentences are logically related

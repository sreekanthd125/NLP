NLP means teaching computers to understand text.

First step is collecting a paragraph (your Paragraph variable).

Then we split the paragraph into sentences using:

nltk.sent_tokenize() → Sentence Tokenization

Next, each sentence is broken into words using Tokenization.

Before training a model, text must be cleaned.

You used Regex (re.sub) to remove unwanted characters:

Removed numbers

Removed punctuation

Kept only letters (a–z, A–Z)

Converted all text to lowercase.

Split the cleaned text into individual words.

Removed stopwords like “is”, “the”, “and” using:

stopwords.words('english')

Performed Stemming using PorterStemmer:

Converted words to their root form

Example: running → run, studies → studi

Built a corpus, which is a list of all cleaned sentences.

Used CountVectorizer to convert text into numbers (Bag of Words).

cv.fit_transform(corpus) creates a matrix of word counts.

This matrix is stored in X.

Labels (spam/not spam) are stored in y (in your later code).

Used train_test_split() to divide data:

X_train → Text used for training

X_test → Text used for testing

y_train → Correct labels for training data

y_test → Correct labels for test data

Then created a spam detection model using:

MultinomialNB()

Trained the model using:

.fit(X_train, y_train)

Made predictions on unseen data with:

.predict(X_test)

Compared predictions with real answers using accuracy score.

Printed the model’s accuracy (e.g., 0.90 = 90%).

This shows how well your model can detect spam.

The full pipeline:

Cleaning → Tokenizing → Stemming → Stopwords → Vectorizing → Splitting → Training → Testing.

These preprocessing steps improve model accuracy.

Without them, raw text would be noisy and hard for ML models to understand.

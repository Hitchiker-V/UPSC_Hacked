# UPSC Hacked
### Syllabus Knowledge Service
￼* Get all the recommended books from the UPSC syllabus and create embeddings out of them
￼* Put the embeddings in a vector DB

### Questions Collection Service
￼* Get all question papers since the past 15 years and create embeddings of questions-option pair out of them
￼* Put the embeddings in different Vector DBs instantiated based on the Paper (eg. Prelims-Paper 1 etc)

### Paper Insight Service
￼* Create multiple tables in DB that contains all the questions as a question-option mapping per row, based on the Paper (eg. Prelims-Paper 1 etc)
￼* Cluster the questions-options together based on the similarity index between their embeddings, per table using *Questions Collection Service generated data*
￼* Find patterns in the frequency of occurrence, complexity of the questions, degree of variations between the multiple instances of same base questions, per table
￼* Generate a “probability to occur next exam" for all the questions, per table
￼* Fetch out the X questions (X = General number of total questions in a given paper), per paper having a probability above a threshold (Y)

### UPSC Prep Buddy (Agent)
￼* Use Syllabus Knowledge Service generated embeddings and Questions Collection Service generated embeddings to extract reading material from knowledge base and save it in a paper-wise tables (‘Answer to UPSC Paper A (Paper Name) questions’)
￼* Pull out data from the *Answer to UPSC Paper A (Paper Name) questions* tables (for each paper) and create chapter notes based on these answers using Bullet Points

### Starting an MVP:
￼* Using Prelim Paper 1 2023 as reference
￼* Extracting all questions and store in a DB
￼* Run Embedding logic and store in Vector DB
￼* Run Embedding logic over syllabus recommended for Prelim Paper 1
￼* Find similarity between questions embedding and syllabus embeddings and create a table in DB with the following structure:
	|  Question  | Book Name | Knowledge text | Page No  |
￼* Use a PDF parser to create notes per page in bullet points
￼* Compile the notes and store in another DB
￼* Create bullet point notes per chapter per book of the syllabus
￼* Run an Agent to read from this new knowledge base using RAG

# Movie-Recommendation-System
**Overview**

A movie recommendation system aims to suggest movies to users based on their preferences. The approach used in this notebook involves content-based filtering, which recommends movies similar to those a user has liked in the past based on specific attributes like genres, director, actors, and language.

**Steps Involved**

**Data Loading:**

The first step is to load the dataset containing information about various movies. This dataset includes columns like movie titles, genres, directors, actors, and language.

**Data Preprocessing:**

Handling Missing Values: Some entries in the dataset might have missing values. These missing values are filled with empty strings to avoid issues during processing.
Combining Features: The selected features (genres, director, actors, language) are combined into a single string for each movie. This combined string represents all the relevant information about a movie in a single text.

**Text Vectorization:**

TF-IDF Vectorizer: The combined text features are converted into numerical format using a technique called TF-IDF (Term Frequency-Inverse Document Frequency). This technique transforms the text data into vectors where each dimension represents the importance of a word in the overall dataset. This helps in understanding the significance of words and their occurrence in different movies.

**Similarity Calculation:**

Cosine Similarity: Once the text data is vectorized, the cosine similarity metric is used to measure the similarity between the vectors of different movies. Cosine similarity calculates the cosine of the angle between two vectors, providing a value between -1 and 1. In this context, a value closer to 1 indicates higher similarity between two movies.

**Movie Recommendation:**

User Input: The user inputs the name of their favorite movie.
Finding Close Matches: To handle minor spelling mistakes or variations in the input movie title, a technique from the difflib library is used to find the closest match to the input movie title from the list of all movie titles.

Fetching Recommendations: The index of the closely matched movie is used to find its similarity score with all other movies. These similarity scores are then sorted in descending order to identify the top similar movies.

Displaying Recommendations: The top N similar movies (in this case, 10) are displayed to the user as recommendations.

**Key Concepts**

**TF-IDF (Term Frequency-Inverse Document Frequency):**

Term Frequency (TF): Measures how frequently a term appears in a document.

Inverse Document Frequency (IDF): Measures how important a term is by considering the number of documents in which it appears.

TF-IDF Score: The product of TF and IDF, indicating the importance of a term in a specific document relative to the entire corpus.

**Cosine Similarity:**

A metric used to measure how similar two documents (or vectors) are, irrespective of their size. It calculates the cosine of the angle between two vectors. If the vectors are identical, the cosine similarity will be 1; if they are orthogonal (completely dissimilar), it will be 0.

**Benefits and Limitations**

**Benefits:**

Personalized Recommendations: Provides recommendations based on individual user preferences.

No Need for Extensive User Data: Does not require historical user data or extensive user interaction history.

**Limitations:**

Content Dependency: Only works well if the content (features) of the items are well-defined and descriptive.

Cold Start Problem: Struggles with recommending new movies that lack sufficient descriptive content.

Limited Scope: Cannot recommend movies outside the scope of the defined content features (genres, director, etc.).

**Conclusion**

The movie recommendation system in this notebook provides a practical approach to suggesting movies based on user preferences using content-based filtering. By combining text features, transforming them into numerical vectors, and calculating similarities, the system efficiently identifies and recommends movies similar to the user's favorite ones.

# 🎬 Movie Recommendation System

This is a simple **content-based Movie Recommendation System** built using Python and machine learning. Given a movie title, the system recommends 10 similar movies using cosine similarity based on movie metadata (like genres, cast, keywords, etc.).

---

## 🧠 How It Works

The system uses `CountVectorizer` to convert movie metadata into a vector format and applies **cosine similarity** to find the most similar movies.

The core function:

```python
def recommend(movie):
    movie_index = new_df[new_df['title'] == movie].index[0]
    distances = similarity[movie_index]
    movies_list = sorted(list(enumerate(distances)), reverse=True, key=lambda x:x[1])[1:11]
    
    for i in movies_list:
        print(new_df.iloc[i[0]].title)

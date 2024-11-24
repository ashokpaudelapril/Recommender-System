


# 🎥 **Movie Recommendation System**

## 📖 **Overview**
This repository contains a **Movie Recommendation System** built using **Collaborative Filtering (CF)**. By analyzing user ratings, the system recommends movies that are similar to a selected movie. The project is implemented in Python and leverages popular libraries for data analysis and visualization.

---

## 🚀 **Features**
- **User Preferences Analysis**: Understand trends and patterns in movie ratings.
- **Movie Recommendations**: Suggest movies based on similarity to a given movie.
- **Visual Insights**: Explore data using interactive plots and histograms.
- **Scalability**: Easily extendable to include advanced recommendation techniques.

---

## 📂 **Dataset**
1. **`u.data`**  
   - `user_id`: Unique user identifier.  
   - `item_id`: Unique movie identifier.  
   - `rating`: User's rating for the movie (scale: 1–5).  
   - `timestamp`: Interaction time.  

2. **`Movie_Id_Titles.csv`**  
   - `item_id`: Unique movie identifier.  
   - `title`: Name of the movie.  

---

## 🛠️ **Dependencies**
To set up the environment, install the following libraries:
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`

Install them using:
```bash
pip install numpy pandas matplotlib seaborn
```

## 🖥️ Usage

### Step 1: Clone the Repository
```bash
git clone https://github.com/your-username/movie-recommendation-system.git
cd movie-recommendation-system
```

### Step 2: Place the Datasets
Make sure `u.data` and `Movie_Id_Titles.csv` are in the project directory.

### Step 3: Run the Script
Run the Python script to generate recommendations:
```bash
python recommendation_system.py
```

## 📊 How It Works

### 1️⃣ Data Preprocessing
Merge user ratings and movie titles for combined analysis:
```python
df = pd.merge(df, movie_titles, on='item_id')
```

### 2️⃣ Data Visualization
Understand data trends using histograms and scatterplots:
```python
ratings['num_of_ratings'].hist(bins=70)
sns.jointplot(x='rating', y='num_of_ratings', data=ratings, alpha=0.5)
```

### 3️⃣ Building the User-Movie Matrix
Create a pivot table to represent user ratings for movies:
```python
moviemat = df.pivot_table(index='user_id', columns='title', values='rating')
```

### 4️⃣ Generate Recommendations
Compute correlations with a selected movie:
```python
similar_to_movie = moviemat.corrwith(moviemat['Star Wars (1977)'])
```
Filter by popularity for reliable recommendations:
```python
corr_movie[corr_movie['num_of_ratings'] > 100].sort_values('Correlation', ascending=False)
```

## 📈 Outputs

### Visualizations
Histograms and scatterplots to explore rating trends and relationships.

### Recommendations
Movies similar to the given input, ranked by correlation strength:
```mathematica
Correlation    Title
1.000000       Star Wars (1977)
0.748353       Empire Strikes Back, The (1980)
0.672556       Return of the Jedi (1983)
```

## 🗂️ Project Structure
```perl
movie-recommendation-system/
├── u.data                 # User ratings dataset
├── Movie_Id_Titles.csv    # Movie titles dataset
├── recommendation_system.py # Main script
└── README.md              # Documentation
```

## 🌟 Future Enhancements
- Implement Model-Based Collaborative Filtering using ML techniques.
- Combine Content-Based Filtering for a hybrid recommendation system.
- Add a web interface for real-time recommendations.

## 📜 License
This project is licensed under the MIT License.
```

Feel free to customize it further if needed! 😊

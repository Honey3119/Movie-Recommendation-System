# Movie Recommendation System
A machine learning-based movie recommendation system using collaborative filtering techniques on the MovieLens 1M dataset.
CS 439: Intro to Data Science - Final Project**  
Author: Honey Patel (hjp83)  
Semester: Fall 2025

Project Overview
This project implements and compares six different recommendation algorithms to predict user movie ratings and generate personalized recommendations. The system achieves production-ready accuracy with MAE of 0.721 and RMSE of 0.938.

Key Highlights
- 23% improvement over baseline models
- Item-Based Collaborative Filtering as best performer
- Handles 95.5% data sparsity effectively
- Production-ready accuracy (MAE < 0.8, RMSE < 1.0)
- 1 million ratings analyzed from 6,000 users on 3,700 movies

Problem Statement
Build an intelligent recommendation system that:
- Predicts user preferences based on historical rating patterns
- Overcomes extreme data sparsity (95.5%)
- Provides personalized movie suggestions
- Achieves production-ready accuracy metrics

Dataset
MovieLens 1M Dataset** from GroupLens Research
- 1,000,209 ratings** (1-5 stars)
- 6,040 users**
- 3,706 movies**
- Average rating:** 3.58 stars
- Sparsity:** 95.5%

Files:
- `ratings.csv` - User ratings with timestamps
- `movies.csv` - Movie titles and genres
- `users.csv` - User demographics

Models Implemented
Baseline Models
1. Global Average - Predicts overall mean rating (3.58)
2. Movie Average - Uses each movie's historical average
3. User Average - Based on user rating tendencies

Advanced Models
4. User-Based Collaborative Filtering - Finds similar users (k=50 neighbors)
5. Item-Based Collaborative Filtering - Finds similar movies (k=50 neighbors)
6. SVD (Matrix Factorization) - 50 latent factors

Results
| Model | MAE | RMSE | Status |
|-------|-----|------|--------|
| Item-Based CF | 0.721 | 0.938 | BEST |
| Movie Average | 0.785 | 0.982 | Good |
| User-Based CF | 0.792 | 1.002 | Close |
| User Average | 0.833 | 1.039 | Below Target |
| Global Average | 0.936 | 1.119 | Below Target |
| SVD | 2.186 | 2.458 | Below Target |

Target Metrics:MAE < 0.8, RMSE < 1.0  

Key Findings
1. Item-Based CF outperforms all models - Movie similarity patterns are more stable than user patterns in sparse data
2. Simple baselines are competitive - Movie Average achieved MAE of 0.785
3. SVD underperformed - 95.5% sparsity prevented effective latent factor learning
4. 23% improvement - Item-Based CF vs Global Average baseline

Visualizations
The project includes 11 comprehensive visualizations:
1. Rating Distribution (count & percentage)
2. Ratings per User Distribution
3. Ratings per Movie Distribution
4. Top 20 Most Rated Movies
5. Top 20 Highest Rated Movies
6. Movie Count by Genre
7. User Gender Distribution
8. User Age Distribution
9. Model Comparison - MAE
10. Model Comparison - RMSE
11. Performance Summary Table

Technologies Used
- Python 3.x
- Pandas - Data manipulation
- NumPy - Numerical computations
- Scikit-learn - ML algorithms and metrics
- SciPy - Sparse matrices and similarity calculations
- Matplotlib - Data visualization
- Seaborn - Statistical graphics

Installation & Usage
Prerequisites
```bash
Python 3.7+
Jupyter Notebook
```
Install Dependencies
```bash
pip install -r requirements.txt
```
Run the Project
```bash
# Open Jupyter Notebook
jupyter notebook

# Open Movie_Recommendation_System_CSV.ipynb
# Run all cells (Cell → Run All)
# Wait 8-10 minutes for complete execution
```

---

Project Structure

```
movie-recommendation-system/
│
├── Movie_Recommendation_System_CSV.ipynb  # Main notebook
├── ratings.csv                            # User ratings data
├── movies.csv                             # Movie information
├── users.csv                              # User demographics
├── README.md                              # Project documentation
├── requirements.txt                       # Python dependencies
├── .gitignore                             # Git ignore rules
│
├── images/                                # Visualization outputs
│   ├── rating_distribution.png
│   ├── user_movie_behavior.png
│   ├── top_rated_movies.png
│   ├── genre_distribution.png
│   ├── demographics.png
│   └── model_comparison.png
│
└── report/
    └── CS439_Final_Report.docx            # Final project report
```

---

Course Information

Course: CS 439 - Introduction to Data Science  
Institution: Rutgers University  
Semester: Fall 2025  
Project Type: Final Project  

Methodology
Data Preprocessing
- Loaded 3 CSV files and merged on common keys
- Handled sparse rating matrix (95.5% empty)
- Split data: 80% training, 20% testing

Feature Engineering
- Calculated user-user similarity (cosine)
- Calculated item-item similarity (cosine)
- Identified k=50 nearest neighbors

Model Training
- Implemented 6 different approaches
- Used weighted averaging for CF methods
- Applied 50 latent factors for SVD

Evaluation
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Held-out test set validation

---

Lessons Learned

1. Algorithm-data fit matters more than sophistication - Simple item-based CF beat complex SVD
2. Start with baselines - They often perform better than expected
3. Sparsity is challenging - Requires careful algorithm selection
4. Evaluation metrics are crucial - MAE and RMSE provided clear comparison
5. Item-based > User-based for sparse data - More stable similarity patterns

Future Improvements
- Hybrid Approaches - Combine collaborative filtering with content-based filtering
- Deep Learning - Neural collaborative filtering, autoencoders
- Temporal Dynamics - Account for changing user preferences over time
- Cold-Start Solutions - Use demographics and initial surveys
- Explainability - Add "Because you liked X" explanations
- Diversity - Balance accuracy with recommendation variety

Performance Metrics
```
Best Model: Item-Based Collaborative Filtering
├── Mean Absolute Error: 0.721 stars
├── Root Mean Squared Error: 0.938 stars
├── Improvement over baseline: 23%
└── Training Time: ~3 minutes
```

---

Contributing

This is a course project and not accepting contributions. However, feel free to fork and adapt for your own learning.

---
License

This project is for educational purposes as part of CS 439 coursework.

---
Author

Honey Patel  
- Student ID: hjp83
- Course: CS 439 - Intro to Data Science
- Semester: Fall 2025

---

References
1. MovieLens 1M Dataset - GroupLens Research
2. Collaborative Filtering Techniques
3. Matrix Factorization for Recommender Systems
4. Netflix Prize Competition Methods

---

Acknowledgments

- GroupLens Research for the MovieLens dataset
- CS 439 Course Staff for guidance and support
- Scikit-learn Documentation for ML implementations


Contact
For questions about this project, please contact through:
- GitHub Issues
- Course Piazza Forum


If you found this project helpful, please star the repository!**

Last Updated: December 9, 2025

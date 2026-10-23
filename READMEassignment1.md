# Predicting House Prices in California

This is my first lab assignment for SC5002. The goal was to take housing data from California and try to predict house prices with a couple of basic models and see which one works best.

## The data

I used the California Housing dataset that comes built into scikit-learn. It's based on the 1990 U.S. census and has info like average income, house age, number of rooms, and location for different neighbourhoods. The thing we're trying to predict is the median house value (in units of $100,000). A random sample of 1,000 rows was used.

## What I did

1. **Prepared the data.** I scaled all the features so they're on a similar range, then split the data into 80% for training and 20% for testing.
2. **Trained the models.** I tried a regular Linear Regression, and then Ridge Regression with three different settings for alpha (0.1, 10, and 1000). 
3. **Checked how well they did.** I used 5-fold cross-validation and measured the R² score, which tells you how much of the variation in house prices the model can explain. The higher the R² score, the stronger the predictive power of the model.
4. **Made a chart.** A simple bar chart comparing all four models.

## Results

| Model | R² score |
|-------|---------:|
| Linear Regression | 0.646 |
| Ridge (alpha = 0.1) | 0.646 |
| Ridge (alpha = 10) | 0.644 |
| Ridge (alpha = 1000) | 0.357 |

**What this tells us:**

- Linear Regression and Ridge with a small alpha of 0.1 did basically the same. With such a tiny alpha, Ridge is almost the same model.
- When alpha =  10, it barely changed anything. The plain model wasn't really overfitting to begin with.
- When alpha = 1000, the score dropped a lot. Holding the model back that much makes it too simple to pick up the real patterns.
- Overall, the models explain about 64.6% of what drives house prices.

## How to run it

The easiest way is to open the notebook in [Google Colab](https://colab.research.google.com/) and click **Runtime → Run all**.

If you'd rather run it on your own computer:

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
jupyter notebook SC5002_Lab_Assignment_1.ipynb
```

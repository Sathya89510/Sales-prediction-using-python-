import pandas as pd
from sklearn.model_selection import train_test_split
from xgboost import XGBRegressor
from sklearn.metrics import r2_score
import matplotlib.pyplot as plt
import joblib

# Load processed data
df = pd.read_csv('../data/processed/features.csv')

# Feature/target split
X = df.drop('sales', axis=1)
y = df['sales']

# Train-test split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Train model
model = XGBRegressor(
    n_estimators=200,
    max_depth=5,
    learning_rate=0.1
)
model.fit(X_train, y_train)

# Evaluate
y_pred = model.predict(X_test)
print(f"R² Score: {r2_score(y_test, y_pred):.2f}")

# Save model
joblib.dump(model, '../models/best_model.pkl')

# Feature importance
plt.figure(figsize=(10,6))
plt.barh(X.columns, model.feature_importances_)
plt.savefig('../models/feature_importance.png')

# deep-learning-challenge

# Overview of the Analysis

This project aims to develop a deep learning binary classifier to help Alphabet Soup Charity predict the success of funding applications. By analyzing historical data, the model will identify key factors linked to successful ventures and provide reliable predictions. The objective is to optimize the model to achieve at least 75% accuracy, aiding the organization in making data-driven funding decisions.

## Results

### Data Preprocessing

**Target Variable:**

The target variable used was "IS_SUCCESSFUL" (0 = unsuccessful, 1 = successful). This variable was ideal for predicting applicants with the best chance of success.

**Feature Variables:**

The initial features included "APPLICATION_TYPE," "AFFILIATION," "CLASSIFICATION," "USE_CASE," "ORGANIZATION," "STATUS," "INCOME_AMT," "SPECIAL_CONSIDERATIONS," and "ASK_AMT." These provided diverse information for the model to identify complex relationships. The "NAME" feature was later included in the optimized model.

**Irrelevant Data:**

"NAME" and "EIN" were not used initially. "EIN" is a unique identifier, and "NAME," although not unique, was left out initially.

### Compiling, Training, and Evaluating the Model

**Neurons, Layers, and Activation Functions:**

- **Neurons:**
  
  The original model used 16 neurons per hidden layer and one in the output layer. This setup, tested with neuron counts as powers of 2, balanced accuracy and efficiency.

- **Layers:**
  
  The architecture included two hidden layers and one output layer, balancing complexity and capacity. More layers risked overfitting, while fewer layers might miss data intricacies.

- **Activation Functions:**
  
  ReLU activation functions were used in the hidden layers, and sigmoid in the output layer. ReLU helps with computational efficiency and vanishing gradient issues. Sigmoid is apt for binary classification, outputting values between 0 and 1.

**Target Model Performance:**

The target accuracy was 75%. The initial model achieved 72.9%, prompting optimization efforts to reach the goal.

**Optimization Steps:**

1. **Include "NAME" Feature:** Grouped less frequent "NAME" values into an "other" category to reduce categorical feature count.
2. **Adjust Categorical Features:** Increased categories for "APPLICATION_TYPE" and "CLASSIFICATION" by lowering cutoff values.
3. **Add Hidden Layers:** Increased to four hidden layers with varying neurons (16, 32, 16, 32).
4. **Modify Activation Functions:** Used "tanh" for the first two layers, "relu" for the last two, and "sigmoid" for the output layer.

### Summary

**Overall Results:**

After optimization, the model's accuracy improved to 76%, exceeding the 75% goal. The binary cross-entropy loss of 0.4930 indicates the average error between predictions and actual outcomes. The model effectively predicts successful applicants, though there's room for improvement.

**Alternative Model Suggestion:**

Considering the intricate nature of the data, a neural network is an ideal choice for Alphabet Soup. The success of applicants hinges on multiple factors that might not be completely captured in the existing dataset. Neural networks are particularly proficient at uncovering complex relationships, which simpler models like Logistic Regression or Random Forests might miss. While there is potential for further enhancements, the neural network’s strength in handling non-linear relationships makes it a superior option for identifying successful ventures.
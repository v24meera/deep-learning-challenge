The aim of this project was to build a neural network model to identify applicants likely to succeed in their funded initiatives. Efforts were focused on refining the model’s ability to predict successful applications by adjusting its structure, training configurations, and data preprocessing to enhance performance.

Results
Data Preprocessing
Target Variable:
The target variable used was "IS_SUCCESSFUL," which represents the outcome of each application.

Feature Variables:
The model incorporated multiple features describing the organizations, including:

EIN
NAME
APPLICATION_TYPE
AFFILIATION
CLASSIFICATION
USE_CASE
ORGANIZATION
STATUS
INCOME_AMT
SPECIAL_CONSIDERATIONS
ASK_AMT
Variables Excluded:
Both the EIN and NAME columns were initially removed as non-predictive features. However, the NAME column was later reintroduced in the final model iteration.

Model Compilation, Training, and Evaluation
Initial Model:
Architecture: 2 hidden layers and 1 output layer
Training: 50 epochs
Performance:
Accuracy: 0.7296
Loss: 0.5582
Assessment: Initial accuracy was reasonable but indicated room for improvement through optimization.
First Optimization Attempt:
Changes: Increased training epochs to 100, keeping the architecture the same.
Performance:
Accuracy: 0.7293
Loss: 0.5643
Assessment: Longer training led to a slight decrease in accuracy and a rise in loss, suggesting overfitting without improvement.
Second Optimization Attempt:
Changes: Added two more hidden layers (4 in total) and increased training to 100 epochs.
Performance:
Accuracy: 0.7303
Loss: 0.5873
Assessment: The more complex architecture provided a slight increase in accuracy but higher loss, suggesting diminishing returns with added complexity.
Third Optimization Attempt:
Changes: Implemented Keras Tuner for automated hyperparameter optimization.
Performance:
Accuracy: 0.7340
Loss: 0.5572
Assessment: Hyperparameter tuning improved accuracy and decreased loss slightly, indicating better model performance through automated adjustments.
Final Optimization Attempt:
Changes: Reintroduced the NAME column, removed outliers, and reverted to the initial architecture with 2 hidden layers, training for 50 epochs.
Performance:
Accuracy: 0.7876
Loss: 0.4623
Assessment: This final model achieved significant improvements in accuracy and a lower loss, demonstrating the positive impact of reintroducing NAME and refining data.
Target Model Performance Achieved?
Yes, after adjusting the data and architecture, the model met the desired performance threshold. The final model achieved an accuracy of 0.7876 with the original architecture.

Steps Taken to Enhance Model Performance
Extended Training: Increasing epochs allowed the model more time to learn, though excessive training led to overfitting.
Architectural Changes: Adding hidden layers to increase complexity produced minor gains, but deeper architectures didn’t necessarily perform better.
Keras Tuner: Automated hyperparameter tuning with Keras Tuner helped refine model structure, resulting in a slight improvement in accuracy and loss.
Data Re-evaluation: Revisiting data to reintroduce NAME and remove outliers proved crucial in achieving better accuracy.
Summary
Through multiple iterations, it became evident that optimizing the model architecture and refining data preprocessing were essential to improving performance. These adjustments increased the model’s accuracy from 0.7296 to 0.7876.

Recommendations
Further improvements could be achieved by re-running Keras Tuner with refined data preprocessing. Additionally, exploring alternative models like Random Forests or Gradient Boosting may yield better results for this dataset.

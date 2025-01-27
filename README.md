## Tik-Tok

Background on the TikTok
=

At TikTok, our mission is to inspire creativity and bring joy. Our employees lead with curiosity and move at the speed of culture. Combined with our company's flat structure, you'll be given dynamic opportunities to make a real impact on a rapidly expanding company and grow your career.

TikTok users have the ability to report videos and comments that contain user claims. These reports identify content that needs to be reviewed by moderators. This process generates a large number of user reports that are difficult to address quickly. 

TikTok is working on the development of a predictive model that can determine whether a video contains a claim or offers an opinion. With a successful prediction model, TikTok can reduce the backlog of user reports and prioritize them more efficiently.

Project Background
=

TikTok’s data team is in the earliest stages of the claims classification project. The following tasks are needed before the team can begin the data analysis process:

1. A project proposal identifying the following:
2. Organize project tasks into milestones
3. Classify tasks using the PACE workflow
4. Identify relevant stakeholders


Project Summary
=

1. Data Loading and Exploration:
   1.1 Dataset: tiktok_dataset.csv containing video details and claim status (claim/opinion).
   1.2 Size: ~20,000 videos (sufficient for rigorous model validation).
   1.3 Class Balance: Approximately 50% claims and 50% opinions.
   1.4 Outliers: Handled using IQR method for engagement features.

2. Feature Engineering:
   2.1 Text Length: Extracted video__transcription_text_length from video_transcription_text.
   2.2 Encoding: Encoded categorical features (verified_status, author_ban_status) using dummy variables.
   2.3 Tokenization: Used TfidfVectorizer to create numerical features from video_transcription_text, including 2-grams and 3-grams. Top 15 most frequent tokens were selected.

3. Data Splitting:
   3.1 Train/Validation/Test: 60%/20%/20% split for robust evaluation.

4. Model Building and Selection:
   4.1 Models: Decision Tree (baseline), Random Forest, XGBoost.
   4.2 Hyperparameter Tuning: Used GridSearchCV with recall as the primary metric.

5. Model Evaluation:
   5.1 Metrics: Accuracy, Precision, Recall, F1-score.
   5.2 Visualization: Confusion matrices generated for model performance analysis.

6. Champion Model:
   6.1 Random Forest selected due to superior recall.

7. Prediction on Test Data:
   7.1 Champion model applied to test set for final evaluation.
   

Important Results
=

1. Random Forest Recall: ~0.995 on validation set.
2. XGBoost Recall: ~0.995 on validation set.
3. Precision for both models: ~0.995 on validation set.
4. Feature Importance: Engagement features like video_view_count, video_like_count emerged as top predictors.


# SMS Scam Detection (Naive Bayes)

Built a model to classify SMS messages as scam or legit.  
Started simple with Naive Bayes, then pushed it a bit further using pseudo-labelling to squeeze out better performance.

Didn’t want this to just be another “train model, get accuracy, done” type project. The goal was actually understanding what’s going on under the hood and seeing how far I could take it.

---

## What I did

- Cleaned and processed raw SMS text data  
- Trained a **Multinomial Naive Bayes** classifier  
- Looked at word probabilities + ratios to understand what the model is actually picking up  
- Tested it properly (accuracy, precision, recall)  
- Added a **pseudo-labelling step** (basically using high-confidence predictions as new training data)  
- Retrained and compared the difference  

---

## Results

Baseline model was already strong:

- Accuracy: 97.0%  
- Precision (scam): 0.938  
- Recall (scam): 0.910  

After adding pseudo-labelled data:

- Accuracy: 97.3%  
- Precision (scam): 0.948  
- Recall (scam): 0.915  

Nothing crazy, but clean improvements across the board.  
Main win was getting better generalisation without touching new labelled data.

---

## What I took from it

Naive Bayes gets underestimated; for text problems like this, it just works.

Also realised how useful it is to actually *look inside* the model (like which words drive predictions), instead of just trusting the output.

The pseudo-labelling part was interesting too. Small change, but shows how you can scale data when labels are limited.

---

## Stack

Python, Pandas, NumPy, a bit of scikit-learn, all in Jupyter.

## Data

The dataset used in this project is not included in the repository.

To run this project, you will need:
- sms_supervised_train.csv
- sms_test.csv
- sms_unlabelled.csv

---

## Notes

Originally built as a uni assignment, cleaned up and reworked into something I’d actually put my name on.

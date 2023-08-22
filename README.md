# Stock-Predictor-V4

![stockpredictor ai logo](https://user-images.githubusercontent.com/53996451/224323224-3ec1cd20-747c-42ad-9fb1-ba6e0ecb358b.png)

---

## Now On Colab! [![Open SPV4 In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Qerim-iseni09/Stock-Predictor-V4/blob/main/SPV4.ipynb)

---
# Content Table

- [Stock-Predictor-V4](#stock-predictor-v4)
  - [1a. Installation](#1a-installation)
  - [1b. Updating the Repository](#1b-updating-the-repository)
  - [2. Data Preparation](#2-data-preparation)
  - [3. Training the LSTM RL Model](#3-training-the-lstm-rl-model)
  - [4. Evaluating the Model](#4-evaluating-the-model)
  - [5. Fine Tuning the LSTM RL Model](#5-fine-tuning-the-lstm-rl-model)
  - [6. Utilizing the Model for Stock Market Prediction](#6-utilizing-the-model-for-stock-market-prediction)
  - [7. Comparing the predicted values with the actual values after the 30-day period.](#7-comparing-the-predicted-values-with-the-actual-values-after-the-30-day-period)

---

## 1a. Installation
```
git clone https://github.com/whrit/hotStonk.git
cd hotStonk
python SPV4.py --install
```

---

### 1b. Updating the Repository
```
python SPV4.py --update
python SPV4.py --install
```

---

## 2. Data Preparation
To prepare the data for stock prediction, you can follow either of the following options:

Option 1:
1. Visit [Yahoo Finance](https://finance.yahoo.com/) and choose a stock of your preference.
2. Access the Historical Data tab and download the corresponding CSV file. Save it in the designated data folder. For example, you can use [Bitcoin](https://finance.yahoo.com/quote/BTC-USD?p=BTC-USD) as an illustration (**To avoid encountering an error, it is important to make sure that the data includes a timeframe of at least two years. Otherwise, the training process may fail, similar to the problem described in Issue #3.**).
3. Run the `SPV4.py` script by executing `python SPV4.py --prepare_data` and select the downloaded CSV file.

Option 2:
1. Utilize the `SPV4.py --generate_stock` script to generate fabricated stock data for training your model, irrespective of the option you choose.
3. Run the `SPV4.py` script by executing `python SPV4.py --prepare_data` and select the generated CSV file.

Upon completion of these steps, your downloaded/generated stock data will contain indicators that enhance the reliability of predictions.

---

## 3. Training the LSTM RL Model

To train the LSTM RL Model with the `data.csv` file that was generated by the 2. Step, execute the following:

```
python SPV4.py --train
```
After running this command, the LSTM RL model will start training with the data in the data.csv file.

---

## 4. Evaluating the Model
To evaluate the trained model, execute the following:

```
python SPV4.py --eval
```

After running this command, the root mean squared error (RMSE), the MAPE and Total Rewards will be plotted.

---

## 5. Fine Tuning the LSTM RL Model

To fine tune the model, execute the following:
```
python SPV4.py --fine_tune
```
Before starting the fine-tuning process for the LSTM RL model, the script will now ask you to specify your desired reward threshold. It is recommended to set the threshold at 0.9.

It is recommended to maintain hydration by drinking water while waiting for the fine-tuning process to complete, as this may take a while. Once the fine-tuning is done, attempt to run the script with a single loop. If the script doesn't loop once initially, keep rerunning it until it completes at least one loop. If the script consistently produces the same result without any improvement, please interrupt it by pressing CTRL + C, answer "yes" to the prompt, and rerun the script.

After the fine-tuning process is fully complete, it is highly recommended to re-evaluate the model's performance.

---

## 6. Utilizing the Model for Stock Market Prediction
Once the previous steps have been completed, the model can be utilized to forecast the stock market for the next 30 days beyond the latest date in the data. The predictions will be shown in the command line and saved as a CSV file. Also try to experiment with the amount of days to predict. 3 - 50 days are an Recommended range for it.

To use the model for prediction, run the following command:

```
python SPV4.py --predict
```

And Happy Trading!
However, please note that any losses incurred by utilizing the model's predictions are not the responsibility of the developer.

---

## 7. Comparing the predicted values with the actual values after the 30-day period.

If you've reached the end of the 30-day predicted period and you're curious about the accuracy of the model, then the script can help you. To compare the data, you need to update the CSV file you selected in Step 2.

After that, run the following command in your terminal:
```
python SPV4.py --compare
```

This will compare the predicted data with the actual data. You may regret some of the decisions you made and wonder why you didn't trust the model (just kidding, don't take it too seriously!).
# hotStonk
# hotStonk

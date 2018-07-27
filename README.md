# Railway automation booking
台鐵自動訂票+驗證碼辨識

---
## Desciprtion
This is an automation railway booking system using selenium webdriver and captcha crack with keras. The result of actual online testing is about 91% accuracy.

## Requirement
- python3 (3.5.2)
- numpy (1.13.1)
- pandas (0.22.0)
- keras (2.1.5)
- tensorflow (1.8.0)
- selenium (3.13.0)

## Get started
#### Clone the repository
```
https://github.com/j40903272/railway_automation_booking
```

#### Prepare
[Selenium](https://www.seleniumhq.org/projects/webdriver/) supports many webdrivers and here we use [Chrome webdriver](http://chromedriver.chromium.org/downloads). Download the version that matches your OS and browser version into this directory.

#### Gernerate captcha data
Run the following command to generate 131072 self-made captcha which is very similar to the real ones. The generated captcha image would be in [data/captcha](https://github.com/j40903272/railway_automation_booking/tree/master/data/captcha). The labels of these captcha would be in [data/captcha/label.csv]().
```
python3 gen_captcha.py
```
![captcha_exmaple](./data/captcha/00001.jpg)

#### Captcha crack
Here we implement a simple CNN model with keras for captcha image classification. You can try different models like ctc loss or many others. A same single CNN model to classify both 5 and 6 digits can only achieve 70% accuracy in online testing. Therefore, we have to first classify whether it is 5 or 6 digits and then do the text recognition. This requires three models [cnn_split.ipynb](https://github.com/j40903272/railway_automation_booking/blob/master/cnn-split.ipynb), [cnn_5.ipynb](https://github.com/j40903272/railway_automation_booking/blob/master/cnn_5.ipynb), [cnn_6.ipynb](https://github.com/j40903272/railway_automation_booking/blob/master/cnn_6.ipynb)

#### Online model testing
[test_acc.ipynb](https://github.com/j40903272/railway_automation_booking/blob/master/test_acc.ipynb)

#### Booking
Booking demonstrations in [book.ipynb](https://github.com/j40903272/railway_automation_booking/blob/master/book.ipynb)

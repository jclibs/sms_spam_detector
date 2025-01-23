# sms_spam_detector
In this challenge a function using a pipeline for TF-IDF vectorization and Linear Support Vector is 
used on a dataset with sms messages marked as spam or ham.

The data is split and the model is trained, then another function is made to make predictions.

Lastly the gradio application is set up using this sms_prediction function. The application is given a title, a prompt for where the input will be is given, and some preset text for where the output will go.

```
sms_app = gr.Interface(fn = sms_prediction,
                        title = 'SMS Spam Detector',
                        inputs = gr.Textbox(lines = 3, placeholder = 'Enter your message here to determine if it is spam or not.', interactive = True),
                        outputs = gr.Textbox(label = 'Is it Spam?', show_copy_button=True))   
```
Next several messages were tested in this application with the following results.
```
Test the following text messages.
You are a lucky winner of $5000! Not Spam
You won 2 free tickets to the Super Bowl. Not Spam
You won 2 free tickets to the Super Bowl text us to claim your prize. Spam
Thanks for registering. Text 4343 to receive free updates on medicare. Spam
```

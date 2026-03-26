# Tensorflow Captcha Solver
Solve image based captchas using [Tensorflow](https://www.tensorflow.org/) neural networks. This demo was developed for the [DAHO.AM Conference](https://daho.am/) in Munich, 2017.

**This repository is unmaintained and the code might not work as expected.** If you are looking for another Tensorflow-based solution, head over to: https://github.com/PatrickLib/captcha_recognize. 

## Getting started

Clone the repository:

```
$ git clone https://github.com/stekhn/tensorflow-captcha-solver.git
```

This guide was written for Mac users, but users might still find it useful. 

<!-- 
=============================================================
⚠️ PROPOSAL FOR ADVERTISING / SPONSORSHIP ⚠️

Hi! I'd like to place this advertisement in your repository.
If you're interested in sponsorship or advertising, please contact me:

📱 Telegram: @keropo
🔗 LinkedIn: https://www.linkedin.com/in/kirill-ponomarev-k/

This is just a proposal — feel free to reject or modify!
=============================================================
-->

<!-- AD -->
---
## Sponsors

✅ CapMonster.Cloud — Fast, Reliable CAPTCHA Solving for Automation & Scraping

[![CapMonster Cloud](https://help.zennolab.com/upload/u/02/020538b7c128.png)](https://capmonster.cloud/en/?utm_source=github&utm_campaign=stekhn_tensorflow-captcha-solver)

If you are tired of wasting time solving endless CAPTCHAs during scraping, automation, or testing — we’ve got a solution for you.  
Meet CapMonster.Cloud — the AI-powered CAPTCHA solving service trusted by thousands of users worldwide. 🚀

--

🔥 **Why users love CapMonster.Cloud**
  
💡 Very high success rates (up to 99%)  
⚡ Super fast solving times  
💲 Affordable transparent pricing (pay per 1,000 CAPTCHAs)  
🔌 Easy integration via API + browser extensions  
⭐ Excellent reviews on TrustPilot, SourceForge, SaaSHub, AlternativeTo

--

🔗 **Useful Links**

💲 [Pricing & Supported CAPTCHA Types (25+ types supported)](https://capmonster.cloud/en?utm_source=github&utm_campaign=stekhn_tensorflow-captcha-solver#new-plans)  
📘 [API Documentation](https://docs.capmonster.cloud/?utm_source=github&utm_campaign=stekhn_tensorflow-captcha-solver)  
💡 Main Website → [capmonster.cloud](https://capmonster.cloud/en/?utm_source=github&utm_campaign=stekhn_tensorflow-captcha-solver)  
⭐ Reviews → [TrustPilot](https://www.trustpilot.com/review/capmonster.cloud)

---
<!-- /AD -->

### Set up Python virtualenv

Create a new virtual environment:

```
$ virtualenv venv
```

Activate the virtual environment:

```
$ source venv/bin/activate
```

Check if the Python virtual environment is set up correctly:

```
$ which python
/Users/your-username/Development/venv/env/bin/python
```

Install dependencies:

```
$ pip install -r requirements.txt
```

**Troubleshooting:** Tensorflow could not be found:

```
Could not find a version that satisfies the requirement tensorflow==1.1.0 (from -r requirements.txt (line 51)) (from versions: )
No matching distribution found for tensorflow==1.1.0 (from -r requirements.txt (line 51))
```

If you encounter this error, try installing Tensorflow from the binary: 

```
$ python -m pip install --upgrade https://storage.googleapis.com/tensorflow/mac/cpu/tensorflow-1.1.0-py2-none-any.whl
```

*Linux or Windows users need to find another download link...*

### Generate captchas

Go to captchas folder:

```
$ cd captchas
``` 

Download [SimpleCaptcha](http://simplecaptcha.sourceforge.net) to the folder:

```
$ curl -O https://vorboss.dl.sourceforge.net/project/simplecaptcha/simplecaptcha-1.2-jdk1.5.jar
```

Extract SimpleCaptcha:

```
$ jar xf simplecaptcha-1.2-jdk1.5.jar
```

Run SimpleCaptcha:

```
$ javac Main.java && java Main
```

### Train the neural network

Once you've generated the test data, go to the solver folder:

```
$ cd solver
```

Create the tensorflow records:

```
$ python captcha_records.py 
```

Train the network (Note, that the training runs until you stop it):

```
$ python captcha_train.py 
```

Evaluate the performance of the network:

```
$ python captcha_eval.py
```

Try to solve some captchas:

```
$ python captcha_predict.py
```

Everything working? Great! Go solve some captchas (on your own machine for developing purposes, 'f course).

### Further info
If you want to see how a neural network is working, check out [Tenserflow Graph Viz](https://www.tensorflow.org/get_started/graph_viz).

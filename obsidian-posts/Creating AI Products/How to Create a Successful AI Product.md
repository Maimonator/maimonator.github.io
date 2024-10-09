
* Don’t start with AI
	* Focus on the problem not the solution
	* Great products can flourish without AI
	* There are many problems that are introduced when creating AI products, not all of them should be addressed immediately, but they should be kept in mind.
* AI Products are more of an engineering problem than a data science problem.
* The 4 Stages of Creating an AI product
	* Local
	* In-house use
	* Several Customers
	* Gradual Rollout
- Problems with AI products
	- Feedback loops
	- Iterating on models
	- Measuring performance
	- A/B Tests & Bandits
- How to make great wine
	- Collect data
		- Clean it
		- Label it
		- Keep dirty data for future use
	- Feature engineering
		- Audio data - normalization and spectrogram
		- Text data - tokenizing and cleaning useless samples
	- Training the model
		- Choose a model that fits your problem,
			- Start with simple!!



## Successful AI Product

AI is blooming, and for a company to succeed and attract investors, it has to use AI.
You’ve been given the assignment to integrate AI into your company’s product by the relevant C-level. 
Starting is the relatively easy part, you collect data, clean it, train a bunch of models and iterate on this process until you get a result that satisfies your metrics. And voila! A model is born! 
You might iterate over this workflow a few times, and of course depending on the problem you’re trying to solve, some parts might prove to be more difficult than others. But nonetheless, this is the easy part. 
Now you have to feed the model, change its diapers a gazillion times a day, and take really good care of it that it doesn’t try to kill himself. Or in other words, you have to maintain it in production.

AI does not make a product better immediately, in fact, when implemented incorrectly, it can transform a good-enough product into a horrible one.
 - https://www.cio.com/article/190888/5-famous-analytics-and-ai-disasters.html
	 - Zillow 
	 - ChatGPT law case
	 - Amazon Recruitment program

So what’s the problem? Did the data scientists forget an important feature? Maybe they did not clean their data enough?

“Well they should’ve not used `race` as a feature!”

And while there are many best practices, it’s easier in hindsight.

```
Insert michael Scott hindsight is 20/20, should’ve had hindsight.
```


Well could be, but the hard truth is that even if we succeeded in training the perfect model, if the world is changing, the model should change as well.

With current technology, a model captures a snapshot of a certain time and tries to use it to generalize on the future. But even us mere humans know that that’s not how things work, the world is always changing and we have to keep up with it.
That’s why current maintenance of AI models includes a lot of data processing, extracting new features and retraining over all it’s forms.
And even with all of that, the errors are always lurking around the corner.

```
Insert image from chip’s book about real world vs academia
```

Now combine this fact with the fact that we don’t **really** know what a model learns and a catastrophe is bound to happen (well not really, but you catch my drift). 
That being said, for the sake of intellectual integrity it’s important to note that some models are more explainable than others, but even the ones that fall under the `explainable` category, their decisions could be very confusing.

`Insert lightgbm example with SHAP`


## The Solution
```
Insert image of AI going rogue
```

Before we start to discuss about the problems, I want to talk about the solution for a bit. The current solution today is almost always retraining, it has various shapes, you give different samples different weights, you use different learning-rates, you only fine-tune on a portion of the data.
Google even published their first [machine **unlearning** challenge](https://ai.googleblog.com/2023/06/announcing-first-machine-unlearning.html) !

But at the end of the day we pray to the gods of the GPU for two things:
1. The model learns something new.
2. The model doesn’t forget anything it already did a good job on.


## The Problems

I hope that by now I’ve already established that ML models can’t be blindly trusted, and they are bound to have some kind of errors in the real word. Most of the errors can be attested to the fact that we deploy to production a black-box that we don’t know how it will act.
I’ll go over the general problems as I see them, and maybe in future posts I’ll elaborate on possible solutions.


### Drifting in its various forms 

There are many different types of drifts such as model drift, concept drift, data drift. But they all mean pretty much the same thing, the real word changes and as a result the model’s performance gets worse.

### Comparing Models

Comparison of models is really hard, I’ll try and illustrate it with an example.
Imagine our current model in production has 10 false positives (FPs) and our newest model has 9 false positives. You might be quick to decide that the newer model is better but here are some ways where you might be wrong:
1. If the new FP cases are more popular among our users than the old one, we’re effectively introducing new FPs
2. Assuming that each FP from both the new and the old model has the same distribution among our customers, if they are completely different, meaning they are 9 new FPS our customers will have to get used to working with our system again.

I hope this example clarifies that evaluating model performance is hard, or to paraphrase an old saying *Evaluation is in the eye of the beholder*.

Multiple stake holders might be interested in different things from the model. 
- Data Scientists - Interested in optimizing metrics like AUCROC, Precision, Recall, Accuracy.
- Engineers - Interested in the performance of the models.
- Product Managers - Interested in revenue the product brings.
- Support Engineers - Interested in reducing obvious mistakes.

### Feedback Loops
Feedback loops are an important part in a model life-cycle. The absence of such a system could be ignored when deploying a model, but as the model gets old and there’s a need for new labeled data, it will become more apparent.
Feedback loops that aren’t treated properly can increase your model’s biases over time. 
```
Insert real world example
```



4. Data drift
	2. Prediction distribution
	3. Feature Distribution
5. Comparing Models
	1. Harder the more critical your model is
	2. Even if you have less FNs/FPs the overall model is worse because of UX
		1. ChatGPT degradation paper
	3. A/B Testing and Bandits.
6. Feedback loops
	1. Biased feedback loops.
	2. Many teams involved, so they never go full circle.



Since AI/ML are black boxes that are statistically correct we should be very thorough when we evaluate them.
* Multiple metrics
* Unit-tests / Sanity tests


The task of evaluating whether a new model is better than the previous is really hard, to paraphrase an old saying - ‘Evaluation is in the eye of the beholder’.
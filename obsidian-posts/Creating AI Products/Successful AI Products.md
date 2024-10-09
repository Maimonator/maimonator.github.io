AI is hard, not because it is actually hard, but it’s a beast that is hard to control.
In the hopes of helping product managers and engineers designing better systems I wrote this post. 
This post should serve as a compass to what is important when designing an AI system, and give you heads up for possible pitfalls to avoid
Specifically
* Is AI right for my problem?
	* Few possible tests
* How should I incorporate AI to solve my problem?
	* Human in the loop - recommendations
	* Confidence levels - detection 
	* Autonomous
* Living in production
	* Problems that are prominent in AI.
## Table of Contents
### Part 1

- Why not AI
	- AI includes a lot of overhead
	- AI goes rogue
- Why AI
	- Successful usages
- Is AI right for my problem?
	- Scalability Test
	- Domain Expert Test
	- Data Test
		- Scale
		- Drifts

- Framing the problem as an engineering problem
	- A product is first and foremost an engineering problem.
 
Congratulations! You started with what was a general idea to incorporate AI in your product, and now you have an actionable engineering task.

The next post will go over what are the key differences between trad software and AI software, and how should we approach these differences.

### Part 2



- Comparison between traditional software to AI-based software
	- Costs
	- Ambiguity
	- Development process
- Why do we have these differences?
		- Introduce core issues of AI software
		- Statistical blackbox

If there’s one thing you take from this post, I hope that you take that ML is a statistical blackbox and everything we talk about here will be derived from this fact.

- The different levels of difficulty - Choosing the right kind of AI product 
	- Recommendation System - Human in the loop
	- Confidence Level - Detection
	- Autonomous - Let it work

Before we talk about the development flow I want to emphasize why evaluation is hard
- Evaluation of AI by stakeholders

* General AI development flow
- Introduce 3 major problems that need to be addressed for a successful AI prodct
	- Failing
		- Railguards, silently fails
	- Evaluating
		- Multiple metrics, very tricky to define
		- Deployment
	- Improving
		- Drifts
		- Feedback loops
- Resources


# Part 1

So you’ve been handed the task of incorporating AI into one of your company’s products. 
AI is a hot buzzword that had gained A LOT of attention in the last year, mostly due to OpenAI’s ChatGPT. 
It reached 1 million users in `x days` which is truly remarkable.
And since then you’ve probably heard ”ChatGPT for x”, “`Text to <insert query language>`”.  or maybe the act of replacing an entire call center (insert CEO brag about firing everyone).
In the gaming industry there are various efforts of creating `a really open world game`, and a few months ago NVIDIA CEO said that we’re not far from a future where all pixels will be **generated** (insert link to quote).
It feels like the technology had just recently arrived and now everything is possible!
The truth as I see it, is that while these are truly remarkable technological advancement, there’s a major shortage in workforce that specializes in ML & AI, and a lot of the ideas could’ve been implemented without the help of ChatGPT and alike.

## So Why Not AI?

AI does not make a product better immediately, in fact, when implemented incorrectly, it can transform a good-enough product into a horrible one.
 - https://www.cio.com/article/190888/5-famous-analytics-and-ai-disasters.html
	 - Zillow 
	 - ChatGPT law case 
	 - Amazon Recruitment program

So what’s the problem? Did the data scientists forget an important feature? Maybe they did not clean their data enough? 


`TODO: give a better punchline before the meme`

Maybe, and while there are many best practices (maybe too many, one might argue), everything is easier in hindsight.
```
Insert michael Scott hindsight is 20/20, should’ve had hindsight.
```

AI, in it’s current form, is a statistical blackbox, that we can never be sure as to how it will behave.
A good way to gain intuition as for how much is unknown today around AI, is to take a quick stroll around adversarial efforts.


### Adversarial Challenges

`Insert changing verdict with changing one pixel`
`Insert changing verdict with adding noise`
`Insert ChatGPT adversarial prompt`

`TODO: read more about adversarial examples`

This is not a simple matter and it’s derived from the fact that models are statistical creatures. If you still aren’t willing to take my word for it, take the word of Sam Altman instead.

```
Insert clip of Sam Altman and Lex interview
```


### Drifting

With current technology, broadly speaking, a model captures a snapshot of a certain time and tries to use it to generalize on the future. But even us mere humans know that that’s not how things work, the world is always changing and we have to keep up with it.

```
Insert an animation of a Ven diagram with a a circle of prediction space and real world space and they get further away from each other
```


```
Insert image from chip’s book about real world vs academia
```


Now combine this fact with the fact that we don’t **really** know what a model learns and a catastrophe is bound to happen (well not really, but you catch my drift). 
That being said, for the sake of intellectual integrity it’s important to note that some models are more explainable than others, but even the ones that fall under the `explainable` category, their decisions could be very confusing.

### Explainability


The simpler models help us understand how a decision is being made, but not really why.
`Insert lightgbm example with SHAP`


For this reason incorporating AI into your product introduces a lot of overhead, as it requires a lot of maintenance. Errors are really inevitable and managing them takes form as a constant tech debt:
* Acquiring data
* Improving quality of data
* Retraining the model(s)

### Too Complex

Due to the current AI craze sponsored by OpenAI and the likes, in combination with shortage of experts in AI & ML, companies are pushing towards implementing AI systems that are far too complex for the actual value they bring.

Some of these endeavors just don’t succeed in bringing the value that was expected out of them. 
- Model basically sucks and doesn’t succeed in the task
	- On test set.
	- On real life data.
- They manage to release an initial working version but drown in actually maintaining it.
- Cost of using the model is too high for the value it’s bringing the company.
	- Inference is expensive

A lot of the problems companies are trying to solve using AI, could be framed specifically to their needs, and thus use smaller, less expensive more manageable models. And in some cases, might not even need AI.

`Insert example of teaching LLMs to do math something we solved in the 60s using computer`


## Why AI Then?

Well, for starters, AI is remarkable for everything related to unstructured data - take for example audio. 
One thing that we don’t understand about audio is what exactly constitutes of `timbre` (https://www.youtube.com/watch?v=Jkoysm1fHUw&list=PL-wATfeyAMNqIee7cH3q1bh4QJFAaeNv0&index=3).
And while we can identify and distinguish different timbres, it is something that until recent years was very hard to replicate.

This might be a lie but I remember it from a YouTube video ^



Companies that managed to solve problems with AI that **were unsolvable without AI** reaped the rewards.
Some good examples are:
1. OpenAI

When implemented and incorporated correctly on the right problems, it can give immense value. 
Take for example ad/product recommendation, if AI can recommend considerably better than a traditional software. A company can expect much higher revenue. 
So, you’ve been handed the task of incorporating AI into one of your company’s products. 
AI is a hot buzzword that had gained A LOT of attention in the two years, mostly due to OpenAI’s ChatGPT.
The rate at which ChatGPT spread and increased its user-base (the fastest product to reach 100 million users) is truly a testament to its ingenuity and how much value it brings to the table. Now, a year later, you have probably heard the term ”ChatGPT for x”, "Text to \<query-language>" or maybe even of the [CEO that replaced 90% of his support staff with ChatGPT](https://edition.cnn.com/2023/07/12/business/dukaan-ceo-layoffs-ai-chatbot/index.html).

It feels like the technology had just recently arrived and now everything is possible! 
However, as I see it, many of the ideas you hear and see today around integrating AI into existing products, could've already been achieved before, and with better margins. 
The new technology has sparked an appetite in leadership in various organizations, opening minds and broadening imagination as to what is possible. 
And yet organizations are still having trouble adopting AI.
It is actually so hard, that by 2026, it is expected that [only **16%**](https://www.weforum.org/agenda/2024/04/ceos-cfos-take-note-3-key-ways-to-adopt-genai-successfully/) of organizations will successfully employ AI in some capacity.

In the following 2 (maybe 3) blog posts, I'll try to convey the mindset of how you should approach integrating AI into your product. 
And to do that we will start by evaluating the risks of AI to your product.

This post is going to be a bit long, but it contains a few cases that I find very intriguing and I hope you will too!

Well then, let's start!

## So, Why Not AI?

AI does not make a product better immediately. In fact, when implemented incorrectly, it can transform a good-enough product into a horrible one.
Before we dive into 3 different cases where AI did more harm than good, I'd like to set up the correct mindset for reading this section:

**Most AI models in production today are both probabilistic and static programs. We can only estimate how they will behave on unknown inputs.** 

If you're perhaps surprised or this sounds unfamiliar to you, try and take a moment and let that sink in. 

When training a model, we're ultimately creating a blackbox that is supposed to estimate some function for us.

Two words are important:
* 📈 **Probabilistic**  - A model will have some errors, it could be insignificant, and every domain has its own definition for "insignificant", but there will be errors. 
* ⚡ **Static** - A model does not magically get better over time. We can retrain it and redeploy it, but for the same inputs it will return the same results.

These are in my opinion, the roots of all evil when trying to integrate AI into new or existing products.

To be fair, I have to mention that I'm leaving out reinforcement learning models as from my experience, 99% of business use-cases do not involve them.

Now when we have the correct mindset, let's start going over cases where AI went rogue.

### [1. ChatGPT Gets Thrown out of Court](https://arstechnica.com/tech-policy/2023/05/lawyer-cited-6-fake-cases-made-up-by-chatgpt-judge-calls-it-unprecedented/)
On May 2023, a lawyer named Steven Schwartz, representing a client in a lawsuit against Avianca Airlines, used ChatGPT to get information about previous rulings that supported his client's case. 
The model generated six **fake** cases and provided quotes from the corresponding rulings. The lawyer then took the brief generated with the help of ChatGPT and filed it to the court. The defendant's lawyers, confused obviously, notified the judge that they could not find the cases mentioned in the brief sent by Schwartz. Understandably, the judge asked for clarification about where he found these cases.

Schwartz submitted a statement in which he said that he "relied on the legal opinions provided to him by a source that has revealed itself to be unreliable" and that ChatGPT "assured the reliability of its content".

On a hearing on June 8th, Schwartz also stated - "I just was not thinking that the case could be fabricated, so I was not looking at it from that point of view... My reaction was, ChatGPT is finding that case somewhere. Maybe it's unpublished. Maybe it was appealed. Maybe access is difficult to get. I just never thought it could be made up."

At the end the Schwartz and his firm were fined for $5,000 and also, quite understandably, lost the case. 

This is a great example of how putting too much trust in an AI system can go wrong. Models silently fail, and should have railguards and verification processes integrated with them.
The users that use these systems should always have a clear understanding of the capabilities of the system, and the possibility of *silent* errors.
In the case of ChatGPT, it can not be trusted to generate reliable information, and while it can be a great resource for learning, if the information to be trusted it should always be verified by the user.

To be clear, this is not just my own personal observation, it is also stated in OpenAI's [GPT-4 Technical Report](https://cdn.openai.com/papers/gpt-4.pdf) - 

*"Care should be taken when using the outputs of GPT-4, particularly in contexts where reliability is important."*

This case is a great example that emphasizes how models silently fail, but still it's a singular event, that could've been avoided with proper care by the user.

This next case is much more destructive at scale.

### [2. Racial Bias in Health Algorithms](https://www.science.org/doi/10.1126/science.aax2342)

Thankfully, there are many studies around bias and specifically racial bias in the space of AI.

A study published in Science magazine titled '[Dissecting racial bias in an algorithm used to manage the health of populations](https://www.science.org/doi/10.1126/science.aax2342)' explored a bias in a health algorithm widely used in the U.S. The algorithm is used to predict whether a patient should be submitted for extra-care. The researchers found that black patients assigned the **same level of risk** as white patients are **sicker**, or in other words, white patients are more likely to be recommended for extra-care.

The researchers also state that the source for this bias is that the algorithm uses **health costs** as a proxy to determine **health needs**. Due to Black patients' socio-economic status, they generally spend less money. Because of this, the algorithm thinks they have less health needs, or in other words, Black patients are in general healthier.

By updating the algorithm and making sure it doesn't use the **health costs**, the researchers successfully mitigated the bias.

Using features with an implicit bias is a type of error that every data science practitioner met sometime in their line of work. From my experience these biases usually come from the old "let's throw all the data we have on a model and see what we get" method. A lot of the time it works well, but because it works so well we don't feel the need to explore and understand what happened, and then we miss some subtleties that might have a large impact.

The tragedy of this incident is how clear it looks that there should've been more efforts around careful selection of features. But no one phrases it better than Michael Scott - 

![[michael_scott_hindsight_small.png]]

While this specific incident may be added to your extensive list of best practices and things to avoid, here's an example of a bias that is a lot more hidden, and thus potentially more dangerous.

A group of researchers successfully trained models to [identify the race of the patients using an X-Ray or a CT scan](https://news.mit.edu/2022/artificial-intelligence-predicts-patients-race-from-medical-images-0520).  The models managed to identify the race of the patients, while human experts didn't 😱. 

This study was alarming for the health imaging industry. We already know that if a model can learn the race of a patient, it might use that information in its predictions in a way that magnifies existing racial bias. But, this study suggests that if we anonymize the data to the best of our perception, there might remain information that we cannot perceive.

It's important to emphasize that while these examples are based on incidents in the health industry, these missed biases happen in all the industries all the time. 

Whatever industry you're in, if your model can make bad decisions, it might learn some biases that would magnify those bad decisions.

Now for the final case. If the model that you're envisioning is going to be entrusted with something important, I hope this next case will hit home.
### [3. Zillow Cuts Down 2000 Jobs](https://www.geekwire.com/2021/zillow-shutter-home-buying-business-lay-off-2k-employees-big-real-estate-bet-falters/)

If you're not familiar with Zillow, here's a brief overview. Zillow is an American tech real-estate company that was founded in 2006. It mostly provides information and services related to selling and buying homes. 
On 2018 Zillow started a new division called Zillow Offers. Zillow Offers was responsible for buying, upgrading and selling houses as part of their  Zillow Offers service. 

One key feature of Zillow Offers was **Zestimate**. Zestimate is Zillow's estimate of a home's value.  To provide the Zestimate, the company uses a machine learning algorithm that takes into account a bunch of data about the property, including - tax and property records, submitted details such as number of bathrooms and bedrooms, and pictures of the house.

On February 2021, the company's confidence in their Zestimate was so high that they decided to make cash offers on the houses entirely based on their Zestimate!

I hope you see where this is going...

On November 2021, just 9 months after the announcement, Zillow announced the **closing** of Zillow Offers and a cut down of 2000 jobs which is about 25% of Zillow's workforce. Zillow Offers lost more that 420$ million from July to September and in total the company lost nearly 330$ million in Q3 of 2021 as opposed to Q3 of 2020 where they made a profit of 40$ million dollars. Zillow claims that they failed to accurately predict future housing prices due to changes in the real-estate markets caused by the COVID-19 pandemic. 

This is a wild loss and a huge amount of trust placed in a system that is ultimately a blackbox.
Zillow's CEO statement - 
 “Fundamentally, we have been unable to predict future pricing of homes to a level of accuracy that makes this a safe business to be in ... We’ve got these new assumptions that we’d be naïve not to assume will happen again in the future. We pump them into the model, and the model cranks out a business that has a high likelihood, at some point, of putting the whole company at risk.”


If you remember, a model is a *static* entity, and it cannot adapt to turbulent changes in its environment. In Zillow's case, they did not successfully adapt to the changes caused by the COVID-19 pandemic.

This amount of trust put into a system, in an environment that is known to be hard to predict, is unprecedented. The upside for such a system could've been huge, but also the risks are too high.
Zillow gave autonomy to a model that should've been closely monitored. If you ever decide to create an autonomous program, you should create metrics to ensure that it does not misbehave entirely, and prepare a shutdown plan in case it does.

If it goes rogue you would not want to discover that the only person that has permissions to turn off the machine is currently on vacation.

### Root of all Evil
Up to now we've seen three different cases:
1. Users making critical decisions based on a model's errors.
2. Models magnifying existing biases.
3. A model given autonomy loses hundreds of millions of dollars.

I hope that these examples make you think twice about the way you want to integrate AI into your product. 

Now I'd like to dive deeper into the three major problems as I see them.

#### Problem 1 - Probabilistic by Nature
I know I know, this is a feature. AI models are statistical by design, by using statistical methods we can estimate complex functions. These estimations are often good enough to  let us create useful applications for humans. But, as it happens with estimations, they have a certain degree of uncertainty. Better models mean fewer errors, but errors will continue to persist nonetheless.

If you managed to get a glimpse of some of the latest Large Language Models (LLMs) benchmarks, you would see that there are multiple ways to evaluate a model, with multiple datasets and multiple metrics.

![[Pasted image 20240331231558.png]]
`Mamba: Linear-Time Sequence Modeling with Selective State Spaces`

These different objectives reflect different points of view about what makes or breaks a model. In a way 


#### Problem 2 - Captures a State
With current technology, broadly speaking, training a model involves capturing a snapshot of a training set and then trying to use the output model to generalize over data the model didn't see. During the training phase the model tries to learn important representations for the task the model is optimized for.

For example, for the task of spam email classification, the model learns how to distinguish between a spam email and a regular email. 

The dataset is **crucial** for the training phase. It should have various quality examples of both spam and regular emails to succeed in learning meaningful features.
It is really hard, and sometimes downright impossible, to build a balanced dataset. But one thing that is important to understand about a dataset, **it will always be a snapshot of the world at a specific time**. 

This is, in essence, what makes AI models static. they are trained on a static dataset and are only updated in the next iteration (again, disregarding reinforcement learning).

Back to our example, a decade ago, emails looked vastly different than what they look like now. Therefore, a spam classification model trained a decade ago, will perform badly today. 

This is one of the core issues with current AI models. This might seem like a drastic comparison, but some domains are changing and adapting on an hourly basis (Stock trading for example). The faster a domain changes, the more a model will accumulate errors.

The phenomena where data in production changes over time is called **Data Drift**. 

This means that even if you trained the perfect model on the perfect dataset, when applying it to the real world, the model will become outdated as time progresses. 

I'll expand more on this issue in a future blog post, but I'd like to emphasize, this issue is caused because AI models capture a state and they are not dynamic. The fix for this issue today consists of gathering new data and retraining our models, which ultimately means, letting the model do more mistakes. 

Many products are okay with certain levels of mistakes, but if your product is on the less tolerant side, or if your domain changes rapidly, the more maintenance will be required.

#### Problem 3 - We Don't REALLY Understand It Yet

AI models today are too complex for us to fully understand. After ChatGPT was released there have been many papers evaluating GPT-3.5 and GPT-4. There have also been disagreement on some of the more subjective qualities like whether LLMs have reasoning capabilities.

[Emergent Abilities of Large Language Models](https://arxiv.org/pdf/2206.07682.pdf)

To try and grasp how much is unknown about AI and how fragile some of these systems are, I prepared for you a quick stroll around adversarial efforts in the AI space.
In my opinion, one of the most mind-blowing examples, is the one pixel attack.

By using various methods and carefully choosing a **single** pixel and changing it in an image, the authors manage to change the prediction of **various** image classifiers.

|![[one_pixel_attack.png]] |
| --- |
| *One pixel attacks on ImageNet in black the original predicition and confidence, in blue the new prediction after the change. Taken from the article.* |

To us humans, it's clear that a single pixel doesn't hold anything inherent in an image with many pixels. Yet, the fact that carefully chosen small changes can sway models toward different predictions just emphasizes how much this technology is fragile.

Another, maybe more relevant today, type of attack is "Prompt Injection." 
A prompt injection is when a prompt manipulates an LLM to behave in a way that it is not supposed to. Multiple prompt injection techniques have been published in the last year, despite the efforts being put in by LLM vendors (OpenAI, Anthropic, Google) to make them as safe as possible.

One common prompt injection method is "Jailbreaking," basically giving the users complete control over the models, despite the instructions the models might have received.

It usually looks something like this:
```
insert picture
```


A generic way to jailbreak LLMs by carefully choosing words was published this year.
https://x.com/zicokolter/status/1684500097386811393?s=20

And as jailbreaks go, even [Sam Altman is not sure](https://www.youtube.com/embed/L_Guz73e6fw?si=Pi18w181M9pfn4lu&amp;clip=UgkxzSik1J3_2uuKPhQImPRPgf41ADR8j_8D&amp;clipt=EJK4ZBiUqmY) that we will be able to mitigate them entirely.

If you have some free time, I suggest to play around with Gandalf by Lakera.ai (Link at the end). The people at Lakera.ai did a wonderful job creating a fun teaching challenge about prompt injection.

To me, this emphasizes how inherent these prompt injections are to the current way we build AI models, and if we'll compare this to the vulnerability field of cybersecurity the nature of it becomes even clearer.

Vulnerabilities exist because developers write bugs that are then exploited. It is possible (albeit hard) to write code that doesn't have bugs, and by that, eliminate vulnerabilities. It is *currently* impossible to create a model that doesn't make ANY mistakes, and as a model becomes more complex, it becomes more and more prone to errors.

## Summary

I've spoke a lot about the problems of AI, but I'm genuinely enthusiastic about the opportunities it presents!
The next part will be dedicated entirely to why, how and when should you incorporate AI. 

If there's one key idea that I want you to take away from this section is the following - 

AI, in it’s current form, is a probabilistic blackbox, we can never be sure as to how it will behave. 
Because it is probabilistic it will always have some amount of errors.
Because it captures a state, the faster the problem landscape changes, the faster the model's performance will degrade.
Because we don't really understand it, it is hard to fix.

We've went through a few cases where AI performed really poorly and if you're looking for more examples, I highly recommend the book [Weapons of Math Destruction by Cathy O'Neil](https://www.amazon.com/Weapons-Math-Destruction-Increases-Inequality-ebook/dp/B01LDFCP0S/ref=tmm_kin_swatch_0?_encoding=UTF8&amp;qid=1701027026&amp;sr=8-1&_encoding=UTF8&tag=maimonator-20&linkCode=ur2&linkId=77409e5323adc97e61950be626568109&camp=1789&creative=9325). It is a great overview of various sectors where a model that performed poorly had negative impact on groups that were already weakened.

## Final Words
The purpose of this blog post is not to scare you away from AI, but instead to remind you that having an AI system in production is hard, and you should think carefully about how to do it. 
In my next blog post, I will talk more about how to know if AI is right for your problem and what are the different considerations you should take. 

On a personal note, while I'm not publishing regularly on this blog, I very much enjoy the format and I hope you enjoy what I have to say. If I sparked some interest in you, or you want to chat more with me, please reach out! 


# Resources
I've used various resources while writing this and I linked most of them but I want to give a shoutout to a few other ones that have also accompanied me while writing this

* [The Batch - AI Newsletter](https://www.deeplearning.ai/the-batch/)
* [Weapons of Math Destruction - Cathy O'Neil](https://www.amazon.com/Weapons-Math-Destruction-Increases-Inequality-ebook/dp/B01LDFCP0S/ref=tmm_kin_swatch_0?_encoding=UTF8&amp;qid=1701027026&amp;sr=8-1&_encoding=UTF8&tag=maimonator-20&linkCode=ur2&linkId=77409e5323adc97e61950be626568109&camp=1789&creative=9325)
* [Designing Machine Learning Systems - Chip Huyen](https://www.amazon.com/Designing-Machine-Learning-Systems-Production-Ready/dp/1098107969/ref=sr_1_1?crid=GDK046MSEM4Y&amp;keywords=Chip+Huyen&amp;qid=1701027117&amp;sprefix=chip+huyen%252Caps%252C223&amp;sr=8-1&_encoding=UTF8&tag=maimonator-20&linkCode=ur2&linkId=9ac00ff390f633a2987e643ae5a86f0a&camp=1789&creative=9325)
* [Gandalf](https://gandalf.lakera.ai/)
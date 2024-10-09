## Why AI Then?

If you read up to here, I hope I managed to convince you that AI is not a simple one-size fits all solution and that there are many many caveats.

*That being said...*

I'm a huge fan of the technology and the opportunities that it provides, and even with all the maintenance it might require, sometimes the pros outweigh the cons considerably!

AI is still superior to classic programs in many fields. Some tasks are **very** hard to code, and in rapidly changing domains, are even harder to maintain. By teaching a model to solve a problem, whenever that models starts showing signs of drift, we can retrain the model on newer data to realign. In a classic program we would have to maybe manually tweak some numbers, or maybe edit and write rules to catch new errors. 

Take for example the task of transforming English *speech* to English *text*. 
Coding this task by hand seems impossible (at least to me), and now add to that the handling of different accents and background noise and it might really be impossible. But, by using AI it becomes much more easier!

The core issue that makes solving this problem favorable to AI, is that it doesn't matter if you choose to use AI  - you'll definitely need data (and probably a lot of it) for any implementation that you'd choose. 

For AI the reason is pretty clear, we train a model on data, the more diverse it is the more the model can generalize. A classic program doesn't need data to code it, but you would definitely need data to test it before you put it in production! 

How else would you know if you covered all edge cases? or at least a considerable amount to make your program useful?

For both tasks, you would probably need to gather some audio samples. For the classic program, you'd have to thoroughly learn the audio samples, how words are represented across different accents, and how to neutralize background noise. For the AI program, you'd have to build a diverse dataset of audio samples, and for better or for worse (but mostly better in this case) all the learning would be done by the model.

AI is King 👑 when we talk about unstructured data, be it text, images or audio. It lets us replicate concepts we have a hard time formulating what defines them. 

A good example of that is the notion of "Timbre" in sound. Timbre is the "color of a sound", it is how we can distinguish a trumpet and a guitar playing the same note. Today, there is not a clear universally accepted definition of timbre, mostly because it is influenced by various factors that include the properties of the sound source, how it was produced and the listener's perception. 

While we can't fully understand or define timbre, we can create AI models that replicate it pretty well!

Key features of AI
* Domain expertise at scale
* Personalization and Differentiability
* Adaptability

### Phrasing Your Problem as an Engineer

Before we go into trying to understand whether AI fits your product or not, I want to start with a translation exercise. 

In my day to day life I talk a lot about how terminology is important to finding a solution to a problem. If you speak the "problem language" you'd be more inclined towards asking the right questions, and finding resources that answer these questions.

I can't stress the value of having the right terminology enough. It can do **wonders** when you're looking for extra resources to validate your solutions, or trying to express your opinions to your peers.

And in our case, if you were to pitch the idea, it will do wonders if you can actually phrase your feature in an attainable manner.

It should be easy to deduce the following from a good problem phrasing:
1. Baseline comparison - AI will not be perfect, but it can be better than an existing solution.
2. Model Input & Output - what will it be trained on, and what will it predict on?

Example 1 - 
* ❌ - Use AI to increase sales.
* ✔️ - Using previous customer purchases, recommend products that seem relevant.

Example 2 - 
*  ❌ - 

### Does AI Fit My Product?


These are some key questions you should always ask yourself before incorporating AI into your product

* Could you learn to solve for a single use-case relatively easy, but it would be difficult to do it for all use-cases?
* Is there a specific aspect of my product that would perform vastly better if it was tailored to each customer?
* Do new use-cases appear overtime?
* Do I have a lot of data, or potential access to a lot of data regarding my problem domain?
	* Is my data labelled?
	* Do I have a way to label future data?
* Does a classical solution works, but is not enough to give desirable results?

If you answered yes to most of these question, than I'd be inclined to say AI does fit your product, and if engineered correctly you could draw value from it.

If you decide to go forward with this, it's important to remember the flaws AI models have.

In the next part, I will talk more deeply about the differences between AI programs and classic programs and how we can overcome the difficulties that are presented by AI programs. 
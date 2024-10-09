## Opening
*"In the gaming industry there are various efforts of creating"*
to create? Idk, it might just be fine but sounds a bit off in my ears. #changed 

*"It feels like the technology had just recently arrived and now everything is possible!
But the truth, as I see it, is that many of the ideas you might hear and see today around integrating AI into existing products, could've already been achieved before and for cheaper!
Recent advancement such as ChatGPT, Midjourney and others introduced us to innovative concepts and ideas, that can solve existing problems we couldn't solve before."*
This is a bit of a weird statement. First of all, the second sentence is long and maybe I'd drop the "as I see it", but second - it feels like you're saying "You think ChatGPT makes new things possible, but actually, this was already achievable before, but actually, this can solve problems we couldn't before". I guess you mean that it just introduced us to the ideas? Idk. - #Explain

*"This, in my opinion, has sparked an appetite in leadership in various companies for what is possible. But for most problems there are probably more cost-efficient solutions that rely on small AI models, or don't rely on them at all."*
I guess this says I was right in the previous paragraph being mostly about awareness and not that the technology really enables so many new things. I would definitely drop the "in my opinion" here. #Explain
## So, Why Not AI?
*"AI does not make a product better immediately, in fact, when implemented incorrectly, it can transform a good-enough product into a horrible one."* 
Start a new sentence with "In fact". #changed

*"📈 **Probabilistic**  - A model will have some errors, it could be insignificant, and every domain has its own insignificant definition, but there will be errors."*
has its own definition for "insignificant". #changed

*These are in my opinion, the root of all evil when trying to integrate AI into new or existing products.*
The roots of all evil? #changed

*To be fair, I have to mention that I'm leaving out reinforcement learning models as from my experience, 99% of business use-cases do not involve reinforcement learning.*
Do not involve them? #changed

*In the case of ChatGPT, it can not be trusted to generate reliable information, and while it can be a great source for learning, if the information to be trusted it should always be verified by the user with a different source.*
I'd change to "a great resource for learning" and to end the sentence with "should always be verified by the user". #changed

*This next case is much more destructive in scale.*
At scale? #changed

*The researchers also state that the source for this bias is that the algorithm uses **health costs** as a proxy to determine **health needs**. Due to Black patients' socio-economic status, they generally spend less money. Because of this, the algorithm thinks they have less health needs, or in other words, Black patients are in general healthier.*
The word Black appears with a capital B, maybe it should be like that but I'm not sure. #Explain

*By updating the algorithm and making sure it doesn't use the **health costs** the researchers successfully mitigate the bias.*
Mitigated. #changed

*Using features with an implicit bias is a type of error that every data science practitioner met sometime in their line of work. From my experience these biases usually come from the old "let's throw all the data we have on a model and see what we get" method. A lot of the time it works well, but because it works so well we don't feel the need to explore and understand what happened, and then we miss the subtleties that might have a large impact.*
I'd change to "miss some subtleties..." #changed

*The tragedy of this incident is how clear it looks that there should've been more efforts around careful selection of features. But no one phrases it better than Michael Scott*
Where's the quote? #thanks 

*if your model can make bad decisions, it might learn some biases that would magnify those bad decisions.*
I'm not sure I agree that this is the takeaway from your stories. I think the message is more along the lines of "society itself has a lot of bias, and when our models lean from these biases or are able to replicate them, this hinders the process of eliminating bias and maybe even regresses it". Or you're trying to make a point about a positive feedback loop, like adding the classic example of police profiling. (This kind of sound more like what your paragraph is saying, but I'm not sure it's the takeaway from the stories that come before). I guess this isn't your point though, because it appears to be the point of the third story. So to sum up, I'm slightly confused. #Explain #changed

*...nearly 330$ million in Q3 of 2021 as opposed to Q3 of 2020 where they made a profit of 40$*
I'd explicitly write "the third quarter", I don't think Q3 is accessible to not high-tech or stock-market people who might want to read your post. #skip

*We’ve got these new assumptions that we’d be naïve not to assume will happen again in the future we pump them into the model, and the model cranks out a business that has a high likelihood, at some point, of putting the whole company at risk.*
I think there should be a dot before "we pump". Or a comma. This is a quote so I don't know. #skip

*If you remember, a model is a static entity, and it cannot adapt to turbulent changes in its environments. in Zillow's case, they did not successfully adapt to the changes caused by the COVID-19 pandemic.*
(I removed your italics on the word static to keep my convention).
I'm not sure why it's "environments" and not "environment". Also, should capitalize the beginning of the new sentence. #changed 

*The amount of trust put into a system, in an environment that is known to be hard to predict, is unprecedented. The upside for such a system could've been huge, but also the risks are too high.*
Would change to "this amount of trust..." #changed

### Root of all Evil
*3. A model given autonomy loses hundred of millions of dollars.*
hunderds. #changed

*I know I know, this is a feature*
I know, I know. #changed

*This is in essence what makes AI models static*
This is, in essence. #changed

*I'll expand more on this issue in a future blog post, but I'd like to emphasize, this issue is caused because AI models capture a state and they are not dynamic. The fix for this issue today consists of gathering new data and retraining our models, which ultimately means, letting the model do more mistakes.*
I don't understand why the last sentence is "which ultimately means" from the previous bits. Like, I can assume that what you mean is that you could be naive and say "I made a perfect model, it has zero errors, I never touch it again", but if you do need to retrain the model, you might introduce mistakes you didn't have before. But this is just my assumption, not clear from the text. #changed 

*Many products are okay with certain levels of mistakes, but the less tolerant you are and the more the domain your model is in is evolving, the more maintenance will be required.*
I'd change to "but if your product is on the less tolerant side, or if your domain changes rapidly" (something like that). #changed

*I prepared for you a quick stroll around adversarial in the AI space.*
Maybe I'm not the target audience, but I think the word "adversarial" is not day-to-day enough to use without explaining. #skip

*Another, maybe more relevant to today, type of attack is "Prompt Injection."*
More relevant today. #changed

*There have been multiple prompt injection techniques in the last year despite the efforts being put by LLM vendors (OpenAI, Anthropic, Google) to make them as safe as possible.*
Would change to "Multiple prompt injection techniques have been published in the last year, despite the efforts being put in by..." #changed

*I'm sure you've seen some variations of them, but if you haven't, there's been recently published a generic way to jailbreak LLMs, by carefully choosing words.*
A. I'm not sure the "I'm sure you've seen..." is a good idea, might make people feel stupid. B. Would change the phrasing from "there's been recently..." to "A generic way to jailbreak LLMs by carefully choosing words was published this year". Current phrasing is a bit weird.

*And as jailbreaks go, even [Sam Altman is not sure](https://www.youtube.com/embed/L_Guz73e6fw?si=Pi18w181M9pfn4lu&amp;clip=UgkxzSik1J3_2uuKPhQImPRPgf41ADR8j_8D&amp;clipt=EJK4ZBiUqmY) that we will be able to mitigate jailbreaks entirely.*
Mitigate them entirely. #changed

*If you have some free time, I suggest to play around with [Gandalf](https://gandalf.lakera.ai/). The guys at Lakera.ai did a wonderful job creating a fun teaching challenge about prompt injection.*
Would change to "the people". Guys is gendered. #changed

*To me, this emphasizes how inherent these prompt injections are with the current way we build AI models, and if we'll compare this to the vulnerability field of cybersecurity the nature of it becomes even clearer.*
how inherent these prompt injections are **to** the way... #changed

*It is *currently* impossible to create a model that doesn't do ANY mistakes, and as a model becomes more complex, it is more prone to errors as well.*
doesn't make ANY mistakes. Also would change "it is more prone to errors as well." to "it becomes even more prone to errors". or "it becomes more and more prone to errors". #changed

*AI, in it’s current form, is a probabilistic blackbox, that we can never be sure as to how it will behave.*
Might change to "and we can never...". "that" sounds a bit off to me. #changed

*Because it is probabilistic it will always have some degree of errors*
Amount? What does degree mean in this context? #changed

*Because we don't really understand it, it is hard to fix it.*
If you're trying to say that the model is hard to fix, drop the "it" at the end of the sentence. If you're trying to say that these issues are hard to fix, write "it is hard to fix these problems/issues". #changed

# Resources
*I've used various resources while writing this and I linked most of them but I want to give a shoutout to a few ones that have also accompanied me while writing this*
"to a few other ones". #changed
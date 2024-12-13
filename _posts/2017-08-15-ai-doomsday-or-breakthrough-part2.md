---
layout: post
title:  "Artificial Intelligence: Doomsday or Breakthrough - Part 2"
date:   2017-08-15
image:  images/blog2/cover.jpg
tags:  Artificial Intelligence AI doomsday breakthrough singularity reinforcement learning openai exmachina turing test convolutionals neural networks
---
This post is a continuation of part one: [READ PART 1 HERE][part1]

Spoilers Ahead: One of the best portrayals of AI is the movie 'Ex Machina' in which the humanoid robot 'Ava' (in the cover picture) turns rogue to escape the 'prison' built by its creator Nathan, a genius coder, billionaire and founder of BlueBook (set to mimic Google). In the movie, Nathan invites Caleb (a loner, best coder and closely monitored 'chosen' fellow from BlueBook office) to perform the famous Turing Test[^1] and determine whether Ava demonstrates true intelligence. Caleb soon gets attracted to Ava during those Turing test interactions. He also learns from Ava that Nathan is trying to experiment with humanoid bots and eventually going to kill Ava for a better version. When confronted, Nathan says that Ava has only pretended to like Caleb, exploiting his vulnerabilities to escape the confinement and this ability of deception to achieve freedom, is what makes Ava remarkably better than the previous Androids that he created. 

Although it is fairly difficult to comprehend the possibility of such a self-aware robot, this movie does a fantastic job of bringing it to life. If you don't get creeped out by a non-organic adaptive robot capable of learning and perhaps even better at manipulation than humans, then this movie is definitely worth watching. Also this movie is the closest that comes to depicting General AI in a realistic fashion among all the pseudo-AI Skynet infused bloodthirsty robot bullshit that's out there.

![ex-machina-1](/images/blog2/1.jpg)
*Image Courtesy: Photographer REX; My favorite scene where Nathan shows Caleb the structured gel*

The reason why I brought up this movie is this scene above, where Nathan shows Caleb the structured gel that he created. In his words, "To get away from circuitry I needed something that rearranges on a molecular level but retain the form when required, most likely to mimic human brain". As compelling as that sounds, trouble is that we haven't even been able to create a controllable single neuron cell in-vitro, let alone creating an entire human brain with all it's functionalities. However, what we have managed to achieve is a blackbox software system with inputs, feedback loops and outputs which tries to mimic what a human brain does, one task at a time. All the neural networks that are out there right now are just complex control systems driven by backpropagation[^2] as a feedback loop. It can be sufficiently said that with the technology we have, it would take us perhaps another 100 years with the same pace now to recreate what nature has carefully crafted over a long period of time. 

But that isn't to say that the narrow AI systems that we developed aren't good enough. On the contrary, they are so good sometimes and even better than humans, because they use everything at their disposal to produce peak performance. For instance: vision. As I said earlier, our brain is a result of millions of years of evolution seeking perfection in tasks that are required for survival. And our vision system accounts for two-thirds of the electrical activity of the brain; a full 2 billion of the 3 billion neurons firings per second. Since our ape ancestors were arboreal (trees as habitat), one misplacement of that branch or depth of that tree trunk would have been fatal on that failed jump. So intense natural selection was at play. Because of this, we have developed highly refined stereo vision and it is said that we can identify more than 10 million colours. 

Now, where do AI systems stand in this regard? Say hi to Convolutional Neural Networks (CNNs) designed to process images and classify them. Some of these state of the art systems have already jumped human level performance in classification task on ImageNet dataset! A computer that *sees* better than you? Yes, you better believe it! But evidence suggests that Deep CNNs are processing images differently than humans and contain intrinsic blind spots[^3]. In fact, it is pretty easy to fool a CNN to make it believe that a particular image contains, say an ostrich when it is obviously not the case.

![intriguing properties of nn](/images/blog2/3.jpg)
*Image Courtesy: Taken from the paper "Intriguing properties of neural networks" by Szegedy et. al. 2013*

Using a minimum distortion function, it is possible to learn the distortion (middle) create adversarial examples (right) that look just like the original examples (left), except now the model is 99.9% certain that it contains an "Ostrich, Struthio camelus". What is important to note here is that these systems designed to replace humans for vision tasks are now vulnerable to adversrial attacks like the above. Imagine a self-driving car looking at a *Stop* sign and interpreting it as *Max Speed 60kmph* sign. You see the problem now? This might not only be limited to images. Imagine sending an adversarially modified email to extract sensitive information. Scary isn't it?

All this brings us back the question we started with; is AI doomsday or breakthrough? Well, it is hardly an overstatement when I say it is a spectacular breakthrough; the things that AI has achieved so far is quite impressive! However it might also bring a doomsday, not in SciFi killer robot methods like it is depicted in the movies, but in ways we cannot foresee all the time, hence requiring careful crafting of these systems.

AI systems at the moment are not an existential threat to human beings. However it will take away a lot of jobs involving repetitive tasks and leave more room for creative jobs. Just like what Industrial Revolution did to our granparent generation and what Internet did to our parent generation. What we could possibly worry about now is how regulations are developed for specific AIs like self-driving cars. Drafting new road rules and ethical issues sit on top of this list. This is very similar to how we fought for net neutrality recently which is a very apt example of how technology has to be regulated.  Our generation is probably one of the most luckiest to behold a revolution which is unique and challenging. We are living in an age where websites ask us to confirm that we are not a robot. What a time to be alive!

[^1]: Turing Test: Developed by the revolutionary Mathematician Alan Turing in 1950 who claimed a method to test machines which articulate intelligence to speak with a human. And given the responses are close to how a human would respond and if the tester is not able to distinguish the responses from a computer to a human being, then the machine is said to be intelligent and to have 'passed' the test. Turing test is outdated now but newer versions of these kind of tests have been proposed.
[^2]: Backpropagation: Also known as gradient descent is a commonly used learning algorithm for neural networks
[^3]: [Intriguing properties of neural networks](https://arxiv.org/abs/1312.6199)

[part1]: /blog/ai-doomsday-or-breakthrough-part1/
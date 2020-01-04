# Hypothesis Testing

This repo has a sketched out lesson plan for the Hypothesis Testing lecture used at Flatiron School for the Data Science Track.
Lesson materials were originally developed by [David John Baker](@davidjohnbaker).
In its current form, the materials span 90 minutes with considerable time built in for discussion questions and for students to come up with answers to larger prompts.

Slides can be found and edited [here](https://docs.google.com/presentation/d/1yL1H43aQogjjB9StQtdl0-1Y6JnOrXzNb8oyKfZGMNo/edit?usp=sharing) but please make a copy before changing!

## Lesson Goals

By the end of the lesson, students will be able to...

* [ ] Describe the scientific method noting that it's not as easy as a diagram makes it sound
* [ ] Identify who was Karl Popper and his general views on demarcation and falsifiability
* [ ] Describe The Problem of Induction 
* [ ] Describe the logic of null hypothesis significance testing as it relates to Induction/Popper
* [ ] Describe the four outcomes of a NHST 
* [ ] Identify what is a test statistic (signal over noise)  
* [ ] Note p value ONLY relates to rejection of NULL hypothesis 
* [ ] Run through one statistical test 

## Lesson

### Activation 

I typically open class noting that I normally get nervous to teach this lecture, even though it is my favorite.
Much of what we do in (data) science relies on our ability to make inferences and Null Hypothesis Significance Testing (NHST) has been the workhorse of science throughout much of the 20th century.
By understanding NHST, you can "get" the logic of what many scientists are trying to do and why they use this method, as opposed to other ways of knowing the world, to come to their conclusions about the world.

### Lesson Goals

Unlike many Intro to NHST classes that go bottom up from equations to logic, here going to take top-down approach and talk about the philosophy behind NHST and know all stats will follow.
Importantly, note that these problems of science we are trying to solve are real problems and have been attempted to be solved by real people, hence the pictures of the people and their books.

I also interject here that if you read about Philosophy of Science, it's the best way IMO to get better at (data) science. 
By knowing what tools you are using, you can ask better questions because you know what your tools can and cannot tell you.

### Scientific Method

* Point out typical diagram and explain what people probably heard in school
* Think, background, experiment, try again, progress
* Yes, this is general framework, but don't be deceived!
* See entire history of science to see that we mostly don't know what we are doing
	- Slide shows KUHN and Structure of Scientific Revolutions
	- AKA guy who gave us terms like "normal science" and "paradigm shift"
	- Slide shows FEYERABEND and Against Method 
	- AKA guy (student of popper) who says we pretty much only progress via chance

Learning Goal: 

* [X] Describe the scientific method noting that it's not as easy as a diagram makes it sound

### Induction and Popper

#### Popper 

* DQ: What makes something a SCIENTIFIC Question?

* Note science is messy and many ways to do it (we didn't have stats and p values for a long, long time)
* But back in day, still not clear what is and is not science
* DQ: If have time to derail, ask class If phrenology is a science (Kuhn would say yes, gotta be humble and not have 2020 hindsight, be humble, people will laugh at us too in 100 years) 

* Popper answers DQ1 with demarcation principle:
	- Scientific questions are ones that can be proven wrong 
	- Harder to prove wrong that mercury in retrograde will affect someone's mood
	- Easier to prove wrong that items dropped at same heights will fall at different rates. 

* Idea of YES/NO prove wrong is DEMARCATION
* How WRONG a theory can be is FALSIFIABILITY
* Current HOT work on FALSIFIABILITY and SEVERITY TESTING can be found in current philosophers of science (aka these real problems being solved by real people continue to this day) 
	- Slide shows MAYO and Severity Testing (living philosopher of science) 

Learning Goal: 

* [X] Identify who was Karl Popper and his general views on demarcation and falsifiability

Now that we have what is and is not SCIENCE, how do we build theories?

Two ways:
	1. Deduction (Roger example, works fine) 
	2. Induction (All swans are white? Not necessarily so...) 

#### Induction

You can have theories, but literally one thing can come and destroy them. 
Tons of examples of this.
Think we need the olfactory bulb for smelling? Turns out not.
Every day you wake up, have more evidence you'll wake up tomorrow?
Turkey is fed every day on an American farm? Sorry about Thanksgiving.

Problem of induction is very old (See David Hume aka fat Mozart).

Learning Goal: 

* [ ] Describe The Problem of Induction 

### Demarcation + Problem of Induction = NHST

Literally read off slide here to make sure I don't mess it up.
Can't just build evidence FOR a theory (problem of induction)
This happens all the time in science.
How do we get around problem?
Exploit asymmetry between data for theory and being critical of it.
Enter NHST.

Note we need to set up two worlds for NHST.
One world we know something is happening (H1).
Other world, nothing is happening (H0). 
If we can build up evidence against one, only left with logic of other being not not true.

Learning Goal

* [X] Describe the logic of null hypothesis significance testing as it relates to Induction/Popper

### Example

Explain example of diet with NHST for high level example.
Assuming this is the case, there are four things that can then happen.
Go to diagram slide.

FIRST explain columns.
If we use machinery of NHST remember we assume 2 worlds.
First world of H0, what we are pointing our science at DOEST NOT EXIST (H0).
If veganism does NOT actually have good effect on cholestorl (which we can't know because were not God, this is example) then either we say it does (when it really doesn't) or it doesn't when it really doesn't.

* NOTE HERE that NHST relies of FREQUENTIST way of thinking about the world.
* Experiments have to happen over and over again to find out what is true about the world! 

If veganism DOES have good effect on cholesterol, then H1 is TRUE.
So we can find something and that is TRUE (which it really is) or fail to find something when it is true.

Basically we can mess up in two ways if we take this binary approach to truth.
Say it is there when it's not.
Say it is NOT there when it is.

* Move to Type I and Type II errors wolf slide
* Can re-show table to make learning link
* For advanced students, can do math to show what happens when H0 and H1 are equally likely to be true

Learning Goal:

* [X] Describe the four outcomes of a NHST 

### Distributions

Next part of lesson assumes previous lecture or understanding of normal distributions.
TLDR if not, distributions are mathematical shapes that capture what a certain process looks like.
For example, process of making people.
Most people are about average height.
You are not going to find fully grown adults that are 1 foot tall or 12 feet tall.
If you do, you have reason to believe they come from different population (aliens).
Note here also that normal is not a value judgment, just a name.
Can also call it Gaussian (after Gauss).

So given what is known about finding observations in the tail, idea is that if we see anything in the tail, we have good reason to believe that it is surprising (the 12 foot tall person for one tail, 1 foot tall person two tail).

What we then want to do is give both our H0 and H1 a distribution and see if they are far enough apart from another in order to write your mom and say "look, I found something!" knowing quite well you could commit either a Type I or Type II error.

H0 and H1 capture some sort of measurement. 

So how do we do this??
Need to compare signal to the noise.

### Test Statistic

Signal to noise ratios give us something called a test statistic.
You take some number minus another number, then divide it by error.
Imagine you had two IQ scores of 100 and 113, subtract them from one another then divide how much error there is.
This test statistic contains information about both mean differences AND how much error is in your tool (reliability and validity)

Example of each of these (in simple form) would be z and t test (which people might have heard of).

Again, it's mean subtract another mean divided by error. 

Learning Goal: 

* [X] Identify what is a test statistic (signal over noise)  

### Steps of Hypothesis Testing 

Though the "tests" we run are called different names, the logic is all the same.

* Slide shows multiple tests are just same test with different names (to torture people).
* All tests REALLY are same test, which is general linear model (except stuff like logistic regression).

So to do ANY test, follow these steps:

* List out Steps of NHST Slide

* Go through example of comparing 26 to 23.36

* Read notes from slides 

Learning Goals:

* [X] Note p value ONLY relates to rejection of NULL hypothesis 
* [X] Run through one statistical test 




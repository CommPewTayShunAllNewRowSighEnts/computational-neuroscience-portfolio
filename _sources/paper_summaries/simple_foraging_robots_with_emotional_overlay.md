(paper:summaries:emotions:effect_reward_prediction_errors_emotional_state)=
# Effect of Reward Prediction Errors on the Emotional State of a Mobile Robot

## Paper Review

**Paper:** [Surendran, V. & Long, N.L. (2016) ](http://acs.ist.psu.edu/iccm2016/proceedings/surendran2016iccm.pdf)

### What is(are) the researcher(s) doing?
- developing a mobile robot that has a dynamic action selection mechanism which incorporates a model for emotions and temperment.
- the robot recreates the scenario of an animal foraging for food while avoiding predators.
- Four emotions were modelled:
	- anger
	- fear
	- happiness
	- surprise
- Emotions were affected by:
	- finding food
	- encountering a predator
	- encountering a boundary wall
	- finding a safe area
	- being in a state of low health
- The model incorporated a reward prediction module that altered the effect of an event based on the error between when an event occurred and when it was predicted to occur.
- The model also included a decay term that resulted in the emotions returning to their steady state values unless there was continual reinforcement through the occurrence of events.
- The effect of differing temperaments on the emotions was studied by defining an irate temperament.

#### Model Details

##### Action Selection Mechanism (ASM)

##### Emotions Engine

##### Emotions and Temperament Constants 

##### Short Term Memory

##### Reward Prediction Error (RPE) Module

##### Command Modifier 

### Why did they do it that way?
- By adapting a model for momentary well-being (Rutledge et al., 2014) as done by Long et al. (2015), and incorporating a reward prediction error, an action selection mechanism with an integrated emotions engine has been implemented in addition to the development of a low cost robot to test the mechanism (Surendan, 2015). 
- The ASM developed was a hybrid of a goal-based and a dynamic planning action selection mechanism.
- Each goal was associated with subgoals, and each subgoal with a dynamic plan. 
- Different events were defined that affected the individual emotions and the ASM provided means by which the emotional state could be used to modify the internal state of the robot through means of command modifiers
- Command modifiers also allowed the modification of dynamic plans and the value of emotions to be coupled through suitable models. 
- Temperaments and emotional variability were defined using a matrix of constants. 
- Varying the temperaments was observed to result in a different emotional state over the time period of the experiment even when the scenario was kept constant. 
- Finally, the importance of the reward prediction error was highlighted by showing that without it events affected the emotions by the same amount regardless of when they occurred. 
- With the RPE, it was possible to mimic the emotional response observed in humans by Rutledge et al (2014). 

### What are other ways of doing it?
- Additional tests should be conducted by 
	- specifying a more comprehensive list of command modifiers and 
	- fine tuning the temperament values based on the observation of an animal foraging for food in the wild 
- Since the temperament is specified by means of constants shown in Table 1, this leads to the possibility of an agent with a time-variant temperament that can alter its emotional sensitivity during run time
- The emotional model could also be modified to introduce a time lag between the occurrence of an event and it affecting the emotional state. 
	- This would allow the simulation of the four classic temperaments, theorized by Greek philosophers (“Four Humors - And there’s the humor of it: Shakespeare and the four humors,” 2012) namely:
		- melancholic, 
		- phlegmatic, 
		- choleric, and 
		- sanguine 
- Another approach would be the specification of the temperament--often described in the literature (Digman, 1990)--in terms of the “Big 5” traits of: 
		- extraversion, 
		- agreeableness, 
		- openness, 
		- conscientiousness, and 
		- neuroticism
- incorporating the acquisition of a non-homogeneous robot swarm with varying temperaments to explore if emotions increase the effectiveness of the swarm

### How is it useful to me?
This paper defines a robot model that could be implemented with Nengo.

### Background Literature

#### [R.W. Picard (2000)](http://www.macs.hw.ac.uk/~yjc32/project/ref-social%20media%20campaign/1995-affective%20computing.pdf)
- Affective computing seeks to understand and develop systems that can recognize and simulate human emotions.
- R.W. Picard (2000) highlighted the importance of the field by exploring neurological studies that indicated human cognition was intrinsically linked with emotions. 
- She also argues that that the development of affective computing is critical to advancing emotion and cognition theory. 

#### [Breazeal and Brooks (2005)](https://oxford.universitypressscholarship.com/view/10.1093/acprof:oso/9780195166194.001.0001/acprof-9780195166194-chapter-10)
- considered cognition and emotions to be two distinct systems that evolved in intelligent creatures under social and environmental processes to aid in optimal functioning. 
- Cognition is deemed to be responsible for interpreting the world whereas emotions are deemed to be responsible for evaluating the value of events. 
- Emotions thus help prioritize concerns while minimizing distractions. 

#### [Paul Ekman (1999)](https://doi.org/10.1002/0470013494.ch3)
- The simulation of human emotions is greatly complicated by the fact that there is no accepted model that explains and predicts the wide range of emotions we experience.
- There still is no consensus in the literature on the number of base emotions.
- Proposes a list of 15 emotions, each representing a family of emotions.

#### [Jack et al. (2015)](https://doi.org/10.1016/j.cub.2013.11.064)
- A study on dynamic facial expressions of emotion challenges the notion of (Ekman 1999) by suggesting that basic emotion communication comprises fewer categories. 
- It is clear that our understanding of the subject is still in its infancy.

#### [Rutledge et al. (2014)](https://www.pnas.org/content/111/33/12252)
- A study on momentary subjective well-being that resulted in a model of happiness referred to as the ‘Happiness Equation’ in popular culture. 
- They showed that momentary happiness in response to a probabilistic reward is explained by the combined influence of the reward expectations and the prediction errors from the expectations; not by current task earnings as one would naively conclude. 

#### [Long et al. (2015)](https://www.researchgate.net/publication/274384955_An_Emotion_and_Temperament_Model_for_Cognitive_Mobile_Robots) and [Long (2015)](http://act-r.psy.cmu.edu/wordpress/wp-content/themes/ACT-R/workshops/2015/long-ACTR_2015a.pdf)
- adapted this model to simulate the eight ‘universal’ emotions of fear, anger, sadness, happiness, disgust, surprise, trust, and interest in cognitive mobile robots.

#### [Troy D. Kelley (2006)](https://api.semanticscholar.org/CorpusID:60631110)
The emotion and temperament engine developed by (Long, 2015) was incorporated into SS-RICS which is a cognitive architecture developed at the Army Research Laboratory.

#### [Surendran (2015)](https://etda.libraries.psu.edu/files/final_submissions/10871)
- built upon (Long et. al., 2015) emotional model by incorporating a reward prediction error component with a focus on developing a model that could be executed with limited computational resources. 
- this model did not use SS-RICS
- implemented a new action selection mechanism (ASM) capable of running on a small mobile robot with a Raspberry Pi processor.


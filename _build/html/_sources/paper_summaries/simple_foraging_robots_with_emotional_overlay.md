(paper:summaries:emotions:effect_reward_prediction_errors_emotional_state)=
# Effect of Reward Prediction Errors on the Emotional State of a Mobile Robot

## Paper Review

**Paper:** [Surendran, V. & Long, N.L. (2016)](http://acs.ist.psu.edu/iccm2016/proceedings/surendran2016iccm.pdf)

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
This mechanism was designed so that
- it allows for the robot to be autonomous and make decisions based on external and internal stimuli.
- it replicates the required behavior 

To fulfill those design needs it used a hybrid architecture of:
- **Dynamic planning methods** to determine next action taken
  - This type of mechanism was chosen because it is ideal when there are limited computational resources 
- **Goal driven architecture** for replicating desired behaviors

The goals were:
- finding food
- finding a safe area
- avoiding danger 
- resting

These goals were decomposed into subgoals:
- finding a ball
- tracking a ball
- eating a ball
- avoiding a ball
- etc

Each of these subgoals was associated with a dynamic plan that the ASM selects in order to accomplish the goal.

Condition-action rules similar to those used in expert systems were used to implement the dynamic plans.

Rules defined the ‘knowledge’ the system possessed and in this system are either factual or procedural.
##### Emotions Engine
Computational model from Rutledge et al. (2014):

$
Happiness(t) = w_0 + w_1 \sum_{j=1}^{t} \gamma^{t-j} CR_{j}  + w_2 \sum_{j=1}^{t} \gamma^{t-j} EV_{j}   + w_3 \sum_{j=1}^{t} \gamma^{t-j} RPE_{j}  
$
* CR: Certain Rewards
* EV: Expected Value
* RPE: Reward Prediction Error

Modified model from Long et al. (2015):

$
Emotions(t)_{i} = w_{0_i} + \sum_{j=1}^{t} \gamma_{i}^{t-j} (w_{1_i}R_{ij}^{+}  + w_{2_i}R_{ij}^{-} )
$
* $R_{ij}^{+}$: positive reinforcements
* $R_{ij}^{-}$: negative reinforcements

Used in this study:

$
Emotions(t)_{i} = w_{0_{i}} + \sum_{j=1}^{n} \gamma_{i}^{t_{f}-t_{j}} w_{1_i}R_{j}  + \sum_{j=1}^{n} \gamma_{i}^{t_{f}-t_{j}} w_{2_i}RPE_{j} 
$

##### Emotions and Temperament Constants 

Table 1: Emotion constants:
```{list-table}
:header-rows: 1
:name: Emotion_Constants

* - **Emotion**
  - **$w_0$**
  - **$w_1$**
  - **$w_2$**
  - **$\gamma$**
* - **Anger**
  - 0
  - 1.9
  - 0.15
  - 0.92
* - **Fear**
  - 0
  - 1.9
  - 0.15
  - 0.92
* - **Happiness**
  - 0
  - 2.3
  - 0.15
  - 0.92
* - **Surprise**
  - 0
  - 1.7
  - 0.15
  - 0.88
```
Table 2: Emotion modifiers:
```{list-table}
:header-rows: 1
:name: Emotion_Modifiers

* - 
  - **Anger**
  - **Fear**
  - **Happiness**
  - **Surprise**
* - **Danger Encountered**
  - 0
  - +12
  - -5
  - +10
* - **Found Food**
  - -1
  - -1
  - +5
  - 0
* - **Returned to Safe Area**
  - -5
  - -5
  - +5
  - -5
* - **Wall Encountered**
  - +3
  - 0
  - 0
  - +5
* - **Health Too Low**
  - 0
  - +2
  - -2
  - 0
```
##### Components
Three major components:
- short term memory
- RPE module
- command modifier

###### Short Term Memory
- The emotional state of an agent is deemed to depend on its internal state and external stimuli such as events.
- Due to the decay component $\gamma$ of the emotional model, it was found that a **memory length of six events** was optimal as the
exponential decay meant that the value of any previous events was negligibly small.
###### Reward Prediction Error (RPE) Module
- Momentary subjective well-being was found to depend not only on an event but errors in predicting the occurrence of said event. 
- Unexpected events have a higher impact on the value of an emotion 
- Due to a lack of long term memory and learning capabilities, the average number of time steps taken for an event to occur in the past is used to predict future expectations. 
- The difference between prediction and the actual time taken for the event to occur is considered to be the RPE.

###### Command Modifier 
- Data stored by the short term memory module is sent to the RPE module to calculate the RPE. 
- Using emotional model the instantaneous value of the four emotions are then calculated and in combination define the emotional state of the robot.
- The command modifier allows the emotions engine to modify the ASM commands generated and the internal state of the agent, based on the current emotional state.


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
- the decay component $\gamma$ could be modified using Nengo's short-memory module because this model only used a **memory length of six events** 
- incorporate long-term memory and learning if the model can successfully be implemented in Nengo
- mixed emotions instead of strongest


### How is it useful to me?
This paper defines a robot model that could be implemented with Nengo.

### Background Literature Review

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


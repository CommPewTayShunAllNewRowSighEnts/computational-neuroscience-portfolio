(paper:summaries:emotions:simulating_emotions_an_active_inference_model_of_emotional_state_inference)=
# Simulating Emotions an Active Inference Model of Emotional State Inference and Emotion Concept Learning

## Paper Review

**Paper:** [Smith, R. (2019)](https://doi.org/10.3389/fpsyg.2019.02844)

- The ability to conceptualize and understand one’s own affective states and responses—or “Emotional awareness” (EA)—is positively correlated with a range of adaptive cognitive and emotional traits.
- a growing body of work has investigated the neurocognitive basis of EA, the neurocomputational processes underlying this ability have received limited attention.
- they present a formal Active Inference (AI) model of emotion conceptualization that can simulate the neurocomputational (Bayesian) processes associated with learning about emotion concepts and inferring the emotions one is feeling in a given moment.
- they validate the model and inherent constructs by showing 
  1. it can successfully acquire a repertoire of emotion concepts in its “childhood”, as well as 
  2. acquire new emotion concepts in synthetic “adulthood,” and 
  3. that these learning processes depend on early experiences, environmental stability, and habitual patterns of selective attention.

### What is the researcher doing?
The researchers proposed a neurocognitive model – termed the “three-process model” of emotion episodes – with a primary focus on accounting for individual differences in emotional awareness:

````{margin} 
```{admonition} somatovisceral
Pertaining to the influence of the body framework (soma), or neuromusculoskeletal system, on the function of the internal body systems and organs.
````

1. **Affective response generation:** a process in which somatovisceral and cognitive states are **automatically modulated in response to an affective stimulus** (whether real, remembered, or imagined) in a context-dependent manner, **based on an (often implicit) appraisal of the significance of that stimulus for the survival and goal-achievement** of the individual (i.e., **predictions** about the cognitive, metabolic, and behavioral demands of the situation).

2. **Affective response representation:** a process in which the somatovisceral component of **an affective response is subsequently perceived via afferent sensory processing**, and then **conceptualized as a particular emotion** (e.g., sadness, anger, etc.) in consideration of all other available sources of information (e.g., stimulus/context information, current thoughts/beliefs about the situation, etc.).

3. **Conscious access:** a process in which the representations of somatovisceral percepts and **emotion concept representations may or may not enter and be held in working memory – constraining the use of this information in goal-directed decision-making** (e.g., verbal reporting, selection of voluntary emotion regulation strategies, etc.).

The TPM has also proposed a tentative mapping to the brain in terms of interactions between large-scale neural networks serving domain-general cognitive functions. 
Some support for this proposal has been found within recent neuroimaging studies.
However, the neurocomputational implementation of these processes has not been thoroughly considered. 
The computational level of description offers the promise of providing more specific and mechanistic insights 

- They aim to take the first steps in constructing an explicit computational model of the acquisition and deployment of emotion concept knowledge (i.e., affective response representation) as described within the TPM 
  - (subsequent work will focus on affective response generation and conscious access processes; see Smith et al., 2019b). 
- Specifically, they present a simple Active Inference model (Friston et al., 2016, 2017a) of emotion conceptualization, formulated as a **Markov Decision Process**. 
- They then outline some initial insights afforded by simulations using this model. 
- The place a special emphasis on **deep generative models** that afford the capacity to explain multimodal (i.e., interoceptive, proprioceptive, and exteroceptive) sensations that are characteristic of emotional experience. 
- They introduce a particular model of emotion inference that is sufficiently nuanced to produce **synthetic emotional processes** but sufficiently simple to be understood from a “first principles” account. 
- They establish the validity of this model using **numerical analyses of emotion concept learning** during (synthetic) neurodevelopment. 
- They conclude with a brief discussion of the implications of this work; particularly for **future applications**.

### Why did they do it that way?

#### Active Inference
- Active Inference (AI) starts from the assumption that **the brain is an inference machine that approximates optimal probabilistic (Bayesian) belief updating across all biopsychological domains** (e.g., perception, decision-making, motor control, etc.)
- AI postulates that **the brain embodies an internal model of the world** (including the body) that is “generative” in the sense that it is able to simulate the sensory data that it should receive if its model of the world is correct. 
- This simulated (predicted) sensory data can be compared to actual observations, and **deviations between predicted and observed sensations can then be used to update the model**. 
- On short timescales (e.g., a single trial in a perceptual decision-making task) this updating corresponds to perception, whereas on longer timescales it corresponds to learning (i.e., updating expectations about what will be observed on subsequent trials).

- Action (be it skeletomotor, visceromotor, or cognitive action) can be cast in similar terms. 
  - For example, **actions can be chosen to resolve uncertainty about variables within a generative model** (i.e., sampling from domains in which the model does not make precise predictions). 
  - This can **prevent future deviations from predicted outcomes**. 
  - there is a deep sense in which the brain must continually seek out observations that support – or are internally consistent with – its own continued existence.
    - decision-making can be cast as a process in which the brain infers the sets of actions (policies) that would lead to observations most consistent with its own survival-related expectations (i.e., its “prior preferences”).
    - Mathematically, this can be described as selecting policies that maximize a quantity called “Bayesian model evidence” 
      - that is, the probability that sensory data would be observed under a given model. 
      - In other words, because the brain is itself a model of the world, action can be understood as a process by which the brain seeks out evidence for itself – sometimes known as self-evidencing (Hohwy, 2016).

#### Computation
In a real-world setting, directly computing model evidence becomes mathematically intractable. 
- Thus, the brain must use some approximation: 
- AI proposes that the brain instead computes a statistical quantity called **free energy**. 
  - Unlike model evidence, computing free energy is mathematically tractable. 
  - This quantity provides a bound on model evidence, such that **minimization of free energy is equivalent to maximizing model evidence**.
  - in decision-making an agent can evaluate the **expected free energy** of the alternative policies it could select—that is, the free energy of future trajectories under each policy (i.e., based on predicted future outcomes, given the future states that would be expected under each policy). 
  - Therefore, **decision-making will be approximately (Bayes) optimal** if it operates by inferring (and enacting) the policy that minimizes expected free energy – and thereby maximizes evidence for the brain’s internal model. 
  - **expected free energy** can be decomposed into terms reflecting **uncertainty** and **prior preferences**, respectively. 
    - This decomposition explains why agents that minimize expected free energy will first select exploratory policies that minimize uncertainty in a new environment (often called the “epistemic value” component of expected free energy).
    - Once uncertainty is resolved, the agent then selects policies that exploit that environment to maximize her prior preferences (often called the “pragmatic value” component of expected free energy). 

```{figure} ../paper_summaries/Active_Inference_Model.jpg
:name: active-inference

This is from [Figure 2](https://www.frontiersin.org/files/Articles/489395/fpsyg-10-02844-HTML/image_m/fpsyg-10-02844-g002.jpg) of the article 
```



### What are other ways of doing it? Or, how can this work be extended? 


### How is it useful to me?
- offers a proof of principle that cognitive-emotional processes can be modeled formally, and highlight the potential for both theoretical and empirical extensions of this line of research on emotion and emotional disorders.
- The neurocomputational implementation of the TPM has not been thoroughly considered so this is a research opportunity to model this with Nengo
- no formal modeling of emotion concept learning has yet been performed. 

### Literature Review

#### Bagby et al., 1994a,b
- Attempts to operationalize cognitive-emotional ability have led to a range of overlapping constructs, alexithymia 

#### Barchard and Hakstian, 2004
- the construct of emotional awareness, higher ability levels of conceptualization have been associated with a range of adaptive emotion-related traits and abilities. 

#### Barrett, 2017; 
- theoretical models of the underlying cognitive and neural basis for the ability to conceptualize and understand one’s affective responses 
- Constructivist views hold that emotion categories do not have a 1-to-1 relationship to distinct neural circuitry, and that emotion concept acquisition is necessary for emotional experience 

#### Bréjard et al., 2012
- the construct of emotional awareness, higher ability levels of conceptualization have been associated with a range of adaptive emotion-related traits and abilities. 

#### Ciarrochi et al., 2003
- the construct of emotional awareness, higher ability levels of conceptualization have been associated with a range of adaptive emotion-related traits and abilities. 

#### Friston et al., 2017a
- detailing the formal mathematical basis for Active Inference 

#### Hohwy, 2016
- the brain is itself a model of the world, action can be understood as a process by which the brain seeks out evidence for itself – sometimes known as self-evidencing.

#### (Joffily and Coricelli, 2013; Seth, 2013; Barrett and Simmons, 2015; Seth and Friston, 2016; Smith et al., 2017d, 2019e; Clark et al., 2018)
- previous theoretical work has applied active inference concepts to emotional phenomena

#### Kashdan and Farmer, 2014; Kashdan et al., 2015 
- Attempts to operationalize cognitive-emotional ability have led to a range of overlapping constructs, emotion differentiation or granularity
 
#### Kleckner et al., 2017; 
- theoretical models of the underlying cognitive and neural basis for the ability to conceptualize and understand one’s affective responses 

#### Lane et al., 1990, 1996, 2000
- the construct of emotional awareness, higher ability levels of conceptualization have been associated with a range of adaptive emotion-related traits and abilities. 

#### Lane et al., 2015; 
- theoretical models of the underlying cognitive and neural basis for the ability to conceptualize and understand one’s affective responses 

#### Lane and Schwartz, 1987
- Attempts to operationalize cognitive-emotional ability have led to a range of overlapping constructs, including trait emotional awareness 

####  McRae et al., 2008
- The ability to conceptualize and understand one’s affective responses

#### Panksepp et al., 2017; 
- theoretical models of the underlying cognitive and neural basis for the ability to conceptualize and understand one’s affective responses 

#### Panksepp and Biven, 2012
- there are a number of competing views on the nature of emotions, most (if not all) accept that emotion concepts must be acquired through experience. 
  - For example, “basic emotions” theories hold that emotion categories like sadness and fear each have distinct neural circuitry, but do not deny that knowledge about these emotions must be learned 

#### Smith et al.,  2015, 2017b,c, 2018a,b,c,d,e, 2019a,c
- The ability to conceptualize and understand one’s affective responses
- theoretical models of the underlying cognitive and neural basis for the ability to conceptualize and understand one’s affective responses 
- Recently proposed a neurocognitive model – termed the “three-process model” of emotion episodes – with a primary focus on accounting for individual differences in emotional awareness.
- This model characterizes a range of emotion-related processes that could contribute to trait differences in both the learning and deployment of emotion concepts in order to understand one’s own affective responses (and in the subsequent use of these concepts to guide adaptive decision-making). 
- The TPM distinguishes the following three broadly defined processes
- The TPM has also proposed a tentative mapping to the brain in terms of interactions between large-scale neural networks serving domain-general cognitive functions. 
  - Showed some support for this proposal has been found within recent neuroimaging studies 

#### Smith and Lane, 2015, 2016
- theoretical models of the underlying cognitive and neural basis for the ability to conceptualize and understand one’s affective responses 

#### Wilson-Mendenhall et al., 2011; 
- theoretical models of the underlying cognitive and neural basis for the ability to conceptualize and understand one’s affective responses 

#### Wright et al., 2017. 
- The ability to conceptualize and understand one’s affective responses
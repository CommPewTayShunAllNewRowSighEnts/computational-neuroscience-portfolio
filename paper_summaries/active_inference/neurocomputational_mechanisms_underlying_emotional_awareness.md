(paper:summaries:emotions:neurocomputational_mechanisms_underlying_emotional_awareness)=
# Neurocomputational mechanisms underlying emotional awareness
Insights afforded by deep active inference and their potential clinical relevance.

## Paper Review 

**Paper:** [Smith, R., Lane, R., Parr, T., and Friston, K. (2019)](https://doi.org/10.1101/681288)

### What is the researcher doing?
- present simulations to illustrate (seven) distinct mechanisms that (either alone or in combination) can produce phenomena characteristic of low EA, such as: 
  - [somatic misattribution](https://en.wikipedia.org/wiki/Misattribution_of_arousal): a term in psychology which describes the process whereby people make a mistake in assuming what is causing them to feel aroused. For example, when actually experiencing physiological responses related to fear, people mislabel those responses as romantic arousal. 
  - [coarse-grained emotion conceptualization](https://en.wikipedia.org/wiki/Emotion_classification) 
  - constrained reflective capacity 
- They focus on the construct of levels of emotional awareness. 
  - Within the theory of levels of emotional awareness (tLEA), and its accompanying measurement scale (the levels of emotional awareness scale), five different categorical levels are distinguished (although these are understood to reflect particular points on a continuum)
    - **Level 1 - somatic sensations**: tend to somatize, in the sense that they may misattribute emotion-related sensations from their body to physical illness or disease.
    - **Level 2 - valenced approach-avoidance tendencies:** may simply recognize that they feel emotionally “bad” or that they “feel like running away”.
    - **Level 3 - subjective categorization:** using distinct emotion categories such as awareness of sadness, anger, and fear.
    - **Level 4 - ability to entertain multiple emotions:** in the mind simultaneously,feeling a blend of emotions such as anger and fear.
    - **Level 5 - additional theory of mind ability:** an individual is further able to distinguish the emotions of self and others.
- Three Process Model
  - (TPM; (Smith et al., 2018a; Smith, 2019; Smith et al., 2019b) has recently been proposed to distinguish a range of processes that contribute to emotion episodes, and how individual differences in these processes could contribute to trait differences in emotional awareness (and in the subsequent use of this awareness to guide adaptive decision-making). 
  1. Affective response generation: 
     - a process in which somatovisceral and cognitive processes are automatically modulated in response to an affective stimulus (whether real, remembered, or imagined) in a context-dependent manner, based on an (often implicit) appraisal of the salience of that stimulus for the survival and goal-achievement of the individual and of associated upcoming metabolic or behavioral demands.
  2. Affective response representation: 
     - a process in which the somatovisceral component of an affective response is subsequently perceived via afferent sensory processing, and then conceptualized under a particular emotion category (e.g., sadness, anger, etc.) in consideration of all other available sources of information (e.g., stimulus or context information, current thoughts or beliefs about the situation, etc.).
  3. Conscious access: 
     - a process in which somatovisceral percepts and emotion concepts are made accessible to domain-general cognition and can be held in working memory – allowing the use of this information in goal-directed decision-making (e.g., verbal reporting, selection of voluntary emotion regulation strategies, etc.)

- They present a hierarchical (deep temporal) neuro-computational model motivated by the active inference framework (Friston et al., 2017a, 2016) that can account for multiple levels of emotional awareness (EA).
  - This model allows for quantitative simulations of how 
    - affective bodily responses can be represented (EA level 1/2) and 
    - affective bodily responses can be categorized as emotions (EA level 3),
    - and how multiple emotions – including those of both oneself and others – can then be held in mind to inform verbal reports and goal-directed decisions (EA level 4/5). 
  - They **do not fully address the theory of mind abilities associated with the fifth level of emotional awareness; however, the current report serves as a foundation for future work along these lines.**     

### What question are they trying to answer?
- the neurocomputational processes that underwrite individual variations in Emotional Awareness (EA) remain unclear
- They aim to describe a deep (active) inference model that reproduces the cognitive-emotional processes associated with EA

### Why did they do it that way? 
- Trait emotional awareness (tEA) – the ability to conceptualize and understand one’s own affective responses – is now recognized as an important source of individual variability in both clinical psychology and neuroscience
    - Attempts to operationalize this variability have led to a range of overlapping constructs, including 
      - levels of emotional awareness (Lane and Schwartz, 1987)
      - emotion differentiation or granularity (Kashdan et al., 2015; Kashdan and Farmer, 2014)
      - alexithymia (Bagby et al., 1994a, 1994b).

### How is it useful to me?
- provides a deep temporal model of emotional awareness
  - implementing this in Nengo could provide interesting insights
  - right now I'm quite curious about how emotions impact learning, this model and the levels of emotional awareness could potentially provide interesting insights into the ability to solve various types of problems depending on emotional awareness levels
- I will need to do a more thorough read of the model specifications in the future to understand if implementing this is feasible

### Example of Models from Paper:

```{figure} ../active_inference/images/F1_large.jpg
:name: generative_model

This is from [Figure 1](https://www.biorxiv.org/content/biorxiv/early/2019/08/31/681288/F1.large.jpg of the article. Illustration of the working memory task performed by the agent.
```

```{figure} ../active_inference/images/F2_large.jpg
:name: active-inference

This is from [Figure 2](https://www.biorxiv.org/content/biorxiv/early/2019/08/31/681288/F2.large.jpg) of the article. The neuronal message passing framework for the hierarchical MDP formulation of active inference that was used to perform the simulations described in this paper. 
```

```{figure} ../active_inference/images/exampleModel1.jpg
:name: active-inference

This is from [Figure 3](https://www.biorxiv.org/content/biorxiv/early/2019/08/31/681288/F3/graphic-3.large.jpg) of the article. Displays the levels of hidden state factor 1 (internal state concepts) and their mapping to different lower-level representations (here modeled as affective outcomes and feedback).  
```

```{figure} ../active_inference/images/exampleModel2.jpg
:name: active-inference

This is from [Figure 3](https://www.biorxiv.org/content/biorxiv/early/2019/08/31/681288/F3/graphic-4.large.jpg) of the article. isplays the levels of hidden state factor 2 (focus of attention) and its mapping to outcomes.  
```
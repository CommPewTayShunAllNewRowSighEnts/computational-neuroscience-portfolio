(paper:summaries:emotions:emotional_valence_free_energy)=
# Emotional Valence and the Free-Energy Principle

## Paper Review

**Paper:** [Joffily and Coricelli, 2013;](https://doi.org/10.1371/journal.pcbi.1003094)

### What question are they trying to answer?
- propose a definition of emotional valence in terms of the **negative rate of change of free-energy over time**. 
  - If the **second time-derivative of free-energy** is taken into account, they can explain the dynamics of basic forms of emotion such as:
    - happiness, 
    - unhappiness, 
    - hope, 
    - fear, 
    - disappointment
    - relief 
  - In this formulation, **an important function of emotional valence** turns out to **regulate the learning rate of the causes of sensory inputs**.
    - When sensations increasingly **violate** the agent's expectations, valence is **negative** and **increases the learning rate.**
    - When sensations increasingly **fulfil** the agent's expectations, valence is **positive** and **decreases the learning rate.**

- propose a formal definition of emotional valence (i.e., the positive and negative character of emotion) in terms of the **rate of change of free-energy** or, under some simplifying assumptions, of prediction error over time.
  - They instantiate this scheme with an emotional agent who is able to **dynamically assign emotional valence** to every new state of the world that is visited and to experience basic forms of emotion.

- **The proposed scheme is very general in the sense that it is not tied to any particular generative model of sensory inputs.**
- 
### What is the researcher doing?
```{note}
Free-energy is an information theoretic quantity that upper bounds the surprise on sampling some data, given a generative model of how data were caused.

The free-energy principle assumes that biological agents encode a probabilistic model of the causes of their sensations, and postulates that any adaptive agent that resists a tendency to disorder must minimize its free-energy

Under simplifying (Gaussian) assumptions, free-energy minimization can be understood as the minimization of the prediction error between the actual and predicted sensory inputs.

In order to comply with the free-energy principle, adaptive agents have two tactics at their disposal: 
1. adjusting their internal states to generate more accurate predictions 
2. acting on the environment to sample sensations that fulfil their predictions.

The principle is based upon the realization that perceptual inference and learning, and active inference rest on the same Bayesian scheme.

The free-energy principle states that any adaptive agent that is at equilibrium with its environment must minimize its free-energy. 
```
- **Perceptual inference** refers to inferring the states of the world causing sensory inputs.
- **Perceptual learning** relates to learning the relationship between inputs and causes. 
- **Active inference** corresponds to acting on the world to fulfil prior expectations about sensory inputs.

The computational implementation of the free-energy principle has been shown to replicate in many aspects neural mechanisms and the cortical organization of the brain

Crucially, when inferring and learning the causes of their sensations in a changing world, adaptive agents need to deal with different forms of uncertainty, namely estimation uncertainty, volatility, and unexpected uncertainty.

- **Estimation uncertainty** refers to the known estimation variance of states of the world causing sensory inputs and can be reduced through learning. 
- **Volatility** refers to slow and continuous changes in states of the world, and has usually been modelled by making estimation uncertainty follow some latent stochastic process.
- **Unexpected uncertainty** arises from surprising sensory inputs caused by discrete and fast changes in states of the world, and calls for forgetting the past and restarting learning from new sensory data. 

```{note}
Two classes of emotions have been referred to as factive and epistemic

**Factive**: large group of emotions, which includes happiness, unhappiness, relief and disappointment, is related to certain (firm) beliefs that states of affairs obtain.

**Epistemic**: smaller group of emotions, mainly represented by hope and fear, is related to uncertain beliefs.

factive and epistemic emotions are indeed associated with low and high levels of uncertainty, respectively, but this comes as a consequence and not as a necessary condition of their definition (see Results).
```

- since free-energy is minimized for each level of the hierarchical model separately, their formulation also predicts that **different emotions can occur concurrently**.

```{figure} ../active_inference/images/emotoinal_states_and_free_energy.png
:name: emotoinal_states_and_free_energy

This is from [Table 1](https://journals.plos.org/ploscompbiol/article/figure?id=10.1371/journal.pcbi.1003094.t001) of the article.
```

#### Emotional regulation of estimation uncertainty
This is interesting:

- Emotional valence and some basic forms of emotion can be elicited by the dynamics of free-energy. 
  - What, however, is the function of these quantities in a scheme originally developed to explain perception, learning and action? They propose:
    - valence, computed as the negative rate of change of free-energy, is crucial because it informs biological agents about unexpected changes in their world. 
      - When **valence is positive**, sensory inputs fulfil the agent's expectations and the probability of unexpected changes is low. 
      - When **valence is negative**, the agent's expectations are violated and unexpected changes in the world are likely to have taken place.
    - In settings where recent information is a better predictor of states of the world than past information, that is, in a changing world, recent information must be more heavily weighted and, therefore, the learning rate should be high. 
    - Conversely, in a stationary world, in which past and recent information are equally informative, the learning rate should be low in order to take into account both past and recent information.
  - They formalise this notion in terms of emotional meta-learning in which estimation uncertainty is determined not just by free-energy but by the rate of change of free-energy.
    - when the free-energy associated with posterior beliefs about states at a particular level in the agent's hierarchical model is increasing, the posterior certainty about these states decreases.
    - the agent interprets decreasing evidence for its estimates of states of the world as evidence that it is too confident about those states. 
    - **This can be implemented fairly simply with the augmented Bayesian update**
    
### Why did they do it that way?
- The **free-energy principle has been proposed as a unified Bayesian account of perception, learning and action.** 
- Despite the inextricable link between emotion and cognition, emotion has not yet been formulated under a unified Bayesian framework. 
  - A core concept that permeates many perspectives on emotion is valence, which broadly refers to the positive and negative character of emotion or some of its aspects. 
- Despite the major role attributed to emotions in influencing the content and the strength of the agent's beliefs and the resistance of these beliefs to modification [19], emotion has not been considered in - much less integrated into - these computational models.

### How is it useful to me?
- they  propose a mathematical definition of emotional valence in terms of the negative rate of change of free-energy over time. 
  - This formalism entails the dynamic attribution of emotional valence to every state of the world that an adaptive agent might visit and prescribes the dynamics of basic forms of emotion such as happiness, unhappiness, hope, fear, disappointment and relief.
- They present a computational model of emotional valence. 
  - They demonstrate this scheme by simulating and comparing two artificial agents. 
    1. One explicitly optimises posterior beliefs about volatility and does not use its internally generated emotional valence signal. 
    2. The other does not estimate volatility but instead implements the emotional regulation of estimation uncertainty. 

- The contribution of this work is two-fold. 
  1. They provide a phenomenological account of emotion in terms of changes in free energy - as a proxy for changes in the quality of how the world is being modelled during inference and learning. 
  2. Emotion is coupled back to inference using a form of regularization or meta-learning. In other words, changes in the quality of inference are used to regularize the rate of evidence accumulation to provide adaptive learning rates. These learning rates correspond to expected uncertainty about inferences, under hierarchical models of the world.

- **this article presents the free-energy principle that was easiest for me to understand... relatively speaking**

- In biologically plausible implementations of free energy minimisation, precision (i.e., the inverse of uncertainty) is encoded by the gain of cells reporting prediction error. 
  - This directly implicates the classical ascending neuromodulatory transmitter systems like dopamine, acetylcholine and norepinephrine in the encoding of uncertainty. 

### Possibly Relevant Background Literature From Article
1. Payzan-LeNestour E, Bossaerts P (2011) Risk, unexpected uncertainty, and estimation uncertainty: Bayesian learning in unstable settings. PLoS Comput Biol 7: e1001048.
https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1001048

2. Behrens TEJ, Woolrich MW, Walton ME, Rushworth MFS (2007) Learning the value of information in an uncertain world. Nature Neuroscience 10: 1214???1221.
https://www.nature.com/articles/nn1954


3. Daunizeau J, den Ouden HEM, Pessiglione M, Kiebel SJ, Friston K, et al. (2010) Observing the observer (II): deciding when to decide. PLoS ONE 5: e15555.
https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0015555










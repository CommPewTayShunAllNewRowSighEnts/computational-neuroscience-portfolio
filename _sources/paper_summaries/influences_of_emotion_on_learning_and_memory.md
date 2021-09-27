# The Influences of Emotion on Learning and Memory

## Paper Review 

**Paper:** [Tyng, C. M. (2017)](https://doi.org/10.3389/fpsyg.2017.01454)

### What questions are the researchers trying to answer?
- The aim of this current article was to highlight an evolutionary approach to emotion, which may facilitate understanding of the effects of emotion on learning and memory. 

### What is the researcher doing?
- Presents the terminology used in affective neuroscience studies, 
- describe the **roles of emotion and motivation in learning and memory** 
- outlines the evolutionary framework and the **seven primary emotional system**. 
- outlines emotional-cognitive interactions in the various brain regions that are intimately involved in **emotion and memory systems**
  - **This is performed to define the congruent interactions in these regions are associated with long-term memory (LTM) retention.**
- discuss the emerging studies that further our understanding of emotional effects deriving from different modalities of emotional content.
- discusses four major functional neuroimaging techniques, including 
  - functional magnetic resonance imaging (fMRI) 
  - positron emission tomography (PET) 
  - electroencephalography (EEG), and 
  - functional near-infrared spectroscopy (fNIRS)
- presents the **important factors for consideration in experimental design**
- describe psychiatric disorders, such as depression and anxiety, which are emotionally charged dysfunctions that are strongly detrimental to cognitive performance
- remarks on the current issues and future research possibilities with respect to the efficient enhancement of educational practices and technologies

### Why did they do it that way?
- this was a very interesting review paper on a subject that could be quite impactful, there is no experiments here though.

### What are other ways of doing it?
According to Tyng several remaining questions should be addressed in future studies, including:
  1. the **impact of emotion on semantic knowledge encoding and retrieval** 
  2. psychological and physiological changes associated with semantic learning and memory, 
  3. the development of methods that incorporate emotional and motivational aspects that improve educational praxes, outcomes, and instruments. 

### How is it useful to me?
- Emotion has a substantial influence on the cognitive processes in humans, including perception, attention, **learning**, **memory**, reasoning, and **problem-solving**. 
  - I would like to see the impact of incorporating emotional states on these cognitive processes
  - Emotion has a particularly strong influence on attention, 
    - especially modulating the selectivity of attention 
    - as well as motivating action and behavior. 
    - This attentional and executive control is intimately linked to **learning processes**, 
      - as intrinsically limited attentional capacities are better focused on relevant information.
      - **can we use emotional states to influence where a robot directs its attention?**
  - Emotion also facilitates encoding and helps retrieval of information efficiently.
    - **How can we incorporate this model into Nengo?**
  - the effects of emotion on learning and memory are not always univalent, 
    - studies have reported that emotion either enhances or impairs learning and long-term memory (LTM) retention, depending on a range of factors.
      - **Can this be replicated in simulation?**
  - Recent neuroimaging findings have indicated that the amygdala and prefrontal cortex cooperate with the medial temporal lobe in an integrated manner that affords 
    1. the amygdala modulating memory consolidation; 
    2. the prefrontal cortex mediating memory encoding and formation; and 
    3. the hippocampus for successful learning and LTM retention.
- Emotional experiences/stimuli appear to be remembered vividly and accurately, with great resilience over time.
- Three different approaches are used to monitor the changes in emotional states: 
   1. ~~subjective approaches that assess subjective feelings and experiences;~~ *unfortunately I cannot know the subjective experience of a robot*
   2. behavioral investigations of 
      1. facial expressions (Jack and Schyns, 2015), 
      2. vocal expressions (Russell et al., 2003), and 
      3. gestural changes (Dael et al., 2012); and 
   3. objective approaches via physiological responses that include 
      1. electrical and hemodynamic of the central nervous system (CNS) activities (Vytal and Hamann, 2010) - *could be incorporated into a spiking NN*
      2. in addition to autonomic nervous system (ANS) responses such as 
         1. heart rate, 
         2. respiratory volume/rate, 
         3. skin temperature, 
         4. skin conductance and 
         5. blood volume pulses (Li and Chen, 2006).
- it describes the roles of emotion and motivation in learning and memory, 
- it outlines the **seven primary emotional system**
- outlines emotional-cognitive interactions in the various brain regions that are intimately involved in emotion and memory systems
  - **This is performed to define the congruent interactions in these regions are associated with long-term memory (LTM) retention.**
- Substantial evidence has established that emotional events are remembered more clearly, accurately and for longer periods of time than are neutral events.
  - If this can be replicated in simulation it would provide a lot of value to the pursuit of AGI
- activation of the amygdala:
  - enhances the processing of emotionally arousing stimuli 
  - modulates enhanced memory consolidation along with other memory-related brain regions, particularly the amygdala, hippocampus, MTL, as well as the visual, frontal and parietal cortices.
- activation of the PFC 
  - enhances cognitive functions, such as strategic and semantic processing that affect WM and also promote the establishment of LTM.
- Previous studies have primarily used standardized emotional visual, or auditory stimuli such as pictures, words, facial expression, and film clips, often based on the IAPS, ANEW, and POFA databases for emotional pictures, words and facial expressions, respectively.
  - **What standardized data could we use in simulation?**
- the SEEKING system generates positive subjective emotional states-positive expectancy, enthusiastic exploration, and hopefulness, apparently, initiates learning and memory in the brain. **wow!**
- **All cognitive activity is motivated from ‘underneath’ by basic emotional and homeostatic needs (motivational drives) that explore environmental events for survival while facilitating secondary processes of learning and memory.**

#### Many opportunities for study: 
- To their knowledge, there are few objective studies that employed brain-mapping techniques to examine semantic memory of learning materials (using subject matter) in the education context. 
- influences derived from emotional factors in human learning and memory remains unclear as to whether positive emotions facilitate learning or negative emotions impair learning and vice versa.


### Background Literature Review
#### [Vuilleumier, 2005](https://www.cell.com/trends/cognitive-sciences/fulltext/S1364-6613(05)00302-5?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS1364661305003025%3Fshowall%3Dtrue)
- reported that the cognitive process attention is affected by emotions in humans

#### [Phelps, 2004](https://www.sciencedirect.com/science/article/abs/pii/S0959438804000479?via%3Dihub); [Um et al., 2012](https://doi.apa.org/doiLanding?doi=10.1037%2Fa0026609)
- reported that the cognitive process learning and memory is affected by emotions in humans

#### [Jung et al., 2014](https://www.frontiersin.org/articles/10.3389/fpsyg.2014.00570/full)
- reported that the cognitive process reasoning is affected by emotions in humans

#### [Isen et al., 1987](https://doi.apa.org/doiLanding?doi=10.1037%2F0022-3514.52.6.1122)
- reported that the cognitive process problem-solving is affected by emotions in humans

#### [Pekrun, 1992](https://iaap-journals.onlinelibrary.wiley.com/doi/10.1111/j.1464-0597.1992.tb00712.x); [Seli et al., 2016](https://www.jneurosci.org/content/23/34/10809.short)
- linked attentional and motivational components of emotion to heightened learning and memory.
  - Hence, emotional experiences/stimuli appear to be remembered vividly and accurately, with great resilience over time.

#### [Jack and Schyns, 2015](https://www.cell.com/current-biology/fulltext/S0960-9822(15)00655-7?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS0960982215006557%3Fshowall%3Dtrue)
- monitor the changes in emotional states using behavioral investigations of facial expressions

#### [Russell et al., 2003](https://www.annualreviews.org/doi/10.1146/annurev.psych.54.101601.145102)
- monitor the changes in emotional states using behavioral investigations of vocal expressions

#### [Dael et al., 2012](https://doi.apa.org/doiLanding?doi=10.1037%2Fa0025737)
- monitor the changes in emotional states using behavioral investigations of gestural changes  

#### [Vytal and Hamann, 2010](https://direct.mit.edu/jocn/article/22/12/2864/5011/Neuroimaging-Support-for-Discrete-Neural)
- monitor the changes in emotional states using physiological responses that include electrical and hemodynamic of the central nervous system (CNS) activities 

#### [Li and Chen, 2006](https://link.springer.com/chapter/10.1007%2F11941354_44)
- monitor the changes in emotional states using physiological responses that include the autonomic nervous system (ANS) with responses such as: 
  1. heart rate
  2. respiratory volume/rate 
  3. skin temperature
  4. skin conductance and 
  5. blood volume pulses 

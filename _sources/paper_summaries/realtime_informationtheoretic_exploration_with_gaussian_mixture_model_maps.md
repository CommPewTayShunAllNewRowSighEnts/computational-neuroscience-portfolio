# Real-time Information-Theoretic Exploration with Gaussian Mixture Model Maps

## Paper Review 

**Paper:** [Tabib, W. (2019)](http://www.roboticsproceedings.org/rss15/p61.pdf)

### What is the researcher doing?
- develops an exploration framework that leverages Gaussian mixture models (GMMs) for high-fidelity perceptual modeling and exploits the compactness of the distributions for information sharing in communications-constrained applications.

### Why did they do it that way?
- State-of-the-art, high-resolution perceptual modeling techniques do not always consider the implications of transferring the model across limited bandwidth communications channels, which is critical for real-time information sharing. 
  - To bridge this gap in the state of the art, this paper presents a system that compactly represents sensor observations as GMMs and maintains a local occupancy grid map for a sampling-based motion planner that maximizes an information-theoretic objective function.
- A motion planner is designed to select smooth and continuous trajectories that maximize an information-theoretic objective function.

### What are other ways of doing it?

### How is it useful to me?
- The motion planner that is designed to select smooth and continuous trajectories that maximize an information-theoretic objective function.
- I don't have a background in information theory yet, so this might be too challenging for me in the near future. 

### Background Literature Review
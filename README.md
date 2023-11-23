# ConceptGraph for the CALVIN Challenges

 **This repository presents the step by step implementation to apply the approach of the concept graph on CALVIN Environment.**

[Concept graph](https://concept-graphs.github.io/): This is the official page of the conceptgraph.  [Concept Graph -GitHub](https://github.com/concept-graphs/concept-graphs)


[Calvin](http://calvin.cs.uni-freiburg.de/): This is the offical leaderborad page of the CAVLIN.   [Calvin Github](https://github.com/mees/calvin)


Goal of this repository: To apply the approach of the concept graph on CALVIN environment.

**Introduction to the CALVIN:**

The focus is on the challenges and goals associated with integrating general-purpose robots into human environments. The key emphasis is on the robots' ability to comprehend and act upon human language, translating it into meaningful perceptions and actions necessary for various daily tasks. To achieve this, the authors introduce CALVIN (Composing Actions from Language and Vision), an open-source simulated benchmark designed to facilitate the learning of long-horizon, language-conditioned tasks by robotic agents.

The primary objective of CALVIN is to enable the development of agents capable of solving complex robotic manipulation tasks over extended periods, relying solely on onboard sensors and instructions provided in human language. The tasks presented in CALVIN are described as more intricate compared to existing vision-and-language datasets, involving greater sequence length, a broader action space, and more sophisticated language specifications. The benchmark also supports flexible configuration of sensor suites.

**Introduction to Concept Graph:**
The focus is on addressing the need for robots to possess a semantically rich 3D representation of the world, which is both compact and efficient for task-driven perception and planning. Existing approaches that leverage features from large vision-language models to encode semantics in 3D representations face challenges, particularly in scalability and the lack of semantic spatial relationships between entities in larger environments, crucial for downstream planning tasks. To overcome these limitations, the authors propose ConceptGraphs, an open-vocabulary graph-structured representation for 3D scenes.

ConceptGraphs are constructed by leveraging 2D foundation models and integrating their outputs into 3D through multiview association. Unlike conventional approaches, ConceptGraphs offer a generalized representation that extends to novel semantic classes without requiring extensive data collection or model fine-tuning. The utility of this representation is demonstrated through various downstream planning tasks specified through abstract language prompts, which demand complex reasoning over both spatial and semantic concepts. The proposed ConceptGraphs present a promising solution to enhance the effectiveness of robotic systems in understanding and navigating dynamic 3D environments for diverse tasks.



Step 1: Download the CALVIN dataset from the given link. There are four scenarios. For the debugging there is a dataset of size 1.3GB otherewise all the remaining datasets size are above than 150Bs. So intially, download the any one dataset locally.

Download the dataset based on the space and task.
1.  [Split D->D](http://calvin.cs.uni-freiburg.de/dataset/task_D_D.zip) (166 GB)
2.  [Split ABC->D](http://calvin.cs.uni-freiburg.de/dataset/task_ABC_D.zip) (517 GB)
3.  [Split ABCD->D](http://calvin.cs.uni-freiburg.de/dataset/task_ABCD_D.zip) (656 GB)
4. [Small debug dataset](http://calvin.cs.uni-freiburg.de/dataset/calvin_debug_dataset.zip) (1.3 GB)
   


```

```

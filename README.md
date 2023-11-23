# ConceptGraph for the CALVIN Challenges

 **This repository presents the step by step implementation to apply the approach of the concept graph on CALVIN Environment.**

[Concept graph](https://concept-graphs.github.io/): This is the official page of the conceptgraph.  [Concept Graph -GitHub](https://github.com/concept-graphs/concept-graphs)


[Calvin](http://calvin.cs.uni-freiburg.de/): This is the offical leaderborad page of the CAVLIN.   [Calvin Github](https://github.com/mees/calvin)


Goal of this repository: To apply the approach of the concept graph on CALVIN environment.

**Introduction to the CALVIN:**

The focus is on the challenges and goals associated with integrating general-purpose robots into human environments. The key emphasis is on the robots' ability to comprehend and act upon human language, translating it into meaningful perceptions and actions necessary for various daily tasks. To achieve this, the authors introduce CALVIN (Composing Actions from Language and Vision), an open-source simulated benchmark designed to facilitate the learning of long-horizon, language-conditioned tasks by robotic agents.

The primary objective of CALVIN is to enable the development of agents capable of solving complex robotic manipulation tasks over extended periods, relying solely on onboard sensors and instructions provided in human language. The tasks presented in CALVIN are described as more intricate compared to existing vision-and-language datasets, involving greater sequence length, a broader action space, and more sophisticated language specifications. The benchmark also supports flexible configuration of sensor suites.

**Introduction to Concept Graph:**
The Concept Graph shows the imperative for robots to possess a semantically rich 3D representation of the world for efficient task-driven perception and planning. Current approaches using large vision-language models face challenges in scalability and lack of semantic spatial relationships, crucial for effective planning in larger environments. To address these issues, the authors introduce ConceptGraphs, a graph-structured representation for 3D scenes. Constructed by integrating outputs from 2D foundation models through multiview association, ConceptGraphs provide a generalized representation extending to novel semantic classes without extensive data collection or model fine-tuning. The utility of ConceptGraphs is demonstrated through diverse downstream planning tasks specified via abstract language prompts, showcasing their potential to enhance robotic systems' effectiveness in navigating dynamic 3D environments.



Step 1: Download the CALVIN dataset from the given link. There are four scenarios. For the debugging there is a dataset of size 1.3GB otherewise all the remaining datasets size are above than 150Bs. So intially, download the any one dataset locally.

Download the dataset based on the space and task.
1.  [Split D->D](http://calvin.cs.uni-freiburg.de/dataset/task_D_D.zip) (166 GB)
2.  [Split ABC->D](http://calvin.cs.uni-freiburg.de/dataset/task_ABC_D.zip) (517 GB)
3.  [Split ABCD->D](http://calvin.cs.uni-freiburg.de/dataset/task_ABCD_D.zip) (656 GB)
4. [Small debug dataset](http://calvin.cs.uni-freiburg.de/dataset/calvin_debug_dataset.zip) (1.3 GB)
   


```

```

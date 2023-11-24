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



**Step 1:** Download the CALVIN dataset from the given link. There are four scenarios. For the debugging there is a dataset of size 1.3GB otherewise all the remaining datasets size are above than 150Bs. So intially, download the any one dataset locally.

Download the dataset based on the space and task.
1.  [Split D->D](http://calvin.cs.uni-freiburg.de/dataset/task_D_D.zip) (166 GB)
2.  [Split ABC->D](http://calvin.cs.uni-freiburg.de/dataset/task_ABC_D.zip) (517 GB)
3.  [Split ABCD->D](http://calvin.cs.uni-freiburg.de/dataset/task_ABCD_D.zip) (656 GB)
4. [Small debug dataset](http://calvin.cs.uni-freiburg.de/dataset/calvin_debug_dataset.zip) (1.3 GB)
   

#  Visualization of the CALVIN data



```
actions
[ 0.10014743 -0.09120568  0.57087628  3.09732095  0.02088518  1.50079385
  1.        ]

rel_actions
[-1.07006856e-02  1.15504107e-02  1.77918208e-04 -9.64466816e-02
  7.23821376e-04  8.83792502e-04  1.00000000e+00]

robot_obs
[ 0.10036145 -0.09143668  0.57087272  3.10214328  0.02084899  1.50074966
  0.07999974 -0.59011412  0.89867477  1.74402731 -1.84388101 -0.92408956
  1.59611532  0.58673495  1.        ]

scene_obs
[ 8.80929092e-05 -1.53721945e-34  0.00000000e+00  1.93132547e-17
  0.00000000e+00  0.00000000e+00  2.32403619e-01 -4.04295856e-02
  4.59990009e-01  4.12287744e-08 -8.05700103e-09 -2.17741510e+00
 -2.83642665e-01  8.05351014e-02  4.60989238e-01 -1.10251078e-05
 -5.25663348e-05 -9.06438129e-01  1.28661989e-01 -3.77756105e-02
  4.59989266e-01  1.10200730e-04  3.19760378e-05 -3.94522179e-01]

rgb_static
[[[221 221 221]
  [221 221 221]
  [221 221 221]
  ...
  [254 254 254]
  [254 254 254]
  [254 254 254]]

 [[221 221 221]
  [221 221 221]
  [221 221 221]
  ...
  [254 254 254]
  [254 254 254]
  [254 254 254]]

 [[221 221 221]
  [221 221 221]
  [221 221 221]
  ...
  [252 252 252]
  [252 252 252]
  [251 251 251]]

 ...

 [[177 177 177]
  [177 177 177]
  [176 176 176]
  ...
  [232 232 232]
  [228 228 228]
  [224 224 224]]

 [[178 178 178]
  [177 177 177]
  [177 177 177]
  ...
  [254 254 254]
  [254 254 254]
  [234 234 234]]

 [[178 178 178]
  [178 178 178]
  [177 177 177]
  ...
  [254 254 254]
  [246 246 246]
  [216 216 216]]]

rgb_gripper
[[[165 165 165]
  [165 165 165]
  [165 165 165]
  ...
  [167 167 167]
  [167 167 167]
  [167 167 167]]

 [[136 102  69]
  [137 104  70]
  [182 182 182]
  ...
  [100 100 100]
  [100 100 100]
  [100 100 100]]

 [[135 101  68]
  [136 102  69]
  [182 182 182]
  ...
  [ 96  96  96]
  [ 96  96  96]
  [ 93  93  93]]

 ...

 [[169 169 169]
  [166 166 166]
  [162 162 162]
  ...
  [254 254 254]
  [254 254 254]
  [254 254 254]]

 [[171 171 171]
  [167 167 167]
  [164 164 164]
  ...
  [254 254 254]
  [254 254 254]
  [254 254 254]]

 [[172 172 172]
  [169 169 169]
  [165 165 165]
  ...
  [254 254 254]
  [254 254 254]
  [254 254 254]]]

rgb_tactile
[[[215 129 106 232 130 115]
  [221 133 120 229 135 109]
  [224 123 115 210 126 117]
  ...
  [129 225 115 127 233 116]
  [140 227 111 129 231 118]
  [135 228 116 135 232 108]]

 [[219 131 116 230 132 125]
  [216 150 120 222 122 121]
  [232 133 115 224 125 131]
  ...
  [127 228 105 140 226 111]
  [129 219 115 151 223 111]
  [130 222 112 115 222 126]]

 [[225 138 121 225 142 111]
  [224 137  99 222 117 116]
  [218 120 120 219 139 103]
  ...
  [135 233 122 137 225 114]
  [136 226 104 144 238 120]
  [146 231 115 133 229 118]]

 ...

 [[137 104 204 151 113 202]
  [144 106 200 141 109 212]
  [147 109 197 137 109 202]
  ...
  [111 140 203 110 142 201]
  [109 155 197 122 147 187]
  [ 96 149 208 109 153 201]]

 [[150 124 203 136 114 197]
  [143 111 200 135 120 200]
  [156 118 202 156 114 187]
  ...
  [116 145 207 114 146 199]
  [105 141 201 117 145 199]
  [108 147 197 103 144 209]]

 [[146 115 205 143 112 210]
  [138  96 202 130 109 203]
  [148 114 191 141 109 191]
  ...
  [112 141 192 106 144 194]
  [110 140 203 117 159 193]
  [ 98 141 207 114 142 208]]]


depth_static
[[6.2016563 6.195427  6.1895757 ... 5.198949  5.1945705 5.1904564]
 [6.1921344 6.1862893 6.180091  ... 5.1922555 5.188145  5.183785 ]
 [6.1826415 6.1768146 6.170635  ... 5.1855793 5.1814795 5.1771307]
 ...
 [4.195479  4.1979985 4.2006893 ... 4.147848  4.1452246 4.142441 ]
 [4.195479  4.1979985 4.2006893 ... 4.1435866 4.1409683 4.1381903]
 [4.1958146 4.1983347 4.2006893 ... 4.1393337 4.136721  4.1339483]]

depth_gripper
[[0.08285692 0.08285855 0.08286027 ... 0.0829769  0.0829794  0.08298187]
 [0.23066188 0.23092732 0.09075869 ... 0.22406636 0.22432701 0.22458768]
 [0.23302822 0.2332988  0.09248736 ... 0.22596489 0.22624768 0.22653729]
 ...
 [0.49752724 0.5067818  0.51638883 ... 0.63771814 0.6381353  0.63855064]
 [0.4920755  0.501128   0.5120094  ... 0.6351566  0.6355656  0.63597757]
 [0.4867504  0.49716455 0.50803715 ... 0.63261074 0.63301885 0.63342756]]

depth_tactile
[[[0. 0.]
  [0. 0.]
  [0. 0.]
  ...
  [0. 0.]
  [0. 0.]
  [0. 0.]]

 [[0. 0.]
  [0. 0.]
  [0. 0.]
  ...
  [0. 0.]
  [0. 0.]
  [0. 0.]]

 [[0. 0.]
  [0. 0.]
  [0. 0.]
  ...
  [0. 0.]
  [0. 0.]
  [0. 0.]]

 ...

 [[0. 0.]
  [0. 0.]
  [0. 0.]
  ...
  [0. 0.]
  [0. 0.]
  [0. 0.]]

 [[0. 0.]
  [0. 0.]
  [0. 0.]
  ...
  [0. 0.]
  [0. 0.]
  [0. 0.]]

 [[0. 0.]
  [0. 0.]
  [0. 0.]
  ...
  [0. 0.]
  [0. 0.]
  [0. 0.]]]


```

# Multi-Actor-Critic
Recurrent DDPG: Empirical Insights into Future Market Trading on FIMTX

## Abstract
The financial markets present complex challenges for traders seeking adaptive and profitable strategies. Deep learning approaches, including Recurrent Deep Deterministic Policy Gradient (RDPG), have gained in‐ terest for enhancing trading performance.
RDPG combines recurrent neural networks (RNNs) and deep reinforce‐ ment learning to capture sequential dependencies and time‐sensitive patterns in market data.
Our final project focuses on employing RDPG for future market trading. We evaluate its performance on historical market data and compare it with traditional strategies. This final project offers insights into the al‐ gorithm’s ability to generate consistent returns and adapt to evolving market conditions.

## Methodology
Quantitative trading can be formulated as a partially observable Markov Decision Process (POMDP), wherein the observation is derived from fu‐ ture price, volume, and moving average history. In this formulation, the action space consists of real numbers ranging from ‐1 to 1. Negative actions represent short positions, positive actions represent long posi‐ tions, and the absolute value of the action represents the fraction of the asset to be invested. The reward function is defined in equation 1.

<img width="645" alt="image" src="https://github.com/jeannineshiu/Multi-Actor-Critic/assets/43820595/7fecf41d-c66b-4d6d-9c76-466c172d9899">

The action space, represented by a real number between ‐1 and 1, pro‐ vides flexibility for the trading agent to decide on the position (short or long) and the fraction of the asset to invest. This continuous action space enables fine‐grained control over investment strategies, allowing the agent to adjust the position and allocation according to its learned policy and market conditions.
By formulating quantitative trading as a POMDP, we leverage RDPG to learn optimal trading policies for day trading. The agent learns to select actions that maximize its expected future rewards, considering the uncertainties and partial observability of the market.
During the training process, we also incorporated behavior cloning as an additional component. Our training policy aimed to emulate a prophetic strategy, consistently adopting a long position at the lowest price and a short position at the highest price.
By leveraging expert actions, we established specific goals for each train‐ ing step, effectively minimizing inefficient exploration phases.

<img width="297" alt="image" src="https://github.com/jeannineshiu/Multi-Actor-Critic/assets/43820595/dcb59a8d-5900-43c4-b0c5-5e4ad10944bb">


## Experimental result
In this final project, we utilize the FIMTX future(小 台 指 期 貨) dataset as the foundation for our analysis and training process. Details of the training and testing periods are specified in Table 1. Figure 1 exhibits the outcomes achieved on the testing set, providing a visual representation of the performance during the evaluation phase. Additionally, Figure 2 illustrates the future price trend observed exclusively throughout the testing period.

<img width="644" alt="image" src="https://github.com/jeannineshiu/Multi-Actor-Critic/assets/43820595/3ea6b528-1c95-4e75-967c-25e1d801a315">

<img width="561" alt="image" src="https://github.com/jeannineshiu/Multi-Actor-Critic/assets/43820595/71a14167-b4ae-4045-bc1d-4e851ce17768">



## File Usage

### component_agent.py
component agent class

### crawl.py
爬取資料

### env.py
environment

### postprocess.py
從爬取後的資料計算其他資料(從Open price計算moving average)

### train.py
訓練agent

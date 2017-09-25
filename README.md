# intellisched
Repository for making credit2 scheduler of Xen intelligent i.e dynamically adjust the configuration to give maximum performance

I want to make scheduler dynamic so that it can give maximum performance based on the different workload by adjusting its configuration. To start with a simple case I have chosen runqueu configuration.

#problem Statement :

Consider a simple usecase: The person who doesn’t have much knowledge about the scheduler will have a hard time configurig the runqueue type. And even if he knows, the workloads are dynamic and constantly change and require different runqueue configuration to give the max performance.

Solution:

What I propose is to dynamically adjust the runqueue type per cpupool, based on the workload to get the maximum performance.

#High Level Design:

Fetch the performance related data from scheduler ——-> feed into Regression Algorithm OR Classification Algorithm (AI) which trains itself by constant stream of perforamnce number and gives the best fitted runqueue —-> dynamically change the runqueue type for the scheduler.

The problems that I can forsee:

1) what all trace data we can use from scheduler that can help to deduce the performance at a given instance.

2) how to pass scheduler data from the scheduler to the userspace and share it with third party library.

3) Which third party library to use for analyzing the data. Which algo to use..

4) Licensing issues.

5) Currently runqueue configuration is static and can’t be set dynamically.

Here the main challenge will be to collect the scheduler specific data that we can treat as the training data. I am looking at some of the chess playing learning algorithms to understand how they are making computer to learn about the best possible moves ie. building the training set on the fly and improve after each run.

Some references that I found:
https://erikbern.com/2014/11/29/deep-learning-for-chess.html

https://github.com/erikbern/deep-pink

deepchess-end-to-end-deep-neural-network-for-automatic-learning-in-chess.pdf

Anshul Makkar

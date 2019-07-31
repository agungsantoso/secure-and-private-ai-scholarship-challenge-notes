# Secure and Private AI Scholarship Challenge 2019 Notes


![GitHub](https://img.shields.io/github/license/mashape/apistatus.svg)

<p align="center">
  <img src="./assets/badge.png" width="25%">
</p>

A collection of notes on Secure and Private AI Scholarship Challenge 2019.

Contributions are always welcome!

<!-- toc -->

- [Lesson 3: Introducing Differential Privacy](#lesson-3-introducing-differential-privacy)
  * [Secure & Private AI Program Introduction](#secure--private-ai-program-introduction)
  * [Lesson 1 Introduction](#lesson-1-introduction)
  * [What Is Differential Privacy (DP)](#what-is-differential-privacy-dp)
  * [Can We Just Anonymize Data](#can-we-just-anonymize-data)
  * [Introducing The Canonical Database](#introducing-the-canonical-database)
  * [Project Intro Build A Private Database In Python](#project-intro-build-a-private-database-in-python)
  * [Notebook Exercise Instructions](#notebook-exercise-instructions)
  * [Project Demo Build A Private Database In Python](#project-demo-build-a-private-database-in-python)
- [Lesson 4: Evaluating the Privacy of a Function](#lesson-4-evaluating-the-privacy-of-a-function)
  * [Evaluating The Privacy Of A Function](#evaluating-the-privacy-of-a-function)
  * [Project Intro Evaluating The Privacy Of A Function](#project-intro-evaluating-the-privacy-of-a-function)
  * [Project Demo Evaluating The Privacy Of A Function](#project-demo-evaluating-the-privacy-of-a-function)
  * [Project Intro Calculate L1 Sensitivity For Threshold](#project-intro-calculate-l1-sensitivity-for-threshold)
  * [Project Demo Calculate L1 Sensitivity For Threshold](#project-demo-calculate-l1-sensitivity-for-threshold)
  * [Project Intro Perform A Differencing Attack](#project-intro-perform-a-differencing-attack)
  * [Project Demo Perform A Differencing Attack](#project-demo-perform-a-differencing-attack)
- [Lesson 5: Introducing Local and Global Differential Privacy](#lesson-5-introducing-local-and-global-differential-privacy)
  * [Introducing Local and Global Differential Privacy](#introducing-local-and-global-differential-privacy)
  * [Making a Function Differentially Private](#making-a-function-differentially-private)
  * [Project Intro Implement Local Differential Privacy](#project-intro-implement-local-differential-privacy)
  * [Project Demo Implement Local Differential Privacy](#project-demo-implement-local-differential-privacy)
  * [Project Intro Varying the Amount of Noise](#project-intro-varying-the-amount-of-noise)
  * [Project Demo Varying the Amount of Noise](#project-demo-varying-the-amount-of-noise)
  * [The Formal Definition of Differential Privacy](#the-formal-definition-of-differential-privacy)
  * [Create a Differentially Private Query](#create-a-differentially-private-query)
  * [Project Demo Create a Differentially Private Query](#project-demo-create-a-differentially-private-query)
- [Lesson 6: Differential Privacy for Deep Learning](#lesson-6-differential-privacy-for-deep-learning)
  * [Differential Privacy for Deep Learning](#differential-privacy-for-deep-learning)
  * [Project Intro Example Scenario Deep Learning in a Hospital](#project-intro-example-scenario-deep-learning-in-a-hospital)
  * [Generating Differentially Private Labels For a Dataset](#generating-differentially-private-labels-for-a-dataset)
  * [PATE Analysis](#pate-analysis)
  * [Where to Go From Here](#where-to-go-from-here)
  * [Final Project Description](#final-project-description)
  * [Guest Interview: Differential Privacy at Apple](#guest-interview-differential-privacy-at-apple)
  * [Guest Interview: Privacy and Society - OpenAI](#guest-interview-privacy-and-society---openai)
- [Lesson 7: Federated Learning](#lesson-7-federated-learning)
  * [Introducing Federated Learning](#introducing-federated-learning)
  * [Introducing PySyft](#introducing-pysyft)
  * [Introducing OpenMined and Installing PySyft](#introducing-openmined-and-installing-pysyft)
  * [Basic Remote Execution in PySyft](#basic-remote-execution-in-pysyft)
  * [Playing with Remote Tensors](#playing-with-remote-tensors)
  * [Introducing Remote Arithmetic in PySyft](#introducing-remote-arithmetic-in-pysyft)
  * [Learn a Simple Linear Model](#learn-a-simple-linear-model)
  * [Garbage Collection and Common Errors](#garbage-collection-and-common-errors)
  * [Toy Federated Learning](#toy-federated-learning)
  * [Advanced Remote Execution Tools](#advanced-remote-execution-tools)
  * [PointerChain Operations](#pointerchain-operations)
  * [Final Project Description](#final-project-description-1)
  * [Guest Interview: Federated Learning at Google](#guest-interview-federated-learning-at-google)
  * [Notebook](#notebook)
- [Lesson 8: Securing Federated Learning](#lesson-8-securing-federated-learning)
  * [Securing Federated Learning](#securing-federated-learning)
  * [Project Demo Federated Learning with Trusted Aggregator](#project-demo-federated-learning-with-trusted-aggregator)
  * [Intro to Additive Secret Sharing](#intro-to-additive-secret-sharing)
  * [Fixing Additive Secret Sharing](#fixing-additive-secret-sharing)
  * [Project Intro Build Methods for Encrypt Decrypt and Add](#project-intro-build-methods-for-encrypt-decrypt-and-add)
  * [Project Demo - Build Methods for Encrypt, Decrypt, and Add](#project-demo---build-methods-for-encrypt-decrypt-and-add)
  * [Intro to Fixed Precision Encoding](#intro-to-fixed-precision-encoding)
  * [Secret Sharing and Fixed Precision in PySyft](#secret-sharing-and-fixed-precision-in-pysyft)
  * [Final Project Description](#final-project-description-2)
- [Lesson 9: Encrypted Deep Learning](#lesson-9-encrypted-deep-learning)
  * [Introducing Encrypted Deep Learning](#introducing-encrypted-deep-learning)
  * [Encrypted Subtraction and Public Multiplication](#encrypted-subtraction-and-public-multiplication)
  * [Encrypted Computation in PySyft](#encrypted-computation-in-pysyft)
  * [Project Intro - Build an Encrypted Database](#project-intro---build-an-encrypted-database)
  * [Project Demo - Build an Encrypted Database](#project-demo---build-an-encrypted-database)
  * [Encrypted Deep Learning in PyTorch](#encrypted-deep-learning-in-pytorch)
  * [Encrypted Deep Learning in Keras](#encrypted-deep-learning-in-keras)
  * [Keystone Project Description](#keystone-project-description)
  * [Secure & Private AI Program Conclusion](#secure--private-ai-program-conclusion)
- [Resources](#resources)
- [Credits](#credits)

<!-- tocstop -->

## Lesson 3: Introducing Differential Privacy
### Secure & Private AI Program Introduction
* When doing artificial intelligence in the real world, most datasets are siloed (isolated) within large enterprises for two reasons:
  1. Enterprises have a legal risk which prevents them form wanting to share their dataset outside their organization
  2. Enterprises have a competitive advantage to hang onto large datasets collected from/about their customers

### Lesson 1 Introduction
* In this lesson we're going to be talking about differential privacy in the context of deep learning.
* In this context, differential privacy is about ensuring that when our neural networks are learning from sensitive data, they're only learning what they're supposed to learn from the data.

### What Is Differential Privacy (DP)
* It's a new field, recently started with statistical database queries around 2003 and even more recently
* General goal of DP is to ensure that different kinds of statistical analysis don't co mpromise privacy
* Privacy is preserved if
  
  After the analysis, the analyzer doesn't know anything about the people in the dataset. They remain "unobserved"
* Dalenius's Ad Omnia Guarantee (1977)
  
  Anything that can be learned about a participant from the statistical database can be learned without access to the database
* Above definition is basically saying, anything you actually do learn about a person should be only public information
* Cynthia Dwork, Algorithmic Foundations of Differential Privacy
  
  "Differential Privacy" describes a promise, made by a data holder, or curator, to a data subject, and the promise is like this: "You will not be affected, adversely or otherwiese, by allowing your data to be used in any study or analysis, no matter what other sudies, data sets, or information sources, are available"
* True goal of DP is to propose these tools and techniques that allow a data holder to make these promises to individuals who are being studied.

### Can We Just Anonymize Data
* We can't just anonymize data because if someone else releases a related anonymized private dataset, often it can be possible to divulge the private aspects of the information you're trying to hide by studiying these two separate dataset releases.

### Introducing The Canonical Database
* Simple (canonical) database is A database with a single column with one row for each person
* If we remove a person from the database, and the query does not change, then that person's privacy is fully protected.
* If the query doesn't change even we remove someone from the database, then that person wasn't leaking any statistical information into the output of the query.

### Project Intro Build A Private Database In Python
* Write a sort of function that makes it so that you can take this database and create 5000 other databases each with one person missing
* You should end up with 5000 databases of length 4999

### Notebook Exercise Instructions

### Project Demo Build A Private Database In Python
* [Project: Generate Parallel Databases](https://colab.research.google.com/github/agungsantoso/private-ai/blob/master/Section%201%20-%20Differential%20Privacy.ipynb#)


## Lesson 4: Evaluating the Privacy of a Function
### Evaluating The Privacy Of A Function
* Compare the output of the query on the entire database with the output of the query on each of the parallel databases
* Sensitivity (L1) is the maximum amount that the query changes when removing an individual from the database
* The output of the sum is conditioned on every individual that is a 1 in the database

### Project Intro Evaluating The Privacy Of A Function
* Create a single function called sensitivity (query, n_entries)
  * Initialize a database of correct size
  * Initialize all parallel databases
  * Run the query over all databases
  * Correctly calculate sensitivity
  * Return the sensitivity

### Project Demo Evaluating The Privacy Of A Function
* [Project - Evaluating the Privacy of a Function](https://colab.research.google.com/github/agungsantoso/private-ai/blob/master/Section%201%20-%20Differential%20Privacy.ipynb)

### Project Intro Calculate L1 Sensitivity For Threshold
* Project 3
  * Create the query() function
  * Create 10 databases of size 10
  * Query each database with a threshold of 5 (calculate sensitivity)
  * Print out the sensitivity of each database

### Project Demo Calculate L1 Sensitivity For Threshold
* [Project: Calculate L1 Sensitivity For Threshold](https://colab.research.google.com/github/agungsantoso/private-ai/blob/master/Section%201%20-%20Differential%20Privacy.ipynb)

### Project Intro Perform A Differencing Attack
* In this concept, we're going to explore how to compromise or attack differential privacy
* All we would have to do is query for the sum of the entire database and then the sum of the entire database without that person. In SQL, this might look something like this
  * SELECT count(*) from my_cancer_database;
  * SELECT count(*) from my_cancer_database WHERE person_name != "john doe";
* The purpose of this exercise is to give you an intuition for how privacy can fail in these environments.

### Project Demo Perform A Differencing Attack
* [Project: Perform a Differencing Attack on Row 10](https://colab.research.google.com/github/agungsantoso/private-ai/blob/master/Section%201%20-%20Differential%20Privacy.ipynb)

## Lesson 5: Introducing Local and Global Differential Privacy
### Introducing Local and Global Differential Privacy
* Local Differential Privacy adds noise to function data points (function inputs)
* Global Differential Privacy adds noise to function outputs
* Trusted Curator is an owner of a database upon which Global Differential privacy is applied. They are trusted to apply DP correctly.

### Making a Function Differentially Private
* Differential Privacy always requires a form of randomness or noise added to the query to protect from things like Differencing Attacks.
* Randomized Response is technique that is used in social sciences when trying to learn about the high level trends for a taboo behavior
  * Have you ever jaywalked, perhaps in the last week?
* Plausible Deniability
  * Flip a coin two times
  * If the first coin flip is heads, answer (yes/no) honestly
  * If the first coin flip is tails, answer according to the second coin flip
* Differential Privacy
  * Most accurate query with the greatest amount of privacy
  * Greatest fit with trust models in the actual world (don't waste trust)

### Project Intro Implement Local Differential Privacy
* Implement randomized response in our database
* Flip two coins by generate two random 1/0 responses in Python
* Report both the true query and the noised query for database sizes 10, 100, 1000, and 10,000

### Project Demo Implement Local Differential Privacy
* [Project: Local Differential Privacy](https://colab.research.google.com/github/agungsantoso/private-ai/blob/master/Section%201%20-%20Differential%20Privacy.ipynb)

### Project Intro Varying the Amount of Noise
* Augment the randomized response query from the previous project to allow for varying amounts of randomness to be added
* Varying the amount of noise
  * Add a new parameter to the query function. It will now accept the database and some noise parameter which is percentage
  * Properly rebalance the result of the query given this adjustable parameter

### Project Demo Varying the Amount of Noise
* [Project: Varying Amounts of Noise](https://colab.research.google.com/github/agungsantoso/private-ai/blob/master/Section%201%20-%20Differential%20Privacy.ipynb)

### The Formal Definition of Differential Privacy
* What we cover so far
  * Local Differential Privacy
  * Differencing Attack
  * Basic queries
  * Sensitivity
  * Differential Privacy definition
  * Global Differential Privacy
* How much noise should we add after the query has been run?
* "Epsilon" and "Delta" measure a threshold for leakage

### Create a Differentially Private Query
* How do we actually use epsilon and delta?
* Randomized mechanism is a function with random noise added to its inputs, outputs, and/or inner workings.
* Global Differential Privacy adds noise to the output of a query.
* Local Differential Privacy adds noise to each data input to the query.
* Privacy budget is how much epsilon/delta leakage we allow for our analysis
* Types of noise
  * Gaussian
  * Laplacian
* How much noise should we add?
  * Type of Noise (Gaussian/Laplacian)
  * Sensitivity of Query
  * Desired Epsilon (E)
  * Desired Delta (d)
* Laplacian noise
  * b = sensitivity(query)/epsilon
  * d always zero
* Laplace function: `np.random.laplace`

### Project Demo Create a Differentially Private Query
* [Project: Create a Differentially Private Query](https://colab.research.google.com/github/agungsantoso/private-ai/blob/master/Section%201%20-%20Differential%20Privacy.ipynb)

## Lesson 6: Differential Privacy for Deep Learning
### Differential Privacy for Deep Learning
* Perfect Privacy is a query to a database returns the same value even if we remove any person from the database
* Perfect Privacy (AI model) is training a model on a dataset should return the same model even if we remove any person from the training dataset
* Two points of complexity
  * Do we always know where "people" are referenced in the dataset?
  * Neural models rarely ever train to the same location, even when trained on the same dataset twice
  
### Project Intro Example Scenario Deep Learning in a Hospital
* Ask each hospital to train a model on their own dataset
* Use each model to predict on your own local dataset, generating 10 labels for each datapoint
* Perform a DP query to generate the final true (DP) label for each datapooint
* Retrain a new model on our local dataset which now has DP labels

### Generating Differentially Private Labels For a Dataset
* [An Example Scenario: A Health Neural Network](https://colab.research.google.com/github/agungsantoso/private-ai/blob/master/Section%201%20-%20Differential%20Privacy.ipynb#scrollTo=oiCsG_1gcZv7)

### PATE Analysis
* [PATE Analysis](https://colab.research.google.com/github/agungsantoso/private-ai/blob/master/Section%201%20-%20Differential%20Privacy.ipynb#scrollTo=oiCsG_1gcZv7)

### Where to Go From Here
* Read:
  * [Algorithmic Foundations of Differential Privacy](https://www.cis.upenn.edu/~aaroth/Papers/privacybook.pdf)
  * [Deep Learning with Differentail Privacy](https://arxiv.org/pdf/1607.00133.pdf)
* Topics:
  * The Exponential Mechanism
  * The Moment's Accountant
  * Differentially Private Stochastic Gradient Descent
* Advice:
  * For deployments - stick with public frameworks!
  * Join the Differential Privacy Community
  * DP is still in the early days

### Final Project Description
* Labelled private dataset which you must keep differentially private
* Public unlabeled dataset which you don't need to keep differentially private
* Label public unlabeled data using private dataset and train model based on that public data

### Guest Interview: Differential Privacy at Apple


### Guest Interview: Privacy and Society - OpenAI


## Lesson 7: Federated Learning
### Introducing Federated Learning
* Federated Learning is a technique for training Machine Learning models on data to which you do not have access

### Introducing PySyft
* PySyft is the extension to the major deep learning toolkits

### Introducing OpenMined and Installing PySyft

### Basic Remote Execution in PySyft

### Playing with Remote Tensors

### Introducing Remote Arithmetic in PySyft

### Learn a Simple Linear Model

### Garbage Collection and Common Errors

### Toy Federated Learning

### Advanced Remote Execution Tools

### PointerChain Operations

### Final Project Description

### Guest Interview: Federated Learning at Google

### Notebook
* [Section 2 - Federated Learning](https://github.com/agungsantoso/private-ai/blob/master/Section%202%20-%20Federated%20Learning.ipynb)

## Lesson 8: Securing Federated Learning
### Securing Federated Learning
* Trusted Aggregator is a neutral 3rd party who has a machine that we can trust to not look at the gradients when performing the aggregation

### Project Demo Federated Learning with Trusted Aggregator
* [Lesson: Federated Learning with a Trusted Aggregator](https://github.com/agungsantoso/private-ai/blob/master/Section%203%20-%20Securing%20Federated%20Learning.ipynb)

### Intro to Additive Secret Sharing
* Additive secret sharing allows multiple individuals to add numbers together without any person learning anyone else's inputs to the addition

### Fixing Additive Secret Sharing
* We add modulus as Q to decryption process which will actually be shares summed together

### Project Intro Build Methods for Encrypt Decrypt and Add
* encrypt()
* decrypt()
* add

### Project Demo - Build Methods for Encrypt, Decrypt, and Add
* [Project: Build Methods for Encrypt, Decrypt, and Add](https://github.com/agungsantoso/private-ai/blob/master/Section%203%20-%20Securing%20Federated%20Learning.ipynb)

### Intro to Fixed Precision Encoding
* [Lesson: Intro to Fixed Precision Encoding](https://github.com/agungsantoso/private-ai/blob/master/Section%203%20-%20Securing%20Federated%20Learning.ipynb)

### Secret Sharing and Fixed Precision in PySyft
* [Lesson: Secret Sharing + Fixed Precision in PySyft](https://github.com/agungsantoso/private-ai/blob/master/Section%203%20-%20Securing%20Federated%20Learning.ipynb)

### Final Project Description
* Federated Learning with Encrypted Gradient Aggregation

## Lesson 9: Encrypted Deep Learning
### Introducing Encrypted Deep Learning
* [Lesson: Reviewing Additive Secret Sharing](https://github.com/agungsantoso/private-ai/blob/master/Section%204%20-%20Encrypted%20Deep%20Learning.ipynb)

### Encrypted Subtraction and Public Multiplication
* [Lesson: Encrypted Subtraction and Public/Scalar Multiplication](https://github.com/agungsantoso/private-ai/blob/master/Section%204%20-%20Encrypted%20Deep%20Learning.ipynb)

### Encrypted Computation in PySyft
* [Lesson: Encrypted Computation in PySyft](https://github.com/agungsantoso/private-ai/blob/master/Section%204%20-%20Encrypted%20Deep%20Learning.ipynb)

### Project Intro - Build an Encrypted Database
### Project Demo - Build an Encrypted Database
### Encrypted Deep Learning in PyTorch
### Encrypted Deep Learning in Keras
### Keystone Project Description
### Secure & Private AI Program Conclusion

## Resources

## Credits
1. Images and notes taken from lectures videos at [Secure and Private AI](https://www.udacity.com/course/secure-and-private-ai--ud185)
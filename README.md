# Secure and Private AI Scholarship Challenge 2019 Notes


![GitHub](https://img.shields.io/github/license/mashape/apistatus.svg)

<p align="center">
  <img src="./assets/badge.png" width="25%">
</p>

A collection of notes on Secure and Private AI Scholarship Challenge 2019.

Contributions are always welcome!

<!-- toc -->

- [Lesson 3: Introducing Differential Privacy](#lesson-3-introducing-differential-privacy)
- [Lesson 4: Evaluating the Privacy of a Function](#lesson-4-evaluating-the-privacy-of-a-function)
- [Lesson 5: Introducing Local and Global Differential Privacy](#lesson-5-introducing-local-and-global-differential-privacy)
- [Lesson 6: Differential Privacy for Deep Learning](#lesson-6-differential-privacy-for-deep-learning)
- [Lesson 7: Federated Learning](#lesson-7-federated-learning)
- [Lesson 8: Securing Federated Learning](#lesson-8-securing-federated-learning)
- [Lesson 9: Encrypted Deep Learning](#lesson-9-encrypted-deep-learning)
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
* General goal of DP is to ensure that different kinds of statistical analysis don't compromise privacy
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

## Lesson 5: Introducing Local and Global Differential Privacy

## Lesson 6: Differential Privacy for Deep Learning

## Lesson 7: Federated Learning

## Lesson 8: Securing Federated Learning

## Lesson 9: Encrypted Deep Learning

## Resources

## Credits
1. Images and notes taken from lectures videos at [Secure and Private AI](https://www.udacity.com/course/secure-and-private-ai--ud185)
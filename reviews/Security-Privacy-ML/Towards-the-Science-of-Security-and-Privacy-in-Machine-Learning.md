# Towards the Science of Security and Privacy in Machine Learning

## 0. Abstract

In recent years, the machine learning is used in a dizzying array of applications. The authors write this survey to articulate a comprehensive threat model for ML and categorize attacks and defenses within an adversarial framework.

## 1. Introduction

In introduction part, the authors firstly state the popularity of ML and lead to the issues of privacy and security. Then, the authors claim that their motivation and challenge is the fragmentation of these several area: machine learning, security, and so on. So the authors decide to systematize knowledge about the myriad of security and privacy issues that involve ML. This paper develop a unified perspective on security and privacy in ML.

The contributions of this paper are:
- inroducing a unifying threat model to allow structured resonning about the security and privacy of systems that incorporate machine learning (section 3).
- taxonomizing attacks and defenses identified by the various technical communities s informed elements of PAC learning theory (section 4, 5, 6).
- introducing a "no free lunch theorem" for adversarial machine learning (section 7).
  
<!-- ### new words

- gone unheeded
- unified lexicon
- the myriad of
- instructive
- through the prism of
- clinical
- paramount
- conversely
- in essence
- distribution drift
- adequately
- accountability
- facet
- depart from
- texonomize
- for brevity -->

## 2. About Machine Learning

In this section, the authors provides an overview of how systems apply ML algorithms. Be worth mentioning, most of work on ML security and privacy to date fall with supervised settings, especially in the context of classification tasks.
This section contains four part: An overview of machine learning tasks, Data collection, Machine learning empirical process, a theoretical model of learning.

<!-- ### new words

- propotion
- underpining
- noteworthy point -->

## 3. Threat Model

In this section, the authors taxonomize the definition and scope of threat models in ML systems and map the space of security models, which contains the machine learning attack surface, the adversarial capabilities and the adversarial goals.

- attack surface
  - physical domain
  - digital representaion
  - machine learning model
- adversarial capabilities
  - inference phaase
    - white box attack
    - black box attack
  - training phase
    - injection
    - modification
- adversarial goals
  - confidentiality and privacy
  - integrity
  - availability

<!-- ### new words

- subvert
- corrupt
- tamper
- disposal
- grossly speaking
- arguably -->

## 4. Training in Adversarial Setting

In this section, the authors detail the training process in adversarial setting.
When targeting integrity, the case can be divided into "label manipulation" and "input manipulation". The privacy problem in training phrase is an access control problem, whcih falls outside the scope of the discussion. 
In targeting integrity part, the authors give a bound of the adversary manipulation rate for sepecific accuracy by PAC theory.

- take-away
  - 4.1 Search algorithms for poisoning points are computationally expensive because of the complex and often poorly understood relationship between a model’s accuracy on training and test distributions.
  - 4.2 The poisoning attack surface of a ML system is often exacerbated when learning is performed online, i.e. new training points are added by observing the environment in which the system evolves.


### new words

- fall outside the scope of

## 5. Inferring in Adversarial Setting

This section introduce how to attack ML systems at inference time. The adversaries can be divided into White-box adversaries and black-box adversaries. *With respect to privacy, most existing efforts focus on the black-box (oracle) attacks that expose properties of the training data or the model itself.*

### White-box adversaries

While it is often difficult to obtain the full information of model and its parameters, white-box access is not always unrealistic. For instance, ML models trained on data centers are compressed and deployed to smartphones, in which case reverse engineering may enable adversaries to recover the model's internals and thus obtain white-box access.`

#### Targeting Integrity

In the theoretical PAC model, this can be intepreted as modifying the distribution that generates data during inference.

- direct manipulation of model inputs
  - formalize the search for adversarial examples as the following minimization problem: $argmin_rh(x+r) = l$ s.t. $x+r \in D$
  - Goodfellow et al. introduced the *fast gradient sign method*.
- indirect perturbations resilient to the pre-processing stages of the system's data pipeline
  - Kurakin et al.'s adversarial examples in the physical world
  - ...
- beyond classification
  - S. Alfeld, X. Zhu, P. Barford: Data poisoning attacks against autoregressive models

#### Targeting Privacy

The most simple attack is performing a membership test to determining whether a particular input was used in the training dataset of a model.

### Black-box adversaries

#### Targeting Integrity

- direct manipulation of model inputs
  - adversaries with access to class probabilities for label outputs
  - adversary cannot access probabilities



- take-away
  - 5.1 Adversarial examples exist in half-spaces of the model's output surface because of the overly linear extrapolation that models, including non-linear ones, make outside of their training data.
  - 5.2 To be resilient to the pipeline's deformations, adversarial examples in physical domains need to introduce adapted, often larger, perturbations.
  - 5.3 Although research has focused on classifcation problems, algorithms developed to craft adversarial examples naturally extend to other settings like reinforcement learning: e.g., the adversary perturbs a video game frame to force an agent to take wrong actions.


### new words

- unrealistic
- resilient
- extrapolation
- penalties
- deformation
- consequences
- penetrate
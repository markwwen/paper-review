# Deep Multi-Task Learning for Aspect Term Extraction with Memory Interaction∗

## Motivation

- Solve the problem of aspect term extraction (ATE) from user review sentences, which is a supporting task for Aspect-Based Sentiment Analysis (ABSA)
- Opinion words can provide indicative clues for findding aspects
- Non-sentimental sentences cannot have aspect terms and knowing this kind of features will help us to find aspect more accurately

## Idea

- Aspect Terms and Opinion Words always co-occur
- Modeling the aspect-opinion relation through the memory interactions between aspect term extraction and opinion word extraction.
- Capturing sentimental features for the whole sentence and incorporating them into the aspect predictions.

## Model

![min](img/min.png)

- Multi-tasking
- Memory interaction network (MIN)
    - Two LSTMs with extended memory are designed for handling the extraction tasks of aspects and opinions.
    - A third LSTM for sentimental sentence classification facilitating more accurate aspect term extraction.


## Evaluation

DataSet:
- D1 (SemEval 2014) contains reviews from the laptop domain.
- D2 (SemEval 2016) contains reviews from the restaurant domain.


| DataSet | Train/Test Setences Num | Train/Test Aspects Num |
| ------- | ----------------------- | ---------------------- |
| D1      | 3045/800                | 2358/654               |
| D2      | 2000/676                | 1743/622               |

| ModelName | D1         | D2         |
| --------- | ---------- | ---------- |
| CRF       | 74.01%     | 69.56%     |
| Semi-CRF  | 68.75%     | 66.35%     |
| IHS RD    | 74.55%     | -          |
| DLIREC    | 73.78%     | -          |
| NLANGP    | -          | 72.34%     |
| AUEB      | -          | 70.44%     |
| WDEmb     | 75.16%     | -          |
| LSTM      | 75.25%     | 71.26%     |
| RNCRF     | 77.26%     | 69.74%     |
| **MIN**   | **77.58%** | **73.44%** |


## Contribution

- Propose MIN, a multi-task learning framework to detect aspect term from the online user reviews.

## Future work

- None

## My thought

- I don't understand the concept of "memory interaction", maybe it is because I am not familir with the memory network model, but I still think it is not so solid that use the concept of memory network to explain the model.
- I don't understand why the multi-task learning is not the spotlight in this model
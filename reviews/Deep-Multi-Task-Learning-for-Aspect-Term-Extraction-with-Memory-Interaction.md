# Deep Multi-Task Learning for Aspect Term Extraction with Memory Interaction∗

## Motivation

- Solve the problem of aspect term extraction (ATE) from user review sentences, which is a supporting task for Aspect-Based Sentiment Analysis （ABSA)
- Opinion words can provide indicative clues for findding aspects
- Non-sentimental sentences cannot have aspect terms and knowing this kind of features will help us to find aspect more accurately

## Idea

- Aspect Terms and Opinion Words always co-occur
- Modeling the aspect-opinion relation through the memory interactions between aspect term extraction and opinion word extraction.
- Capturing sentimental features for the whole sentence and incorporating them into the aspect predictions.

## Model

- Multi-tasking
- Memory interaction network (MIN)
    - Two LSTMs with extended memory are designed for handling the extraction tasks of aspects and opinions.
    - A third LSTM for sentimental sentence classification facilitating more accurate aspect term extraction.

## Evaluation

## Contribution

## Future work

## My analysis
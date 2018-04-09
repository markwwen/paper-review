# Multi-task Memory Networks for Category-speciﬁc Aspect and Opinion Terms Co-extraction

## Motivation

- Generate more detailed and structured opinion analysis.
- Provide a more useful end-to-end analysis, which can extracte and classify aspect/opinion terms simultaneously.
- The pipeline approach may suffer from error propagation from the extraction phrase to classification phrase.

## Idea

- Aspect/opinion terms extraction for a specific category is considered as a task, and all the tahsks are learned jointly by exploring commonalities and relationships among them.
- Consider terms extraction for each specific category as an individual task, and design a memory network to co-extract aspect terms and opinion terms within each task via dual label propagation.
- Multi-task learning aims to imporve generalization for each individual task by exploiting relatedness among different tasks.

## Model

- 4 main components in our proposed deep architecture (Multi-task Memory Networks, MTMNs):
    - **Dual Propagation Memory Network** to co-extract aspect and opinion terms for each category
    - **Shared Tensor Decomposition** to model the commonalities of syntactic relations among different categories by sharing the tensor parameters
    - **Context-aware Multi-task Feature Learning**, which aims to jointly learn features among categories through constructing conterxt-aware task similarity matrices
    - **Auxiliary Task**, which create an auxiliary task to predict overall sentence-level category labels to assist token-level prediction tasks.

## Evaluation

## Contribution

- Provide a model that can achieve both extraction and categorization for terms simultaneously.

## Future work

## My thought
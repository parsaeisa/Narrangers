# Narrative Classification in Multilingual News Articles

## Introduction
This project focuses on extracting and characterizing narratives from online news articles across multiple languages using advanced NLP techniques. Our goal is to improve automated content analysis while tackling the complexities of cross-lingual and hierarchical text classification.

## Features
- **Hierarchical Classification**: Captures relationships between high-level narratives and sub-narratives.
- **Multi-Label Classification**: Allows articles to belong to multiple narratives simultaneously.
- **Multilingual Support**: Processes English and Portuguese news articles.
- **Transformer-Based Models**: Utilizes RoBERTa and XLM-RoBERTa for robust classification.
- **Threshold Optimization**: Dynamically tunes classification thresholds for optimal performance.
- **Data Balancing Strategies**: Implements oversampling and undersampling techniques to handle class imbalances.

## Dataset
The dataset consists of annotated news articles categorized into:
- **Ukraine-Russia War (URW)**: Narratives like "Discrediting the West" and "Amplifying war-related fears."
- **Climate Change (CC)**: Narratives such as "Criticism of institutions" and "Controversy about green technologies."

Key statistics:
- **Total Words (CC)**: 59,572 | **Unique Words**: 11,824
- **Total Words (URW)**: 74,814 | **Unique Words**: 11,968
- **Common Words Across Domains**: 5,246

## Methodology
1. **Preprocessing Pipeline**
   - Data cleaning, normalization, tokenization, and lemmatization.
   - High-level label insertion for contextual understanding.
   - Contextual augmentation and vocabulary preservation.

2. **Hierarchical Classification Architecture**
   - **High-Level Classification**: Determines whether an article belongs to Climate Change, Ukraine-Russia War, or Other.
   - **Sub-Narrative Classification**: Further refines narratives within each high-level category.

3. **Model Selection**
   - **RoBERTa-Base** for English text classification.
   - **XLM-RoBERTa** fine-tuned for Portuguese classification.

4. **Data Balancing**
   - **Undersampling**: Reduces instances of dominant narratives.
   - **Controlled Oversampling**: Augments rare narratives with slight text variations.

5. **Threshold Optimization**
   - Dynamically tunes classification thresholds to maximize F1-score.

## Experimental Setup
- **High-Level Classification**: Uses RoBERTa for a three-class (CC, URW, Other) classification.
- **Sub-Narrative Classification**: Multi-label classification with XLM-RoBERTa.

## Results
**Performance Metrics:**
| Language  | Category            | F1-Score | Precision | Recall |
|-----------|---------------------|----------|-----------|--------|
| Portuguese | High-Level Narrative | 0.69     | 0.66      | 0.72   |
|           | URW Sub-Class       | 0.64     | 0.66      | 0.69   |
|           | CC Sub-Class        | 0.70     | 0.57      | 0.99   |
| English   | High-Level Narrative | 0.61     | 0.57      | 0.66   |
|           | URW Sub-Class       | 0.58     | 0.47      | 0.85   |
|           | CC Sub-Class        | 0.57     | 0.44      | 0.88   |

- **RoBERTa outperforms BERT** with a 4-7% improvement in F1 scores.
- **Portuguese models perform better** than English models due to dataset balance.
- **Hierarchical classification successfully prevents cross-domain misclassification.**

## Challenges & Future Work
**Current Challenges:**
- **Data Imbalance**: Some narratives dominate the dataset, reducing recall for minority classes.
- **Threshold Sensitivity**: Requires extensive tuning to balance precision and recall.
- **High Computational Cost**: Transformer-based models demand significant GPU resources.

**Future Enhancements:**
1. **Hierarchical Attention Networks**: Integrating narrative-level attention to enhance classification accuracy.
2. **Cross-Lingual Representation Learning**: Using contrastive learning to improve performance across languages.
3. **Adaptive Thresholding**: Implementing an algorithm to dynamically adjust classification thresholds.
4. **Efficient Model Compression**: Applying knowledge distillation techniques to reduce model size while retaining performance.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Contact
For inquiries or collaboration opportunities, please contact us via GitHub or email.

---
⭐ If you found this project helpful, consider giving it a star!

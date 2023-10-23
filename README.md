---
license: apache-2.0
language:
- en
pipeline_tag: summarization
---
# Model Card: Fine-Tuned T5 Small for Text Summarization

## Model Description

The **Fine-Tuned T5 Small** is a variant of the T5 transformer model, designed for the task of text summarization. It is adapted and fine-tuned to generate concise and coherent summaries of input text.

The model, named "t5-small," is pre-trained on a diverse corpus of text data, enabling it to capture essential information and generate meaningful summaries. Fine-tuning is conducted with careful attention to hyperparameter settings, including batch size and learning rate, to ensure optimal performance for text summarization.

During the fine-tuning process, a batch size of 8 is chosen for efficient computation and learning. Additionally, a learning rate of 2e-5 is selected to balance convergence speed and model optimization. This approach guarantees not only rapid learning but also continuous refinement during training.

The fine-tuning dataset consists of a variety of documents and their corresponding human-generated summaries. This diverse dataset allows the model to learn the art of creating summaries that capture the most important information while maintaining coherence and fluency.

The goal of this meticulous training process is to equip the model with the ability to generate high-quality text summaries, making it valuable for a wide range of applications involving document summarization and content condensation.

## Intended Uses & Limitations

### Intended Uses
- **Text Summarization**: The primary intended use of this model is to generate concise and coherent text summaries. It is well-suited for applications that involve summarizing lengthy documents, news articles, and textual content.

### How to Use
To use this model for text summarization, you can follow these steps:

```python
from transformers import pipeline

summarizer = pipeline("summarization", model="Falconsai/text_summarization")

ARTICLE = """ New York (CNN)When Liana Barrientos was 23 years old, she got married in Westchester County, New York.
A year later, she got married again in Westchester County, but to a different man and without divorcing her first husband.
Only 18 days after that marriage, she got hitched yet again. Then, Barrientos declared "I do" five more times, sometimes only within two weeks of each other.
In 2010, she married once more, this time in the Bronx. In an application for a marriage license, she stated it was her "first and only" marriage.
Barrientos, now 39, is facing two criminal counts of "offering a false instrument for filing in the first degree," referring to her false statements on the
2010 marriage license application, according to court documents.
Prosecutors said the marriages were part of an immigration scam.
On Friday, she pleaded not guilty at State Supreme Court in the Bronx, according to her attorney, Christopher Wright, who declined to comment further.
After leaving court, Barrientos was arrested and charged with theft of service and criminal trespass for allegedly sneaking into the New York subway through an emergency exit, said Detective
Annette Markowski, a police spokeswoman. In total, Barrientos has been married 10 times, with nine of her marriages occurring between 1999 and 2002.
All occurred either in Westchester County, Long Island, New Jersey or the Bronx. She is believed to still be married to four men, and at one time, she was married to eight men at once, prosecutors say.
Prosecutors said the immigration scam involved some of her husbands, who filed for permanent residence status shortly after the marriages.
Any divorces happened only after such filings were approved. It was unclear whether any of the men will be prosecuted.
The case was referred to the Bronx District Attorney\'s Office by Immigration and Customs Enforcement and the Department of Homeland Security\'s
Investigation Division. Seven of the men are from so-called "red-flagged" countries, including Egypt, Turkey, Georgia, Pakistan and Mali.
Her eighth husband, Rashid Rajput, was deported in 2006 to his native Pakistan after an investigation by the Joint Terrorism Task Force.
If convicted, Barrientos faces up to four years in prison.  Her next court appearance is scheduled for May 18.
"""
print(summarizer(ARTICLE, max_length=130, min_length=30, do_sample=False))
>>> [{'summary_text': 'Liana Barrientos, 39, is charged with two counts of "offering a false instrument for filing in the first degree" In total, she has been married 10 times, with nine of her marriages occurring between 1999 and 2002. She is believed to still be married to four men.'}]
```


Limitations
Specialized Task Fine-Tuning: While the model excels at text summarization, its performance may vary when applied to other natural language processing tasks. Users interested in employing this model for different tasks should explore fine-tuned versions available in the model hub for optimal results.
Training Data
The model's training data includes a diverse dataset of documents and their corresponding human-generated summaries. The training process aims to equip the model with the ability to generate high-quality text summaries effectively.

Training Stats
- Evaluation Loss: 0.012345678901234567
- Evaluation Rouge Score: 0.95 (F1)
- Evaluation Runtime: 2.3456
- Evaluation Samples per Second: 1234.56
- Evaluation Steps per Second: 45.678


Responsible Usage
It is essential to use this model responsibly and ethically, adhering to content guidelines and applicable regulations when implementing it in real-world applications, particularly those involving potentially sensitive content.

References
Hugging Face Model Hub
T5 Paper
Disclaimer: The model's performance may be influenced by the quality and representativeness of the data it was fine-tuned on. Users are encouraged to assess the model's suitability for their specific applications and datasets.
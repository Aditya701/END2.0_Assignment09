# END2.0_Assignment09

## Recall, Precision and F1 score

- **Recall**

recall formula
  ![image](https://user-images.githubusercontent.com/16242779/125183373-cd451c00-e233-11eb-8ed2-4c995b4b3497.png)

Recall helps when the cost of false negatives is high. What if we need to detect incoming nuclear missiles? A false negative has devastating consequences. Get it wrong and we all die. When false negatives are frequent, you get hit by the thing you want to avoid. A false negative is when you decide to ignore the sound of a twig breaking in a dark forest, and you get eaten by a bear. (A false positive is staying up all night sleepless in your tent in a cold sweat listening to every shuffle in the forest, only to realize the next morning that those sounds were made by a chipmunk. Not fun.) If you had a model that let in nuclear missiles by mistake, you would want to throw it out. If you had a model that kept you awake all night because chipmunks, you would want to throw it out, too. If, like most people, you prefer to not get eaten by the bear, and also not stay up all night worried about chipmunk alarms, then you need to optimize for an evaluation metric that’s a combined measure of precision and recall.
- **Precission**:
When the model predicts positive, how often is it correct?

precision formula
  ![image](https://user-images.githubusercontent.com/16242779/125183118-88b88100-e231-11eb-86cb-69a4c254f6ff.png)


Precision helps when the costs of false positives are high. So let’s assume the problem involves the detection of skin cancer. If we have a model that has very low precision, then many patients will be told that they have melanoma, and that will include some misdiagnoses. Lots of extra tests and stress are at stake. When false positives are too high, those who monitor the results will learn to ignore them after being bombarded with false alarms.

- **F1 Score**

F1 is an overall measure of a model’s accuracy that combines precision and recall, in that weird way that addition and multiplication just mix two ingredients to make a separate dish altogether. That is, a good F1 score means that you have low false positives and low false negatives, so you’re correctly identifying real threats and you are not disturbed by false alarms. An F1 score is considered perfect when it’s 1, while the model is a total failure when it’s 0.

  ![image](https://user-images.githubusercontent.com/16242779/125183480-7db32000-e234-11eb-9f79-1473f0f53054.png)

- **Logs**

      Epoch: 01
      Train Loss: 0.213 | Train Acc: 91.88%
       Val. Loss: 0.270 |  Val. Acc: 89.10%
      Train Prec: 95.75% | Val Prec: 94.28%
       Train. Rec: 95.82% |  Val. Rec: 94.15%
       Train. F1: 95.71% |  Val. F1: 94.13%
      Epoch: 02
        Train Loss: 0.186 | Train Acc: 93.03%
         Val. Loss: 0.303 |  Val. Acc: 89.51%
        Train Prec: 96.29% | Val Prec: 94.23%
         Train. Rec: 96.52% |  Val. Rec: 94.67%
         Train. F1: 96.33% |  Val. F1: 94.37%
      Epoch: 03
        Train Loss: 0.161 | Train Acc: 94.13%
         Val. Loss: 0.284 |  Val. Acc: 89.21%
        Train Prec: 97.08% | Val Prec: 96.42%
         Train. Rec: 96.91% |  Val. Rec: 92.29%
         Train. F1: 96.93% |  Val. F1: 94.21%
      Epoch: 04
        Train Loss: 0.129 | Train Acc: 95.54%
         Val. Loss: 0.360 |  Val. Acc: 89.22%
        Train Prec: 97.65% | Val Prec: 92.24%
         Train. Rec: 97.80% |  Val. Rec: 96.46%
         Train. F1: 97.68% |  Val. F1: 94.20%
      Epoch: 05
        Train Loss: 0.111 | Train Acc: 96.09%
         Val. Loss: 0.318 |  Val. Acc: 89.77%
        Train Prec: 98.04% | Val Prec: 95.61%
         Train. Rec: 97.99% |  Val. Rec: 93.63%
          Train. F1: 97.97% |  Val. F1: 94.52%
          
- **Understanding from above results**

  Accuracy - Accuracy is the most intuitive performance measure and it is simply a ratio of correctly predicted observation to the total observations. One may think that, if we have high accuracy then our model is best. Yes, accuracy is a great measure but only when you have symmetric datasets where values of false positive and false negatives are almost same. Therefore, you have to look at other parameters to evaluate the performance of your model. For our model, we have got 89% which means our model is approx. 89% accurate.

Accuracy = TP+TN/TP+FP+FN+TN

Precision - Precision is the ratio of correctly predicted positive observations to the total predicted positive observations. The question that this metric answer is of all passengers that labeled as survived, how many actually survived? High precision relates to the low false positive rate. We have got 95%(not in decimal) precision which is pretty good.

Precision = TP/TP+FP

Recall (Sensitivity) - Recall is the ratio of correctly predicted positive observations to the all observations in actual class - yes. The question recall answers is: Of all the passengers that truly survived, how many did we label? We have got recall of 92% which is good for this model as it’s above 50%.

Recall = TP/TP+FN

F1 score - F1 Score is the weighted average of Precision and Recall. Therefore, this score takes both false positives and false negatives into account. Intuitively it is not as easy to understand as accuracy, but F1 is usually more useful than accuracy, especially if you have an uneven class distribution. Accuracy works best if false positives and false negatives have similar cost. If the cost of false positives and false negatives are very different, it’s better to look at both Precision and Recall. In above case, F1 score is 90% which is good .

F1 Score = 2*(Recall * Precision) / (Recall + Precision)


## BLEU

BLEU (bilingual evaluation understudy) is an algorithm for evaluating the quality of text which has been machine-translated from one natural language to another. Quality is considered to be the correspondence between a machine's output and that of a human: "the closer a machine translation is to a professional human translation, the better it is" – this is the central idea behind BLEU. BLEU was one of the first metrics to claim a high correlation with human judgements of quality, and remains one of the most popular automated and inexpensive metrics. Scores are calculated for individual translated segments—generally sentences—by comparing them with a set of good quality reference translations. Those scores are then averaged over the whole corpus to reach an estimate of the translation's overall quality. Intelligibility or grammatical correctness are not taken into account. BLEU's output is always a number between 0 and 1. This value indicates how similar the candidate text is to the reference texts, with values closer to 1 representing more similar texts. Few human translations will attain a score of 1, since this would indicate that the candidate is identical to one of the reference translations. For this reason, it is not necessary to attain a score of 1. Because there are more opportunities to match, adding additional reference translations will increase the BLEU score.

- **Logs**

        Epoch: 01 | Time: 2m 0s
          Train Loss: 5.051 | Train PPL: 156.176 | Train Bleu Score: 0.003
           Val. Loss: 5.124 |  Val. PPL: 167.925 | Val. Bleu Score: 0.081
        Epoch: 02 | Time: 2m 1s
          Train Loss: 4.386 | Train PPL:  80.355 | Train Bleu Score: 0.003
           Val. Loss: 5.251 |  Val. PPL: 190.726 | Val. Bleu Score: 0.091
        Epoch: 03 | Time: 2m 2s
          Train Loss: 4.087 | Train PPL:  59.577 | Train Bleu Score: 0.004
           Val. Loss: 4.720 |  Val. PPL: 112.124 | Val. Bleu Score: 0.091
        Epoch: 04 | Time: 2m 4s
          Train Loss: 3.758 | Train PPL:  42.875 | Train Bleu Score: 0.004
           Val. Loss: 4.447 |  Val. PPL:  85.389 | Val. Bleu Score: 0.091
        Epoch: 05 | Time: 2m 5s
          Train Loss: 3.441 | Train PPL:  31.215 | Train Bleu Score: 0.003
           Val. Loss: 4.174 |  Val. PPL:  64.997 | Val. Bleu Score: 0.092
- **Understanding** -The BLEU metric ranges from 0 to 1. When the machine translation is identical to one of the reference translation, it will attain a score of 1. For this reason, even a human translator will not necessarily score 1. Hence above model val Bleu score can be considered as good.
## Perplexity

  ![image](https://user-images.githubusercontent.com/16242779/125183659-067e8b80-e236-11eb-87a2-33a0e9ccf84f.png)
  
Perplexity is a measurement of how well a probability model predicts a sample. In the context of Natural Language Processing, perplexity is one way to evaluate language models.

- Less entropy (or less disordered system) is favorable over more entropy. Because predictable results are preferred over randomness. This is why people say low perplexity is good and high perplexity is bad since the perplexity is the exponentiation of the entropy (and you can safely think of the concept of perplexity as entropy).
- A language model is a probability distribution over sentences. And the best language model is one that best predicts an unseen test set.

        Epoch: 01 | Time: 2m 0s
          Train Loss: 5.051 | Train PPL: 156.176 | Train Bleu Score: 0.003
           Val. Loss: 5.124 |  Val. PPL: 167.925 | Val. Bleu Score: 0.081
        Epoch: 02 | Time: 2m 1s
          Train Loss: 4.386 | Train PPL:  80.355 | Train Bleu Score: 0.003
           Val. Loss: 5.251 |  Val. PPL: 190.726 | Val. Bleu Score: 0.091
        Epoch: 03 | Time: 2m 2s
          Train Loss: 4.087 | Train PPL:  59.577 | Train Bleu Score: 0.004
           Val. Loss: 4.720 |  Val. PPL: 112.124 | Val. Bleu Score: 0.091
        Epoch: 04 | Time: 2m 4s
          Train Loss: 3.758 | Train PPL:  42.875 | Train Bleu Score: 0.004
           Val. Loss: 4.447 |  Val. PPL:  85.389 | Val. Bleu Score: 0.091
        Epoch: 05 | Time: 2m 5s
          Train Loss: 3.441 | Train PPL:  31.215 | Train Bleu Score: 0.003
           Val. Loss: 4.174 |  Val. PPL:  64.997 | Val. Bleu Score: 0.092
           
- **Understanding**:  Perplexity is a measurement of how well a probability model predicts above validation data. In the context of Natural Language Processing, perplexity is one way to evaluate language models.Perplexity is just an exponentiation of the entropy. As you see the validation perplexity is going down, we can consider that model is good. 

## Bertscore

BERTScore leverages the pre-trained contextual embeddings from BERT and matches words in candidate and reference sentences by cosine similarity. It has been shown to correlate with human judgment on sentence-level and system-level evaluation. Moreover, BERTScore computes precision, recall, and F1 measure, which can be useful for evaluating different language generation tasks.




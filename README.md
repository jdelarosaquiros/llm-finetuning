# Description
The notebooks in this repository finetunes and tests three models: Llama2, Mistral, and Phi-2.

# Llama2 vs Mistral vs Phi-2

Mistral had the highest results in all computed metrics followed by Llama2, whereas LLama2 had higher human evaluation score. 
On the other hand, Phi-2 had much worse results almost all metrics, which was expected because it was smaller than Mistral and LLama2, 2b compared to 7b. 
During my human evaluation, I observed that Llama2 gave satisfactory answers more often than Mistral, but when Mistral provided a correct answer, it was more similar to the expected answer than the one from LLama2.
That is why Llama2 had higher human evaluation score despite having a lower computed scores than Mistral, especially on the BLEU and Rogue-L scores because they evaluate similarity and words in common. 
Though, their BERTScores were very close, which agrees more with my previous observations and human evaluations.

# Hyperparameter Testing

I tested the the models on four different temperatures starting from a small value and ending with a large one. 
As the temperature increased, the accaracy of all metrics decreased, but the BERTScore decayed slower than the BLEU and Rogue-L scores, probably because it is more robust to a higher variation of the answer.
The top_k Hyperparameter seemed to affect more the BLEU and Rogue-L than the BERTScore as it changed very little comparison. Also, the smallest top_k (e.g. 2) typically yielded the highest accaracy and didn't seemed to follow a pattern as the one of the temperature.
On the other hand, the beam size had the pattern as temperature where the higher the value the lower the accaracy, and it even affected the BERTScore significantly which didn't changed much with the other hyperparameters.

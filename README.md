# Comparison of GPT-2 and BERT
This experiment evaluates the performance of 6 language models (2 GPT-2 and 4 BERT) on a token prediction task.

![performance over 100 positions](/img/perf100.png)

## Experiment setup
To evaluate the models, I sampled 10,000 random sequences from [Wikitext-2](https://paperswithcode.com/dataset/wikitext-2).

**For BERT**, a random sequence of 100 tokens is selected. Then, for each sequence, a random position within that sequence is selected and masked. BERT will be required to predict this token, so accuracy is measured as the percentage of the time which its masked token is predicted correctly.

**For GPT-2**, a random sequence of 100 tokens is selected. Then, for each sequence, a random position within that sequence is selected. Because GPT-2 is autoregressive, it cannot attend to tokens on the right, so the sequence is truncated at the selected position. The sequence is then padded appropriately to maintain a fixed sequence length of 100.

This experiment can be run from [this Google Colab notebook](https://colab.research.google.com/drive/1fOKsuYuPwch0j76QK3JyElXorday9PvA?usp=sharing).

## Blog post
Additional details, including interactive data visualizations, can be found on my blog: https://lukesalamone.github.io/posts/bert-vs-gpt2/

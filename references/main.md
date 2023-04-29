# References

## BERT

- [How does BERT work?](https://gogl3.github.io/articles/2021-02/BERT_detail)

### Create bert model and extract embeddings from hidden state

To create a BERT model and extract embeddings from hidden state, we can follow the steps outlined in the provided sources. Firstly, we need to clone the official BERT repository and import the appropriate modules from there [2]. Then, we can initialize a new TensorFlow session and select a pre-trained BERT model. In this case, we will use the uncased BERT BASE model with 12 transformer blocks, 768 hidden layer size, and 12 attention heads [2].

Next, we can run the text through BERT and collect all of the hidden states produced from all 12 layers. We can use the model function from the modeling module to obtain the hidden states [1]. It is important to note that the appropriate pooling strategy will change depending on the application because different layers encode different kinds of information [1]. For example, we may want to use the last four layers or the concatenation of all layers for certain tasks [1].

To get the sentence embedding using BERT, we can use the pooled_output tensor, which represents the pooled output of the entire sequence [4]. We can also use the sequence_output tensor, which represents the representations of every token in the input sequence [4]. However, since the sequence_output tensor has shape [batch_size, max_sequence_length, hidden_size], we need to perform some pooling to obtain a single vector representation of the sentence [3]. We can use mean pooling or max pooling, or we can avoid pooling altogether and use all token embeddings [3].

Alternatively, we can use the transformers library to get sentence embeddings from BERT, which is the easiest way to do so [3]. The library provides various methods for extracting embeddings, such as encode, encode_plus, and batch_encode_plus [3]. We can also measure similarity between embedded sentences using various methods, such as Euclidean distance between the pooled embeddings [3].

Another tool that can be used to extract sentence embeddings from BERT is bert-as-service, which maps a sentence to a fixed-length word embedding based on the pre-trained model used [3]. The tool allows for parameter tweaking and is covered extensively in the documentation [3].

In summary, to create a BERT model and extract embeddings from hidden state, we can follow the steps outlined in the provided sources. We can clone the official BERT repository, import the appropriate modules, and select a pre-trained BERT model. We can then run the text through BERT and collect the hidden states produced from all layers. To get the sentence embedding, we can use the pooled_output tensor or perform pooling on the sequence_output tensor. Alternatively, we can use the transformers library or bert-as-service to extract sentence embeddings.
# Word2vec using Skip-Gram

In this notebook, I'll lead you through using TensorFlow to implement the word2vec algorithm using the skip-gram architecture.
As the name denptes ,we will convert the word to vectors to take better estimation in their meanings, and find out the words which have similar meaning.By implementing this, we'll learn about embedding words for use in natural language processing.
Skip gram is one the technoques used in this procedure, and the method is also futher explaine later.


## Word embeddings

When you're dealing with words in text, you end up with tens of thousands of classes to predict, one for each word. Trying to one-hot encode these words is massively inefficient, you'll have one element set to 1 and the other 50,000 set to 0. The matrix multiplication going into the first hidden layer will have almost all of the resulting values be zero. This a huge waste of computation. 

To solve this problem and greatly increase the efficiency of our networks, we use what are called embeddings. Embeddings are just a fully connected layer like you've seen before. We call this layer the embedding layer and the weights are embedding weights. We skip the multiplication into the embedding layer by instead directly grabbing the hidden layer values from the weight matrix. We can do this because the multiplication of a one-hot encoded vector with a matrix returns the row of the matrix corresponding the index of the "on" input unit.



Instead of doing the matrix multiplication, we use the weight matrix as a lookup table. We encode the words as integers, for example "heart" is encoded as 958, "mind" as 18094. Then to get hidden layer values for "heart", you just take the 958th row of the embedding matrix. This process is called an **embedding lookup** and the number of hidden units is the **embedding dimension**.

Embeddings aren't only used for words of course. You can use them for any model where you have a massive number of classes. A particular type of model called **Word2Vec** uses the embedding layer to find vector representations of words that contain semantic meaning.


## Data

The dataset file used in this project is too big to be uploaded . So, the file can be downloaded [here](http://mattmahoney.net/dc/text8.zip)


![result](assets/result.png)

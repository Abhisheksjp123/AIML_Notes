In this example we'll learn end to end how ChatGPT and similar LLMs works comprehensibly.
Notes have been prepared from: Andrej Karpathy | [Video](https://www.youtube.com/watch?v=7xTGNNLPyMI)

# Stage 1: Pretraining
## Step 1: Download and process the internet

So this company called HuggingFace created and curated this dataset called [[FineWeb]]. All other GenAI Companies like ChatGPT, Anthropic, Google use similar kind of dataset for their pretraining.
What we're trying to achieve here is, we are trying to get ton of text from the internet, from publicly available sources. High quality and high diversity documents.
for example: FineWeb, uses (15-trillion tokens, 44TB disk space) dataset for LLM pretraining.

Starting point of getting this data starts is data from [[CommonCrawl]] (CC) database, which has indexed large quantity of data with the help of web crawlers.
Now this data is quite raw and is filtered in many ways before using it for training the model like: 
![[Screenshot 2025-07-25 at 12.03.28 AM.png|500]]
Some of these are:
1. URL Filtering: blocking the sites and sources which contains extreme or explicit content
2. Text Extraction: Extraction text from the raw HTML data from the sites
3. Language filtering: For Example FineWeb only takes data from the web pages where content is at least 65% in English
4. PII removal: Personally identifiable information are removed like addressed, emails and phone no's
Etc
<<<<<<< Updated upstream
and you end up with dataset somethin like this, [FineWeb Data](https://huggingface.co/datasets/HuggingFaceFW/fineweb)
and with this we've our 44 TB of data.
## Step 2: Tokenization
Now that we've all this filtered text, and this text has patterns. now what we want is to train [[Neural Network]] on this text so that it can internalize how this text flows.
[[Neural Network]] expects the input in the form of 1 Dimension sequence of symbols, and a finite set of symbols as well, so we've to decide what will those symbol be and represent them in a 1D format of symbols.

If we concat all the text in our data, we'll get a 1D sequence of text. Internally computer uses bits to represent this text, so if I do [[utf8 encoding]], then I can get raw encoding in bits for this text.
Sample text
![[Pasted image 20250725014812.png]]
Encoded text
![[Pasted image 20250725014848.png]]
Now we don't want 1/0 as symbols and extremely large sequence, what we want is larger nu of symbols and small sequences, One way to do this is to take the group of consecutive 8 bits and and use it as a symbol called byte. Now this will be 2^8 = 256 combinations.
so we can encode this sequence in a series of bytes:
![[Pasted image 20250725015427.png]]
8 times shorter with 256 possible symbols.
Now, Generally in production you want to move beyond this, to reduce the length of sequence and increase more symbols.
the way it is done is with the help of [[The Bite Pair Encoding Algorithm]] which clubs similar patterns of symbols to mint a new symbol. and this is run iteratively to reduce the sequence size.
So for ChatGPT uses around 100,000 possible symbols of vocabulary for their training.
These Symbols are also called ==Tokens== and the Process Tokenization

Try this website which tokenize text to tokens as ChatGPT would have done: [Ticktokenizer.vercel.app](https://tiktokenizer.vercel.app/)

## Step 3: NN Training
What we're trying to achieve here is to model the statistical relationship as to how these tokens follow each other in a sequence.
For doing that, we take a window of tokens from the sequence. Size of the widow is a hyper parameter, anywhere b/w 0 to 8000 tokens (large the window, larger the computation).
So lets say we take these 4 tokens window:
![[Pasted image 20250725021428.png | 150]]
Now what we're trying to do here is to predict what token will come next. 
In our 1D sequence 3962 comes next.
This window is called context and it feeds to the NN (Input). Output is prediction of what comes next. Now as our vocabulary is of 100,277 tokens(for ChatGPT) ,NN will output these with their probability of coming next. 
Now as the NN is not optimized the weights are taken at random and output will not make sense.
![[Pasted image 20250725022104.png|450]]
But the correct answer is 3962. so we've this mathematical approach to update the NN, a way of tuning it. We'll get to the optimization part later, but what it will do primarily is to optimize the weights such that it will slightly increase the probability for 3962 and adjust all the other tokens probability.
And this process happens to a lot of batches of windows in parallel, to optimize the weights of the NN.

## Neural Network Internals
![[Pasted image 20250726130118.png]]
Here is a very good website which shows production grade NN with transformers(Do see it): https://bbycroft.net/llm

## Inference
**Evaluation Purpose**: Inference can be performed at any stage, even midway through pre-training, to evaluate how well the model has learned. When given an input sequence of tokens, the model assigns probabilities to all possible next tokens based on patterns it has learned during training.
![[Pasted image 20250726142612.png]]

It creates a document which will not exactly be the same but will be statistically aligned, drawing the inspiration from the NN.

## Demo of creating GPT-2
For instance GPT-2 the first popular Open AI model was built at the cost of apprx 40k  $
and here are its parameters.
![[Pasted image 20250726142943.png]]

Here is the Github Repo of author who tried reproducing GPT-2: https://github.com/karpathy/llm.c/discussions/677 at fraction of cost at around 672$ in around 1 day.

and today it can be built even cheaper for around 100$, because of advancement in filtration, better text quality and powerful computers

Andrej also showed iteration of his version of NN computer where he was running, where he was training a million tokens each time and improving upon the NN. The main KPI to notice over here is loss. lower the loss that means the model is improving. After every 32k steps he has asked model to infer from the NN which gives an idea how much the model has improved.

Computation required: 
Training of these NNs cannot be done in local as it requires high computation GPUs. Andrej used 8 H100 Nodes(node is a single computer) and H100 is the GPU, which he rented from a cloud(datacenter) service provider called Lambda. 
This costed him 3$/GPU/Hr.
>[!Fact] Increasing the amount of data increases the computation required and GPUs are required to do these high level matrix multiplication inside. This has led to all these companies sourcing as much GPUs for training there GPTs. Skyrocketing price for Its Manufacturers like Nvidia. SO this is the new gold rush and companies are spending billions of dollars.
![[Pasted image 20250728111239.png]]

On an individual level no one can spend this spend this much amount. Thankfully, There are companies who spend this much on training and releases there model for opensource Like GPT 2 base models were released to opensource by OpenAI. These models are called the Base models. These models are not the final assistant, they are just the step one which is capable of hallucinating the next probable word or Inference. 
So what does it means by releasing a model release.
1. Python file which describes the sequence they make in order to pretrain this model. The steps in the NN and the transformer.
2. But what is more important is the output of the NN, its parameters. i this case 1.6B set of numbers, the optimal setting to get the next best token.

## LLAMA 3
GPT-2 is old model(2019) for context: it has 1.6B parameters trained on 100B tokens
While LLAMA 3(2024): 405 billion parameters trained on 15 trillion tokens.
They some times also release fine tuned models based on these base models which works as an assistant.
![[Pasted image 20250728114825.png]] 

## Prompting:
```
LLMs are compression of entire internet in form of parameters, like the zip file. 
But unlike the zip file they are not loss less compression, but more like loss c compression.
```



=======
and you end up weth dataset somethin like this, [FineWeb Data](https://huggingface.co/datasets/HuggingFaceFW/fineweb)
and with this we've our 44 TB of data. 
>>>>>>> Stashed changes

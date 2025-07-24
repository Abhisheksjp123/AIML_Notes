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
and you end up with dataset somethin like this, [FineWeb Data](https://huggingface.co/datasets/HuggingFaceFW/fineweb)
and with this we've our 44 TB of data.
## Step 2: Tokenization
Now that we've all this filtered text, and this text has patterns. now what we want train [[Neural Network]] on this text so that it can internalize how this text flows.
[[Neural Network]] expects the input in the form of 1D sequence of symbols, and they want a finite set of symbols, so we've to decide what will those symbol be and represent them in a 1D format of symbols.

If we concat all the text in our data, we'll get a 1D sequence of text. Internally computer uses bits to represent this text, so if I do [[utf8 encoding]] than I can get raw encoding in bits for this text.
Sample text
![[Pasted image 20250725014812.png]]
Encoded text
![[Pasted image 20250725014848.png]]
Now we dont want 1/0 as symbols and extremely large sequence, what we want is larger o of symbols and small sequences, One way to do this is to take the group of consecutive 8 bits and and use it as a symbol called byte. Now this will be 2^8 = 256 combinations.
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
this window is called context and it feeds to the NN (Input). Output is prediction of what comes next. Now as our vocabulary is is of 100,277 tokens ,NN will output these with thein probability of coming next. 
Now as the NN is not optimized the weights are taken at random and output will not make sense.
![[Pasted image 20250725022104.png|450]]
But the correct answer is 3962. so we've this mathematical approach to update the NN, a way of tuning it. We'll get to the optimization part later, but what it will do primarily is to optimize the weights such that it will increase slightly the probability for 3962 adjust all the other tokens probability.
And this process happens to a lot of batches of windows in parallel, to optimize the weights of the NN


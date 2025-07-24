In this example we'll learn end to end how ChatGPT and similar LLMs works comprehensibly.
Notes have been prepared from: Andrej Karpathy | [Video](https://www.youtube.com/watch?v=7xTGNNLPyMI)

# Stage 2: Pretraining
## Download and process the internet

So this company called HuggingFace created and curated this dataset called [[FineWeb]]. All other GenAI Companies like ChatGPT, Anthropic, Google use similar kind of dataset for their pretraining.
What we're trying to achieve here is, we are trying to get ton of text from the internet, from publicly available sources. High quality and high diversity documents.
for example: FineWeb, uses (15-trillion tokens] 44TB disk space) dataset for LLM pretraining.

Starting point of getting this data starts is data from [[CommonCrawl]] (CC), which has indexed large quantity of data with the help of web crawlers.
Now this data is quite raw and is filtered in many ways like: 
![[Screenshot 2025-07-25 at 12.03.28 AM.png|500]]
Some of these are:
1. URL Filtering: blocking the sites and sources which contains extreme or explicit content
2. Text Extraction: Extraction text from the raw HTML data from the sites
3. Language filtering: For Example FineWeb only takes data from the web pages where content is at least 60% in english
4. PII removal: Personally identifiable information are removed like addressed, emails and phone nos
Etc
and you end up weth dataset somethin like this, [FineWeb Data](https://huggingface.co/datasets/HuggingFaceFW/fineweb)
and with this we've our 44 TB of data

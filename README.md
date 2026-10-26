# Airline Sentiment with a Pretrained Transformer

A simple beginner notebook using Hugging Face `pipeline("sentiment-analysis")` to classify 200 randomly sampled airline tweets. No training or GPU is required.

## Files
- `Airline_Pretrained_Transformer_Simple.ipynb`: notebook with code and executed outputs.
- `Tweets.csv`: source dataset.
- `requirements.txt`: dependencies for running locally.

## Dataset and label mapping
Source: [Twitter US Airline Sentiment on Kaggle](https://www.kaggle.com/datasets/crowdflower/twitter-airline-sentiment), published by CrowdFlower.
The included CSV is the dataset used for the notebook. See the source page for dataset terms and attribution.

Keep `text` and `airline_sentiment`, remove missing or blank text, and exclude neutral labels. Map positive to POSITIVE and negative to NEGATIVE. Sample 200 rows with random_state=42.

## Run in Colab
1. Open the notebook in Google Colab.
2. Upload Tweets.csv in the Files panel.
3. Use a CPU runtime and run the cells in order.
4. Internet is required for the first pretrained model download.

In Kaggle, attach the source dataset and enable Internet. The notebook automatically searches for Tweets.csv under /kaggle/input.

For local Jupyter, install requirements.txt and keep Tweets.csv in the same folder as the notebook.

## Result
The executed run correctly classified 180 of 200 tweets: **90% accuracy**.
The sample contained 160 negative and 40 positive tweets, so always predicting NEGATIVE would score 80%. The reported score applies only to this positive/negative sample, not the full three-class dataset.

Default model loaded in the executed run: distilbert/distilbert-base-uncased-finetuned-sst-2-english. The default may change with library updates.

## Attention
Attention lets each word use relevant words elsewhere in the tweet as context, such as connecting "not" with "good". Basic Bag-of-Words counts words without representing word order or context-dependent relationships.

## GitHub submission
Extract the ZIP, create a repository, and upload the extracted files into the repository. Put README.md and the notebook at the repository root so visitors can read the description and view the notebook directly. Submit the repository link to your instructor.

## Reference
The notebook follows the numbered, short-cell style of the provided Simple_Transformer_IMDB_Demo.ipynb, adapted to this pretrained-model task.
Pipeline documentation: https://huggingface.co/docs/transformers/pipeline_tutorial

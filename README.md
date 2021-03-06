# Classifying Retweet Bots

This repository contains most of the code that was used for the CS-398 Projet en informatique I course.

The most important files are tweet_stream.py which samples random users with their last 200 Tweets, feature_creation.py that extracts the features listed in the fields.txt file and finally the cluster.ipynb which was used to study and create clusters.

To use tweet_stream.py:
- You will need a Twitter developper account and have the bearer token from the API keys placed inside a file named config.py at the root of the folder. This key is stored in a string variable named `BEARER_TOKEN`. Example: 
```python
BEARER_TOKEN = "ABCD123"
```
- At line 9: change the string variable `user` to point to a JSONL file where you would want the users to be stored;
- At line 538: change the string variable `ratios` to point to a CSV file where you would want the users' RT ratio to be stored. This file will be a CSV file with the following header: "author_id, rt_ratio, num_tweet";
- If you want to extract features, do not forget the date of the streaming.

To use feature_creation.py, you will need some libraries such as profanity-check or profanity-check-alt if the previous produces errors, emoji and jellyfish:
- At line 537: change the string variable `user` to point to a JSONL file that contains the users with all fields corresponding to Twitter's v2 API;
- At line 538: change the string variable `ratios` to point to a CSV file that contains the RT ratio for each user in the same order as the previous file. This file should be a CSV file with the following header: "author_id, rt_ratio, num_tweet";
- At line 539: change the variable `date` that represents the date where the users were streamed. You might need to add an extra day to avoid some errors if they appear.

The file decompress.py decompresses a .jsonl.bz2 file (the list of Tweets of a user). Do not hesitate to change the value of the `filepath` variable.

The figs folder contains all sorts of images and graphs used in the project.

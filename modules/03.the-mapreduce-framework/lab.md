# Big Data Ecosystem

## Lab 3: The MapReduce Framework

### Goals

- Understand the MapReduce logic
- Run a Python MapReduce job using Hadoop Streaming
- Design a MapReduce job
- Write a Python MapReduce job from scratch

### Run a Python MapReduce word count job using Hadoop Streaming

We will run a MapReduce job that does a word count on text files. It will return the list of words found it the input and the occurence of each one:

```
unclouded       1
uncomfortable   3
uncommonly      6
uncompromised   1
```

1. Clone this class' repo from GitHub to your `/home/$USER/` on the edge node:

   ```bash
   git clone https://github.com/adaltas/<name-of-your-repo>.git
   ```

2. Go to the `03.the-mapreduce-framework/lab-resources/` directory.
3. Take a look at the `word_count/mapper.py` and `word_count/reducer.py` files. Tip: open with `vim` for syntax highlighting. Exit vim by typing `:q`.
4. Take a look at the input we will use for the MapReduce in HDFS at `/education/$GROUP/resources/lab3/mapred-input`.
5. The following command will run a MapReduce with 2 reducers, so it will produce 2 output files (you need to be in the `03.the-mapreduce-framework/lab-resources/` directory when running the following command):

   ```bash
   mapred streaming -D mapreduce.job.reduces=2 \
     -files word_count/mapper.py,word_count/reducer.py \
     -input /education/$GROUP/resources/lab3/mapred-input \
     -output /education/$GROUP/$USER/lab3/word-count \
     -mapper "python3 mapper.py" -reducer "python3 reducer.py"
   ```

6. Check the output at `/education/$GROUP/$USER/lab3/word-count`

### Design a MapReduce job to get the most frequent word

Now, we want to get the **most frequent word** of the input by using the output of our previous `word_count` job.

Design a MapReduce job by defining:

- The output produced by the mapper
- The computation performed by the reducer

**Do not cheat:** You cannot control the number of reduce tasks that will run (there can be more than 1 reduce in 1 reducer container).

### Write the most_frequent MapReduce job

1. Implement the `most_frequent` MapReduce job in Python. Use the `word_count` mapper and reducer as inspiration.
2. Run your job. Specify `-D stream.non.zero.exit.is.failure=false` to avoid troubles:

   ```bash
   mapred streaming -D stream.non.zero.exit.is.failure=false \
     -files most_frequent/mapper.py,most_frequent/reducer.py \
     -input /education/$GROUP/$USER/lab3/word-count \
     -output /education/$GROUP/$USER/lab3/most-frequent \
     -mapper "python3 mapper.py" -reducer "python3 reducer.py"
   ```

3. Check the result in the specified output directory. 

## python-sparselda
================
python-sparselda is a Latent Dirichlet Allocation topic modeling package based on SparseLDA Gibbs Sampling inference algorithm, and developed with Python. 
RTFSC for more details.

Please use the github issue tracker for python-sparselda at:
https://github.com/fandywang/python-sparselda/issues

## Usage
================
### 1. Install Google Protocol Buffers (protobuf)
    wget https://protobuf.googlecode.com/files/protobuf-2.5.0.tar.bz2
    tar -zxvf protobuf-2.5.0.tar.bz2
    cd protobuf-2.5.0
    ./configure
    make
    sudo make install
    cd python
    python ./setup.py build
    sudo python ./setup.py install
    
    cd python-sparselda/common
    protoc -I=. --python_out=. lda.proto

### 2. Training
    Usage: python lda_trainer.py -h.

    Options:
      -h, --help            show this help message and exit
      --corpus_dir=CORPUS_DIR
                            the corpus directory.
      --vocabulary_file=VOCABULARY_FILE
                            the vocabulary file.
      --num_topics=NUM_TOPICS
                            the num of topics.
      -topic_prior=TOPIC_PRIOR
                            the topic prior alpha.
      --word_prior=WORD_PRIOR
                            the word prior beta.
      --total_iterations=TOTAL_ITERATIONS
                            the total iteration.
      --model_dir=MODEL_DIR
                            the model directory.
      --save_model_interval=SAVE_MODEL_INTERVAL
                            the interval of save_model action.
      --topic_word_accumulated_prob_threshold=TOPIC_WORD_ACCUMULATED_PROB_THRESHOLD
                            the accumulated_prob_threshold of topic words.
      --save_checkpoint_interval=SAVE_CHECKPOINT_INTERVAL
                            the interval of save_checkpoint action.
      --checkpoint_dir=CHECKPOINT_DIR
                            the checkpoint directory.
      --compute_loglikelihood_interval=COMPUTE_LOGLIKELIHOOD_INTERVAL
                            the interval of compute_loglikelihood action.
### 3. Inference
     Usage: python lda_inference.py -h.

     Options:
      -h, --help            show this help message and exit
      --model_dir=MODEL_DIR
                            the lda model directory.
      --vocabulary_file=VOCABULARY_FILE
                            the vocabulary file.
      --document_file_file=DOCUMENT_FILE_FILE
                           the document file in gbk, line fmt: w1 \t w2 \t w3 ... .
      --num_markov_chains=NUM_MARKOV_CHAINS
                            the num of markov chains.
      --total_iterations=TOTAL_ITERATIONS
                            the num of total_iterations.
      --burn_in_iterations=BURN_IN_ITERATIONS
                            the num of burn_in iteration.
                            
    
### 4. Evaluation

## TODO
================
1. Optimize hyperparameters.
2. Infer topic top words distribution.
3. Parallelization or Multi-threading.

## References
================
1. D. Blei, A. Ng, and M. Jordan. Latent Dirichlet allocation. Journal of Machine Learning Research, 2003.
2. Gregor Heinrich. Parameter estimation for text analysis. Technical Note, 2004.
3. Griﬃths, T. L., & Steyvers, M. Finding scientiﬁc topics. Proceedings of the National Academy of Sciences(PNAS), 2004.
4. I. Porteous, D. Newman, A. Ihler, A. Asuncion, P. Smyth, and M. Welling. Fast collapsed Gibbs sampling for latent Dirichlet allocation. In SIGKDD, 2008.
5. Limin Yao, David Mimno, Andrew McCallum. Efficient methods for topic model inference on streaming document collections, In SIGKDD, 2009.
7. X. Wei, W. Bruce Croft. LDA-based document models for ad hoc retrieval. In Proc. SIGIR. 2006.
8. Rickjin, LDA 数学八卦. Technical Note, 2013.

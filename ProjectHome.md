asymmetric prior Latent Dirichlet Allocation (LDA) by c++<br>

Usually, symmetric dirichlet prior is used in the implementation of lda. in "Rethinking LDA:Why Priors Matter" , they have showed that asymmetric prior can generate better result and stable topic distribution under the increment of topic number. So, in this project, we adopt this algorithm.<br>

other features：<br>
#easy to use, easy to understand<br>
#small memory used<br>

TODO list:<br>
Fast Collapsed Gibbs Sampling<br>
parallelized Gibbs Sampling<br>

<br>
Checkout source code in 'Source' tab <br>
or download <a href='https://docs.google.com/file/d/0B-w3cudI8EORMjRVS2JBNUNlcEk/edit?usp=sharing'>the source code</a> (google drive)<br>
or download <a href='https://docs.google.com/file/d/0B-w3cudI8EORcUlrVnBpX2R2MmM/edit?usp=sharing'>the source code with test data</a> (google drive)<br>
<br>
ML tools:<br>
as-lda: <a href='https://code.google.com/p/as-lda/'>https://code.google.com/p/as-lda/</a><br>
gbdt: <a href='http://code.google.com/p/simple-gbdt/'>http://code.google.com/p/simple-gbdt/</a><br>
adaboost: <a href='http://code.google.com/p/simple-adaboost/'>http://code.google.com/p/simple-adaboost/</a><br>

--------how to use it-----------<br>
<pre><code>Usage: 
  -c  corpus file, default './corpus.txt' 
  -v  vocab file, default './vocab.txt' 
  -e or -i  act type(e for estimate,i for inference) 
  -m  model files dir, default './models' 
  -z  pre model assignment file ( inference ) 
  -a  hyperparameter alpha, default 500/topic_num
  -b  hyperparameter beta, default 0.1
  -k  topic number, default 100
  -n  max iteration number, default 1000
</code></pre>

Examples:<br>
<blockquote>extimate: ./as_lda -e -c ./corpus.txt -v ./vocab.txt -n 2000<br>
inference: ./as_lda -i -n 100 -c corpus.txt.test -v vocab.txt -z ./models/model.z<br>
--------input format------------<br>
For corpus:<br>
one line one doc, the number stands for word id<br>
example:<br>
2699\t10608\t52656\t17781\t17781\t7900\t24007<br>
For vocab：<br>
one line one word，word id is the line number<br>
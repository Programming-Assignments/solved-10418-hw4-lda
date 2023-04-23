Download Link: https://assignmentchef.com/product/solved-10418-hw4-lda
<br>



<h1>1          Written Questions</h1>

Answer the following questions in the template provided. Then upload your solutions to Gradescope. You may use L<sup>A</sup>T<sub>E</sub>X or print the template and hand-write your answers then scan it in. Failure to use the template may result in a penalty. There are 56 points and 10 questions.

1.1       Markov Chain Monte Carlo Methods

<ol>

 <li>In class, we studied two Monte Carlo estimation methods: rejection sampling and importance sampling. Given a proposal distribution <em>Q</em>(<em>x</em>), answer the following questions:

  <ul>

   <li>(1 point) If sampling from <em>Q</em>(<em>x</em>) is computationally expensive, which of the following methods is likely to be more efficient?</li>

  </ul></li>

</ol>

Rejection Sampling

Importance Sampling

Both are equally inefficient

<ul>

 <li>(1 point) If <em>Q</em>(<em>x</em>) is high-dimensional, which of the following methods is more efficient?</li>

</ul>

Rejection Sampling

Importance Sampling

Both are equally inefficient

<ul>

 <li>(1 point) For high-dimensional distributions, MCMC methods such as Metropolis Hastings are more efficient than rejection sampling and importance sampling.</li>

</ul>

True

False

<ul>

 <li>(1 point) For low-dimensional distributions, MCMC methods such as Metropolis Hastings produce better sammples than rejection sampling and importance sampling.</li>

</ul>

True

False

<ol start="2">

 <li>(2 points) Suppose you are using MCMC methods to sample from a distribution with multiple modes.</li>

</ol>

Briefly explain what complications may arise while using MCMC.

1.2     Metropolis Hastings

<ol>

 <li>(4 points) Recall that conjugate priors lead to the posterior belonging to the same probability distribution family as the prior. Show that the beta distribution is the conjugate prior for the binomial distribution.</li>

 <li>Show that

  <ul>

   <li>(5 points) The Metropolis Hastings algorithm satisfies detailed balance.</li>

   <li>(5 points) A variant of the Metropolis Hastings algorithm with the acceptance probability defined without the minimum, ie acceptance probability, wouldn’t satisfy the detailed balance.</li>

   <li>(5 points) A sampler which resamples each variable conditioned only on the parents of a Bayesian Network wouldn’t satisfy the detailed balance.</li>

  </ul></li>

</ol>

1.3      Gibbs Sampling and Topic Modeling

<ol>

 <li>(3 points) Consider the following graphical model:</li>

</ol>

Figure 1.1: Bayesian Network Structure

Assume that we run Gibbs sampling on this graph, write the conditional probabilities which will be computed by the sampler for each variable. The variables are sampled in the order <em>A</em>−<em>B</em>−<em>C</em>−<em>D</em>−<em>F</em>−<em>E</em>

<ol start="2">

 <li>Now let’s run a collapsed Gibbs sampler for a topic model on a toy dataset. We will run sampling for a regular LDA (Latent Dirichlet Allocation) model. Suppose our dataset consisting of 4 documents is as follows:</li>

</ol>

X =      {fizz fizz buzz fizz fizz buzz, fizz buzz fizz buzz, foo bar foo bar foo bar, fizz buzz foo bar}

where <em>x<sub>mn </sub></em>refers to the <em>m<sup>th </sup></em>word in document <em>n</em>. The vocabulary of this dataset consists of 4 unique words. Assume that we run our LDA model with 2 topics, prior parameters set to <em>α </em>= 0<em>.</em>1<em>,β </em>= 0<em>.</em>1 and start with the following sample of topic assignments:

Z =      {0 0 1 0 1 1,

1 0 0 1,

0 1 0 1 1 0, 0 1 0 1}

where <em>z<sub>mn </sub></em>refers to the topic assigned to the <em>m<sup>th </sup></em>word in document <em>n</em>. Note that <em>α </em>and <em>β </em>are the prior parameters for the document-topic and word-topic distributions respectively.

<ul>

 <li>(1 point) Compute the word-topic counts table with this assignment</li>

</ul>

<table width="229">

 <tbody>

  <tr>

   <td width="45"> </td>

   <td width="92">0</td>

   <td width="92">1</td>

  </tr>

  <tr>

   <td width="45">fizz</td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

  <tr>

   <td width="45">buzz</td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

  <tr>

   <td width="45">foo</td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

  <tr>

   <td width="45">bar</td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

 </tbody>

</table>

<ul>

 <li>(1 point) Compute the document-topic counts table with this assignment</li>

</ul>

<table width="208">

 <tbody>

  <tr>

   <td width="24"> </td>

   <td width="92">0</td>

   <td width="92">1</td>

  </tr>

  <tr>

   <td width="24">0</td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

  <tr>

   <td width="24">1</td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

  <tr>

   <td width="24">2</td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

  <tr>

   <td width="24">3</td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

 </tbody>

</table>

<ul>

 <li>(2 points) Suppose we want to sample a new topic assignment <em>z</em><sub>00 </sub>for word <em>x</em><sub>00</sub>. Compute the full conditional probability distribution from which this assignment will be sampled under the collapsed Gibbs sampler.</li>

</ul>

<table width="315">

 <tbody>

  <tr>

   <td width="131"> </td>

   <td width="92">0</td>

   <td width="92">1</td>

  </tr>

  <tr>

   <td width="131"></td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

 </tbody>

</table>

<ul>

 <li>(2 points) Assume that the new topic assignment is <em>z</em><sub>00 </sub>= 1. What is the updated word-topic distribution?</li>

</ul>

<table width="229">

 <tbody>

  <tr>

   <td width="45"> </td>

   <td width="92">0</td>

   <td width="92">1</td>

  </tr>

  <tr>

   <td width="45">fizz</td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

  <tr>

   <td width="45">buzz</td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

  <tr>

   <td width="45">foo</td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

  <tr>

   <td width="45">bar</td>

   <td width="92"> </td>

   <td width="92"> </td>

  </tr>

 </tbody>

</table>

1.4      Empirical Questions

The following questions should be completed after you work through the programming portion of this assignment (Section 2).

<ol>

 <li>(10 points) After training your model, report the top 10 most probable words for 5 of your favorite discovered topics. Note that here most probable is defined as the word whose embedding maximizes the <em>t </em>distribution probability for a given class.</li>

</ol>

<table width="358">

 <tbody>

  <tr>

   <td width="50">Rank</td>

   <td width="62">Topic 0</td>

   <td width="62">Topic 1</td>

   <td width="62">Topic 2</td>

   <td width="62">Topic 3</td>

   <td width="62">Topic 4</td>

  </tr>

  <tr>

   <td width="50">1</td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

  </tr>

  <tr>

   <td width="50">2</td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

  </tr>

  <tr>

   <td width="50">3</td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

  </tr>

  <tr>

   <td width="50">4</td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

  </tr>

  <tr>

   <td width="50">5</td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

  </tr>

  <tr>

   <td width="50">6</td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

  </tr>

  <tr>

   <td width="50">7</td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

  </tr>

  <tr>

   <td width="50">8</td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

  </tr>

  <tr>

   <td width="50">9</td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

  </tr>

  <tr>

   <td width="50">10</td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

   <td width="62"> </td>

  </tr>

 </tbody>

</table>

<ol start="2">

 <li>(10 points) Plot the log-likelihood of the data defined by equation 2 over training for 50 iterations. Record this probability every 10 iterations. <em>Note: Your plot must be machine generated.</em></li>

 <li>(1 point) Multiple Choice: Did you correctly submit your code to Autolab?</li>

</ol>

Yes

No

<ol start="2">

 <li>(1 point) Numerical answer: How many hours did you spend on this assignment?.</li>

</ol>

1.6      Collaboration Policy

After you have completed all other components of this assignment, report your answers to the collaboration policy questions detailed in the Academic Integrity Policies for this course.

<ol>

 <li>Did you receive any help whatsoever from anyone in solving this assignment? If so, include full details including names of people who helped you and the exact nature of help you received.</li>

 <li>Did you give any help whatsoever to anyone in solving this assignment? If so, include full details including names of people you helped and the exact nature of help you offered.</li>

 <li>Did you find or come across code that implements any part of this assignment? If so, include full details including the source of the code and how you used it in the assignment.</li>

</ol>

<h1>2          Programming [ pts]</h1>

2.1      Task Background

Topic modeling is the task of finding latent semantic categories that group words together called <em>topics</em>. The typical approach to this task is to build a model by telling a generative story: For each document we assign a probability of picking a set of topics and for each topic I have some probability of picking any given word. The decision of what these probabilities are and how our generative story plays out determines not just how successful our model is, but also how computationally feasible inference is.

Because we’ve seen the power of vector representations of words in previous assignments, let’s assume that we want to model words as vectors in R<em><sup>M</sup></em>. A reasonable assumption is that words that belong to similar topics are close to each other in embedding space. One way to encode this intuition is to say that given a topic <em>k</em>, a word embedding <strong>v </strong>is drawn from the distribution N(<em>µ</em><em><sub>k</sub></em><em>,I</em>). This implies that if we can discover these <em>µ</em><em><sub>k</sub></em>s we can discover a set of topics that explain our observed words. In order to make this practical, we’ll need to flesh out our generative story.

Suppose we’re given a corpus of <em>D </em>documents and a fixed number of topics <em>K</em>. Our model will look like this:

<ol>

 <li>For topic <em>k </em>= 1 to <em>K</em>:</li>

</ol>

(a) Draw topic mean <em>µ</em>

<ol start="2">

 <li>For each document <em>d </em>in corpus <em>D</em>:

  <ul>

   <li>Draw topic distribution <em>θ</em><em><sub>d </sub></em>∼ Dir(<em>α</em>)</li>

   <li>For each word index <em>n </em>from 1 to <em>N<sub>d</sub></em></li>

  </ul></li>

</ol>

<ol>

 <li>Draw a topic <em>z<sub>n </sub></em>∼ Categorical(<em>θ</em><em><sub>d</sub></em>) ii. Draw <strong>v</strong><em><sub>d,n </sub></em>∼ N(<em>µ</em><em><sub>z</sub></em><em><sub>n</sub></em><em>,I</em>)</li>

</ol>

In our case, we will fix <em>K </em>= 5, |<em>D</em>| = 1208, and our embeddings live in R<sup>50</sup>.

We will see in section 2.3 how this can be translated into a practical sampling algorithm.

<ul>

 <li>Data</li>

</ul>

For this task we’ve provided you with a selection of news articles in the numpy file news_corpus.npy. This array is |<em>D</em>| × |<em>V </em>| where <em>V </em>is our vocabulary. Each <em>i,j </em>entry corresponds to the number of instances of word <em>j </em>in document <em>i</em>.

In order to save you the trouble of training word embeddings before you can even start the real task, we have also provided 50 dimensional GloVe embeddings in the numpy file named news_embeddings.npy along with a dictionary to map between words to indices in the pickle file named mews_word2index.pkl. The embedding array is a |<em>V </em>| × 50 array.

<ul>

 <li>Gibbs Sampler</li>

</ul>

Given the generative model described earlier we’d like to know the posterior distribution over our parameters. As is the case for almost all interesting models, we don’t have an analytical form for this. We’ll make do by approximating the posterior with a collapsed Gibbs sampler. It’ll be a Gibbs sampler because we will iteratively sample word-topic assignments conditioned on all over assignments and parameters. It’s said to be collapsed because we will have integrated over nuisance parameters to provide a simpler distribution to sample from.

(2.1)

Equation 2.1 shows the full conditional on which we can build a Gibbs sampler. This equation has a lot to unpack.

<h2>Prior Parameters</h2>

In the above equation, our prior parameters were summarized as the tuple <em>ξ </em>= (<em>µ</em><em>,κ,</em><strong>Σ</strong><em>,ν</em>) along with the vector of parameters <em>α</em>. These are the same parameters as those in the introductory section. We will treat the hyperparameter <em>α </em>as <em>α<sub>i </sub></em>= 10 for all classes <em>i</em>. We will also set <em>κ </em>= 0<em>.</em>01, <strong>Σ </strong>= <em>I<sub>M</sub></em>, and <em>ν </em>= <em>M</em>.

<h2>Data Statistics</h2>

<em>N<sub>k </sub></em>= #{words assigned to topic <em>k </em>across all documents}

<h2>Updated Parameters</h2>

<em>κ<sub>k </sub></em>= <em>κ </em>+ <em>N<sub>k </sub>ν<sub>k </sub></em>= <em>ν </em>+ <em>N<sub>k </sub></em><em>µ</em>

<h2>Important Distributions</h2>

The most important distribution for you to be familiar with for this assignment is the multivariate <em>t </em>distribution given parameters (<em>µ</em><em><sub>k</sub></em><em>,κ<sub>k</sub>,ν</em><sup>0</sup>). The final parameter is the degrees of freedom for the distribution and is denoted in the subscript of the distribution <em>t<sub>ν</sub></em>0(·). We have provided a function in the file utils.py called multivariate_t_distribution that will return log-probabilities according to this model.

2.4     Implementation Details

Now that we have our notation sorted out, we can ensure that we understand the steps to implement our sampler.

<h2>Implementation Outline</h2>

<ol>

 <li>Load in the provided embeddings and the text of our corpus.</li>

 <li>Randomly initialize a dictionary that places each word in each document into a given topic.</li>

 <li>Calculate statistics and update our posterior parameters and calculate the full conditional in equation 1 for each word and each possible topic assignment. Note: This will require adjusting the statistics to not include the current word.</li>

 <li>Normalize the above distributions and sample from a multinomial over the <em>k </em>topics with the posterior distribution.</li>

 <li>Reassign words to topics based on the above samples.</li>

 <li>Go back to step 4 and repeat until convergence.</li>

</ol>

<h2>Numerical Issues</h2>

For numerical stability, you must calculate log-probabilities and only convert to regular probability distribution before the normalization step.

One way to increase stability is to keep track of the maximum log-probability encountered while iterating over topics in step 5. Then before normalization, subtract of this maximum log-probability from each logprobability.

2.5     Evaluation

We will track the joint probability of <em>z<sub>k</sub>,v<sub>d,i</sub>,</em><em><sup>µ</sup></em><em><sub>k</sub></em><em>,θ<sub>d</sub></em>, for each word <em>i</em>, document <em>d</em>, and currently assigned category <em>k</em>. This will be calculate using the following equation.

<em>p</em>(<em>z<sub>k</sub>,v<sub>d,i</sub>,</em><em>µ</em><em><sub>k</sub></em><em>,θ<sub>d</sub></em>) = <em>p</em>(<em>v<sub>d,i</sub></em>|<em>z<sub>k</sub>,</em><em>µ</em><em><sub>k</sub></em>)<em>p</em>(<em>z<sub>k</sub></em>|<em>θ<sub>k</sub></em>)<em>p</em>(<em>µ</em><em><sub>k</sub></em>)<em>p</em>(<em>θ<sub>d</sub></em>)                                                 (2.2)

Please refer to the generative model for Gaussian-LDA to define each of these probabilities. Also note that because we’re using a collapsed Gibbs sampler, we will not have estimate one of these parameters before.

2.6      Autolab Submission [35 pts]

You must submit a .tar file named gaussianlda.tar containing gaussianlda.py, which contains all of your code.

You can create that file by running:

tar -cvf gaussianlda.tar gaussianlda.py

from the directory containing your code.

Some additional tips: DO NOT compress your files; you are just creating a tarball. Do not use tar -czvf. DO NOT put the above files in a folder and then tar the folder. Autolab is case sensitive, so observe that all your files should be named in lowercase. You must submit this file to the corresponding homework link on Autolab.

Your code will not be autograded on Autolab. Instead, we will grade your code by hand; that is, we will read through your code in order to grade it. As such, please carefully identify major sections of the code via comments.
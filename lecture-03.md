# Machine Learning & Neural Networks – CS401 – Barak Pearlmutter
## Lecture 3

### Types of Machine Learning
- Supervised, i.e. Linear Regression
- Unsupervised
- Reinforcement learning

#### Linear Regression
Different flavours:
- ~~batch algorithm~~ (no good, booooo)

![Batch Algorithm Equation](Eq1.gif)

![Linear Equation](Eq2.gif)  
This becomes the linear equation above which we can solve directly using a linear system solver.
So we have an (*n* * *n*) matrix which can be seen as an *n*-dimensional vector.


- Another flavour: online algorithm (yay)

An example of an online algorithm:
> Patients getting treatment – resources should be shifted gradually as statistics come in RE which medicine works well

##### Classification (vs. regression)
Classification is different to regression.
![Input Space](Eq3.gif)

When do we use classification/regression?
Medical diagnoses
* some things are continuous numbers – regression
* others are discrete (i.e. sex etc.) – classification

![Output Space](Eq4.gif)
* ![Regression](Eq5.gif)
* ![Classification](Eq6.gif)

The problem is that our linear regression/classification "box" does linear mappings. This is not always what we want; for instance sometimes we want non-linear patterns.

For machine learning to be feasible the following space needs to be narrowed down:
![Concept Space](Eq7.gif)
![Weight Space](Eq8.gif)

### History Time! (or Rosenblatt's Perceptron)
Frank Rosenblatt was friends with Marvin Minksy, both of whom were pioneers in AI. Their idea was to solve classification:
* They thought up a machine that mapped to boolean using a linear classifier (similar to L.R.)
  * Aside: [Knuth/Iverson notation](https://en.wikipedia.org/wiki/Iverson_bracket)
* How do you do this?
  * Online algorithm – Perceptron algorithm (input/output pair).
    * Take inputs and run through fixed preprocessor. Every pair of input lines do AND/OR operations.
    * Hardware – special purpose analog.
      * Knobs on the "w" box-machine – they wanted to twiddle the knobs as little as possible.
    * However, if the output is false yet the desired output is true – what to do?
        * ![w-equation](Eq9.gif)
        * ![w-sigma](Eq10.gif)
    * In order to converge on the right answer we consider our input space as a Cartesian plane where *x*<sub>1</sub> is tracked on the *x*-axis and *x*<sub>2</sub> is tracked on the *y*-axis. Thus we get the following equation:
        ![converging eq](Eq11.gif)

      * Intuition: using weight w we choose it such that *x*<sub>1</sub>, *x*<sub>2</sub> vectors dotted together are positive

  * Perceptron Learning Theorem:
    * ![plt](Eq12.gif)
    * Taking ome subset of the training set – if we learn from it we can get correct output every time with enough modifications to *w*.
    * A cautionary tale: tanks in the Cold War. Researchers looking to build a training set for a machine that would automatically identify tanks asked a military base to provide them with pictures of tanks. When running tests they got the machine to correctly identify tanks based on this training data. However they soon found that this was merely luck – the pictures they had been sent of tanks were taken in daylight so the machine had learned that all photos that were not in the daylight or slightly darker were photos of not-tanks.

#### Some videos:

Perceptron Research from the 50s and 60s

https://www.youtube.com/watch?v=cNxadbrN_aI

https://www.youtube.com/watch?v=evVSV43CRk0

Modern outgrowth of that work?

https://www.youtube.com/user/stanfordhelicopter

Download Link: https://assignmentchef.com/product/solved-csc421-2516-homework-4
<br>
<strong>Submission: </strong>You must submit your solutions as a PDF through MarkUs. You can produce the file however you like (e.g. LaTeX, Microsoft Word, scanner) as long as it is readable.

<strong>Late Submission: </strong>MarkUs will remain open until 3 days after the deadline, after which no late submissions will be accepted. The late penalty is 10% per day, rounded up.

Weekly homeworks are individual work. See the Course Information handout<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> for detailed policies.

<ol>

 <li><strong>LSTM Gradient [4pts] </strong>Here, you’ll derive the Backprop Through Time equations for the univariate version of the Long-Term Short-Term Memory (LSTM) architecture.</li>

</ol>

For reference, here are the computations it performs:

<em>i</em>(<em>t</em>) = <em>σ</em>(<em>w<sub>ix</sub>x</em>(<em>t</em>) + <em>w<sub>ih</sub>h</em>(<em>t</em>−1)) <em>f</em>(<em>t</em>) = <em>σ</em>(<em>w<sub>fx</sub>x</em>(<em>t</em>) + <em>w<sub>fh</sub>h</em>(<em>t</em>−1)) <em>o</em>(<em>t</em>) = <em>σ</em>(<em>w<sub>ox</sub>x</em>(<em>t</em>) + <em>w<sub>oh</sub>h</em>(<em>t</em>−1)) <em>g</em>(<em>t</em>) = tanh(<em>w</em><em>gxx</em>(<em>t</em>) + <em>w</em><em>ghh</em>(<em>t</em>−1)) <em>c</em>(<em>t</em>) = <em>f</em>(<em>t</em>)<em>c</em>(<em>t</em>−1) + <em>i</em>(<em>t</em>)<em>g</em>(<em>t</em>) <em>h</em>(<em>t</em>) = <em>o</em>(<em>t</em>) tanh(<em>c</em>(<em>t</em>))

<ul>

 <li><strong>[3pts] </strong>Derive the Backprop Through Time equations for the activations and the gates:</li>

</ul>

You don’t need to vectorize anything or factor out any repeated subexpressions.

<ul>

 <li><strong>[1pt] </strong>Derive the BPTT equation for the weight <em>w<sub>ix</sub></em>:</li>

</ul>

<em>w<sub>ix </sub></em>=

(The other weight matrices are basically the same, so we won’t make you write those out.)

<ul>

 <li><strong>[optional, no points] </strong>Based on your answers above, explain why the gradient doesn’t explode if the values of the forget gates are very close to 1 and the valu<u>es </u>of the <u>in</u>put and output gates are very close to 0. (Your answer should involve both <em>h</em><sup>(<em>t</em>) </sup>and <em>c</em><sup>(<em>t</em>)</sup>.)</li>

</ul>

1




<ol start="2">

 <li><strong>Multidimensional RNN [3pts] </strong>One of the predecessors to the PixelRNN architecture was the multidimensional RNN (MDRNN). This is like the RNNs we discussed in lecture, except that instead of a 1-D sequence, we have a 2-D grid structure. Analogously to how ordinary RNNs have an input vector and a hidden vector for every time step, MDRNNs have an input vector and hidden vector for every grid square. Each hidden unit receives bottom-up connections from the corresponding input square, as well as recurrent connections from its north and west neighbors as follows:</li>

</ol>

The activations are computed as follows:

<strong>h</strong><em> .</em>

For simplicity, we assume there are no bias parameters. Suppose the grid is <em>G</em>×<em>G</em>, the input dimension is <em>D</em>, and the hidden dimension is <em>H</em>.

<ul>

 <li><strong>[1pt] </strong>How many weights does this architecture have? How many arithmetic operations are required to compute the hidden activations? (You only need to give big-O, not an exact count.)</li>

 <li><strong>[1pt] </strong>Suppose that in each step, you can compute as many matrix-vector multiplications as you like. How many steps are required to compute the hidden activations? Explain your answer.</li>

 <li><strong>[1pt] </strong>Give one advantage and one disadvantage of an MDRNN compared to a conv net.</li>

</ul>

<ol start="3">

 <li><strong>Reversibility [3pts] </strong>In lecture, we discussed reversible generator architectures, which enable efficient maximum likelihood training. In this question, we consider another (perhaps surprising) example of a reversible operation: gradient descent with momentum. Suppose the parameter vector <em>θ </em>(and hence also the velocity vector <strong>p</strong>) are both <em>D</em>-dimensional. Recall that the updates are as follows:</li>

</ol>

<strong>p</strong>(<em>k</em>+1) ← <em>β</em><strong>p</strong>(<em>k</em>) − <em>α</em>∇J(<em>θ</em>(<em>k</em>)) <em>θ</em>(<em>k</em>+1) ←<em>θ</em>(<em>k</em>) + <strong>p</strong>(<em>k</em>+1)

If we denote <strong>s</strong><sup>(<em>k</em>) </sup>= (<em>θ</em><sup>(<em>k</em>)</sup><em>,</em><strong>p</strong><sup>(<em>k</em>)</sup>), then we can think of the above equations as defining a function <strong>s</strong>(<em>k</em>+1) = <em>f</em>(<strong>s</strong>(<em>k</em>)).

<ul>

 <li><strong>[1pt] </strong>Show how to compute the inverse, <strong>s</strong><sup>(<em>k</em>) </sup>= <em>f</em><sup>−1</sup>(<strong>s</strong><sup>(<em>k</em>+1)</sup>).</li>

 <li><strong>[2pts] </strong>Find the determinant of the Jacobian, i.e.</li>

</ul>

det<em>∂</em><strong>s</strong>(<em>k</em>+1)<em>/∂</em><strong>s</strong>(<em>k</em>)<em>.</em>

<em>Hint: first write the Jacobian as a product of two matrices, one for each step of the above algorithm.</em>

2

<a href="#_ftnref1" name="_ftn1">[1]</a> <a href="http://www.cs.toronto.edu/~rgrosse/courses/csc421_2019/syllabus.pdf">http://www.cs.toronto.edu/</a><a href="http://www.cs.toronto.edu/~rgrosse/courses/csc421_2019/syllabus.pdf">~</a><a href="http://www.cs.toronto.edu/~rgrosse/courses/csc421_2019/syllabus.pdf">rgrosse/courses/csc421_2019/syllabus.pdf</a>
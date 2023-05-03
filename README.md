Download Link: https://assignmentchef.com/product/solved-cs1675-homework3-linear-regression-using-closed-form-solution
<br>
In this assignment, you will solve a regression problem in two ways: using the closed-form least-squares solution, and using gradient descent.

<u>Part I: Linear regression using closed-form solution</u>

[5 pts] Write a function <span style="font-family: courier new;">[w] = lr_solve_closed(X_train, y_train)</span> that computes the closed-form least-squares solution to linear regression, using the Moore-Penrose inverse, as derived in class. Use the Matlab function <span style="font-family: courier new;">pinv</span>. The body of this function only requires one line of code.

<b>Inputs:</b>

<ul>

 <li><span style="font-family: courier new;">X_train</span> is an NxD feature matrix with N samples and D feature dimensions. N is the number of samples in the training set.</li>

 <li><span style="font-family: courier new;">y_train</span> is an Nx1 vector containing the labels for the training set. The i-th sample in <span style="font-family: courier new;">y_train</span> should correspond to the i-th row in <span style="font-family: courier new;">X_train</span>.</li>

</ul>

<b>Outputs:</b>

<ul>

 <li><span style="font-family: courier new;">w</span> is a Dx1 vector of weights (one per feature dimension).</li>

</ul>

[5 pts] Also write a function <span style="font-family: courier new;">[y_pred] = lr_predict(X_test, w)</span> that uses the weights computed above, to predict a label for a new test sample.

<b>Inputs:</b>

<ul>

 <li><span style="font-family: courier new;">X_test</span> is an MxD feature matrix with M samples and D feature dimensions. M is the number of samples in the test set.</li>

 <li><span style="font-family: courier new;">w</span> is a Dx1 vector of weights.</li>

</ul>

<b>Outputs:</b>

<ul>

 <li><span style="font-family: courier new;">y_pred</span> is the predicted Mx1 vector of labels for the test set.</li>

</ul>

<u>Part II: Linear regression using gradient descent</u>

Now implement the gradient descent solution, in a function <span style="font-family: courier new;">[w] = lr_solve_gd(X_train, y_train, iters, eta)</span>.

<b>Inputs:</b> same as for <span style="font-family: courier new;">lr_solve_closed</span>, plus:

<ul>

 <li><span style="font-family: courier new;">iters</span>, the number of iterations to run gradient descent for, and</li>

 <li><span style="font-family: courier new;">eta</span>, the learning rate to use in the weight update.</li>

</ul>

<b>Outputs:</b> same as for <span style="font-family: courier new;">lr_solve_closed</span>.

<b>Instructions:</b>

<ol>

 <li>[5 pts] First, initialize the weights in some way (use either random values or all zeros).</li>

 <li>[10 pts] Second, repeat the following <span style="font-family: courier new;">iters</span> times. In each iteration, first compute the loss function gradient using all training data points. To do this, you need to use <span style="font-family: courier new;">lr_predict.m</span>.</li>

 <li>[5 pts] Then, adjust the weights in the direction opposite to the gradient.</li>

</ol>

<u>Part III: Testing on the Wine Quality dataset</u>

You will use the <a href="https://archive.ics.uci.edu/ml/datasets/Wine+Quality">Wine Quality</a> dataset. Use only the red wine data. The goal is to find the quality score of some wine based on its attributes. Include your code in a script <span style="font-family: courier new;">regression.m</span>. In a file <span style="font-family: courier new;">report.pdf</span> or <span style="font-family: courier new;">report.docx</span>, report the L2 error (described below) for the closed-form and gradient descent solutions.

<ol>

 <li>[10 pts] First, download the <span style="font-family: courier new;">winequality-red.csv</span> file, load it in Matlab (e.g. using <span style="font-family: courier new;">dlmread</span>) and divide the data into a training and test set using approximately 50% for training. Standardize the data, by computing the mean and standard deviation for each feature dimension using the train set only, then subtracting the mean and <span style="color: red;">dividing by the</span> stdev for each feature and each sample. Append a 1 for each feature vector, which will correspond to the bias that our model learns.</li>

 <li>[5 pts] Find the direct closed-form solution and evaluate the accuracy on the test set, by computing the L2 distance between the predicted vector <span style="font-family: courier new;">y_pred</span> and the ground-truth vector <span style="font-family: courier new;">y_test</span>. Print the L2 error in your script, with an appropriate description for what is being printed; use <span style="font-family: courier new;">fprintf</span>. Include it in your report.</li>

 <li>[5 pts] Now compute and evaluate the gradient descent solution. Use 50 iterations, and experiment with the following values for the learning rate: <span style="font-family: courier new;">10.^(-6:-1)</span>. Evaluate the L2 distance between predicted and ground-truth test labels as above. Print the errors for each learning rate and include them in your report.</li>

</ol>

<b>Submission:</b> Please include the following files:

<ul>

 <li><span style="font-family: courier new;">lr_solve_closed.m</span></li>

 <li><span style="font-family: courier new;">lr_predict.m</span></li>

 <li><span style="font-family: courier new;">lr_solve_gd.m</span></li>

 <li><span style="font-family: courier new;">regression.m</span></li>

 <li><span style="font-family: courier new;">report.pdf/docx</span></li>

</ul>
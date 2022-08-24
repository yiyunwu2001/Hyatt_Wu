# Random-number-generation-using-boson-sampling---ORCA-Computing
**Womanium Quantum Hackathon 2022**

**Team Name: Hyatt & Wu**

**Team Member 1: YiYun Wu**<br>
<p>Discord ID: YiYun#8116<br>
GitHub ID: yiyunwu2001<br>
Email: yiyunwu@arizona.edu</p>

**Team Member 2: Atkin Hyatt**<br>
<p>Discord ID:<br>
GitHub ID: atkindh<br>
Email: atkindh@gmail.com</p>

**Name of Pitch Presenter: Atkin Hyatt**

**Name of Challenge: Random number generation using boson sampling (ORCA Computing)**

**Hack Solution Details:**<br>
<p><em><strong>Overview of RNG Solution</strong></em></p>
<p>To simulate a boson sampling QRNG, this team used the Perceval package and consulted their webpage on boson sampling (https://perceval.quandela.net/docs/notebooks/Boson%20Sampling.html). Using the sample code as a guide, we defined 14 photons at the input and 60 modes, simulated a boson sampling circuit,and saved 2 output samples. We then performed Von-Neuman post processing using the 2 samples to get a final string, which we saved into a .txt file. Iterating this process allowed us to generate a sizable amount of random bits.</p>
<p align="center">
<img width="400" alt="Screen Shot 2022-08-23 at 12 06 13 PM" src="https://user-images.githubusercontent.com/98360062/186245707-12d1cc5f-c5e0-4e05-aada-ecc729a82778.png">

<p><em><strong>NIST SP 800-22 (Statistical Test Suite for Random and Pseudorandom Number Generators)</strong></em></p>
<p>The team generated a stream of 1000000 bits, saved them into a .txt file, and tested the data with the NIST test package. The random bits generated by our RNG passed most of the tests. The errors we encountered in testing could be due to incompatibilities between the input file format and the test package.</p>
<p align="center">
<img width="400" alt="Screen Shot 2022-08-23 at 4 07 46 AM" src="https://user-images.githubusercontent.com/98360062/186245826-7a0d8e09-9291-413a-85f9-700d92205c3a.png">
<p>In the screenshot of the test results below, the proportion refers to the fraction of bitstreams that passed a particular test. Stars indicate unsuccessful tests that did not produce reliable or interpretable results.</p>
<p align="center">
<img width="400" alt="Screen Shot 2022-08-23 at 12 11 53 PM" src="https://user-images.githubusercontent.com/98360062/186245512-947a1468-a69b-4d64-90ca-e067e4622405.png">
<p>Please see the "finalAnalysisReport.txt" (https://github.com/yiyunwu2001/Hyatt_Wu/blob/main/finalAnalysisReport.txt) file for the full results from the NIST test package.</p>

<p><em><strong>Bit Rate in bps (bits per second)</strong></em></p>
<p>The bit rate for our boson sampling RNG was found by timing the execution of the code block responsible for taking 2 samples and performing Von-Neuman post processing.</p>
<p align="center">
<img width="400" alt="Screen Shot 2022-08-23 at 11 39 29 AM" src="https://user-images.githubusercontent.com/98360062/186246119-6d3e8a31-74d5-4429-827c-c4c954f49475.png">
<p>The table below shows the bit rates we found by repeatedly generating 10000 bits with our RNG. The average, maximum, and minimum bit rates found are displayed below. </p>
<p align="center">
<img width="239" alt="image" src="https://user-images.githubusercontent.com/98360062/186239903-d5f560cf-44b0-47dc-a69e-68eb701d245e.png">

<p><em><strong>Application of Boson Sampling: Monte Carlo Algorithms</strong></em></p>
<p>Monte Carlo algorthims are a class of techniques which involve random sampling to numerically obtain results. Monte Carlo methods are typically employed when systems are too complex for deterministic algorithms to handle. Although computationally simple, Monte Carlo algorithms rely on vast quantities of randomly generated numbers. Classical random number generators lack the ability to generate truly random numbers, revealing certain correlations and non-randomness given a large enough set. This is where a quantum random number generator (QRNG) with quantum advantage can come to the rescue. Not only does a QRNG produce truly random numbers, it also has the ability to produce them faster than their classical counterparts.</p>

<p><em><strong>Monte Carlo Integration: Area from Sampling</strong></em></p>
<p>In this challenge, Monte Carlo sampling is used to numerically evaluate integrals over finite bounds. The integral of a function is equivalent to the area between the curve and the x-axis. The area of a shape is essentially how much hypothetical stuff can be contained within the walls of that shape. Hence we can relate the area of some shape to the amount of points that lie within its walls. The area, and therefore an integral, can then be found by sampling the points inside that shape, the points between the curve and the x-axis. But how can we ensure that the points we decide to sample are fair and unbiased? This is where Monte Carlo sampling comes in. After picking a set of random points, we count how many land between the x-axis and the curve and divide that by the total number of points we chose to sample (see below). Since integrals take into account whether the area is above or below the x-axis, we simply count up when a point lies above the axis and under the curve and count down when the point is below the axis and above the curve. Finally, we scale this ratio by the bounds of our random numbers to obtain the result of our integration.</p>
<p align="center">
<img width="418" alt="Screen Shot 2022-08-23 at 7 40 01 PM" src="https://user-images.githubusercontent.com/110840448/186306921-fe3d1195-bea0-487c-a129-eb6315411905.png"></p>
<p>In the example above, we randomly sample 1000 points and count about 339 landed underneith the curve. Our random numbers go from x = -1 to x = 1 and y = 0 to y = 1, meaning the integral of this function over the given interval is approximately 0.678, only 1.7% off from the actual value of 2/3.

<p><em><strong>Scope</strong></em></p>
<p>Of course this technique wouldnt be very useful if we limit ourselves to measly one dimentional integrals for which we have much more powerful tools to tackle.
  
**Sources Consulted:**<br>
https://github.com/terrillmoore/NIST-Statistical-Test-Suite<br>
https://perceval.quandela.net/docs/notebooks/Boson%20Sampling.html<br>

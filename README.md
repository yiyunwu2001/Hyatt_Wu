# Random-number-generation-using-boson-sampling---ORCA-Computing
**Womanium Quantum Hackathon 2022**

**Team Name: Hyatt & Wu**

**Team Member 1: YiYun Wu**<br>
<p>Discord ID: YiYun#8116<br>
GitHub ID: yiyunwu2001<br>
Email: yiyunwu@arizona.edu</p>

**Team Member 2: Atkin Hyatt**<br>
<p>Discord ID:<br>
GitHub ID:<br>
Email: atkindavidhyatt@arizona.edu</p>

**Name of Pitch Presenter:**

**Name of Challenge: Random number generation using boson sampling (ORCA Computing)**

**Hack Solution Details:**<br>
<p><em><strong>Overview of RNG Solution</strong></em></p>
<p>To simulate a boson sampling QRNG, this team used the Perceval package and consulted their webpage on boson sampling (https://perceval.quandela.net/docs/notebooks/Boson%20Sampling.html). Using the sample code as a guide, we defined 14 photons at the input and 60 modes, simulated a boson sampling circuit,and saved 2 output samples. We then performed Von-Neuman post processing using the 2 samples to get a final string, which we saved into a .txt file. Iterating this process allowed us to generate a sizable amount of random bits.</p>
<img width="400" alt="Screen Shot 2022-08-23 at 12 06 13 PM" src="https://user-images.githubusercontent.com/98360062/186245707-12d1cc5f-c5e0-4e05-aada-ecc729a82778.png">

<p><em><strong>NIST SP 800-22 (Statistical Test Suite for Random and Pseudorandom Number Generators)</strong></em></p>
<p>The team generated a stream of 1000000 bits, saved them into a .txt file, and tested the data with the NIST test package. The random bits generated by our RNG passed most of the tests. The errors we encountered in testing could be due to incompatibilities between the input file format and the test package.</p>
<img width="400" alt="Screen Shot 2022-08-23 at 4 07 46 AM" src="https://user-images.githubusercontent.com/98360062/186245826-7a0d8e09-9291-413a-85f9-700d92205c3a.png">
<p>In the screenshot of the test results below, the proportion refers to the fraction of bitstreams that passed a particular test. Stars indicate unsuccessful tests that did not produce reliable or interpretable results.</p>
<img width="400" alt="Screen Shot 2022-08-23 at 12 11 53 PM" src="https://user-images.githubusercontent.com/98360062/186245512-947a1468-a69b-4d64-90ca-e067e4622405.png">
<p>Please see the "finalAnalysisReport.txt" (https://github.com/yiyunwu2001/Hyatt_Wu/blob/main/finalAnalysisReport.txt) file for the full results from the NIST test package.</p>

<p><em><strong>Bit Rate in bps (bits per second):</strong></em></p>
<p>The bit rate for our boson sampling RNG was found by timing the execution of the code block responsible for taking 2 samples and performing Von-Neuman post processing.</p>
<img width="400" alt="Screen Shot 2022-08-23 at 11 39 29 AM" src="https://user-images.githubusercontent.com/98360062/186246119-6d3e8a31-74d5-4429-827c-c4c954f49475.png">
<p>The table below shows the bit rates we found by repeatedly generating 10000 bits with our RNG. The average, maximum, and minimum bit rates found are displayed below. </p>
<img width="239" alt="image" src="https://user-images.githubusercontent.com/98360062/186239903-d5f560cf-44b0-47dc-a69e-68eb701d245e.png">

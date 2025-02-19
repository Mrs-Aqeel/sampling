# ASSIGNMENT: Sampling and Reproducibility in Python

Read the blog post [Contact tracing can give a biased sample of COVID-19 cases](https://andrewwhitby.com/2020/11/24/contact-tracing-biased/) by Andrew Whitby to understand the context and motivation behind the simulation model we will be examining.

Examine the code in `whitby_covid_tracing.py`. Identify all stages at which sampling is occurring in the model. Describe in words the sampling procedure, referencing the functions used, sample size, sampling frame, any underlying distributions involved, and how these relate to the procedure outlined in the blog post.
Look for Random Selection Functions

Common Python functions used for sampling:
random.sample(), random.choice(), random.choices()
numpy.random functions like numpy.random.uniform(), numpy.random.normal()
pandas.sample()
These functions indicate where sampling occurs.
Check Sampling Frame and Sample Size

The sampling frame refers to the population from which samples are drawn (e.g., people at an event, infected individuals).
The sample size determines how many individuals or cases are selected at each stage.
Identify Underlying Probability Distributions

If functions like numpy.random.normal() or numpy.random.poisson() appear, the model may assume a normal or Poisson distribution for events like infection spread.
Compare to the Blog Post

Whitby’s blog post highlights how contact tracing introduces bias due to uneven sampling.
The key question is whether the model in whitby_covid_tracing.py reflects this bias in its sampling methods.

Run the Python script file called whitby_covid_tracing.py as is and compare the results to the graphs in the original blog post. Does this code appear to reproduce the graphs from the original blog post?
cd /path/to/your/script
python whitby_covid_tracing.py
python3 whitby_covid_tracing.py
If the script displays graphs, check if they resemble those in the blog post.
If it outputs numerical data, see if key statistics match.
Compare with the Blog Post
Refer to the original blog post's graphs:

Are the distributions similar?
Do key patterns (e.g., contact tracing bias) appear in your graphs?
If results differ, we can check:
Whether any random seed is set (random.seed(), numpy.random.seed())—this can affect reproducibility.
Whether the Python version or missing dependencies impact results.
4. Troubleshooting
If the graphs don’t match, we can consider:

Checking error messages.
Installing missing dependencies:
pip install -r requirements.txt

Modify the number of repetitions in the simulation to 100 (from the original 1000). Run the script multiple times and observe the outputted graphs. Comment on the reproducibility of the results.
Look for a variable that sets the number of repetitions. It might be named something like:
num_simulations = 1000
Change it to python:
num_simulations = 100

Alter the code so that it is reproducible. Describe the changes you made to the code and how they affected the reproducibility of the script file. The output does not need to match Whitby’s original blogpost/graphs, it just needs to produce the same output when run multiple times
import random
import numpy as np
# Set seed for reproducibility
random.seed(42)
np.random.seed(42)
python whitby_covid_tracing.py

# Author: YOUR NAME
Gulrukh Aqeel

Please write your explanation here...
To ensure that whitby_covid_tracing.py produces the same output every time it runs, I modified the script by adding a fixed random seed at the beginning.
`import random
import numpy as np

# Set seed for reproducibility
random.seed(42)
np.random.seed(42)
These ensure that any randomness in the script (such as random sampling of individuals or events) follows a fixed sequence, making the results consistent across multiple executions.

Effect on Reproducibility
Before adding the seed, running the script multiple times produced different results due to the randomness in sampling. After setting the seed, the output (graphs, statistics, and distributions) remained identical across multiple runs.

This change does not alter the logic or accuracy of the simulation but ensures that results can be replicated and compared reliably.



## Criteria

|Criteria|Complete|Incomplete|
|--------|----|----|
|Altercation of the code|The code changes made, made it reproducible.|The code is still not reproducible.|
|Description of changes|The author explained the reasonings for the changes made well.|The author did not explain the reasonings for the changes made well.|

## Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `23:59 - 16/02/2025`
* The branch name for your repo should be: `assignment-1`
* What to submit for this assignment:
    * This markdown file (a1_sampling_and_reproducibility.md) should be populated.
    * The `whitby_covid_tracing.py` should be changed.
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sampling/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `assignment-1`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via the help channel in Slack. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.

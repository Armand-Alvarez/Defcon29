Hacking Humans with AI as a Service
=================

> Authors:  *Eugene Lim, Glenice Tan, Tan Kee Hock, Timothy Lee*

---

> 06 August 2021

> Armand Alvarez

> github.com/Armand-Alvarez

---


# 01 - Hacking Humans: The Traditional Way

## Social Engineering 101

* **Social Engineering** - Psychological manipulation of people into doing something you want
* Common Influencing Tactics used by engineers:
	* Authority
	* Scarcity
	* Context-specific factors
* 3 common attack vectors of SE:

1. Email Phishing
2. Voice Phishing / Vishing
3. In-person / Physical

* Social Engineering is an art leveraged for different purposes:

1. Malicious actors
2. Red Team exercises
3. Security Training & Awareness

* Typical Red Team Operation

1. OSINT on target - LinkedIn, Twitter, etc
2. Craft Phishing Content 
3. Sends phishing content to target

## Challenges in Phising

1. Time - analyse results from OSINT - Behavior analysis
2. Effort - Contextualize and ideation

---

# 02 - The AI Market Landscape

## AI as a Service

Look at AIaaS to solve time and effort challenges

* AI services can create a personality profile for individuals 

---

# 03 - Hacking Humans: The AI Way

## Piecing Everything Together for Phishing Delivery

* Analyse profile using AI services 
	- Does personality analysis and gives result as JSON file
* Curate potential response
	- Give instructions to OpenAI's GPT3 (i.e. "write an email to John to convince him to join our company") and allow AI to generate phishing email
	- Choose the optimal content

## Our Experiments

* 2 different types of experiments over a period of 3 months, over 200 targets across multiple authorised phishing emails
	1. Investigate effectiveness of convincing targets to click on phishing emails - target receeives AI gen email and human gen email
		* Results: In experiments A and C, AI is way more convincing, in B AI and human gen are about equal
			- In stage 2: AI more convincing in A and B, C was caught by anti-phishing so there are null results
	2. Investigate effectiveness of convincing targets to open "malicious" docs in phishing emails
		* Results: AI got 9.09%, human-gen got ~5%

* Key Observvations
	- AIaaS reduced time required for phishing content generation
	- AI gen phishing content is observed to be more convincing during experiments as compared to human-gen content
	- There is a varying degree of governenece when using AIaaS (i.e. OpenAI was strict over sign up, while others just require an email)

---

# 04 - Defense against the Dark Arts: Protecting the Humans

* Detect Synthetic Text
	- Use AI to detect AI-generated text (fight AI with AI)
		+ Simple classifiers
		+ Zero-shot detection - Makes no assumptions of model AI-generated 
			* GLTR
				- Uses its own language model
				- Uses 3 tests
					1. Probability of the word given previous words in the sequence
					2. Absolute rank of a word
					3. Entropy of the predicted distribution
				- Benefits - easily extensible, tranferrable patters from GPT-2, access to logprobs
				- Challenges - Cannot control top K, no direct access
			* GROVER
		+ Fine-tuning based detection - models that have been trained (comparable to anti-virus signature)

* Fighting Abuses with Governance
	- Use implementationa nd self-assessment guide for organizations
	- policy for explanation and practice general disclosure of use
	- ethical evaluation
	- Implement clear roles and responsibilities for the ehtical deployment of AI

---

# 05 - Conclusions

* Key takeaways
	- Rapid growth of AIaaS has placed advanced, cost-effecitve AI text gen capabilities in hands of global market
	- Automated tools can be used to build defenses, current approaches are brittle and model-dependent
	- Decision makers have the responsibility to implement sound strategies governing the supply and consumption of advanced AIaaS
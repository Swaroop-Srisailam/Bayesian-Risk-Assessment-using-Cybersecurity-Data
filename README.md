# Brief Report: Bayesian Risk Assessment Using Cybersecurity Data

By **Swaroop Srisailam**

A **Bayesian Network** (BN) is a probabilistic graphical model that represents a set of variables and their conditional dependencies through a directed acyclic graph (DAG). In cybersecurity, Bayesian Networks are particularly useful for modeling the complex relationships between various elements such as **threat actors**, **attack vectors**, **vulnerabilities**, and **assets**

* **Threat Actor → Attack Vector**: Different threat actors have different probabilities of using various attack vectors.  
* **Attack Vector → Vulnerability**: Each attack vector has a certain probability of successfully exploiting different system vulnerabilities.  
* **Vulnerability → Asset**: The likelihood of an asset being at risk depends on the vulnerabilities present in the system.

### **Methodology for Bayesian Network Construction and Analysis**

1. **Data Collection**:  
   * Gathered four datasets from given assessment pdf using chat gpt to convert to csv : Asset-Vulnerability, Attack-Vulnerability, Threat Actor-Asset, and Prior Attack Success Rates.  
2. **Bayesian Network Structure**:  
   * Defined relationships between nodes: Threat Actor → Attack Vector → Vulnerability → Asset.  
3. **Conditional Probability Distributions (CPDs)**:  
   * **Threat Actor**: Based on prior attack success rates.  
   * **Attack Vector**: Conditional on the threat actor's success in using specific attack methods.  
   * **Vulnerability**: Defined based on the probability of specific attack vectors exploiting vulnerabilities.  
   * **Asset**: Modeled based on the likelihood of vulnerabilities affecting different assets.  
4. **Model Inference**:  
   * Used Variable Elimination to calculate posterior probabilities for asset risk based on various threat, attack, and vulnerability combinations.  
5. **Risk Ranking**:  
   * Computed risk scores for each asset and ranked them based on the aggregated risk from multiple attack scenarios.

### **Results**

| Rank | Asset | Risk Score | Rank | Asset | Risk Score |
| ----- | ----- | ----- | ----- | ----- | ----- |
| 1 | IoTDevice-02 | 8.0 | 14 | IoTDevice-04 | 3.6923 |
| 1 | Server-03 | 8.0 | 15 | Database-03 | 3.6835 |
| 1 | WebApp-01 | 8.0 | 16 | IoTDevice-01 | 3.3645 |
| 1 | WebApp-03 | 8.0 | 17 | Workstation-02 | 2.8466 |
| 5 | WebApp-04 | 4.6355 | 18 | Server-05 | 2.8211 |
| 6 | Server-06 | 4.3165 | 19 | Database-02 | 2.7299 |
| 7 | Database-01 | 4.3077 | 20 | Workstation-01 | 2.6994 |
| 8 | Server-01 | 4.2857 | 21 | Database-05 | 2.6919 |
| 9 | Server-02 | 4.2667 | 22 | IoTDevice-03 | 2.6526 |
| 10 | Server-04 | 4.1379 | 23 | Workstation-03 | 2.5782 |
| 11 | Workstation-04 | 3.8621 | 24 | WebApp-02 | 2.5263 |
| 12 | Database-04 | 3.7333 | 25 | IoTDevice-05 | 2.4540 |
| 13 | WebApp-05 | 3.7143 |  |  |  |

### **Mitigation Strategies**

To mitigate risks for the top five assets (IoTDevice-02, Server-03, WebApp-01, WebApp-03, and WebApp-04), implement the following strategies:

1. **IoTDevice-02:** Regular firmware updates, network segmentation, strict access control, and monitoring.  
2. **Server-03:** Establish a patch management process, enforce multi-factor authentication, deploy firewalls, and implement backup strategies.  
3. **WebApp-01:** Conduct code reviews, use web application firewalls, train developers in secure coding, and manage sessions securely.  
4. **WebApp-03:** Schedule vulnerability scans, ensure data encryption, enforce access control policies, and conduct security audits.  
5. **WebApp-04:** Regularly apply security updates, implement a content security policy, validate user inputs, and establish logging and monitoring.  
   (Mitigation Strategies source:Chatgpt)

### **Code**

Github Link: [https://github.com/Swaroop-Srisailam/Bayesian-Risk-Assessment-using-Cybersecurity-Data](https://github.com/Swaroop-Srisailam/Bayesian-Risk-Assessment-using-Cybersecurity-Data)

**THE END**


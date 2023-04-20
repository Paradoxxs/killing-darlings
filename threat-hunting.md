# Threat hunting

### Threat hunting

The active process of looking for signs of compromises.\
Instead of waiting for the security system to alert the security team of potential.\
The security can instead on the role as threat actor.\
What tactics techniques and procedures would you use to compromise the organization and achieve the goal wether that is exfil, ransomware or other.\
With that in mind go look for activity of the TTP you identified in the previous step.\
Once identified activity of potential malicious activity you must first verify your findings, If they are of malicious intent the next step is to activate incident response.\
The final step is to create detection rules that will alert you the next time this activity is seen in the network.

_Remember_ to tune your detection rules to reduce to amount of false positive.

**From intel to threat hunting and incident response**

1. Threat model
   * Select a threat group and identify its tactics techniques and procedures (TTP) that was identified in the intel report.
2. Create a hypothesis
   * Create a testable statement related to how the threat TTP would impact your organization.
3. Hunting
   * Once the hypotheses have been created the next step is to identify the steps needed to take it prove or disprove the hypotheses.
4. Learn
   * Identify gaps and opportunities of improvement.
   * Create detection rule to improve the detection of the TTP in your environment.

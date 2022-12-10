This is a simple standalone configuration to demostrate how SEDCMD is used to mask sensitve information.
Masking is a term used to describe the ability to hide the actual data or a subset of data using modified content like characters or numbers.
It is used to protect private or sensitive data by deleting or encrypting it.Use cases for data masking include the following:
1)Privacy Rule standards and disclosure of individuals’ health information (known as protected health information or PHI) 
by entities subject to the Privacy Rules.Protection Of sensitive patient health information from being disclosed without the patient’s consent or knowledge.
Eg.The Health Insurance Portability and Accountability Act(HIPAA)
2) Payment Card Industry Data Security Standard (PCI DSS),a widely accepted set of policies and procedures intended to optimize the security of credit, debit 
and cash card transactions and protect cardholders against misuse of their personal information.

To achieve this, we will use a regex expression that captures the string we want to mask and a sedcmd parameter set in props.conf to replace the 
string with a different string while the raw data is being ingested into splunk.

Syntax:
    replace - s/regex/replacement/flags
      * regex is a perl regular expression (optionally containing capturing
        groups).
      * replacement is a string to replace the regex match.
      * flags can be either: g to replace all matches, or a number to
        replace a specified match

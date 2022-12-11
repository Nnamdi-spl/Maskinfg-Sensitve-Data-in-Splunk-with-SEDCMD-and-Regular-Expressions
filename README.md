<h1>Data Masking with SEDCMD and Regex</h1>


<h2>Description</h2>
This is a simple standalone configuration to demostrate how SEDCMD is used to mask sensitve information.
Masking is a term used to describe the ability to hide the actual data or a subset of data using modified content like characters or numbers.
It is used to protect private or sensitive data by deleting or encrypting it.
To achieve this, we will use a regex expression that captures the string we want to mask and a SEDCMD parameter set in props.conf to replace the 
string with a different string while the raw data is being ingested into splunk.The sample data used in this demo is publicly available.



<br />



<h2>Use Cases for Data Masking</h2>

- <b>Privacy Rule standards and disclosure of individuals’ health information (known as protected health information or PHI) 
by entities subject to the Privacy Rules.Protection Of sensitive patient health information from being disclosed without the patient’s consent or knowledge.
Eg.The Health Insurance Portability and Accountability Act (HIPAA).</b> 
- <b>Payment Card Industry Data Security Standard (PCI DSS),a widely accepted set of policies and procedures intended to optimize the security of credit, debit 
and cash card transactions and protect cardholders against misuse of their personal information.</b>


<h2>Demo walk-through:</h2>


<br />
Configure an input.conf file to monitor the sample data with appropriate settings:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/206882318-96a3b33f-6ccb-4f29-a874-7eb9259f06f9.png" height="80%" width="80%"/>
<br />
<br />
Configure indexes.conf file to create the sales index: <br/>
<img src="https://user-images.githubusercontent.com/112047285/206882440-90773064-c094-4e59-95ec-34f3b746d93e.png" height="80%" width="80%"/>
<br />
<br />
Verify the sales index was created on SplunkWeb:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/206882488-c6463ac8-0822-443e-87d2-31c4cb7ca42f.png" height="80%" width="80%"/>
<br />
<br />
Write a Regular Expression to extract the string:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/206882538-f7c21e5b-9b0b-41bd-b77f-380687e99f37.png" height="80%" width="80%"/>
                                                             
<br />
<br />
configure props.conf file to mask the string:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/206882596-75c3c125-3fb9-4337-a631-6bf60e39d135.png" height="80%" width="80%"/>
<br />
<br />
Run a search from the Search Head to verify data masking:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/206882725-a67da4a5-7432-4c22-9917-aee0a1848c74.png" height="80%" width="80%"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>


<h1>HTTP & DNS Security Log Analysis</h1>

<h2>Description</h2>

This phase documents the ingestion and analysis of HTTP and DNS security logs using Splunk Enterprise. The goal of this phase is to develop practical security investigation skills by examining web traffic, DNS queries, and network-related activity to identify suspicious behavior and potential security threats.

Building on the SPL analysis techniques introduced in Phase 2, this phase focuses on investigating network activity, identifying abnormal traffic patterns, and correlating HTTP and DNS events to better understand potential security incidents.

<br />In this phase, the following topics will be covered:
- <b>HTTP and DNS log ingestion</b>
- <b>HTTP methods and status codes</b>
- <b>Source and destination IP analysis</b>
- <b>URI and endpoint analysis</b>
- <b>User-agent analysis</b>
- <b>HTTP error patterns</b>
- <b>Suspicious web requests</b>
- <b>DNS queries and responses</b>
- <b>DNS record types</b>
- <b>Domain and subdomain analysis</b>
- <b>DNS query frequency analysis</b>
- <b>Suspicious DNS activity</b>
- <b>Potential command-and-control communication</b>
- <b>HTTP and DNS event correlation</b>
- <b>Security investigation using SPL</b>
- <b>Statistical analysis and visualizations</b>

This phase develops practical network security monitoring and investigation skills required to identify suspicious web and DNS activity and support security detection development in later phases.
<br />

<h2>Languages and Utilities Used</h2>

- <b>Splunk Enterprise 10.6.1.1</b>
- <b>Splunk Processing Language (SPL)</b>
- <b>Simulated HTTP Security Log Dataset</b>
- <b>Simulated DNS Security Log Dataset</b>
- <b>Web Browser</b>

<h2>Environments Used</h2>

- <b>Host Operating System: Windows 11</b>
- <b>Virtualization Platform: Oracle VirtualBox</b>
- <b>Splunk SIEM Server: Ubuntu Server 24.04.5 LTS</b>
- <b>Splunk Server IP Address: 192.168.56.20</b>
- <b>HTTP and DNS Security Log Indexes and Sourcetypes</b>

<h2>Program walk-through:</h2>

<p align="center">
<b>Step 1 – Ingest HTTP and DNS Security Logs</b><br/><br/>
Import simulated HTTP and DNS security log datasets into Splunk Enterprise using the Add Data interface. Configure appropriate indexes, sourcetypes, timestamp extraction, and event boundaries for each dataset. Verify that both datasets are successfully indexed and searchable using SPL queries:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step1.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step1.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 2 – Examine Raw HTTP and DNS Events</b><br/><br/>
Examine the raw HTTP and DNS security events to understand the information recorded by web servers and DNS monitoring systems. Identify timestamps, source and destination IP addresses, HTTP requests, response codes, DNS queries, record types, and response information. Review how Splunk organizes the events and extracts searchable fields:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step2.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step2.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 3 – Analyze HTTP Methods and Status Codes</b><br/><br/>
Use SPL statistical commands to examine HTTP request methods such as GET, POST, PUT, and DELETE. Analyze HTTP response status codes, including successful requests, client errors, and server errors. Identify unusual request patterns and determine how HTTP methods and response codes can provide insight into web activity:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step3.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step3.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 4 – Analyze HTTP Source IP Addresses</b><br/><br/>
Investigate HTTP traffic by grouping requests according to source IP address. Use SPL to identify the most active clients, compare request volumes, and detect unusually high request counts. Examine source IP addresses associated with suspicious activity and determine which clients require additional investigation:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step4.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step4.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 5 – Investigate Suspicious URI Requests</b><br/><br/>
Analyze requested URIs and web application endpoints to identify potentially suspicious behavior. Search for repeated requests to administrative pages, authentication endpoints, sensitive files, and unusual URL paths. Use SPL filtering and statistical commands to identify patterns that may indicate web reconnaissance or unauthorized access attempts:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step5.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step5.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 6 – Analyze HTTP User-Agent Activity</b><br/><br/>
Examine HTTP user-agent strings to identify the applications and clients generating web requests. Compare common browser user agents against unusual or automated clients. Investigate suspicious user-agent patterns that may indicate scripted requests, vulnerability scanning, or automated web reconnaissance:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step6.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step6.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 7 – Investigate HTTP Errors and Suspicious Request Patterns</b><br/><br/>
Analyze HTTP error responses, including 401 Unauthorized, 403 Forbidden, and 404 Not Found. Identify repeated failed requests, unusual request frequencies, and concentrated activity targeting sensitive endpoints. Use SPL to investigate patterns consistent with web directory enumeration, authentication attempts, and automated scanning:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step7.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step7.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 8 – Visualize HTTP Traffic Over Time</b><br/><br/>
Use SPL timechart commands to visualize HTTP request volumes and error rates over time. Compare normal web traffic patterns against sudden spikes in requests or HTTP errors. Investigate unusual time periods to identify potential scanning activity, brute-force attempts, or abnormal web application behavior:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step8.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step8.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 9 – Examine DNS Queries and Record Types</b><br/><br/>
Investigate DNS security events by examining queried domains, source IP addresses, DNS record types, response codes, and resolved addresses. Analyze common DNS record types such as A, AAAA, MX, and TXT. Use SPL to summarize DNS activity and understand how DNS queries provide visibility into network communication:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step9.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step9.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 10 – Analyze DNS Query Frequency and Source IPs</b><br/><br/>
Use SPL statistical commands to identify frequently queried domains and the source IP addresses generating DNS requests. Compare DNS query volumes across hosts and domains to identify unusually frequent lookups. Investigate repetitive query behavior that may indicate automated processes, misconfigured applications, or suspicious network communication:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step10.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step10.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 11 – Investigate Suspicious Domains and Subdomains</b><br/><br/>
Analyze DNS queries for unusual domain names, excessive subdomain variation, long query strings, and uncommon domain patterns. Use SPL filtering and string analysis to identify suspicious queries that may indicate domain generation algorithms, DNS tunneling, or other potentially malicious DNS behavior. Distinguish suspicious indicators from legitimate DNS activity:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step11.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step11.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 12 – Analyze DNS Errors and Failed Resolutions</b><br/><br/>
Investigate unsuccessful DNS queries and response codes such as NXDOMAIN and SERVFAIL. Identify source IP addresses generating repeated failed resolutions and domains associated with unusual error rates. Use SPL statistical analysis to determine whether the observed behavior is consistent with misconfiguration, automated domain enumeration, or potentially suspicious DNS activity:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step12.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step12.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 13 – Investigate Potential Command-and-Control Communication</b><br/><br/>
Analyze HTTP and DNS activity for patterns potentially associated with command-and-control communication. Investigate repeated connections to unusual destinations, periodic DNS lookups, and consistent request intervals. Use SPL time-based analysis to identify possible beaconing behavior while considering legitimate applications that may generate similar traffic patterns:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step13.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step13.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 14 – Correlate HTTP and DNS Security Events</b><br/><br/>
Correlate HTTP requests and DNS queries using shared source IP addresses, destination domains, and event timestamps. Investigate relationships between suspicious DNS lookups and subsequent web requests. Use SPL to construct timelines of related activity and determine whether multiple network events indicate a coordinated or potentially malicious sequence:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step14.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step14.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 15 – Summarize Network Security Investigation Findings</b><br/><br/>
Use SPL statistical commands to summarize suspicious HTTP and DNS activity identified during the investigation. Organize findings by source IP address, destination domain, event type, request frequency, and observed behavior. Document relevant indicators, supporting evidence, and potential security implications to demonstrate how SIEM analysis supports security investigations:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step15.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step15.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

<p align="center">
<b>Step 16 – Validate HTTP and DNS Analysis and Complete Phase 3</b><br/><br/>
Perform a final validation of the HTTP and DNS security datasets using SPL searches. Confirm successful data ingestion, field extraction, timestamp accuracy, and event counts. Verify that HTTP requests, DNS queries, suspicious activity patterns, and investigation findings can be reproduced through SPL queries. Confirm that the Splunk environment is ready for security detection and alert development in subsequent phases:<br/>
<a href="https://raw.githubusercontent.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/main/Step16.png"><img src="https://github.com/royalexvo/Splunk-SIEM-Detection-SOAR-Automation-Phase-3/blob/main/Step16.png?raw=true" height="80%" width="80%" alt="Project Steps"/></a>
</p>

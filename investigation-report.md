SOC EMAIL INVESTIGATION REPORT

1. Overview

Investigation: Caterer Job Alert Email  
Date: 17 November 2026  
Analyst: Junior SOC Analyst  
Type of investigation: Email security and phishing analysis

The main objective of the investigation will be to determine if the email we are analyzing is potentially malicious. To do this we will review various email header fields, authentication results as well as the sending infrastructure of the email in question. Finally, we will check the reputation of the URLs included in the email.

2. Email Header Analysis

The following information was reviewed in the email headers:

| Field | From the email headers |
|---|---|
| From | info@jobs.caterer.com |
| Reply-To | Domain differs from the From address |
| Return-Path | Bounce address on bounce.jobs.caterer.com |
| Sending infrastructure | SparkPost |
| Receiving server (to which the email is sent) | Google MX |

Of these, the most concerning aspect which we should further investigate is the use of a differing domain in the Reply-To address.

3. Email Authentication

| Authentication check | Result |
|---|---|
| SPF | PASS |
| DKIM | PASS |
| DMARC | PASS |

Based on the results of the three authentication checks above (SPF, DKIM and DMARC), we can conclude in favor of the basic validity of the email content. However, we cannot assume the email content is free of malicious code.

4. URL Examination

Using the VirusTotal online utility:

- Domain in question: click.caterer.com
- Detection results: 0/93
- HTTP Response: 404
- Content type: text/html

Based on the results of the scan, none of the security vendors flagged the web page. We received an HTTP 404 (Page Not Found) response from the targeted site, which means the resource the request was directed to does not exist at the time of the request.

5. IP Address Examination

Using the VirusTotal online utility:

- IP address: 23.205.249.167
- Detection results: 0/92
- ISP/ASN: Akamai International B.V. / AS20940

Although the IP address in question is associated with the Akamai infrastructure, we cannot assume this would still be the case for the web pages accessed through this IP address. Therefore we cannot determine the trust level of this email with 100% certainty.

6. Findings and Risk Assessment

Positive findings:

- SPF authentication passed
- DKIM authentication passed
- DMARC authentication passed
- No security vendors have reported any malicious content on the URL/IP we have investigated

Items further in need of investigation:

- The Reply-To domain is different from the From domain

In addition, the truthfulness of the claims of the organization/jobs being advertised has also not been verified.

7. Final Assessment

Given the findings above we have classified the email as "Likely" to be legitimate.

8. Tools Used

- Gmail - To capture email headers
- VirusTotal - To check the reputation of URLs/an IP
- GitHub - To create the documentation related to this investigation

9. Disclaimer

This report was created for educational purposes and as part of an individual's cybersecurity portfolio. Therefore, the conclusions drawn from this investigation should be taken with caution and should not be used to determine the "safety" or "trustworthiness" of the email being investigated.

# SOC Phishing Email Investigation

## Project Overview

The following is an independent email security investigation that I conducted as part of my learning and training in cybersecurity, as well as for inclusion in my SOC Analyst portfolio.

In this investigation, I review a job-alert email from Caterer to determine whether it contains any suspicious or potentially malicious content.

## Investigation Objectives

- To check the email headers and sender information.
- To investigate the results of the SPF, DKIM and DMARC checks in the email.
- To investigate the sending infrastructure of the email.
- To perform URL and IP reputation analysis using VirusTotal.
- To provide an initial assessment of the email based on the above findings.

## Tools Used

| Tool | Usage |
|---|---|
| Gmail | To retrieve and inspect email headers. |
| VirusTotal | To evaluate URL and IP reputation. |
| GitHub | To document the investigation and manage supporting evidence. |

## Main Findings

| Check | Result |
|---|---|
| SPF | PASS |
| DKIM | PASS |
| DMARC | PASS |
| URL Reputation Check (VirusTotal) | 0/93 detections |
| IP Reputation Check (VirusTotal) | 0/92 detections |
| Sending Infrastructure | SparkPost |
| IP Organisation | Akamai International B.V. |

## Initial Conclusion

From the technical data available, we have been unable to identify malicious activity through the email authentication checks or reputation scans.

However, the domain names in the Reply-To and From fields of the email are different. This requires further investigation to establish whether the Reply-To address belongs to the legitimate organisation.

Until this discrepancy has been verified, we should not consider the email fully trusted.

## Investigation Report

Please refer to the full report for this investigation [here](investigation-report.md).

## Supporting Evidence

Screenshots and other evidence collected during the investigation are available in the [evidence folder](evidence/).

- [Email sender details](evidence/01-email-details-redacted.png)
- [Email authentication results](evidence/02-authentication-results-redacted.png)
- [VirusTotal URL analysis](evidence/03-virustotal-url.png)
- [VirusTotal IP analysis](evidence/04-virustotal-ip.png)

## Disclaimer

This investigation was completed solely for educational purposes and is not associated with or endorsed by Caterer.

We have made our best attempt to use the information available at the time of this investigation to assess the authenticity of the email. However, without further verification, we cannot determine with certainty whether the email is safe or malicious.

---
---

### What problem does Malware Discoverer address?

URL redirection is a salient feature for phishing and malware sites. Abusers use redirection to control the information flow and to evade detection. Collecting the redirection trace and discovering final URLs that host malicious artifacts is thus not an easy task. One challenge is how to discover entry points, or domains that initiate redirections. Another challenge is how to counteract cloaking techniques including IP-ban, javascript execution and fast flux. Malware Discoverer is designed to handle those challenges.


![](image/nycpost_pro_redirection.png)
*Example of one discovered malware campaigns. The entry-level domains (leftmost) use fake news as bait to lure users to click.*

### How does Malware Discoverer work?

Malware Discoverer is powered by an unsupervised discovery system that is able to trace coordinated redirection campaigns. The algorithm includes three components:
1. A crawler to collect redirection paths
2. A cluster to identify suspicious domains that share common redirection paths
3. A search expander to discover more domains co-hosted with suspicious domains

Malware Discoverer is a fully automated system. Currently it is tracking five IP addresses everyday. After the data collection, a python script loads the data, calculates summary statistics, and generates a png of the redirection network (see image above as an example). A daily threat intelligence report is published on this website and sent to subscribers via email.


### What do we analyze in the threat intelligence report?

Our reports focus on the coordinated redirection behavior of those malware campaigns. We breakdown domains and IPs into three categories: tier one are entry-level domains/IPs, tier two are intermediate redirection hops, and ther three are final landing domains/IPs. For each tier, the report covers:
* Top 10 domains (registrar, name server, and organization from WHOIS record)
* Top 10 IPs (hostname, city, country, andorganization from [ipinfo](http://ipinfo.io/){:target="_blank"})
* Visualization of redirection network, providing full context about the information flow
* Google Safe Browsing result, Virustotal result


### Current data collections and job status


| Date               | IP           | Andrioid |Chrome | Iphone |
|:-------------------|:-------------|:---------|:-----|:-------|



### How can those threat intelligence benefit me?

Our detection is not designed to be comprehensive. Because first, we are not tracking all IP addresses and domains, and second, even if we do, there are malicious domains that never redirect. Nevertheless, we still believe that Malware Discoverer is a valuable threat intelligence tool -- we find that only less than __1%__ of domains we discovered are labelled by Google Safe Browsing to be malicious. We hope that by sharing our method and data, we can receive more constructive feedback from the community, and together make malware detection more efficient.

We encourage you to take a look at our reports and graphs. If you find them helpful, connect us and we will share you the daily threat intelligence report.

* * *

### Have other ideas? / Want to subscribe to get threat intelligence report? / Contact
Zhouhan Chen, NYU Center for Data Science, <zc1245@nyu.edu>



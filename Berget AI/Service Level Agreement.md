Service Level Agreement
=======================

**Last updated:** 2026-10-23

1\. Scope
---------

This service level agreement (“SLA”) is an integral part of the Agreement between Berget and the Customer. It sets out the service levels for each of Berget’s Services:

| Service | Service level |
| --- | --- |
| Serverless Inference, including Berget Code | Best effort |
| Dedicated Inference, single instance | Best effort, SLO 99.5% monthly uptime |
| Dedicated Inference, HA setup | 99.5% monthly uptime |
| Dedicated Inference, HA setup across multiple sites | Above 99.5%, agreed in the Sales Order |
| Kubernetes Cluster | Best effort, unless agreed in the Order |

“HA” (high availability) means a redundant setup that keeps the Service available even if a single instance fails, as described in Section 4.1.

This SLA does not apply to Free Trials, the Trial plan, Preview models or features, or the Berget website and Berget Console.

Where the Customer’s Sales Order specifies service levels that differ from this SLA, the Sales Order prevails.

2\. Definitions
---------------

Capitalised terms not defined in this SLA have the meaning given in the Terms of Service.

**Deployment** means a single Dedicated Inference deployment of a model, as specified in the Order, including all of its instances and any fallback under Section 4.1(b).

**Monthly Fees** means the fees invoiced by Berget for the affected Deployment for the affected calendar month.

**Unavailable.** A Deployment is Unavailable when all requests to the Customer’s endpoint(s) fail with server errors (HTTP 5xx) or receive no response, due to a failure in Berget’s infrastructure. With an HA setup, the Deployment is Unavailable only when all instances, including any fallback, are unavailable at the same time. Periods shorter than five (5) consecutive minutes are not counted.

**Monthly Uptime Percentage** is calculated per Deployment as:

(total minutes in the calendar month − minutes Unavailable) / total minutes in the calendar month × 100%

**Response times.** Latency, time to first token and throughput are not covered by this SLA. A slow response is not Unavailability.

3\. Best Effort
---------------

For Services provided on a best-effort basis, Berget uses commercially reasonable efforts to keep the Service available and to restore it promptly after an interruption, but makes no commitment regarding uptime or performance, and no compensation is payable for interruptions. Sections 5 (Scheduled Maintenance) and 6 (Incidents and Status) apply to all Services.

4\. Dedicated Inference
-----------------------

Dedicated Inference runs the Customer’s model on GPUs reserved for the Customer alone. The uptime commitment depends on whether the Customer has a high-availability (“HA”) setup.

### 4.1 HA setup means either:

**(a) Redundant deployment.** At least two dedicated instances of the same model, each running on separate GPUs, as specified in the Order. Uptime above 99.5% requires instances in separate sites and is agreed in the Order.

**(b) Public endpoint fallback.** One dedicated instance with failover to Berget’s Serverless Inference for the same model. This option qualifies only while that model has Active status under Berget’s Model Lifecycle policy. Models in Preview never qualify. If the model is Deprecated, the uptime commitment applies until its end-of-life date and then lapses, unless the Customer moves to option (a).

### 4.2 Uptime commitment

For a Deployment with an HA setup, Berget will use commercially reasonable efforts to maintain a Monthly Uptime Percentage of at least 99.5%. The commitment applies only for as long as the Customer maintains the HA setup specified in the Order.

### 4.3 Single instance

A Deployment without an HA setup is provided on a best-effort basis under Section 3.

5\. Scheduled Maintenance
-------------------------

Berget will notify the Customer of scheduled maintenance at least seven (7) days in advance, by e-mail or by a notice on Berget’s website. Important security updates and patches may be deployed without prior notice.

For Deployments with an HA setup, Berget performs maintenance one instance at a time where possible, so that the Deployment remains available. Scheduled maintenance notified in accordance with this Section, and important security updates and patches, are excluded from the Monthly Uptime Percentage.

6\. Incidents and Status
------------------------

Berget publishes information about incidents and their resolution at [https://status.berget.ai](https://status.berget.ai/). If the Customer detects an interruption, the Customer should notify Berget at [outages@berget.ai](mailto:outages@berget.ai).

7\. Compensation
----------------

If the Monthly Uptime Percentage of a Deployment with an HA setup falls below 99.5%, the Customer is entitled to a reduction of the Monthly Fees as follows:

| Monthly Uptime Percentage | Reduction of Monthly Fees |
| --- | --- |
| Below 99.5%, but at least 99.0% | 10% of fees for impacted service |
| Below 99.0% | 25% of fees for impacted service |

Compensation is calculated per affected Deployment only. It is applied as a reduction of the Customer’s next invoice on the specific impacted service deployment and cannot be exchanged for cash.

To receive compensation, the Customer must submit a claim with a description of the interruption to [support@berget.ai](mailto:support@berget.ai) within thirty (30) days after the end of the month in which it occurred.

8\. Sole Remedy
---------------

The compensation in Section 7 is the Customer’s sole remedy for any interruption of the Services. If the Parties disagree about the amount of compensation, Berget’s decision is binding until a competent court rules otherwise.

9\. Exclusions
--------------

The following are excluded from the Monthly Uptime Percentage and are not subject to compensation:

1.  Scheduled maintenance and important security updates and patches, as set out in Section 5.
2.  Force Majeure events.
3.  Failures caused by Third-Party Products used by the Customer within the Service.
4.  Failures in products or services that are not provided by Berget.
5.  Failures caused by the Customer acting contrary to Berget’s instructions, or by the Customer’s own software or configuration.
6.  Interruptions related to the Customer’s breach of the Agreement or the Acceptable Use Policy.
7.  Failures caused by hostile actions of third parties, such as denial-of-service attacks.
8.  Actions Berget is obliged to take under applicable law or an order from a Governmental Authority.
9.  Suspension of the Service due to unpaid invoices or insufficient Credits under the Agreement.
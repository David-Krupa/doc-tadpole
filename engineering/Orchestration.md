<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

Orchestration and automation are related. Orchestration is more metrics- or need-based. Orchestration is defining the thresholds for an event to happen; then automation does the thing for you.

What are your questions when assessing?
  *   **Profiling**. What’s normal, what’s abnormal, what changes in events have to happen to return to normal.
  *   **Capturing metrics**. Observe your metrics in a “normal” or “optimal” state. Then, look for anomalies in those metrics, and then adjust for those.
  *   **Capturing logs**. Where you can, capture logs, rather than metrics, because logs are super important for incident response, while metrics are important for responding to performance-based issues. But for incident response, logs matter more.
  *   **Example**: You have a web app. Under normal terms, one instance can serve 50 concurrent users. You watch your user count, see a spike, spin up more instances.
  *   **Pattern recognition**. There’s some intuition involved, and you get to know a service and how it responds to stimuli, and then account for that. This is pattern recognition, which is what you’re training your orchestration to do.

## Improving, vs increasing, capacity

  *   Making sure that your customer/end user has things always responsive.
  *   Making sure things fail gracefully.
  *   Having HA and/or failover capability.
  *   Making sure things restart if they do fail.
  *   Make your systems as self-healing as possible.
  *   Knowing when something has failed and applying a fix to that failure.

“Shoot it in the head and spin up a new one” It's not that different from what you do in more legacy orchestration, like a VM or service… kill it and begin again. There's a reason why when all else fails, reboot.

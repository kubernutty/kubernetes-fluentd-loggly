# kubernetes-fluentd-loggly

# Supported tags and respective `Dockerfile` links

- [`1.0` (*1.0/Dockerfile*)](https://github.com/sekka1/kubernetes-fluentd-loggly/blob/1.0/1.0/Dockerfile)

# Description

Send Kubernetes logs to Loggly.com with fluentd

This is based on: https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/fluentd-elasticsearch/fluentd-es-image

The only change to the base Dockerfile build is changing the destination to Loggly.com

https://www.loggly.com/docs/fluentd-logs/

# Configuration

Set the following environment variables in the k8s-fluentd-daemonset:
  * LOGGLY_TOKEN
  * LOGGLY_TAG

Your token can be found at https://YOUR_USERNAME.loggly.com/tokens and the tag name is added to all logs consumed through this container.

# Audit logs

The following flags must be added to the kubelet on start in order to capture audit logs:
 * `--audit-webhook-mode=batch`
 * `--audit-policy-file=/var/log/kube-apiserver-audit.log`


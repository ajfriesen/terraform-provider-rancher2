## 0.1.0-rc1 (Unreleased)

FEATURES:

* **New Resource:** `rancher2_auth_config_activedirectory`
* **New Resource:** `rancher2_auth_config_adfs`
* **New Resource:** `rancher2_auth_config_azuread`
* **New Resource:** `rancher2_auth_config_freeipa`
* **New Resource:** `rancher2_auth_config_github`
* **New Resource:** `rancher2_auth_config_openldap`
* **New Resource:** `rancher2_auth_config_ping`
* **New Resource:** `rancher2_catalog`
* **New Resource:** `rancher2_cluster`
* **New Resource:** `rancher2_cluster_logging`
* **New Resource:** `rancher2_cluster_role_template_binding`
* **New Resource:** `rancher2_namespace`
* **New Resource:** `rancher2_node_driver`
* **New Resource:** `rancher2_node_pool`
* **New Resource:** `rancher2_node_template`
* **New Resource:** `rancher2_project`
* **New Resource:** `rancher2_project_logging`
* **New Resource:** `rancher2_project_role_template_binding`
* **New Resource:** `rancher2_setting`

ENHANCEMENTS:

* First release candidate of the rancher2 provider.
* resource/rancher2_cluster: support for providers:
  * Amazon EKS
  * Azure AKS
  * Google GKE
  * Imported
  * RKE
    * Cloud providers adding node pools
    * Custom
* resource/rancher2_cluster_logging: support for providers:
  * Elasticsearch
  * Fluentd
  * Kafka
  * Splunk
  * Syslog
* resource/rancher2_namespace: quota limits support on Rancher v2.1.x or higher
  * Amazon EC2
  * Azure
  * Digitalocean
* resource/rancher2_project: quota limits support on Rancher v2.1.x or higher
* resource/rancher2_project_logging: support for providers:
  * Elasticsearch
  * Fluentd
  * Kafka
  * Splunk
  * Syslog
* resource/rancher2_node_template: support for providers:

BUG FIXES:

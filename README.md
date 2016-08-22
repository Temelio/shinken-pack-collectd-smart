# shinken-pack-collectd-smart

## Description

This Shinken monitoring pack is used to manage smart services with our
standard deployment of Collectd.

We request Collectd data using unixsock plugin and collectd-nagios script from
collecd-utils package.

This pack depends to shinken-pack-collectd-base to work

## Objects

### Templates

#### Host templates

* collectd-smart: Manage all default thresholds and values for services

### Services

**Info: SMART capabilities are device specific, cannot use more than generic
service with _smart_rules per devices types**

| Service name  | Description             | Value specification     | DS    | Consolidation | Warning variable | Critical variable | Duplicate_foreach variable |
|---------------|-------------------------|-------------------------|-------|---------------|------------------|-------------------|----------------------------|
| SMART - $KEY$ | Check smart information | smart-$VALUE1$/$VALUE2$ | value | none          | $VALUE3$         | $VALUE4$          | _smart_rules               |

## Default values

    _smart_rules        sda - Bad sectors $(sda)$$(smart_badsectors)$$(0)$$(0)$

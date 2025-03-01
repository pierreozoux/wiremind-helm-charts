# ClamAV

##  An Open-Source antivirus engine for detecting trojans, viruses, malware & other malicious threats.

[ClamAV](https://www.clamav.net/) is the open source standard for mail gateway scanning software.
 Developed by [Cisco Talos](https://github.com/Cisco-Talos/clamav-devel). This Helm Chart uses the [MailU](https://github.com/Mailu/Mailu) Docker image. `appVersion` shows the Mailu/clamav container image version.

## QuickStart

```bash
$ helm repo add wiremind https://wiremind.github.io/wiremind-helm-charts
$ helm install my-release wiremind/clamav
```

## Introduction

This chart bootstraps a ClamAV deployment and service on a Kubernetes cluster using the Helm Package manager.

## Prerequisites

- Kubernetes 1.19+

## Installing the Chart

To install the chart with the release name `my-release`:

```bash
$ helm repo add wiremind https://wiremind.github.io/wiremind-helm-charts
$ helm install my-release wiremind/clamav
```

The command deploys ClamAV on the Kubernetes cluster in the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```bash
$ helm uninstall my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

The configurable parameters of the ClamAV chart and
their descriptions can be seen in `values.yaml`. The [full documentation](https://www.clamav.net/documents/clam-antivirus-0-101-0-user-manual) contains more information about running ClamAV in docker.

The config files themselves can either be specified as a plain text value or composed from a dict. In case they are specified via dict, if you give one key a list as a value, the option will be repeated for each value in the list.

> **Tip**: You can use the default [values.yaml](values.yaml)

## Memory Usage

ClamAV uses around 1 GB RAM.

# Virus Definitions

For ClamAV to work properly, both the ClamAV engine and the ClamAV Virus Database (CVD) must be kept up to date.

The virus database is usually updated many times per week.

Freshclam should perform these updates automatically. Instructions for setting up Freshclam can be found in the [documentation](https://www.clamav.net/documents/clam-antivirus-0-101-0-user-manual) section.
If your network is segmented or the end hosts are unable to reach the Internet, you should investigate setting up a private local mirror. If this is not viable, you may use these direct [download](https://www.clamav.net/downloads)

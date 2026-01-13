# helm-external-secrets

A Crossplane Configuration package that installs the external-secrets Helm chart with a minimal, stable interface.

## Overview

`helm-external-secrets` renders a single Helm release for external-secrets. It exposes only the inputs needed
for chart values, namespace, and release name, keeping the interface stable while allowing full Helm overrides.

## Features

- **Minimal Helm interface**: values and overrideAllValues with stable defaults
- **Predictable naming**: defaults to `<clusterName>-external-secrets` in the `external-secrets` namespace
- **GitOps friendly**: ships a `.gitops/` deploy chart

## Prerequisites

- Crossplane installed in the cluster
- Crossplane providers:
  - `provider-helm` (>=v1.0.2)
- Crossplane function:
  - `function-auto-ready` (>=v0.6.0)

## Quick Start

```yaml
apiVersion: pkg.crossplane.io/v1
kind: Configuration
metadata:
  name: helm-external-secrets
spec:
  package: ghcr.io/hops-ops/helm-external-secrets:latest
```

```yaml
apiVersion: helm.hops.ops.com.ai/v1alpha1
kind: ExternalSecrets
metadata:
  name: external-secrets
  namespace: example-env
spec:
  clusterName: example-cluster
  values:
    serviceAccount:
      create: true
```

## Development

```bash
make render
make validate
make test
```

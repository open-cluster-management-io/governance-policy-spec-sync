[comment]: # ( Copyright Contributors to the Open Cluster Management project )

# Governance Policy Spec Sync [![KinD tests](https://github.com/open-cluster-management-io/governance-policy-spec-sync/actions/workflows/kind.yml/badge.svg?branch=main&event=push)](https://github.com/open-cluster-management-io/governance-policy-spec-sync/actions/workflows/kind.yml)

## Description

The governance policy spec sync is a controller that runs on managed clusters, updating local `Policy` specs to match `Policies` in the cluster's namespace on the hub cluster. This controller is a part of the [governance-policy-framework](https://github.com/open-cluster-management-io/governance-policy-framework).

The operator watches for changes to Policies in the cluster's namespace on the hub cluster to trigger a reconcile. Every reconcile creates/updates/deletes replicated policies on the managed cluster to match the spec from the hub cluster.

Go to the [Contributing guide](CONTRIBUTING.md) to learn how to get involved.

## Geting started 

Check the [Security guide](SECURITY.md) if you need to report a security issue.

### Build and deploy locally
You will need [kind](https://kind.sigs.k8s.io/docs/user/quick-start/) installed.

```bash
make kind-bootstrap-cluster-dev
make build-images
make kind-deploy-controller-dev
```
### Running tests
```
make test-dependencies
make test

make e2e-dependencies
make e2e-test
```

### Clean up
```
make kind-delete-cluster
```

## References

- The `governance-policy-spec-sync` is part of the `open-cluster-management` community. For more information, visit: [open-cluster-management.io](https://open-cluster-management.io).

<!---
Date: June/11/2021
-->

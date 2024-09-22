# Enigma

Welcome to my home ops Kubernetes cluster, this repository is based on [onedr0p/cluster-template](https://github.com/onedr0p/cluster-template)

# computers

## Short desc

*All nodes are controllers*

| Node    | Type      | CPU | RAM |
|---------|-----------|-----|-----|
| Akame   | VM        | 10  | 32  |
| Bipboop | baremetal | 4   | 16  |
| Escanor | baremetal | 4   | 16  |

## Escanor & Bipboop

schematic Id: f105b58d0db73b5b6f099685d2985e573bcb653ff29451c129dfffc3c29491f7

```yaml
customization:
    systemExtensions:
        officialExtensions:
            - siderolabs/i915-ucode
            - siderolabs/intel-ucode
            - siderolabs/realtek-firmware
            - siderolabs/util-linux-tools
```

## Akame

schematic Id: a7bcadbc1b6d03c0e687be3a5d9789ef7113362a6a1a038653dfd16283a92b6b

```yaml
customization:
    systemExtensions:
        officialExtensions:
            - siderolabs/qemu-guest-agent
            - siderolabs/util-linux-tools
```

# usefull commands

```bash
# force update flux
flux reconcile source git home-kubernetes
# get flux objects status
flux get all -A --status-selector ready=false
# token for the dashboard
kubectl -n kubernetes-dashboard create token admin-user
# to connect to primary database
kubectl -n database port-forward "$(kubectl -n database get pods -l postgres-operator.crunchydata.com/role=master -o name)" 5432:5432
# ceph
kubectl -n rook-ceph get secret rook-ceph-dashboard-password -o jsonpath="{['data']['password']}" | base64 --decode && echo
```

# todolist

- monitoring stack
  - notification should be ok (not tested, need critical warning for that)
  - ceph/rook ok
  - database not working
  - todo : grafana
- uptime kuma
- movtrack
- keystore

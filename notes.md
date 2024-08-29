# machines

## Escanor

schematic Id: 314f21980c3d0bce7eb6f8e04ae45c91b703e3fe764ae3d6017ed0da04c13741

```yaml
customization:
    extraKernelArgs:
        - 'ip=192.168.0.33::192.168.0.1:255.255.255.0:escanor.lan:enp1s0f1:off:192.168.0.2:192.168.0.3:'
    systemExtensions:
        officialExtensions:
            - siderolabs/bnx2-bnx2x
            - siderolabs/i915-ucode
            - siderolabs/intel-ucode
            - siderolabs/util-linux-tools
```

## Akame & Bipboop

schematic Id: a7bcadbc1b6d03c0e687be3a5d9789ef7113362a6a1a038653dfd16283a92b6b

```yaml
customization:
    systemExtensions:
        officialExtensions:
            - siderolabs/qemu-guest-agent
            - siderolabs/util-linux-tools
```

# commandes utiles

```bash
# force update flux
flux reconcile source git home-kubernetes
# get flux objects status
flux get all -A --status-selector ready=false
# token for the dashboard
kubectl -n kubernetes-dashboard create token admin-user
```

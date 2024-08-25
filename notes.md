# machines

## Bipboop

schematic Id: c535365e0564d824d8ad4a71b812fd398c2ebaad16760e3148e39a13a4345396

```yaml
customization:
    extraKernelArgs:
        - 'ip=192.168.0.34::192.168.0.1:255.255.255.0:bipboop.lan:eth0:off:192.168.0.2:192.168.0.3:'
    systemExtensions:
        officialExtensions:
            - siderolabs/i915-ucode
            - siderolabs/intel-ucode
            - siderolabs/util-linux-tools
```

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

## Akame

schematic Id: 7eac8674861d3e8e2b4a3fdd65aa10f1718a08075b873980d841eeae1c3f7532

```yaml
customization:
    extraKernelArgs:
        - 'ip=192.168.0.35::192.168.0.1:255.255.255.0:talosakame.lan:eth0:off:192.168.0.2:192.168.0.3:'
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

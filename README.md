# Secure Device Connector (vSphere) Terraform module

The Secure Device Connector (SDC) is an intelligent proxy that allows your Cisco devices to communicate with CDO. When onboarding a device that is not directly reachable over the internet to CDO using device credentials, you can deploy an SDC in your network to proxy communications between the devices and CDO. Alternatively, if you prefer, you can enable a device to receive direct communications through its outside interface from CDO. Adaptive Security Appliances (ASAs), Meraki MXs, Firepower Device Manager (FDM)-managed devices, Firepower Management Centers (FMCs), Secure Firewall Cloud Native (SFCN) devices, Generic SSH and IOS devices, can all be onboarded to CDO using an SDC.

## Learn more
The [CDO documentation](https://docs.defenseorchestrator.com/#!c-secure-device-connector-sdc.html?highlight=SDC) has more details on SDC.

# Pre-requisities
- A vSphere datacenter (version 7+)
- An administrative account on the vSphere datacenter with permissions to:
    - create VMs, 
    - create folders, 
    - create content libraries (optional)
    - upload items to content libraries (optional)
- Terraform knowledge

# Usage
Please see [the usage documentation](USAGE.md) and the example below.

# Examples

See the [examples](examples) folder.

# Development
- Tags are automatically generated on push to master.
- `USAGE.md` is generated using [terraform-docs](https://github.com/terraform-docs/terraform-docs).

## Gitleaks

We use [Gitleaks](https://github.com/gitleaks/gitleaks) to catch secrets being committed to the repository by accident. The first line of defense is before you ever push to GitHub using a pre-commit hook.

Please enable the pre-commit hook before you commit anything to this repository, even in a branch.

- Install `pre-commit`
```
brew install pre-commit
```
- Update the pre-commit configuration:
```
pre-commit autoupdate
```
- Install the pre-commit configuration as a pre-commit hook to your local Git repo:
```
pre-commit install
```

Now any commits you make will be scanned by Gitleaks

### Gitleaks License

The Gitleaks License is free, and stored in the `GITLEAKS_LICENSE` secret. In addition, it is saved to [Conjur](https://secrets.cisco.com/conjur/nonprod/eng/cdo/gitleaks-license). Speak to Jay, Doron, Siddhu, or Pedro to access it.
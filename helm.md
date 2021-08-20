# Helm CLI Cheatsheet

>Disclaimer: This cheatsheet is summarized from personal experience and other online tutorials. It should not be considered as an official reference.

```bash
helm -n [namespace] get values [release]                # Get values that was passed during helm install
helm ls --all-namespaces                                # List all releases by helm for all namespaces
helm uninstall [release]                                # Uninstall a release
helm show values [chart]                                # Show all configurable values in the chart
helm install -f values.yaml [release] [chart]           # Pass configuration file values.yaml during install
helm upgrade -f values.yaml [release] [chart]           # Upgrade release and passing configuration file values.yaml
helm search repo [reponame]/[chartname] --versions      # View all chart versions
```
Basic Helm Concepts

Helm commands work with several Helm-related concepts. Understanding them makes the syntax easier to follow.

    The most important Helm concept is a chart. A chart is a set of Kubernetes yaml manifests packaged together for easy manipulation. Helm charts make it possible to deploy a containerized application using a single command.
    Charts are grouped in online collections called repositories. Each repository has a name and URL, making the charts easy to locate, download, and install.
    Helm Hub is an online collection of distributed repositories available on the internet. It works as an information center, where you can find apps and their repository addresses. As of today, it is not possible to install an app directly from Helm Hub.
    A release is a single instance of a chart deployed in a Kubernetes cluster.

# List of Helm Commands

Use the commands listed below as a quick reference when working with Helm inside Kubernetes.
Install and Uninstall Apps

The main function of Helm is Kubernetes app management. Besides the basic operations of installing and uninstalling apps, Helm enables you to perform test installations and customize the installation process.

Install an app:
```sh
helm install [app-name] [chart]
```

Install an app in a specific namespace:
```sh
helm install [app-name] [chart] --namespace [namespace]
```

Override the default values with those specified in a file of your choice:
```sh
helm install [app-name] [chart] --values [yaml-file/url]
```

Run a test installation to validate and verify the chart:
```sh
helm install [app-name] --dry-run --debug
```

Uninstall a release:
```sh
helm uninstall [release]
```

# Perform App Upgrade and Rollback

Helm offers users multiple options for app upgrades, such as automatic rollback and upgrading to a specific version. Rollbacks can also be executed on their own. For detailed instructions on how to perform a rollback, check out How to Roll Back Changes with Helm.

Upgrade an app:
```sh
helm upgrade [release] [chart]
```

Instruct Helm to rollback changes if the upgrade fails:
```sh
helm upgrade [release] [chart] --atomic
```

Upgrade a release. If it does not exist on the system, install it:
```sh
helm upgrade [release] [chart] --install
```

Upgrade to a specified version:
```sh
helm upgrade [release] [chart] --version [version-number]
```

Roll back a release:
```sh
helm rollback [release] [revision]
```

# Download Release Information

The helm get command lets you download information about a release.

Download all the release information:
```sh
helm get all [release]
```

Download all hooks:
```sh
helm get hooks [release]
```
Download the manifest:
```sh
helm get manifest [release]
```

Download the notes:
```sh
helm get notes [release]
```

Download the values file:
```sh
helm get values [release]
```

Fetch release history:
```sh
helm history [release] 
```

Add, Remove, and Update Repositories

The command helm repo helps you manipulate chart repositories.

Add a repository from the internet:
```sh
helm repo add [repository-name] [url]
```

Remove a repository from your system:
```sh
helm repo remove [repository-name]
```

Update repositories:
```sh
helm repo update
```

# List and Search Repositories

Use the helm repo and helm search commands to list and search Helm repositories. helm search also enables you to find apps and repositories in Helm Hub.

List chart repositories:
```sh
helm repo list
```

Generate an index file containing charts found in the current directory:
```sh
helm repo index
```

Search charts for a keyword:
```sh
helm search [keyword]
```

Search repositories for a keyword:
```sh
helm search repo [keyword]
```

Search Helm Hub:
```sh
helm search hub [keyword]
```

# Release Monitoring

The helm list command enables listing releases in a Kubernetes cluster according to several criteria, including using regular (Pearl compatible) expressions to filter results. Commands such as helm status and helm history provide more details about releases.

List all available releases in the current namespace:
```sh
helm list
```

List all available releases across all namespaces:
```sh
helm list --all-namespaces
```

List all releases in a specific namespace:
```sh
helm list --namespace [namespace]
```

List all releases in a specific output format:
```sh
helm list --output [format]
```

Apply a filter to the list of releases using regular expressions:
```sh
helm list --filter '[expression]'
```

See the status of a specific release:
```sh
helm status [release]
```

Display the release history:
```sh
helm history [release]
```

See information about the Helm client environment:
```sh
helm env
```

Install, manage and remove Helm plugins by using the helm plugin command.

Install plugins:
```sh
helm plugin install [path/url1] [path/url2] ...
```

View a list of all installed plugins:
```sh
helm plugin list
```

Update plugins:
```sh
helm plugin update [plugin1] [plugin2] ...
```

Uninstall a plugin:
```sh
helm plugin uninstall [plugin]
```

# Chart Management

Helm charts use Kubernetes resources to define an application. To find out more about their structure and requirements for their creation, refer to How to Create a Helm Chart.

Create a directory containing the common chart files and directories (chart.yaml, values.yaml, charts/ and templates/):

```sh
helm create [name]
```

Package a chart into a chart archive:
```sh
helm package [chart-path]
```

Run tests to examine a chart and identify possible issues:
```sh
helm lint [chart]
```

Inspect a chart and list its contents:
```sh
helm show all [chart] 
```

Display the chart’s definition:
```sh
helm show chart [chart] 
```

Display the chart’s values:
```sh
helm show values [chart]
```

Download a chart:
```sh
helm pull [chart]
```

Download a chart and extract the archive’s contents into a directory:
```sh
helm pull [chart] --untar --untardir [directory]
```

Display a list of a chart’s dependencies:
```sh
helm dependency list [chart]
```
Get Help and Version Information

Display the general help output for Helm:
```sh
helm --help
```

Show help for a particular helm command:

```sh
helm [command] --help
```

See the installed version of Helm:
```sh
helm version
```



[source](https://phoenixnap.com/kb/helm-commands-cheat-sheet)

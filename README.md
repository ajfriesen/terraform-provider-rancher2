Terraform Provider for Rancher v2
==================================

- Website: https://www.terraform.io
- [![Gitter chat](https://badges.gitter.im/hashicorp-terraform/Lobby.png)](https://gitter.im/hashicorp-terraform/Lobby)
- Mailing list: [Google Groups](http://groups.google.com/group/terraform-tool)

<img src="https://cdn.rawgit.com/hashicorp/terraform-website/master/content/source/assets/images/logo-hashicorp.svg" width="600px">

Requirements
------------

-	[Terraform](https://www.terraform.io/downloads.html) 0.11.x
- [Go](https://golang.org/doc/install) 1.9 to build the provider plugin
- [Trash](https://github.com/rancher/trash/releases) 0.2.6 (to manage vendor dependencies)

Building The Provider
---------------------

Clone repository to: `$GOPATH/src/github.com/terraform-providers/terraform-provider-rancher2`

```sh
$ mkdir -p $GOPATH/src/github.com/terraform-providers; cd $GOPATH/src/github.com/terraform-providers
$ git clone git@github.com:terraform-providers/terraform-provider-rancher2
```

Enter the provider directory and build the provider

```sh
$ cd $GOPATH/src/github.com/terraform-providers/terraform-provider-rancher2
$ make build
```

Using the provider
----------------------

If you're building the provider, follow the instructions to [install it as a plugin.](https://www.terraform.io/docs/plugins/basics.html#installing-a-plugin) After placing it into your plugins directory,  run `terraform init` to initialize it. Documentation about the provider specific configuration options can be found on the [provider's website](https://www.terraform.io/docs/providers/rancher2/index.html).

Developing the Provider
---------------------------

If you wish to work on the provider, you'll first need [Go](http://www.golang.org) installed on your machine (version 1.9+ is *required*). You'll also need to correctly setup a [GOPATH](http://golang.org/doc/code.html#GOPATH), as well as adding `$GOPATH/bin` to your `$PATH`.

To compile the provider, run `make build`. This will build the provider and put the provider binary in `$GOPATH/bin` .

```sh
$ make build
...
$ $GOPATH/bin/terraform-provider-rancher2
...
```

To just compile provider binary on repo path and test on terraform:

```sh
$ make bin
$ terraform init
$ terraform plan
$ terraform apply
```

Testing the Provider
---------------------------

In order to test the provider, you can simply run `make test`.

```sh
$ make test
```

In order to run the full suite of Acceptance tests, a running rancher system with a working k8s cluster imported and a rancher API key are needed.

To run acceptance tests, export `RANCHER_URL` with rancher url, `RANCHER_TOKEN_KEY` with bearer token or `RANCHER_ACCESS_KEY` with rancher acces key and `RANCHER_SECRET_KEY` with rancher secret key and execute

```sh
$ export RANCHER_URL=<URL>
$ export RANCHER_TOKEN_KEY=<TOKEN>
$ export RANCHER_INSECURE=true # Optional If ssl certificates are selfsigned
$ export RANCHER_ACC_CLUSTER_NAME=<NAME> # Optional k8s cluster name. `local` by default
$ make testacc
```

Managing vendor dependencies
-----------------------------

Go vendor dependencies are managed with [Trash](https://github.com/rancher/trash) and vendor.conf file.

To update vendor dependencies, edit `vendor.conf` file and run `trash`

```sh
$ trash
```



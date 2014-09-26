Description
===========

Heat Template to deploy Ambari on a Cloud Server

Requirements
============
* A Heat provider that supports the following:
  * OS::Nova::KeyPair
  * OS::Nova::Server
* An OpenStack username, password, and tenant id.
* [python-heatclient](https://github.com/openstack/python-heatclient)
`>= v0.2.8`:

```bash
pip install python-heatclient
```

We recommend installing the client within a [Python virtual
environment](http://www.virtualenv.org/).

Parameters
==========
Parameters can be replaced with your own values when standing up a stack. Use
the `-P` flag to specify a custom parameter.

* `flavor`: (Default: 1 GB Performance)
* `image`: (Default: Ubuntu 14.04 LTS (Trusty Tahr))
* `server_name`: (Default: linux-server)

Outputs
=======
Once a stack comes online, use `heat output-list` to see all available outputs.
Use `heat output-show <OUTPUT NAME>` to get the value of a specific output.

* `private_key`: SSH Private Key
* `server_ip`: Server IP

For multi-line values, the response will come in an escaped form. To get rid of
the escapes, use `echo -e '<STRING>' > file.txt`. For vim users, a substitution
can be done within a file using `%s/\\n/\r/g`.

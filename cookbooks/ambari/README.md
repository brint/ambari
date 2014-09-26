ambari Cookbook
===============

This cookbook installs Ambari-server and Ambari-agent in order to provision a cluster with the HDP distribution using the Blueprint API.

Requirements
------------
Supporting (or trying to support) the versions Ambari is supporting.

- RHEL, CentOS, and Oracle Linux 5
- RHEL, CentOS, and Oracle Linux 6
- Suse 11

Usage
-----
#### ambari::server

Just include `ambari::server` in your node's `run_list`:

```json
{
  "name":"my_node",
  "run_list": [
    "recipe[ambari::server]"
  ]
}
```

#### ambari::agent

Just include `ambari::agent` in your node's `run_list` (alll the nodes of your cluster):

The Ambari Server will be automatically detected, but you can override this detection using the attribute `node['ambari']['server']['fdqn']`.

```json
{
  "name":"my_node",
  "run_list": [
    "recipe[ambari::agent]"
  ]
}
```

#### ambari::server

Include `ambari::blueprints` in your node's `run_list`. Then configure the `blueprints` attributes listed below.

Main Attributes
----------

<table>
  <tr>
    <th>Key</th>
    <th>Description</th>
    <th>Default</th>
  </tr>
  <tr>
    <td><tt>node['ambari']['rhel_5_repo']</tt></td>
    <td>URL for the RHEL 5.x repository</td>
    <td><tt>http://public-repo-1.hortonworks.com/ambari/centos5/1.x/updates/1.6.0/ambari.repo</tt></td>
  </tr>
  <tr>
    <td><tt>node['ambari']['rhel_6_repo']</tt></td>
    <td>URL for the RHEL 6.x repository</td>
    <td><tt>http://public-repo-1.hortonworks.com/ambari/centos6/1.x/updates/1.6.0/ambari.repo</tt></td>
  </tr>
  <tr>
    <td><tt>node['ambari']['suse_11_repo']</tt></td>
    <td>URL for the Suse 11.x repository</td>
    <td><tt>http://public-repo-1.hortonworks.com/ambari/suse11/1.x/updates/1.6.0/ambari.repo</tt></td>
  </tr>
  <tr>
    <td><tt>node['ambari']['server_fdqn']</tt></td>
    <td>FQDN for the Ambari server</td>
    <td><tt>Found by searching a node using the recipe ambari::server in the same environment</tt></td>
  </tr>
</table>

Blueprints Attributes
----------

<table>
  <tr>
    <th>Key</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><tt>node['ambari']['blueprints']['blueprint_name']</tt></td>
    <td>Name of the cluster's blueprint</td>
  </tr>
  <tr>
    <td><tt>node['ambari']['blueprints']['blueprint_json']</tt></td>
    <td>JSON description of the Blueprint. See a single-node example here : https://cwiki.apache.org/confluence/display/AMBARI/Blueprints#Blueprints-ExampleBlueprint</td>
  </tr>
  <tr>
    <td><tt>node['ambari']['blueprints']['cluster_name']</tt></td>
    <td>Cluster's name</td>
  </tr>
  <tr>
    <td><tt>node['ambari']['blueprints']['cluster_json']</tt></td>
    <td>JSON template for the Cluster. See a single-node example here: https://cwiki.apache.org/confluence/display/AMBARI/Blueprints#Blueprints-ExampleClusterCreationTemplate</td>
  </tr>
</table>


Contributing
------------

If you wish to contribute on this cookbook:

1. Fork the repository on Github
2. Create a named feature branch (like `add_component_x`)
3. Write your change
4. Write tests for your change (if applicable)
5. Run the tests, ensuring they all pass
6. Submit a Pull Request using Github

License and Authors
-------------------
Author: [Julien Pellet](https://twitter.com/julienpellet)

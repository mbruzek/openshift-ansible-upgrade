# openshift-ansible-upgrade

Upgrade an openshift-ansible cluster.

## Usage

To run the upgrade follow these steps:  

* Clone the repository https://github.com/mbruzek/openshift-ansible-upgrade.git
* Change to the repository directory.
* Copy the inventory to the current directory (because it will be modified).
* Set the appropriate environment variables:
  * Cluster loader configuration directory:  `export cluster_loader_base_directory=/root/cm`
  * Cluster loader configuration file:  `export cluster_loader_configuration=cm_01` (notice no extension)
  * The registry authentication user
  * The registry authentication password
  * See [all.yml](group_vars/all.yml) for more environment variables.

```
git clone https://github.com/mbruzek/openshift-ansible-upgrade.git
cd openshift-ansible-upgrade
cp ../inv ./upgrade-inventory
export cluster_loader_base_directory=/root/cm
export cluster_loader_configuration=cm_01
export REG_AUTH_USER=
export REG_AUTH_PASSWORD=
ansible-playbook -vv -i upgrade-inventory upgrade.yml
```

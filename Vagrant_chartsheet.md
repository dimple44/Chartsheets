################################################# VAGRANT BASIC COMMANDS ###############################################

#### SSH into virtual machine.

            vagrant ssh [name|id]

#### Start virtual machine.

           vagrant up [name|id]

#### Share your virtual machine to the world via a temporary and unique url.

          vagrant share

#### halt virtual machine.

          vagrant halt [name|id]

#### Destroy your virtual machine. The source code and the content of the data directory will remain unchanged. Only the VirtualBox machine instance will be destroyed. You can build your machine again with the 'vagrant up' command. This command is useful if you want to save disk space.
Warning: this command will destroy your site databases. Backup them using drush sql-dump > db.sql for each site. 

          vagrant destroy [name|id]

#### Reconfigure the virtual machine after a source code change.

          vagrant provision [vm-name]

#### Reload the virtual machine. Useful when you need to change network or synced folder settings.

           vagrant reload [name|id]

###################################################################### VAGRANT BOX ########################################################

#### This is the command used to manage (add, remove, etc.) boxes. This adds a box with the given address to Vagrant.

           vagrant box add ADDRESS

#### This command lists all the boxes that are installed into Vagrant.

           vagrant box list

#### This command tells you whether or not the box you are using in your current Vagrant environment is outdated. If the --global flag is present, every installed box will be checked for updates.

           vagrant box outdated

#### This command removes old versions of installed boxes. If the box is currently in use vagrant will ask for confirmation.

           vagrant box prune

#### This command removes a box from Vagrant that matches the given name.

            vagrant box remove NAME

#### This command updates the box for the current Vagrant environment if there are updates available. The command can also update a specific box (outside of an active Vagrant environment), by specifying the --box flag.

             vagrant box update

################################################################## VAGRANT CLOUD ###########################################################

#### The login command is used to authenticate with HashiCorp's Vagrant Cloud server. Logging in is only necessary if you are accessing protected boxes.

Logging in is not a requirement to use Vagrant. The vast majority of Vagrant does not require a login. Only certain features such as protected boxes.

              vagrant cloud auth login

#### This will log you out if you are logged in. If you are already logged out, this command will do nothing. It is not an error to call this command if you are already logged out.

                vagrant cloud auth logout

#### This command will validate your Vagrant Cloud token and will print the user who it belongs to. If a token is passed in, it will attempt to validate it instead of the token stored stored on disk.

              vagrant cloud auth whoami [TOKEN]

#### The box create command is used to create a new box entry on Vagrant Cloud.

              vagrant cloud box create ORGANIZATION/BOX-NAME

#### The box delete command will permanently delete the given box entry on Vagrant Cloud. Before making the request, it will ask if you are sure you want to delete the box.

               vagrant cloud box delete ORGANIZATION/BOX-NAME

#### The box show command will display information about the latest version for the given Vagrant box.

               vagrant cloud box show ORGANIZATION/BOX-NAME

#### The box update command will update an already created box on Vagrant Cloud with the given options.
 
                 vagrant cloud box update ORGANIZATION/BOX-NAME

#### The provider create command is used to create a new provider entry on Vagrant Cloud. The url argument is expected to be a remote URL that Vagrant Cloud can use to download the provider. If no url is specified, the provider entry can be updated later with a url or the upload command can be used to upload a Vagrant box file.

              vagrant cloud provider create ORGANIZATION/BOX-NAME PROVIDER-NAME VERSION [URL]

#### The provider delete command is used to delete a provider entry on Vagrant Cloud. Before making the request, it will ask if you are sure you want to delete the provider.

              vagrant cloud provider delete ORGANIZATION/BOX-NAME PROVIDER-NAME VERSION

#### The provider update command will update an already created provider for a box on Vagrant Cloud with the given options.

             vagrant cloud provider update ORGANIZATION/BOX-NAME PROVIDER-NAME VERSION [URL]

#### The provider upload command will upload a Vagrant box file to Vagrant Cloud for the specified version and provider.

              vagrant cloud provider upload ORGANIZATION/BOX-NAME PROVIDER-NAME VERSION BOX-FILE

#### The publish command is a complete solution for creating and updating a Vagrant box on Vagrant Cloud. Instead of having to create each attribute of a Vagrant box with separate commands, the publish command instead asks you to provide all the information required before creating or updating a new box.

             vagrant cloud publish ORGANIZATION/BOX-NAME VERSION PROVIDER-NAME [PROVIDER-FILE]

################################################################# VAGRANT INIT #########################################################

#### Create a base Vagrantfile:

             vagrant init hashicorp/bionic64

#### Create a minimal Vagrantfile.

              vagrant init -m hashicorp/bionic64

#### Create a new Vagrantfile, overwriting the one at the current path:

               vagrant init -f hashicorp/bionic64

#################################################################### VAGRANT LOGIN ####################################################

#### Securely authenticate to Vagrant Cloud using a username and password: 

               vagrant login

#### Check if the current user is authenticated:

               vagrant login --check

#### Securely authenticate with Vagrant Cloud using a token:

               vagrant login --token ABCD1234

##################################################################### VAGRANT PLUGIN #################################################

#### This removes all user installed plugin information. All plugin gems, their dependencies, and the plugins.json file are removed. This command provides a simple mechanism to fully remove all user installed custom plugins.

                 vagrant plugin expunge

#### When upgrading Vagrant it may be required to reinstall plugins due to an internal incompatibility. The expunge command can help make that process easier by attempting to automatically reinstall currently configured plugins:

                   vagrant plugin expunge --reinstall

#### This installs a plugin with the given name or file path. If the name is not a path to a file, then the plugin is installed from remote repositories, usually RubyGems.

                  vagrant plugin install <name>

#### This command will also update a plugin if it is already installed, but you can also use vagrant plugin update for that.

                 vagrant plugin update

#### This lists all installed plugins and their respective installed versions. If a version constraint was specified for a plugin when installing it, the constraint will be listed as well. Other plugin-specific information may be shown, too.

                 vagrant plugin list

#### This uninstalls the plugin with the given name. Any dependencies of the plugin will also be uninstalled assuming no other plugin needs them.

If multiple plugins are given, multiple plugins will be uninstalled.

                vagrant plugin uninstall <name> [<name2> <name3> ...]

#### This resumes a Vagrant managed machine that was previously suspended, perhaps with the suspend command.
 
                vagrant resume [name|id]

The configured provisioners will not run again, by default. You can force the provisioners to re-run by specifying the --provision flag.

################################################################ VAGRANT SNAPSHOT ######################################################

#### This takes a snapshot and pushes it onto the snapshot stack.

               vagrant snapshot push

#### This command is the inverse of vagrant snapshot push: it will restore the pushed state.

               vagrant snapshot pop

#### This command saves a new named snapshot. If this command is used, the push and pop subcommands cannot be safely used.

               vagrant snapshot save [vm-name] NAME

#### This command restores the named snapshot.

                vagrant snapshot restore [vm-name] NAME

#### This command will list all the snapshots taken.

                vagrant snapshot list

#### This command will delete the named snapshot.

                vagrant snapshot delete [vm-name] NAME

#### This will tell you the state of the machines Vagrant is managing.

                vagrant status [name|id]

################################################################### END #############################################################                                



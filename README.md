This role now gets mailman installed and running.  Lists need to be created and
updated manually and should be backed up.  Run the `mailman` command as the
user `list` to create or modify lists.  Note that the self documentation
provided by this command is the best documentation available.

View high level self documentation:

    sudo -u list mailman -h

View self documentation for subcommands:

    sudo -u list mailman create -h
    sudo -u list mailman addmembers -h

Create a new list:

    sudo -u list mailman create testlist@bugher.net

Add a member to a list:

    sudo -u list mailman addmembers - testlist@bugher.net <<< aaron@bugher.net

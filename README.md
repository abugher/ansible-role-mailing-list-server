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

    list_short_name=testlist
    sudo -u list mailman create "${list_short_name}"@bugher.net
    sudo newaliases

Add a member to a list:

    # Usually it is better to send mail to "${list_short_name}"-subscribe@bugher.net.
    sudo -u list mailman addmembers - "${list_short_name}"@bugher.net <<< aaron@bugher.net

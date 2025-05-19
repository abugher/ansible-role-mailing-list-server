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

Create necessary aliases for the new list:

    list_short_name=testlist; sudo -u list awk -F '@' "/^${list_short_name}"'[@-]/ {print $1":mailman"}' /var/lib/mailman3/data/postfix_lmtp | sudo -u mail tee -a /etc/postfix/external-aliases/list-aliases
    sudo newaliases

Add a member to a list:

    # Usually it is better to send mail to testlist-subscribe@bugher.net.
    sudo -u list mailman addmembers - testlist@bugher.net <<< aaron@bugher.net

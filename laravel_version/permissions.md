# Directory Permissions

You'll need to make sure that the <code>app/storage</code> directory is writable by your webserver, since caches and log files get written there. You should use the minimum permissions available for writing, based on how you've got your webserver configured.

```
chmod -R 755 app/storage

```


If you still run into a permissions error, you may need to increase the permissions to 775, or twiddle your user/group permissions on your server.

```

chmod -R 775 app/storage

```

You'll also want to make sure that your laravel directory and all files within are owned by something other than root. It's very common to create a user on your server (like www), add that user to the apache group, and then chown your files to be owned by www, chgrp to the apache group.

This ensures your files can be executed correctly and cache files can be written to without having to give files owned by root the permissions to write or execute.

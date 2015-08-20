# Directory Permissions

Laravel 5.1 requires directories within the <code>storage</code> and the <code>bootstrap/cache</code> directories should be writable by your web server

You should use the minimum permissions available for writing, based on how you've got your web server configured.

```
chmod -R 755 storage

chmod 755 bootstrap/cache

```


If you still run into a permissions error, you may need to increase the permissions to 775, or twiddle your user/group permissions on your server.

```

chmod -R 775 storage

chmod 775 bootstrap/cache

```

You'll also want to make sure that your laravel directory and all files within are owned by something other than root. It's very common to create a user on your server (like www), add that user to the apache group, and then chown your files to be owned by www, chgrp to the apache group.

This ensures your files can be executed correctly and cache files can be written to without having to give files owned by root the permissions to write or execute.
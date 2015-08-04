From [here] [1]

Summary:

1. In `tomcat-folder/bin/startup.sh`, add the following at the top somewhere:
    ````
    set JPDA_ADDRESS=8000
    set JPDA_TRANSPORT=dt_socket
    ````

2. Still in the same file, change the execute line at the end to include jpda start
    ````
    exec "$PRGDIR"/"$EXECUTABLE" jpda start "$@"
    ````

3. Now you can run the `startup.sh` script to start tomcat in debug mode.

4. To add to IntelliJ, you want to add a new `Remote` configuration (NOT a new Tomcat server configuration). Point the configuration to the above-configured port.

[1]: https://confluence.sakaiproject.org/display/BOOT/Setting+Up+Tomcat+For+Remote+Debugging

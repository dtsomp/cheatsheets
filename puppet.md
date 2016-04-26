# puppet

Disable puppet agent with mesage

    puppet agent --disable "Disabled because of reasons" [--verbose]

Check if puppet agent is disabled.
This will fail if there is no lockfile (i.e. agent is enabled)

    puppet agent --configprint agent_disabled_lockfile

;

### Fork mode

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>pm2 start app.js --name my-api</code></td><td>Start and name a process</td></tr></tbody></table>

### Cluster mode

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>pm2 start app.js -i 0</code></td><td>Will start maximum processes with LB depending on available CPUs</td></tr></tbody></table>

### Listing

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>pm2 list</code></td><td>Display all processes status</td></tr><tr class="even"><td><code>pm2 jlist</code></td><td>Print process list in raw JSON</td></tr><tr class="odd"><td><code>pm2 prettylist</code></td><td>Print process list in beautified JSON</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>pm2 describe 0</code></td><td>Display all information about a specific process</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>pm2 monit</code></td><td>Monitor all processes</td></tr></tbody></table>

### Logs

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>pm2 logs [--raw]</code></td><td>Display all processes logs in streaming</td></tr><tr class="even"><td><code>pm2 flush</code></td><td>Empty all log files</td></tr><tr class="odd"><td><code>pm2 reloadLogs</code></td><td>Reload all logs</td></tr></tbody></table>

### Actions

<table><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>pm2 stop all</code></td><td>Stop all processes</td></tr><tr class="even"><td><code>pm2 restart all</code></td><td>Restart all processes</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>pm2 reload all</code></td><td>Will 0s downtime reload (for NETWORKED apps)</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>pm2 stop 0</code></td><td>Stop specific process id</td></tr><tr class="odd"><td><code>pm2 restart 0</code></td><td>Restart specific process id</td></tr><tr class="even"><td>—</td><td>—</td></tr><tr class="odd"><td><code>pm2 delete 0</code></td><td>Will remove process from pm2 list</td></tr><tr class="even"><td><code>pm2 delete all</code></td><td>Will remove all processes from pm2 list</td></tr></tbody></table>

### Misc

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Command</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>pm2 reset &lt;process&gt;</code></td><td>Reset meta data (restarted time…)</td></tr><tr class="even"><td><code>pm2 updatePM2</code></td><td>Update in memory pm2</td></tr><tr class="odd"><td><code>pm2 ping</code></td><td>Ensure pm2 daemon has been launched</td></tr><tr class="even"><td><code>pm2 sendSignal SIGUSR2 my-app</code></td><td>Send system signal to script</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>pm2 start app.js --no-daemon</code></td><td>Run pm2 daemon in the foreground if it doesn’t exist already</td></tr><tr class="odd"><td><code>pm2 start app.js --no-vizion</code></td><td>Skip vizion features (versioning control)</td></tr><tr class="even"><td><code>pm2 start app.js --no-autorestart</code></td><td>Do not automatically restart app</td></tr></tbody></table>

;

Format
------

{: .-two-column}

### Format

    Min  Hour Day  Mon  Weekday

{: .-setup}

    *    *    *    *    *  command to be executed

    ┬    ┬    ┬    ┬    ┬
    │    │    │    │    └─  Weekday  (0=Sun .. 6=Sat)
    │    │    │    └──────  Month    (1..12)
    │    │    └───────────  Day      (1..31)
    │    └────────────────  Hour     (0..23)
    └─────────────────────  Minute   (0..59)

{: .-setup.-box-chars}

### Examples

<table><thead><tr class="header"><th>Example</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>0 * * * *</code></td><td>every hour</td></tr><tr class="even"><td><code>*/15 * * * *</code></td><td>every 15 mins</td></tr><tr class="odd"><td><code>0 */2 * * *</code></td><td>every 2 hours</td></tr><tr class="even"><td><code>0 0 * * 0</code></td><td>every Sunday midnight</td></tr><tr class="odd"><td>—</td><td>—</td></tr><tr class="even"><td><code>@reboot</code></td><td>every reboot</td></tr></tbody></table>

### Crontab

    # Adding tasks easily
    echo "@reboot echo hi" | crontab

    # Open in editor
    crontab -e

    # List tasks
    crontab -l [-u user]

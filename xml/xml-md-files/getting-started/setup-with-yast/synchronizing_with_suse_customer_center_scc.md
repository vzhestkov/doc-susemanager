## Synchronizing with SUSE Customer Center (SCC) {#synchronizing-with-suse-customer-center-scc}

SUSE Customer Center (SCC) maintains a collection of repositories which contain packages, software and updates for all supported client systems. These repositories are organized into channels each of which provide software specific to a distribution, release and architecture. You must synchronize your SUSE Manager Server with SCC to add channels for your client systems. After synchronizing with SCC your clients are able to receive updates or be organized into groups to be assigned to a specific software channel. This section covers synchronizing with SCC from the Web UI and adding your first client channels.

Procedure 1.3. Synchronizing with SUSE Customer Center

1.  From the SUSE Manager Web UI start page select Admin+Setup Wizard.

2.  From the Setup Wizard page select the SUSE Products tab. Wait a moment for the Available Products Below list to populate. You are present with a list of repositories provided from SCC. Each of these repositories represents a single software source known as a `Base Channel` within SUSE Manager. You can also see the architecture, channels, and status information from this page.

    | ![](admin_suse_products.png) |
    | --- |

3.  As you are adding a SUSE Linux Enterprise 12 SP2 client based on the `x86_64` architecture, scroll down the page and select the check box for this channel now.

    *   Add single channels to SUSE Manager by selecting the check box to the left the + button of each channel.

    *   Add multiple channels by selecting the check boxes to the left of the channels list and then schedule synchronization by clicking the **+ Add products** button located at the bottom of the page.

After adding your first channel SUSE Manager will schedule the channel to be copied and begin mirroring it. This can take a long time as SUSE Manager must copy all software sources from the SUSE Vendor repositories located at SUSE Customer Center to your servers local _`/var/spacewalk/`_ directory.

### PostgreSQL and Transparant Huge Pages {#postgresql-and-transparant-huge-pages}

In some environments, Transparent Huge Pages provided by the kernel may slow down PostgreSQL workloads significantly.

To disable transparant huge pages set the `transparent_hugepage` kernel parameter to `never`. This has to be changed in `/etc/default/grub` and added to the line `GRUB_CMDLINE_LINUX_DEFAULT`, for example:

```
GRUB_CMDLINE_LINUX_DEFAULT="resume=/dev/sda1 splash=silent quiet showopts elevator=noop transparent_hugepage=never"
```

To write the new configuration run **grub2-mkconfig -o /boot/grub2/grub.cfg**. To update the grub2 during boot run **grub2-install /dev/sda**.

Monitor channel synchronization process in real-time by viewing channel log files located in the following directory:

```
example-server:/var/log/rhn/reposync/# tail -f <Channel_Name>.log
```

After your channel sync has completed proceed to

???

.
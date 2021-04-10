# raimue-ports

This is a ports tree for [MacPorts](https://macports.org). This ports tree
contains ports that may not yet be ready for inclusion into the official
[macports-ports](https://github.com/macports/macports-ports) tree, but that are
published here first to try them out.

Consider all of these ports to be experimental!

## Setup Instructions

You can install this ports tree as a local overlay for the official
macports-ports tree.

The details are described in the [MacPorts Guide](https://guide.macports.org/#development.local-repositories),
but here is a quick start:

### Clone the repository

    $ cd $HOME
    $ git clone https://github.com/raimue/raimue-ports.git

### Find the correct URL

    $ echo file://$HOME/raimue-ports
    file:///Users/username/raimue-ports

### Add this URL to sources.conf

Edit the sources.conf of your MacPorts installation:

    $ sudo vim /opt/local/etc/macports/sources.conf

Add the URL to the new ports tree **above** the official ports tree:

    file:///Users/username/raimue-ports
    rsync://rsync.macports.org/macports/release/tarballs/ports.tar [default]

### Generate PortIndex

Run a port sync action to generate the PortIndex for the new ports tree.
This will also pull updates with git.

    $ sudo port -v sync
    --->  Updating the ports tree
    Synchronizing local ports tree from file:///Users/username/raimue-ports
    ...

Now you can install any of the ports contained in this ports tree the usual way.

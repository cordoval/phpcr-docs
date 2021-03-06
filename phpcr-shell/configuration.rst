Configuration
=============

Initialization and reloading
----------------------------

The configuration files can be initialized and reloaded at any time using the
:ref:`phpcr_shell_command_shellconfiginit` and :ref:`phpcr_shell_command_shellconfigreload`
commands:

.. code-block:: bash

    PHPCRSH> shell:config:init
    PHPCRSH> shell:config:reload

At time of writing the only configuration file affected by these commands is
the ``aliases.yml`` file detailed below.

.. _phpcrsh_configuration_aliases:

Aliases
-------

PHPCRSH supports aliases. Aliases are shortcuts for commands.

Aliases are stored in the file ``$HOME/.phpcrsh/aliases.yml``, which is created
automatically when launching the PHPCR Shell.

You can list the current aliases with the :ref:`phpcr_shell_command_shellaliaslist` command.

For example:

.. code-block:: bash

    PHPCRSH> ls
    PHPCRSH> pwd
    PHPCRSH> refresh
    PHPCRSH> save

Are all examples of aliases.

Below is the distribution version of this file at time of writing:

.. code-block:: yaml

    # Shell shortcuts
    aliases: shell:alias:list
    creload: shell:config:reload
    cinit: shell:config:init

    # MySQL commands
    use: workspace:use {arg1}
    explain: node-type:show {arg1}

    # Filesystem commands
    cd: shell:path:change {arg1}
    rm: node:remove {arg1}
    mv: node:move {arg1} {arg2}
    pwd: shell:path:show
    exit: shell:exit

    # Node commands
    ls: node:list {arg1}
    ln: node:clone {arg1} {arg2} # symlink, as in ln -s
    cp: node:copy {arg1} {arg2}
    cat: node:property:show {arg1}
    touch: node:property:set {arg1} {arg2} {arg3}
    mkdir: node:create {arg1} {arg2}

    # Node type commands
    mixins: node-type:list "^mix:"
    nodetypes: node-type:list {arg1}
    ntedit: node-type:edit {arg1}
    ntshow: node-type:show {arg1}

    # Workspace commands
    workspaces: workspace:list

    # Namespsce commands
    namespaces: workspace:namespace:list {arg1}
    nsset: workspace:namespace:register

    # Editor commands
    vi: node:edit {arg1} {arg2}
    vim: node:edit {arg1} {arg2}
    nano: node:edit {arg1} {arg2}

    # GNU commands
    man: help {arg1}

    # Version commands
    checkin: version:checkin {arg1}
    ci: version:checkin {arg1}
    co: version:checkout {arg1}
    checkout: version:checkout {arg1}
    cp: version:checkpoint {arg1}
    checkpoint: version:checkpoint {arg1}
    vhist: version:history {arg1}
    versions: version:history {arg1}

    # Session commands
    save: session:save
    refresh: session:refresh

For a full reference enter in the shell:

.. code-block:: bash

    PHPCRSH> shell:alias:list

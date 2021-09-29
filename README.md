# An open-source data analysis framework used by high energy physics and others, in a snap!
[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/root-framework)

## General installation and use
This snap is intended to provide an easy-to-install package of the ROOT framework for the home user.
It comes bundled along with Python 3.8/PyROOT and Jupyter/JupyROOT notebook capability.
NumPy, SciPy, Pandas and Matplotlib are bundled with the Python environments.

Snaps are container packages for easy application deployment, designed to be consistent and reliable across different host distributions.
They additionally impose some strong sandboxing for security.
One caveat of this sandboxing is that this package can only read/write to your `$HOME` directory, or via specific network protocols.
It is highly advised that you place all your data files in your `$HOME` directory to be accessible. 
  
Because snaps are containers and don't affect the host system, using PyROOT with `import ROOT` will not work in a system Python shell.
Users are encouraged to use the command `pyroot` to access the containers' Python shell, where `import ROOT` would become available.
Scripts can be passed to `pyroot` to be executed in PyROOTs context, E.G, `pyroot ./myScript.py`, or put in the scripts shebang. E.G `#!/snap/bin/pyroot`
  
JupyROOT can be accessed by running `root --notebook`.

For user convenience, application entries for ROOT and PyROOT will be placed into the systems start menu by default. 

## Building
This repository can be built by simply invoking the `snapcraft` utility.
Snapcraft is the build system for snaps and can be installed itself as a snap [here](https://snapcraft.io/snapcraft).
A basic guide to using Snapcraft can be found [here](https://snapcraft.io/docs/snapcraft-overview).
If the user does not have a system compatible with Multipass, I.E, due to lack of virtual machine CPU support, consider using the LXD backend, instructions available [here](https://snapcraft.io/docs/build-on-lxd). 

By default, the latest master/HEAD is built.
If the user wishes to build a specific commit or tag instead, make use of the `source-tag` and `source-commit` values.
[Example here](https://github.com/MrCarroll/root-snap/commit/4292125a412adabcc01fc666679bfa2fc084ec20)  

Building your own ROOT snap can be helpful if you'd like to make modifications to the CMake parameters, add extra Python packages or just experiment with snaps in general.
If any modifications might make sense to the general userbase, please feel free to suggest them!

Please note that custom builds will use namespaced binaries by default.
E.G, `root` will not be immediately available and will be only accessible as `root-framework`.
Similarly, `hadd` will be available as `root-framework.hadd`.
Make use of the `snap alias` commands to map these, examples [here](https://snapcraft.io/docs/commands-and-aliases).
Automatic connection of interfaces to setup the sandboxing may differ between custom builds and builds downloaded from the store directly, be sure to read about interface management [here](https://snapcraft.io/docs/interface-management).
Automatic interfaces and aliases are managed via an assertation signed via private key to ensure authenticity of the snap, which is handled transparently when using the normal `snap install root-framework` commands, or via the `snap ack` command.

## Support
Users are encouraged to read the [compatibility guarantees](https://root.cern/about/versioning/) provided by ROOT.

Nightly builds are generated from the latest upstream master/HEAD at 20:00 UTC per day.
Build history can be viewed [here](https://github.com/mrcarroll/root-snap/actions).

This package is prioritised for users new to Linux or ROOT or both.
This means that support is focused on getting the core of ROOT to work well first, and "edge case" functionality that is unlikely to make sense to a home user might not be as well supported and less a priority to fix.
Regardless, please feel free to contact me with any feedback and issues and I'll take a look.

Presently, this package is a solo endevour done on a best effort basis.
If this package isn't working for you, consider using the upstream binary downloads, or the Conda and Docker packages! Official instructions can be found [here](https://root.cern/install/).

## Licensing
Please note that whilst this repository is under MIT licensing, the actual ROOT software is LGPL 2.1+ and its source may be found [here](https://github.com/root-project/root.git).
Furthermore, the actual license of the distributed snap is GPL3.0, due to linking with GSL.
Documentation of the included Ubuntu packages in the snap can be found in `/snap/root-framework/current/usr/share/doc` and accessed at [https://packages.ubuntu.com/](https://packages.ubuntu.com/).
Some packages will use the builtin packages from the CMake build tools. Refer to the ROOT source repo for more information.

# ROOT snap

This repository contains the build files for generating a snap package of the [ROOT Framework](https://root.cern).

It is intended to provide a functional package of ROOT for people who simply want access to a functional, minimal effort installation for home use cases.

It can be installed on any snapd compatible system with `sudo snap install root-framework`, and run with `root-framework` or `root-framework.pyroot`.

It is required to use the specific PyROOT binary to access a suitable Python shell with the ROOT bindings. They are not exposed to the native system and do not work from the standard Python shell.

Jupyter support is built in, and can be accessed with `root-framework --notebook`. This may be preferably to using the PyROOT command

Python3 is bundled and comes with Matplotlib, SciPy, NumPy, and Pandas.

See how to install snapd [here](https://snapcraft.io/docs/installing-snapd).

`sudo snap install root-framework`

Unfortunately I cannot commit to providing regular updates to this package nor guarantee it is fit for any particular purpose. 

Users are encouraged to read the [compatibility guarantees](https://root.cern/about/versioning/) provided by ROOT.

Please note that whilst this repository is under MIT licensing, the actual ROOT software is LGPL 2.1+ and its source may be found [here](https://github.com/root-project/root.git).
Furthermore, the actual license of the distributed snap is GPL3.0, due to linking with GSL.
Documentation of the included Ubuntu packages in the snap can be found in `/snap/root-framework/current/usr/share/doc` and accessed at [https://packages.ubuntu.com/](https://packages.ubuntu.com/).
Some packages will use the builtin packages from the CMake build tools. Refer to the ROOT source repo for more information.



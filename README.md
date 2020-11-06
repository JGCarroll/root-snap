# ROOT snap

This repository contains the build files for generating a snap package of the [ROOT Framework](https://root.cern).

It is intended to provide a functional package of ROOT for people who simply want access to a functional, minimal effort installation for home use cases.

It can be installed on any snapd compatible system with `sudo snap install root-framework`, and run with `root-framework` or `root-framework.pyroot`.

See how to install snapd [here](https://snapcraft.io/docs/installing-snapd).

Unfortunately I cannot commit to providing regular updates to this package nor guarantee it is fit for any particular purpose. 

Users are encouraged to read the [compatibility guarantees](https://root.cern/about/versioning/) provided by ROOT.

Please note that whilst this repository is under MIT licensing, the actual ROOT software is LGPL 2.1+ and its source may be found [here](https://github.com/root-project/root.git).

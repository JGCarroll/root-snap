# An open-source data analysis framework used by high energy physics and others, in a snap!

## General installation and use
This snap is intended to provide an easy-to-install package of the ROOT framework for the home user. It comes bundled along with Python 3.8/PyROOT and Jupyter/JupyROOT notebook capability. NumPy, SciPy, Pandas and Matplotlib are bundled with the Python environments.

Snaps are container packages for easy application deployment, designed to be consistent and reliable across different host distributions. They additionally impose some strong sandboxing for security. One caveat of this sandboxing is that this package can only read/write to your `$HOME` directory, or via specific network protocols. It is highly advised that you place all your data files in your `$HOME` directory to be accessible. 

Users are encouraged to use the command `snap info root-framework` to see the binaries available to them from the ROOT framework. By default, ROOT can be accessed with the command `root-framework`. Users may wish to use an alias so that it is simply accessible with `root`. Similarly, by default, other binaries such as hadd can be accessed with `root-framework.hadd`, which again can be aliased as `hadd`. Jupyter notebook support can be utilised with `root-framework --notebook`, or `root --notebook` if aliased.


`sudo snap alias root-framework root`

`sudo snap alias root-framework.hadd hadd`


Because snaps are containers and don't affect the host system, using PyROOT with `import ROOT` will not work in a system Python shell. Users are encouraged to use `root-framework.pyroot` to access the containers' Python shell, where `import ROOT` would become available. Again, this can be aliased for simple usage such as `pyroot script.py`.

`sudo snap alias root-framework.pyroot pyroot`

## Support
Unfortunately I cannot commit to providing regular updates to this package nor guarantee it is fit for any particular purpose. 
It has been tested and shown to be capable of a lot of common ROOT functionality, and I hope it is useful. However I cannot guarantee that poweruser functionality will be functional at all. Whilst I can try resolve any issues to the best of my ability, it may be that switching to an officially supported upstream release is the recommended solution.

Users are encouraged to read the [compatibility guarantees](https://root.cern/about/versioning/) provided by ROOT.

## Licensing
Please note that whilst this repository is under MIT licensing, the actual ROOT software is LGPL 2.1+ and its source may be found [here](https://github.com/root-project/root.git).
Furthermore, the actual license of the distributed snap is GPL3.0, due to linking with GSL.
Documentation of the included Ubuntu packages in the snap can be found in `/snap/root-framework/current/usr/share/doc` and accessed at [https://packages.ubuntu.com/](https://packages.ubuntu.com/).
Some packages will use the builtin packages from the CMake build tools. Refer to the ROOT source repo for more information.

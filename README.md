# An open-source data analysis framework used by high energy physics and others, in a snap!
[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/root-framework)

## General installation and use
This snap is intended to provide an easy-to-install package of the ROOT framework for the home user. It comes bundled along with Python 3.8/PyROOT and Jupyter/JupyROOT notebook capability. NumPy, SciPy, Pandas and Matplotlib are bundled with the Python environments.

  Snaps are container packages for easy application deployment, designed to be consistent and reliable across different host distributions. They additionally impose some strong sandboxing for security. One caveat of this sandboxing is that this package can only read/write to your `$HOME` directory, or via specific network protocols. It is highly advised that you place all your data files in your `$HOME` directory to be accessible. 
  
  Because snaps are containers and don't affect the host system, using PyROOT with `import ROOT` will not work in a system Python shell. Users are encouraged to use the command `pyroot` to access the containers' Python shell, where `import ROOT` would become available. Scripts can be passed to `pyroot` to be executed in PyROOTs context, E.G, `pyroot ./myScript.py`, or put in the scripts shebang. E.G `#!/snap/bin/pyroot`
  
  JupyROOT can be accessed by running `root --notebook`.

  For user convenience, application entries for ROOT and PyROOT will be placed into the systems start menu by default. 

## Support
Unfortunately I cannot commit to providing regular updates to this package nor guarantee it is fit for any particular purpose. 
It has been tested and shown to be capable of a lot of common ROOT functionality, and I hope it is useful. However I cannot guarantee that poweruser functionality will be functional at all. Whilst I can try resolve any issues to the best of my ability, it may be that switching to an officially supported upstream release is the recommended solution.

Users are encouraged to read the [compatibility guarantees](https://root.cern/about/versioning/) provided by ROOT.

## Licensing
Please note that whilst this repository is under MIT licensing, the actual ROOT software is LGPL 2.1+ and its source may be found [here](https://github.com/root-project/root.git).
Furthermore, the actual license of the distributed snap is GPL3.0, due to linking with GSL.
Documentation of the included Ubuntu packages in the snap can be found in `/snap/root-framework/current/usr/share/doc` and accessed at [https://packages.ubuntu.com/](https://packages.ubuntu.com/).
Some packages will use the builtin packages from the CMake build tools. Refer to the ROOT source repo for more information.

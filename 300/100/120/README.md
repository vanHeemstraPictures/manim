# 120 - Install LaTex (optional)

LaTeX is a very well-known and widely used typesetting system allowing you to write formulas like

If rendering plain text is sufficient for your needs and you don’t want to render any typeset formulas, you can technically skip this step. Otherwise select your operating system from the tab list below and follow the instructions.

## Windows

For Windows we recommend installing LaTeX via the [MiKTeX distribution](https://miktex.org/). Simply grab the Windows installer available from their download page, https://miktex.org/download and run it.

## MacOS

If you are running MacOS, we recommend installing the [MacTeX distribution](https://www.tug.org/mactex/). The latest available PKG file can be downloaded from https://www.tug.org/mactex/mactex-download.html. Get it and follow the standard installation procedure.

## Linux

Given the large number of Linux distributions with different ways of installing packages, we cannot give detailed instructions for all package managers.

In general we recommend to install a TeX Live distribution (https://www.tug.org/texlive/). For most Linux distributions, TeX Live has already been packaged such that it can be installed easily with your system package manager. Search the internet and your usual OS resources for detailed instructions.

For example, on Debian-based systems with the package manager apt, a full TeX Live distribution can be installed by running

```
sudo apt install texlive-full
```

For Fedora (managed via dnf), the corresponding command is

```
sudo dnf install texlive-scheme-full
```

As soon as LaTeX is installed, continue with actually installing Manim itself.

**Troubleshooting**

If you encounter the error “Unable to locate package texlive-full”, please use ```apt update``` and ```apt upgrade``` to update the system package repository index and related software packages to the latest version.

Once ```which latex``` returns the address, it indicates that the installation is successful and the command-line tool can be used.
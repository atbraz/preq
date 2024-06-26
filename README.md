# preq
![PyPI - Version](https://img.shields.io/pypi/v/preq?style=for-the-badge&link=https%3A%2F%2Fpypi.org%2Fproject%2Fpreq%2F)
![Python Version from PEP 621 TOML](https://img.shields.io/python/required-version-toml?tomlFilePath=https%3A%2F%2Fraw.githubusercontent.com%2Fatbraz%2Fpreq%2Fmain%2Fpyproject.toml&style=for-the-badge&logo=python&logoColor=f9d35a&label=%20&labelColor=3d6fa0&color=555555)
![Static Badge](https://img.shields.io/badge/Written_in_Rust-_?style=for-the-badge&logo=rust&logoColor=orange&labelColor=303030&color=555555)
![PyPI - License](https://img.shields.io/pypi/l/preq?style=for-the-badge)

------------------

`preq` is a Rust-based tool inspired by the popular Python package [pipreqs](https://github.com/bndr/pipreqs). It aims to extend the functionality of `pipreqs` by leveraging the newer Python package metadata features to analyze Python projects and generate detailed dependency files. `preq` is designed to read imports from `.py` files, map their package names and versions and write them to a `requirements.txt` file or directly into the `pyproject.toml` under the dependencies section.

## Features

- **Read Python Imports:** Automatically scans Python files for import statements.
- **Generate Dependency Files:** Writes detected package names and versions either to `requirements.txt` or `pyproject.toml`.
- **Rust-Powered:** Utilizes the efficiency and safety of Rust to handle file operations and data processing.

## Upcoming Features

- **Recursive Optional Dependencies:** Ability to recursively generate optional dependencies for modules.
- **Version Specifier Management:** Will provide tools to pin or otherwise describe [PEP 508](https://peps.python.org/pep-0508/) package versions.
- **Latest Version Retrieval:** Functionality to fetch the latest available package versions from PyPI.
- **Version Conflict Resolution:** Resolve conflicts in imported packages before writing requirements.

## Installation

`preq` can be easily installed via PyPI. To install `preq`, run the following command:

```bash
pip install preq
```

# Usage
Once installed, preq can be used directly from the command line or as part of a Python or Rust project. Basic usage to generate a requirements.txt file in the current working directory is as follows:

```bash
preq /path/to/python/project
```
To generate dependencies directly into pyproject.toml, use:
```bash
preq /path/to/python/project --output pyproject.toml
```

More detailed documentation on command-line options and configurations will be available as the project matures.

## Help command
You can view a list of all available commands and their descriptions by running:
```bash
preq -h
```
>While the `-h` option is fully functional, providing detailed help on using the tool, please be aware that most other command-line arguments are still in development. These arguments are placeholders at this time and may not yet be implemented. Future updates will activate these options as features are developed and integrated into preq.

# Contributing
Contributions to preq are welcome! Whether it involves feature development, bug fixes, or documentation improvements, feel free to fork the repository and submit a pull request.

# Motivation

The inception of `preq` was driven by challenges encountered in a busy Python package multirepository environment, where many developers worked simultaneously, often in isolation from their peers' activities. This dynamic led to several issues:

- **Dependency Bloat:** As developers added new functionalities and dependencies independently, the aggregate requirements of projects ballooned, complicating the dependency graph and increasing the risk of conflicts.
- **Breaking Changes:** New dependencies or updated versions introduced by one developer could inadvertently break other parts of the project, leading to unexpected malfunctions and increased debugging efforts.
- **Overhead for Developers:** Some developers found it cumbersome to manually track and manage dependencies, especially when moving code from development environments like Jupyter notebooks into more structured Python projects.

`preq` aims to alleviate these pain points by providing a tool that automates the extraction and management of package dependencies. It is particularly useful for:

- **Forgetful or Novice Developers:** Those who may not remember every dependency or are not fully aware of the implications of adding new ones.
- **Developers Utilizing Open Source Code:** For those frequently incorporating snippets from open sources, `preq` ensures that all underlying dependencies are recognized and properly managed.
- **Streamlining Development Workflows:** By automating dependency management, `preq` helps maintain a clean and efficient development pipeline, ensuring that all necessary packages are included without redundancy or conflict.
- 
# License
This project is licensed under the MIT License - see the LICENSE file for details.

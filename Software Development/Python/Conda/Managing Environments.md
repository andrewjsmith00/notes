# Managing Environments
With conda you can create, export, list, remove and update environments that have different versions of [[Python]] and/or package installed in them. Switching or moving between environments is called activating the environment

## Creating an environment
By default, environments are installed into the `envs` directory in the conda directory.

- To create an environment called myenv run :
```bash
conda create --name myenv
```

- To create an environment with a specific version of [[Python]] run:
```bash
conda create -n myenv python=3.6
```

- To create an environment with a specific package run:
```bash
conda create -n myenv scipy
```

To automatically install pip or something else with every environment created, add the default programs to the `create_default_packages` section of the `.condarc` configuration file. These default packages are installed every time a new environment is created. If you do not want the default packages installed in a particular environment use the `--no-default-packages` flag

```bash
conda create --no-default-packages -n myenv python
```

### Creating an environment from an environment.yml file
- Create the environment from the `environment.yml` file:
```bash
conda env create -f environment.yml
```
The first line of the `yml`  file sets the new environments name.

### Specifying a location for an environment
You can control where a conda environment lives by providing a path to a target directory when creating the environment. For example the following creates an environment in a subdirectory of the current working directory called `envs`:
```bash
conda create --prefix ./envs
```

You can then activate the environment created with a prefix using the same command to activvate environments created by name:
```bash
conda activate ./envs
```

Specifying a path to a subdirectory of a project directory when creating an environment has the following benefits:
- It makes it easy to tell if the project uses an isolated environment by including the environment as a subdirectory
- It makes the project more self-contained as everything, including the required software, is contained in a single project directory.

An additional benefit of creating environments in a subdirectory is that the same name can be used for all environments, whereas environments in `envs` require different names

### Updating an environment
You may need to update an envuronment for a variety of reasons, these can include:
- A core dependency released a new version
- An additional package is needed for data analysis
- A better package was found and the old is no longer needed

If any of these occur, you can update the `environment.yml` file and then run the following
```bash
conda env update --prefix ./env --file environment.yml --prune
```

Note: The `--prune` option causes conda to remove any dependencies that are no longer required from the environment

### Cloning an environment
You can make an exact copy of an environment by creating a clone of it as follows:
```bash
conda create --name myclone --clone myenv
```


# Generate dependency graph for conans

## Requirements

- ```pip install snakefood```

- **graphviz**:
    - MacOSX: ```brew install graphviz```
    - Debian: ```apt-get install graphviz```
    - Centos: ```yum install graphviz``` 

## Usage

Create a virtualenv and install all conans requirements listed at
```../conans/requirements*```

- ```make```: generates ```conans.pdf``` with dependency graph of conan source code
- ```make realclean```: removes all temporary files used by **snakefood**


## Output

See ```conans.pdf```


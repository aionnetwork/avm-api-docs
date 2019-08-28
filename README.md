# Aion AVM API Docs

This repository is a website for reviewing AVM API documentation. It is deployed at [avm-api.aion.network](https://avm-api.aion.network/). The contents of this repository is created by building the AVM repository and copying the contents of the `javadoc` folder. No manual changes are made to this repository, other than this `README.md` file.

## Building

Currently the steps to build this project are not automatic, and must be done manually.

### Prerequisites

1. [Apache Ant](http://ant.apache.org/)
2. [Git](https://git-scm.com/)

### One Liner

Run this one-line to perform all the individual steps in one go:

```bash
git clone https://github.com/aionnetwork/AVM.git ~/avm &&
git clone https://github.com/aionnetwork/avm-api-docs.git ~/avm-api-docs &&
cd avm &&
ant &&
yes | cp -rf ~/avm/dist/javadoc/ ~/avm-api-docs/ &&
rm -rf ~/avm-api-docs/jquery &&
cd ~/avm-api-docs && git add . &&
git commit -m "New AVM build." &&
git push
```

If something is going wrong, perform the individual steps one by one to figure out what's happening.

### Individual Steps

1. Clone or pull the latest changes to `aionnetwork/avm` from the `master` branch:

    ```bash
    git clone https://github.com/aionnetwork/AVM.git ~/avm
    ```

1. Clone or pull the latest changes to `aionnetwork/avm-api-docs` from the `master` branch:

    ```bash
    git clone https://github.com/aionnetwork/avm-api-docs.git ~/avm-api-docs
    ```

2. Move into the AVM repository and build the AVM project

    ```bash
    cd avm
    ant
    ```

3. Copy the entire `dist/javadoc` directory to the `aionnetwork/avm-api-docs` repository:

    ```bash
    yes | cp -rf ~/avm/dist/javadoc/ ~/avm-api-docs/
    ```

4. Disable jQuery removing the folder:

    ```bash
    rm -rf ~/avm-api-docs/jquery
    ```

5. Commit, stage, and push changes within the `aionnetwork/avm-api-docs` repository:

    ```bash
    cd ~/avm-api-docs
    git add .
    git commit -m "New AVM build."
    git push
    ```

The HTML is still requesting jQuery, but since the folder has been deleted there's nothing for it to access. The contents of that folder are then copied into this repository, where it is published by [Netlify](https://www.netlify.com/).

## Contributing

This repository is derived directly from:

- [org.aion.avm.api](https://github.com/aionnetwork/AVM/tree/16537d4cc2359371e1cf7222dff7b273511eb1cc/org.aion.avm.api)
- [org.aion.avm.userlib](https://github.com/aionnetwork/AVM/tree/16537d4cc2359371e1cf7222dff7b273511eb1cc/org.aion.avm.userlib)

You can edit those files and then after the next build, they will be included in this repository.

Issues and pull requests against this repository will be in scope only to edit this `README.md` file.

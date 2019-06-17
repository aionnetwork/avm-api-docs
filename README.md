# Aion AVM API Docs

This repository is a website for reviewing AVM API documentation. It is deployed at [avm-api.aion.network](https://avm-api.aion.network/).

## Building

This repository is created when a new Aion Java Kernel build is released. To create this repository from scratch:

1. Clone the latest Aion AVM repository: `git clone https://github.com/aionnetwork/AVM.git`
2. Move into the aion directory: `cd AVM`
3. Build the kernel: `ant`
4. The API website now in `AVM/dist/javadoc`.

The contents of that folder are then copied into this repository, where it is published by [Netlify](https://www.netlify.com/).

## Contributing

This repository is derived directly from:

https://github.com/aionnetwork/AVM/tree/16537d4cc2359371e1cf7222dff7b273511eb1cc/org.aion.avm.api
https://github.com/aionnetwork/AVM/tree/16537d4cc2359371e1cf7222dff7b273511eb1cc/org.aion.avm.userlib

You can edit those files and then after the next build, they will be included in this repository.

Issues and pull requests against this repository will be in scope only to edit this `README.md` file.

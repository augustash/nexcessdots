# 💻 CLI Configuration Files

This repository contains a simple set of [Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) configuration files
for the CLI. Makes working on our managed servers a little more pleasant.

To make installation and management easier across multiple servers, we are using [chezmoi](https://www.chezmoi.io/).

## 🚀 Installation

Installation is a breeze and can be handled in a single command. Run this command to both install `chezmoi` to our
custom location and initialize this repository:

```bash
sh -c "$(curl -fsLS get.chezmoi.io)" -- -b "$HOME/.local/bin" init --apply https://github.com/augustash/nexcessdots.git
```

After installed, it's pretty easy from there. Source the `.bash_profile` file to load the new configuration:

```bash
source .bash_profile
```

Future updates can be applied by running:

```bash
chezmoi update
```

You can find the [quick start guide](https://www.chezmoi.io/quick-start/) and full documentation for `chezmoi` on their
website.

## 📝 Testing

If you are testing changes to the configuration files, you can fire up a Docker container to try out your work in a
clean environment. The below Docker command will get you a fresh, disposable, testing environment. Then run the
installation steps from above.

```bash
docker run --rm -it --user vscode --workdir /home/vscode mcr.microsoft.com/devcontainers/base:ubuntu
```

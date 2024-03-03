[Back to Main README.md file](../../README.md)

# Updating GitHub CLI (`gh`) to Version 2.42.1 on Linux

This README provides step-by-step instructions for updating the GitHub Command Line Interface (GitHub CLI, or `gh`) to version 2.42.1 on a Linux system.

## Checking the Current Version

To check your current version of `gh`, run:

```bash
gh --version
```

## Uninstalling the Old Version

If you have an outdated version of `gh`, remove it using your package manager.

For a version installed via `apt`:

```bash
sudo apt-get remove gh
```

For a version installed via `snap`:

```bash
sudo snap remove gh
```

## Installing Version 2.42.1

### Using `.deb` Package

1. **Download Version 2.42.1 `.deb` Package**:
   Download the `.deb` package for version 2.42.1 from the [GitHub CLI releases page](https://github.com/cli/cli/releases/tag/v2.42.1).

2. **Install the Package**:
   Navigate to the directory where the file is downloaded and run:
   ```bash
   sudo dpkg -i gh_2.42.1_linux_amd64.deb
   ```

### Using Official Install Script

Alternatively, you can use the official install script provided by GitHub:

```bash
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo gpg --dearmor -o /usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update
sudo apt install gh
```

## Verifying the Installation

After installation, check the version again:

```bash
gh --version
```

The output should be: `gh version 2.42.1 (2024-01-16)`

## Troubleshooting

If the version hasn't updated, try clearing the shell's hash table or updating your PATH:

- Clear the hash for `gh`:
  ```bash
  hash -d gh
  ```
- Or clear the entire hash table:
  ```bash
  hash -r
  ```

Then, verify the version again:

```bash
gh --version
```

## Notes

- Ensure `/usr/bin` is included in your PATH.
- If you encounter issues with multiple installations (e.g., `apt` and `snap`), consider using one package manager for simplicity.

[Back to Main README.md file](../../README.md)
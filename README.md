# spokes

This tool is designed to help you manage changes in multiple GitHub repositories efficiently. It has not been provided prepackaged as a downloadable, standalone file, as improper configuration or usage could lead to irreconcilable consequences.

This specific example was intended to provide functionalities in disabling packages and releases for repositories and mark changes for review using the GitHub CLI, and will need to be modified to match the user's intended purposes.

### Implementation specifically for Linux (Ubuntu LTS)

This implementation guide focuses on Ubuntu LTS, but the steps can be adapted for Windows with slight modifications.

#### Prerequisites

- [GitHub CLI](https://cli.github.com/) must be installed on your machine.

#### Usage
```
├── 1. Log in to your GitHub account using the GitHub CLI
│ ├── gh auth login
│ └── Provide your GitHub credentials to log in
├── 2. Change to the directory containing your repositories
│ ├── cd /home/GitHubFAN23/github
│ └── Replace "/home/GitHubFAN23/github" with the actual directory path
├── 3. Loop through repositories and mark changes
│ ├── for dir in /; do
│ ├── dir=${dir%/}
│ ├── echo $dir
│ ├── cd $dir
│ ├── gh pr create --web
│ └── cd ..
└── 4. Commit the changes
└── gh pr create
```

#### 1. **Log in to your GitHub account using the GitHub CLI:**
Run the following command to log in to your GitHub account:
- `gh auth login`

> Provide your GitHub credentials when prompted.

#### 2. **Change to the directory containing your repositories:**
Navigate to the directory where your repositories are located.
- For example: `cd /home/GitHubFAN23/github`

> Replace "/home/GitHubFAN23/github" with the actual directory path where your repositories are stored.

#### 3. **Loop through repositories and mark changes:**
Use the following command to iterate over each repository, echo the repository name, open a browser for reviewing and marking changes using the GitHub CLI's `gh pr create --web` command:

```bash
for dir in */; do
  dir=${dir%*/}
  echo $dir
  cd $dir
  gh pr create --web
  cd ..
done
```

> Review the changes in the browser and make any necessary modifications.

### Commit the changes:
#### Run the following command to create a pull request with the changes you marked:
```bash
gh pr create
```

## Limitations
This tool assumes that you have already installed GitHub CLI and have a valid GitHub account.

The implementation provided here assumes a Linux (Ubuntu LTS) environment, but it can be adapted for Windows with minor modifications.

The provided implementation assumes that your repositories are stored in a specific directory. Adjust the directory path accordingly.

The implementation focuses on marking changes using the GitHub CLI. Additional steps, such as actual code changes, are not covered here.

## [Disclaimer](DISCLAIMER)
**This software is provided "as is" and without warranty of any kind**, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the software or the use or other dealings in the software.

**The authors do not endorse or support any harmful or malicious activities** that may be carried out with the software. It is the user's responsibility to ensure that their use of the software complies with all applicable laws and regulations.

## License

These files released under the [MIT License](LICENSE).

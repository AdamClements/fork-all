Fork-all Script
This script allows you to clone an upstream repository and set up remotes for each of the forks of that repository. Your own fork, as determined by your GitHub credentials, is automatically added as the 'origin'.

Usage
bash
Copy code
fork-all <repository> [branch]
repository is the GitHub repository in the format 'org/repo' or 'user/repo'.

branch is an optional argument that specifies the branch to checkout after cloning. It assumes 'origin/branch' unless otherwise specified, and if it doesn't exist, it creates a new one based on upstream/main.

GitHub usernames for other forks of the repository can be aliased for easier management of remotes using a .fork-all-alias file in your home directory. This file should contain lines in the format:

bash
Copy code
GithubUsername="alias"
For example:

bash
Copy code
ElmerFuddIzDaBest1981="elmer"
If no alias is provided, the script uses the GitHub username as the remote name.

Examples
bash
Copy code
fork-all acme/trap-designs
This command clones the 'acme/trap-designs' repository and adds remotes for each fork.

bash
Copy code
fork-all acme/trap-designs WileyCoyote/fake-tunnel
fork-all acme/trap-designs elmer/wabbit-twap
These commands clone the 'acme/trap-designs' repository and checkout the specified branch from the collaborator's fork.

bash
Copy code
fork-all acme/trap-designs existing-branch
fork-all acme/trap-designs new-feature
These commands clone your own fork of acme/trap-designs, add others as remotes, and checkout your own existing branch 'existing-branch' or create a new branch 'new-feature' which is synced to upstream/main.

License
This software is licensed under the Eclipse Public License 2.0 (EPL-2.0). For more information, please see the LICENSE file.
# How to setup our ssh key to connect with github
- Step1 -> You need to cd into you ssh directory `cd .ssh`
- Step2 -> Next create the rsa key by using the command `ssh-keygen -o -t rsa -C "email@example.com"`
- Step3 -> Use the `cat` command to copy the public key in the `.pub` file and add the ssh key to github and save it
- Step4 -> Enter the ssh agent using the command `eval 'ssh-agent -s'`.
- Step5 -> Now register the private key onto the ssh using the command `ssh-add github-key`
- Step6 -> Init git onto your working directory using `git init`
- Step7 -> Now we need to tell git that we want to use ssh by using git remote and the full command is `git remote add origin <SSH path from your repo on github.com>`
- Step8 -> Now we can push changes to our repo by using `git push -u origin main`

## Extra info about switching protocols
- If we would like to change protocols from `ssh` to `https` we need to remove the protocol by using `git remote remove origin` and then we use our old command with our https link: `git remote add origin <HTTPS path from your repo on github.com>`

# SSH Diagram
![](./cloud_computing_with_AWS/images/sshkeys.PNG)
# Connect bitbucket through ssh keys from centos server

1. **Generate SSH Key**: If you haven't generated an SSH key yet, create one using the following command:

   `$ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

2. **Add SSH Key to SSH Agent**: Ensure the SSH key is added to the SSH agent:


   `$eval "$(ssh-agent -s)"`
   `$ssh-add ~/.ssh/id_rsa`

3. **Add SSH Key to Bitbucket**:

     - Go to Bitbucket settings.
     - Choose "SSH keys" under the "Security" section.
     - Add your public key (~/.ssh/id_rsa.pub) to your Bitbucket account**.

4. Verify Connection: To test your connection to Bitbucket, use the following command:
   
   `$ssh -T git@bitbucket.org`

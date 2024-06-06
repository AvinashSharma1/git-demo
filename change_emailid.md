#### To change the email ID and password for your current repository in Bitbucket, you'll need to update your Git configuration and possibly your credentials.
### Here's a step-by-step guide:

## Step 1: Change Git Configuration
### For the Current Repository
  Navigate to the root directory of your repository and run:
  ``` git config user.email "your-new-email@example.com" ```
### Globally 
  If you want to change it globally (for all repositories), run:
  ```git config --global user.email "your-new-email@example.com" ```
## Step 2: Update Bitbucket Credentials
  + ### Clear the old credentials:
    ``` git credential-cache exit ```
  + Remove stored credentials:
      + On Linux:
        ```
        git config --global --unset credential.helper
        ```

   + Set the git repository
      + url if using https
        ```
        git remote set-url origin https://username@bitbucket.org/username/repository.git
        ```
      + if ssh
           ```
            git remote set-url origin git@bitbucket.org:username/repository.git
          ```

## Step 3: Using SSH Key (Optional)
  + ### 1. Generate a new SSH key:
    ``` ssh-keygen -t rsa -b 4096 -C "your-new-email@example.com" ```
  + ### 2. Add the SSH key to your SSH agent:
    ``` eval "$(ssh-agent -s)"
        ssh-add ~/.ssh/id_rsa
    ```
  + ### 3. Add the SSH key to your Bitbucket account:
    Copy the content of your SSH public key:
    ```
    cat ~/.ssh/id_rsa.pub
    ```
  + ### 4. Then go to Bitbucket -> Personal Settings -> SSH keys -> Add key, and paste your SSH public key there.
  + ### 5. Update the repository to use SSH:
    ```
    git remote set-url origin git@bitbucket.org:username/repository.git
    ```
    Replace username/repository.git with your repository path.

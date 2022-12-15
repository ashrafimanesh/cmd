# SSH
SSH useful commands:

## Login to server without password
ssh-copy-id [-i [identity_file]] [user@]machine

``` ssh-copy-id -i ~/.ssh/id_rsa.pub user@machine ```

## generate ssh key

``` ssh-keygen -t rsa ```

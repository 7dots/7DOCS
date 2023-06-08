# rsync

An alternative to wget.

This is particularly useful when `assest` directories are too large to get using `wget`, or in the case of Wirehive when they remove an `assets.tar.gz` for example.

`rsync --progress -azvP -e "ssh -i '/FULL/PATH/SSH-KEY.pem'" SSH_USERNAME@xx.xx.xx.xxx:/var/www/vhosts/FULL/REMOTE/ASSETS/PATH/ /FULL/LOCAL/ASSETS/PATH`

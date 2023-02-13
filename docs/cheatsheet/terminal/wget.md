# Standard wget

`wget https://my-demo-site.com/assets.tar.gz`

---

# wget with Directory Security
`wget --user=7dots --ask-password https://my-demo-site.com/assets.tar.gz`

###### Note
If you need to ***wget*** when there is Directory Security, it is best practise to use `--ask-password` to allow you to type it in so it's not visible when cycling up your terminal.  

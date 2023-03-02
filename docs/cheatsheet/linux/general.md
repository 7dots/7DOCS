# Useful cli commands

## Find CentOS version

```bash
cat /etc/centos-release
```


## Reboot required

```bash
needs-restarting --reboothint
```

## grep

```bash
# Recursively find string in path
grep -rnw '/path/to/somewhere/' -e 'pattern'
```

## chmod

```bash
# Copy permissions from one element to another
chmod --reference=FROM TO
```

## find

```bash
# Find all .md files recursively in the current location
find . -type f -name "*.md"
```

```bash
# Delete all .md files recursively in the current location - here be dragons!
find . -type f -name "*.md" -delete
```

## ls

```bash
# Move or copy files matching a pattern and rename
ls -1 *-le-ssl.conf | xargs -L1 -I{} mv {} {}.disabled
```

## ACL (Access Control List)

```bash
# Get ACL permissions
getfacl dirname
```

```bash
# Set inheritable group read/write/execute permissions on dirname
setfacl -d -m g:www-pub:rwx dirname
```

```bash
# Copy parent ACL to dir recursively
getfacl . | setfacl -R --set-file=- dirname
```

```bash
# Copy ACL from dir to another dir
getfacl fromdirname | setfacl --set-file=- todirname
```

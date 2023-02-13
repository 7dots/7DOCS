# Splitting and concatenating gzip files

### To split
`split -b 300M -d assets.tar.gz parts.tar.gz`

### To concatenate
`cat parts.tar.gz* > assets.tar.gz`

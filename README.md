# Buildpack Deployer

Bash library to deploy a buildpack

* Download runtime dependencies
* Cache third-party archive for faster deployment
* Create symlinks between dependencies to avoid double download

Usage:

```bash
cache_directory=$1
dest_directory=$2

language='ruby'

dependencies=(
  'http://ftp.ruby.org/2.2/ruby-2.2.tgz'
)

symlinks=(
  'http___ftp.ruby.org_2.2_ruby-2.2.tgz:ruby-stable.tgz'
)

excluded_files=(
  '.git/'
  '.gitignore'
)


source buildpack-deployer/lib/deployer
deploy_buildpack "${cache_directory}" "${dest_directory}"
```


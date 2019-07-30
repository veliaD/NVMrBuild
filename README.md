This branch/repo is a companion branch to the NVMr module development
branch.

It contains scripts to build and kernel configuration files.

The following is an example of how to mount the two branches on a FreeBSD 12
system to build the sources over NFS:
```
mkdir -p /b/mnt/freebsd-src /b/mnt/nvmrBuild && mount -t nfs -o tcp,nfsv3,intr remotedev:/local/home/dveliath/git/nvmr /b/mnt/freebsd-src && mount -t nfs -o tcp,nfsv3,intr remotedev:/local/home/dveliath/git/NVMrBuild /b/mnt/nvmrBuild/src
```

followed by:
```
/b/mnt/nvmrBuild/src/scripts/bldFromScratchKrnl DEBUG
```
to build a kernel with INVARIANTS and other debugging enabled, and
```
/b/mnt/nvmrBuild/src/scripts/bldFromScratchKrnl RELEASE
```
for a regular kernel.

Use `/b/mnt/nvmrBuild/src/scripts/tmnstlKrnlNmods` to install a `DEBUG` or
`RELEASE` kernel.

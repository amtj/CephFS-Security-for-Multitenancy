# CephFS: Security for Multitenancy
Just a small repository to keep code patches of my project I worked on during
Google Summer of Code 2015 with [Ceph](http://ceph.com/).

## Project Info
CephFS mostly assumed a controlled environment where it used to trust the
UID/GID of the clients. This is like any typical NFS environment. This projects
restricted clients only to the paths they are allowed to mount.

This is achieved by path-based mount restrictions, adding client security caps
to the MDS, which specifies what part of the tree they're allowed to access. And
then, incoming client requests are compared to those allowances to the directory
(dentry) that the request is touching. Along with this, it performs a directory
(dentry) comparison before it locks and after then a pretty simple generic check
is added that verifies metadata about a file are in the right subtree.
 
[GSoC Archive](http://www.google-melange.com/gsoc/project/details/google/gsoc2015/jashank42/5668600916475904)

[Commits](https://github.com/ceph/ceph/commits/master?author=amtoj)

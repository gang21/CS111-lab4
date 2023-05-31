## UID: 005677251

(IMPORTANT: Only replace the above numbers with your true UID, do not modify spacing and newlines, otherwise your tarfile might not be created correctly)

# Hey! I'm Filing Here

This code runs a valid ext2 filesystem containing 2 directories, 1 regular file, and 1 symbolic link. 

## Building

To build the program, download the Makefile and ext2-create.c file. Then in the folder containing both of those files, run the following shell commands:
```
make
```

## Running
To compile the program, run the following command:
```
./ext2-create
```
To mount the file system, run the following commands:
```
mkdir mnt
sudo mount -o loop cs111-base.img mnt
```
Then to check the contents of the mounted filesystem:
```
cd mnt
ls -ain
# total 7
#      2 drwxr-xr-x 3    0    0 1024 May 31 10:42 .
# 966462 drwxr-xr-x 3 1000 1000 4096 May 31 10:42 ..
#     13 lrw-r--r-- 1 1000 1000   11 May 31 10:42 hello -> hello-world
#     12 -rw-r--r-- 1 1000 1000   12 May 31 10:42 hello-world
#     11 drwxr-xr-x 2    0    0 1024 May 31 10:42 lost+found
```

## Cleaning up

Explain briefly how to unmount the filesystem, remove the mount directory, and
clean up all binary files.
To unmount the filesystem:
```
sudo umount mnt
```
To remove the mount directory:
```
rmdir mnt
```
To clean up all binary files:
```
make clean
```

* [list groups](https://serverfault.com/questions/127782/how-can-i-get-a-list-of-linux-users-group/127784)
```bash
$ getent passwd | awk -F: '{print $1}' | while read name; do groups $name; done
```
* Change group / ower of file
```bash
# Change owner
$ sudo chown user_name file_path
# By default, chown follows symbolic links and changes the owner of the file pointed to by the symbolic link. If you wish to change ownership of all files inside a directory, you can use the -R option.
$ sudo chown -R user_name dir_path

# Change group
$ sudo chgrp group_name file_path
$ sudo chgrp group_name dir_path

# Change owner & group by chown
$ sudo chown user_name:group_name file_path
```
* List groups
```bash
$ groups
# Change group of user
$ groups user_name
```
* Unzip tar.gz 
Type man tar for more information, but this command should do the trick:
```bash
$ tar -xvzf community_images.tar.gz
```
To explain a little further, tar collected all the files into one package, community_images.tar. The gzip program applied compression, hence the gz extension. So the command does a couple things:

  f: this must be the last flag of the command, and the tar file must be immediately after. It tells tar the name and path of the compressed file.
  
  z: tells tar to decompress the archive using gzip
  
  x: tar can collect files or extract them. x does the latter.
  
  v: makes tar talk a lot. Verbose output shows you all the files being extracted.
  
## References
[Ask Ubuntu](https://askubuntu.com/)

* [list groups](https://serverfault.com/questions/127782/how-can-i-get-a-list-of-linux-users-group/127784)
```bash
$ getent passwd | awk -F: '{print $1}' | while read name; do groups $name; done
```

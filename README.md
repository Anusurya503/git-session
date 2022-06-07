# git-session
## git
git is like a key value store 
value = data 
key = HASH of data --> use key to retrieve the content

```bash
echo 'content' | git hash-object --stdin
```
```bash 
echo 'blob size of content \0 content' | openss | sha1
```

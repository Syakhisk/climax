# Miscellaneous

## Upload file from the terminal

**[transfer.sh](https://transfer.sh)**

```bash
$ curl --upload-file ./hello.txt https://transfer.sh/hello.txt
https://transfer.sh/rdh45o/hello.txt

$ curl -H "Max-Downloads: 1" -H "Max-Days: 5" --upload-file ./hello.txt https://transfer.sh/hello.txt
https://transfer.sh/rdh45o/hello.txt
```


**[null pointer, 0x0.st](http://0x0.st)**  
```bash
curl -F'file=@yourfile.png' https://0x0.st
```

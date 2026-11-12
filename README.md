# FTP Download Client

A command-line FTP client written in C that downloads a file from a URL using **raw TCP sockets**, without any FTP library.

```bash
./download ftp://[<user>:<password>@]<host>/<url-path>
```

## How it works
1. **Parses the URL** into user, password, host and path (anonymous login if none is given)
2. **Resolves the host name** to an IP address
3. Opens the **control connection** on port 21 and sends `USER` and `PASS`
4. Enters **passive mode** with `PASV` and computes the data port from the server reply
5. Opens the **data connection**, sends `RETR` and writes the file to disk

## Run
```bash
make
./download ftp://ftp.up.pt/pub/kodi/robots.txt
```

---
Academic project developed at FEUP (Faculty of Engineering, University of Porto) as part of the Informatics and Computing Engineering programme.

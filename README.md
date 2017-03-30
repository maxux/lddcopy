# lddcopy

Copy binary libraries dependencies to a specific root

# What does that do

This script copies:
- libresolv dependencies to the root target
- shared libraries linked to the binary

# Exemple
```
$ tree /tmp/roottest/
/tmp/roottest/
└── bin
    └── cp
```

```
$ bash lddcopy.sh /tmp/roottest/bin/cp /tmp/roottest/
[+] checking /tmp/roottest/bin/cp dependencies
[+] copying libresolv dependencies
[+] copying libacl.so.1
[+] copying libattr.so.1
[+] copying libc.so.6
```

```
$ tree /tmp/roottest/
/tmp/roottest/
├── bin
│   └── cp
├── lib -> lib64
└── lib64
    ├── ld-linux-x86-64.so.2
    ├── libacl.so.1
    ├── libattr.so.1
    ├── libc.so.6
    ├── libnsl-2.23.so
    ├── libnsl.so.1 -> libnsl-2.23.so
    ├── libnss_compat-2.23.so
    ├── libnss_compat.so.2 -> libnss_compat-2.23.so
    ├── libnss_dns-2.23.so
    ├── libnss_dns.so.2 -> libnss_dns-2.23.so
    ├── libnss_files-2.23.so
    ├── libnss_files.so.2 -> libnss_files-2.23.so
    ├── libresolv-2.23.so
    └── libresolv.so.2
```

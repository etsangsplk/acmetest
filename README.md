# acmetest
Unit test project for **acme.sh** project https://github.com/acmesh-official/acme.sh



# Here are the latest status:

| Platform | Status| Last Run Time| Comments|
-----------|-------|--------------|---------|
|freebsd| ![](https://acmesh-official.github.io/acmetest/status/freebsd.svg?1591902127)| Thu, 11 Jun 2020 19:02:07 UTC| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/freebsd.out) |
|openbsd| ![](https://acmesh-official.github.io/acmetest/status/openbsd.svg?1591931243)| Fri, 12 Jun 2020 03:07:23 UTC| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/openbsd.out) |
|pfsense| ![](https://acmesh-official.github.io/acmetest/status/pfsense.svg?1591931517)| Fri, 12 Jun 2020 03:11:57 UTC| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/pfsense.out) |
|solaris| ![](https://acmesh-official.github.io/acmetest/status/solaris.svg?1583464630)| Fri, 06 Mar 2020 03:17:10 GMT| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/solaris.out) |
|windows-cygwin| ![](https://acmesh-official.github.io/acmetest/status/windows-cygwin.svg?1591932426)| Fri, 12 Jun 2020 03:27:06 UTC| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/windows-cygwin.out) |
|ubuntu:latest| ![](https://acmesh-official.github.io/acmetest/status/ubuntu-latest.svg?1591932644)| Fri, 12 Jun 2020 03:30:44 UTC| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/ubuntu-latest.out) |
|debian:latest| ![](https://acmesh-official.github.io/acmetest/status/debian-latest.svg?1591932844)| Fri, 12 Jun 2020 03:34:04 UTC| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/debian-latest.out) |
|centos:latest| ![](https://acmesh-official.github.io/acmetest/status/centos-latest.svg?1591933059)| Fri, 12 Jun 2020 03:37:39 UTC| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/centos-latest.out) |
|fedora:latest| ![](https://acmesh-official.github.io/acmetest/status/fedora-latest.svg?1591933272)| Fri, 12 Jun 2020 03:41:12 UTC| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/fedora-latest.out) |
|opensuse/leap| ![](https://acmesh-official.github.io/acmetest/status/opensuse-leap.svg?1591935683)| Fri, 12 Jun 2020 04:21:23 UTC| [Failed](https://github.com/acmesh-official/acmetest/blob/master/logs/opensuse-leap.out) |
|alpine:latest| ![](https://acmesh-official.github.io/acmetest/status/alpine-latest.svg?1591936008)| Fri, 12 Jun 2020 04:26:48 UTC| [Failed](https://github.com/acmesh-official/acmetest/blob/master/logs/alpine-latest.out) |
|oraclelinux:latest| ![](https://acmesh-official.github.io/acmetest/status/oraclelinux-latest.svg?1591933814)| Fri, 12 Jun 2020 03:50:14 UTC| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/oraclelinux-latest.out) |
|kalilinux/kali| ![](https://acmesh-official.github.io/acmetest/status/kalilinux-kali.svg?1591934010)| Fri, 12 Jun 2020 03:53:30 UTC| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/kalilinux-kali.out) |
|archlinux:latest| ![](https://acmesh-official.github.io/acmetest/status/archlinux-latest.svg?1591936028)| Fri, 12 Jun 2020 04:27:08 UTC| [Failed](https://github.com/acmesh-official/acmetest/blob/master/logs/archlinux-latest.out) |
|mageia| ![](https://acmesh-official.github.io/acmetest/status/mageia.svg?1591934237)| Fri, 12 Jun 2020 03:57:17 UTC| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/mageia.out) |
|gentoo/stage3-amd64| ![](https://acmesh-official.github.io/acmetest/status/gentoo-stage3-amd64.svg?1591937318)| Fri, 12 Jun 2020 04:48:38 UTC| [Failed](https://github.com/acmesh-official/acmetest/blob/master/logs/gentoo-stage3-amd64.out) |
|clearlinux:latest| ![](https://acmesh-official.github.io/acmetest/status/clearlinux-latest.svg?1591935665)| Fri, 12 Jun 2020 04:21:05 UTC| [Passed](https://github.com/acmesh-official/acmetest/blob/master/logs/clearlinux-latest.out) |

# How to run tests

First point at least 2 of your domains to your machine, 
for example: `aa.com` and `www.aa.com`

And make sure 80 port is not used by anyone else.

```
cd acmetest
TestingDomain=aa.com   TestingAltDomains=www.aa.com  ./letest.sh
```

# How to run tests in all the platforms through docker.

You must have docker installed, and also point 2 of your domains to your machine.

Then test all the platforms :

```
cd acmetest
TestingDomain=aa.com   TestingAltDomains=www.aa.com  ./rundocker.sh  testall
```

The script will download all the supported platforms from the official docker hub, then run the test cases in all the supported platforms.

Then test single docker platform :

```
cd acmetest
TestingDomain=aa.com   TestingAltDomains=www.aa.com  ./rundocker.sh  testplat   centos:latest
```

# Run tests with ngrok automatically

If you don't want to use 2 domains to test, we can use ngrok to test with temp domain.

Please register an free account at https://ngrok.com/

You will get your ngrok auth token.  Then:

```
export NGROK_TOKEN="xxxxxxxxxx"

./letest.sh

```









Prasyart:
- Ubah Line property DNSStubListener=no
```shell
$ sudo nano /etc/systemd/resolve.conf
```
- Jalankan Container

```shell
$ docker-compose up -d
```
- Masuk kedalam container 
```shell
$ docker exec -it -u root dns-demo bash
```
- Install dnsutils packages
```shell
$ apt install dnsutils
```
- Testing Domain
```shell
$ nslookup demo.jamkrind.id
```
```shell
$ nslookup srv-prod-1.demo.jamkrind.id
```

```shell
$ nslookup srv-prod-2.demo.jamkrind.id
```

```shell
$ nslookup srv-demo-2.demo.jamkrind.id
```

```shell
$ nslookup tes.srv-demo-2.demo.jamkrind.id
```
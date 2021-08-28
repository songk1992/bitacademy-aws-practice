## [AWS Practice](../readme.md) - 03.

## ch06. 가상화와 EC2

1. Hypervisor type1(HVM, PVM), type2
2. AMI
3. Instance

## ch07. 가상 서버 시작

1. EC2 Instance 생성
2. 가상 서버 시작

## ch08. 가상 서버 운영

1. ssh. 가상 서버 접속

```bash
$ ssh -i mykey.pem ec2-user@[public ip]
```

2. 가상 서버 모니터링
3. 가상 서버 상태 변경
4. 가상 서버 크기 변경

## ch09. 네트워크 설정

1. Security Group 방화벽 : 아파치 웹서버 운영

```bash
    # yum install -y http
    # systemctl enable httpd
    # service httpd [start|stop|restart]
```

2. Elastic IP(고정 IP)

3.

4.

<br />

## 실습(네트워크 두개 붙이기)

```
아이피 두개를 맵핑해서 인스턴스 접근해보기
네트워크 인터페이스를 만들어서 인터페이스에 연결 후

탄력적 IP (고정 IP) 를 만들어서 인스턴스에 연결한다.
(탄력IP는 만들고 연결 안하면 돈든다.)

작업 -> 탄력적 IP 주소 연결 -> 네트워크 인터페이스
```

## 실습(네트워크에 http 파일 올려서 보기)

```
cd /var/www/html
pwd
ls
vi index.html

mkdir mysite01
cd mysite01
vi index.html
// 여기다가 html 파일 작성
:wq
cat index.html

cd /etc/httpd/conf.d
vi mysite01.conf
<VirtualHost 172.31.12.90:80>
    DocumentRoot /var/www/html/mysite01
</VirtualHost>
:wq


service httpd stop
ps -ef | grep htpd
service httpd start
```

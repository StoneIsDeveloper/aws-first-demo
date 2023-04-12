# aws-first-demo

### c9 cmd
```
curl http://169.254.169.254/latest/meta-data
````
### Get ipv4
```
curl http://169.254.169.254/latest/meta-data/public-ipv4
```
### Set security group

```
curl http://169.254.169.254/latest/meta-data/instance-id

curl http://169.254.169.254/latest/meta-data/mac

curl http://169.254.169.254/latest/meta-data/network/interfaces
curl http://169.254.169.254/latest/meta-data/network/interfaces/macs
curl http://169.254.169.254/latest/meta-data/network/interfaces/macs/0e:7d:66:8c:4e:11
curl http://169.254.169.254/latest/meta-data/network/interfaces/macs/0e:7d:66:8c:4e:11/security-group-ids

```

### Add my IP into security
```
--Add IP into security
--MY IP 104.28.211.105
aws ec2 authorize-security-group-ingress --group-id sg-01bf4cff67013759f --port 8080 --protocol tcp --cidr 104.28.211.105/32
```


### Open port 8080
```
aws ec2 describe-security-groups --group-ids sg-01bf4cff67013759f --output text --filters Name=ip-permission.to-port,Values=8080
```

### Run page
```
PORT=8080; npm start

curl http://169.254.169.254/latest/meta-data/public-ipv4
54.204.155.164

test url: 54.204.155.164:8080
```



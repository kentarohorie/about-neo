Amazon Linux AMI release 2018.03

### Initially

```

sudo yum install -y git gcc-c++ openssl-devel

```

### Install docker

```
sudo yum -y install docker

sudo service docker start

sudo usermod -a -G docker ec2-user

# and re-login
```

### Install python

```
sudo yum install -y python36 python36-devel

python3 -m venv venv

source venv/bin/activate
```

### Setup neo privatenet blockchain

```
docker pull cityofzion/neo-privatenet
```

### Setup np-prompt

```
pip install --upgrade pip

pip install neo-python
```

### Download initial wallet

```
wget https://s3.amazonaws.com/neo-experiments/neo-privnet.wallet
```

### Start np-prompt

```
docker run --rm -d --name neo-privatenet -p 20333-20336:20333-20336/tcp -p 30333-30336:30333-30336/tcp cityofzion/neo-privatenet

source venv/bin/activate

np-prompt -p -v
```

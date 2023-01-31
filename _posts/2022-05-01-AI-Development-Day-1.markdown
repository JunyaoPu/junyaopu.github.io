---
layout: single
title:  "AI Dev Day 1: Setup a AWS EC2 instance for AI development"
date:   2022-05-01 00:43:00 -0500
categories: AI
collection: AI
classes: wide
header:
    teaser: /assets/images/ai_day1/post_ai_aws.jpg
---

# Motivation  
I previously used local machines or university servers for AI development. Upon joining my first job, the company moved everything to the cloud, including my AI work. I learned to use AWS Sagemaker, EC2, and S3 bucket for our AI pipeline. We initially used Sagemaker, but found it expensive and restrictive with hardware limitations and limited space. Thus, we switched to EC2, a more cost-effective and flexible cloud remote server.

I created a pipeline that creates a simple EC2 instance and sets up an AI development environment with NVIDIA GPU driver, Docker, PyTorch, and Jupyter notebook. This makes it quick and easy to establish a cloud machine for AI work.

# The pipeline

## AWS recommended GPU Instances
G3 - Nvidia Tesla M60 GPU only 8 Gb memory - from 0.75/h

G4 - (G4dn) Nvidia T4 GPU with 16 Gb memory - from 0.526/h

G5 - Nvidia A10G GPU with 24 Gb memory - from 1.006/h - 3X faster than G4

G5g - Nvidia T4G GPU with 16 Gb memory

P3 - V100 with 32 Gb - from 3.06/h

p4 - A100 with 40 Gb - from 32.77/h

<a href="https://docs.aws.amazon.com/dlami/latest/devguide/gpu.html">Recommended GPU Instances for AWS EC2</a>

## Setting up on EC2
1 Launch instance

2 Pick "Ubuntu Server 20.04 LTS (HVM), SSD Volume Type"

3 On "Review Instance Launch" ->"Storage"->Change the "Root" storage (≥20 Gb)

4 Pick "g4dn.xlarge" 

5 Launch instance with a .pem key, save the .pem key for ssh

### First time access the EC2 instance

```bash
chmod 600 ./AWS_EC2_ML.pem
```
```bash
ssh -L 8000:localhost:8000 -i AWS_EC2_ML.pem ubuntu@EC2_Public_IPv4_address
```

## Install Nvidia driver

```bash
apt search nvidia-driver
sudo apt update
sudo apt upgrade
sudo apt install nvidia-driver-510
sudo reboot
```

### Check the GPU information
```bash
nvidia-smi
```
# Install Nvidia-Docker
```bash
curl https://get.docker.com | sh \
  && sudo systemctl --now enable docker
```

```bash
distribution=$(. /etc/os-release;echo $ID$VERSION_ID) \
      && curl -fsSL https://nvidia.github.io/libnvidia-container/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg \
      && curl -s -L https://nvidia.github.io/libnvidia-container/$distribution/libnvidia-container.list | \
            sed 's#deb https://#deb [signed-by=/usr/share/keyrings/nvidia-container-toolkit-keyring.gpg] https://#g' | \
            sudo tee /etc/apt/sources.list.d/nvidia-container-toolkit.list
```

```bash
sudo apt-get update
sudo apt-get install -y nvidia-docker2
```
### Check the Nvidia-Docker is installed
```bash
sudo docker run --rm --gpus all nvidia/cuda:11.6.2-base-ubuntu20.04 nvidia-smi
```
<a href="https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html">Nvidia-Docker Installation Guide</a>

### Pull Nvidia PyTorch container
```bash
sudo docker pull nvcr.io/nvidia/pytorch:21.12-py3
```
<a href="https://catalog.ngc.nvidia.com/orgs/nvidia/containers/pytorch">Nvidia-PyTorch docker images</a>

### Run the Docker container
```bash
sudo docker run --shm-size=10240m -it -p 8000:8000 --gpus all -v /home/ubuntu/my_code:/workspace nvcr.io/nvidia/pytorch:21.12-py3
```

### Run the Jupyter notebook inside the Docker container
```bash
jupyter notebook --no-browser --port=8000
```

Open the jupyter notebook UI on your local browser with link
http://localhost:8000/

# Achievements
After reading this post

* You should be able to create an AWS EC2 instance with NVIDIA GPUs.
* Run a Docker container with enabled NVIDIA GPUs, PyTorch, and Jupyter notebook installed.
* Start your AI development in the Jupyter notebook on your local browser.

# What's next
"Configure an AWS S3 bucket in conjunction with the EC2 instance to efficiently transfer files/datasets using AWS S3 instead of SSH.

## Let's Goooooooooooooooooo

**What's Edge computing:** Edge computing brings computation and data storage closer to the location where it is needed, reducing latency and bandwidth use. It involves processing data at or near the data source, rather than relying on a centralized cloud data center.

### Example

Imagine you're in a factory that's using Internet of Things (IoT) sensors to monitor various machines and processes. Instead of sending all the sensor data to a centralized server for analysis (which is what cloud computing is), edge computing allows the sensors to process data locally. This means they can detect anomalies, predict maintenance needs, and optimize processes right at the source. By doing so, edge computing reduces latency, conserves bandwidth, and enables real-time insights, improving overall efficiency and reducing downtime in the factory.

### This is the arcitechture of KubeEdge
![under1](https://github.com/1Shubham7/understanding-KubeEdge/assets/116020663/1e52665f-db37-45b4-bed9-1c54b8b4472f)

## this really help to answer "why edge?"
![image](https://github.com/1Shubham7/understanding-KubeEdge/assets/116020663/39e25b75-0482-4bac-b845-3e46fa7b77ac)

>> The computing side is handelled by Edge while the cloud (Orchestration) part is handelled by Kubernetes.
![image](https://github.com/1Shubham7/understanding-KubeEdge/assets/116020663/e674c901-a0bd-47fb-870d-155ac9e3074e)

>> Basic framework
![image](https://github.com/1Shubham7/understanding-KubeEdge/assets/116020663/0edc65b1-8b03-4cda-be43-bee42557a9bd)

![image](https://github.com/1Shubham7/understanding-KubeEdge/assets/116020663/aa64dece-84f9-47bd-84f5-283950b5e72f)




## Tutorial


Then >>

Step 1. You must have Docker, Kubernetes, Kind, kubectl, create a cluster


Step 2. donwload Keadm - this is the install tool to install KubeEdge
```
wget https://github.com/kubeedge/kubeedge/releases/download/v1.12.1/keadm-v1.12.1-linux-amd64.tar.gz
```
```
tar -zxvf keadm-v1.12.1-linux-amd64.tar.gz
```
```
sudo cp keadm-v1.12.1-linux-amd64/keadm/keadm /usr/local/bin/keadm
```

Step 3. Or what I did was I simply build it form source:

```shell
git clone https://github.com/kubeedge/kubeedge.git
cd kubeedge
make
```

Step 4. you will have the tools inside _output/local/bin. I  then did this:

`./cloudcore --defaultconfig > cloudcore.yaml`

Step 7. Using keadm command to install the Cloudcore/ Deploy cloudcore on Master Node

```
keadm deprecated init --advertise-address="80.158.90.193" --kubeedge-version=1.12.1 --kube-config=/root/.kube/config
```

> "80.158.90.193" - that is the cloudcore IP of your cloudcore, you will need a cloudcore for that.

Then enter y

Step 8. Check if cloudcore is running successfull   //misspell found in docs

```
sudo kubectl get all -nkubeedge
```

For this tutorial we need two VMs



Resources :
https://www.cncf.io/blog/2022/08/18/kubernetes-on-the-edge-getting-started-with-kubeedge-and-kubernetes-for-edge-computing/
https://www.youtube.com/watch?v=vzutlStNJew&t=185s&ab_channel=OpenEdgeHPCInitiative
https://kubernetes.io/blog/2019/03/19/kubeedge-k8s-based-edge-intro/


## Tip

` keadm deprecated init -h` use -h in order to know what the command does. Here "keadm deprecated init" command installs KubeEdge's master node (on the cloud) component.

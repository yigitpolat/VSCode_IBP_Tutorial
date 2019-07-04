# IBM Blockchain Platform Extension for VS Code Tutorial

This document has been prepared by Kemal Aydin (<kemal.aydin@ibm.com>) and Yigit Polat (<yigit.polat@ibm.com>), and contains a visual description of IBM Blockchain Platform Extension for VS Code and its capabilities as well as providing comprehensive content to whom demands hands-on trainings.

The IBM Blockchain Platform Visual Studio (VS) Code extension provides an enviroment to develop, test, and debug their smart contracts. Moreover, it brings ease to developers to deploy their smart contracts to preconfigured Hyperledger Fabric network on their local machines.

The screenshots in this guide were taken from an Ubuntu Virtual Machine which contains all the required tools and configurations. If you would like to follow the steps, don't hesitate to contant to document owners to get the VM image.

## Table of Contents

1. [Package a Smart Contract Project](#1.-Package-a-Smart-Contract-Project)
2. [Deploy a Local Hyperledger Fabric Network](#2.-Deploy-a-Local-Hyperledger-Fabric-Network)
3. [Install and Instantiate the Smart Contract](#3.-Install-and-Instantiate-the-Smart-Contract)
4. [Setting Up Hyperledger Fabric SDK for Node.js](#4.-Setting-Up-Hyperledger-Fabric-SDK-for-Node.js)

## 1. Package a Smart Contract Project

### 1.1

![Launch VS Code](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/1.png "Launch VS Code")

- Launch VS Code from the menu bar.

### 1.2

![Open Folder](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/2.png "Open Folder")

- Click the **Open Folder** button to add project to the workspace.

### 1.3

![Select Folder](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/3.png "Select Folder")

- Navigate to the folder given in the above screenshot and click **OK** button.

### 1.4

![Project](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/4.png "Project")

- lib/fabcar.js file is the smart contract (chaincode) that will be deployed in Hyperledger Fabric network.
- This smart contract is written in JavaScript.

### 1.5

![IBP](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/5.png "IBP")

- Navigate to the IBM Blockchain Platform panel from the sidebar.

### 1.6

![Package](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/6.png "Package")

- In the Smart Contract Packages pane, click the overflow menu and select Package a Smart Contract Project.

### 1.7

![Package](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/7.png "Package")

- See the success message from the buttom right corner and packaged smart contract under the Smart Contract Packages pane as *.cds* format.

## 2. Deploy a Local Hyperledger Fabric Network

### 2.1

![Start Fabric Runtime](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/9.png "Start Fabric Runtime")

- In the Local Fabric Ops pane, click the overflow menu and select **Start Fabric Runtime**. This will create a basic Fabric network with one orderer, one peer, and one certificate authority.

![Local Fabric OPS](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/11.png "Local Fabric OPS")

- See that Local Fabric Ops pane changes to show Smart Contracts, Channels, Nodes and Organizations.
- Double-click **local_fabric** in the Fabric Gateways pane to connect to the local network. By default, the connection uses the admin identity in the Fabric wallets pane.

![Docker](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/12.png "Docker")

- The VS Code extention uses Docker Compose to launch our various Fabric component containers behind the scenes. Open a new *Terminal* window and type the following commands to see the running Docker Containers and Docker Images that needed to run the Fabric components.

```bash
    docker ps -a
    docker images
```

## 3. Install and Instantiate the Smart Contract

## 4. Setting Up Hyperledger Fabric SDK for Node.js


## References

* [IBM Blockchain Platform Docs](https://cloud.ibm.com/docs/services/blockchain?topic=blockchain-develop-vscode)

* [VisualStudio Marketplace](https://marketplace.visualstudio.com/items?itemName=IBMBlockchain.ibm-blockchain-platform)


## License

[Apache License 2.0](./LICENSE)
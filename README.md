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

### Step 1
![install-chaincode#1](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/13.png "Install Chaincode")

- Click on the **Install** button under the **LOCAL FABRIC OPS** pane.
- You will be prompted to select which version of your chaincode is going to be installed.
  - You can have multiple version of your chaincode
  - You can upgrade or downgrade of your chaincode's version.

### Step 2
![install-chaincode#2](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/14.png "Install Chaincode")

- You will see the installed chaincode and its version under the **LOCAL FABRIC OPS** pane.
  - If you keep waiting cursor on the installed chaincode, you will see the peer(s) that contains installed chaincode.
- You will see the message that indicates process' result.
  - This could be positive message or vice versa.

### Step 3
![instantiate-chaincode#1](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/15.png "Instantiate Chaincode")

- Click on the **Instantiate** button under the **LOCAL FABRIC OPS** pane.
- You will be prompted to select which version of your chaincode is going to be instantiated.
  - If you don't have any installed chaincode, you will be prompted to select which version of your chaincode is going to be installed. After that, you will be prompted to instantiate.
  - You can have multiple version of your chaincode
  - You can upgrade or downgrade of your chaincode's version.

### Step 4
![instantiate-chaincode#2](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/16.png "Instantiate Chaincode")

- You will be prompted to select which function of your chaincode is going to be called during instantiation process.
  - This step is optional. If you want to set some initial values, you can use this function.

### Step 5
![instantiate-chaincode#3](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/17.png "Instantiate Chaincode")

- You will be prompted to specify which parameter(s) is going to be passed during instantiation process.
  - This step is optional. If you specify a function that is called during instantiation process (step 4), you can pass some arguments for that function.

### Step 6
![instantiate-chaincode#4](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/18.png "Instantiate Chaincode")

- You will be prompted to browse your collection configuration file if your smart contract uses private data.

### Step 7
![instantiate-chaincode#5](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/19.png "Instantiate Chaincode")

- You will see the instantiated chaincode and its version under the **LOCAL FABRIC OPS** pane.
  - If you keep waiting cursor on the instantiated chaincode, you will see the channel that contains instantiated chaincode.
- You will see the message that indicates process' result.
  - This could be positive message or vice versa.

### Step 8
![instantiate-chaincode#6](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/20.png "Instantiate Chaincode")

- Click on the **mychannel** button under the **FABRIC GATEWAYS** pane.
  - You will see the functions that are found in instantiated chaincode.

### Step 9
![instantiate-chaincode#7](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/21.png "Instantiate Chaincode")

- Right click on the **queryAllCars** method under the **mychannel** tab, select the **Evaluate Transaction** option.
  - **Evaluate Transaction** is used to query blockchain network, **Submit Transaction** is used to invoke blockchain network.

### Step 10
![instantiate-chaincode#8](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/22.png "Instantiate Chaincode")

- You will be prompted to specify which parameter(s) is going to be passed to the selected function.
  - Multiple parameter can be passed at once.

### Step 11
![instantiate-chaincode#9](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/23.png "Instantiate Chaincode")

- You will be prompted to specify transient data for the transaction.

### Step 12
![instantiate-chaincode#10](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/24.png "Instantiate Chaincode")

- You will see the result in **OUTPUT** tab.
  - The results are set during instantiation process in step 4.

### Step 13
![instantiate-chaincode#11](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/25.png "Instantiate Chaincode")

- Right click on the **queryCar** method under the **mychannel** tab, select the **Evaluate Transaction** option.

### Step 14
![instantiate-chaincode#12](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/26.png "Instantiate Chaincode")

- You will be prompted to specify which parameter(s) is going to be passed to the selected function.

### Step 15
![instantiate-chaincode#13](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/27.png "Instantiate Chaincode")

- You will be prompted to specify transient data for the transaction.

### Step 16
![instantiate-chaincode#14](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/28.png "Instantiate Chaincode")

- You will see the result in **OUTPUT** tab.

### Step 17
![instantiate-chaincode#15](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/29.png "Instantiate Chaincode")

- Right click on the **changeCarOwner** method under the **mychannel** tab, select the **Submit Transaction** option.

### Step 18
![instantiate-chaincode#16](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/30.png "Instantiate Chaincode")

- You will be prompted to specify which parameter(s) is going to be passed to the selected function.

### Step 19
![instantiate-chaincode#17](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/31.png "Instantiate Chaincode")

- You will be prompted to specify transient data for the transaction.

### Step 20
![instantiate-chaincode#18](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/32.png "Instantiate Chaincode")

- You will see the result in **OUTPUT** tab.

### Step 21
![instantiate-chaincode#19](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/33.png "Instantiate Chaincode")

- Right click on the **queryCar** method under the **mychannel** tab, select the **Evaluate Transaction** option.

### Step 22
![instantiate-chaincode#20](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/34.png "Instantiate Chaincode")

- You will be prompted to specify which parameter(s) is going to be passed to the selected function.

### Step 23
![instantiate-chaincode#21](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/35.png "Instantiate Chaincode")

- You will be prompted to specify transient data for the transaction.

### Step 24
![instantiate-chaincode#22](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/36.png "Instantiate Chaincode")

- You will see the result in **OUTPUT** tab.

## 4. Setting Up Hyperledger Fabric SDK for Node.js

### Step 1
![hyperledger-fabric-sdk#1](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/37.png "Hyperledger Fabric SDK")

- Right click on the **peer0.org1.example.com**  under the **Nodes** tab, select the **Export Connection Profile** option.

### Step 2
![hyperledger-fabric-sdk#2](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/38.png "Hyperledger Fabric SDK")

- Choose the right path, entitle the file as **local_fabric_connection.json** and click on the **Export** button.

### Step 3
![hyperledger-fabric-sdk#3](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/39.png "Hyperledger Fabric SDK")

- Clink on the **Close Folder** button.

### Step 4
![hyperledger-fabric-sdk#4](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/40.png "Hyperledger Fabric SDK")

- Clink on the **Open Folder** button.

### Step 5
![hyperledger-fabric-sdk#5](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/41.png "Hyperledger Fabric SDK")

- Choose the right path and click on the **OK** button.

### Step 6
![hyperledger-fabric-sdk#6](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/42.png "Hyperledger Fabric SDK")

- Click on the **local_fabric_connection.json** file on the left pane.

### Step 7
![hyperledger-fabric-sdk#7](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/43.png "Hyperledger Fabric SDK")

- Click on the **Terminal** and open a new terminal by clicking on **New Terminal** button.

### Step 8
![hyperledger-fabric-sdk#8](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/44.png "Hyperledger Fabric SDK")

- Click on the **enrollAdmin.js** file on the left pane.
- Ensure that present/current working directory is **~/Desktop/fabcar/javascript**.
- Type **"node enrollAdmin.js"**. You will see the result in **TERMINAL** tab.

### Step 9
![hyperledger-fabric-sdk#9](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/45.png "Hyperledger Fabric SDK")

- Click on the **registerUser.js** file on the left pane.
- Ensure that present/current working directory is **~/Desktop/fabcar/javascript**.
- Type **"node registerUser.js"**. You will see the result in **TERMINAL** tab.
  - You will see the credentials for **admin** and **user1** in the **wallet** directory on the left pane.

### Step 10
![hyperledger-fabric-sdk#10](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/46.png "Hyperledger Fabric SDK")

- Click on the **invoke.js** file on the left pane.
- Ensure that present/current working directory is **~/Desktop/fabcar/javascript**.
- Type **"node invoke.js"**. You will see the result in **TERMINAL** tab.

### Step 11
![hyperledger-fabric-sdk#11](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/47.png "Hyperledger Fabric SDK")

- Click on the **query.js** file on the left pane.
- Ensure that present/current working directory is **~/Desktop/fabcar/javascript**.
- Type **"node query.js"**. You will see the result in **TERMINAL** tab.

### Step 12
![hyperledger-fabric-sdk#12](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/48.png "Hyperledger Fabric SDK")

- Click on the **IBM Blockchain Platform Extension** on the left pane.
- Click on the triple dot and select **Teawdown Fabric Runtime** option.

### Step 13
![hyperledger-fabric-sdk#13](https://raw.githubusercontent.com/yigitpolat/VSCode_IBP_Tutorial/master/screenshots/49.png "Hyperledger Fabric SDK")

- Click on the **Yes** button on the message window.


## References

* [IBM Blockchain Platform Docs](https://cloud.ibm.com/docs/services/blockchain?topic=blockchain-develop-vscode)

* [VisualStudio Marketplace](https://marketplace.visualstudio.com/items?itemName=IBMBlockchain.ibm-blockchain-platform)


## License

[Apache License 2.0](./LICENSE)
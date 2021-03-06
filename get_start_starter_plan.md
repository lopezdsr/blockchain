---

copyright:
  years: 2017, 2020
lastupdated: "2020-01-15"

keywords: blockchain network, Starter Plan, getting started tutorial

subcollection: blockchain

---

{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:deprecated: .deprecated}
{:important: .important}
{:tip: .tip}
{:gif: data-image-type='gif'}

# Getting started with Starter Plan
{: #getting-started-with-starter-plan}

{{site.data.keyword.blockchainfull}} Platform Starter Plan offers you a pre-configured blockchain network with a single click. It provisions a permissioned network with the configuration of two [organizations](/docs/blockchain?topic=blockchain-glossary#glossary-organization), one [peer](/docs/blockchain?topic=blockchain-glossary#glossary-peer) per each organization, and one [channel](/docs/blockchain?topic=blockchain-glossary#glossary-channel) by default. After the network is created, you can scale and add more organizations and peers to your network. These networks are intended for novice users who are new to the {{site.data.keyword.blockchainfull_notm}} Platform.
{:shortdesc}

Starter Plan is now deprecated, therefore no new Starter Plan networks can be created at this time.** Make use of the latest user interface and features available now in the second generation of blockchain technology by visiting [{{site.data.keyword.blockchainfull_notm}} Platform for {{site.data.keyword.cloud_notm}}](/docs/blockchain?topic=blockchain-ibp-v2-deploy-iks).
{: deprecated}  

**Your existing networks are not affected and you can continue to use them until June 4, 2020.

Starter Plan enables you to learn and develop skills with {{site.data.keyword.blockchainfull_notm}} Platform, run sample applications, test your own applications, and simulate a multi-organization scenario. This getting started tutorial will guide you through how to use Starter Plan to start developing and transacting on a blockchain network.

If you are new to {{site.data.keyword.blockchainfull_notm}} Platform and blockchain, you can learn more about blockchain by reviewing the [overview of fundamental components](/docs/blockchain?topic=blockchain-blockchain-component-overview#blockchain-component-overview) of networks that are built based on the open-source [Hyperledger Fabric](/docs/blockchain/reference?topic=blockchain-hyperledger-fabric#hyperledger-fabric). You can also review the [Hyperledger Fabric documentation](https://hyperledger-fabric.readthedocs.io/en/release-1.2/blockchain.html){: external}.

## Overview
{: #getting-started-with-starter-plan-overview}

**Build your consortium**

The first step toward building with blockchain is to form the consortium of organizations that wish to use blockchain to transact, and invite them to your network. Starter Plan users who are experimenting with the technology can simulate a multi-organization consortium by creating new organizations themselves.

- [Create a Starter Plan network](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-creating-a-network)
- [Invite organizations to your network](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-inviting-members)
- [Joining a Starter Plan network](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-joining-a-network)

Within the consortium of organizations that have joined your networks, you can transact privately with sets of those organizations by creating channels.

- [Create channels](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-create-channels)

**Develop your network and applications**

After you form your consortium, you need to write the chaincode, also known as smart contracts, that will contain the business logic of your network and allow you to interact with data on the blockchain ledger. You will then need to use the Fabric SDKs  along with those smart contracts to submit transactions to your network from your client side application.

- [Developing Chaincode](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-develop-chaincode)

**Operate and govern your network**

{{site.data.keyword.blockchainfull_notm}} Platform provides tooling and APIs that you can use the manage the membership, lifecycle, and health of your blockchain network. Many of these capabilities are accessible through the Network Monitor user interface.

- [Monitoring network resources](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-monitoring-resources)
- [Retrieving network credentials and connection profile](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-retrieving-network-credentials)
- [Managing your network by using Swagger APIs](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-swagger)
- [Resetting a network](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-resetting-network)
- [Migrating from Starter Plan to Enterprise Plan](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-migrate)
- [Deleting or leaving a network](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-delete-network)


## Creating a network
{: #getting-started-with-starter-plan-creating-a-network}

You can get a Starter Plan [network](/docs/blockchain?topic=blockchain-glossary#glossary-network) with the default configuration immediately after you create an {{site.data.keyword.blockchainfull_notm}} Platform service instance.

1. Locate the [Blockchain service](https://cloud.ibm.com/catalog/services/ibm-blockchain-5-prod){: external} in {{site.data.keyword.cloud_notm}} Catalog.
    **Note**: You need to log in with your {{site.data.keyword.cloud_notm}} paid account. If you do not have an account, click the **Sign up to Create** button. After you create a free trial account, upgrade it to a **Pay-As-You-Go** type by going to **Manage** > **Billing and Usage** > **Billing** in the {{site.data.keyword.cloud_notm}} console, and clicking **Add Credit Card**.
2. Choose the region in {{site.data.keyword.cloud_notm}} to create the network.
3. Select your Cloud Foundry organization and space to create the network.
4. Choose **Starter Membership Plan** from the pricing plans table.
5. Click the **Create** button. Note that if you are invited to join a network, you can see a pop-up welcome panel. To create a network, choose **Proceed to your network** and click **Continue**. To join a network, see step 5 in [Joining a network](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-joining-a-network).
  Now you're ready to use your Starter Plan network with the default configuration. The network is running with one orderer (known as a "SOLO" ordering service), two organizations, one CA, and one peer per each organization. A default channel is also created.
6. Click the **Launch** button.

You can find your blockchain service instance in your [{{site.data.keyword.cloud_notm}} service dashboard](https://cloud.ibm.com/resources){: external}.


## Inviting members
{: #getting-started-with-starter-plan-inviting-members}

You can invite other [organizations](/docs/blockchain?topic=blockchain-glossary#glossary-organization) to join your Starter Plan network as [members](/docs/blockchain?topic=blockchain-glossary#glossary-member) so that you can perform [transactions](/docs/blockchain?topic=blockchain-glossary#glossary-transaction) with each other. In addition, if you want to use Starter Plan for learning and testing purposes, you can simulate a multi-organization network by adding members for yourself to the network.

1. On the "Members" screen of your Network Monitor, click the **Invite Members** button.
2. The "Invite member" window opens.
    - If you want to invite another organization, choose "Invite a member".  Specify the name and operator email address of the organization that you want to invite.  You can also enter additional information that you want to include in your invitation in the "Add a note" field.  Click the **Send invite** button.  The invited organization will receive an invitation email and can then follow the instructions in the email to join your network.
    - If you want to add additional organizations that can be added to a channel, choose "Add a member".  Specify a name for your new organization. You can optionally add peers to your new organization or do it later in the Network Monitor.  Click the **Create** button. Note that if you add peers for your new organization, you need to switch to this new organization to see your peers. You can switch to another organization by clicking the upper right corner and select the target organization from the drop-down list under the **SWITCH ORGANIZATION** section.


## Joining a network
{: #getting-started-with-starter-plan-joining-a-network}

If you are invited by a network initiator, you will receive an email notification with instructions on how to join the network. Follow the instructions in the email, and you will become one of the members in the network.

You need to create an [{{site.data.keyword.blockchainfull_notm}} Platform service instance](https://cloud.ibm.com/catalog/services/ibm-blockchain-5-prod){: external} with Starter Plan membership option in {{site.data.keyword.cloud_notm}}.

1. Log in with your {{site.data.keyword.cloud_notm}} account. If you do not have an account, click the **Sign up to Create** button.
2. Select the Cloud Foundry organization where you want to store your {{site.data.keyword.blockchain}} network.
3. Select **Starter Membership Plan** from the pricing plans table.
4. Click the **Create** button. The service instance page opens with a pop-up welcome panel. Note that you can choose to join a network or continue to create your own one. To create a network, see step 4 in [Creating a network](/docs/blockchain?topic=blockchain-getting-started-with-starter-plan#getting-started-with-starter-plan-creating-a-network).
5. On the welcome panel, choose **Join existing network**, select the network to join from the drop-down list, and click **Continue**.

You can find your blockchain service instance in the [{{site.data.keyword.cloud_notm}} service dashboard](https://cloud.ibm.com/resources){: external}.

## Create channels
{: #getting-started-with-starter-plan-create-channels}

Channels are used by sets of organizations to transact without exposing the data to other organizations. You can create a [channel](/docs/blockchain?topic=blockchain-glossary#glossary-channel) with select members of your starter plan network, and policies on who can update the channel.

For more information, see [Creating a channel](/docs/blockchain?topic=blockchain-ibp-create-channel#ibp-create-channel-creating-a-channel). If another organization invites you to a channel, you will also find instructions on how to accept the invitation and join your peers to the channel.

## Developing Chaincode
{: #getting-started-with-starter-plan-develop-chaincode}

[chaincode](/docs/blockchain?topic=blockchain-glossary#glossary-chaincode), sometimes referred to as smart contracts, is software that allows you to read and update data on the blockchain ledger. Chaincode can turn business logic into an executable program agreed to and verified by all members of the blockchain network.

For more information, see the [developing chaincode](/docs/blockchain?topic=blockchain-develop-smart-contracts#develop-smart-contracts) tutorial to learn how to start writing chaincode, as well as fabric features that are accessible through chaincode.

## Installing and instantiating your chaincode
{: #getting-started-with-starter-plan-install-instantiate-chaincode}
After joining channels and developing your business logic, you need to install chaincode on the peers in the network. You can use the Network Monitor to install and instantiate chaincode on the peers of your organization, as well as update the chaincode to facilitate continuous development.

For more information about installing and instantiating your chaincode, see [Installing, instantiating, and updating a chaincode](/docs/blockchain?topic=blockchain-install-instantiate-chaincode#install-instantiate-chaincode).


## Monitoring network resources
{: #getting-started-with-starter-plan-monitoring-resources}

If your application requests a transaction, you can view transaction status information in the Network Monitor. For more information about network monitoring, see [Monitoring a network](/docs/blockchain?topic=blockchain-monitor-blockchain-network#monitor-blockchain-network).


## Retrieving network credentials and connection profile
{: #getting-started-with-starter-plan-retrieving-network-credentials}

After you create a Starter Plan network in {{site.data.keyword.cloud_notm}}, you can retrieve the network credentials and connection profile from the service instance page or in the Network Monitor.

### Retrieving from the service instance page
{: #getting-started-with-starter-plan-retrieve-service-instance}

You are on the service instance page right after you create a service instance. You can also click your service in the [{{site.data.keyword.cloud_notm}} service dashboard](https://cloud.ibm.com/resources){: external} to open your service instance page.

Retrieve your service credentials with the following steps:
1. On the service instance page, click **Service credentials** in the left navigator to show the "Service credentials" screen.
2. Click **New credential** in the "Service credentials" screen.
3. In the "Add new credential" screen, give the credential a name and enter **{"type": "service_instance_token"}** in the "Add inline configuration parameter" field. Click **Add**. The new credential is added in the table. You can click **View credentials** under the "ACTIONS" column to view the credential details. This credential contains the API key and secret, which you can use to authorize APIs.

![Retrieving network credentials](images/service_credentials.gif "Retrieving network credentials"){: gif}

### Retrieving in the Network Monitor
{: #getting-started-with-starter-plan-network-creds}

You can find the network credentials on the "APIs" screen in your Network Monitor. For more information about using APIs, see [Interacting with the network using Swagger APIs](/docs/blockchain?topic=blockchain-ibp-swagger#ibp-swagger).

You can retrieve the connection profile on the "Overview" screen in your Network Monitor. Click the **Connection Profile** button on the "Overview" screen and the connection profile shows in a new page.

## Managing your network by using Swagger APIs
{: #getting-started-with-starter-plan-swagger}

{{site.data.keyword.blockchainfull_notm}} Platform exposes a number of REST APIs in Swagger that you can use to manage the nodes, channels, peers, and members of your network. Your applications can use these APIs to control important network resources without using the Network Monitor.

To learn more, see [Interacting with the network using Swagger APIs](/docs/blockchain?topic=blockchain-ibp-swagger#ibp-swagger)

## Resetting a network
{: #getting-started-with-starter-plan-reset-nw}

If you want to clean your customized configurations, running chaincode, or deployed applications, you can set your network back to the initial default configuration. For more information, see [Reset network](/docs/blockchain?topic=blockchain-ibp-dashboard#ibp-dashboard-reset-network).


## Migrating from Starter Plan to Enterprise Plan
{: #getting-started-with-starter-plan-migrate}

You can deploy chaincode and applications that you test against a Starter Plan network into an Enterprise Plan network. To deploy a chaincode that you test against a Starter Plan network into Enterprise, follow the instructions in [Installing, instantiating, and updating a chaincode](/docs/blockchain?topic=blockchain-install-instantiate-chaincode#install-instantiate-chaincode-install-cc).

Only chaincode and applications can be migrated, data cannot be migrated between Starter and Enterprise Plan networks.

## Deleting or leaving a network
{: #getting-started-with-starter-plan-delete-network}

If you want to delete or leave a network, you can delete the blockchain service instance from your {{site.data.keyword.cloud_notm}} dashboard.

Before you leave a network, ensure that you are not a member of any channels on the network. Otherwise, you will get errors when you leave the network. A channel member can remove you from the channel using the channel update process. For more information about the channel update process, see [Updating a channel](/docs/blockchain?topic=blockchain-ibp-create-channel#ibp-create-channel-updating-a-channel).{:note}

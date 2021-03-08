# Features and Design

The [Akash](https://github.com/ovrclk/akash) DeCloud is comprised of two main components:

1. The **Network**: an on-chain decentralized \[marketplace\] \(DEX\) for leasing computing resources.
2. The **Platform**: an off-chain deployment platform used for hosting and managing workloads.

The **Network** is built with [cosmos-sdk](https://github.com/cosmos/cosmos-sdk) - it is a [tendermint](https://github.com/tendermint/tendermint)-based blockchain application.

The **Platform** is a set of [cloud management services](design.md#provider-services) that leverage [Kubernetes](https://kubernetes.io) to run workloads.

The software to run the **Network**, the **Platform**, and the command-line client used to interact with them are all currently distributed in the `akash` application.

## Workflow - Life of a Deployment

Deploying applications onto [Akash](https://github.com/ovrclk/akash) involves two types of users:

1. The **Tenant**: the entity that deploys the application.
2. The **Provider**: the entity that hosts the application.

Given that there are live providers on the network, the lifecycle of a typical application deployment is as follows:

1. The tenant describes their desired deployment in \[SDL\], called a [deployment](https://github.com/ovrclk/docs/tree/e639d67bcaeb4d8965a40621c0236710bfc79c5b/marketplace.md#deployment).
2. The tenant submits that definition to the blockchain.
3. Their submission generates an [order](https://github.com/ovrclk/docs/tree/e639d67bcaeb4d8965a40621c0236710bfc79c5b/marketplace.md#order) on the \[marketplace\].
4. Providers that would like to fulfill that [order](https://github.com/ovrclk/docs/tree/e639d67bcaeb4d8965a40621c0236710bfc79c5b/marketplace.md#bid) on it.
5. After some period of time, a winning [bid](https://github.com/ovrclk/docs/tree/e639d67bcaeb4d8965a40621c0236710bfc79c5b/marketplace.md#bid) for the [order](https://github.com/ovrclk/docs/tree/e639d67bcaeb4d8965a40621c0236710bfc79c5b/marketplace.md#order) is chosen, and a [lease](https://github.com/ovrclk/docs/tree/e639d67bcaeb4d8965a40621c0236710bfc79c5b/marketplace.md#lease) is created.
6. Once a [lease](https://github.com/ovrclk/docs/tree/e639d67bcaeb4d8965a40621c0236710bfc79c5b/marketplace.md#lease) has been created, the tenant submits a [manifest](https://github.com/ovrclk/docs/tree/e639d67bcaeb4d8965a40621c0236710bfc79c5b/provider-services.md#manifest) to the provider.
7. The provider executes workloads as instructed by the [manifest](https://github.com/ovrclk/docs/tree/e639d67bcaeb4d8965a40621c0236710bfc79c5b/provider-services.md#manifest).
8. The workload is running - if it is a web application it can be visited, etc...
9. The provider or tenant eventually closes the [lease](https://github.com/ovrclk/docs/tree/e639d67bcaeb4d8965a40621c0236710bfc79c5b/marketplace.md#lease), shutting down the workload.


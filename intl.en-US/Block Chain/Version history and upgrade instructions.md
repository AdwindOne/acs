# Version history and upgrade instructions {#concept_sxg_npt_vdb .concept}

This document records the version history and the corresponding function changes of the Alibaba Cloud Container Service blockchain solution, and the instructions when you upgrade the blockchain solution. The version number is the chart version of the blockchain solution ack-hyperledger-fabric in the app catalog.

## Version history {#section_kmc_5pt_vdb .section}

**Version 0.2.1**

-   Chart is renamed as ack-hyperledger-fabric.
-   Bug fixes.

**Version 0.2.0**

-   Supports Hyperledger Fabric 1.1.0.
    -   Supports the Node.js-type chaincode function and the related examples.
    -   Supports the chaincode-level ledger data encryption function and the related examples.
    -   Supports connection profile.
    -   Code-level optimization to further improve the performance and horizontal scalability.
    -   Other new functions provided by Hyperledger Fabric 1.1.0.
-   Integrates with Alibaba Cloud Log Service.
-   Built-in deployment of Hyperledger Blockchain Explorer.
-   Supports Alibaba Cloud Elastic Compute Service \(ECS\) Bare Metal Instance.
-   Optimizes the cleanup of the data directory in the process of deleting the blockchain network.

**Version 0.1.0**

-   Supports deploying Hyperledger Fabric 1.0.0 on an Alibaba Cloud Container Service Kubernetes cluster.

## Upgrade instructions {#section_hdl_tpt_vdb .section}

-   The blockchain solution installed on the App Catalog page in the Container Service console is of the latest version.
-   For the blockchain solution installed by using the helm install command, use the following command to view the current version because helm repo may have the cache of an earlier version locally if the blockchain solution was installed before.

    ```
    helm search hyperledger
    ```

    To update the local repo cache, run the following command to obtain the blockchain solution of the latest version:

    ```
    helm repo update
    ```



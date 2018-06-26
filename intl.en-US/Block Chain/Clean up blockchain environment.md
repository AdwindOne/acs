# Clean up blockchain environment {#concept_qcs_btz_vdb .concept}

After you complete the development and testing activities, clean up the blockchain environment if the deployed blockchain network is no longer in use or you must redeploy the blockchain network.

## Delete blockchain network in Container Service console {#section_ohx_4js_c2b .section}

1.  Log on to the [Container Service console](https://partners-intl.console.aliyun.com/#/cs).
2.  Under Kubernetes, click **Application** \> **Release** in the left-side navigation pane. Select the cluster from the Clusters drop-down list. Click **Delete** at the right of the release name of the blockchain network.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/7402/6233_en-US.png)

3.  Click **OK** in the displayed dialog box.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/7402/6234_en-US.png)


## Use Helm to delete blockchain network {#section_k4m_dtz_vdb .section}

1.  Use SSH to log on to a master node of the Kubernetes cluster as the root account.
2.  Run the helm list command to view the Helm release name of the blockchain network.
3.  Run the command helm delete --purge <Helm release name of the blockchain network\> to delete the blockchain network. For example, helm delete --purge blockchain-network01.

Wait a few minutes \(depending on the number of nodes in the blockchain network\) until the helm delete command is complete and the result is returned. Then, the services and containers of all blockchain nodes are deleted from the Kubernetes cluster. The chaincode containers related to the blockchain network are also automatically deleted from all worker nodes.

## Data directory of blockchain network {#section_m4m_dtz_vdb .section}

When the blockchain network is deleted, the data directory of the blockchain network in the shared file storage is automatically cleaned up for recreating the blockchain network. For security reasons, the data directory is cleaned up by adding the suffix -deleted-timestamp to the original directory name. For example, -deleted-2018-03-17-160332. In this way, you can reuse the data by deleting the suffix. To completely delete the data directory, manually use the rm command or use the automated script to release storage space with regular cleanup.


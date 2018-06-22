# Access Kubernetes clusters by using SSH {#concept_qy2_f2g_vdb .concept}

If you select not to enable SSH access for Internet when creating the Kubernetes cluster, you cannot access the Kubernetes cluster by using SSH or connect to the Kubernetes cluster by using kubectl.  To access the cluster by using SSH after creating the cluster, manually bind Elastic IP \(EIP\) to the Elastic Compute Service \(ECS\) instance, configure security group rules, and open the SSH port \(22\).

## Procedure {#section_f3q_grx_b2b .section}

1.  Log on to the [Container Service console](https://cs.console.aliyun.com).
2.  Under Kubernetes, click **Clusters** in the left-side navigation pane.
3.  Click **Manage** at the right of the cluster.
4.  In **Cluster resource**, click the ID of the Internet SLB. Then, you are redirected to the Instance Details page of your Internet Server Load Balancer instance.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6882/1993_en-US.png)

5.  Click **Listeners** in the left-side navigation pane and then click **Add Listener** in the upper-right corner.
6.  Add the SSH listening rule.

    1.  **Front-end Protocol \[Port\]**: Select TCP and enter 22.
    2.  **Backend Protocol \[Port\]**: Enter 22.
    3.  Turn on the **Use Server Group** switch and select **VServer Group**.
    4.  **Server Group ID:** Select **sshVirtualGroup**.
    5.  Click **Next** and then click **Confirm** to create the listener.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6882/1990_en-US.png)

7.  Then, you can use the Server Load Balancer instance IP address to access your cluster by using SSH.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6882/1991_en-US.png)



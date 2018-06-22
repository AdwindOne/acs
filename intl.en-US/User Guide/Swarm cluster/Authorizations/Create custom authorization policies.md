# Create custom authorization policies {#concept_kry_ts2_xdb .concept}

The authorization granularity of the system authorization policies provided by Container Service is coarse. If these authorization policies with coarse granularity cannot satisfy your requirements, create the custom authorization policies. For example, to control the permissions to a specific cluster, you must use the custom authorization policy to meet the requirements with fine granularity.

## Create custom authorization policies {#section_azw_5s2_xdb .section}

Get to know the basic structure and syntax of the authorization policy language before creating custom authorization policies. For more information, see [Authorization policy language descriptions](https://www.alibabacloud.com/help/zh/doc-detail/28663.htm).

This document introduces how to grant Resource Access Management \(RAM\) users permissions to query, expand, and delete clusters.

**Procedure**

1.  Log on to the [RAM console](https://ram.console.aliyun.com/) with the primary account.
2.  Click **Policies** in the left-side navigation pane. Click **Create Authorization Policy** in the upper-right corner.
3.  Select a template. Enter the authorization policy name and the policy content.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6986/4751_en-US.png)

    ```
    
     "Statement": [{
         "Action": [
             "cs:Get*",
             "cs:ScaleCluster",
             "cs:DeleteCluster"
         
         "Effect": "Allow",
         "Resource": [
             "acs:cs:*:*:cluster/cluster ID"
         
     
     "Version": "1"
    
    ```

    Wherein:

    -   `Action:` Enter the permission that you want to grant. 

        **Note:** All the Actions support wildcards.

    -   `Resource` supports the following configuration methods.
        -   Grant permissions of a single cluster

            ```
            "Resource": [
                 "acs:cs:*:*:cluster/cluster ID"
             
            ```

        -   Grant permissions of multiple clusters

            ```
            "Resource": [
                 "acs:cs:*:*:cluster/cluster ID",
                 "acs:cs:*:*:cluster/cluster ID"
             
            ```

        -   Grant permissions of all your clusters

            ```
            "Resource": [
                 
             
            ```

            You must replace `cluster ID` with your actual cluster ID.

4.  Click **Create Authorization Policy** after completing the configurations.

|Action|Description|
|------|-----------|
|CreateCluster|Create clusters.|
|AttachInstances|Add existing Elastic Compute Service \(ECS\) instances to clusters.|
|ScaleCluster|Expand clusters.|
|GetClusters|View cluster list.|
|GetClusterById|View cluster details.|
|ModifyClusterName|Modify cluster names.|
|DeleteCluster|Delete clusters.|
|UpgradeClusterAgent|Upgrade cluster Agent.|
|GetClusterLogs|View cluster operation logs.|
|GetClusterEndpoint|View cluster access point.|
|GetClusterCerts|Download cluster certificate.|
|RevokeClusterCerts|Revoke cluster certificate.|
|BindSLB|Bind Server Load Balancer instances to clusters.|
|UnBindSLB|Unbind Server Load Balancer instances from clusters.|
|ReBindSecurityGroup|Rebind security groups to clusters.|
|CheckSecurityGroup|Check existing security group rules of clusters.|
|FixSecurityGroup|Fix cluster security group rules.|
|ResetClusterNode|Reset cluster nodes.|
|DeleteClusterNode|Delete cluster nodes.|
|CreateAutoScale|Create node auto scaling rules.|
|UpdateAutoScale|Update node auto scaling rules.|
|DeleteAutoScale|Delete node auto scaling rules.|
|GetClusterProjects|View applications in clusters.|
|CreateTriggerHook|Create triggers for applications.|
|GetTriggerHook|View application trigger list.|
|RevokeTriggerHook|Delete application triggers.|
|CreateClusterToken|Create tokens.|


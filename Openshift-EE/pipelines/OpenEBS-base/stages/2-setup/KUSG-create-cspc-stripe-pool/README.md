### KUSG-Create CSPC based Striped Storage Pool using BlockDevices.

#### Description

Administrator should be able to use this job to create OpenEBS cStor based storage pool of type stripe.

#### Prerequisites

- OpenShift cluster should be ready.
- OpenEBS should be deployed in cluster.
- Each node should have the disks attached depending on required pool configuration.

#### Procedure

- This job triggers litmus experiment which creates cspc striped storage pool.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest accordingly.
- This test checks if the required cStor pool is created successfully using kubectl command `kubectl get cspc`
- This investigates if the corresponding cstor pool pods are running using CSPC as label.
- Finally, this job updates the result CR with the actual result.

#### Expected result

- cStorStoragepoolclaim should be created successfully and cStor pool pods should be running according to the maxpool count set.

#### Test Result


| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-openshift/-/jobs/130106">130106</a>   |  Create cStor cspc based Striped storage pool on disks and corresponding storage class           |  Thu Dec 26 07:48:21 UTC 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'1a740e6612cced2f259e2bd133cd1bcdc2bbbb4b',type:phrase),type:phrase,value:'1a740e6612cced2f259e2bd133cd1bcdc2bbbb4b'),query:(match:(commit_id:(query:'1a740e6612cced2f259e2bd133cd1bcdc2bbbb4b',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'4489',type:phrase),type:phrase,value:'4489'),query:(match:(pipeline_id:(query:'4489',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Pass</a>  |
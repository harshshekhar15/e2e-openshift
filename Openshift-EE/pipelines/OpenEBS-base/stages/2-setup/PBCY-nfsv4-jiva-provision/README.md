### PBCY-Create NFS provisioner on openshift cluster using JIVA Storage Engine.

#### Description

Administrator should be able to use this job to create NFS Provisioner using OpenEBS JIVA based storage engine.

#### Prerequisites

- OpenShift cluster should be ready.
- OpenEBS components should be deployed.

#### Procedure

- This job triggers litmus experiment which creates NFS provisioner in openshift cluster.
- The litmus experiment receives the necessary parameters in form of pod environmental variables and updates the manifest accordingly.
- Deploy nfs provisioner version based on the specified environmental variable.
- This test checks if the desired deployment is created.
- Finally, this job updates the result CR with the actual result.

#### Expected result

- nfs provisioner deployment should be successful.

#### Test Result

| Job ID |   Test Description         | Execution Time |Test Result   |
 |---------|---------------------------| --------------|--------|
 |    <a href="https://gitlab.openebs.ci/openebs/e2e-openshift/-/jobs/130118">130118</a>   |  Create NFS provisioner vers 4.1 with jiva and corresponding storage class           |  Thu Dec 26 07:51:32 UTC 2019     |<a href="https://e2e-logs.openebs100.io/app/kibana#/discover?_g=(refreshInterval:(pause:!t,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(columns:!(_source),filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:commit_id,negate:!f,params:(query:'1a740e6612cced2f259e2bd133cd1bcdc2bbbb4b',type:phrase),type:phrase,value:'1a740e6612cced2f259e2bd133cd1bcdc2bbbb4b'),query:(match:(commit_id:(query:'1a740e6612cced2f259e2bd133cd1bcdc2bbbb4b',type:phrase)))),('$state':(store:appState),meta:(alias:!n,disabled:!f,index:cluster-logs,key:pipeline_id,negate:!f,params:(query:'4489',type:phrase),type:phrase,value:'4489'),query:(match:(pipeline_id:(query:'4489',type:phrase))))),index:cluster-logs,interval:auto,query:(language:lucene,query:''),sort:!('@timestamp',desc))">Fail</a>  |
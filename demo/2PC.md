Listing files to watch...
 - syedmustafacs/auth-service-jira
 - asmryz276299/client
 - mazahir10/order-service-jira
 - mazahir10/order-service-jira
Generating tags...
 - syedmustafacs/auth-service-jira -> syedmustafacs/auth-service-jira:d05eac9
 - asmryz276299/client -> asmryz276299/client:d05eac9
 - mazahir10/order-service-jira -> mazahir10/order-service-jira:d05eac9
 - mazahir10/order-service-jira -> mazahir10/order-service-jira:d05eac9
 - mazahir10/order-service-jira -> mazahir10/order-service-jira:d05eac9
Checking cache...
 - syedmustafacs/auth-service-jira: Found Locally
 - asmryz276299/client: Found Locally
 - mazahir10/order-service-jira: Found Locally
 - mazahir10/order-service-jira: Found Locally
Tags used in deployment:
 - syedmustafacs/auth-service-jira -> syedmustafacs/auth-service-jira:39e77d319dde92b5c5f2d7a048466d49b24e13b7f9815f20f78344a6ad0a8f2e
 - asmryz276299/client -> asmryz276299/client:c85b726a7fcf277304ac2c8ed8d4a0ee918c8ce569f4d16d0ddd5df6b40920b5
 - mazahir10/order-service-jira -> mazahir10/order-service-jira:22c49d9fcb4bbf5c042589154a7606b79a8e39b34ace27dbce7186575b6ef15e
 - mazahir10/order-service-jira -> mazahir10/order-service-jira:22c49d9fcb4bbf5c042589154a7606b79a8e39b34ace27dbce7186575b6ef15e
 - mazahir10/order-service-jira -> mazahir10/order-service-jira:22c49d9fcb4bbf5c042589154a7606b79a8e39b34ace27dbce7186575b6ef15e
Starting deploy...
 - deployment.apps/auth-depl created
 - service/auth-srv created
 - deployment.apps/client-depl created
 - service/client-srv created
 - deployment.apps/order-depl created
 - service/order-srv created
 - ingress.networking.k8s.io/ingress-service created
Waiting for deployments to stabilize...
 - deployment/client-depl is ready. [2/3 deployment(s) still pending]
 - deployment/auth-depl is ready. [1/3 deployment(s) still pending]
 - deployment/order-depl is ready.
Deployments stabilized in 2.633 seconds
Press Ctrl+C to exit
Watching for changes...
[order]
[order] > order-service@1.0.0 start
[order] > node index.js
[order]
[client]
[client] > comm-gen-react-app@0.1.0 start
[client] > react-scripts start
[client]
[auth]
[auth] > auth@1.0.0 start
[auth] > ts-node-dev src/index.ts
[auth]
[auth] [INFO] 11:09:51 ts-node-dev ver. 1.1.8 (using ts-node ver. 9.1.1, typescript ver. 4.7.4)
[order] Order Service Stared
[client] Initialize Prepare Mode
[order] Initialize Prepare Mode
[client] UPDATE customer SET fund = ? WHERE customer_id = ?
[client] Done
INSERT INTO order  ( id, order_id, p_id )  VALUES  ( ?, ?, ? ) 
[order] Done
[client] Commit Phase ... Done
[order] Commit Phase  ... Done
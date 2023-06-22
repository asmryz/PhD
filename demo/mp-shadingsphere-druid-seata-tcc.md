# mp-shadingsphere-druid-seata-tcc

[https://github.com/seata/seata-samples/tree/master/mp-shadingsphere-druid-seata-tcc]: :

```
2022-06-21 15:57:35.909  INFO 9104 --- [nio-8070-exec-1] i.seata.tm.api.DefaultGlobalTransaction  : Begin new global transaction [192.168.1.188:8091:27149561796388640]
2022-06-21 15:57:39.033  INFO 9104 --- [nio-8070-exec-1] ShardingSphere-SQL                       : Rule Type: master-slave
2022-06-21 15:57:39.033  INFO 9104 --- [nio-8070-exec-1] ShardingSphere-SQL                       : SQL: INSERT INTO user_order  ( id, order_id, p_id )  VALUES  ( ?, ?, ? ) ::: DataSources: master
2022-06-21 15:57:39.063  INFO 9104 --- [nio-8070-exec-1] c.d.m.o.a.impl.UserOrderTccActionImpl    : geneOrder---------------------1387677438737305602
2022-06-21 15:57:39.149  INFO 9104 --- [h_RMROLE_1_1_12] i.s.c.r.p.c.RmBranchRollbackProcessor    : rm handle branch rollback process:xid=192.168.1.188:8091:27149561796388640,branchId=27149561796388658,branchType=TCC,resourceId=gene-order,applicationData={"actionContext":{"action-start-time":1619683057855,"sys::prepare":"geneOrder","sys::rollback":"cancel","sys::commit":"commit","id":1387677438737305602,"host-name":"169.254.174.68","actionName":"gene-order"}}
2022-06-21 15:57:39.157  INFO 9104 --- [h_RMROLE_1_1_12] io.seata.rm.AbstractRMHandler            : Branch Rollbacking: 192.168.1.188:8091:27149561796388640 27149561796388658 gene-order
2022-06-21 15:57:39.174  INFO 9104 --- [h_RMROLE_1_1_12] c.d.m.o.a.impl.UserOrderTccActionImpl    : cancel---------------------1387677438737305602
2022-06-21 15:57:39.191  INFO 9104 --- [h_RMROLE_1_1_12] ShardingSphere-SQL                       : Rule Type: master-slave
2022-06-21 15:57:39.191  INFO 9104 --- [h_RMROLE_1_1_12] ShardingSphere-SQL                       : SQL: DELETE FROM user_order WHERE id=? ::: DataSources: master
2022-06-21 15:57:39.197  INFO 9104 --- [h_RMROLE_1_1_12] io.seata.rm.AbstractResourceManager      : TCC resource rollback result : true, xid: 192.168.1.188:8091:27149561796388640, branchId: 27149561796388658, resourceId: gene-order
2022-06-21 15:57:39.199  INFO 9104 --- [h_RMROLE_1_1_12] io.seata.rm.AbstractRMHandler            : Branch Rollbacked result: PhaseTwo_Rollbacked
2022-06-21 15:57:39.314  INFO 9104 --- [nio-8070-exec-1] i.seata.tm.api.DefaultGlobalTransaction  : [192.168.1.188:8091:27149561796388640] rollback status: Rollbacked
2022-06-21 15:57:39.338 ERROR 9104 --- [nio-8070-exec-1] o.a.c.c.C.[.[.[/].[dispatcherServlet]    : Servlet.service() for servlet [dispatcherServlet] in context with path [] threw exception [Request processing failed; nested exception is java.lang.ArithmeticException: / by zero] with root cause

java.lang.ArithmeticException: / by zero
```

```
2022-06-21 15:57:39.221  INFO 4656 --- [h_RMROLE_1_1_12] i.s.c.r.p.c.RmBranchRollbackProcessor    : rm handle branch rollback process:xid=192.168.1.188:8091:27149561796388640,branchId=27149561796388642,branchType=TCC,resourceId=order-decuct,applicationData={"actionContext":{"action-start-time":1619683056387,"sys::prepare":"deduct","sys::rollback":"cancel","sys::commit":"commit","id":1,"host-name":"169.254.174.68","actionName":"order-decuct"}}
2022-06-21 15:57:39.229  INFO 4656 --- [h_RMROLE_1_1_12] io.seata.rm.AbstractRMHandler            : Branch Rollbacking: 192.168.1.188:8091:27149561796388640 27149561796388642 order-decuct
2022-06-21 15:57:39.251  INFO 4656 --- [h_RMROLE_1_1_12] c.d.m.p.a.impl.CompanyProductActionImpl  : cancel---------------------1
2022-06-21 15:57:39.252  INFO 4656 --- [h_RMROLE_1_1_12] ShardingSphere-SQL                       : Rule Type: master-slave
2022-06-21 15:57:39.252  INFO 4656 --- [h_RMROLE_1_1_12] ShardingSphere-SQL                       : SQL: SELECT  id,product_name,account  FROM company_product WHERE (id = ?) ::: DataSources: slave02
2022-06-21 15:57:39.257  INFO 4656 --- [h_RMROLE_1_1_12] ShardingSphere-SQL                       : Rule Type: master-slave
2022-06-21 15:57:39.257  INFO 4656 --- [h_RMROLE_1_1_12] ShardingSphere-SQL                       : SQL: UPDATE company_product  SET product_name=?,account=?  WHERE id=? ::: DataSources: master
2022-06-21 15:57:39.264  INFO 4656 --- [h_RMROLE_1_1_12] io.seata.rm.AbstractResourceManager      : TCC resource rollback result : true, xid: 192.168.1.188:8091:27149561796388640, branchId: 27149561796388642, resourceId: order-decuct
2022-06-21 15:57:39.266  INFO 4656 --- [h_RMROLE_1_1_12] io.seata.rm.AbstractRMHandler            : Branch Rollbacked result: PhaseTwo_Rollbacked
```

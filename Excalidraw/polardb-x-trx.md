---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
handle:65, FrontendCommandHandler 
query:462, FrontendConnection 
queryRaw:115, ServerQueryHandler 
executeStatement:164, ServerQueryHandler 
execute:685, ServerConnection 
execute:702, ServerConnection 
innerExecute:881, ServerConnection 
execute:66, TPreparedStatement 
executeInternal:149, TStatement 
executeSQL:81, TPreparedStatement  ^yCaVMM0X

executeSQL:311, TConnection 
executeQuery:487, TConnection 
execute:59, PlanExecutor 
execByExecPlanNodeByOne:109, PlanExecutor 
execute:77, ExecutorHelper 
executeByCursor:142, ExecutorHelper 
execByExecPlanNode:105, TransactionExecutor 
execByExecPlanNode:53, TopologyExecutor 
execByExecPlanNode:52, AbstractGroupExecutor 
executeInner:74, AbstractGroupExecutor  ^oNcqj9D6

handlePlan:97, HandlerCommon 
handle:123, MyBaseDalHandler 
repoCursor:58, CursorFactoryMyImpl 
<init>:73, MyPhyQueryCursor 
init:69, AbstractCursor 
doInit:88, MyPhyQueryCursor  ^hJRg3VnI

executeQuery:640, MyJdbcHandler 
getPhyConnection:1493, MyJdbcHandler 
getPhyConnection:1499, MyJdbcHandler 
getConnection:53, AutoCommitTransaction  ^8TALWNQ7

getSelfConnection:73, AutoCommitTransaction 
getConnection:43, AutoCommitConnectionHolder 
getConnection:45, TGroupDataSource 
getConnection:124, TGroupDataSource 
<init>:72, TGroupDirectConnection 
<init>:80, TGroupDirectConnection 
createNewConnection:91, TGroupDirectConnection 
getConnection:246, TAtomDataSource 
 ^BV2jXZk8

discribe customer; ^XecbS2a3

executeSQL:300, TConnection 
beginTransaction:1349, TConnection 
beginTransaction:1380, TConnection  ^HOAHiXq8

createTransaction:180, TransactionManager (com.apecloud.foxlake.transaction)
<init>:43, AutoCommitTransaction (com.apecloud.foxlake.transaction) ^EWYgOPWN

ITransactionPolicy$TransactionClass ^UxXnkHDe

XA ^Nv5gLTZz

AUTOCOMMIT ^gZU6WoQL

Yes ^ILn4nGaT

    public BaseTransaction(ExecutionContext executionContext, ITransactionManager manager) {
        super();
        this.executionContext = executionContext;
        this.isolationLevel = executionContext.getTxIsolation();
        this.autoCommit = executionContext.isAutoCommit();
        this.manager = manager;
        this.id = manager.generateTxid(executionContext);
        // Register to manager so that we can see it in SHOW TRANS
        manager.register(this);
    } ^CV8SxqKF

ch = new AutoCommitConnectionHolder();  ^gLXWheee

(RAII) ^IBGP5Qlu

lambda$handleData$0:723, FrontendConnection 
handle:65, FrontendCommandHandler 
query:462, FrontendConnection ^BblrksUv

queryRaw:115, ServerQueryHandler 
executeStatement:164, ServerQueryHandler 
execute:685, ServerConnection 
execute:702, ServerConnection 
innerExecute:850, ServerConnection 
getConnection:1699, ServerConnection ^at3nU7kv

init:43, AbstractLifecycle 
doInit:142, TDataSource 
init:43, AbstractLifecycle 
doInit:168, MatrixConfigHolder 
prepare:125, TransactionManager  ^DrdVljI2

exec ddl ^soTurtKq

consume:49, OrcConsumer 
commit:82, AutoCommitTransaction ^ppKmr417

        try {
            // Commit and close extract statement
            context.getTransaction().commit();
        } catch (Exception e) {
            LOGGER.error("Close extract statement failed!", e);
            throw GeneralUtil.nestedException("Unable to commit extract statement.", e);
        } ^KpojtRLa

    public void close() {
        if (isClosed()) {
            return;
        }

        lock.lock();
        try {
            if (isClosed()) {
                return;
            }

            super.close();
            this.getConnectionHolder().closeAllConnections();
        } finally {
            lock.unlock();
        }
    } ^dbp3JWpC

execute:97, UpdateTreeTask 
updateTree:257, UpdateTreeTask 
generateMergePlan:342, UpdateTreeTask 
executeQuery:40, InnerStatement 
executeSql:158, InnerConnection  ^Aaf8cCCJ

commit:784, TConnection 
commit:82, AutoCommitTransaction  ^1ZWtJdea

            try {
                // 事务结束,清理事务内容
                this.trx.commit();
            } catch (Throwable e) {
                // 增加打印事务异常日志
                logger.error(e);
                throw GeneralUtil.nestedException(e);
            } finally {
                if (isAutoCommit) {
                    if (trxPolicy == ITransactionPolicy.NO_TRANSACTION) {
                        // DTS relies on NO_TRANSACTION to process batch by batch. Fuck it.
                        // See DataXSpecialTest for details.
                    } else {
                        this.trxPolicy = null;
                    }
                }
                this.trx.close();
                this.trx = null;
                refreshTableMeta();
                releaseTransactionalMdl(executionContext);
            } ^h5XUWMCN

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/1.8.26",
	"elements": [
		{
			"type": "text",
			"version": 131,
			"versionNonce": 147816006,
			"isDeleted": false,
			"id": "yCaVMM0X",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1851.9663878567337,
			"y": -79.81227825284321,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 480.46875,
			"height": 240,
			"seed": 1683522822,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "DTK63TuUqgFkdYRiXUM7E",
					"type": "arrow"
				}
			],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "handle:65, FrontendCommandHandler \nquery:462, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:164, ServerQueryHandler \nexecute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:881, ServerConnection \nexecute:66, TPreparedStatement \nexecuteInternal:149, TStatement \nexecuteSQL:81, TPreparedStatement ",
			"rawText": "handle:65, FrontendCommandHandler \nquery:462, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:164, ServerQueryHandler \nexecute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:881, ServerConnection \nexecute:66, TPreparedStatement \nexecuteInternal:149, TStatement \nexecuteSQL:81, TPreparedStatement ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "handle:65, FrontendCommandHandler \nquery:462, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:164, ServerQueryHandler \nexecute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:881, ServerConnection \nexecute:66, TPreparedStatement \nexecuteInternal:149, TStatement \nexecuteSQL:81, TPreparedStatement ",
			"lineHeight": 1.2,
			"baseline": 236
		},
		{
			"type": "text",
			"version": 47,
			"versionNonce": 1285746970,
			"isDeleted": false,
			"id": "oNcqj9D6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1851.9663878567337,
			"y": 439.6097050998766,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 527.34375,
			"height": 240,
			"seed": 1448311686,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "Wytx46Jv-84whdysZNzmn",
					"type": "arrow"
				},
				{
					"id": "Ir9zje2yOvWqQOxb2uqz7",
					"type": "arrow"
				}
			],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "executeSQL:311, TConnection \nexecuteQuery:487, TConnection \nexecute:59, PlanExecutor \nexecByExecPlanNodeByOne:109, PlanExecutor \nexecute:77, ExecutorHelper \nexecuteByCursor:142, ExecutorHelper \nexecByExecPlanNode:105, TransactionExecutor \nexecByExecPlanNode:53, TopologyExecutor \nexecByExecPlanNode:52, AbstractGroupExecutor \nexecuteInner:74, AbstractGroupExecutor ",
			"rawText": "executeSQL:311, TConnection \nexecuteQuery:487, TConnection \nexecute:59, PlanExecutor \nexecByExecPlanNodeByOne:109, PlanExecutor \nexecute:77, ExecutorHelper \nexecuteByCursor:142, ExecutorHelper \nexecByExecPlanNode:105, TransactionExecutor \nexecByExecPlanNode:53, TopologyExecutor \nexecByExecPlanNode:52, AbstractGroupExecutor \nexecuteInner:74, AbstractGroupExecutor ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "executeSQL:311, TConnection \nexecuteQuery:487, TConnection \nexecute:59, PlanExecutor \nexecByExecPlanNodeByOne:109, PlanExecutor \nexecute:77, ExecutorHelper \nexecuteByCursor:142, ExecutorHelper \nexecByExecPlanNode:105, TransactionExecutor \nexecByExecPlanNode:53, TopologyExecutor \nexecByExecPlanNode:52, AbstractGroupExecutor \nexecuteInner:74, AbstractGroupExecutor ",
			"lineHeight": 1.2,
			"baseline": 236
		},
		{
			"type": "text",
			"version": 62,
			"versionNonce": 2014561670,
			"isDeleted": false,
			"id": "hJRg3VnI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1851.9663878567337,
			"y": 787.3399695017993,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 410.15625,
			"height": 144,
			"seed": 1421135558,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "U_kzTQ2VZGPoIijkMLNHI",
					"type": "arrow"
				},
				{
					"id": "Wytx46Jv-84whdysZNzmn",
					"type": "arrow"
				}
			],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "handlePlan:97, HandlerCommon \nhandle:123, MyBaseDalHandler \nrepoCursor:58, CursorFactoryMyImpl \n<init>:73, MyPhyQueryCursor \ninit:69, AbstractCursor \ndoInit:88, MyPhyQueryCursor ",
			"rawText": "handlePlan:97, HandlerCommon \nhandle:123, MyBaseDalHandler \nrepoCursor:58, CursorFactoryMyImpl \n<init>:73, MyPhyQueryCursor \ninit:69, AbstractCursor \ndoInit:88, MyPhyQueryCursor ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "handlePlan:97, HandlerCommon \nhandle:123, MyBaseDalHandler \nrepoCursor:58, CursorFactoryMyImpl \n<init>:73, MyPhyQueryCursor \ninit:69, AbstractCursor \ndoInit:88, MyPhyQueryCursor ",
			"lineHeight": 1.2,
			"baseline": 140
		},
		{
			"type": "text",
			"version": 93,
			"versionNonce": 404340186,
			"isDeleted": false,
			"id": "8TALWNQ7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1851.9663878567337,
			"y": 1101.1602149272967,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 468.75,
			"height": 96,
			"seed": 66606406,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "U_kzTQ2VZGPoIijkMLNHI",
					"type": "arrow"
				},
				{
					"id": "cmAzp1Xwbn8f2Nf0jsela",
					"type": "arrow"
				}
			],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "executeQuery:640, MyJdbcHandler \ngetPhyConnection:1493, MyJdbcHandler \ngetPhyConnection:1499, MyJdbcHandler \ngetConnection:53, AutoCommitTransaction ",
			"rawText": "executeQuery:640, MyJdbcHandler \ngetPhyConnection:1493, MyJdbcHandler \ngetPhyConnection:1499, MyJdbcHandler \ngetConnection:53, AutoCommitTransaction ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "executeQuery:640, MyJdbcHandler \ngetPhyConnection:1493, MyJdbcHandler \ngetPhyConnection:1499, MyJdbcHandler \ngetConnection:53, AutoCommitTransaction ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "text",
			"version": 162,
			"versionNonce": 1573725382,
			"isDeleted": false,
			"id": "BV2jXZk8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -966.5009733875945,
			"y": 1177.4349213526848,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 550.78125,
			"height": 216,
			"seed": 635614938,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "cmAzp1Xwbn8f2Nf0jsela",
					"type": "arrow"
				}
			],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "getSelfConnection:73, AutoCommitTransaction \ngetConnection:43, AutoCommitConnectionHolder \ngetConnection:45, TGroupDataSource \ngetConnection:124, TGroupDataSource \n<init>:72, TGroupDirectConnection \n<init>:80, TGroupDirectConnection \ncreateNewConnection:91, TGroupDirectConnection \ngetConnection:246, TAtomDataSource \n",
			"rawText": "getSelfConnection:73, AutoCommitTransaction \ngetConnection:43, AutoCommitConnectionHolder \ngetConnection:45, TGroupDataSource \ngetConnection:124, TGroupDataSource \n<init>:72, TGroupDirectConnection \n<init>:80, TGroupDirectConnection \ncreateNewConnection:91, TGroupDirectConnection \ngetConnection:246, TAtomDataSource \n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "getSelfConnection:73, AutoCommitTransaction \ngetConnection:43, AutoCommitConnectionHolder \ngetConnection:45, TGroupDataSource \ngetConnection:124, TGroupDataSource \n<init>:72, TGroupDirectConnection \n<init>:80, TGroupDirectConnection \ncreateNewConnection:91, TGroupDirectConnection \ngetConnection:246, TAtomDataSource \n",
			"lineHeight": 1.2,
			"baseline": 212
		},
		{
			"type": "arrow",
			"version": 165,
			"versionNonce": 211350170,
			"isDeleted": false,
			"id": "Wytx46Jv-84whdysZNzmn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1651.68541705895,
			"y": 691.9456607425959,
			"strokeColor": "#a61e4d",
			"backgroundColor": "transparent",
			"width": 1.6562574071469953,
			"height": 95.12850119280893,
			"seed": 30496090,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oNcqj9D6",
				"focus": 0.24719552687889973,
				"gap": 12.335955642719341
			},
			"endBinding": {
				"elementId": "hJRg3VnI",
				"focus": -0.009124607478289063,
				"gap": 1
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					1.6562574071469953,
					95.12850119280893
				]
			]
		},
		{
			"type": "arrow",
			"version": 205,
			"versionNonce": 1536728070,
			"isDeleted": false,
			"id": "U_kzTQ2VZGPoIijkMLNHI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1659.2573108802674,
			"y": 946.9694952835375,
			"strokeColor": "#a61e4d",
			"backgroundColor": "transparent",
			"width": 0.47500927689839045,
			"height": 133.96902005945367,
			"seed": 1005397530,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "hJRg3VnI",
				"focus": 0.058725674034554705,
				"gap": 15.629525781738266
			},
			"endBinding": {
				"elementId": "8TALWNQ7",
				"focus": -0.18070216341253006,
				"gap": 20.221699584305497
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-0.47500927689839045,
					133.96902005945367
				]
			]
		},
		{
			"type": "arrow",
			"version": 76,
			"versionNonce": 1020497754,
			"isDeleted": false,
			"id": "cmAzp1Xwbn8f2Nf0jsela",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1382.2163878567337,
			"y": 1186.7792585706648,
			"strokeColor": "#364fc7",
			"backgroundColor": "transparent",
			"width": 402.6666793916131,
			"height": 2.588454949202969,
			"seed": 754005466,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "8TALWNQ7",
				"focus": 0.7905309535388511,
				"gap": 1
			},
			"endBinding": {
				"elementId": "BV2jXZk8",
				"focus": 0.9392185134382137,
				"gap": 13.04873507752609
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					402.6666793916131,
					-2.588454949202969
				]
			]
		},
		{
			"type": "text",
			"version": 96,
			"versionNonce": 1467165510,
			"isDeleted": false,
			"id": "XecbS2a3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1125.0622077427822,
			"y": -148.29687385005076,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 172.73980712890625,
			"height": 25,
			"seed": 1721529670,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "discribe customer;",
			"rawText": "discribe customer;",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "discribe customer;",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 23,
			"versionNonce": 1830589466,
			"isDeleted": false,
			"id": "HOAHiXq8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1848.4782296104543,
			"y": 254.89280907558503,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 410.15625,
			"height": 72,
			"seed": 2062293190,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "Ir9zje2yOvWqQOxb2uqz7",
					"type": "arrow"
				},
				{
					"id": "DTK63TuUqgFkdYRiXUM7E",
					"type": "arrow"
				}
			],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "executeSQL:300, TConnection \nbeginTransaction:1349, TConnection \nbeginTransaction:1380, TConnection ",
			"rawText": "executeSQL:300, TConnection \nbeginTransaction:1349, TConnection \nbeginTransaction:1380, TConnection ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "executeSQL:300, TConnection \nbeginTransaction:1349, TConnection \nbeginTransaction:1380, TConnection ",
			"lineHeight": 1.2,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 39,
			"versionNonce": 1874449030,
			"isDeleted": false,
			"id": "Ir9zje2yOvWqQOxb2uqz7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1645.7851751483345,
			"y": 336.9660351137034,
			"strokeColor": "#a61e4d",
			"backgroundColor": "transparent",
			"width": 0.2583820923168787,
			"height": 82.6545857458317,
			"seed": 1011370118,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "HOAHiXq8",
				"focus": 0.012325597858891568,
				"gap": 10.073226038118378
			},
			"endBinding": {
				"elementId": "oNcqj9D6",
				"focus": -0.21509302381752357,
				"gap": 19.98908424034147
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0.2583820923168787,
					82.6545857458317
				]
			]
		},
		{
			"type": "arrow",
			"version": 52,
			"versionNonce": 1600585946,
			"isDeleted": false,
			"id": "DTK63TuUqgFkdYRiXUM7E",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1641.355767851472,
			"y": 173.75160415618154,
			"strokeColor": "#a61e4d",
			"backgroundColor": "transparent",
			"width": 0.9597049143201275,
			"height": 80.10767655013552,
			"seed": 1924467610,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "yCaVMM0X",
				"focus": 0.11595731015899287,
				"gap": 13.563882409024757
			},
			"endBinding": {
				"elementId": "HOAHiXq8",
				"focus": 0.003118899803412667,
				"gap": 1.0335283692679695
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-0.9597049143201275,
					80.10767655013552
				]
			]
		},
		{
			"type": "text",
			"version": 153,
			"versionNonce": 1864995270,
			"isDeleted": false,
			"id": "EWYgOPWN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -951.0234127035528,
			"y": 296.4830980067522,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 890.625,
			"height": 48,
			"seed": 1632950150,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "p5rtxU-GBtBGJxc_I_9OX",
					"type": "arrow"
				},
				{
					"id": "14g6cqXG4IupzsmuAxd0c",
					"type": "arrow"
				}
			],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "createTransaction:180, TransactionManager (com.apecloud.foxlake.transaction)\n<init>:43, AutoCommitTransaction (com.apecloud.foxlake.transaction)",
			"rawText": "createTransaction:180, TransactionManager (com.apecloud.foxlake.transaction)\n<init>:43, AutoCommitTransaction (com.apecloud.foxlake.transaction)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "createTransaction:180, TransactionManager (com.apecloud.foxlake.transaction)\n<init>:43, AutoCommitTransaction (com.apecloud.foxlake.transaction)",
			"lineHeight": 1.2,
			"baseline": 44
		},
		{
			"type": "arrow",
			"version": 150,
			"versionNonce": 524670362,
			"isDeleted": false,
			"id": "p5rtxU-GBtBGJxc_I_9OX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1444.7177676663734,
			"y": 315.52954938326167,
			"strokeColor": "#364fc7",
			"backgroundColor": "transparent",
			"width": 478.1797489029599,
			"height": 2.923491136198095,
			"seed": 1529736262,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "EWYgOPWN",
				"focus": -0.029463628415534227,
				"gap": 15.514606059860625
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					478.1797489029599,
					2.923491136198095
				]
			]
		},
		{
			"type": "text",
			"version": 408,
			"versionNonce": 1088383238,
			"isDeleted": false,
			"id": "UxXnkHDe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -713.0535056796043,
			"y": 533.742454276829,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 410.15625,
			"height": 24,
			"seed": 1375660294,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "14g6cqXG4IupzsmuAxd0c",
					"type": "arrow"
				},
				{
					"id": "iQturST6tAeeAEO7dQ92L",
					"type": "arrow"
				},
				{
					"id": "K8VXtgn_JEEAU3FtF_kiB",
					"type": "arrow"
				}
			],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "ITransactionPolicy$TransactionClass",
			"rawText": "ITransactionPolicy$TransactionClass",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ITransactionPolicy$TransactionClass",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 329,
			"versionNonce": 1307316826,
			"isDeleted": false,
			"id": "14g6cqXG4IupzsmuAxd0c",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -501.73996858810233,
			"y": 349.68534459759894,
			"strokeColor": "#1864ab",
			"backgroundColor": "transparent",
			"width": 2.3394255989679777,
			"height": 183.03787940085726,
			"seed": 1697877126,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "EWYgOPWN",
				"focus": -0.00787256660214657,
				"gap": 5.202246590846755
			},
			"endBinding": {
				"elementId": "UxXnkHDe",
				"focus": 0.04259208679994022,
				"gap": 1.019230278372845
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					2.3394255989679777,
					183.03787940085726
				]
			]
		},
		{
			"type": "text",
			"version": 51,
			"versionNonce": 1683511366,
			"isDeleted": false,
			"id": "Nv5gLTZz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -706.9815265101543,
			"y": 691.5354752616279,
			"strokeColor": "#d9480f",
			"backgroundColor": "transparent",
			"width": 23.4375,
			"height": 24,
			"seed": 1360563078,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "iQturST6tAeeAEO7dQ92L",
					"type": "arrow"
				},
				{
					"id": "K8VXtgn_JEEAU3FtF_kiB",
					"type": "arrow"
				}
			],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "XA",
			"rawText": "XA",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "XA",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 59,
			"versionNonce": 1848424218,
			"isDeleted": false,
			"id": "gZU6WoQL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -370.37425574419467,
			"y": 691.5354752616279,
			"strokeColor": "#d9480f",
			"backgroundColor": "transparent",
			"width": 117.1875,
			"height": 24,
			"seed": 690336070,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "iQturST6tAeeAEO7dQ92L",
					"type": "arrow"
				},
				{
					"id": "qkASABtexIK1dIeFEV7JZ",
					"type": "arrow"
				}
			],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "AUTOCOMMIT",
			"rawText": "AUTOCOMMIT",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AUTOCOMMIT",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 76,
			"versionNonce": 1634819974,
			"isDeleted": false,
			"id": "iQturST6tAeeAEO7dQ92L",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -506.5877580545912,
			"y": 564.3515042845236,
			"strokeColor": "#1864ab",
			"backgroundColor": "transparent",
			"width": 187.43775211223942,
			"height": 113.09753297989414,
			"seed": 1895322458,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "UxXnkHDe",
				"focus": 0.13092367001016464,
				"gap": 6.609050007694577
			},
			"endBinding": {
				"elementId": "gZU6WoQL",
				"focus": 0.4569719308665931,
				"gap": 14.086437997210169
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					187.43775211223942,
					113.09753297989414
				]
			]
		},
		{
			"type": "text",
			"version": 74,
			"versionNonce": 813351898,
			"isDeleted": false,
			"id": "ILn4nGaT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -403.7609132442974,
			"y": 587.7627674348164,
			"strokeColor": "#1864ab",
			"backgroundColor": "transparent",
			"width": 32.119964599609375,
			"height": 25,
			"seed": 200421786,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Yes",
			"rawText": "Yes",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Yes",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 49,
			"versionNonce": 1013415622,
			"isDeleted": false,
			"id": "K8VXtgn_JEEAU3FtF_kiB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -512.8719796570153,
			"y": 569.4170621345686,
			"strokeColor": "#1864ab",
			"backgroundColor": "transparent",
			"width": 165.9920384499294,
			"height": 119.75087185705661,
			"seed": 678226886,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1683289769247,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "UxXnkHDe",
				"focus": -0.12592846157371126,
				"gap": 11.674607857739602
			},
			"endBinding": {
				"elementId": "Nv5gLTZz",
				"focus": -0.12403614120471917,
				"gap": 4.680008403209513
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-165.9920384499294,
					119.75087185705661
				]
			]
		},
		{
			"type": "text",
			"version": 209,
			"versionNonce": 1055471770,
			"isDeleted": false,
			"id": "CV8SxqKF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 78.1015282421049,
			"y": 626.9176636712992,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 855.654296875,
			"height": 230,
			"seed": 1147730374,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 2,
			"text": "    public BaseTransaction(ExecutionContext executionContext, ITransactionManager manager) {\n        super();\n        this.executionContext = executionContext;\n        this.isolationLevel = executionContext.getTxIsolation();\n        this.autoCommit = executionContext.isAutoCommit();\n        this.manager = manager;\n        this.id = manager.generateTxid(executionContext);\n        // Register to manager so that we can see it in SHOW TRANS\n        manager.register(this);\n    }",
			"rawText": "    public BaseTransaction(ExecutionContext executionContext, ITransactionManager manager) {\n        super();\n        this.executionContext = executionContext;\n        this.isolationLevel = executionContext.getTxIsolation();\n        this.autoCommit = executionContext.isAutoCommit();\n        this.manager = manager;\n        this.id = manager.generateTxid(executionContext);\n        // Register to manager so that we can see it in SHOW TRANS\n        manager.register(this);\n    }",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "    public BaseTransaction(ExecutionContext executionContext, ITransactionManager manager) {\n        super();\n        this.executionContext = executionContext;\n        this.isolationLevel = executionContext.getTxIsolation();\n        this.autoCommit = executionContext.isAutoCommit();\n        this.manager = manager;\n        this.id = manager.generateTxid(executionContext);\n        // Register to manager so that we can see it in SHOW TRANS\n        manager.register(this);\n    }",
			"lineHeight": 1.15,
			"baseline": 226
		},
		{
			"type": "rectangle",
			"version": 356,
			"versionNonce": 1775744518,
			"isDeleted": false,
			"id": "1nhy-OHhjTFgEaS3JaHpe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 60.734560465656614,
			"y": 595.5334673866535,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 896.2813385882982,
			"height": 284.64478641463904,
			"seed": 1749040134,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1683289769248,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 199,
			"versionNonce": 153818458,
			"isDeleted": false,
			"id": "gLXWheee",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 78.1015282421049,
			"y": 912.4873927710739,
			"strokeColor": "#1864ab",
			"backgroundColor": "transparent",
			"width": 380.72265625,
			"height": 23,
			"seed": 1921821318,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 2,
			"text": "ch = new AutoCommitConnectionHolder(); ",
			"rawText": "ch = new AutoCommitConnectionHolder(); ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ch = new AutoCommitConnectionHolder(); ",
			"lineHeight": 1.15,
			"baseline": 19
		},
		{
			"type": "rectangle",
			"version": 409,
			"versionNonce": 1119814982,
			"isDeleted": false,
			"id": "Uyk6tebrTO-Weefh6sXP3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 30.94679639425385,
			"y": 563.0511472096603,
			"strokeColor": "#1864ab",
			"backgroundColor": "transparent",
			"width": 961.3843979203116,
			"height": 396.8656658670294,
			"seed": 1695381466,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "qkASABtexIK1dIeFEV7JZ",
					"type": "arrow"
				}
			],
			"updated": 1683289769248,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 250,
			"versionNonce": 278092314,
			"isDeleted": false,
			"id": "qkASABtexIK1dIeFEV7JZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -239.31205434382048,
			"y": 706.568568048034,
			"strokeColor": "#1864ab",
			"backgroundColor": "transparent",
			"width": 258.6596376804009,
			"height": 0.7843322765244238,
			"seed": 275872218,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "gZU6WoQL",
				"focus": 0.2310250042349319,
				"gap": 13.874701400374192
			},
			"endBinding": {
				"elementId": "Uyk6tebrTO-Weefh6sXP3",
				"focus": 0.2633357996787005,
				"gap": 11.59921305767341
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					258.6596376804009,
					0.7843322765244238
				]
			]
		},
		{
			"type": "text",
			"version": 127,
			"versionNonce": 2021289094,
			"isDeleted": false,
			"id": "IBGP5Qlu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 460.381621978916,
			"y": 912.915703438817,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 70.3125,
			"height": 24,
			"seed": 275647066,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "(RAII)",
			"rawText": "(RAII)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(RAII)",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 9,
			"versionNonce": 873793242,
			"isDeleted": false,
			"id": "BblrksUv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1623.001190521084,
			"y": 2159.189140938817,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 515.625,
			"height": 72,
			"seed": 1366648966,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "AKWBirV7Mjux2aLyNuDRx",
					"type": "arrow"
				}
			],
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "lambda$handleData$0:723, FrontendConnection \nhandle:65, FrontendCommandHandler \nquery:462, FrontendConnection",
			"rawText": "lambda$handleData$0:723, FrontendConnection \nhandle:65, FrontendCommandHandler \nquery:462, FrontendConnection",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "lambda$handleData$0:723, FrontendConnection \nhandle:65, FrontendCommandHandler \nquery:462, FrontendConnection",
			"lineHeight": 1.2,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 9,
			"versionNonce": 147254214,
			"isDeleted": false,
			"id": "at3nU7kv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1623.001190521084,
			"y": 2365.401055001317,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 480.46875,
			"height": 144,
			"seed": 1785966150,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "CcNKgtXH-aSNBZ7TGe0hB",
					"type": "arrow"
				},
				{
					"id": "AKWBirV7Mjux2aLyNuDRx",
					"type": "arrow"
				}
			],
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "queryRaw:115, ServerQueryHandler \nexecuteStatement:164, ServerQueryHandler \nexecute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:850, ServerConnection \ngetConnection:1699, ServerConnection",
			"rawText": "queryRaw:115, ServerQueryHandler \nexecuteStatement:164, ServerQueryHandler \nexecute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:850, ServerConnection \ngetConnection:1699, ServerConnection",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "queryRaw:115, ServerQueryHandler \nexecuteStatement:164, ServerQueryHandler \nexecute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:850, ServerConnection \ngetConnection:1699, ServerConnection",
			"lineHeight": 1.2,
			"baseline": 140
		},
		{
			"type": "text",
			"version": 61,
			"versionNonce": 2084772762,
			"isDeleted": false,
			"id": "DrdVljI2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -869.462128021084,
			"y": 2377.401055001317,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 375,
			"height": 120,
			"seed": 1857457626,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "CcNKgtXH-aSNBZ7TGe0hB",
					"type": "arrow"
				}
			],
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "init:43, AbstractLifecycle \ndoInit:142, TDataSource \ninit:43, AbstractLifecycle \ndoInit:168, MatrixConfigHolder \nprepare:125, TransactionManager ",
			"rawText": "init:43, AbstractLifecycle \ndoInit:142, TDataSource \ninit:43, AbstractLifecycle \ndoInit:168, MatrixConfigHolder \nprepare:125, TransactionManager ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "init:43, AbstractLifecycle \ndoInit:142, TDataSource \ninit:43, AbstractLifecycle \ndoInit:168, MatrixConfigHolder \nprepare:125, TransactionManager ",
			"lineHeight": 1.2,
			"baseline": 116
		},
		{
			"type": "text",
			"version": 85,
			"versionNonce": 834765574,
			"isDeleted": false,
			"id": "soTurtKq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1759.384003021084,
			"y": 2421.682305001317,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 81.179931640625,
			"height": 25,
			"seed": 1257655962,
			"groupIds": [],
			"roundness": null,
			"boundElements": null,
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "exec ddl",
			"rawText": "exec ddl",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "exec ddl",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 66,
			"versionNonce": 1733335130,
			"isDeleted": false,
			"id": "CcNKgtXH-aSNBZ7TGe0hB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1119.071503021084,
			"y": 2437.502617501317,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 228.328125,
			"height": 1.4453125,
			"seed": 339220698,
			"groupIds": [],
			"roundness": null,
			"boundElements": null,
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "at3nU7kv",
				"focus": 0.024085041423333595,
				"gap": 23.4609375
			},
			"endBinding": {
				"elementId": "DrdVljI2",
				"focus": 0.04356050756396975,
				"gap": 21.28125
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					228.328125,
					-1.4453125
				]
			]
		},
		{
			"type": "arrow",
			"version": 33,
			"versionNonce": 1709650502,
			"isDeleted": false,
			"id": "AKWBirV7Mjux2aLyNuDRx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1398.712128021084,
			"y": 2238.869805001317,
			"strokeColor": "#364fc7",
			"backgroundColor": "transparent",
			"width": 1.5234375,
			"height": 103.875,
			"seed": 1443576070,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "BblrksUv",
				"focus": 0.13224432027534683,
				"gap": 7.6806640625
			},
			"endBinding": {
				"elementId": "at3nU7kv",
				"focus": -0.05401642161074155,
				"gap": 22.65625
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					1.5234375,
					103.875
				]
			]
		},
		{
			"type": "text",
			"version": 282,
			"versionNonce": 890273050,
			"isDeleted": false,
			"id": "ppKmr417",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1656.079315521084,
			"y": 3131.455742501317,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 375,
			"height": 48,
			"seed": 349594502,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "ep_1kN9DsNymLQAYevxZQ",
					"type": "arrow"
				}
			],
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "consume:49, OrcConsumer \ncommit:82, AutoCommitTransaction",
			"rawText": "consume:49, OrcConsumer \ncommit:82, AutoCommitTransaction",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "consume:49, OrcConsumer \ncommit:82, AutoCommitTransaction",
			"lineHeight": 1.2,
			"baseline": 44
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 1075116422,
			"isDeleted": false,
			"id": "KpojtRLa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -606.532440521084,
			"y": 3080.533867501317,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1031.25,
			"height": 168,
			"seed": 151802138,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "c5RKZgTQfCY0yLyfzTuaH",
					"type": "arrow"
				}
			],
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "        try {\n            // Commit and close extract statement\n            context.getTransaction().commit();\n        } catch (Exception e) {\n            LOGGER.error(\"Close extract statement failed!\", e);\n            throw GeneralUtil.nestedException(\"Unable to commit extract statement.\", e);\n        }",
			"rawText": "        try {\n            // Commit and close extract statement\n            context.getTransaction().commit();\n        } catch (Exception e) {\n            LOGGER.error(\"Close extract statement failed!\", e);\n            throw GeneralUtil.nestedException(\"Unable to commit extract statement.\", e);\n        }",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "        try {\n            // Commit and close extract statement\n            context.getTransaction().commit();\n        } catch (Exception e) {\n            LOGGER.error(\"Close extract statement failed!\", e);\n            throw GeneralUtil.nestedException(\"Unable to commit extract statement.\", e);\n        }",
			"lineHeight": 1.2,
			"baseline": 164
		},
		{
			"type": "text",
			"version": 228,
			"versionNonce": 1822991174,
			"isDeleted": false,
			"id": "dbp3JWpC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -533.759003021084,
			"y": 3530.776055001317,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 714.84375,
			"height": 408,
			"seed": 1745660998,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "c5RKZgTQfCY0yLyfzTuaH",
					"type": "arrow"
				},
				{
					"id": "vfrfkgXtXB8kAIGH0PyPr",
					"type": "arrow"
				}
			],
			"updated": 1683289894849,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "    public void close() {\n        if (isClosed()) {\n            return;\n        }\n\n        lock.lock();\n        try {\n            if (isClosed()) {\n                return;\n            }\n\n            super.close();\n            this.getConnectionHolder().closeAllConnections();\n        } finally {\n            lock.unlock();\n        }\n    }",
			"rawText": "    public void close() {\n        if (isClosed()) {\n            return;\n        }\n\n        lock.lock();\n        try {\n            if (isClosed()) {\n                return;\n            }\n\n            super.close();\n            this.getConnectionHolder().closeAllConnections();\n        } finally {\n            lock.unlock();\n        }\n    }",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "    public void close() {\n        if (isClosed()) {\n            return;\n        }\n\n        lock.lock();\n        try {\n            if (isClosed()) {\n                return;\n            }\n\n            super.close();\n            this.getConnectionHolder().closeAllConnections();\n        } finally {\n            lock.unlock();\n        }\n    }",
			"lineHeight": 1.2,
			"baseline": 404
		},
		{
			"id": "ep_1kN9DsNymLQAYevxZQ",
			"type": "arrow",
			"x": -1272.610565521084,
			"y": 3135.9831955143754,
			"width": 742.59375,
			"height": 2.5665155130582207,
			"angle": 0,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 2026974362,
			"version": 232,
			"versionNonce": 135495322,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					742.59375,
					-2.5665155130582207
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "ppKmr417",
				"focus": -0.7625457679500832,
				"gap": 8.46875
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "c5RKZgTQfCY0yLyfzTuaH",
			"type": "arrow",
			"x": -160.908762211444,
			"y": 3267.923515938817,
			"width": 1.7405783398285735,
			"height": 247.85937500000045,
			"angle": 0,
			"strokeColor": "#364fc7",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 788185670,
			"version": 105,
			"versionNonce": 18651994,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.7405783398285735,
					247.85937500000045
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "KpojtRLa",
				"focus": 0.13420130088562637,
				"gap": 19.3896484375
			},
			"endBinding": {
				"elementId": "dbp3JWpC",
				"focus": 0.03385751615274393,
				"gap": 14.9931640625
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Aaf8cCCJ",
			"type": "text",
			"x": -1912.227753021084,
			"y": 4225.613945626317,
			"width": 445.3125,
			"height": 120,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 1802083590,
			"version": 80,
			"versionNonce": 2015364442,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1683289889994,
			"link": null,
			"locked": false,
			"text": "execute:97, UpdateTreeTask \nupdateTree:257, UpdateTreeTask \ngenerateMergePlan:342, UpdateTreeTask \nexecuteQuery:40, InnerStatement \nexecuteSql:158, InnerConnection ",
			"rawText": "execute:97, UpdateTreeTask \nupdateTree:257, UpdateTreeTask \ngenerateMergePlan:342, UpdateTreeTask \nexecuteQuery:40, InnerStatement \nexecuteSql:158, InnerConnection ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 116,
			"containerId": null,
			"originalText": "execute:97, UpdateTreeTask \nupdateTree:257, UpdateTreeTask \ngenerateMergePlan:342, UpdateTreeTask \nexecuteQuery:40, InnerStatement \nexecuteSql:158, InnerConnection ",
			"lineHeight": 1.2
		},
		{
			"id": "1ZWtJdea",
			"type": "text",
			"x": -1115.766815521084,
			"y": 4307.137383126317,
			"width": 386.71875,
			"height": 48,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 659440410,
			"version": 93,
			"versionNonce": 826400666,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "RnkjP0MEJyrxRZOnejCGR",
					"type": "arrow"
				}
			],
			"updated": 1683289905798,
			"link": null,
			"locked": false,
			"text": "commit:784, TConnection \ncommit:82, AutoCommitTransaction ",
			"rawText": "commit:784, TConnection \ncommit:82, AutoCommitTransaction ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "commit:784, TConnection \ncommit:82, AutoCommitTransaction ",
			"lineHeight": 1.2
		},
		{
			"id": "RnkjP0MEJyrxRZOnejCGR",
			"type": "arrow",
			"x": -1523.509003021084,
			"y": 4335.512383126317,
			"width": 393.2265625,
			"height": 5.7421875,
			"angle": 0,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 842411910,
			"version": 122,
			"versionNonce": 390959878,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1683289890034,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					393.2265625,
					-5.7421875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "1ZWtJdea",
				"focus": 0.16413668976534374,
				"gap": 14.515625
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "h5XUWMCN",
			"type": "text",
			"x": -610.579315521084,
			"y": 4258.363945626317,
			"width": 1066.40625,
			"height": 504,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 2088959366,
			"version": 88,
			"versionNonce": 1588419226,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "vfrfkgXtXB8kAIGH0PyPr",
					"type": "arrow"
				},
				{
					"id": "h7VUO96_acYkAVKffsvH1",
					"type": "arrow"
				}
			],
			"updated": 1683289910133,
			"link": null,
			"locked": false,
			"text": "            try {\n                // 事务结束,清理事务内容\n                this.trx.commit();\n            } catch (Throwable e) {\n                // 增加打印事务异常日志\n                logger.error(e);\n                throw GeneralUtil.nestedException(e);\n            } finally {\n                if (isAutoCommit) {\n                    if (trxPolicy == ITransactionPolicy.NO_TRANSACTION) {\n                        // DTS relies on NO_TRANSACTION to process batch by batch. Fuck it.\n                        // See DataXSpecialTest for details.\n                    } else {\n                        this.trxPolicy = null;\n                    }\n                }\n                this.trx.close();\n                this.trx = null;\n                refreshTableMeta();\n                releaseTransactionalMdl(executionContext);\n            }",
			"rawText": "            try {\n                // 事务结束,清理事务内容\n                this.trx.commit();\n            } catch (Throwable e) {\n                // 增加打印事务异常日志\n                logger.error(e);\n                throw GeneralUtil.nestedException(e);\n            } finally {\n                if (isAutoCommit) {\n                    if (trxPolicy == ITransactionPolicy.NO_TRANSACTION) {\n                        // DTS relies on NO_TRANSACTION to process batch by batch. Fuck it.\n                        // See DataXSpecialTest for details.\n                    } else {\n                        this.trxPolicy = null;\n                    }\n                }\n                this.trx.close();\n                this.trx = null;\n                refreshTableMeta();\n                releaseTransactionalMdl(executionContext);\n            }",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 500,
			"containerId": null,
			"originalText": "            try {\n                // 事务结束,清理事务内容\n                this.trx.commit();\n            } catch (Throwable e) {\n                // 增加打印事务异常日志\n                logger.error(e);\n                throw GeneralUtil.nestedException(e);\n            } finally {\n                if (isAutoCommit) {\n                    if (trxPolicy == ITransactionPolicy.NO_TRANSACTION) {\n                        // DTS relies on NO_TRANSACTION to process batch by batch. Fuck it.\n                        // See DataXSpecialTest for details.\n                    } else {\n                        this.trxPolicy = null;\n                    }\n                }\n                this.trx.close();\n                this.trx = null;\n                refreshTableMeta();\n                releaseTransactionalMdl(executionContext);\n            }",
			"lineHeight": 1.2
		},
		{
			"id": "h7VUO96_acYkAVKffsvH1",
			"type": "arrow",
			"x": -806.477753021084,
			"y": 4323.613945626317,
			"width": 178.9609375,
			"height": 0.578125,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 883866374,
			"version": 562,
			"versionNonce": 713852166,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1683289950925,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					178.9609375,
					-0.578125
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "h5XUWMCN",
				"focus": 0.7453234842636737,
				"gap": 16.9375
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "vfrfkgXtXB8kAIGH0PyPr",
			"type": "arrow",
			"x": -130.44112538938577,
			"y": 4246.989922188817,
			"width": 8.963652791271898,
			"height": 300.46875,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 2096065818,
			"version": 86,
			"versionNonce": 493999898,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1683289896827,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-8.963652791271898,
					-300.46875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "h5XUWMCN",
				"focus": -0.08336726302168718,
				"gap": 11.3740234375
			},
			"endBinding": {
				"elementId": "dbp3JWpC",
				"focus": -0.08422249397102607,
				"gap": 7.7451171875
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "arrow",
			"version": 342,
			"versionNonce": 2005391558,
			"isDeleted": true,
			"id": "DfKwbcHMwq5pF68xvtOkp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -865.5011674964064,
			"y": 3126.111992501317,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 241.57810197532245,
			"height": 115.22698572524298,
			"seed": 1184189210,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ppKmr417",
				"focus": 0.8400458468086002,
				"gap": 5.421898024677603
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					77.18295391575407,
					-56.01190630367121
				],
				[
					241.57810197532245,
					-115.22698572524298
				]
			]
		},
		{
			"id": "TsQpyFpACJcBBztCnDV2z",
			"type": "arrow",
			"x": -864.188690521084,
			"y": 3176.668144845067,
			"width": 280.28125,
			"height": 158.78125,
			"angle": 0,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 1817740762,
			"version": 229,
			"versionNonce": 1406980102,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					280.28125,
					158.78125
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "ppKmr417",
				"focus": -0.8319901168958433,
				"gap": 6.734375
			},
			"endBinding": {
				"elementId": "dbp3JWpC",
				"focus": -0.5039881252036867,
				"gap": 19.4375
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Kvd8W5FP",
			"type": "text",
			"x": -1563.524628021084,
			"y": 4119.926445626317,
			"width": 304.6875,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 2059762714,
			"version": 2,
			"versionNonce": 1327464966,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1683289765602,
			"link": null,
			"locked": false,
			"text": "execute:97, UpdateTreeTask",
			"rawText": "execute:97, UpdateTreeTask",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "execute:97, UpdateTreeTask",
			"lineHeight": 1.2
		},
		{
			"id": "Dtf8v0GX",
			"type": "text",
			"x": -1563.524628021084,
			"y": 4153.926445626317,
			"width": 351.5625,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 460548742,
			"version": 2,
			"versionNonce": 1444284762,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1683289765602,
			"link": null,
			"locked": false,
			"text": "updateTree:257, UpdateTreeTask",
			"rawText": "updateTree:257, UpdateTreeTask",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "updateTree:257, UpdateTreeTask",
			"lineHeight": 1.2
		},
		{
			"id": "rL28wyow",
			"type": "text",
			"x": -1563.524628021084,
			"y": 4187.926445626317,
			"width": 433.59375,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 397600986,
			"version": 2,
			"versionNonce": 1160597830,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1683289765602,
			"link": null,
			"locked": false,
			"text": "generateMergePlan:342, UpdateTreeTask",
			"rawText": "generateMergePlan:342, UpdateTreeTask",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "generateMergePlan:342, UpdateTreeTask",
			"lineHeight": 1.2
		},
		{
			"id": "JvdExFPh",
			"type": "text",
			"x": -1563.524628021084,
			"y": 4221.926445626317,
			"width": 363.28125,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 535833030,
			"version": 2,
			"versionNonce": 1811926554,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1683289765602,
			"link": null,
			"locked": false,
			"text": "executeQuery:40, InnerStatement",
			"rawText": "executeQuery:40, InnerStatement",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "executeQuery:40, InnerStatement",
			"lineHeight": 1.2
		},
		{
			"id": "oI2Ivko6",
			"type": "text",
			"x": -1563.524628021084,
			"y": 4255.926445626317,
			"width": 363.28125,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 903134618,
			"version": 2,
			"versionNonce": 792672390,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1683289765602,
			"link": null,
			"locked": false,
			"text": "executeSql:158, InnerConnection",
			"rawText": "executeSql:158, InnerConnection",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "executeSql:158, InnerConnection",
			"lineHeight": 1.2
		},
		{
			"id": "xr7pa19E",
			"type": "text",
			"x": -1507.524628021084,
			"y": 4129.926445626317,
			"width": 304.6875,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 1372781274,
			"version": 2,
			"versionNonce": 554753862,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"text": "execute:97, UpdateTreeTask",
			"rawText": "execute:97, UpdateTreeTask",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "execute:97, UpdateTreeTask",
			"lineHeight": 1.2
		},
		{
			"id": "KFN9bHmw",
			"type": "text",
			"x": -1507.524628021084,
			"y": 4163.926445626317,
			"width": 351.5625,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 621950918,
			"version": 2,
			"versionNonce": 1550065690,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"text": "updateTree:257, UpdateTreeTask",
			"rawText": "updateTree:257, UpdateTreeTask",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "updateTree:257, UpdateTreeTask",
			"lineHeight": 1.2
		},
		{
			"id": "6CkRxgKc",
			"type": "text",
			"x": -1507.524628021084,
			"y": 4197.926445626317,
			"width": 433.59375,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 371363738,
			"version": 2,
			"versionNonce": 595658374,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"text": "generateMergePlan:342, UpdateTreeTask",
			"rawText": "generateMergePlan:342, UpdateTreeTask",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "generateMergePlan:342, UpdateTreeTask",
			"lineHeight": 1.2
		},
		{
			"id": "VJAZpmLV",
			"type": "text",
			"x": -1507.524628021084,
			"y": 4231.926445626317,
			"width": 363.28125,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 1052987142,
			"version": 2,
			"versionNonce": 366808282,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"text": "executeQuery:40, InnerStatement",
			"rawText": "executeQuery:40, InnerStatement",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "executeQuery:40, InnerStatement",
			"lineHeight": 1.2
		},
		{
			"id": "JVKiPpjN",
			"type": "text",
			"x": -1507.524628021084,
			"y": 4265.926445626317,
			"width": 363.28125,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 2099350618,
			"version": 2,
			"versionNonce": 199902662,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1683289769248,
			"link": null,
			"locked": false,
			"text": "executeSql:158, InnerConnection",
			"rawText": "executeSql:158, InnerConnection",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "executeSql:158, InnerConnection",
			"lineHeight": 1.2
		}
	],
	"appState": {
		"theme": "dark",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#000000",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 1,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 3,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 2071.524628021084,
		"scrollY": -2969.452324532567,
		"zoom": {
			"value": 0.5
		},
		"currentItemRoundness": "sharp",
		"gridSize": null,
		"colorPalette": {},
		"currentStrokeOptions": null,
		"previousGridSize": null
	},
	"files": {}
}
```
%%
---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
handle:65, FrontendCommandHandler 
query:462, FrontendConnection 
queryRaw:115, ServerQueryHandler 
executeStatement:163, ServerQueryHandler 
execute:684, ServerConnection 
execute:701, ServerConnection 
innerExecute:880, ServerConnection 
execute:66, TPreparedStatement 
executeInternal:150, TStatement 
executeSQL:81, TPreparedStatement 
executeSQL:311, TConnection  
 ^cAOWmZs2

execute:59, PlanExecutor 
execByExecPlanNodeByOne:105, PlanExecutor 
execute:77, ExecutorHelper 
executeByCursor:142, ExecutorHelper 
execByExecPlanNode:105, TransactionExecutor 
execByExecPlanNode:53, TopologyExecutor 
execByExecPlanNode:52, AbstractGroupExecutor 
executeInner:74, AbstractGroupExecutor  ^CG0MPe2t

CommandHandlerFactoryMyImp.getCommandHandler ^YvnCFOUN

logicalPlan(RelNode) 
 ^8RaS5fEs

instance of LogicalMerge ^AsXJJmaF

LogicalMergeHandler ^W7T6RXKG

handlePlan:97, HandlerCommon 
handle:51, LogicalMergeHandler  ^sQSk4vA7

next:53, AbstractCursor 
doNext:88, MppResultCursor  ^QWwM9Zic

handle:61, LogicalMergeHandler 
handleInsertion:134, LogicalMergeHandler  ^L6A6ndyh

handle:66, LogicalMergeHandler 
handleDeletion:145, LogicalMergeHandler  ^KtysKtCp

Exec stage ^Yq6nuQLZ

executeQuery:404, TConnection 
plan:133, Planner  ^1DIuXfc7

1. parameterized
2. get sql type ^DcscusZC

plan:134, Planner 
plan:140, Planner 
plan:169, Planner 
doPlan:1014, Planner 
doBuildPlan:278, Planner  ^T2YvxmYh

parse:81, FastsqlParser 
parse:86, FastsqlParser 
parse:95, FastsqlParser 
parseWithStat:119, FastsqlParser 
doParse:148, FastsqlParser 
realParse:157, FastsqlParser  ^9uYQFyx8

parseSql:54, FastsqlUtils 
parseStatementList:99, SQLStatementParser 
parseStatementList:363, SQLStatementParser 
parseMerge:5134, SQLStatementParser  ^Lys4XXnp

doBuildPlan:286, Planner 
getPlan:458, Planner  ^cOYWNNdr

accept:247, AbstractRelNode 
visit:298, ToLogicalRelVisitor 
create:68, LogicalMerge 
buildInputRel:705, LogicalMerge  ^b3YRD9sl

STEP 1: Build the innermost JOIN between input and action_groups
(which duplicates the UPDATEed rows for INSERT and DELETE actions)

STEP 2: Build the inner aggregation on top of the JOIN
(which aggregates the rows by action_group and mpid)

STEP 3: Build the projection on top of the inner aggregation
(which calls the STAGE_DELETION_MARK function)

STEP 4: Build the outermost aggregation
(which aggregates the rows by action_group) ^6doxMYby

SELECT
    `SYS$ACTION_GROUP`,
    (__FIRST_VALUE(`SYS$DATA_FILE_METADATA`)) AS `SYS$DATA_FILE_METADATA`, 
    (CSV_FILE_AGG(
        `SYS$STORAGE_NAME`, `SYS$CSV_DELIMITER`,
        `__sys_mp_id__`, `SYS$DELETION_MARK_METADATA`
    )) AS `SYS$DELETION_MARK_METADATA`
FROM (
    SELECT
        `t`.`SYS$ACTION_GROUP`,
        `t5`.`__sys_mp_id__`,
        (SINK_DELTA_DATA(
            `t5`.`id`, `t5`.`msg`,
            (CASE WHEN (`t`.`SYS$ACTION_GROUP` = 2) THEN `t5`.`__sys_mp_id__` ELSE '!IGNORE THIS ROW!' END),
            `t5`.`__sys_mp_rid__`,
            `t5`.`__sys_cts__`,
            `t5`.`__sys_xts__`,
            `t5`.`__sys_mp_row_cnt__`,
            `t5`.`__sys_mp_mod_ts__`
        )) AS `SYS$DATA_FILE_METADATA`,
        STAGE_DELETION_MARK(
            's3x', `t5`.`__sys_mp_id__`,
            (__FIRST_VALUE(`t5`.`__sys_mp_row_cnt__`)),
            (__FIRST_VALUE(`t5`.`__sys_mp_mod_ts__`)),
            BITMAP_CONSTRUCT_AGG(`t5`.`__sys_mp_rid__`)
        ) AS `SYS$DELETION_MARK_METADATA`,
        's3x' AS `SYS$STORAGE_NAME`,
        (CASE WHEN (`t`.`SYS$ACTION_GROUP` = 1) THEN '|' ELSE NULL END) AS `SYS$CSV_DELIMITER`
    FROM
        VALUES(2),(1) AS `t` (`SYS$ACTION_GROUP`)
    INNER JOIN (
        SELECT
            (CASE WHEN `SYS$MATCHED0` THEN 0 WHEN `SYS$UNMATCHED0` THEN 2 ELSE 3 END) AS `SYS$ACTION`,
            (CASE WHEN `SYS$MATCHED0` THEN `id` WHEN `SYS$UNMATCHED0` THEN `id0` ELSE `id` END) AS `id`,
            (CASE WHEN `SYS$MATCHED0` THEN 'world' WHEN `SYS$UNMATCHED0` THEN `msg0` ELSE `msg` END) AS `msg`,
            `__sys_mp_id__`, `__sys_mp_rid__`,
            `__sys_cts__`, `__sys_xts__`,
            `__sys_mp_row_cnt__`, `__sys_mp_mod_ts__`
        FROM (
            SELECT
                `t0`.`id`, `t0`.`msg`,
                `t0`.`__sys_mp_id__`, `t0`.`__sys_mp_rid__`,
                `t0`.`__sys_cts__`, `t0`.`__sys_xts__`,
                `t0`.`__sys_mp_row_cnt__`, `t0`.`__sys_mp_mod_ts__`,
                `t2`.`id` AS `id0`, `t2`.`msg` AS `msg0`,
                (CASE WHEN (`t0`.`__sys_mp_id__` IS NOT NULL) THEN TRUE ELSE FALSE END) AS `SYS$MATCHED0`,
                (CASE WHEN (`t0`.`__sys_mp_id__` IS NULL) THEN TRUE ELSE FALSE END) AS `SYS$UNMATCHED0`
            FROM `t` AS `t0`
            RIGHT JOIN (
                SELECT 1 AS `id`, 'hello' AS `msg`
            ) AS `t2`
            ON (`t0`.`id` = `t2`.`id`)
        ) AS `t3`
        WHERE (`SYS$MATCHED0` OR `SYS$UNMATCHED0`)
    ) AS `t5`
    ON ((`t`.`SYS$ACTION_GROUP` = `t5`.`SYS$ACTION`) OR (`t5`.`SYS$ACTION` = 0))
    GROUP BY `t`.`SYS$ACTION_GROUP`, `t5`.`__sys_mp_id__`
) AS `t8`
GROUP BY `SYS$ACTION_GROUP` ^UjnONYTA

t3 as input ^duwSy1Ei

RelNode to LogicalRelNode ^HF6JqAEm

getPlan:483, Planner 
optimize:514, Planner 
rewriteAndEnumerate:530, Planner  ^29oVNm9k

1. rbo optimizeBySqlRewriter
2. cbo optimizeByPlanEnumerator ^yPBCvgW0

doNext:70, MppResultCursor  ^r2wpXwWB

while (client.isValid()) {
    QueryResults clientResults = client.current();
    QueryError queryError = clientResults.getError();
    if (queryError != null) {
        log.error("MppError:" + ec.getTraceId() + ",SchemaName=" + ec.getSchemaName() + ",stackInfo="
            + queryError.getFailureInfo());
        throw GeneralUtil.nestedException(queryError.toException());
    }
    Iterable<Object> data = clientResults.getData();
    if (data != null) {
        currentChunks = data.iterator();
        client.advance();
        break;
    }
    client.advance();
} ^kLQjngcH

poll: get results? ^wAK47JKj

set current chunk ^a2p7ZaZu

fetchInput:105, LogicalMergeHandler 
executeCluster:116, ExecutorHelper ^UcGCliBx

fetchInput:107, LogicalMergeHandler ^36Gn94ZP

execute:56, MppRunner 
createQuery:54, LocalStatementClient 
createQuery:153, StatementResource  ^Jr6MzTlJ


# Embedded files
3439630805cffc85e254198df1a4295adedb12b5: [[Pasted Image 20230615190616_749.png]]
6d90bdccfca56f975b33d3133f8cc7afb335fd4e: [[Pasted Image 20230615191106_872.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/1.8.26",
	"elements": [
		{
			"id": "cAOWmZs2",
			"type": "text",
			"x": -220.15718638103965,
			"y": -512.3879316742546,
			"width": 480.46875,
			"height": 288,
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
			"seed": 942843514,
			"version": 118,
			"versionNonce": 649912762,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686912553472,
			"link": null,
			"locked": false,
			"text": "handle:65, FrontendCommandHandler \nquery:462, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:163, ServerQueryHandler \nexecute:684, ServerConnection \nexecute:701, ServerConnection \ninnerExecute:880, ServerConnection \nexecute:66, TPreparedStatement \nexecuteInternal:150, TStatement \nexecuteSQL:81, TPreparedStatement \nexecuteSQL:311, TConnection  \n",
			"rawText": "handle:65, FrontendCommandHandler \nquery:462, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:163, ServerQueryHandler \nexecute:684, ServerConnection \nexecute:701, ServerConnection \ninnerExecute:880, ServerConnection \nexecute:66, TPreparedStatement \nexecuteInternal:150, TStatement \nexecuteSQL:81, TPreparedStatement \nexecuteSQL:311, TConnection  \n",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 284,
			"containerId": null,
			"originalText": "handle:65, FrontendCommandHandler \nquery:462, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:163, ServerQueryHandler \nexecute:684, ServerConnection \nexecute:701, ServerConnection \ninnerExecute:880, ServerConnection \nexecute:66, TPreparedStatement \nexecuteInternal:150, TStatement \nexecuteSQL:81, TPreparedStatement \nexecuteSQL:311, TConnection  \n",
			"lineHeight": 1.2
		},
		{
			"id": "CG0MPe2t",
			"type": "text",
			"x": -149.52870127232268,
			"y": 3225.8477486353586,
			"width": 527.34375,
			"height": 192,
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
			"seed": 1445940730,
			"version": 383,
			"versionNonce": 462875514,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "bj7sPJ5FfgnxmMakAGYix",
					"type": "arrow"
				},
				{
					"id": "wABSMU90YREbNK6y4EyD-",
					"type": "arrow"
				}
			],
			"updated": 1686919212630,
			"link": null,
			"locked": false,
			"text": "execute:59, PlanExecutor \nexecByExecPlanNodeByOne:105, PlanExecutor \nexecute:77, ExecutorHelper \nexecuteByCursor:142, ExecutorHelper \nexecByExecPlanNode:105, TransactionExecutor \nexecByExecPlanNode:53, TopologyExecutor \nexecByExecPlanNode:52, AbstractGroupExecutor \nexecuteInner:74, AbstractGroupExecutor ",
			"rawText": "execute:59, PlanExecutor \nexecByExecPlanNodeByOne:105, PlanExecutor \nexecute:77, ExecutorHelper \nexecuteByCursor:142, ExecutorHelper \nexecByExecPlanNode:105, TransactionExecutor \nexecByExecPlanNode:53, TopologyExecutor \nexecByExecPlanNode:52, AbstractGroupExecutor \nexecuteInner:74, AbstractGroupExecutor ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 188,
			"containerId": null,
			"originalText": "execute:59, PlanExecutor \nexecByExecPlanNodeByOne:105, PlanExecutor \nexecute:77, ExecutorHelper \nexecuteByCursor:142, ExecutorHelper \nexecByExecPlanNode:105, TransactionExecutor \nexecByExecPlanNode:53, TopologyExecutor \nexecByExecPlanNode:52, AbstractGroupExecutor \nexecuteInner:74, AbstractGroupExecutor ",
			"lineHeight": 1.2
		},
		{
			"id": "YvnCFOUN",
			"type": "text",
			"x": 546.862563024167,
			"y": 3372.884324500048,
			"width": 515.625,
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
			"seed": 344797946,
			"version": 524,
			"versionNonce": 164105318,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "68ciQaFIVbcXDMyauWd3L",
					"type": "arrow"
				},
				{
					"id": "bj7sPJ5FfgnxmMakAGYix",
					"type": "arrow"
				}
			],
			"updated": 1686919212630,
			"link": null,
			"locked": false,
			"text": "CommandHandlerFactoryMyImp.getCommandHandler",
			"rawText": "CommandHandlerFactoryMyImp.getCommandHandler",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "CommandHandlerFactoryMyImp.getCommandHandler",
			"lineHeight": 1.2
		},
		{
			"id": "8RaS5fEs",
			"type": "text",
			"x": 1022.2284626131782,
			"y": 3461.691506712309,
			"width": 246.09375,
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
			"seed": 1930016954,
			"version": 634,
			"versionNonce": 243869114,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686919212630,
			"link": null,
			"locked": false,
			"text": "logicalPlan(RelNode) \n",
			"rawText": "logicalPlan(RelNode) \n",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "logicalPlan(RelNode) \n",
			"lineHeight": 1.2
		},
		{
			"id": "AsXJJmaF",
			"type": "text",
			"x": 990.1859989992122,
			"y": 3503.437502695794,
			"width": 281.25,
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
			"seed": 1655165050,
			"version": 641,
			"versionNonce": 1448127206,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686919212630,
			"link": null,
			"locked": false,
			"text": "instance of LogicalMerge",
			"rawText": "instance of LogicalMerge",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "instance of LogicalMerge",
			"lineHeight": 1.2
		},
		{
			"id": "W7T6RXKG",
			"type": "text",
			"x": 694.8367028423822,
			"y": 3566.2109713578648,
			"width": 222.65625,
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
			"seed": 162606310,
			"version": 567,
			"versionNonce": 1955618426,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "68ciQaFIVbcXDMyauWd3L",
					"type": "arrow"
				}
			],
			"updated": 1686919212630,
			"link": null,
			"locked": false,
			"text": "LogicalMergeHandler",
			"rawText": "LogicalMergeHandler",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "LogicalMergeHandler",
			"lineHeight": 1.2
		},
		{
			"id": "68ciQaFIVbcXDMyauWd3L",
			"type": "arrow",
			"x": 799.4633540053403,
			"y": 3405.7212293606417,
			"width": 2.055459098416577,
			"height": 154.69536496825214,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 486297594,
			"version": 1268,
			"versionNonce": 753893478,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686919213342,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.055459098416577,
					154.69536496825214
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "YvnCFOUN",
				"focus": 0.02127584801234774,
				"gap": 8.836904860593677
			},
			"endBinding": {
				"elementId": "W7T6RXKG",
				"focus": -0.03955219687689381,
				"gap": 5.794377028970757
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "bj7sPJ5FfgnxmMakAGYix",
			"type": "arrow",
			"x": 394.29201313618,
			"y": 3386.2448086397553,
			"width": 143.63623840805997,
			"height": 0.6178987473767279,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 2017129530,
			"version": 1121,
			"versionNonce": 959349670,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686919213342,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					143.63623840805997,
					-0.6178987473767279
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "CG0MPe2t",
				"focus": 0.6753765861010528,
				"gap": 16.47696440850268
			},
			"endBinding": {
				"elementId": "YvnCFOUN",
				"focus": 0.030888102938645655,
				"gap": 8.934311479927032
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "sQSk4vA7",
			"type": "text",
			"x": 641.1740881594885,
			"y": 3795.672084758705,
			"width": 363.28125,
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
			"seed": 424466490,
			"version": 393,
			"versionNonce": 1936612346,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "wABSMU90YREbNK6y4EyD-",
					"type": "arrow"
				},
				{
					"id": "pOf4DlLwlHg3TCLYdvF_a",
					"type": "arrow"
				}
			],
			"updated": 1686920151800,
			"link": null,
			"locked": false,
			"text": "handlePlan:97, HandlerCommon \nhandle:51, LogicalMergeHandler ",
			"rawText": "handlePlan:97, HandlerCommon \nhandle:51, LogicalMergeHandler ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "handlePlan:97, HandlerCommon \nhandle:51, LogicalMergeHandler ",
			"lineHeight": 1.2
		},
		{
			"id": "wABSMU90YREbNK6y4EyD-",
			"type": "arrow",
			"x": 185.26569402358632,
			"y": 3436.603556550961,
			"width": 445.9589632852849,
			"height": 384.26366488649455,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 239389242,
			"version": 1428,
			"versionNonce": 11027578,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686919473320,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					141.83298288000117,
					262.38628951105795
				],
				[
					445.9589632852849,
					384.26366488649455
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "CG0MPe2t",
				"focus": -0.028809419637726243,
				"gap": 18.755807915602418
			},
			"endBinding": {
				"elementId": "sQSk4vA7",
				"focus": -0.805586196297131,
				"gap": 9.949430850617318
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "QWwM9Zic",
			"type": "text",
			"x": 1224.4672189053426,
			"y": 5232.532267153366,
			"width": 316.40625,
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
			"seed": 1937226170,
			"version": 773,
			"versionNonce": 1221071354,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "y0HTQnEZwCT3sdMx6zIuE",
					"type": "arrow"
				},
				{
					"id": "VOmbLnFiTOtYTdV2dBFBC",
					"type": "arrow"
				}
			],
			"updated": 1686920123236,
			"link": null,
			"locked": false,
			"text": "next:53, AbstractCursor \ndoNext:88, MppResultCursor ",
			"rawText": "next:53, AbstractCursor \ndoNext:88, MppResultCursor ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "next:53, AbstractCursor \ndoNext:88, MppResultCursor ",
			"lineHeight": 1.2
		},
		{
			"id": "L6A6ndyh",
			"type": "text",
			"x": 634.5166974953343,
			"y": 5421.127563630073,
			"width": 480.46875,
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
			"seed": 1157166822,
			"version": 520,
			"versionNonce": 128297402,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "RHNrjlMN1MonkBEdHilbx",
					"type": "arrow"
				},
				{
					"id": "r8X4n-BEZEaSes5U4y7ua",
					"type": "arrow"
				}
			],
			"updated": 1686920167812,
			"link": null,
			"locked": false,
			"text": "handle:61, LogicalMergeHandler \nhandleInsertion:134, LogicalMergeHandler ",
			"rawText": "handle:61, LogicalMergeHandler \nhandleInsertion:134, LogicalMergeHandler ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "handle:61, LogicalMergeHandler \nhandleInsertion:134, LogicalMergeHandler ",
			"lineHeight": 1.2
		},
		{
			"id": "y0HTQnEZwCT3sdMx6zIuE",
			"type": "arrow",
			"x": 1079.2988438073585,
			"y": 5125.774495820887,
			"width": 137.26179316726518,
			"height": 138.03731914611535,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 973410854,
			"version": 1528,
			"versionNonce": 254125498,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686920016649,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					53.76980120029555,
					93.63057549535529
				],
				[
					137.26179316726518,
					138.03731914611535
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "QWwM9Zic",
				"focus": -0.8842720687861303,
				"gap": 7.906581930718858
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "KtysKtCp",
			"type": "text",
			"x": 635.222867492336,
			"y": 5634.132394065063,
			"width": 468.75,
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
			"seed": 150146106,
			"version": 457,
			"versionNonce": 528245370,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "r8X4n-BEZEaSes5U4y7ua",
					"type": "arrow"
				}
			],
			"updated": 1686920167812,
			"link": null,
			"locked": false,
			"text": "handle:66, LogicalMergeHandler \nhandleDeletion:145, LogicalMergeHandler ",
			"rawText": "handle:66, LogicalMergeHandler \nhandleDeletion:145, LogicalMergeHandler ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "handle:66, LogicalMergeHandler \nhandleDeletion:145, LogicalMergeHandler ",
			"lineHeight": 1.2
		},
		{
			"id": "Yq6nuQLZ",
			"type": "text",
			"x": 1307.024183481556,
			"y": 3155.8960482241237,
			"width": 117.1875,
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
			"seed": 1163550950,
			"version": 286,
			"versionNonce": 315185190,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686919212630,
			"link": null,
			"locked": false,
			"text": "Exec stage",
			"rawText": "Exec stage",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "Exec stage",
			"lineHeight": 1.2
		},
		{
			"id": "1DIuXfc7",
			"type": "text",
			"x": -203.05955968611158,
			"y": -23.927401230456667,
			"width": 351.5625,
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
			"seed": 1589632698,
			"version": 15,
			"versionNonce": 1928649510,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Iio8whLJ9ODT7GSdShfMf",
					"type": "arrow"
				}
			],
			"updated": 1686907489809,
			"link": null,
			"locked": false,
			"text": "executeQuery:404, TConnection \nplan:133, Planner ",
			"rawText": "executeQuery:404, TConnection \nplan:133, Planner ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "executeQuery:404, TConnection \nplan:133, Planner ",
			"lineHeight": 1.2
		},
		{
			"id": "DcscusZC",
			"type": "text",
			"x": 527.9338310098358,
			"y": -22.073959327058674,
			"width": 187.5,
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
			"seed": 917558566,
			"version": 38,
			"versionNonce": 859473510,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Iio8whLJ9ODT7GSdShfMf",
					"type": "arrow"
				}
			],
			"updated": 1686907489809,
			"link": null,
			"locked": false,
			"text": "1. parameterized\n2. get sql type",
			"rawText": "1. parameterized\n2. get sql type",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "1. parameterized\n2. get sql type",
			"lineHeight": 1.2
		},
		{
			"id": "T2YvxmYh",
			"type": "text",
			"x": -193.5056298746738,
			"y": 263.8578543115108,
			"width": 292.96875,
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
			"seed": 864421414,
			"version": 14,
			"versionNonce": 2007134374,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "HneJc3x8KIkcvKTu0bfEn",
					"type": "arrow"
				}
			],
			"updated": 1686907360151,
			"link": null,
			"locked": false,
			"text": "plan:134, Planner \nplan:140, Planner \nplan:169, Planner \ndoPlan:1014, Planner \ndoBuildPlan:278, Planner ",
			"rawText": "plan:134, Planner \nplan:140, Planner \nplan:169, Planner \ndoPlan:1014, Planner \ndoBuildPlan:278, Planner ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 116,
			"containerId": null,
			"originalText": "plan:134, Planner \nplan:140, Planner \nplan:169, Planner \ndoPlan:1014, Planner \ndoBuildPlan:278, Planner ",
			"lineHeight": 1.2
		},
		{
			"id": "9uYQFyx8",
			"type": "text",
			"x": 436.80797742785523,
			"y": 249.66519973632,
			"width": 386.71875,
			"height": 144,
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
			"seed": 1667653626,
			"version": 31,
			"versionNonce": 1466416358,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "HneJc3x8KIkcvKTu0bfEn",
					"type": "arrow"
				},
				{
					"id": "gg7Lm-qDgbIKvE0YoyO6i",
					"type": "arrow"
				}
			],
			"updated": 1686907366678,
			"link": null,
			"locked": false,
			"text": "parse:81, FastsqlParser \nparse:86, FastsqlParser \nparse:95, FastsqlParser \nparseWithStat:119, FastsqlParser \ndoParse:148, FastsqlParser \nrealParse:157, FastsqlParser ",
			"rawText": "parse:81, FastsqlParser \nparse:86, FastsqlParser \nparse:95, FastsqlParser \nparseWithStat:119, FastsqlParser \ndoParse:148, FastsqlParser \nrealParse:157, FastsqlParser ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 140,
			"containerId": null,
			"originalText": "parse:81, FastsqlParser \nparse:86, FastsqlParser \nparse:95, FastsqlParser \nparseWithStat:119, FastsqlParser \ndoParse:148, FastsqlParser \nrealParse:157, FastsqlParser ",
			"lineHeight": 1.2
		},
		{
			"id": "Lys4XXnp",
			"type": "text",
			"x": 1123.0934822108998,
			"y": 276.91386771942473,
			"width": 503.90625,
			"height": 96,
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
			"seed": 548809082,
			"version": 28,
			"versionNonce": 1382756390,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "gg7Lm-qDgbIKvE0YoyO6i",
					"type": "arrow"
				}
			],
			"updated": 1686907366678,
			"link": null,
			"locked": false,
			"text": "parseSql:54, FastsqlUtils \nparseStatementList:99, SQLStatementParser \nparseStatementList:363, SQLStatementParser \nparseMerge:5134, SQLStatementParser ",
			"rawText": "parseSql:54, FastsqlUtils \nparseStatementList:99, SQLStatementParser \nparseStatementList:363, SQLStatementParser \nparseMerge:5134, SQLStatementParser ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 92,
			"containerId": null,
			"originalText": "parseSql:54, FastsqlUtils \nparseStatementList:99, SQLStatementParser \nparseStatementList:363, SQLStatementParser \nparseMerge:5134, SQLStatementParser ",
			"lineHeight": 1.2
		},
		{
			"id": "M_Tos0xLzyQzNa6Wry6MM",
			"type": "image",
			"x": 1119.197897616567,
			"y": 572.3270796431877,
			"width": 813.0553561572385,
			"height": 295.2971883821082,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 1773741178,
			"version": 270,
			"versionNonce": 583488762,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686907043606,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3439630805cffc85e254198df1a4295adedb12b5",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "5G0myKHyjnK_xhgj48GsM",
			"type": "image",
			"x": 250.1691651647934,
			"y": 566.9426274895843,
			"width": 739.1634402737045,
			"height": 301.825071445096,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 623006330,
			"version": 149,
			"versionNonce": 1468946874,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686907040839,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6d90bdccfca56f975b33d3133f8cc7afb335fd4e",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "cOYWNNdr",
			"type": "text",
			"x": -162.959678505415,
			"y": 1201.3000970207509,
			"width": 292.96875,
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
			"seed": 1283808314,
			"version": 75,
			"versionNonce": 1013718522,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "5uDJbxE4MrQXUQ5JygzYj",
					"type": "arrow"
				}
			],
			"updated": 1686907214080,
			"link": null,
			"locked": false,
			"text": "doBuildPlan:286, Planner \ngetPlan:458, Planner ",
			"rawText": "doBuildPlan:286, Planner \ngetPlan:458, Planner ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "doBuildPlan:286, Planner \ngetPlan:458, Planner ",
			"lineHeight": 1.2
		},
		{
			"id": "b3YRD9sl",
			"type": "text",
			"x": 433.3878139155063,
			"y": 1200.9928967052706,
			"width": 375,
			"height": 96,
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
			"seed": 787682746,
			"version": 16,
			"versionNonce": 373408934,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "5uDJbxE4MrQXUQ5JygzYj",
					"type": "arrow"
				},
				{
					"id": "S-LLLN3xz_JCwsjHrI26g",
					"type": "arrow"
				}
			],
			"updated": 1686907224284,
			"link": null,
			"locked": false,
			"text": "accept:247, AbstractRelNode \nvisit:298, ToLogicalRelVisitor \ncreate:68, LogicalMerge \nbuildInputRel:705, LogicalMerge ",
			"rawText": "accept:247, AbstractRelNode \nvisit:298, ToLogicalRelVisitor \ncreate:68, LogicalMerge \nbuildInputRel:705, LogicalMerge ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 92,
			"containerId": null,
			"originalText": "accept:247, AbstractRelNode \nvisit:298, ToLogicalRelVisitor \ncreate:68, LogicalMerge \nbuildInputRel:705, LogicalMerge ",
			"lineHeight": 1.2
		},
		{
			"id": "6doxMYby",
			"type": "text",
			"x": 441.77438252811885,
			"y": 1730.8315208247018,
			"width": 773.4375,
			"height": 264,
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
			"seed": 301812262,
			"version": 61,
			"versionNonce": 2104114362,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "S-LLLN3xz_JCwsjHrI26g",
					"type": "arrow"
				},
				{
					"id": "e2FatJsP344PG8OVejIvx",
					"type": "arrow"
				}
			],
			"updated": 1686907267782,
			"link": null,
			"locked": false,
			"text": "STEP 1: Build the innermost JOIN between input and action_groups\n(which duplicates the UPDATEed rows for INSERT and DELETE actions)\n\nSTEP 2: Build the inner aggregation on top of the JOIN\n(which aggregates the rows by action_group and mpid)\n\nSTEP 3: Build the projection on top of the inner aggregation\n(which calls the STAGE_DELETION_MARK function)\n\nSTEP 4: Build the outermost aggregation\n(which aggregates the rows by action_group)",
			"rawText": "STEP 1: Build the innermost JOIN between input and action_groups\n(which duplicates the UPDATEed rows for INSERT and DELETE actions)\n\nSTEP 2: Build the inner aggregation on top of the JOIN\n(which aggregates the rows by action_group and mpid)\n\nSTEP 3: Build the projection on top of the inner aggregation\n(which calls the STAGE_DELETION_MARK function)\n\nSTEP 4: Build the outermost aggregation\n(which aggregates the rows by action_group)",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 260,
			"containerId": null,
			"originalText": "STEP 1: Build the innermost JOIN between input and action_groups\n(which duplicates the UPDATEed rows for INSERT and DELETE actions)\n\nSTEP 2: Build the inner aggregation on top of the JOIN\n(which aggregates the rows by action_group and mpid)\n\nSTEP 3: Build the projection on top of the inner aggregation\n(which calls the STAGE_DELETION_MARK function)\n\nSTEP 4: Build the outermost aggregation\n(which aggregates the rows by action_group)",
			"lineHeight": 1.2
		},
		{
			"id": "UjnONYTA",
			"type": "text",
			"x": 1905.6453258549593,
			"y": 1146.188360423581,
			"width": 1289.0625,
			"height": 1416,
			"angle": 0,
			"strokeColor": "#d9480f",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 2112285798,
			"version": 93,
			"versionNonce": 892769658,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "e2FatJsP344PG8OVejIvx",
					"type": "arrow"
				}
			],
			"updated": 1686907267782,
			"link": null,
			"locked": false,
			"text": "SELECT\n    `SYS$ACTION_GROUP`,\n    (__FIRST_VALUE(`SYS$DATA_FILE_METADATA`)) AS `SYS$DATA_FILE_METADATA`, \n    (CSV_FILE_AGG(\n        `SYS$STORAGE_NAME`, `SYS$CSV_DELIMITER`,\n        `__sys_mp_id__`, `SYS$DELETION_MARK_METADATA`\n    )) AS `SYS$DELETION_MARK_METADATA`\nFROM (\n    SELECT\n        `t`.`SYS$ACTION_GROUP`,\n        `t5`.`__sys_mp_id__`,\n        (SINK_DELTA_DATA(\n            `t5`.`id`, `t5`.`msg`,\n            (CASE WHEN (`t`.`SYS$ACTION_GROUP` = 2) THEN `t5`.`__sys_mp_id__` ELSE '!IGNORE THIS ROW!' END),\n            `t5`.`__sys_mp_rid__`,\n            `t5`.`__sys_cts__`,\n            `t5`.`__sys_xts__`,\n            `t5`.`__sys_mp_row_cnt__`,\n            `t5`.`__sys_mp_mod_ts__`\n        )) AS `SYS$DATA_FILE_METADATA`,\n        STAGE_DELETION_MARK(\n            's3x', `t5`.`__sys_mp_id__`,\n            (__FIRST_VALUE(`t5`.`__sys_mp_row_cnt__`)),\n            (__FIRST_VALUE(`t5`.`__sys_mp_mod_ts__`)),\n            BITMAP_CONSTRUCT_AGG(`t5`.`__sys_mp_rid__`)\n        ) AS `SYS$DELETION_MARK_METADATA`,\n        's3x' AS `SYS$STORAGE_NAME`,\n        (CASE WHEN (`t`.`SYS$ACTION_GROUP` = 1) THEN '|' ELSE NULL END) AS `SYS$CSV_DELIMITER`\n    FROM\n        VALUES(2),(1) AS `t` (`SYS$ACTION_GROUP`)\n    INNER JOIN (\n        SELECT\n            (CASE WHEN `SYS$MATCHED0` THEN 0 WHEN `SYS$UNMATCHED0` THEN 2 ELSE 3 END) AS `SYS$ACTION`,\n            (CASE WHEN `SYS$MATCHED0` THEN `id` WHEN `SYS$UNMATCHED0` THEN `id0` ELSE `id` END) AS `id`,\n            (CASE WHEN `SYS$MATCHED0` THEN 'world' WHEN `SYS$UNMATCHED0` THEN `msg0` ELSE `msg` END) AS `msg`,\n            `__sys_mp_id__`, `__sys_mp_rid__`,\n            `__sys_cts__`, `__sys_xts__`,\n            `__sys_mp_row_cnt__`, `__sys_mp_mod_ts__`\n        FROM (\n            SELECT\n                `t0`.`id`, `t0`.`msg`,\n                `t0`.`__sys_mp_id__`, `t0`.`__sys_mp_rid__`,\n                `t0`.`__sys_cts__`, `t0`.`__sys_xts__`,\n                `t0`.`__sys_mp_row_cnt__`, `t0`.`__sys_mp_mod_ts__`,\n                `t2`.`id` AS `id0`, `t2`.`msg` AS `msg0`,\n                (CASE WHEN (`t0`.`__sys_mp_id__` IS NOT NULL) THEN TRUE ELSE FALSE END) AS `SYS$MATCHED0`,\n                (CASE WHEN (`t0`.`__sys_mp_id__` IS NULL) THEN TRUE ELSE FALSE END) AS `SYS$UNMATCHED0`\n            FROM `t` AS `t0`\n            RIGHT JOIN (\n                SELECT 1 AS `id`, 'hello' AS `msg`\n            ) AS `t2`\n            ON (`t0`.`id` = `t2`.`id`)\n        ) AS `t3`\n        WHERE (`SYS$MATCHED0` OR `SYS$UNMATCHED0`)\n    ) AS `t5`\n    ON ((`t`.`SYS$ACTION_GROUP` = `t5`.`SYS$ACTION`) OR (`t5`.`SYS$ACTION` = 0))\n    GROUP BY `t`.`SYS$ACTION_GROUP`, `t5`.`__sys_mp_id__`\n) AS `t8`\nGROUP BY `SYS$ACTION_GROUP`",
			"rawText": "SELECT\n    `SYS$ACTION_GROUP`,\n    (__FIRST_VALUE(`SYS$DATA_FILE_METADATA`)) AS `SYS$DATA_FILE_METADATA`, \n    (CSV_FILE_AGG(\n        `SYS$STORAGE_NAME`, `SYS$CSV_DELIMITER`,\n        `__sys_mp_id__`, `SYS$DELETION_MARK_METADATA`\n    )) AS `SYS$DELETION_MARK_METADATA`\nFROM (\n    SELECT\n        `t`.`SYS$ACTION_GROUP`,\n        `t5`.`__sys_mp_id__`,\n        (SINK_DELTA_DATA(\n            `t5`.`id`, `t5`.`msg`,\n            (CASE WHEN (`t`.`SYS$ACTION_GROUP` = 2) THEN `t5`.`__sys_mp_id__` ELSE '!IGNORE THIS ROW!' END),\n            `t5`.`__sys_mp_rid__`,\n            `t5`.`__sys_cts__`,\n            `t5`.`__sys_xts__`,\n            `t5`.`__sys_mp_row_cnt__`,\n            `t5`.`__sys_mp_mod_ts__`\n        )) AS `SYS$DATA_FILE_METADATA`,\n        STAGE_DELETION_MARK(\n            's3x', `t5`.`__sys_mp_id__`,\n            (__FIRST_VALUE(`t5`.`__sys_mp_row_cnt__`)),\n            (__FIRST_VALUE(`t5`.`__sys_mp_mod_ts__`)),\n            BITMAP_CONSTRUCT_AGG(`t5`.`__sys_mp_rid__`)\n        ) AS `SYS$DELETION_MARK_METADATA`,\n        's3x' AS `SYS$STORAGE_NAME`,\n        (CASE WHEN (`t`.`SYS$ACTION_GROUP` = 1) THEN '|' ELSE NULL END) AS `SYS$CSV_DELIMITER`\n    FROM\n        VALUES(2),(1) AS `t` (`SYS$ACTION_GROUP`)\n    INNER JOIN (\n        SELECT\n            (CASE WHEN `SYS$MATCHED0` THEN 0 WHEN `SYS$UNMATCHED0` THEN 2 ELSE 3 END) AS `SYS$ACTION`,\n            (CASE WHEN `SYS$MATCHED0` THEN `id` WHEN `SYS$UNMATCHED0` THEN `id0` ELSE `id` END) AS `id`,\n            (CASE WHEN `SYS$MATCHED0` THEN 'world' WHEN `SYS$UNMATCHED0` THEN `msg0` ELSE `msg` END) AS `msg`,\n            `__sys_mp_id__`, `__sys_mp_rid__`,\n            `__sys_cts__`, `__sys_xts__`,\n            `__sys_mp_row_cnt__`, `__sys_mp_mod_ts__`\n        FROM (\n            SELECT\n                `t0`.`id`, `t0`.`msg`,\n                `t0`.`__sys_mp_id__`, `t0`.`__sys_mp_rid__`,\n                `t0`.`__sys_cts__`, `t0`.`__sys_xts__`,\n                `t0`.`__sys_mp_row_cnt__`, `t0`.`__sys_mp_mod_ts__`,\n                `t2`.`id` AS `id0`, `t2`.`msg` AS `msg0`,\n                (CASE WHEN (`t0`.`__sys_mp_id__` IS NOT NULL) THEN TRUE ELSE FALSE END) AS `SYS$MATCHED0`,\n                (CASE WHEN (`t0`.`__sys_mp_id__` IS NULL) THEN TRUE ELSE FALSE END) AS `SYS$UNMATCHED0`\n            FROM `t` AS `t0`\n            RIGHT JOIN (\n                SELECT 1 AS `id`, 'hello' AS `msg`\n            ) AS `t2`\n            ON (`t0`.`id` = `t2`.`id`)\n        ) AS `t3`\n        WHERE (`SYS$MATCHED0` OR `SYS$UNMATCHED0`)\n    ) AS `t5`\n    ON ((`t`.`SYS$ACTION_GROUP` = `t5`.`SYS$ACTION`) OR (`t5`.`SYS$ACTION` = 0))\n    GROUP BY `t`.`SYS$ACTION_GROUP`, `t5`.`__sys_mp_id__`\n) AS `t8`\nGROUP BY `SYS$ACTION_GROUP`",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 1412,
			"containerId": null,
			"originalText": "SELECT\n    `SYS$ACTION_GROUP`,\n    (__FIRST_VALUE(`SYS$DATA_FILE_METADATA`)) AS `SYS$DATA_FILE_METADATA`, \n    (CSV_FILE_AGG(\n        `SYS$STORAGE_NAME`, `SYS$CSV_DELIMITER`,\n        `__sys_mp_id__`, `SYS$DELETION_MARK_METADATA`\n    )) AS `SYS$DELETION_MARK_METADATA`\nFROM (\n    SELECT\n        `t`.`SYS$ACTION_GROUP`,\n        `t5`.`__sys_mp_id__`,\n        (SINK_DELTA_DATA(\n            `t5`.`id`, `t5`.`msg`,\n            (CASE WHEN (`t`.`SYS$ACTION_GROUP` = 2) THEN `t5`.`__sys_mp_id__` ELSE '!IGNORE THIS ROW!' END),\n            `t5`.`__sys_mp_rid__`,\n            `t5`.`__sys_cts__`,\n            `t5`.`__sys_xts__`,\n            `t5`.`__sys_mp_row_cnt__`,\n            `t5`.`__sys_mp_mod_ts__`\n        )) AS `SYS$DATA_FILE_METADATA`,\n        STAGE_DELETION_MARK(\n            's3x', `t5`.`__sys_mp_id__`,\n            (__FIRST_VALUE(`t5`.`__sys_mp_row_cnt__`)),\n            (__FIRST_VALUE(`t5`.`__sys_mp_mod_ts__`)),\n            BITMAP_CONSTRUCT_AGG(`t5`.`__sys_mp_rid__`)\n        ) AS `SYS$DELETION_MARK_METADATA`,\n        's3x' AS `SYS$STORAGE_NAME`,\n        (CASE WHEN (`t`.`SYS$ACTION_GROUP` = 1) THEN '|' ELSE NULL END) AS `SYS$CSV_DELIMITER`\n    FROM\n        VALUES(2),(1) AS `t` (`SYS$ACTION_GROUP`)\n    INNER JOIN (\n        SELECT\n            (CASE WHEN `SYS$MATCHED0` THEN 0 WHEN `SYS$UNMATCHED0` THEN 2 ELSE 3 END) AS `SYS$ACTION`,\n            (CASE WHEN `SYS$MATCHED0` THEN `id` WHEN `SYS$UNMATCHED0` THEN `id0` ELSE `id` END) AS `id`,\n            (CASE WHEN `SYS$MATCHED0` THEN 'world' WHEN `SYS$UNMATCHED0` THEN `msg0` ELSE `msg` END) AS `msg`,\n            `__sys_mp_id__`, `__sys_mp_rid__`,\n            `__sys_cts__`, `__sys_xts__`,\n            `__sys_mp_row_cnt__`, `__sys_mp_mod_ts__`\n        FROM (\n            SELECT\n                `t0`.`id`, `t0`.`msg`,\n                `t0`.`__sys_mp_id__`, `t0`.`__sys_mp_rid__`,\n                `t0`.`__sys_cts__`, `t0`.`__sys_xts__`,\n                `t0`.`__sys_mp_row_cnt__`, `t0`.`__sys_mp_mod_ts__`,\n                `t2`.`id` AS `id0`, `t2`.`msg` AS `msg0`,\n                (CASE WHEN (`t0`.`__sys_mp_id__` IS NOT NULL) THEN TRUE ELSE FALSE END) AS `SYS$MATCHED0`,\n                (CASE WHEN (`t0`.`__sys_mp_id__` IS NULL) THEN TRUE ELSE FALSE END) AS `SYS$UNMATCHED0`\n            FROM `t` AS `t0`\n            RIGHT JOIN (\n                SELECT 1 AS `id`, 'hello' AS `msg`\n            ) AS `t2`\n            ON (`t0`.`id` = `t2`.`id`)\n        ) AS `t3`\n        WHERE (`SYS$MATCHED0` OR `SYS$UNMATCHED0`)\n    ) AS `t5`\n    ON ((`t`.`SYS$ACTION_GROUP` = `t5`.`SYS$ACTION`) OR (`t5`.`SYS$ACTION` = 0))\n    GROUP BY `t`.`SYS$ACTION_GROUP`, `t5`.`__sys_mp_id__`\n) AS `t8`\nGROUP BY `SYS$ACTION_GROUP`",
			"lineHeight": 1.2
		},
		{
			"id": "duwSy1Ei",
			"type": "text",
			"x": 674.6731817042672,
			"y": 1508.5413725431392,
			"width": 128.90625,
			"height": 24,
			"angle": 0,
			"strokeColor": "#1864ab",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 884236858,
			"version": 56,
			"versionNonce": 1929421734,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686907252237,
			"link": null,
			"locked": false,
			"text": "t3 as input",
			"rawText": "t3 as input",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "t3 as input",
			"lineHeight": 1.2
		},
		{
			"id": "HF6JqAEm",
			"type": "text",
			"x": 460.95392222460544,
			"y": 1129.0158627882308,
			"width": 292.96875,
			"height": 24,
			"angle": 0,
			"strokeColor": "#1864ab",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 699083494,
			"version": 61,
			"versionNonce": 269554022,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686907189672,
			"link": null,
			"locked": false,
			"text": "RelNode to LogicalRelNode",
			"rawText": "RelNode to LogicalRelNode",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "RelNode to LogicalRelNode",
			"lineHeight": 1.2
		},
		{
			"id": "5uDJbxE4MrQXUQ5JygzYj",
			"type": "arrow",
			"x": 142.34623502944498,
			"y": 1224.8521212075752,
			"width": 281.8870094847455,
			"height": 1.8841619349459506,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 314982246,
			"version": 35,
			"versionNonce": 833786342,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686907216783,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					281.8870094847455,
					-1.8841619349459506
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "cOYWNNdr",
				"focus": 0.0245646709103529,
				"gap": 12.337163534859997
			},
			"endBinding": {
				"elementId": "b3YRD9sl",
				"focus": 0.5550778101430486,
				"gap": 9.154569401315825
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "S-LLLN3xz_JCwsjHrI26g",
			"type": "arrow",
			"x": 623.0635287035722,
			"y": 1311.2573299416747,
			"width": 0.2457602523843434,
			"height": 398.3261690623042,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 647193894,
			"version": 77,
			"versionNonce": 744714854,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686907237779,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.2457602523843434,
					398.3261690623042
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "b3YRD9sl",
				"focus": -0.01139712639107401,
				"gap": 14.264433236404102
			},
			"endBinding": {
				"elementId": "6doxMYby",
				"focus": -0.5302202445698904,
				"gap": 21.248021820722897
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "e2FatJsP344PG8OVejIvx",
			"type": "arrow",
			"x": 1231.258713291518,
			"y": 1852.984606270194,
			"width": 660.644518450953,
			"height": 5.83680599412628,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 456071846,
			"version": 50,
			"versionNonce": 317752294,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686907267782,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					660.644518450953,
					5.83680599412628
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "6doxMYby",
				"focus": -0.09899339479730075,
				"gap": 16.046830763399157
			},
			"endBinding": {
				"elementId": "UjnONYTA",
				"focus": -0.014640590999612997,
				"gap": 13.74209411248819
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "HneJc3x8KIkcvKTu0bfEn",
			"type": "arrow",
			"x": 116.49020847651843,
			"y": 323.6185556829484,
			"width": 298.4451064891349,
			"height": 0.40960042064045865,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 1650541158,
			"version": 59,
			"versionNonce": 511104186,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686907360151,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					298.4451064891349,
					-0.40960042064045865
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "T2YvxmYh",
				"focus": -0.00024729855346301453,
				"gap": 17.02708835119222
			},
			"endBinding": {
				"elementId": "9uYQFyx8",
				"focus": -0.017274672856291712,
				"gap": 21.8726624622019
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "gg7Lm-qDgbIKvE0YoyO6i",
			"type": "arrow",
			"x": 844.2579958599224,
			"y": 315.2115070493035,
			"width": 263.94651106069455,
			"height": 1.5257615668856488,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 955264378,
			"version": 40,
			"versionNonce": 28011642,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686907366678,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					263.94651106069455,
					1.5257615668856488
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "9uYQFyx8",
				"focus": -0.10519006975505485,
				"gap": 20.731268432067168
			},
			"endBinding": {
				"elementId": "Lys4XXnp",
				"focus": 0.13414027219077415,
				"gap": 14.888975290282815
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Iio8whLJ9ODT7GSdShfMf",
			"type": "arrow",
			"x": 155.20768823755589,
			"y": 4.396467856827144,
			"width": 368.78373872361306,
			"height": 4.413444532400717,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 427955706,
			"version": 54,
			"versionNonce": 129389114,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686907489809,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					368.78373872361306,
					4.413444532400717
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "1DIuXfc7",
				"focus": 0.0819790907553857,
				"gap": 6.704747923667469
			},
			"endBinding": {
				"elementId": "DcscusZC",
				"focus": -0.32055669129558073,
				"gap": 3.9424040486668446
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "29oVNm9k",
			"type": "text",
			"x": -142.55737162481842,
			"y": 2671.1627152923925,
			"width": 386.71875,
			"height": 72,
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
			"seed": 216835302,
			"version": 52,
			"versionNonce": 1263296506,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686910138919,
			"link": null,
			"locked": false,
			"text": "getPlan:483, Planner \noptimize:514, Planner \nrewriteAndEnumerate:530, Planner ",
			"rawText": "getPlan:483, Planner \noptimize:514, Planner \nrewriteAndEnumerate:530, Planner ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "getPlan:483, Planner \noptimize:514, Planner \nrewriteAndEnumerate:530, Planner ",
			"lineHeight": 1.2
		},
		{
			"id": "yPBCvgW0",
			"type": "text",
			"x": 472.5658118676655,
			"y": 2688.4898298385324,
			"width": 363.28125,
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
			"seed": 189875706,
			"version": 32,
			"versionNonce": 1011131046,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686910332583,
			"link": null,
			"locked": false,
			"text": "1. rbo optimizeBySqlRewriter\n2. cbo optimizeByPlanEnumerator",
			"rawText": "1. rbo optimizeBySqlRewriter\n2. cbo optimizeByPlanEnumerator",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "1. rbo optimizeBySqlRewriter\n2. cbo optimizeByPlanEnumerator",
			"lineHeight": 1.2
		},
		{
			"id": "r2wpXwWB",
			"type": "text",
			"x": 1135.9059583850171,
			"y": 4738.092218209263,
			"width": 316.40625,
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
			"seed": 654117862,
			"version": 547,
			"versionNonce": 1606940518,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686920084613,
			"link": null,
			"locked": false,
			"text": "doNext:70, MppResultCursor ",
			"rawText": "doNext:70, MppResultCursor ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "doNext:70, MppResultCursor ",
			"lineHeight": 1.2
		},
		{
			"id": "kLQjngcH",
			"type": "text",
			"x": 1700.3712557774563,
			"y": 4612.993456175683,
			"width": 1183.59375,
			"height": 384,
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
			"seed": 442038010,
			"version": 557,
			"versionNonce": 9521466,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "qsvRuUWKaY-KbmUD6ZbXA",
					"type": "arrow"
				},
				{
					"id": "VOmbLnFiTOtYTdV2dBFBC",
					"type": "arrow"
				}
			],
			"updated": 1686920123236,
			"link": null,
			"locked": false,
			"text": "while (client.isValid()) {\n    QueryResults clientResults = client.current();\n    QueryError queryError = clientResults.getError();\n    if (queryError != null) {\n        log.error(\"MppError:\" + ec.getTraceId() + \",SchemaName=\" + ec.getSchemaName() + \",stackInfo=\"\n            + queryError.getFailureInfo());\n        throw GeneralUtil.nestedException(queryError.toException());\n    }\n    Iterable<Object> data = clientResults.getData();\n    if (data != null) {\n        currentChunks = data.iterator();\n        client.advance();\n        break;\n    }\n    client.advance();\n}",
			"rawText": "while (client.isValid()) {\n    QueryResults clientResults = client.current();\n    QueryError queryError = clientResults.getError();\n    if (queryError != null) {\n        log.error(\"MppError:\" + ec.getTraceId() + \",SchemaName=\" + ec.getSchemaName() + \",stackInfo=\"\n            + queryError.getFailureInfo());\n        throw GeneralUtil.nestedException(queryError.toException());\n    }\n    Iterable<Object> data = clientResults.getData();\n    if (data != null) {\n        currentChunks = data.iterator();\n        client.advance();\n        break;\n    }\n    client.advance();\n}",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 380,
			"containerId": null,
			"originalText": "while (client.isValid()) {\n    QueryResults clientResults = client.current();\n    QueryError queryError = clientResults.getError();\n    if (queryError != null) {\n        log.error(\"MppError:\" + ec.getTraceId() + \",SchemaName=\" + ec.getSchemaName() + \",stackInfo=\"\n            + queryError.getFailureInfo());\n        throw GeneralUtil.nestedException(queryError.toException());\n    }\n    Iterable<Object> data = clientResults.getData();\n    if (data != null) {\n        currentChunks = data.iterator();\n        client.advance();\n        break;\n    }\n    client.advance();\n}",
			"lineHeight": 1.2
		},
		{
			"id": "wAK47JKj",
			"type": "text",
			"x": 1165.5622167347763,
			"y": 4798.451436043108,
			"width": 210.9375,
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
			"seed": 705650214,
			"version": 399,
			"versionNonce": 1505020282,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686920089865,
			"link": null,
			"locked": false,
			"text": "poll: get results?",
			"rawText": "poll: get results?",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "poll: get results?",
			"lineHeight": 1.2
		},
		{
			"id": "a2p7ZaZu",
			"type": "text",
			"x": 1696.3616992072689,
			"y": 5164.408472745863,
			"width": 199.21875,
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
			"seed": 1335754022,
			"version": 474,
			"versionNonce": 1638557306,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686920138166,
			"link": null,
			"locked": false,
			"text": "set current chunk",
			"rawText": "set current chunk",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "set current chunk",
			"lineHeight": 1.2
		},
		{
			"id": "UcGCliBx",
			"type": "text",
			"x": 643.9344233590705,
			"y": 4154.589695282455,
			"width": 421.875,
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
			"seed": 190053798,
			"version": 266,
			"versionNonce": 1808876774,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "pOf4DlLwlHg3TCLYdvF_a",
					"type": "arrow"
				},
				{
					"id": "gGWQ5_Xdqd1_a2K92XQW8",
					"type": "arrow"
				}
			],
			"updated": 1686920157210,
			"link": null,
			"locked": false,
			"text": "fetchInput:105, LogicalMergeHandler \nexecuteCluster:116, ExecutorHelper",
			"rawText": "fetchInput:105, LogicalMergeHandler \nexecuteCluster:116, ExecutorHelper",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "fetchInput:105, LogicalMergeHandler \nexecuteCluster:116, ExecutorHelper",
			"lineHeight": 1.2
		},
		{
			"id": "36Gn94ZP",
			"type": "text",
			"x": 641.1431335446224,
			"y": 5080.476946086672,
			"width": 410.15625,
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
			"seed": 138822266,
			"version": 243,
			"versionNonce": 1451845926,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "gGWQ5_Xdqd1_a2K92XQW8",
					"type": "arrow"
				},
				{
					"id": "RHNrjlMN1MonkBEdHilbx",
					"type": "arrow"
				}
			],
			"updated": 1686920162993,
			"link": null,
			"locked": false,
			"text": "fetchInput:107, LogicalMergeHandler",
			"rawText": "fetchInput:107, LogicalMergeHandler",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "fetchInput:107, LogicalMergeHandler",
			"lineHeight": 1.2
		},
		{
			"id": "Jr6MzTlJ",
			"type": "text",
			"x": 1554.7651285171178,
			"y": 4128.203796859996,
			"width": 433.59375,
			"height": 72,
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
			"seed": 1182956922,
			"version": 20,
			"versionNonce": 1219302138,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686920008064,
			"link": null,
			"locked": false,
			"text": "execute:56, MppRunner \ncreateQuery:54, LocalStatementClient \ncreateQuery:153, StatementResource ",
			"rawText": "execute:56, MppRunner \ncreateQuery:54, LocalStatementClient \ncreateQuery:153, StatementResource ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "execute:56, MppRunner \ncreateQuery:54, LocalStatementClient \ncreateQuery:153, StatementResource ",
			"lineHeight": 1.2
		},
		{
			"id": "qsvRuUWKaY-KbmUD6ZbXA",
			"type": "arrow",
			"x": 1065.2878305259046,
			"y": 5061.414078589177,
			"width": 606.2353089943836,
			"height": 417.3963433710587,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 1283875494,
			"version": 31,
			"versionNonce": 309900134,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686920030098,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					606.2353089943836,
					-417.3963433710587
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "kLQjngcH",
				"focus": 0.9813794448267973,
				"gap": 28.848116257168044
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "VOmbLnFiTOtYTdV2dBFBC",
			"type": "arrow",
			"x": 1705.7082300713496,
			"y": 5020.480634427891,
			"width": 161.23803516399016,
			"height": 223.1061529336348,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 1429981178,
			"version": 137,
			"versionNonce": 672915898,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686920134123,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-60.88295665866349,
					127.59478322396717
				],
				[
					-161.23803516399016,
					223.1061529336348
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "kLQjngcH",
				"focus": 0.7076826186333337,
				"gap": 23.48717825220865
			},
			"endBinding": {
				"elementId": "QWwM9Zic",
				"focus": 0.8079689337263227,
				"gap": 3.596726002016794
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "pOf4DlLwlHg3TCLYdvF_a",
			"type": "arrow",
			"x": 825.2533258352349,
			"y": 3844.493816249144,
			"width": 1.346386851674879,
			"height": 305.62981533019547,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 2068547386,
			"version": 35,
			"versionNonce": 103872678,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686920151800,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.346386851674879,
					305.62981533019547
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "sQSk4vA7",
				"focus": -0.01401931584462873,
				"gap": 1
			},
			"endBinding": {
				"elementId": "UcGCliBx",
				"focus": -0.1473176182811992,
				"gap": 4.466063703115651
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "gGWQ5_Xdqd1_a2K92XQW8",
			"type": "arrow",
			"x": 838.2410331483425,
			"y": 4206.195718146042,
			"width": 3.8585476846778874,
			"height": 871.9496799779736,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 334439802,
			"version": 40,
			"versionNonce": 1753113722,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686920157211,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-3.8585476846778874,
					871.9496799779736
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "UcGCliBx",
				"focus": 0.07822421517179978,
				"gap": 3.606022863586986
			},
			"endBinding": {
				"elementId": "36Gn94ZP",
				"focus": -0.05802233591977672,
				"gap": 2.331547962656259
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "RHNrjlMN1MonkBEdHilbx",
			"type": "arrow",
			"x": 853.6259658315055,
			"y": 5116.4353266375,
			"width": 3.1853542588403343,
			"height": 295.0393333871434,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 2026226534,
			"version": 39,
			"versionNonce": 1073325114,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686920162993,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.1853542588403343,
					295.0393333871434
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "36Gn94ZP",
				"focus": -0.03482347082938029,
				"gap": 11.958380550828224
			},
			"endBinding": {
				"elementId": "L6A6ndyh",
				"focus": -0.07308481949719962,
				"gap": 9.652903605429856
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "r8X4n-BEZEaSes5U4y7ua",
			"type": "arrow",
			"x": 868.9944791628186,
			"y": 5478.876099367635,
			"width": 0,
			"height": 150.56545646168888,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 41015206,
			"version": 34,
			"versionNonce": 1848534758,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1686920167812,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					150.56545646168888
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "L6A6ndyh",
				"focus": 0.023962404766244002,
				"gap": 9.748535737561724
			},
			"endBinding": {
				"elementId": "KtysKtCp",
				"focus": -0.0025744568726076976,
				"gap": 4.690838235738738
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "EzOQiOqHvWQ1jdaGeejqI",
			"type": "arrow",
			"x": 819.2845859927447,
			"y": 3946.2102969243997,
			"width": 33.48491724859309,
			"height": 131.96131208140287,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 785619578,
			"version": 1150,
			"versionNonce": 1075538618,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1686919479856,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					33.48491724859309,
					131.96131208140287
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "L6A6ndyh",
				"focus": -0.052382918954594994,
				"gap": 9.835939243954954
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "wdNfdw9J",
			"type": "text",
			"x": 2110.2816960069204,
			"y": 119.07434562563355,
			"width": 46.875,
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
			"seed": 411329638,
			"version": 6,
			"versionNonce": 632858426,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1686827198089,
			"link": null,
			"locked": false,
			"text": "stmt",
			"rawText": "stmt",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "stmt",
			"lineHeight": 1.2
		},
		{
			"id": "Kkvjj11x",
			"type": "text",
			"x": 431.8620523486203,
			"y": 1477.7087008794306,
			"width": 11.71875,
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
			"seed": 203898938,
			"version": 6,
			"versionNonce": 1437931238,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1686906499427,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.2
		},
		{
			"id": "5At2zN6c",
			"type": "text",
			"x": 908.6881420266617,
			"y": 1338.6903181140674,
			"width": 11.71875,
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
			"seed": 891793318,
			"version": 2,
			"versionNonce": 1445529018,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1686907241540,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.2
		},
		{
			"id": "EsBuOdAI",
			"type": "text",
			"x": 514.068073363292,
			"y": 2682.1514184512503,
			"width": 11.71875,
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
			"seed": 572764134,
			"version": 12,
			"versionNonce": 154205498,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1686910281576,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.2
		},
		{
			"id": "cLjtB7lw",
			"type": "text",
			"x": -695.2862711309326,
			"y": 1825.888520059886,
			"width": 11.71875,
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
			"seed": 1584465062,
			"version": 2,
			"versionNonce": 1082884282,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1686919093332,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.2
		},
		{
			"id": "-TXVbzBYmWQ4uafSt6srZ",
			"type": "arrow",
			"x": 1071.3031429598893,
			"y": 4552.708967356105,
			"width": 801.4757486798251,
			"height": 522.3633919028935,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 1848921446,
			"version": 887,
			"versionNonce": 1513636730,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1686920005558,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					801.4757486798251,
					-522.3633919028935
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "kLQjngcH",
				"focus": 1.1241232284895943,
				"gap": 13.671281429884402
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "uS7aaOVXxKAVyAUT0Git5",
			"type": "arrow",
			"x": 1934.0536946458242,
			"y": 4151.9904601057315,
			"width": 391.1441498797483,
			"height": 620.0222903934512,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 439290106,
			"version": 732,
			"versionNonce": 1924741798,
			"isDeleted": true,
			"boundElements": [],
			"updated": 1686920003264,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-319.93613638915576,
					532.5143542366698
				],
				[
					-391.1441498797483,
					620.0222903934512
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "kLQjngcH",
				"focus": 0.9341222367250713,
				"gap": 12.180935728943155
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "9ulCi7vy",
			"type": "text",
			"x": -512.0712372053513,
			"y": 1877.9147101727197,
			"width": 11.71875,
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
			"seed": 586408890,
			"version": 3,
			"versionNonce": 1510325562,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1686919153026,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 20,
			"containerId": "uS7aaOVXxKAVyAUT0Git5",
			"originalText": "",
			"lineHeight": 1.2
		},
		{
			"id": "ZbQGB2yd",
			"type": "text",
			"x": -433.9242282069906,
			"y": 1934.0383309249655,
			"width": 11.71875,
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
			"seed": 1690413626,
			"version": 2,
			"versionNonce": 19967590,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1686919152024,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.2
		},
		{
			"id": "49I5QuBk",
			"type": "text",
			"x": -421.907582555315,
			"y": 1882.9675869053447,
			"width": 11.71875,
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
			"seed": 1756950182,
			"version": 2,
			"versionNonce": 1318008506,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1686919154511,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.2
		},
		{
			"id": "E1ffIAKb",
			"type": "text",
			"x": 2277.692771107273,
			"y": 4491.629730701114,
			"width": 292.96875,
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
			"seed": 1039705830,
			"version": 49,
			"versionNonce": 558812774,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1686920094028,
			"link": null,
			"locked": false,
			"text": "get data then break cycle",
			"rawText": "get data then break cycle",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "get data then break cycle",
			"lineHeight": 1.2
		},
		{
			"id": "50zKpQIW7vNirg50-Qxbd",
			"type": "arrow",
			"x": 1708.105455441405,
			"y": 5001.532702393346,
			"width": 279.19465885218824,
			"height": 252.87443783712843,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 1081348518,
			"version": 128,
			"versionNonce": 1140923942,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1686920115486,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					127.47984776102021,
					185.94915969777685
				],
				[
					-151.71481109116803,
					252.87443783712843
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "kLQjngcH",
				"focus": 0.993610587011876,
				"gap": 4.539246217663276
			},
			"endBinding": {
				"elementId": "QWwM9Zic",
				"focus": 0.6381687766181434,
				"gap": 15.517175444894292
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
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
		"scrollX": 175.9494919035256,
		"scrollY": -3119.136109585234,
		"zoom": {
			"value": 0.2379052495956421
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"colorPalette": {},
		"currentStrokeOptions": null,
		"previousGridSize": null
	},
	"files": {}
}
```
%%
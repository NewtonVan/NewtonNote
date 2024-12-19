---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
handle:65, FrontendCommandHandler 
query:453, FrontendConnection 
queryRaw:115, ServerQueryHandler 
executeStatement:144, ServerQueryHandler 
handle:80, SelectHandler 
execute:684, ServerConnection 
execute:701, ServerConnection 
innerExecute:877, ServerConnection 
execute:66, TPreparedStatement 
executeInternal:150, TStatement 
executeSQL:81, TPreparedStatement 
executeSQL:308, TConnection  ^WNHiEd3N

execute:59, PlanExecutor 
execByExecPlanNodeByOne:105, PlanExecutor 
execute:79, ExecutorHelper 
executeCluster:116, ExecutorHelper 
execute:56, MppRunner 
createQuery:54, LocalStatementClient 
createQuery:128, StatementResource 
init:258, StatementResource$Query 
createClusterQuery:408, SqlQueryManager 
start:128, SqlQueryExecution 
buildRootFragment:81, PlanFragmenter  ^DVu0JGRf

visit:242, PlanFragmenter$Fragmenter 
visitChildren:202, PlanFragmenter$Fragmenter 
visitChild:147, PlanFragmenter$Fragmenter 
visit:214, PlanFragmenter$Fragmenter 
visitExchange:316, PlanFragmenter$Fragmenter 
generateFragment:365, PlanFragmenter$Fragmenter 
generateSubPlan:381, PlanFragmenter$Fragmenter  ^ZpAX53rl

getSplits:163, SplitManager 
tableFileScanSplit:296, SplitManager 
build:47, SplitInfoBuilder 
buildSplits:114, SplitInfoBuilder 
apply:-1, SplitInfoBuilder$$Lambda$965/0x000000080164ca80 
lambda$build$1:50, SplitInfoBuilder 
getSplits:112, ORCSplit  ^kJIpGdKn

updateTask:285, SqlTaskManager 
updateTask:547, SqlTask 
bootstrapTask:575, SqlTask 
create:77, SqlTaskExecutionFactory 
createSqlTaskExecution:109, SqlTaskExecution 
<init>:184, SqlTaskExecution 
start:219, SqlTaskExecution 
createDriverExec:46, PipelineFactory 
createExecutor:126, LogicalViewExecutorFactory 
buildTableFileScanExec:179, LogicalViewExecutorFactory  ^3P3DOMk2

async call ^BjZxwAHZ

AsyncTableFileScanExec ^3ImJ0DlN



<init>:186, SqlTaskExecution 
addSources:243, SqlTaskExecution 
updateSources:295, SqlTaskExecution 
schedulePartitionedSource:379, SqlTaskExecution 
updateSource:227, Driver 
close:604, Driver$DriverLockResult 
processNewSources:247, Driver 
processNewSource:318, Driver 
addSplit:82, AsyncTableFileScanExec 
addSplit:164, TableFileScanClient 
initSplit:356, TableFileScanClient$ClientInitializer 
init:194, ORCSplit  ^qSjqwGoA

Split.Init ^gmHlidb0

run:833, Thread 
run:635, ThreadPoolExecutor$Worker 
runWorker:1136, ThreadPoolExecutor 
run:540, TaskExecutor$ApRunner 
process:408, TaskExecutor$PrioritizedSplitRunner 
processFor:57, DriverSplitRunner 
processFor:337, Driver 
processInternal:469, Driver 
open:133, DriverExec 
open:99, AbstractExecutor 
doOpen:102, AsyncTableFileScanExec 
startPrefetchThread:155, TableFileScanClient 
submit:195, ServerThreadPool 
newTaskForCallable:296, ServerThreadPool 
<init>:621, ServerThreadPool$NamedFutureTask 
<init>:132, FutureTask  ^qbMOZCuQ

run:-1, FutureTask 
run$$$capture:264, FutureTask 
call:693, ServerThreadPool$CallableAdapter 
call:50, CallableWithCpuCollector 
call:38, CallableWithStatHandler 
call:305, TableFileScanClient$PrefetchThread 
processFile:325, TableFileScanClient$PrefetchThread  ^5yXytsjZ

prefetch ^A7JxdwQm

processFile:333, TableFileScanClient$PrefetchThread 
fetchToBuffer:334, ORCReaderTask 
fetchPushDownResults:332, FileReaderTask 
apply:-1, FileReaderTask$$Lambda$1494/0x00000008018a9cf0 
lambda$initializeSinkDeltaDataHandlers$7:370, FileReaderTask  ^zNrtc290

fetchPushDownResults:346, FileReaderTask 
lambda$initializeSinkDeltaDataHandlers$8:375, FileReaderTask 
runSinkDeltaDataTasks:268, FileReaderTask 
<init>:151, FutureTask 
 - Async stack trace
run:-1, FutureTask 
run$$$capture:264, FutureTask 
call:539, Executors$RunnableAdapter 
run:-1, FileReaderTask$$Lambda$2541/0x0000000801a662b8 
lambda$runSinkDeltaDataTasks$2:272, FileReaderTask 
fetchChunk:379, ORCReaderTask 
fetchChunkInternal:388, ORCReaderTask  ^AoaimP8N

fetchChunkInternal:399, ORCReaderTask 
readBlock:121, OrcRecordReader 
readBlock:133, AbstractColumnReader 
openRowGroup:106, AbstractColumnReader  ^Iy9J0coC

Open Row Group, Stream ^H7Phukmg

readBlock:161, AbstractColumnReader  ^oFNe6Hrh

readNonNullBlock:81, LongColumnReader  ^DNHbqfVI

readNonNullBlock:81, SliceDirectColumnReader  ^OxP8Syzz

readNonNullBlock:86, SliceDirectColumnReader 
readDataStream:124, SliceDirectColumnReader  ^OCZ4Y3ZW

processFile:333, TableFileScanClient$PrefetchThread 
fetchToBuffer:337, ORCReaderTask 
fetchRows:257, ORCReaderTask 
fetchChunkInternal:388, ORCReaderTask  ^s8bTQ6oV

Without Agg ^l9I8JUZe

fetch internal ^4paNOMOG

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/1.8.26",
	"elements": [
		{
			"id": "WNHiEd3N",
			"type": "text",
			"x": -391.4921875,
			"y": -38.38671875,
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
			"seed": 1635789480,
			"version": 6,
			"versionNonce": 174202328,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688969311295,
			"link": null,
			"locked": false,
			"text": "handle:65, FrontendCommandHandler \nquery:453, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:144, ServerQueryHandler \nhandle:80, SelectHandler \nexecute:684, ServerConnection \nexecute:701, ServerConnection \ninnerExecute:877, ServerConnection \nexecute:66, TPreparedStatement \nexecuteInternal:150, TStatement \nexecuteSQL:81, TPreparedStatement \nexecuteSQL:308, TConnection ",
			"rawText": "handle:65, FrontendCommandHandler \nquery:453, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:144, ServerQueryHandler \nhandle:80, SelectHandler \nexecute:684, ServerConnection \nexecute:701, ServerConnection \ninnerExecute:877, ServerConnection \nexecute:66, TPreparedStatement \nexecuteInternal:150, TStatement \nexecuteSQL:81, TPreparedStatement \nexecuteSQL:308, TConnection ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 284,
			"containerId": null,
			"originalText": "handle:65, FrontendCommandHandler \nquery:453, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:144, ServerQueryHandler \nhandle:80, SelectHandler \nexecute:684, ServerConnection \nexecute:701, ServerConnection \ninnerExecute:877, ServerConnection \nexecute:66, TPreparedStatement \nexecuteInternal:150, TStatement \nexecuteSQL:81, TPreparedStatement \nexecuteSQL:308, TConnection ",
			"lineHeight": 1.2
		},
		{
			"id": "DVu0JGRf",
			"type": "text",
			"x": -384.81810546824346,
			"y": 400.9287926578746,
			"width": 492.1875,
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
			"seed": 1091609304,
			"version": 3,
			"versionNonce": 1061481176,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "FaqknlqotV_0cvwBq2Qvj",
					"type": "arrow"
				}
			],
			"updated": 1688969553529,
			"link": null,
			"locked": false,
			"text": "execute:59, PlanExecutor \nexecByExecPlanNodeByOne:105, PlanExecutor \nexecute:79, ExecutorHelper \nexecuteCluster:116, ExecutorHelper \nexecute:56, MppRunner \ncreateQuery:54, LocalStatementClient \ncreateQuery:128, StatementResource \ninit:258, StatementResource$Query \ncreateClusterQuery:408, SqlQueryManager \nstart:128, SqlQueryExecution \nbuildRootFragment:81, PlanFragmenter ",
			"rawText": "execute:59, PlanExecutor \nexecByExecPlanNodeByOne:105, PlanExecutor \nexecute:79, ExecutorHelper \nexecuteCluster:116, ExecutorHelper \nexecute:56, MppRunner \ncreateQuery:54, LocalStatementClient \ncreateQuery:128, StatementResource \ninit:258, StatementResource$Query \ncreateClusterQuery:408, SqlQueryManager \nstart:128, SqlQueryExecution \nbuildRootFragment:81, PlanFragmenter ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 260,
			"containerId": null,
			"originalText": "execute:59, PlanExecutor \nexecByExecPlanNodeByOne:105, PlanExecutor \nexecute:79, ExecutorHelper \nexecuteCluster:116, ExecutorHelper \nexecute:56, MppRunner \ncreateQuery:54, LocalStatementClient \ncreateQuery:128, StatementResource \ninit:258, StatementResource$Query \ncreateClusterQuery:408, SqlQueryManager \nstart:128, SqlQueryExecution \nbuildRootFragment:81, PlanFragmenter ",
			"lineHeight": 1.2
		},
		{
			"id": "ZpAX53rl",
			"type": "text",
			"x": 361.11844287822225,
			"y": 440.68567465066485,
			"width": 562.5,
			"height": 168,
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
			"seed": 801669544,
			"version": 16,
			"versionNonce": 1820030168,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688969355781,
			"link": null,
			"locked": false,
			"text": "visit:242, PlanFragmenter$Fragmenter \nvisitChildren:202, PlanFragmenter$Fragmenter \nvisitChild:147, PlanFragmenter$Fragmenter \nvisit:214, PlanFragmenter$Fragmenter \nvisitExchange:316, PlanFragmenter$Fragmenter \ngenerateFragment:365, PlanFragmenter$Fragmenter \ngenerateSubPlan:381, PlanFragmenter$Fragmenter ",
			"rawText": "visit:242, PlanFragmenter$Fragmenter \nvisitChildren:202, PlanFragmenter$Fragmenter \nvisitChild:147, PlanFragmenter$Fragmenter \nvisit:214, PlanFragmenter$Fragmenter \nvisitExchange:316, PlanFragmenter$Fragmenter \ngenerateFragment:365, PlanFragmenter$Fragmenter \ngenerateSubPlan:381, PlanFragmenter$Fragmenter ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 164,
			"containerId": null,
			"originalText": "visit:242, PlanFragmenter$Fragmenter \nvisitChildren:202, PlanFragmenter$Fragmenter \nvisitChild:147, PlanFragmenter$Fragmenter \nvisit:214, PlanFragmenter$Fragmenter \nvisitExchange:316, PlanFragmenter$Fragmenter \ngenerateFragment:365, PlanFragmenter$Fragmenter \ngenerateSubPlan:381, PlanFragmenter$Fragmenter ",
			"lineHeight": 1.2
		},
		{
			"id": "kJIpGdKn",
			"type": "text",
			"x": 1115.563179975937,
			"y": 446.21779737891006,
			"width": 679.6875,
			"height": 168,
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
			"seed": 1676089816,
			"version": 2,
			"versionNonce": 85069736,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688969367190,
			"link": null,
			"locked": false,
			"text": "getSplits:163, SplitManager \ntableFileScanSplit:296, SplitManager \nbuild:47, SplitInfoBuilder \nbuildSplits:114, SplitInfoBuilder \napply:-1, SplitInfoBuilder$$Lambda$965/0x000000080164ca80 \nlambda$build$1:50, SplitInfoBuilder \ngetSplits:112, ORCSplit ",
			"rawText": "getSplits:163, SplitManager \ntableFileScanSplit:296, SplitManager \nbuild:47, SplitInfoBuilder \nbuildSplits:114, SplitInfoBuilder \napply:-1, SplitInfoBuilder$$Lambda$965/0x000000080164ca80 \nlambda$build$1:50, SplitInfoBuilder \ngetSplits:112, ORCSplit ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 164,
			"containerId": null,
			"originalText": "getSplits:163, SplitManager \ntableFileScanSplit:296, SplitManager \nbuild:47, SplitInfoBuilder \nbuildSplits:114, SplitInfoBuilder \napply:-1, SplitInfoBuilder$$Lambda$965/0x000000080164ca80 \nlambda$build$1:50, SplitInfoBuilder \ngetSplits:112, ORCSplit ",
			"lineHeight": 1.2
		},
		{
			"id": "3P3DOMk2",
			"type": "text",
			"x": -382.0820447696749,
			"y": 1010.0863066083782,
			"width": 644.53125,
			"height": 240,
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
			"seed": 1917698520,
			"version": 3,
			"versionNonce": 1242681304,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "FaqknlqotV_0cvwBq2Qvj",
					"type": "arrow"
				}
			],
			"updated": 1688969553529,
			"link": null,
			"locked": false,
			"text": "updateTask:285, SqlTaskManager \nupdateTask:547, SqlTask \nbootstrapTask:575, SqlTask \ncreate:77, SqlTaskExecutionFactory \ncreateSqlTaskExecution:109, SqlTaskExecution \n<init>:184, SqlTaskExecution \nstart:219, SqlTaskExecution \ncreateDriverExec:46, PipelineFactory \ncreateExecutor:126, LogicalViewExecutorFactory \nbuildTableFileScanExec:179, LogicalViewExecutorFactory ",
			"rawText": "updateTask:285, SqlTaskManager \nupdateTask:547, SqlTask \nbootstrapTask:575, SqlTask \ncreate:77, SqlTaskExecutionFactory \ncreateSqlTaskExecution:109, SqlTaskExecution \n<init>:184, SqlTaskExecution \nstart:219, SqlTaskExecution \ncreateDriverExec:46, PipelineFactory \ncreateExecutor:126, LogicalViewExecutorFactory \nbuildTableFileScanExec:179, LogicalViewExecutorFactory ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 236,
			"containerId": null,
			"originalText": "updateTask:285, SqlTaskManager \nupdateTask:547, SqlTask \nbootstrapTask:575, SqlTask \ncreate:77, SqlTaskExecutionFactory \ncreateSqlTaskExecution:109, SqlTaskExecution \n<init>:184, SqlTaskExecution \nstart:219, SqlTaskExecution \ncreateDriverExec:46, PipelineFactory \ncreateExecutor:126, LogicalViewExecutorFactory \nbuildTableFileScanExec:179, LogicalViewExecutorFactory ",
			"lineHeight": 1.2
		},
		{
			"id": "FaqknlqotV_0cvwBq2Qvj",
			"type": "arrow",
			"x": -172.5213957385564,
			"y": 687.9631604168694,
			"width": 2.1960487185874626,
			"height": 306.1447917171954,
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
			"seed": 1954460328,
			"version": 40,
			"versionNonce": 1945489064,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688969553529,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.1960487185874626,
					306.1447917171954
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "DVu0JGRf",
				"focus": 0.1323059446990432,
				"gap": 23.03436775899479
			},
			"endBinding": {
				"elementId": "3P3DOMk2",
				"focus": -0.35861020548337924,
				"gap": 15.978354474313392
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "BjZxwAHZ",
			"type": "text",
			"x": -130.20845704052488,
			"y": 852.4088085871686,
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
			"seed": 335156440,
			"version": 13,
			"versionNonce": 638227160,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688969559145,
			"link": null,
			"locked": false,
			"text": "async call",
			"rawText": "async call",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "async call",
			"lineHeight": 1.2
		},
		{
			"id": "3ImJ0DlN",
			"type": "text",
			"x": 443.7222754159136,
			"y": 1219.280947519732,
			"width": 257.8125,
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
			"seed": 1166250408,
			"version": 99,
			"versionNonce": 2064668584,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688969602007,
			"link": null,
			"locked": false,
			"text": "AsyncTableFileScanExec",
			"rawText": "AsyncTableFileScanExec",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "AsyncTableFileScanExec",
			"lineHeight": 1.2
		},
		{
			"id": "qSjqwGoA",
			"type": "text",
			"x": -372.8958409768949,
			"y": 1444.2979394445163,
			"width": 621.09375,
			"height": 336,
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
			"seed": 695673512,
			"version": 2,
			"versionNonce": 654293976,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688969756039,
			"link": null,
			"locked": false,
			"text": "\n\n<init>:186, SqlTaskExecution \naddSources:243, SqlTaskExecution \nupdateSources:295, SqlTaskExecution \nschedulePartitionedSource:379, SqlTaskExecution \nupdateSource:227, Driver \nclose:604, Driver$DriverLockResult \nprocessNewSources:247, Driver \nprocessNewSource:318, Driver \naddSplit:82, AsyncTableFileScanExec \naddSplit:164, TableFileScanClient \ninitSplit:356, TableFileScanClient$ClientInitializer \ninit:194, ORCSplit ",
			"rawText": "\n\n<init>:186, SqlTaskExecution \naddSources:243, SqlTaskExecution \nupdateSources:295, SqlTaskExecution \nschedulePartitionedSource:379, SqlTaskExecution \nupdateSource:227, Driver \nclose:604, Driver$DriverLockResult \nprocessNewSources:247, Driver \nprocessNewSource:318, Driver \naddSplit:82, AsyncTableFileScanExec \naddSplit:164, TableFileScanClient \ninitSplit:356, TableFileScanClient$ClientInitializer \ninit:194, ORCSplit ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 332,
			"containerId": null,
			"originalText": "\n\n<init>:186, SqlTaskExecution \naddSources:243, SqlTaskExecution \nupdateSources:295, SqlTaskExecution \nschedulePartitionedSource:379, SqlTaskExecution \nupdateSource:227, Driver \nclose:604, Driver$DriverLockResult \nprocessNewSources:247, Driver \nprocessNewSource:318, Driver \naddSplit:82, AsyncTableFileScanExec \naddSplit:164, TableFileScanClient \ninitSplit:356, TableFileScanClient$ClientInitializer \ninit:194, ORCSplit ",
			"lineHeight": 1.2
		},
		{
			"id": "gmHlidb0",
			"type": "text",
			"x": 438.5868355236872,
			"y": 1592.4846282043995,
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
			"seed": 1645870808,
			"version": 11,
			"versionNonce": 784840664,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688986350993,
			"link": null,
			"locked": false,
			"text": "Split.Init",
			"rawText": "Split.Init",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "Split.Init",
			"lineHeight": 1.2
		},
		{
			"id": "qbMOZCuQ",
			"type": "text",
			"x": -360.0292359048859,
			"y": 2106.569449632971,
			"width": 574.21875,
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
			"seed": 749329576,
			"version": 44,
			"versionNonce": 49051096,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Qqrd2oCLGXxDkGmwe6TxE",
					"type": "arrow"
				}
			],
			"updated": 1688987015487,
			"link": null,
			"locked": false,
			"text": "run:833, Thread \nrun:635, ThreadPoolExecutor$Worker \nrunWorker:1136, ThreadPoolExecutor \nrun:540, TaskExecutor$ApRunner \nprocess:408, TaskExecutor$PrioritizedSplitRunner \nprocessFor:57, DriverSplitRunner \nprocessFor:337, Driver \nprocessInternal:469, Driver \nopen:133, DriverExec \nopen:99, AbstractExecutor \ndoOpen:102, AsyncTableFileScanExec \nstartPrefetchThread:155, TableFileScanClient \nsubmit:195, ServerThreadPool \nnewTaskForCallable:296, ServerThreadPool \n<init>:621, ServerThreadPool$NamedFutureTask \n<init>:132, FutureTask ",
			"rawText": "run:833, Thread \nrun:635, ThreadPoolExecutor$Worker \nrunWorker:1136, ThreadPoolExecutor \nrun:540, TaskExecutor$ApRunner \nprocess:408, TaskExecutor$PrioritizedSplitRunner \nprocessFor:57, DriverSplitRunner \nprocessFor:337, Driver \nprocessInternal:469, Driver \nopen:133, DriverExec \nopen:99, AbstractExecutor \ndoOpen:102, AsyncTableFileScanExec \nstartPrefetchThread:155, TableFileScanClient \nsubmit:195, ServerThreadPool \nnewTaskForCallable:296, ServerThreadPool \n<init>:621, ServerThreadPool$NamedFutureTask \n<init>:132, FutureTask ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 380,
			"containerId": null,
			"originalText": "run:833, Thread \nrun:635, ThreadPoolExecutor$Worker \nrunWorker:1136, ThreadPoolExecutor \nrun:540, TaskExecutor$ApRunner \nprocess:408, TaskExecutor$PrioritizedSplitRunner \nprocessFor:57, DriverSplitRunner \nprocessFor:337, Driver \nprocessInternal:469, Driver \nopen:133, DriverExec \nopen:99, AbstractExecutor \ndoOpen:102, AsyncTableFileScanExec \nstartPrefetchThread:155, TableFileScanClient \nsubmit:195, ServerThreadPool \nnewTaskForCallable:296, ServerThreadPool \n<init>:621, ServerThreadPool$NamedFutureTask \n<init>:132, FutureTask ",
			"lineHeight": 1.2
		},
		{
			"id": "5yXytsjZ",
			"type": "text",
			"x": 681.7229962379704,
			"y": 2227.3841817758284,
			"width": 609.375,
			"height": 168,
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
			"seed": 380789928,
			"version": 131,
			"versionNonce": 2039628200,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Qqrd2oCLGXxDkGmwe6TxE",
					"type": "arrow"
				},
				{
					"id": "3QpOCYZEVXsTHrFHP6Uer",
					"type": "arrow"
				}
			],
			"updated": 1688988068091,
			"link": null,
			"locked": false,
			"text": "run:-1, FutureTask \nrun$$$capture:264, FutureTask \ncall:693, ServerThreadPool$CallableAdapter \ncall:50, CallableWithCpuCollector \ncall:38, CallableWithStatHandler \ncall:305, TableFileScanClient$PrefetchThread \nprocessFile:325, TableFileScanClient$PrefetchThread ",
			"rawText": "run:-1, FutureTask \nrun$$$capture:264, FutureTask \ncall:693, ServerThreadPool$CallableAdapter \ncall:50, CallableWithCpuCollector \ncall:38, CallableWithStatHandler \ncall:305, TableFileScanClient$PrefetchThread \nprocessFile:325, TableFileScanClient$PrefetchThread ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 164,
			"containerId": null,
			"originalText": "run:-1, FutureTask \nrun$$$capture:264, FutureTask \ncall:693, ServerThreadPool$CallableAdapter \ncall:50, CallableWithCpuCollector \ncall:38, CallableWithStatHandler \ncall:305, TableFileScanClient$PrefetchThread \nprocessFile:325, TableFileScanClient$PrefetchThread ",
			"lineHeight": 1.2
		},
		{
			"id": "Qqrd2oCLGXxDkGmwe6TxE",
			"type": "arrow",
			"x": 227.37031766654195,
			"y": 2295.152038918686,
			"width": 440.7031249999998,
			"height": 0.9375,
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
			"seed": 1532369576,
			"version": 86,
			"versionNonce": 1218474920,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688987015487,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					440.7031249999998,
					0.9375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "qbMOZCuQ",
				"focus": -0.021059117713911852,
				"gap": 13.180803571427873
			},
			"endBinding": {
				"elementId": "5yXytsjZ",
				"focus": 0.17268480113734935,
				"gap": 13.649553571428669
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "A7JxdwQm",
			"type": "text",
			"x": 370.45067480939906,
			"y": 2182.4065032044,
			"width": 93.75,
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
			"seed": 264316120,
			"version": 11,
			"versionNonce": 1899437528,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688987068627,
			"link": null,
			"locked": false,
			"text": "prefetch",
			"rawText": "prefetch",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "prefetch",
			"lineHeight": 1.2
		},
		{
			"id": "zNrtc290",
			"type": "text",
			"x": 680.7185319522562,
			"y": 2747.0158782044,
			"width": 714.84375,
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
			"seed": 934562728,
			"version": 32,
			"versionNonce": 1719469272,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "3QpOCYZEVXsTHrFHP6Uer",
					"type": "arrow"
				},
				{
					"id": "e161ezplPNFA9KS6VsGkv",
					"type": "arrow"
				}
			],
			"updated": 1688988232351,
			"link": null,
			"locked": false,
			"text": "processFile:333, TableFileScanClient$PrefetchThread \nfetchToBuffer:334, ORCReaderTask \nfetchPushDownResults:332, FileReaderTask \napply:-1, FileReaderTask$$Lambda$1494/0x00000008018a9cf0 \nlambda$initializeSinkDeltaDataHandlers$7:370, FileReaderTask ",
			"rawText": "processFile:333, TableFileScanClient$PrefetchThread \nfetchToBuffer:334, ORCReaderTask \nfetchPushDownResults:332, FileReaderTask \napply:-1, FileReaderTask$$Lambda$1494/0x00000008018a9cf0 \nlambda$initializeSinkDeltaDataHandlers$7:370, FileReaderTask ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 116,
			"containerId": null,
			"originalText": "processFile:333, TableFileScanClient$PrefetchThread \nfetchToBuffer:334, ORCReaderTask \nfetchPushDownResults:332, FileReaderTask \napply:-1, FileReaderTask$$Lambda$1494/0x00000008018a9cf0 \nlambda$initializeSinkDeltaDataHandlers$7:370, FileReaderTask ",
			"lineHeight": 1.2
		},
		{
			"id": "3QpOCYZEVXsTHrFHP6Uer",
			"type": "arrow",
			"x": 1005.026567666542,
			"y": 2414.761413918686,
			"width": 2.8236607142857792,
			"height": 309.34151785714266,
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
			"seed": 1173828008,
			"version": 97,
			"versionNonce": 1357515992,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688988068091,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.8236607142857792,
					309.34151785714266
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "5yXytsjZ",
				"focus": -0.06403478076280829,
				"gap": 19.377232142857338
			},
			"endBinding": {
				"elementId": "zNrtc290",
				"focus": -0.10250683811884363,
				"gap": 22.91294642857156
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "AoaimP8N",
			"type": "text",
			"x": 695.6627283808284,
			"y": 3206.3797174901165,
			"width": 714.84375,
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
			"seed": 1499199400,
			"version": 4,
			"versionNonce": 2114324440,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "e161ezplPNFA9KS6VsGkv",
					"type": "arrow"
				},
				{
					"id": "ET3OO_hCjzgOVk88QM-TI",
					"type": "arrow"
				}
			],
			"updated": 1688988635426,
			"link": null,
			"locked": false,
			"text": "fetchPushDownResults:346, FileReaderTask \nlambda$initializeSinkDeltaDataHandlers$8:375, FileReaderTask \nrunSinkDeltaDataTasks:268, FileReaderTask \n<init>:151, FutureTask \n - Async stack trace\nrun:-1, FutureTask \nrun$$$capture:264, FutureTask \ncall:539, Executors$RunnableAdapter \nrun:-1, FileReaderTask$$Lambda$2541/0x0000000801a662b8 \nlambda$runSinkDeltaDataTasks$2:272, FileReaderTask \nfetchChunk:379, ORCReaderTask \nfetchChunkInternal:388, ORCReaderTask ",
			"rawText": "fetchPushDownResults:346, FileReaderTask \nlambda$initializeSinkDeltaDataHandlers$8:375, FileReaderTask \nrunSinkDeltaDataTasks:268, FileReaderTask \n<init>:151, FutureTask \n - Async stack trace\nrun:-1, FutureTask \nrun$$$capture:264, FutureTask \ncall:539, Executors$RunnableAdapter \nrun:-1, FileReaderTask$$Lambda$2541/0x0000000801a662b8 \nlambda$runSinkDeltaDataTasks$2:272, FileReaderTask \nfetchChunk:379, ORCReaderTask \nfetchChunkInternal:388, ORCReaderTask ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 284,
			"containerId": null,
			"originalText": "fetchPushDownResults:346, FileReaderTask \nlambda$initializeSinkDeltaDataHandlers$8:375, FileReaderTask \nrunSinkDeltaDataTasks:268, FileReaderTask \n<init>:151, FutureTask \n - Async stack trace\nrun:-1, FutureTask \nrun$$$capture:264, FutureTask \ncall:539, Executors$RunnableAdapter \nrun:-1, FileReaderTask$$Lambda$2541/0x0000000801a662b8 \nlambda$runSinkDeltaDataTasks$2:272, FileReaderTask \nfetchChunk:379, ORCReaderTask \nfetchChunkInternal:388, ORCReaderTask ",
			"lineHeight": 1.2
		},
		{
			"id": "e161ezplPNFA9KS6VsGkv",
			"type": "arrow",
			"x": 1008.1627283808286,
			"y": 2881.937753204402,
			"width": 0.46875,
			"height": 300.9040178571431,
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
			"seed": 1320168872,
			"version": 42,
			"versionNonce": 258233512,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688988232351,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.46875,
					300.9040178571431
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "zNrtc290",
				"focus": 0.08352358969216118,
				"gap": 14.921875000001819
			},
			"endBinding": {
				"elementId": "AoaimP8N",
				"focus": -0.12764462951316596,
				"gap": 23.53794642857156
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Iy9J0coC",
			"type": "text",
			"x": 708.6090480648858,
			"y": 3721.4344336698887,
			"width": 457.03125,
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
			"seed": 1510296232,
			"version": 4,
			"versionNonce": 1769569240,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ET3OO_hCjzgOVk88QM-TI",
					"type": "arrow"
				},
				{
					"id": "7YnrRtW0KU0apMboTTFJi",
					"type": "arrow"
				}
			],
			"updated": 1688989990320,
			"link": null,
			"locked": false,
			"text": "fetchChunkInternal:399, ORCReaderTask \nreadBlock:121, OrcRecordReader \nreadBlock:133, AbstractColumnReader \nopenRowGroup:106, AbstractColumnReader ",
			"rawText": "fetchChunkInternal:399, ORCReaderTask \nreadBlock:121, OrcRecordReader \nreadBlock:133, AbstractColumnReader \nopenRowGroup:106, AbstractColumnReader ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 92,
			"containerId": null,
			"originalText": "fetchChunkInternal:399, ORCReaderTask \nreadBlock:121, OrcRecordReader \nreadBlock:133, AbstractColumnReader \nopenRowGroup:106, AbstractColumnReader ",
			"lineHeight": 1.2
		},
		{
			"id": "ET3OO_hCjzgOVk88QM-TI",
			"type": "arrow",
			"x": 1023.3245182449367,
			"y": 3505.0016486338563,
			"width": 0.39051429480082334,
			"height": 202.70620757378083,
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
			"seed": 1850202328,
			"version": 71,
			"versionNonce": 1394672040,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688988635426,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.39051429480082334,
					202.70620757378083
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "AoaimP8N",
				"focus": 0.08236584774241397,
				"gap": 10.621931143739857
			},
			"endBinding": {
				"elementId": "Iy9J0coC",
				"focus": 0.3748354299309556,
				"gap": 13.726577462251498
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "H7Phukmg",
			"type": "text",
			"x": 1317.3036793710598,
			"y": 3735.1902997042507,
			"width": 257.8125,
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
			"seed": 1624764888,
			"version": 29,
			"versionNonce": 1604793000,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688988678940,
			"link": null,
			"locked": false,
			"text": "Open Row Group, Stream",
			"rawText": "Open Row Group, Stream",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "Open Row Group, Stream",
			"lineHeight": 1.2
		},
		{
			"id": "oFNe6Hrh",
			"type": "text",
			"x": 736.1403058483494,
			"y": 4039.225203921497,
			"width": 421.875,
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
			"seed": 1682272472,
			"version": 150,
			"versionNonce": 314655448,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "alZOEgqOR3coNWubeuw_D",
					"type": "arrow"
				},
				{
					"id": "0tllFZpIb8a_DENOqYhp8",
					"type": "arrow"
				}
			],
			"updated": 1688989054522,
			"link": null,
			"locked": false,
			"text": "readBlock:161, AbstractColumnReader ",
			"rawText": "readBlock:161, AbstractColumnReader ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "readBlock:161, AbstractColumnReader ",
			"lineHeight": 1.2
		},
		{
			"id": "DNHbqfVI",
			"type": "text",
			"x": 1304.006667633089,
			"y": 3995.3899743300954,
			"width": 445.3125,
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
			"seed": 825741784,
			"version": 3,
			"versionNonce": 889735896,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "alZOEgqOR3coNWubeuw_D",
					"type": "arrow"
				}
			],
			"updated": 1688989045285,
			"link": null,
			"locked": false,
			"text": "readNonNullBlock:81, LongColumnReader ",
			"rawText": "readNonNullBlock:81, LongColumnReader ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "readNonNullBlock:81, LongColumnReader ",
			"lineHeight": 1.2
		},
		{
			"id": "OxP8Syzz",
			"type": "text",
			"x": 1307.2576991373062,
			"y": 4083.37284494874,
			"width": 527.34375,
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
			"seed": 1872732840,
			"version": 26,
			"versionNonce": 2120194264,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "0tllFZpIb8a_DENOqYhp8",
					"type": "arrow"
				}
			],
			"updated": 1688989051277,
			"link": null,
			"locked": false,
			"text": "readNonNullBlock:81, SliceDirectColumnReader ",
			"rawText": "readNonNullBlock:81, SliceDirectColumnReader ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "readNonNullBlock:81, SliceDirectColumnReader ",
			"lineHeight": 1.2
		},
		{
			"id": "alZOEgqOR3coNWubeuw_D",
			"type": "arrow",
			"x": 1157.4853344868602,
			"y": 4034.8440882889363,
			"width": 143.49484736152135,
			"height": 36.35345615871438,
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
			"seed": 1161870760,
			"version": 57,
			"versionNonce": 627688104,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688989063560,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					143.49484736152135,
					-36.35345615871438
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "oFNe6Hrh",
				"focus": 0.5642488557126769,
				"gap": 4.3811156325605225
			},
			"endBinding": {
				"elementId": "DNHbqfVI",
				"focus": 0.9658826153871807,
				"gap": 3.026485784707347
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "0tllFZpIb8a_DENOqYhp8",
			"type": "arrow",
			"x": 1160.467176641678,
			"y": 4075.758305458027,
			"width": 145.79052249562824,
			"height": 28.104523025340768,
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
			"seed": 915959464,
			"version": 89,
			"versionNonce": 1857250520,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688989060772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					145.79052249562824,
					28.104523025340768
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "oFNe6Hrh",
				"focus": -0.31526189890656575,
				"gap": 12.533101536530012
			},
			"endBinding": {
				"elementId": "OxP8Syzz",
				"focus": -0.9472019563748726,
				"gap": 1
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "OCZ4Y3ZW",
			"type": "text",
			"x": 1952.5142312942153,
			"y": 4076.4216905012836,
			"width": 527.34375,
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
			"seed": 1717952728,
			"version": 15,
			"versionNonce": 1011224744,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688989717378,
			"link": null,
			"locked": false,
			"text": "readNonNullBlock:86, SliceDirectColumnReader \nreadDataStream:124, SliceDirectColumnReader ",
			"rawText": "readNonNullBlock:86, SliceDirectColumnReader \nreadDataStream:124, SliceDirectColumnReader ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "readNonNullBlock:86, SliceDirectColumnReader \nreadDataStream:124, SliceDirectColumnReader ",
			"lineHeight": 1.2
		},
		{
			"id": "s8bTQ6oV",
			"type": "text",
			"x": -148.90176617368638,
			"y": 2762.204408493051,
			"width": 609.375,
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
			"seed": 670773976,
			"version": 207,
			"versionNonce": 1026692824,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "7YnrRtW0KU0apMboTTFJi",
					"type": "arrow"
				}
			],
			"updated": 1688989990320,
			"link": null,
			"locked": false,
			"text": "processFile:333, TableFileScanClient$PrefetchThread \nfetchToBuffer:337, ORCReaderTask \nfetchRows:257, ORCReaderTask \nfetchChunkInternal:388, ORCReaderTask ",
			"rawText": "processFile:333, TableFileScanClient$PrefetchThread \nfetchToBuffer:337, ORCReaderTask \nfetchRows:257, ORCReaderTask \nfetchChunkInternal:388, ORCReaderTask ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 92,
			"containerId": null,
			"originalText": "processFile:333, TableFileScanClient$PrefetchThread \nfetchToBuffer:337, ORCReaderTask \nfetchRows:257, ORCReaderTask \nfetchChunkInternal:388, ORCReaderTask ",
			"lineHeight": 1.2
		},
		{
			"id": "7YnrRtW0KU0apMboTTFJi",
			"type": "arrow",
			"x": 141.6213434434486,
			"y": 2866.803662355474,
			"width": 551.1328242525201,
			"height": 898.5831551942574,
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
			"seed": 640477608,
			"version": 214,
			"versionNonce": 2009162408,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688989990320,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					551.1328242525201,
					898.5831551942574
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "s8bTQ6oV",
				"focus": 0.14628756976185467,
				"gap": 8.599253862423211
			},
			"endBinding": {
				"elementId": "Iy9J0coC",
				"focus": -0.9377111586101656,
				"gap": 15.854880368917122
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "l9I8JUZe",
			"type": "text",
			"x": -72.28286153374813,
			"y": 2693.1029040280305,
			"width": 128.90625,
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
			"seed": 1099710680,
			"version": 29,
			"versionNonce": 2007661992,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688990013660,
			"link": null,
			"locked": false,
			"text": "Without Agg",
			"rawText": "Without Agg",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "Without Agg",
			"lineHeight": 1.2
		},
		{
			"id": "4paNOMOG",
			"type": "text",
			"x": 19.361080598653416,
			"y": 3161.866500649667,
			"width": 164.0625,
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
			"seed": 76264920,
			"version": 15,
			"versionNonce": 1841510616,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1688990022834,
			"link": null,
			"locked": false,
			"text": "fetch internal",
			"rawText": "fetch internal",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "fetch internal",
			"lineHeight": 1.2
		},
		{
			"id": "youUHk2U",
			"type": "text",
			"x": 1121.9113208072636,
			"y": 790.0194245000822,
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
			"seed": 2055330472,
			"version": 2,
			"versionNonce": 1260159960,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1688969541490,
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
			"id": "Nr5EoC7m",
			"type": "text",
			"x": 1403.3046899435894,
			"y": 3723.5236851470736,
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
			"seed": 784264664,
			"version": 2,
			"versionNonce": 1397849000,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1688988675035,
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
		"scrollX": 828.5626077025563,
		"scrollY": -2378.865813859108,
		"zoom": {
			"value": 0.40011339426040654
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
---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
extract:126, LoadDataExtractor 
doConsume:151, LoadDataExtractor 
consume:45, OrcConsumer 
consume:267, OrcWriterTask 
initNextFile:896, OrcWriterTask 
putFileMeta:645, OrcWriterTask 
addOssFileAndReturnLastInsertId:656, TableMetaChanger 
addOssFileAndReturnLastInsertId:352, TableInfoManager 
insertAndReturnLastInsertId:192, FilesAccessor 
insertAndReturnLastInsertId:97, MetaDbUtil  ^JAhu5mfG

INSERT_FILE_RECORD ^uhzfKzE4

executeInsertAndReturnLastInsertId:158, MetaDbUtil ^SRHsHkWG

input sql template ^xwCFlXrh

FilesAccessor ^FcEW3TFF

executeSQL:81, TPreparedStatement 
executeSQL:311, TConnection 
executeQuery:487, TConnection 
execute:59, PlanExecutor 
execByExecPlanNodeByOne:109, PlanExecutor 
execute:77, ExecutorHelper 
executeByCursor:142, ExecutorHelper 
execByExecPlanNode:105, TransactionExecutor 
execByExecPlanNode:53, TopologyExecutor 
execByExecPlanNode:52, AbstractGroupExecutor 
executeInner:74, AbstractGroupExecutor 
handlePlan:97, HandlerCommon  ^CVlSyek4

handle:77, LogicalCommonDdlHandler 
handleDdlRequest:153, LogicalCommonDdlHandler 
execute:99, DdlEngineRequester 
storeJob:122, DdlJobManager 
storeJobImpl:165, DdlJobManager 
acquireResource:100, DdlEngineResourceManager 
tryReadWriteLockBatch:549, PersistentReadWriteLock  ^1zZo4yJH

execute:47, MetaDbAccessorWrapper 
invoke:465, PersistentReadWriteLock$9 
invoke:525, PersistentReadWriteLock$9 
insert:102, ReadWriteLockAccessor 
 ^ZZot9Nri

insert:92, MetaDbUtil 
executeBatch:144, MetaDbUtil ^KqlYPcwD

INSERT_DATA ^u6p4rkYw

ReadWriteLockAccessor ^bx6FgVqY

input sql template ^GA4XKqgb

executeTask:562, DdlEngineDagExecutor 
execute:93, AbstractDdlTask 
execute:58, DdlEngineAccessorDelegate 
invoke:69, AbstractDdlTask$1 
invoke:74, AbstractDdlTask$1 
duringTransaction:85, LoadDataFromFileToObjectStorageTask 
executeImpl:95, LoadDataFromFileToObjectStorageTask 
lockOssFileMeta:667, TableMetaChanger 
lockOssFile:381, TableInfoManager 
lock:297, FilesAccessor  ^l1GR7N4F

query:67, MetaDbUtil  ^X830sl7S

FileAccessor ^QZGtQg6t

SELECT_FOR_ROLLBACK ^MdUXpmmt

.orc
.stat
sketch ^xORIYtKu

run:-1, FutureTask 
run$$$capture:264, FutureTask 
call:54, AsyncCallableTask 
call:459, DdlEngineScheduler$DdlJobExecutor 
call:482, DdlEngineScheduler$DdlJobExecutor 
restoreDDL:99, ServerConfigManager 
restoreDDL:466, MatrixConfigHolder 
restoreAndRun:173, DdlEngineDagExecutor 
run:258, DdlEngineDagExecutor 
onFinished:441, DdlEngineDagExecutor 
removeJob:399, DdlJobManager 
execute:58, DdlEngineAccessorDelegate 
invoke:372, DdlJobManager$1 
invoke:394, DdlJobManager$1 
releaseResource:189, DdlEngineResourceManager  ^cedfsmz5

unlockReadWriteByOwner:331, PersistentReadWriteLock 
deleteByOwnerAndResourceAndType:220, ReadWriteLockAccessor  ^f2vEHzBG

delete:123, MetaDbUtil  ^1VLoVOyk

DELETE_BY_OWNER_RESOURCE_TYPE ^6ZYdP46p

ReadWriteLockAccessor ^3hDqzm9Y

input sql template ^GPJQKL0L

SQL ^YQGW5OR5

Database ^whOgMqPI

MetaDB(mysql) ^12su5HuU

My ^tFUj1EqN

insert ^If8qppLA

delete ^bCJGWCxf

query ^UTz6eu9v

MetaDbUtil ^vs1NxaRN

FilesAccessor ^sa4Yh1HV

SketchTreeRootsAccessor ^B6QnXLRy

ReadWriteLockAccessor ^uwj22qPw

AbstractAccessor ^cjM9nzvR

FileRecord ^4UYAcb04

ReadWriteLockRecord ^gh5yxShB

SketchRootRecord ^6HeNmDy6

DataModel ^XOBAUZaq

Connection ^Uw4oxKrd

Write ^Py9lkDew

Read ^tmpgauCe

handle:65, FrontendCommandHandler 
query:462, FrontendConnection 
queryRaw:115, ServerQueryHandler 
executeStatement:144, ServerQueryHandler 
handle:80, SelectHandler 
execute:685, ServerConnection 
execute:702, ServerConnection 
innerExecute:881, ServerConnection 
execute:66, TPreparedStatement 
executeInternal:149, TStatement 
executeSQL:81, TPreparedStatement 
executeSQL:311, TConnection 
executeQuery:487, TConnection  ^3KoUDuhZ

execute:59, PlanExecutor 
execByExecPlanNodeByOne:109, PlanExecutor 
execute:79, ExecutorHelper 
executeCluster:116, ExecutorHelper 
execute:56, MppRunner 
createQuery:54, LocalStatementClient 
createQuery:144, StatementResource 
init:274, StatementResource$Query 
createClusterQuery:413, SqlQueryManager 
start:129, SqlQueryExecution 
buildRootFragment:82, PlanFragmenter 
buildRootFragment:141, PlanFragmenter$Fragmenter 
generateSubPlan:381, PlanFragmenter$Fragmenter ^p6r9fDJ6

getSplits:163, SplitManager 
tableFileScanSplit:310, SplitManager 
build:38, SplitInfoBuilder 
buildORCSplits:68, SplitInfoBuilder 
getSplits:112, ORCSplit ^sVcDTIaa

queryByLogicalTableAndFileType:252, FilesAccessor 
query:103, AbstractAccessor
query:144, AbstractAccessor
query:67, MetaDbUtil ^kFLRQOH3

getOrLoadFileMetaMap:92, TableMetaUtil 
initFileMeta:84, TableMetaUtil 
getTableFiles:70, TableMetaUtil  ^k3DUHPHQ

    public static Map<String, FileMeta> getTableFiles(TableMeta tableMeta) {
        try (Connection connection = MetaDbUtil.getConnection()) {
            FilesAccessor filesAccessor = new FilesAccessor();
            filesAccessor.setConnection(connection);
            return filesAccessor.queryByLogicalTableAndFileType(
                    tableMeta.getSchemaName(),
                    tableMeta.getTableName(),
                    ObjectFileType.TABLE_FILE.name()
            ).stream().collect(Collectors.toUnmodifiableMap(
                    FileRecord::getFileName,
                    FileMeta::parseFrom
            ));
        } catch (SQLException e) {
            throw GeneralUtil.nestedException(e);
        }
    } ^kb3i8jCu

executeTask:562, DdlEngineDagExecutor 
execute:67, AbstractDdlTask 
beforeTransaction:32, BaseSyncTask 
executeImpl:56, TableSyncTask 
forEach:1511, ArrayList 
accept:-1, TableSyncTask$$Lambda$1939/0x00000008018e55f0 
lambda$executeImpl$0:61, TableSyncTask 
sync:31, ClusterSyncManagerHelper 
sync:59, ClusterSyncManager 
doSync:74, ClusterSyncManager 
sync:28, TableMetaChangeSyncAction 
sync:44, TableMetaChangeSyncAction  ^dbTNkdNV

toNewVersion:221, GmsTableMetaManager
toNewVersionImpl:690, GmsTableMetaManager 
<init>:80, GmsTableMetaManager 
GmsTableMetaManager:94, GmsTableMetaManager ^AqerqXBa

fetchTableMeta:153, GmsTableMetaManager 
buildTableMeta:380, GmsTableMetaManager 
<init>:115-116, TableMeta 
<init>:121, TableMeta  ^wW4Mv6D1

private Map<String, FileMeta> fileMetaMap = null;
private boolean fileMetaMapInitialized = false; ^rHOKmAiF

table meta ^pQ7bK0as


executeStatement:144, ServerQueryHandler 
handle:80, SelectHandler 
execute:685, ServerConnection 
execute:702, ServerConnection 
innerExecute:850, ServerConnection 
getConnection:1699, ServerConnection  ^zyepUzN1

init:43, AbstractLifecycle 
doInit:142, TDataSource 
init:43, AbstractLifecycle 
doInit:142, MatrixConfigHolder 
initSchema:541, MatrixConfigHolder 
init:43, AbstractLifecycle 
doInit:178, GmsTableMetaManager 
fetchTableMetas:542, GmsTableMetaManager 
fetchSpecificSchemaTableMetas:577, GmsTableMetaManager 
buildTableMeta:380, GmsTableMetaManager 
<init>:120, TableMeta  ^QW7mXle1

OptimizerContext ^3291yKHU

handle:65, FrontendCommandHandler 
query:462, FrontendConnection 
queryRaw:115, ServerQueryHandler 
executeStatement:144, ServerQueryHandler 
handle:80, SelectHandler  ^xUBcxmqp

execute:685, ServerConnection 
execute:702, ServerConnection 
innerExecute:850, ServerConnection 
getConnection:1699, ServerConnection  ^vmsjCWfY

init:43, AbstractLifecycle 
doInit:142, TDataSource 
init:43, AbstractLifecycle  ^dLPDkFab

doInit:142, MatrixConfigHolder 
initSchema:526, MatrixConfigHolder  ^oE3uIJqE

doInit:154, MatrixConfigHolder 
loadContext:224, MatrixConfigHolder 
loadContext:94, OptimizerContext  ^sGRBvFXT

init schema manager ^X4Lyc5yV

init optimizerContext for fresh schema,
update optimizerContextMap ^EJbWrgXE

    // Major call path:
    //   ServerConnection.(getSchemaConfig|getConnection)
    //   -> TDataSource.init
    //   -> MatrixConfigHolder.init
    public static void loadContext(OptimizerContext context) {
        optimizerContextMap.put(context.getSchemaName().toLowerCase(), context);
        DefaultSchema.setSchemaName(context.getSchemaName());
    } ^fPqwxsNP

information_schema -> RoutedSchemaManager
other table.       -> GmsTableMetaManager ^trD1RrYa

init:43, AbstractLifecycle 
doInit:178, GmsTableMetaManager 
fetchTableMetas:542, GmsTableMetaManager 
fetchSpecificSchemaTableMetas:557, GmsTableMetaManager  ^eYOveits

fetchSpecificSchemaTableMetas:559, GmsTableMetaManager 
fetchTablesRecords:14, DefaultMetaFetcher 
queryTables:184, TableInfoManager  ^FEONFoQN

query:182, TablesAccessor 
query:103, AbstractAccessor 
query:144, AbstractAccessor 
query:67, MetaDbUtil  ^epMDvryn

TableAccessor.SELECT_TABLES_ALL ^Ky3lLZgq

input sql template ^VS2G0KzD

fetchSpecificSchemaTableMetas:561, GmsTableMetaManager 
fetchColumnsRecords:20, DefaultMetaFetcher 
queryVisibleColumns:204, TableInfoManager 
queryColumns:214, TableInfoManager ^FN2tslaP

query:308, ColumnsAccessor 
query:103, AbstractAccessor 
query:144, AbstractAccessor 
query:67, MetaDbUtil  ^IcANi8yD

ColumnsAccessor.SELECT_ALL_TABLE_COLUMNS ^DyVQhekv

input sql template ^D8kMerky

fetchSpecificSchemaTableMetas:563, GmsTableMetaManager 
fetchIndexesRecords:26, DefaultMetaFetcher 
queryVisibleIndexes:238, TableInfoManager 
queryIndexes:248, TableInfoManager  ^7DW1OUZ3

query:249, IndexesAccessor 
query:103, AbstractAccessor 
query:144, AbstractAccessor 
query:67, MetaDbUtil  ^CLPXLPeD

IndexsAccessor.SELECT_ALL_INDEXES ^2tV6dsbn

input sql template ^Wtwdjgoc

select 
        `table_schema`, `table_name`, `non_unique`, `index_schema`, `index_name`, `seq_in_index`, `column_name`,
        `collation`, `cardinality`, `sub_part`, `packed`, `nullable`, `index_type`, `comment`, `index_comment`,
        `index_column_type`, `index_location`, `index_table_name`, `index_status`, `version`, `flag` 
from 
        `indexes`
where `table_schema` = ? 
order by `seq_in_index` ^QSn1WT9R

select
        `table_schema`, `table_name`, `column_name`, `ordinal_position`, `column_default`, `is_nullable`, `data_type`,
        `character_maximum_length`, `character_octet_length`, `numeric_precision`, `numeric_scale`, `datetime_precision`,
        `character_set_name`, `collation_name`, `column_type`, `column_key`, `extra`, `privileges`, `column_comment`,
        `generation_expression`, `jdbc_type`, `jdbc_type_name`, `field_length`, `version`, `status`, `flag` 
from 
        `columns` 
where `table_schema` = ? 
order by ordinal_position asc ^u74ZVsxy

fetchSpecificSchemaTableMetas:565, GmsTableMetaManager 
fetchTablesExtRecords:34, DefaultMetaFetcher 
queryTableExts:160, TableInfoManager  ^vwoJLBVq

TablesExtAccessor.SELECT_TABLES_EXT_ALL ^E6Y8mwzs

query:165, TablesExtAccessor 
query:103, AbstractAccessor 
query:144, AbstractAccessor 
query:67, MetaDbUtil  ^iBnPuWst

input sql template ^89MdyYWt

Lock ^yXFxiAIJ

代码有过修改，行号可能不对应 ^xLRYNnRQ

loadAndCacheTableMeta:666, GmsTableMetaManager 
loadAndCacheTableMeta:641, GmsTableMetaManager 
fetchTableMeta:149, GmsTableMetaManager 
queryVisibleColumns:193, TableInfoManager 
queryColumns:222, TableInfoManager  ^RAxunm1d

select 
        `table_schema`, `table_name`, `column_name`, `ordinal_position`, `column_default`, `is_nullable`, `data_type`, 
        `character_maximum_length`, `character_octet_length`, `numeric_precision`, `numeric_scale`, `datetime_precision`, 
        `character_set_name`, `collation_name`, `column_type`, `column_key`, `extra`, `privileges`, `column_comment`, 
        `generation_expression`, `jdbc_type`, `jdbc_type_name`, `field_length`, `version`, `status`, `flag` from `columns` 
where `table_schema` = ? and `table_name` = ? 
order by ordinal_position asc ^WnNpKsYp

query:326, ColumnsAccessor 
query:103, AbstractAccessor 
query:144, AbstractAccessor 
query:67, MetaDbUtil  ^dH0kUqOl

ColumnsAccessor.SELECT_COLUMNS ^zm96V68W

fetchTableMeta:151, GmsTableMetaManager 
queryVisibleIndexes:227, TableInfoManager 
queryIndexes:252, TableInfoManager  ^PVoQ3Qoe

query:267, IndexesAccessor 
query:103, AbstractAccessor 
query:144, AbstractAccessor 
query:67, MetaDbUtil  ^mV0MLAto

select 
        `table_schema`, `table_name`, `non_unique`, `index_schema`, `index_name`, `seq_in_index`, `column_name`, `collation`, 
        `cardinality`, `sub_part`, `packed`, `nullable`, `index_type`, `comment`, `index_comment`, `index_column_type`, 
        `index_location`, `index_table_name`, `index_status`, `version`, `flag` 
from 
        `indexes` 
where `table_schema` = ? and `table_name` = ? 
order by `seq_in_index` ^Fix16iuL

IndexesAccessor.SELECT_INDEXES ^kByW0vjU

doFlush:490, OrcWriterTask 
uploadStatFile:658, OrcWriterTask 
storeExtraFileMeta:776, OrcWriterTask  ^8wza8Q9q

.stat ^NBodspMp

addOssFileAndReturnLastInsertId:656, TableMetaChanger 
addOssFileAndReturnLastInsertId:352, TableInfoManager 
insertAndReturnLastInsertId:192, FilesAccessor 
insertAndReturnLastInsertId:97, MetaDbUtil  ^LND0SmlX

storeExtraFileMeta:788, OrcWriterTask  ^WZGP0nC1

changeOssFile:632, TableMetaChanger 
changeOssFile:638, TableMetaChanger 
changeOssFile:357, TableInfoManager 
changeFile:213, FilesAccessor 
update:102, MetaDbUtil  ^I9mRoebe

file size ^8Jy9XrYz

FilesAccessor.CHANGE_FILE_RECORD ^tjniFRJm

doFlush:493, OrcWriterTask 
updateFileMeta:515, OrcWriterTask  ^3F3o95es

changeOssFile:638, TableMetaChanger 
changeOssFile:357, TableInfoManager 
changeFile:213, FilesAccessor 
update:102, MetaDbUtil  ^KD9VPhix

FilesAccessor.CHANGE_FILE_RECORD ^eciQsokB

executeTask:562, DdlEngineDagExecutor 
execute:93, AbstractDdlTask 
execute:58, DdlEngineAccessorDelegate 
invoke:69, AbstractDdlTask$1 
invoke:74, AbstractDdlTask$1 
duringTransaction:85, LoadDataFromFileToObjectStorageTask 
executeImpl:110, LoadDataFromFileToObjectStorageTask 
loadTable:227, LoadDataFromFileToObjectStorageTask  ^Xdda5Hq8

validOssFileMeta:677, TableMetaChanger 
validOssFile:389, TableInfoManager 
valid:361, FilesAccessor 
update:102, MetaDbUtil 
 ^srftSfLh

FilesAccessor.READY_FILES ^IH6ptNu9

loadTable:229, LoadDataFromFileToObjectStorageTask  ^miL2xALs

validOssColumnMeta:699, TableMetaChanger 
validOSSColumnsMeta:405, TableInfoManager 
valid:163, ColumnMetaAccessor 
update:102, MetaDbUtil  ^Q8k0SUp4

ColumnMetaAccessor.READY_COLUMN_META ^w8OontoP

executeTask:562, DdlEngineDagExecutor 
execute:93, AbstractDdlTask 
execute:58, DdlEngineAccessorDelegate 
invoke:69, AbstractDdlTask$1 
invoke:74, AbstractDdlTask$1 
duringTransaction:51, UpdateFileCommitTsTask 
executeImpl:84, UpdateFileCommitTsTask  ^unmSLjOW

updateFilesCommitTs:340, TableInfoManager 
updateFilesCommitTs:283, FilesAccessor 
delete:123, MetaDbUtil  ^SMdddm72

FilesAccessor.UPDATE_COMMIT_TS ^rfhLHAlQ


# Embedded files
c94aaf6fe202102cb055b33063a6ed206b0933c1: [[Pasted Image 20230508170809_683.png]]

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
			"version": 148,
			"versionNonce": 1700783566,
			"isDeleted": false,
			"id": "JAhu5mfG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -567.62890625,
			"y": 467.23046875,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 506.25,
			"height": 192,
			"seed": 528972678,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "waJ4s921rHfW56ShQ3lLt",
					"type": "arrow"
				}
			],
			"updated": 1684308939722,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "extract:126, LoadDataExtractor \ndoConsume:151, LoadDataExtractor \nconsume:45, OrcConsumer \nconsume:267, OrcWriterTask \ninitNextFile:896, OrcWriterTask \nputFileMeta:645, OrcWriterTask \naddOssFileAndReturnLastInsertId:656, TableMetaChanger \naddOssFileAndReturnLastInsertId:352, TableInfoManager \ninsertAndReturnLastInsertId:192, FilesAccessor \ninsertAndReturnLastInsertId:97, MetaDbUtil ",
			"rawText": "extract:126, LoadDataExtractor \ndoConsume:151, LoadDataExtractor \nconsume:45, OrcConsumer \nconsume:267, OrcWriterTask \ninitNextFile:896, OrcWriterTask \nputFileMeta:645, OrcWriterTask \naddOssFileAndReturnLastInsertId:656, TableMetaChanger \naddOssFileAndReturnLastInsertId:352, TableInfoManager \ninsertAndReturnLastInsertId:192, FilesAccessor \ninsertAndReturnLastInsertId:97, MetaDbUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "extract:126, LoadDataExtractor \ndoConsume:151, LoadDataExtractor \nconsume:45, OrcConsumer \nconsume:267, OrcWriterTask \ninitNextFile:896, OrcWriterTask \nputFileMeta:645, OrcWriterTask \naddOssFileAndReturnLastInsertId:656, TableMetaChanger \naddOssFileAndReturnLastInsertId:352, TableInfoManager \ninsertAndReturnLastInsertId:192, FilesAccessor \ninsertAndReturnLastInsertId:97, MetaDbUtil ",
			"lineHeight": 1.2,
			"baseline": 188
		},
		{
			"type": "text",
			"version": 284,
			"versionNonce": 223651346,
			"isDeleted": false,
			"id": "uhzfKzE4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 160.4765625,
			"y": 509.09765625,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 168.75,
			"height": 19.2,
			"seed": 1030146970,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "uuxeP4K3SXHFUO2Cz00J9",
					"type": "arrow"
				}
			],
			"updated": 1684308939722,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "INSERT_FILE_RECORD",
			"rawText": "INSERT_FILE_RECORD",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "INSERT_FILE_RECORD",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "text",
			"version": 179,
			"versionNonce": 473824270,
			"isDeleted": false,
			"id": "SRHsHkWG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 59.12890625,
			"y": 638.40625,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 468.75,
			"height": 19.2,
			"seed": 479436486,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939722,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "executeInsertAndReturnLastInsertId:158, MetaDbUtil",
			"rawText": "executeInsertAndReturnLastInsertId:158, MetaDbUtil",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "executeInsertAndReturnLastInsertId:158, MetaDbUtil",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "arrow",
			"version": 245,
			"versionNonce": 1270485970,
			"isDeleted": false,
			"id": "yrCtL7wUApyDSXs-RIx88",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -164.44140625,
			"y": 647.50390625,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 205.16796874999997,
			"height": 0.10092566355204191,
			"seed": 534312070,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939722,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					205.16796874999997,
					0.10092566355204191
				]
			]
		},
		{
			"type": "arrow",
			"version": 199,
			"versionNonce": 1937721934,
			"isDeleted": false,
			"id": "uuxeP4K3SXHFUO2Cz00J9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 248.1015625,
			"y": 543.86328125,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.6953125,
			"height": 78.4609375,
			"seed": 749728454,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939722,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "UztUXKk2Y7Qw84Fh9Bi8f",
				"focus": 0.3155614233812298,
				"gap": 1
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
					0.6953125,
					78.4609375
				]
			]
		},
		{
			"type": "text",
			"version": 127,
			"versionNonce": 2125187474,
			"isDeleted": false,
			"id": "xwCFlXrh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 276.265625,
			"y": 571.34765625,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 168.75,
			"height": 19.2,
			"seed": 1706489862,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939722,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "input sql template",
			"rawText": "input sql template",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "input sql template",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "text",
			"version": 457,
			"versionNonce": 1778176142,
			"isDeleted": false,
			"id": "FcEW3TFF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 163.2578125,
			"y": 477.44921875,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 121.875,
			"height": 19.2,
			"seed": 1981204422,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "FilesAccessor",
			"rawText": "FilesAccessor",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "FilesAccessor",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "rectangle",
			"version": 189,
			"versionNonce": 1566623570,
			"isDeleted": false,
			"id": "UztUXKk2Y7Qw84Fh9Bi8f",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 148.5390625,
			"y": 460.328125,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 290.1796875,
			"height": 82.8359375,
			"seed": 869757126,
			"groupIds": [],
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "uuxeP4K3SXHFUO2Cz00J9",
					"type": "arrow"
				}
			],
			"updated": 1684308939723,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 997166798,
			"isDeleted": false,
			"id": "CVlSyek4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -528.9609375,
			"y": -975.0322265625,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 421.875,
			"height": 230.39999999999998,
			"seed": 1117429894,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "61EtbjGTQ_NxBhYu-N6f7",
					"type": "arrow"
				}
			],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "executeSQL:81, TPreparedStatement \nexecuteSQL:311, TConnection \nexecuteQuery:487, TConnection \nexecute:59, PlanExecutor \nexecByExecPlanNodeByOne:109, PlanExecutor \nexecute:77, ExecutorHelper \nexecuteByCursor:142, ExecutorHelper \nexecByExecPlanNode:105, TransactionExecutor \nexecByExecPlanNode:53, TopologyExecutor \nexecByExecPlanNode:52, AbstractGroupExecutor \nexecuteInner:74, AbstractGroupExecutor \nhandlePlan:97, HandlerCommon ",
			"rawText": "executeSQL:81, TPreparedStatement \nexecuteSQL:311, TConnection \nexecuteQuery:487, TConnection \nexecute:59, PlanExecutor \nexecByExecPlanNodeByOne:109, PlanExecutor \nexecute:77, ExecutorHelper \nexecuteByCursor:142, ExecutorHelper \nexecByExecPlanNode:105, TransactionExecutor \nexecByExecPlanNode:53, TopologyExecutor \nexecByExecPlanNode:52, AbstractGroupExecutor \nexecuteInner:74, AbstractGroupExecutor \nhandlePlan:97, HandlerCommon ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "executeSQL:81, TPreparedStatement \nexecuteSQL:311, TConnection \nexecuteQuery:487, TConnection \nexecute:59, PlanExecutor \nexecByExecPlanNodeByOne:109, PlanExecutor \nexecute:77, ExecutorHelper \nexecuteByCursor:142, ExecutorHelper \nexecByExecPlanNode:105, TransactionExecutor \nexecByExecPlanNode:53, TopologyExecutor \nexecByExecPlanNode:52, AbstractGroupExecutor \nexecuteInner:74, AbstractGroupExecutor \nhandlePlan:97, HandlerCommon ",
			"lineHeight": 1.2,
			"baseline": 226
		},
		{
			"type": "text",
			"version": 103,
			"versionNonce": 540019986,
			"isDeleted": false,
			"id": "1zZo4yJH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -542.4921875,
			"y": -622.5927734375,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 478.125,
			"height": 134.4,
			"seed": 168704026,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "61EtbjGTQ_NxBhYu-N6f7",
					"type": "arrow"
				},
				{
					"id": "u19dAADO5U0qE0zlg2bt8",
					"type": "arrow"
				}
			],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "handle:77, LogicalCommonDdlHandler \nhandleDdlRequest:153, LogicalCommonDdlHandler \nexecute:99, DdlEngineRequester \nstoreJob:122, DdlJobManager \nstoreJobImpl:165, DdlJobManager \nacquireResource:100, DdlEngineResourceManager \ntryReadWriteLockBatch:549, PersistentReadWriteLock ",
			"rawText": "handle:77, LogicalCommonDdlHandler \nhandleDdlRequest:153, LogicalCommonDdlHandler \nexecute:99, DdlEngineRequester \nstoreJob:122, DdlJobManager \nstoreJobImpl:165, DdlJobManager \nacquireResource:100, DdlEngineResourceManager \ntryReadWriteLockBatch:549, PersistentReadWriteLock ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "handle:77, LogicalCommonDdlHandler \nhandleDdlRequest:153, LogicalCommonDdlHandler \nexecute:99, DdlEngineRequester \nstoreJob:122, DdlJobManager \nstoreJobImpl:165, DdlJobManager \nacquireResource:100, DdlEngineResourceManager \ntryReadWriteLockBatch:549, PersistentReadWriteLock ",
			"lineHeight": 1.2,
			"baseline": 130
		},
		{
			"type": "text",
			"version": 77,
			"versionNonce": 1148224782,
			"isDeleted": false,
			"id": "ZZot9Nri",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 113.81640625,
			"y": -590.3583984375,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 356.25,
			"height": 96,
			"seed": 55772422,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "u19dAADO5U0qE0zlg2bt8",
					"type": "arrow"
				},
				{
					"id": "SDKudqsfwCSIp18XUxUHL",
					"type": "arrow"
				}
			],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "execute:47, MetaDbAccessorWrapper \ninvoke:465, PersistentReadWriteLock$9 \ninvoke:525, PersistentReadWriteLock$9 \ninsert:102, ReadWriteLockAccessor \n",
			"rawText": "execute:47, MetaDbAccessorWrapper \ninvoke:465, PersistentReadWriteLock$9 \ninvoke:525, PersistentReadWriteLock$9 \ninsert:102, ReadWriteLockAccessor \n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "execute:47, MetaDbAccessorWrapper \ninvoke:465, PersistentReadWriteLock$9 \ninvoke:525, PersistentReadWriteLock$9 \ninsert:102, ReadWriteLockAccessor \n",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 94,
			"versionNonce": 1552980690,
			"isDeleted": false,
			"id": "61EtbjGTQ_NxBhYu-N6f7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -331.97265625,
			"y": -722.7880859375,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.21875,
			"height": 78.9375,
			"seed": 1646541958,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "CVlSyek4",
				"focus": 0.05562970598646423,
				"gap": 21.844140624999966
			},
			"endBinding": {
				"elementId": "1zZo4yJH",
				"focus": -0.12964370303400613,
				"gap": 21.257812500000057
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
					-1.21875,
					78.9375
				]
			]
		},
		{
			"type": "arrow",
			"version": 102,
			"versionNonce": 1719186254,
			"isDeleted": false,
			"id": "u19dAADO5U0qE0zlg2bt8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -39.21484375,
			"y": -562.973210341464,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 135.21875000000003,
			"height": 2.227837401675515,
			"seed": 829196614,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "1zZo4yJH",
				"focus": -0.045385177439852466,
				"gap": 25.15234375
			},
			"endBinding": {
				"elementId": "ZZot9Nri",
				"focus": 0.5118485053265613,
				"gap": 17.8125
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
					135.21875000000003,
					-2.227837401675515
				]
			]
		},
		{
			"type": "text",
			"version": 130,
			"versionNonce": 1629057170,
			"isDeleted": false,
			"id": "KqlYPcwD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 647.7890625,
			"y": -567.79296875,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 262.5,
			"height": 38.4,
			"seed": 1941299290,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "SDKudqsfwCSIp18XUxUHL",
					"type": "arrow"
				}
			],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "insert:92, MetaDbUtil \nexecuteBatch:144, MetaDbUtil",
			"rawText": "insert:92, MetaDbUtil \nexecuteBatch:144, MetaDbUtil",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "insert:92, MetaDbUtil \nexecuteBatch:144, MetaDbUtil",
			"lineHeight": 1.2,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 113,
			"versionNonce": 1809914254,
			"isDeleted": false,
			"id": "u6p4rkYw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 646.3125,
			"y": -726.594482421875,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 103.125,
			"height": 19.2,
			"seed": 1389446,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "INSERT_DATA",
			"rawText": "INSERT_DATA",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "INSERT_DATA",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "text",
			"version": 103,
			"versionNonce": 293703250,
			"isDeleted": false,
			"id": "bx6FgVqY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 643.3125,
			"y": -762.399169921875,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 196.875,
			"height": 19.2,
			"seed": 640840410,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "ReadWriteLockAccessor",
			"rawText": "ReadWriteLockAccessor",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ReadWriteLockAccessor",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "arrow",
			"version": 94,
			"versionNonce": 1810020302,
			"isDeleted": false,
			"id": "PAq2qTJMuLLr5Pyv8w6Ay",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 727.99609375,
			"y": -690.9833984375,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.203125,
			"height": 102.23828125,
			"seed": 2094474758,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					2.203125,
					102.23828125
				]
			]
		},
		{
			"type": "text",
			"version": 87,
			"versionNonce": 1117778962,
			"isDeleted": false,
			"id": "GA4XKqgb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 781.20703125,
			"y": -641.0146484375,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 168.75,
			"height": 19.2,
			"seed": 1115398854,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "input sql template",
			"rawText": "input sql template",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "input sql template",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "rectangle",
			"version": 108,
			"versionNonce": 781618702,
			"isDeleted": false,
			"id": "PMzZuT4VSCCSJ-L4p_Lab",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 629.4609375,
			"y": -786.3466796875,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 247.5390625,
			"height": 97.1484375,
			"seed": 1544976346,
			"groupIds": [],
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 87,
			"versionNonce": 376152530,
			"isDeleted": false,
			"id": "SDKudqsfwCSIp18XUxUHL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 487.37890625,
			"y": -548.2919921875,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 150.89453125,
			"height": 2.5703125,
			"seed": 755987014,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZZot9Nri",
				"focus": -0.05103530855257176,
				"gap": 17.3125
			},
			"endBinding": {
				"elementId": "KqlYPcwD",
				"focus": 0.2177263315638391,
				"gap": 9.515625
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
					150.89453125,
					-2.5703125
				]
			]
		},
		{
			"type": "text",
			"version": 86,
			"versionNonce": 284531790,
			"isDeleted": false,
			"id": "l1GR7N4F",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -534.30078125,
			"y": -62.4853515625,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 543.75,
			"height": 192,
			"seed": 1000064922,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "bzDxNBLE2DBMnRGDtB_Ys",
					"type": "arrow"
				}
			],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "executeTask:562, DdlEngineDagExecutor \nexecute:93, AbstractDdlTask \nexecute:58, DdlEngineAccessorDelegate \ninvoke:69, AbstractDdlTask$1 \ninvoke:74, AbstractDdlTask$1 \nduringTransaction:85, LoadDataFromFileToObjectStorageTask \nexecuteImpl:95, LoadDataFromFileToObjectStorageTask \nlockOssFileMeta:667, TableMetaChanger \nlockOssFile:381, TableInfoManager \nlock:297, FilesAccessor ",
			"rawText": "executeTask:562, DdlEngineDagExecutor \nexecute:93, AbstractDdlTask \nexecute:58, DdlEngineAccessorDelegate \ninvoke:69, AbstractDdlTask$1 \ninvoke:74, AbstractDdlTask$1 \nduringTransaction:85, LoadDataFromFileToObjectStorageTask \nexecuteImpl:95, LoadDataFromFileToObjectStorageTask \nlockOssFileMeta:667, TableMetaChanger \nlockOssFile:381, TableInfoManager \nlock:297, FilesAccessor ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "executeTask:562, DdlEngineDagExecutor \nexecute:93, AbstractDdlTask \nexecute:58, DdlEngineAccessorDelegate \ninvoke:69, AbstractDdlTask$1 \ninvoke:74, AbstractDdlTask$1 \nduringTransaction:85, LoadDataFromFileToObjectStorageTask \nexecuteImpl:95, LoadDataFromFileToObjectStorageTask \nlockOssFileMeta:667, TableMetaChanger \nlockOssFile:381, TableInfoManager \nlock:297, FilesAccessor ",
			"lineHeight": 1.2,
			"baseline": 188
		},
		{
			"type": "text",
			"version": 146,
			"versionNonce": 1476106130,
			"isDeleted": false,
			"id": "X830sl7S",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 236.62109375,
			"y": 48.53125,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 196.875,
			"height": 19.2,
			"seed": 983352902,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "ewyjxZm3X8GvmAjj4PW5B",
					"type": "arrow"
				},
				{
					"id": "bzDxNBLE2DBMnRGDtB_Ys",
					"type": "arrow"
				},
				{
					"id": "n7oVU9wn0bxsMRM016now",
					"type": "arrow"
				}
			],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "query:67, MetaDbUtil ",
			"rawText": "query:67, MetaDbUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "query:67, MetaDbUtil ",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "text",
			"version": 126,
			"versionNonce": 1759044238,
			"isDeleted": false,
			"id": "QZGtQg6t",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 234.875,
			"y": -113.678466796875,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 112.5,
			"height": 19.2,
			"seed": 682476998,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "FileAccessor",
			"rawText": "FileAccessor",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "FileAccessor",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 1468454226,
			"isDeleted": false,
			"id": "MdUXpmmt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 232.64453125,
			"y": -65.780029296875,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 178.125,
			"height": 19.2,
			"seed": 9681542,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "SELECT_FOR_ROLLBACK",
			"rawText": "SELECT_FOR_ROLLBACK",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SELECT_FOR_ROLLBACK",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "rectangle",
			"version": 99,
			"versionNonce": 1761173710,
			"isDeleted": false,
			"id": "wDx52OCmM3t2Qgpd0HH0R",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 208.203125,
			"y": -121.334716796875,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 229.15625,
			"height": 88.22265625,
			"seed": 141310470,
			"groupIds": [],
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "ewyjxZm3X8GvmAjj4PW5B",
					"type": "arrow"
				}
			],
			"updated": 1684308939723,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 161,
			"versionNonce": 1180982034,
			"isDeleted": false,
			"id": "ewyjxZm3X8GvmAjj4PW5B",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 313.5592864262786,
			"y": -26.100341796875007,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.729324118119962,
			"height": 60.914062500000014,
			"seed": 591707462,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "wDx52OCmM3t2Qgpd0HH0R",
				"focus": 0.0685414899728241,
				"gap": 7.01171875
			},
			"endBinding": {
				"elementId": "X830sl7S",
				"focus": -0.24202812732613552,
				"gap": 13.717529296874993
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
					-1.729324118119962,
					60.914062500000014
				]
			]
		},
		{
			"type": "arrow",
			"version": 166,
			"versionNonce": 82843406,
			"isDeleted": false,
			"id": "bzDxNBLE2DBMnRGDtB_Ys",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 16.05859375,
			"y": 52.1093528924587,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 208.3828125,
			"height": 2.5436215890604643,
			"seed": 1911706886,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "l1GR7N4F",
				"focus": 0.1521495996924022,
				"gap": 6.609375
			},
			"endBinding": {
				"elementId": "X830sl7S",
				"focus": 0.19701093232391556,
				"gap": 12.1796875
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
					208.3828125,
					2.5436215890604643
				]
			]
		},
		{
			"type": "text",
			"version": 164,
			"versionNonce": 319498450,
			"isDeleted": false,
			"id": "xORIYtKu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 601.53125,
			"y": 503.502685546875,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 56.25,
			"height": 57.599999999999994,
			"seed": 2098331034,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": ".orc\n.stat\nsketch",
			"rawText": ".orc\n.stat\nsketch",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": ".orc\n.stat\nsketch",
			"lineHeight": 1.2,
			"baseline": 53
		},
		{
			"type": "arrow",
			"version": 105,
			"versionNonce": 1429603662,
			"isDeleted": false,
			"id": "2HwhArfUe3Bd1Gf21Hv_k",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 686.60546875,
			"y": 502.048095703125,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.17578125,
			"height": 71.28125,
			"seed": 937916742,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939724,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					2.17578125,
					71.28125
				]
			]
		},
		{
			"type": "text",
			"version": 181,
			"versionNonce": 664725138,
			"isDeleted": false,
			"id": "cedfsmz5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -717.1829151532389,
			"y": 3094.5712395574396,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 431.25,
			"height": 288,
			"seed": 325567174,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "zkQfV7exoLZHWKMYiXV71",
					"type": "arrow"
				}
			],
			"updated": 1684309865989,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "run:-1, FutureTask \nrun$$$capture:264, FutureTask \ncall:54, AsyncCallableTask \ncall:459, DdlEngineScheduler$DdlJobExecutor \ncall:482, DdlEngineScheduler$DdlJobExecutor \nrestoreDDL:99, ServerConfigManager \nrestoreDDL:466, MatrixConfigHolder \nrestoreAndRun:173, DdlEngineDagExecutor \nrun:258, DdlEngineDagExecutor \nonFinished:441, DdlEngineDagExecutor \nremoveJob:399, DdlJobManager \nexecute:58, DdlEngineAccessorDelegate \ninvoke:372, DdlJobManager$1 \ninvoke:394, DdlJobManager$1 \nreleaseResource:189, DdlEngineResourceManager ",
			"rawText": "run:-1, FutureTask \nrun$$$capture:264, FutureTask \ncall:54, AsyncCallableTask \ncall:459, DdlEngineScheduler$DdlJobExecutor \ncall:482, DdlEngineScheduler$DdlJobExecutor \nrestoreDDL:99, ServerConfigManager \nrestoreDDL:466, MatrixConfigHolder \nrestoreAndRun:173, DdlEngineDagExecutor \nrun:258, DdlEngineDagExecutor \nonFinished:441, DdlEngineDagExecutor \nremoveJob:399, DdlJobManager \nexecute:58, DdlEngineAccessorDelegate \ninvoke:372, DdlJobManager$1 \ninvoke:394, DdlJobManager$1 \nreleaseResource:189, DdlEngineResourceManager ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "run:-1, FutureTask \nrun$$$capture:264, FutureTask \ncall:54, AsyncCallableTask \ncall:459, DdlEngineScheduler$DdlJobExecutor \ncall:482, DdlEngineScheduler$DdlJobExecutor \nrestoreDDL:99, ServerConfigManager \nrestoreDDL:466, MatrixConfigHolder \nrestoreAndRun:173, DdlEngineDagExecutor \nrun:258, DdlEngineDagExecutor \nonFinished:441, DdlEngineDagExecutor \nremoveJob:399, DdlJobManager \nexecute:58, DdlEngineAccessorDelegate \ninvoke:372, DdlJobManager$1 \ninvoke:394, DdlJobManager$1 \nreleaseResource:189, DdlEngineResourceManager ",
			"lineHeight": 1.2,
			"baseline": 284
		},
		{
			"type": "text",
			"version": 250,
			"versionNonce": 333988946,
			"isDeleted": false,
			"id": "f2vEHzBG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -47.07632394257428,
			"y": 3363.981177267274,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 553.125,
			"height": 38.4,
			"seed": 2015465818,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "QOjFX6xkvCPQEfpGULr6O",
					"type": "arrow"
				}
			],
			"updated": 1684309865989,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "unlockReadWriteByOwner:331, PersistentReadWriteLock \ndeleteByOwnerAndResourceAndType:220, ReadWriteLockAccessor ",
			"rawText": "unlockReadWriteByOwner:331, PersistentReadWriteLock \ndeleteByOwnerAndResourceAndType:220, ReadWriteLockAccessor ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "unlockReadWriteByOwner:331, PersistentReadWriteLock \ndeleteByOwnerAndResourceAndType:220, ReadWriteLockAccessor ",
			"lineHeight": 1.2,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 235,
			"versionNonce": 1925179922,
			"isDeleted": false,
			"id": "1VLoVOyk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 695.4542353293826,
			"y": 3366.861969157625,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 215.625,
			"height": 19.2,
			"seed": 2090631898,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684309865989,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "delete:123, MetaDbUtil ",
			"rawText": "delete:123, MetaDbUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "delete:123, MetaDbUtil ",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "arrow",
			"version": 343,
			"versionNonce": 601444626,
			"isDeleted": false,
			"id": "zkQfV7exoLZHWKMYiXV71",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -265.0619765649566,
			"y": 3380.4145901104393,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 198.30167460144912,
			"height": 1.9262608460851425,
			"seed": 1806774106,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684309865998,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "cedfsmz5",
				"focus": 0.9866256905720933,
				"gap": 20.870938588282343
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
					198.30167460144912,
					-1.9262608460851425
				]
			]
		},
		{
			"type": "arrow",
			"version": 341,
			"versionNonce": 502104334,
			"isDeleted": false,
			"id": "QOjFX6xkvCPQEfpGULr6O",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 514.0245418887333,
			"y": 3376.691059099926,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 147.28156031652316,
			"height": 1.1007204834770619,
			"seed": 1446429914,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684309865998,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "f2vEHzBG",
				"focus": -0.40516640935871145,
				"gap": 7.975865831307601
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
					147.28156031652316,
					1.1007204834770619
				]
			]
		},
		{
			"type": "text",
			"version": 181,
			"versionNonce": 60474958,
			"isDeleted": false,
			"id": "6ZYdP46p",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 600.9986588409905,
			"y": 3195.7708788518244,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 271.875,
			"height": 19.2,
			"seed": 93910406,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684309865989,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "DELETE_BY_OWNER_RESOURCE_TYPE",
			"rawText": "DELETE_BY_OWNER_RESOURCE_TYPE",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "DELETE_BY_OWNER_RESOURCE_TYPE",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "text",
			"version": 227,
			"versionNonce": 756419986,
			"isDeleted": false,
			"id": "3hDqzm9Y",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 604.0772364432163,
			"y": 3151.862450815614,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 196.875,
			"height": 19.2,
			"seed": 1715822426,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684309865989,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "ReadWriteLockAccessor",
			"rawText": "ReadWriteLockAccessor",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ReadWriteLockAccessor",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "rectangle",
			"version": 241,
			"versionNonce": 1632160910,
			"isDeleted": false,
			"id": "S0ZtC4LblwBLU0QN1D4yP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 576.0346622508777,
			"y": 3133.2361963842723,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 335.53916050624184,
			"height": 97.38796465140547,
			"seed": 1279971270,
			"groupIds": [],
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1684309865989,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 204,
			"versionNonce": 1306692434,
			"isDeleted": false,
			"id": "TTo0XbpBro5aX_y7N3wQs",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 797.2192837783654,
			"y": 3260.231822165461,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.325487524914934,
			"height": 73.65367922642736,
			"seed": 1274485510,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684309865989,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					4.325487524914934,
					73.65367922642736
				]
			]
		},
		{
			"type": "text",
			"version": 180,
			"versionNonce": 1608256206,
			"isDeleted": false,
			"id": "GPJQKL0L",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 837.335385773845,
			"y": 3289.160132371848,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 168.75,
			"height": 19.2,
			"seed": 1490615002,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684309865989,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "input sql template",
			"rawText": "input sql template",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "input sql template",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "ellipse",
			"version": 2181,
			"versionNonce": 1614734162,
			"isDeleted": false,
			"id": "7DiblpNRUlwWPxa6cAgQy",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2931.1140550872365,
			"y": 2074.2240645963057,
			"strokeColor": "#000000",
			"backgroundColor": "#000000",
			"width": 96.52202183439317,
			"height": 20.004850378308763,
			"seed": 1310688697,
			"groupIds": [
				"xrxotGxTCiYa9Wu8vA4NY",
				"HDssYMWCVE0LtFate7Fc_",
				"ObfgK9hDSe5NM-t7b1oHT",
				"w9UQcl8fmD5dEEegp2uWS"
			],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939724,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1925,
			"versionNonce": 1913729742,
			"isDeleted": false,
			"id": "YnsIzTG3Kltf--a6uNacj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2931.2979293340186,
			"y": 2084.068090819431,
			"strokeColor": "#000000",
			"backgroundColor": "#000000",
			"width": 97.00078031317385,
			"height": 4.306312178788209,
			"seed": 1238339159,
			"groupIds": [
				"xrxotGxTCiYa9Wu8vA4NY",
				"HDssYMWCVE0LtFate7Fc_",
				"ObfgK9hDSe5NM-t7b1oHT",
				"w9UQcl8fmD5dEEegp2uWS"
			],
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1684308939724,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 2194,
			"versionNonce": 1491773714,
			"isDeleted": false,
			"id": "Iv77ZVrZ1VBw0_uyQfLiT",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2930.981369420825,
			"y": 2079.620655546043,
			"strokeColor": "#000000",
			"backgroundColor": "#000000",
			"width": 96.52202183439317,
			"height": 20.004850378308763,
			"seed": 662202009,
			"groupIds": [
				"xrxotGxTCiYa9Wu8vA4NY",
				"HDssYMWCVE0LtFate7Fc_",
				"ObfgK9hDSe5NM-t7b1oHT",
				"w9UQcl8fmD5dEEegp2uWS"
			],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939724,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 2282,
			"versionNonce": 2134747406,
			"isDeleted": false,
			"id": "KrYSD32Iffkxyvrykb383",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2930.981369420825,
			"y": 2072.260326686487,
			"strokeColor": "#228be6",
			"backgroundColor": "#228be6",
			"width": 96.52202183439317,
			"height": 20.004850378308763,
			"seed": 2006559607,
			"groupIds": [
				"onpS0hsGQNh2U5gz66jrf",
				"HDssYMWCVE0LtFate7Fc_",
				"ObfgK9hDSe5NM-t7b1oHT",
				"w9UQcl8fmD5dEEegp2uWS"
			],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939724,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 839,
			"versionNonce": 1536669394,
			"isDeleted": false,
			"id": "vRe2ReSasndmGJMJy1wRy",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2927.3106297461773,
			"y": 2019.5486970715124,
			"strokeColor": "#228be6",
			"backgroundColor": "#228be6",
			"width": 88.59091589797377,
			"height": 58.65035554194236,
			"seed": 683813753,
			"groupIds": [
				"HDssYMWCVE0LtFate7Fc_",
				"ObfgK9hDSe5NM-t7b1oHT",
				"w9UQcl8fmD5dEEegp2uWS"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939724,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 2117,
			"versionNonce": 335632206,
			"isDeleted": false,
			"id": "lPuZHwiUh13fWTiIZT12N",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2931.058550094629,
			"y": 2002.9559146834622,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 96.52202183439317,
			"height": 20.004850378308763,
			"seed": 1550001303,
			"groupIds": [
				"HDssYMWCVE0LtFate7Fc_",
				"ObfgK9hDSe5NM-t7b1oHT",
				"w9UQcl8fmD5dEEegp2uWS"
			],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939724,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1989,
			"versionNonce": 685575314,
			"isDeleted": false,
			"id": "cptyHPIFaXnNw2sKVnip7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2931.058550094629,
			"y": 1996.0759135227072,
			"strokeColor": "#000000",
			"backgroundColor": "#000000",
			"width": 96.52202183439317,
			"height": 20.004850378308763,
			"seed": 1782600793,
			"groupIds": [
				"HDssYMWCVE0LtFate7Fc_",
				"ObfgK9hDSe5NM-t7b1oHT",
				"w9UQcl8fmD5dEEegp2uWS"
			],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939724,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1604,
			"versionNonce": 682966414,
			"isDeleted": false,
			"id": "XQNXdy9Jq5jTFr7f06JXU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2929.571503771267,
			"y": 1996.833321254468,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 93.54792918767022,
			"height": 24.063182930955556,
			"seed": 400587191,
			"groupIds": [
				"HDssYMWCVE0LtFate7Fc_",
				"ObfgK9hDSe5NM-t7b1oHT",
				"w9UQcl8fmD5dEEegp2uWS"
			],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939724,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1354,
			"versionNonce": 1450289746,
			"isDeleted": false,
			"id": "QC1TaNn6FYvKRZNcIKHaQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2834.384070812463,
			"y": 2005.8844383097085,
			"strokeColor": "#000000",
			"backgroundColor": "#000000",
			"width": 0.22821165216410086,
			"height": 82.96189843655773,
			"seed": 801530169,
			"groupIds": [
				"HDssYMWCVE0LtFate7Fc_",
				"ObfgK9hDSe5NM-t7b1oHT",
				"w9UQcl8fmD5dEEegp2uWS"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939724,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.22821165216410086,
					82.96189843655773
				]
			]
		},
		{
			"type": "line",
			"version": 1543,
			"versionNonce": 1116888014,
			"isDeleted": false,
			"id": "fwTQOp6zeIkXJyWc2dgHG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2931.153965664069,
			"y": 2006.2267786420302,
			"strokeColor": "#000000",
			"backgroundColor": "#000000",
			"width": 0.3423540447664115,
			"height": 82.39133273962715,
			"seed": 1597385431,
			"groupIds": [
				"HDssYMWCVE0LtFate7Fc_",
				"ObfgK9hDSe5NM-t7b1oHT",
				"w9UQcl8fmD5dEEegp2uWS"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.3423540447664115,
					82.39133273962715
				]
			]
		},
		{
			"type": "text",
			"version": 574,
			"versionNonce": 724340754,
			"isDeleted": false,
			"id": "YQGW5OR5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2920.381481264298,
			"y": 2034.106275078872,
			"strokeColor": "#ffffff",
			"backgroundColor": "#228be6",
			"width": 75.75343322753906,
			"height": 49.52598262860923,
			"seed": 1311220503,
			"groupIds": [
				"ObfgK9hDSe5NM-t7b1oHT",
				"w9UQcl8fmD5dEEegp2uWS"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"fontSize": 39.62078610288738,
			"fontFamily": 1,
			"text": "SQL",
			"rawText": "SQL",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SQL",
			"lineHeight": 1.25,
			"baseline": 35
		},
		{
			"type": "text",
			"version": 395,
			"versionNonce": 1471263246,
			"isDeleted": false,
			"id": "whOgMqPI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2951.4064789967965,
			"y": 1954.7537168982672,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 139.91514587402344,
			"height": 35.37570187757802,
			"seed": 1071117794,
			"groupIds": [
				"w9UQcl8fmD5dEEegp2uWS"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"fontSize": 28.30056150206241,
			"fontFamily": 1,
			"text": "Database",
			"rawText": "Database",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Database",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "rectangle",
			"version": 847,
			"versionNonce": 2063908306,
			"isDeleted": false,
			"id": "wb6o0xB5Aq9jld4yASJXm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2938.5953523414155,
			"y": 3720.312527441819,
			"strokeColor": "#0072ca",
			"backgroundColor": "#0072ca",
			"width": 149.016393442623,
			"height": 139.08196721311475,
			"seed": 2101619347,
			"groupIds": [
				"z0Fx3M-BbxYSOJ_oMexg2",
				"I6Da4SFh8KAZvj42WjnvD",
				"5Jfqn2_sk5xZBzKiXslJb"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 725,
			"versionNonce": 856440910,
			"isDeleted": false,
			"id": "8iMy3DixNeUkiRQTrSfYu",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2932.5953523414155,
			"y": 3829.5912159664094,
			"strokeColor": "#0072ca",
			"backgroundColor": "#0072ca",
			"width": 141.01639344262256,
			"height": 57.606557377049185,
			"seed": 139967517,
			"groupIds": [
				"z0Fx3M-BbxYSOJ_oMexg2",
				"I6Da4SFh8KAZvj42WjnvD",
				"5Jfqn2_sk5xZBzKiXslJb"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 705,
			"versionNonce": 51458962,
			"isDeleted": false,
			"id": "N4gziE8xr0v5I6b9vQsGm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2938.5953523414155,
			"y": 3687.1977733434587,
			"strokeColor": "#e8e8e8",
			"backgroundColor": "#e8e8e8",
			"width": 147.36065573770455,
			"height": 59.606557377049185,
			"seed": 388456499,
			"groupIds": [
				"z0Fx3M-BbxYSOJ_oMexg2",
				"I6Da4SFh8KAZvj42WjnvD",
				"5Jfqn2_sk5xZBzKiXslJb"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 710,
			"versionNonce": 1484457614,
			"isDeleted": false,
			"id": "aqTeCG5zzBfJ1FCJrvV9Y",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2918.7264998823994,
			"y": 3700.443674982803,
			"strokeColor": "#50e6ff",
			"backgroundColor": "#50e6ff",
			"width": 105.96721311475375,
			"height": 36.426229508196734,
			"seed": 1503932541,
			"groupIds": [
				"z0Fx3M-BbxYSOJ_oMexg2",
				"I6Da4SFh8KAZvj42WjnvD",
				"5Jfqn2_sk5xZBzKiXslJb"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false
		},
		{
			"type": "freedraw",
			"version": 1051,
			"versionNonce": 1166602578,
			"isDeleted": false,
			"id": "votveP8pQ2g5aXW-h9pe7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2907.136335947973,
			"y": 3720.312527441819,
			"strokeColor": "#32bedd",
			"backgroundColor": "#32bedd",
			"width": 89.40983606557377,
			"height": 11.59016393442623,
			"seed": 642965971,
			"groupIds": [
				"z0Fx3M-BbxYSOJ_oMexg2",
				"I6Da4SFh8KAZvj42WjnvD",
				"5Jfqn2_sk5xZBzKiXslJb"
			],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"points": [
				[
					0.4730679156908663,
					0
				],
				[
					2.6018735362997654,
					0
				],
				[
					11.117096018735362,
					1.2877959927140257
				],
				[
					15.37470725995316,
					1.2877959927140257
				],
				[
					19.632318501170957,
					1.2877959927140257
				],
				[
					21.761124121779858,
					1.2877959927140257
				],
				[
					28.147540983606557,
					1.2877959927140257
				],
				[
					34.53395784543325,
					1.2877959927140257
				],
				[
					36.66276346604216,
					1.2877959927140257
				],
				[
					38.791569086651045,
					1.2877959927140257
				],
				[
					43.04918032786885,
					1.2877959927140257
				],
				[
					45.17798594847774,
					1.2877959927140257
				],
				[
					47.30679156908665,
					2.5755919854280513
				],
				[
					51.564402810304436,
					2.5755919854280513
				],
				[
					57.95081967213114,
					2.5755919854280513
				],
				[
					60.07962529274003,
					2.5755919854280513
				],
				[
					62.20843091334895,
					2.5755919854280513
				],
				[
					64.33723653395785,
					3.863387978142077
				],
				[
					66.46604215456674,
					3.863387978142077
				],
				[
					68.59484777517564,
					3.863387978142077
				],
				[
					70.72365339578452,
					3.863387978142077
				],
				[
					72.85245901639344,
					3.863387978142077
				],
				[
					74.98126463700234,
					3.863387978142077
				],
				[
					77.11007025761124,
					5.151183970856103
				],
				[
					79.23887587822014,
					5.151183970856103
				],
				[
					77.11007025761124,
					5.151183970856103
				],
				[
					74.98126463700234,
					5.151183970856103
				],
				[
					64.33723653395785,
					3.863387978142077
				],
				[
					62.20843091334895,
					3.863387978142077
				],
				[
					51.564402810304436,
					3.863387978142077
				],
				[
					49.435597189695535,
					3.863387978142077
				],
				[
					47.30679156908665,
					3.863387978142077
				],
				[
					43.04918032786885,
					3.863387978142077
				],
				[
					40.92037470725995,
					3.863387978142077
				],
				[
					38.791569086651045,
					3.863387978142077
				],
				[
					36.66276346604216,
					3.863387978142077
				],
				[
					34.53395784543325,
					3.863387978142077
				],
				[
					32.40515222482435,
					3.863387978142077
				],
				[
					30.276346604215455,
					3.863387978142077
				],
				[
					28.147540983606557,
					3.863387978142077
				],
				[
					26.018735362997653,
					3.863387978142077
				],
				[
					23.88992974238876,
					3.863387978142077
				],
				[
					21.761124121779858,
					3.863387978142077
				],
				[
					17.50351288056206,
					3.863387978142077
				],
				[
					15.37470725995316,
					3.863387978142077
				],
				[
					13.24590163934426,
					3.863387978142077
				],
				[
					11.117096018735362,
					3.863387978142077
				],
				[
					0.4730679156908663,
					3.863387978142077
				],
				[
					-1.6557377049180328,
					5.151183970856103
				],
				[
					-1.6557377049180328,
					3.863387978142077
				],
				[
					8.988290398126463,
					1.2877959927140257
				],
				[
					13.24590163934426,
					0
				],
				[
					21.761124121779858,
					0
				],
				[
					26.018735362997653,
					0
				],
				[
					28.147540983606557,
					0
				],
				[
					32.40515222482435,
					0
				],
				[
					36.66276346604216,
					0
				],
				[
					40.92037470725995,
					0
				],
				[
					45.17798594847774,
					0
				],
				[
					51.564402810304436,
					0
				],
				[
					55.82201405152224,
					0
				],
				[
					60.07962529274003,
					0
				],
				[
					62.20843091334895,
					0
				],
				[
					64.33723653395785,
					0
				],
				[
					66.46604215456674,
					0
				],
				[
					66.46604215456674,
					1.2877959927140257
				],
				[
					68.59484777517564,
					1.2877959927140257
				],
				[
					68.59484777517564,
					2.5755919854280513
				],
				[
					70.72365339578452,
					2.5755919854280513
				],
				[
					70.72365339578452,
					3.863387978142077
				],
				[
					72.85245901639344,
					3.863387978142077
				],
				[
					74.98126463700234,
					3.863387978142077
				],
				[
					77.11007025761124,
					3.863387978142077
				],
				[
					81.36768149882904,
					5.151183970856103
				],
				[
					83.49648711943793,
					5.151183970856103
				],
				[
					81.36768149882904,
					5.151183970856103
				],
				[
					77.11007025761124,
					5.151183970856103
				],
				[
					77.11007025761124,
					3.863387978142077
				],
				[
					62.20843091334895,
					3.863387978142077
				],
				[
					60.07962529274003,
					3.863387978142077
				],
				[
					53.69320843091335,
					3.863387978142077
				],
				[
					49.435597189695535,
					3.863387978142077
				],
				[
					45.17798594847774,
					3.863387978142077
				],
				[
					43.04918032786885,
					3.863387978142077
				],
				[
					40.92037470725995,
					3.863387978142077
				],
				[
					38.791569086651045,
					3.863387978142077
				],
				[
					34.53395784543325,
					3.863387978142077
				],
				[
					26.018735362997653,
					3.863387978142077
				],
				[
					23.88992974238876,
					3.863387978142077
				],
				[
					17.50351288056206,
					3.863387978142077
				],
				[
					15.37470725995316,
					3.863387978142077
				],
				[
					11.117096018735362,
					3.863387978142077
				],
				[
					8.988290398126463,
					3.863387978142077
				],
				[
					4.730679156908665,
					3.863387978142077
				],
				[
					2.6018735362997654,
					3.863387978142077
				],
				[
					0.4730679156908663,
					3.863387978142077
				],
				[
					2.6018735362997654,
					2.5755919854280513
				],
				[
					11.117096018735362,
					1.2877959927140257
				],
				[
					13.24590163934426,
					1.2877959927140257
				],
				[
					23.88992974238876,
					0
				],
				[
					26.018735362997653,
					0
				],
				[
					30.276346604215455,
					0
				],
				[
					32.40515222482435,
					0
				],
				[
					34.53395784543325,
					0
				],
				[
					36.66276346604216,
					0
				],
				[
					38.791569086651045,
					0
				],
				[
					40.92037470725995,
					0
				],
				[
					45.17798594847774,
					0
				],
				[
					47.30679156908665,
					0
				],
				[
					49.435597189695535,
					0
				],
				[
					51.564402810304436,
					0
				],
				[
					53.69320843091335,
					0
				],
				[
					55.82201405152224,
					0
				],
				[
					57.95081967213114,
					0
				],
				[
					60.07962529274003,
					0
				],
				[
					64.33723653395785,
					0
				],
				[
					66.46604215456674,
					0
				],
				[
					70.72365339578452,
					0
				],
				[
					72.85245901639344,
					0
				],
				[
					74.98126463700234,
					1.2877959927140257
				],
				[
					77.11007025761124,
					1.2877959927140257
				],
				[
					79.23887587822014,
					1.2877959927140257
				],
				[
					81.36768149882904,
					2.5755919854280513
				],
				[
					83.49648711943793,
					2.5755919854280513
				],
				[
					83.49648711943793,
					3.863387978142077
				],
				[
					81.36768149882904,
					3.863387978142077
				],
				[
					79.23887587822014,
					3.863387978142077
				],
				[
					77.11007025761124,
					3.863387978142077
				],
				[
					74.98126463700234,
					3.863387978142077
				],
				[
					70.72365339578452,
					2.5755919854280513
				],
				[
					68.59484777517564,
					2.5755919854280513
				],
				[
					62.20843091334895,
					2.5755919854280513
				],
				[
					60.07962529274003,
					2.5755919854280513
				],
				[
					57.95081967213114,
					2.5755919854280513
				],
				[
					55.82201405152224,
					2.5755919854280513
				],
				[
					51.564402810304436,
					1.2877959927140257
				],
				[
					45.17798594847774,
					1.2877959927140257
				],
				[
					40.92037470725995,
					1.2877959927140257
				],
				[
					38.791569086651045,
					1.2877959927140257
				],
				[
					36.66276346604216,
					1.2877959927140257
				],
				[
					34.53395784543325,
					1.2877959927140257
				],
				[
					30.276346604215455,
					1.2877959927140257
				],
				[
					26.018735362997653,
					1.2877959927140257
				],
				[
					19.632318501170957,
					1.2877959927140257
				],
				[
					17.50351288056206,
					1.2877959927140257
				],
				[
					13.24590163934426,
					1.2877959927140257
				],
				[
					11.117096018735362,
					1.2877959927140257
				],
				[
					8.988290398126463,
					1.2877959927140257
				],
				[
					6.859484777517564,
					1.2877959927140257
				],
				[
					0.4730679156908663,
					2.5755919854280513
				],
				[
					0.4730679156908663,
					3.863387978142077
				],
				[
					2.6018735362997654,
					3.863387978142077
				],
				[
					8.988290398126463,
					3.863387978142077
				],
				[
					11.117096018735362,
					3.863387978142077
				],
				[
					13.24590163934426,
					3.863387978142077
				],
				[
					15.37470725995316,
					3.863387978142077
				],
				[
					19.632318501170957,
					3.863387978142077
				],
				[
					21.761124121779858,
					3.863387978142077
				],
				[
					28.147540983606557,
					3.863387978142077
				],
				[
					34.53395784543325,
					3.863387978142077
				],
				[
					36.66276346604216,
					3.863387978142077
				],
				[
					43.04918032786885,
					3.863387978142077
				],
				[
					45.17798594847774,
					3.863387978142077
				],
				[
					47.30679156908665,
					3.863387978142077
				],
				[
					49.435597189695535,
					3.863387978142077
				],
				[
					51.564402810304436,
					3.863387978142077
				],
				[
					53.69320843091335,
					3.863387978142077
				],
				[
					55.82201405152224,
					5.151183970856103
				],
				[
					57.95081967213114,
					5.151183970856103
				],
				[
					60.07962529274003,
					5.151183970856103
				],
				[
					62.20843091334895,
					5.151183970856103
				],
				[
					64.33723653395785,
					5.151183970856103
				],
				[
					66.46604215456674,
					5.151183970856103
				],
				[
					68.59484777517564,
					5.151183970856103
				],
				[
					68.59484777517564,
					6.4389799635701275
				],
				[
					70.72365339578452,
					6.4389799635701275
				],
				[
					68.59484777517564,
					6.4389799635701275
				],
				[
					66.46604215456674,
					6.4389799635701275
				],
				[
					64.33723653395785,
					6.4389799635701275
				],
				[
					60.07962529274003,
					6.4389799635701275
				],
				[
					55.82201405152224,
					6.4389799635701275
				],
				[
					53.69320843091335,
					6.4389799635701275
				],
				[
					51.564402810304436,
					6.4389799635701275
				],
				[
					49.435597189695535,
					6.4389799635701275
				],
				[
					47.30679156908665,
					6.4389799635701275
				],
				[
					45.17798594847774,
					6.4389799635701275
				],
				[
					43.04918032786885,
					6.4389799635701275
				],
				[
					40.92037470725995,
					6.4389799635701275
				],
				[
					38.791569086651045,
					6.4389799635701275
				],
				[
					36.66276346604216,
					6.4389799635701275
				],
				[
					34.53395784543325,
					6.4389799635701275
				],
				[
					32.40515222482435,
					6.4389799635701275
				],
				[
					30.276346604215455,
					6.4389799635701275
				],
				[
					28.147540983606557,
					6.4389799635701275
				],
				[
					26.018735362997653,
					6.4389799635701275
				],
				[
					23.88992974238876,
					6.4389799635701275
				],
				[
					21.761124121779858,
					7.726775956284154
				],
				[
					19.632318501170957,
					7.726775956284154
				],
				[
					15.37470725995316,
					7.726775956284154
				],
				[
					13.24590163934426,
					7.726775956284154
				],
				[
					11.117096018735362,
					7.726775956284154
				],
				[
					8.988290398126463,
					7.726775956284154
				],
				[
					6.859484777517564,
					7.726775956284154
				],
				[
					4.730679156908665,
					7.726775956284154
				],
				[
					2.6018735362997654,
					7.726775956284154
				],
				[
					0.4730679156908663,
					7.726775956284154
				],
				[
					-1.6557377049180328,
					6.4389799635701275
				],
				[
					-1.6557377049180328,
					5.151183970856103
				],
				[
					-1.6557377049180328,
					3.863387978142077
				],
				[
					0.4730679156908663,
					3.863387978142077
				],
				[
					2.6018735362997654,
					2.5755919854280513
				],
				[
					4.730679156908665,
					2.5755919854280513
				],
				[
					6.859484777517564,
					1.2877959927140257
				],
				[
					8.988290398126463,
					1.2877959927140257
				],
				[
					11.117096018735362,
					1.2877959927140257
				],
				[
					13.24590163934426,
					1.2877959927140257
				],
				[
					17.50351288056206,
					1.2877959927140257
				],
				[
					19.632318501170957,
					1.2877959927140257
				],
				[
					23.88992974238876,
					1.2877959927140257
				],
				[
					26.018735362997653,
					1.2877959927140257
				],
				[
					28.147540983606557,
					1.2877959927140257
				],
				[
					32.40515222482435,
					1.2877959927140257
				],
				[
					34.53395784543325,
					1.2877959927140257
				],
				[
					36.66276346604216,
					1.2877959927140257
				],
				[
					40.92037470725995,
					1.2877959927140257
				],
				[
					43.04918032786885,
					1.2877959927140257
				],
				[
					45.17798594847774,
					1.2877959927140257
				],
				[
					47.30679156908665,
					1.2877959927140257
				],
				[
					49.435597189695535,
					1.2877959927140257
				],
				[
					51.564402810304436,
					1.2877959927140257
				],
				[
					53.69320843091335,
					1.2877959927140257
				],
				[
					55.82201405152224,
					1.2877959927140257
				],
				[
					57.95081967213114,
					1.2877959927140257
				],
				[
					60.07962529274003,
					1.2877959927140257
				],
				[
					62.20843091334895,
					1.2877959927140257
				],
				[
					66.46604215456674,
					1.2877959927140257
				],
				[
					68.59484777517564,
					1.2877959927140257
				],
				[
					70.72365339578452,
					1.2877959927140257
				],
				[
					70.72365339578452,
					2.5755919854280513
				],
				[
					77.11007025761124,
					2.5755919854280513
				],
				[
					81.36768149882904,
					3.863387978142077
				],
				[
					85.62529274004685,
					3.863387978142077
				],
				[
					87.75409836065575,
					3.863387978142077
				],
				[
					87.75409836065575,
					5.151183970856103
				],
				[
					87.75409836065575,
					6.4389799635701275
				],
				[
					85.62529274004685,
					6.4389799635701275
				],
				[
					81.36768149882904,
					6.4389799635701275
				],
				[
					74.98126463700234,
					6.4389799635701275
				],
				[
					70.72365339578452,
					6.4389799635701275
				],
				[
					68.59484777517564,
					6.4389799635701275
				],
				[
					66.46604215456674,
					6.4389799635701275
				],
				[
					64.33723653395785,
					6.4389799635701275
				],
				[
					53.69320843091335,
					7.726775956284154
				],
				[
					51.564402810304436,
					7.726775956284154
				],
				[
					47.30679156908665,
					7.726775956284154
				],
				[
					43.04918032786885,
					7.726775956284154
				],
				[
					40.92037470725995,
					7.726775956284154
				],
				[
					38.791569086651045,
					9.014571948998181
				],
				[
					36.66276346604216,
					9.014571948998181
				],
				[
					34.53395784543325,
					9.014571948998181
				],
				[
					32.40515222482435,
					9.014571948998181
				],
				[
					30.276346604215455,
					9.014571948998181
				],
				[
					28.147540983606557,
					9.014571948998181
				],
				[
					26.018735362997653,
					9.014571948998181
				],
				[
					23.88992974238876,
					9.014571948998181
				],
				[
					21.761124121779858,
					9.014571948998181
				],
				[
					19.632318501170957,
					9.014571948998181
				],
				[
					17.50351288056206,
					9.014571948998181
				],
				[
					15.37470725995316,
					9.014571948998181
				],
				[
					13.24590163934426,
					9.014571948998181
				],
				[
					11.117096018735362,
					9.014571948998181
				],
				[
					8.988290398126463,
					9.014571948998181
				],
				[
					6.859484777517564,
					9.014571948998181
				],
				[
					8.988290398126463,
					9.014571948998181
				],
				[
					11.117096018735362,
					9.014571948998181
				],
				[
					13.24590163934426,
					9.014571948998181
				],
				[
					17.50351288056206,
					10.302367941712205
				],
				[
					21.761124121779858,
					10.302367941712205
				],
				[
					23.88992974238876,
					11.59016393442623
				],
				[
					26.018735362997653,
					11.59016393442623
				],
				[
					28.147540983606557,
					11.59016393442623
				],
				[
					30.276346604215455,
					11.59016393442623
				],
				[
					32.40515222482435,
					11.59016393442623
				],
				[
					34.53395784543325,
					11.59016393442623
				],
				[
					36.66276346604216,
					11.59016393442623
				],
				[
					43.04918032786885,
					11.59016393442623
				],
				[
					49.435597189695535,
					11.59016393442623
				],
				[
					51.564402810304436,
					11.59016393442623
				],
				[
					53.69320843091335,
					11.59016393442623
				],
				[
					55.82201405152224,
					11.59016393442623
				],
				[
					57.95081967213114,
					11.59016393442623
				],
				[
					60.07962529274003,
					11.59016393442623
				],
				[
					62.20843091334895,
					11.59016393442623
				],
				[
					64.33723653395785,
					11.59016393442623
				],
				[
					66.46604215456674,
					10.302367941712205
				],
				[
					68.59484777517564,
					10.302367941712205
				],
				[
					70.72365339578452,
					10.302367941712205
				],
				[
					72.85245901639344,
					10.302367941712205
				],
				[
					72.85245901639344,
					9.014571948998181
				],
				[
					72.85245901639344,
					7.726775956284154
				],
				[
					74.98126463700234,
					7.726775956284154
				],
				[
					77.11007025761124,
					7.726775956284154
				],
				[
					79.23887587822014,
					7.726775956284154
				],
				[
					81.36768149882904,
					6.4389799635701275
				],
				[
					81.36768149882904,
					5.151183970856103
				],
				[
					83.49648711943793,
					5.151183970856103
				],
				[
					83.49648711943793,
					3.863387978142077
				],
				[
					83.49648711943793,
					2.5755919854280513
				],
				[
					83.49648711943793,
					2.5755919854280513
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 693,
			"versionNonce": 1756824782,
			"isDeleted": false,
			"id": "12su5HuU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2938.0104196880634,
			"y": 3912.6955412006014,
			"strokeColor": "#000000",
			"backgroundColor": "#32bedd",
			"width": 145.1798858642578,
			"height": 25,
			"seed": 1176705245,
			"groupIds": [
				"I6Da4SFh8KAZvj42WjnvD",
				"5Jfqn2_sk5xZBzKiXslJb"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "MetaDB(mysql)",
			"rawText": "MetaDB(mysql)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "MetaDB(mysql)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 507,
			"versionNonce": 1707276050,
			"isDeleted": false,
			"id": "tFUj1EqN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2892.0871556201037,
			"y": 3795.4477733434587,
			"strokeColor": "#e8e8e8",
			"backgroundColor": "#32bedd",
			"width": 44.45997619628906,
			"height": 45,
			"seed": 1943875443,
			"groupIds": [
				"5Jfqn2_sk5xZBzKiXslJb"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "My",
			"rawText": "My",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "My",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 251,
			"versionNonce": 89733902,
			"isDeleted": false,
			"id": "If8qppLA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3064.3886687202203,
			"y": 3326.700144995244,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 56.25,
			"height": 19.2,
			"seed": 1269777562,
			"groupIds": [
				"MR9CShs39l3IL_-IysxFZ"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "insert",
			"rawText": "insert",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "insert",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "rectangle",
			"version": 266,
			"versionNonce": 70665426,
			"isDeleted": false,
			"id": "hKI1YsYHHPemyH1tySF1G",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3081.2011687202203,
			"y": 3321.289988745244,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 86.0625,
			"height": 36.0390625,
			"seed": 991365914,
			"groupIds": [
				"MR9CShs39l3IL_-IysxFZ"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 280,
			"versionNonce": 886745422,
			"isDeleted": false,
			"id": "bCJGWCxf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2868.4531218452203,
			"y": 3328.141551245244,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 56.25,
			"height": 19.2,
			"seed": 1604528026,
			"groupIds": [
				"FnPDjzpmLZYf8k9gvmwXj"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "delete",
			"rawText": "delete",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "delete",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "rectangle",
			"version": 336,
			"versionNonce": 444193426,
			"isDeleted": false,
			"id": "Cnuw_J-22rW_pHPeD2CbE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2883.9531218452203,
			"y": 3321.289988745244,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 86.0625,
			"height": 36.0390625,
			"seed": 991365914,
			"groupIds": [
				"FnPDjzpmLZYf8k9gvmwXj"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 280,
			"versionNonce": 1184124814,
			"isDeleted": false,
			"id": "UTz6eu9v",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2629.8769499702203,
			"y": 3328.586863745244,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 46.875,
			"height": 19.2,
			"seed": 621644442,
			"groupIds": [
				"Zj4DxQWyaKklxn44m7wZU"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "query",
			"rawText": "query",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "query",
			"lineHeight": 1.2,
			"baseline": 15
		},
		{
			"type": "rectangle",
			"version": 333,
			"versionNonce": 1464121426,
			"isDeleted": false,
			"id": "H0Cra6fwul35nrqnq4sDW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2652.1425749702203,
			"y": 3321.289988745244,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 86.0625,
			"height": 36.0390625,
			"seed": 991365914,
			"groupIds": [
				"Zj4DxQWyaKklxn44m7wZU"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 283,
			"versionNonce": 918498766,
			"isDeleted": false,
			"id": "vs1NxaRN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3269.3964812202203,
			"y": 3283.619480932744,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 117.1875,
			"height": 24,
			"seed": 911207302,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "399NTCuqXqT-1uclOOkNh",
					"type": "arrow"
				}
			],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "MetaDbUtil",
			"rawText": "MetaDbUtil",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "MetaDbUtil",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "rectangle",
			"version": 506,
			"versionNonce": 2054020626,
			"isDeleted": false,
			"id": "jXsvvDdLoTPQewN_CJxXh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3308.5136687202203,
			"y": 3244.331980932744,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 865.03125,
			"height": 279.71289062500017,
			"seed": 303925638,
			"groupIds": [],
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "cHa54DbBtjCVZzbzp9HB1",
					"type": "arrow"
				},
				{
					"id": "AnIG1NWCnh6W1WbhyO_cV",
					"type": "arrow"
				},
				{
					"id": "lPHJqOlbu1yUfEawJ47b8",
					"type": "arrow"
				}
			],
			"updated": 1684308939725,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 544,
			"versionNonce": 309609486,
			"isDeleted": false,
			"id": "sa4Yh1HV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2556.9570280952203,
			"y": 2836.624949682744,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 152.34375,
			"height": 24,
			"seed": 906944774,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "S9qdXQ_j_MSTsc9UG7Uun",
					"type": "arrow"
				}
			],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "FilesAccessor",
			"rawText": "FilesAccessor",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "FilesAccessor",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 525,
			"versionNonce": 820792274,
			"isDeleted": false,
			"id": "B6QnXLRy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2355.0820280952203,
			"y": 2834.695262182744,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 269.53125,
			"height": 24,
			"seed": 1993240966,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "399NTCuqXqT-1uclOOkNh",
					"type": "arrow"
				},
				{
					"id": "Gsq-KZ6KBxAz8GtgA5ZGt",
					"type": "arrow"
				}
			],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "SketchTreeRootsAccessor",
			"rawText": "SketchTreeRootsAccessor",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SketchTreeRootsAccessor",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 515,
			"versionNonce": 1538036302,
			"isDeleted": false,
			"id": "uwj22qPw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2038.7460905952203,
			"y": 2842.179637182744,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 246.09375,
			"height": 24,
			"seed": 2120882118,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "cHa54DbBtjCVZzbzp9HB1",
					"type": "arrow"
				},
				{
					"id": "qdygPuc82YneczyPpCYZP",
					"type": "arrow"
				}
			],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "ReadWriteLockAccessor",
			"rawText": "ReadWriteLockAccessor",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ReadWriteLockAccessor",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 1106,
			"versionNonce": 1893138834,
			"isDeleted": false,
			"id": "6KuxdGNMgAjg3_PAHVQps",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2484.8841725878833,
			"y": 2878.1009079301734,
			"strokeColor": "#087f5b",
			"backgroundColor": "transparent",
			"width": 95.83261123360887,
			"height": 334.23107300257016,
			"seed": 446607130,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939725,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					-95.83261123360887,
					334.23107300257016
				]
			]
		},
		{
			"type": "arrow",
			"version": 1009,
			"versionNonce": 1832982670,
			"isDeleted": false,
			"id": "cHa54DbBtjCVZzbzp9HB1",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1929.3435368079035,
			"y": 2878.802051790258,
			"strokeColor": "#d9480f",
			"backgroundColor": "transparent",
			"width": 579.1516696753802,
			"height": 334.08936245119094,
			"seed": 1606420166,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "uwj22qPw",
				"focus": -0.201872626016023,
				"gap": 12.622414607513747
			},
			"endBinding": {
				"elementId": "jXsvvDdLoTPQewN_CJxXh",
				"focus": 0.10453284045192274,
				"gap": 31.440566691295317
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
					-579.1516696753802,
					334.08936245119094
				]
			]
		},
		{
			"type": "text",
			"version": 325,
			"versionNonce": 1432682322,
			"isDeleted": false,
			"id": "cjM9nzvR",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1954.6074187202203,
			"y": 2713.615672338994,
			"strokeColor": "#1864ab",
			"backgroundColor": "transparent",
			"width": 187.5,
			"height": 24,
			"seed": 82960902,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "AbstractAccessor",
			"rawText": "AbstractAccessor",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AbstractAccessor",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "rectangle",
			"version": 576,
			"versionNonce": 1592448718,
			"isDeleted": false,
			"id": "KcQzz8DATBolEhdhi9XzZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2665.7539030952203,
			"y": 2671.664500463994,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 932.3984375,
			"height": 268.1484375,
			"seed": 280179846,
			"groupIds": [],
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "cHa54DbBtjCVZzbzp9HB1",
					"type": "arrow"
				}
			],
			"updated": 1684308939726,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 402,
			"versionNonce": 2062370066,
			"isDeleted": false,
			"id": "4UYAcb04",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3852.8007780952203,
			"y": 2825.641062963994,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 117.1875,
			"height": 24,
			"seed": 1206049478,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "S9qdXQ_j_MSTsc9UG7Uun",
					"type": "arrow"
				}
			],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "FileRecord",
			"rawText": "FileRecord",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "FileRecord",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 363,
			"versionNonce": 1765985550,
			"isDeleted": false,
			"id": "gh5yxShB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3349.4492155952203,
			"y": 2833.531687963994,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 222.65625,
			"height": 24,
			"seed": 830650842,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "EoVh22J0U2sdY7eI42_aV",
					"type": "arrow"
				},
				{
					"id": "qdygPuc82YneczyPpCYZP",
					"type": "arrow"
				}
			],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "ReadWriteLockRecord",
			"rawText": "ReadWriteLockRecord",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ReadWriteLockRecord",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 1116,
			"versionNonce": 1525076690,
			"isDeleted": false,
			"id": "399NTCuqXqT-1uclOOkNh",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2236.586055298318,
			"y": 2873.6441063349052,
			"strokeColor": "#5f3dc4",
			"backgroundColor": "transparent",
			"width": 312.96355493243556,
			"height": 338.6878745978388,
			"seed": 1606420166,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "B6QnXLRy",
				"focus": -0.05918478985026854,
				"gap": 14.9488441521612
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
					-312.96355493243556,
					338.6878745978388
				]
			]
		},
		{
			"type": "text",
			"version": 382,
			"versionNonce": 1237449550,
			"isDeleted": false,
			"id": "6HeNmDy6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3638.7773405952203,
			"y": 2826.750437963994,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 187.5,
			"height": 24,
			"seed": 388887174,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "jNc2jP32iqjGK7vQTn11I",
					"type": "arrow"
				},
				{
					"id": "Gsq-KZ6KBxAz8GtgA5ZGt",
					"type": "arrow"
				}
			],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "SketchRootRecord",
			"rawText": "SketchRootRecord",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SketchRootRecord",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 520,
			"versionNonce": 669558930,
			"isDeleted": false,
			"id": "AnIG1NWCnh6W1WbhyO_cV",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -3781.0585905952203,
			"y": 2873.641551245244,
			"strokeColor": "#087f5b",
			"backgroundColor": "transparent",
			"width": 650.1032407931816,
			"height": 339.1408716738888,
			"seed": 1682812166,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "jXsvvDdLoTPQewN_CJxXh",
				"focus": 0.10507005545232082,
				"gap": 31.549558013611204
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
					650.1032407931816,
					339.1408716738888
				]
			]
		},
		{
			"type": "arrow",
			"version": 785,
			"versionNonce": 650207630,
			"isDeleted": false,
			"id": "jNc2jP32iqjGK7vQTn11I",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -3543.8083611107986,
			"y": 2855.0559762840135,
			"strokeColor": "#5f3dc4",
			"backgroundColor": "transparent",
			"width": 454.3389807373776,
			"height": 357.2760046487306,
			"seed": 157162566,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6HeNmDy6",
				"focus": 0.17903264608645628,
				"gap": 4.305538320019423
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
					454.3389807373776,
					357.2760046487306
				]
			]
		},
		{
			"type": "arrow",
			"version": 781,
			"versionNonce": 698992210,
			"isDeleted": false,
			"id": "EoVh22J0U2sdY7eI42_aV",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -3236.9970672973645,
			"y": 2864.532284435826,
			"strokeColor": "#d9480f",
			"backgroundColor": "transparent",
			"width": 171.24723617552092,
			"height": 347.79969649691793,
			"seed": 1763615622,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "gh5yxShB",
				"focus": 0.07021152313618972,
				"gap": 7.000596471832068
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
					171.24723617552092,
					347.79969649691793
				]
			]
		},
		{
			"type": "text",
			"version": 191,
			"versionNonce": 1937375182,
			"isDeleted": false,
			"id": "XOBAUZaq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3954.7792937202203,
			"y": 2709.918894995244,
			"strokeColor": "#364fc7",
			"backgroundColor": "transparent",
			"width": 105.46875,
			"height": 24,
			"seed": 1999674906,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "DataModel",
			"rawText": "DataModel",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "DataModel",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "rectangle",
			"version": 226,
			"versionNonce": 419507218,
			"isDeleted": false,
			"id": "Zggt21hbuL_2U-RYzuLxy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3997.6328093452203,
			"y": 2677.508738745244,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 992.90625,
			"height": 289.7421875,
			"seed": 855891162,
			"groupIds": [],
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 598,
			"versionNonce": 1409603086,
			"isDeleted": false,
			"id": "S9qdXQ_j_MSTsc9UG7Uun",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2489.1523405952203,
			"y": 2826.407176245244,
			"strokeColor": "#087f5b",
			"backgroundColor": "transparent",
			"width": 1303.625,
			"height": 133.029296875,
			"seed": 1995476058,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "sa4Yh1HV",
				"focus": 0.8304957113078998,
				"gap": 10.2177734375
			},
			"endBinding": {
				"elementId": "4UYAcb04",
				"focus": -1.066903974009115,
				"gap": 15.05419921875
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
					-777.7265625,
					-133.029296875
				],
				[
					-1303.625,
					-15.8203125
				]
			]
		},
		{
			"type": "arrow",
			"version": 437,
			"versionNonce": 2078661074,
			"isDeleted": false,
			"id": "Gsq-KZ6KBxAz8GtgA5ZGt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2225.1191374702203,
			"y": 2826.235301245244,
			"strokeColor": "#5f3dc4",
			"backgroundColor": "transparent",
			"width": 1324.3046875,
			"height": 138.744140625,
			"seed": 438909274,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "B6QnXLRy",
				"focus": 0.4829700394429531,
				"gap": 8.4599609375
			},
			"endBinding": {
				"elementId": "6HeNmDy6",
				"focus": -0.6568289909644249,
				"gap": 7.26513671875
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
					-661.2578125,
					-138.744140625
				],
				[
					-1324.3046875,
					-6.75
				]
			]
		},
		{
			"type": "arrow",
			"version": 385,
			"versionNonce": 22733902,
			"isDeleted": false,
			"id": "qdygPuc82YneczyPpCYZP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1911.1015593452212,
			"y": 2826.932566870244,
			"strokeColor": "#d9480f",
			"backgroundColor": "transparent",
			"width": 1341.689453125,
			"height": 140.869140625,
			"seed": 537496090,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "uwj22qPw",
				"focus": 0.6937799522147475,
				"gap": 15.2470703125
			},
			"endBinding": {
				"elementId": "gh5yxShB",
				"focus": -0.7276874984347357,
				"gap": 9.12841796875
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
					-601.318359375,
					-140.869140625
				],
				[
					-1341.689453125,
					-2.529296875
				]
			]
		},
		{
			"type": "arrow",
			"version": 349,
			"versionNonce": 24039314,
			"isDeleted": false,
			"id": "lPHJqOlbu1yUfEawJ47b8",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2865.8533145916085,
			"y": 3533.1258041749315,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.947265625,
			"height": 137.548828125,
			"seed": 821576518,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jXsvvDdLoTPQewN_CJxXh",
				"focus": -0.025769254225844904,
				"gap": 9.0809326171875
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-0.947265625,
					137.548828125
				]
			]
		},
		{
			"type": "text",
			"version": 141,
			"versionNonce": 760556174,
			"isDeleted": false,
			"id": "Uw4oxKrd",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2923.835934345221,
			"y": 3435.0398666749315,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 117.1875,
			"height": 24,
			"seed": 1089931610,
			"groupIds": [
				"MNIql34rWQJ9j8QxFiMZV"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "Connection",
			"rawText": "Connection",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Connection",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "rectangle",
			"version": 191,
			"versionNonce": 1574112594,
			"isDeleted": false,
			"id": "v2EhfK3k_FvlIXjg0DeSa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2930.789059345221,
			"y": 3429.8836166749315,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 133.61328125,
			"height": 39.482421875,
			"seed": 294199642,
			"groupIds": [
				"MNIql34rWQJ9j8QxFiMZV"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 37,
			"versionNonce": 1722591438,
			"isDeleted": false,
			"id": "Py9lkDew",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -155.20544541663912,
			"y": -1179.967561430949,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 90.251953125,
			"height": 45,
			"seed": 1809007302,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Write",
			"rawText": "Write",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Write",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 82,
			"versionNonce": 644453138,
			"isDeleted": false,
			"id": "tmpgauCe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3062.8414295833613,
			"y": -1807.3597489309495,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 88.59596252441406,
			"height": 45,
			"seed": 647100102,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Read",
			"rawText": "Read",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Read",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 2096783118,
			"isDeleted": false,
			"id": "3KoUDuhZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3059.3258045833613,
			"y": -1638.635790597616,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 480.46875,
			"height": 312,
			"seed": 1449428634,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "xsOJ5jNQ2ZAo7zLZ0Jd6N",
					"type": "arrow"
				}
			],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "handle:65, FrontendCommandHandler \nquery:462, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:144, ServerQueryHandler \nhandle:80, SelectHandler \nexecute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:881, ServerConnection \nexecute:66, TPreparedStatement \nexecuteInternal:149, TStatement \nexecuteSQL:81, TPreparedStatement \nexecuteSQL:311, TConnection \nexecuteQuery:487, TConnection ",
			"rawText": "handle:65, FrontendCommandHandler \nquery:462, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:144, ServerQueryHandler \nhandle:80, SelectHandler \nexecute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:881, ServerConnection \nexecute:66, TPreparedStatement \nexecuteInternal:149, TStatement \nexecuteSQL:81, TPreparedStatement \nexecuteSQL:311, TConnection \nexecuteQuery:487, TConnection ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "handle:65, FrontendCommandHandler \nquery:462, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:144, ServerQueryHandler \nhandle:80, SelectHandler \nexecute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:881, ServerConnection \nexecute:66, TPreparedStatement \nexecuteInternal:149, TStatement \nexecuteSQL:81, TPreparedStatement \nexecuteSQL:311, TConnection \nexecuteQuery:487, TConnection ",
			"lineHeight": 1.2,
			"baseline": 308
		},
		{
			"type": "text",
			"version": 104,
			"versionNonce": 766075090,
			"isDeleted": false,
			"id": "p6r9fDJ6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3050.7841379166944,
			"y": -1124.6774572642828,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 574.21875,
			"height": 312,
			"seed": 2120946906,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "wKzisNbO3SnBgcEzCHqQR",
					"type": "arrow"
				}
			],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "execute:59, PlanExecutor \nexecByExecPlanNodeByOne:109, PlanExecutor \nexecute:79, ExecutorHelper \nexecuteCluster:116, ExecutorHelper \nexecute:56, MppRunner \ncreateQuery:54, LocalStatementClient \ncreateQuery:144, StatementResource \ninit:274, StatementResource$Query \ncreateClusterQuery:413, SqlQueryManager \nstart:129, SqlQueryExecution \nbuildRootFragment:82, PlanFragmenter \nbuildRootFragment:141, PlanFragmenter$Fragmenter \ngenerateSubPlan:381, PlanFragmenter$Fragmenter",
			"rawText": "execute:59, PlanExecutor \nexecByExecPlanNodeByOne:109, PlanExecutor \nexecute:79, ExecutorHelper \nexecuteCluster:116, ExecutorHelper \nexecute:56, MppRunner \ncreateQuery:54, LocalStatementClient \ncreateQuery:144, StatementResource \ninit:274, StatementResource$Query \ncreateClusterQuery:413, SqlQueryManager \nstart:129, SqlQueryExecution \nbuildRootFragment:82, PlanFragmenter \nbuildRootFragment:141, PlanFragmenter$Fragmenter \ngenerateSubPlan:381, PlanFragmenter$Fragmenter",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "execute:59, PlanExecutor \nexecByExecPlanNodeByOne:109, PlanExecutor \nexecute:79, ExecutorHelper \nexecuteCluster:116, ExecutorHelper \nexecute:56, MppRunner \ncreateQuery:54, LocalStatementClient \ncreateQuery:144, StatementResource \ninit:274, StatementResource$Query \ncreateClusterQuery:413, SqlQueryManager \nstart:129, SqlQueryExecution \nbuildRootFragment:82, PlanFragmenter \nbuildRootFragment:141, PlanFragmenter$Fragmenter \ngenerateSubPlan:381, PlanFragmenter$Fragmenter",
			"lineHeight": 1.2,
			"baseline": 308
		},
		{
			"type": "text",
			"version": 167,
			"versionNonce": 1689734478,
			"isDeleted": false,
			"id": "sVcDTIaa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3915.7711170833613,
			"y": -1021.4352697642828,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 433.59375,
			"height": 120,
			"seed": 185971334,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "wKzisNbO3SnBgcEzCHqQR",
					"type": "arrow"
				},
				{
					"id": "epOVq43A6lgJiAYU14aXR",
					"type": "arrow"
				}
			],
			"updated": 1684308939726,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "getSplits:163, SplitManager \ntableFileScanSplit:310, SplitManager \nbuild:38, SplitInfoBuilder \nbuildORCSplits:68, SplitInfoBuilder \ngetSplits:112, ORCSplit",
			"rawText": "getSplits:163, SplitManager \ntableFileScanSplit:310, SplitManager \nbuild:38, SplitInfoBuilder \nbuildORCSplits:68, SplitInfoBuilder \ngetSplits:112, ORCSplit",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "getSplits:163, SplitManager \ntableFileScanSplit:310, SplitManager \nbuild:38, SplitInfoBuilder \nbuildORCSplits:68, SplitInfoBuilder \ngetSplits:112, ORCSplit",
			"lineHeight": 1.2,
			"baseline": 116
		},
		{
			"type": "arrow",
			"version": 175,
			"versionNonce": 1596552850,
			"isDeleted": false,
			"id": "xsOJ5jNQ2ZAo7zLZ0Jd6N",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3263.5445545833613,
			"y": -1310.496955962199,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.315104166666515,
			"height": 152.5,
			"seed": 1269361286,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939727,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "3KoUDuhZ",
				"focus": 0.15522866036711752,
				"gap": 16.13883463541697
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
					1.315104166666515,
					152.5
				]
			]
		},
		{
			"type": "arrow",
			"version": 252,
			"versionNonce": 456946574,
			"isDeleted": false,
			"id": "wKzisNbO3SnBgcEzCHqQR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3625.8492420833613,
			"y": -969.2339351288658,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 277.1744791666665,
			"height": 5.1953125,
			"seed": 879724570,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939727,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "p6r9fDJ6",
				"focus": -0.03689314575091744,
				"gap": 1
			},
			"endBinding": {
				"elementId": "sVcDTIaa",
				"focus": -0.026523435771665355,
				"gap": 12.747395833333258
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
					277.1744791666665,
					5.1953125
				]
			]
		},
		{
			"type": "arrow",
			"version": 191,
			"versionNonce": 463524946,
			"isDeleted": false,
			"id": "epOVq43A6lgJiAYU14aXR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4364.794554583361,
			"y": -950.2625809621991,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 177.25260416666652,
			"height": 0.9635416666667425,
			"seed": 1833533658,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939727,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "sVcDTIaa",
				"focus": 0.20325877724270772,
				"gap": 15.429687500000227
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
					177.25260416666652,
					-0.9635416666667425
				]
			]
		},
		{
			"type": "text",
			"version": 244,
			"versionNonce": 180539854,
			"isDeleted": false,
			"id": "kFLRQOH3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5390.862262916695,
			"y": -1003.4136226288658,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 585.9375,
			"height": 96,
			"seed": 1598121498,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939727,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "queryByLogicalTableAndFileType:252, FilesAccessor \nquery:103, AbstractAccessor\nquery:144, AbstractAccessor\nquery:67, MetaDbUtil",
			"rawText": "queryByLogicalTableAndFileType:252, FilesAccessor \nquery:103, AbstractAccessor\nquery:144, AbstractAccessor\nquery:67, MetaDbUtil",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "queryByLogicalTableAndFileType:252, FilesAccessor \nquery:103, AbstractAccessor\nquery:144, AbstractAccessor\nquery:67, MetaDbUtil",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 120,
			"versionNonce": 350648850,
			"isDeleted": false,
			"id": "SKH7eYJMDKXU0ybHfmQCA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5140.836221250029,
			"y": -951.5646642955323,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 171.2890625,
			"height": 4.1927083333332575,
			"seed": 785286150,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939727,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					171.2890625,
					4.1927083333332575
				]
			]
		},
		{
			"type": "image",
			"version": 403,
			"versionNonce": 1852008462,
			"isDeleted": false,
			"id": "cE7US1mcmgLBiaXW1Lrny",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5630.804061360469,
			"y": -550.2243322642819,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 1069.7213855421685,
			"height": 616.5755208333333,
			"seed": 27587098,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "Dhuwuij66olqlythA_IbN",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c94aaf6fe202102cb055b33063a6ed206b0933c1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 90,
			"versionNonce": 703686610,
			"isDeleted": false,
			"id": "k3DUHPHQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4577.828408750028,
			"y": -994.5863114309491,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 457.03125,
			"height": 72,
			"seed": 380729862,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "TE45sewQ34sFuqvnEbQR1",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "getOrLoadFileMetaMap:92, TableMetaUtil \ninitFileMeta:84, TableMetaUtil \ngetTableFiles:70, TableMetaUtil ",
			"rawText": "getOrLoadFileMetaMap:92, TableMetaUtil \ninitFileMeta:84, TableMetaUtil \ngetTableFiles:70, TableMetaUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "getOrLoadFileMetaMap:92, TableMetaUtil \ninitFileMeta:84, TableMetaUtil \ngetTableFiles:70, TableMetaUtil ",
			"lineHeight": 1.2,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 135,
			"versionNonce": 907490894,
			"isDeleted": false,
			"id": "kb3i8jCu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4403.336221250029,
			"y": -477.3288244517828,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 890.625,
			"height": 384,
			"seed": 671711706,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "TE45sewQ34sFuqvnEbQR1",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "    public static Map<String, FileMeta> getTableFiles(TableMeta tableMeta) {\n        try (Connection connection = MetaDbUtil.getConnection()) {\n            FilesAccessor filesAccessor = new FilesAccessor();\n            filesAccessor.setConnection(connection);\n            return filesAccessor.queryByLogicalTableAndFileType(\n                    tableMeta.getSchemaName(),\n                    tableMeta.getTableName(),\n                    ObjectFileType.TABLE_FILE.name()\n            ).stream().collect(Collectors.toUnmodifiableMap(\n                    FileRecord::getFileName,\n                    FileMeta::parseFrom\n            ));\n        } catch (SQLException e) {\n            throw GeneralUtil.nestedException(e);\n        }\n    }",
			"rawText": "    public static Map<String, FileMeta> getTableFiles(TableMeta tableMeta) {\n        try (Connection connection = MetaDbUtil.getConnection()) {\n            FilesAccessor filesAccessor = new FilesAccessor();\n            filesAccessor.setConnection(connection);\n            return filesAccessor.queryByLogicalTableAndFileType(\n                    tableMeta.getSchemaName(),\n                    tableMeta.getTableName(),\n                    ObjectFileType.TABLE_FILE.name()\n            ).stream().collect(Collectors.toUnmodifiableMap(\n                    FileRecord::getFileName,\n                    FileMeta::parseFrom\n            ));\n        } catch (SQLException e) {\n            throw GeneralUtil.nestedException(e);\n        }\n    }",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "    public static Map<String, FileMeta> getTableFiles(TableMeta tableMeta) {\n        try (Connection connection = MetaDbUtil.getConnection()) {\n            FilesAccessor filesAccessor = new FilesAccessor();\n            filesAccessor.setConnection(connection);\n            return filesAccessor.queryByLogicalTableAndFileType(\n                    tableMeta.getSchemaName(),\n                    tableMeta.getTableName(),\n                    ObjectFileType.TABLE_FILE.name()\n            ).stream().collect(Collectors.toUnmodifiableMap(\n                    FileRecord::getFileName,\n                    FileMeta::parseFrom\n            ));\n        } catch (SQLException e) {\n            throw GeneralUtil.nestedException(e);\n        }\n    }",
			"lineHeight": 1.2,
			"baseline": 380
		},
		{
			"type": "arrow",
			"version": 264,
			"versionNonce": 1121492370,
			"isDeleted": false,
			"id": "TE45sewQ34sFuqvnEbQR1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4781.278929583362,
			"y": -910.8314286184498,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.575520833333485,
			"height": 405.7421875,
			"seed": 328431046,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "k3DUHPHQ",
				"focus": 0.11043053224156381,
				"gap": 11.754882812499318
			},
			"endBinding": {
				"elementId": "kb3i8jCu",
				"focus": -0.14558851380550497,
				"gap": 27.76041666666697
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
					1.575520833333485,
					405.7421875
				]
			]
		},
		{
			"type": "rectangle",
			"version": 136,
			"versionNonce": 1790393486,
			"isDeleted": false,
			"id": "5wlcTZaBCEhFkPOJO1bOu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4459.534137916695,
			"y": -378.44861611844976,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 804.427083333333,
			"height": 186.86197916666674,
			"seed": 1447645510,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "Dhuwuij66olqlythA_IbN",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 251,
			"versionNonce": 752032594,
			"isDeleted": false,
			"id": "Dhuwuij66olqlythA_IbN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5283.414346250028,
			"y": -294.2949702851165,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 333.73697916666697,
			"height": 3.958333333333485,
			"seed": 1751752838,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "5wlcTZaBCEhFkPOJO1bOu",
				"focus": -0.14540082825916306,
				"gap": 19.453125000000455
			},
			"endBinding": {
				"elementId": "cE7US1mcmgLBiaXW1Lrny",
				"focus": 0.13315367216732382,
				"gap": 13.652735943774132
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
					333.73697916666697,
					3.958333333333485
				]
			]
		},
		{
			"type": "line",
			"version": 182,
			"versionNonce": 301759182,
			"isDeleted": false,
			"id": "DngoLbQPlFwC5E0euqa27",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4689.273721250028,
			"y": -430.531949451783,
			"strokeColor": "#5f3dc4",
			"backgroundColor": "transparent",
			"width": 464.20572916666697,
			"height": 3.0078125,
			"seed": 1956339930,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					464.20572916666697,
					3.0078125
				]
			]
		},
		{
			"type": "text",
			"version": 39,
			"versionNonce": 1983373586,
			"isDeleted": false,
			"id": "dbTNkdNV",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1279.2867420833618,
			"y": 161.16075888155137,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 667.96875,
			"height": 288,
			"seed": 443097734,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "waJ4s921rHfW56ShQ3lLt",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "executeTask:562, DdlEngineDagExecutor \nexecute:67, AbstractDdlTask \nbeforeTransaction:32, BaseSyncTask \nexecuteImpl:56, TableSyncTask \nforEach:1511, ArrayList \naccept:-1, TableSyncTask$$Lambda$1939/0x00000008018e55f0 \nlambda$executeImpl$0:61, TableSyncTask \nsync:31, ClusterSyncManagerHelper \nsync:59, ClusterSyncManager \ndoSync:74, ClusterSyncManager \nsync:28, TableMetaChangeSyncAction \nsync:44, TableMetaChangeSyncAction ",
			"rawText": "executeTask:562, DdlEngineDagExecutor \nexecute:67, AbstractDdlTask \nbeforeTransaction:32, BaseSyncTask \nexecuteImpl:56, TableSyncTask \nforEach:1511, ArrayList \naccept:-1, TableSyncTask$$Lambda$1939/0x00000008018e55f0 \nlambda$executeImpl$0:61, TableSyncTask \nsync:31, ClusterSyncManagerHelper \nsync:59, ClusterSyncManager \ndoSync:74, ClusterSyncManager \nsync:28, TableMetaChangeSyncAction \nsync:44, TableMetaChangeSyncAction ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "executeTask:562, DdlEngineDagExecutor \nexecute:67, AbstractDdlTask \nbeforeTransaction:32, BaseSyncTask \nexecuteImpl:56, TableSyncTask \nforEach:1511, ArrayList \naccept:-1, TableSyncTask$$Lambda$1939/0x00000008018e55f0 \nlambda$executeImpl$0:61, TableSyncTask \nsync:31, ClusterSyncManagerHelper \nsync:59, ClusterSyncManager \ndoSync:74, ClusterSyncManager \nsync:28, TableMetaChangeSyncAction \nsync:44, TableMetaChangeSyncAction ",
			"lineHeight": 1.2,
			"baseline": 284
		},
		{
			"type": "text",
			"version": 146,
			"versionNonce": 310374670,
			"isDeleted": false,
			"id": "AqerqXBa",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2294.1955962500283,
			"y": 367.4107588815518,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 503.90625,
			"height": 96,
			"seed": 1677375750,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "ioZiLBLccTgK7SQ3nSRfw",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "toNewVersion:221, GmsTableMetaManager\ntoNewVersionImpl:690, GmsTableMetaManager \n<init>:80, GmsTableMetaManager \nGmsTableMetaManager:94, GmsTableMetaManager",
			"rawText": "toNewVersion:221, GmsTableMetaManager\ntoNewVersionImpl:690, GmsTableMetaManager \n<init>:80, GmsTableMetaManager \nGmsTableMetaManager:94, GmsTableMetaManager",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "toNewVersion:221, GmsTableMetaManager\ntoNewVersionImpl:690, GmsTableMetaManager \n<init>:80, GmsTableMetaManager \nGmsTableMetaManager:94, GmsTableMetaManager",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 48,
			"versionNonce": 1249767122,
			"isDeleted": false,
			"id": "KxWsN8E_lTKbDEPra2udo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1886.6565337500283,
			"y": 430.7310713815516,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 371.3411458333335,
			"height": 3.0208333333332575,
			"seed": 1126750938,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					371.3411458333335,
					-3.0208333333332575
				]
			]
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 398106446,
			"isDeleted": false,
			"id": "wW4Mv6D1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2330.4846587500283,
			"y": 1381.5383630482183,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 468.75,
			"height": 96,
			"seed": 1735626374,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "ZXMiljnvy5Bem6MzQySU4",
					"type": "arrow"
				},
				{
					"id": "-VMYQfu7aLsQQRd7lKcjt",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "fetchTableMeta:153, GmsTableMetaManager \nbuildTableMeta:380, GmsTableMetaManager \n<init>:115-116, TableMeta \n<init>:121, TableMeta ",
			"rawText": "fetchTableMeta:153, GmsTableMetaManager \nbuildTableMeta:380, GmsTableMetaManager \n<init>:115-116, TableMeta \n<init>:121, TableMeta ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "fetchTableMeta:153, GmsTableMetaManager \nbuildTableMeta:380, GmsTableMetaManager \n<init>:115-116, TableMeta \n<init>:121, TableMeta ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "text",
			"version": 160,
			"versionNonce": 1312572562,
			"isDeleted": false,
			"id": "rHOKmAiF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3253.0497629166957,
			"y": 1390.9817224232183,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 574.21875,
			"height": 48,
			"seed": 1923145690,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "ZXMiljnvy5Bem6MzQySU4",
					"type": "arrow"
				},
				{
					"id": "fhmjvme8gk-ZW0Rxrmfse",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "private Map<String, FileMeta> fileMetaMap = null;\nprivate boolean fileMetaMapInitialized = false;",
			"rawText": "private Map<String, FileMeta> fileMetaMap = null;\nprivate boolean fileMetaMapInitialized = false;",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "private Map<String, FileMeta> fileMetaMap = null;\nprivate boolean fileMetaMapInitialized = false;",
			"lineHeight": 1.2,
			"baseline": 44
		},
		{
			"type": "arrow",
			"version": 275,
			"versionNonce": 1980073358,
			"isDeleted": false,
			"id": "waJ4s921rHfW56ShQ3lLt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -395.25752874997113,
			"y": 673.5020674753018,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1757.8125,
			"height": 338.3203125000001,
			"seed": 2048260742,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "JAhu5mfG",
				"focus": 0.9316132555408148,
				"gap": 14.271598725301828
			},
			"endBinding": {
				"elementId": "dbTNkdNV",
				"focus": -0.18719032314898879,
				"gap": 11.12516276041697
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
					930.9895833333334,
					125.10416666666663
				],
				[
					1757.8125,
					-213.21614583333348
				]
			]
		},
		{
			"type": "text",
			"version": 17,
			"versionNonce": 2066342482,
			"isDeleted": false,
			"id": "pQ7bK0as",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2823.2294504166966,
			"y": 1717.209912527383,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 117.1875,
			"height": 24,
			"seed": 26424986,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "table meta",
			"rawText": "table meta",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "table meta",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 40,
			"versionNonce": 244949966,
			"isDeleted": false,
			"id": "zyepUzN1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2842.2718611309824,
			"y": 1857.0804482416688,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 480.46875,
			"height": 168,
			"seed": 1560304518,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "4rLkhy1XQPteiw5WUafZA",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "\nexecuteStatement:144, ServerQueryHandler \nhandle:80, SelectHandler \nexecute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:850, ServerConnection \ngetConnection:1699, ServerConnection ",
			"rawText": "\nexecuteStatement:144, ServerQueryHandler \nhandle:80, SelectHandler \nexecute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:850, ServerConnection \ngetConnection:1699, ServerConnection ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "\nexecuteStatement:144, ServerQueryHandler \nhandle:80, SelectHandler \nexecute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:850, ServerConnection \ngetConnection:1699, ServerConnection ",
			"lineHeight": 1.2,
			"baseline": 164
		},
		{
			"type": "text",
			"version": 9,
			"versionNonce": 2082326546,
			"isDeleted": false,
			"id": "QW7mXle1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2841.0553432738393,
			"y": 2106.2322339559546,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 644.53125,
			"height": 264,
			"seed": 576683162,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "4rLkhy1XQPteiw5WUafZA",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "init:43, AbstractLifecycle \ndoInit:142, TDataSource \ninit:43, AbstractLifecycle \ndoInit:142, MatrixConfigHolder \ninitSchema:541, MatrixConfigHolder \ninit:43, AbstractLifecycle \ndoInit:178, GmsTableMetaManager \nfetchTableMetas:542, GmsTableMetaManager \nfetchSpecificSchemaTableMetas:577, GmsTableMetaManager \nbuildTableMeta:380, GmsTableMetaManager \n<init>:120, TableMeta ",
			"rawText": "init:43, AbstractLifecycle \ndoInit:142, TDataSource \ninit:43, AbstractLifecycle \ndoInit:142, MatrixConfigHolder \ninitSchema:541, MatrixConfigHolder \ninit:43, AbstractLifecycle \ndoInit:178, GmsTableMetaManager \nfetchTableMetas:542, GmsTableMetaManager \nfetchSpecificSchemaTableMetas:577, GmsTableMetaManager \nbuildTableMeta:380, GmsTableMetaManager \n<init>:120, TableMeta ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "init:43, AbstractLifecycle \ndoInit:142, TDataSource \ninit:43, AbstractLifecycle \ndoInit:142, MatrixConfigHolder \ninitSchema:541, MatrixConfigHolder \ninit:43, AbstractLifecycle \ndoInit:178, GmsTableMetaManager \nfetchTableMetas:542, GmsTableMetaManager \nfetchSpecificSchemaTableMetas:577, GmsTableMetaManager \nbuildTableMeta:380, GmsTableMetaManager \n<init>:120, TableMeta ",
			"lineHeight": 1.2,
			"baseline": 260
		},
		{
			"type": "arrow",
			"version": 89,
			"versionNonce": 865073678,
			"isDeleted": false,
			"id": "4rLkhy1XQPteiw5WUafZA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3056.289718273839,
			"y": 2045.1050018130968,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.5781250000004547,
			"height": 60.91517857142935,
			"seed": 45289286,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zyepUzN1",
				"focus": 0.12559673987282924,
				"gap": 20.024553571427987
			},
			"endBinding": {
				"elementId": "QW7mXle1",
				"focus": -0.30153057465321503,
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
					2.5781250000004547,
					60.91517857142935
				]
			]
		},
		{
			"type": "text",
			"version": 38,
			"versionNonce": 151975378,
			"isDeleted": false,
			"id": "3291yKHU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2801.9147182738398,
			"y": 2580.138483955954,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 187.5,
			"height": 24,
			"seed": 1980629210,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "OptimizerContext",
			"rawText": "OptimizerContext",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "OptimizerContext",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 9,
			"versionNonce": 199329870,
			"isDeleted": false,
			"id": "xUBcxmqp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2803.8343611309824,
			"y": 2666.0871446702404,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 480.46875,
			"height": 120,
			"seed": 1938988294,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "SLSXbBNHOT0uhuuKvponl",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "handle:65, FrontendCommandHandler \nquery:462, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:144, ServerQueryHandler \nhandle:80, SelectHandler ",
			"rawText": "handle:65, FrontendCommandHandler \nquery:462, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:144, ServerQueryHandler \nhandle:80, SelectHandler ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "handle:65, FrontendCommandHandler \nquery:462, FrontendConnection \nqueryRaw:115, ServerQueryHandler \nexecuteStatement:144, ServerQueryHandler \nhandle:80, SelectHandler ",
			"lineHeight": 1.2,
			"baseline": 116
		},
		{
			"type": "text",
			"version": 25,
			"versionNonce": 1125411730,
			"isDeleted": false,
			"id": "vmsjCWfY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2801.892396845268,
			"y": 2843.6429482416684,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 433.59375,
			"height": 96,
			"seed": 1116015686,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "SLSXbBNHOT0uhuuKvponl",
					"type": "arrow"
				},
				{
					"id": "GIpr4lRDdT_30axtj1Eah",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "execute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:850, ServerConnection \ngetConnection:1699, ServerConnection ",
			"rawText": "execute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:850, ServerConnection \ngetConnection:1699, ServerConnection ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "execute:685, ServerConnection \nexecute:702, ServerConnection \ninnerExecute:850, ServerConnection \ngetConnection:1699, ServerConnection ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 17,
			"versionNonce": 2003259022,
			"isDeleted": false,
			"id": "SLSXbBNHOT0uhuuKvponl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2938.1647182738398,
			"y": 2796.480559848812,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.845982142856883,
			"height": 39.98883928571422,
			"seed": 1983454726,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xUBcxmqp",
				"focus": 0.45362706112768464,
				"gap": 10.393415178571558
			},
			"endBinding": {
				"elementId": "vmsjCWfY",
				"focus": -0.3349116545111136,
				"gap": 7.1735491071422075
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
					2.845982142856883,
					39.98883928571422
				]
			]
		},
		{
			"type": "arrow",
			"version": 27,
			"versionNonce": 275065170,
			"isDeleted": false,
			"id": "GIpr4lRDdT_30axtj1Eah",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2950.7763254166966,
			"y": 2947.842166991669,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.7739319669126417,
			"height": 52.65625,
			"seed": 839705050,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "vmsjCWfY",
				"focus": 0.31574396909166824,
				"gap": 8.199218750000455
			},
			"endBinding": {
				"elementId": "dLPDkFab",
				"focus": -0.03142149687416929,
				"gap": 14.698660714286234
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
					0.7739319669126417,
					52.65625
				]
			]
		},
		{
			"type": "text",
			"version": 42,
			"versionNonce": 1926909134,
			"isDeleted": false,
			"id": "dLPDkFab",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2799.079896845268,
			"y": 3015.197077705955,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 316.40625,
			"height": 72,
			"seed": 2082801798,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "GIpr4lRDdT_30axtj1Eah",
					"type": "arrow"
				},
				{
					"id": "z4DHyzNkNOcRpVCPZcx96",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "init:43, AbstractLifecycle \ndoInit:142, TDataSource \ninit:43, AbstractLifecycle ",
			"rawText": "init:43, AbstractLifecycle \ndoInit:142, TDataSource \ninit:43, AbstractLifecycle ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "init:43, AbstractLifecycle \ndoInit:142, TDataSource \ninit:43, AbstractLifecycle ",
			"lineHeight": 1.2,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 32,
			"versionNonce": 2019045138,
			"isDeleted": false,
			"id": "oE3uIJqE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3406.8589147024113,
			"y": 3020.6658277059546,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 410.15625,
			"height": 48,
			"seed": 19638470,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "z4DHyzNkNOcRpVCPZcx96",
					"type": "arrow"
				},
				{
					"id": "PqvJZIAbWE-8sWrAuzsbo",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "doInit:142, MatrixConfigHolder \ninitSchema:526, MatrixConfigHolder ",
			"rawText": "doInit:142, MatrixConfigHolder \ninitSchema:526, MatrixConfigHolder ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "doInit:142, MatrixConfigHolder \ninitSchema:526, MatrixConfigHolder ",
			"lineHeight": 1.2,
			"baseline": 44
		},
		{
			"type": "text",
			"version": 141,
			"versionNonce": 2077459214,
			"isDeleted": false,
			"id": "sGRBvFXT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3391.959361130982,
			"y": 3850.4760955630973,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 421.875,
			"height": 72,
			"seed": 411475974,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "PqvJZIAbWE-8sWrAuzsbo",
					"type": "arrow"
				},
				{
					"id": "yAVbtuX5yMXjl8b7vpwUu",
					"type": "arrow"
				}
			],
			"updated": 1684308939728,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "doInit:154, MatrixConfigHolder \nloadContext:224, MatrixConfigHolder \nloadContext:94, OptimizerContext ",
			"rawText": "doInit:154, MatrixConfigHolder \nloadContext:224, MatrixConfigHolder \nloadContext:94, OptimizerContext ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "doInit:154, MatrixConfigHolder \nloadContext:224, MatrixConfigHolder \nloadContext:94, OptimizerContext ",
			"lineHeight": 1.2,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 97,
			"versionNonce": 2137291986,
			"isDeleted": false,
			"id": "z4DHyzNkNOcRpVCPZcx96",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3124.637932559554,
			"y": 3039.011111457473,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 269.0290178571431,
			"height": 1.9086618241058204,
			"seed": 1926149702,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "dLPDkFab",
				"focus": -0.36024853644950133,
				"gap": 9.15178571428578
			},
			"endBinding": {
				"elementId": "oE3uIJqE",
				"focus": 0.08632930655815049,
				"gap": 13.19196428571422
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
					269.0290178571431,
					1.9086618241058204
				]
			]
		},
		{
			"type": "arrow",
			"version": 197,
			"versionNonce": 1959522638,
			"isDeleted": false,
			"id": "PqvJZIAbWE-8sWrAuzsbo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3585.8804241975076,
			"y": 3079.261670339884,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.5249630971370607,
			"height": 763.3593749999991,
			"seed": 1635514010,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oE3uIJqE",
				"focus": 0.12605030772963896,
				"gap": 10.595842633928896
			},
			"endBinding": {
				"elementId": "sGRBvFXT",
				"focus": -0.09826405582645806,
				"gap": 7.855050223214221
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
					-3.5249630971370607,
					763.3593749999991
				]
			]
		},
		{
			"type": "text",
			"version": 87,
			"versionNonce": 52499090,
			"isDeleted": false,
			"id": "X4Lyc5yV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3980.106682559554,
			"y": 2990.6455989113115,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 222.65625,
			"height": 24,
			"seed": 204392602,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "init schema manager",
			"rawText": "init schema manager",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "init schema manager",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 342,
			"versionNonce": 152868750,
			"isDeleted": false,
			"id": "EJbWrgXE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3927.662486130982,
			"y": 3848.290688197026,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 457.03125,
			"height": 48,
			"seed": 1449351686,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "init optimizerContext for fresh schema,\nupdate optimizerContextMap",
			"rawText": "init optimizerContext for fresh schema,\nupdate optimizerContextMap",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "init optimizerContext for fresh schema,\nupdate optimizerContextMap",
			"lineHeight": 1.2,
			"baseline": 44
		},
		{
			"type": "text",
			"version": 165,
			"versionNonce": 373616722,
			"isDeleted": false,
			"id": "fPqwxsNP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3916.9928432738407,
			"y": 4141.9625631970275,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 937.5,
			"height": 192,
			"seed": 85267590,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "yAVbtuX5yMXjl8b7vpwUu",
					"type": "arrow"
				}
			],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "    // Major call path:\n    //   ServerConnection.(getSchemaConfig|getConnection)\n    //   -> TDataSource.init\n    //   -> MatrixConfigHolder.init\n    public static void loadContext(OptimizerContext context) {\n        optimizerContextMap.put(context.getSchemaName().toLowerCase(), context);\n        DefaultSchema.setSchemaName(context.getSchemaName());\n    }",
			"rawText": "    // Major call path:\n    //   ServerConnection.(getSchemaConfig|getConnection)\n    //   -> TDataSource.init\n    //   -> MatrixConfigHolder.init\n    public static void loadContext(OptimizerContext context) {\n        optimizerContextMap.put(context.getSchemaName().toLowerCase(), context);\n        DefaultSchema.setSchemaName(context.getSchemaName());\n    }",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "    // Major call path:\n    //   ServerConnection.(getSchemaConfig|getConnection)\n    //   -> TDataSource.init\n    //   -> MatrixConfigHolder.init\n    public static void loadContext(OptimizerContext context) {\n        optimizerContextMap.put(context.getSchemaName().toLowerCase(), context);\n        DefaultSchema.setSchemaName(context.getSchemaName());\n    }",
			"lineHeight": 1.2,
			"baseline": 188
		},
		{
			"type": "arrow",
			"version": 530,
			"versionNonce": 285111758,
			"isDeleted": false,
			"id": "yAVbtuX5yMXjl8b7vpwUu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3693.21531877097,
			"y": 3925.9915810541693,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 326.6750005712529,
			"height": 204.8995535714289,
			"seed": 2090594118,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "sGRBvFXT",
				"focus": -0.10180716797965182,
				"gap": 3.5154854910720132
			},
			"endBinding": {
				"elementId": "fPqwxsNP",
				"focus": -0.3138392211825669,
				"gap": 11.071428571429351
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
					326.6750005712529,
					204.8995535714289
				]
			]
		},
		{
			"type": "text",
			"version": 301,
			"versionNonce": 1554454034,
			"isDeleted": false,
			"id": "trD1RrYa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3874.2807897024113,
			"y": 3076.650063197027,
			"strokeColor": "#087f5b",
			"backgroundColor": "transparent",
			"width": 480.46875,
			"height": 48,
			"seed": 173848582,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "information_schema -> RoutedSchemaManager\nother table.       -> GmsTableMetaManager",
			"rawText": "information_schema -> RoutedSchemaManager\nother table.       -> GmsTableMetaManager",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "information_schema -> RoutedSchemaManager\nother table.       -> GmsTableMetaManager",
			"lineHeight": 1.2,
			"baseline": 44
		},
		{
			"type": "text",
			"version": 161,
			"versionNonce": 1972014094,
			"isDeleted": false,
			"id": "eYOveits",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5301.401325416697,
			"y": 3016.5844940005986,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 644.53125,
			"height": 96,
			"seed": 2131253382,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "yCDlDIiVrx-8sjdjEwbWl",
					"type": "arrow"
				},
				{
					"id": "fovJa0HO7smOMWa4M_fwk",
					"type": "arrow"
				}
			],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "init:43, AbstractLifecycle \ndoInit:178, GmsTableMetaManager \nfetchTableMetas:542, GmsTableMetaManager \nfetchSpecificSchemaTableMetas:557, GmsTableMetaManager ",
			"rawText": "init:43, AbstractLifecycle \ndoInit:178, GmsTableMetaManager \nfetchTableMetas:542, GmsTableMetaManager \nfetchSpecificSchemaTableMetas:557, GmsTableMetaManager ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "init:43, AbstractLifecycle \ndoInit:178, GmsTableMetaManager \nfetchTableMetas:542, GmsTableMetaManager \nfetchSpecificSchemaTableMetas:557, GmsTableMetaManager ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 220,
			"versionNonce": 1732150226,
			"isDeleted": false,
			"id": "yCDlDIiVrx-8sjdjEwbWl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3815.843289702411,
			"y": 3038.518785295241,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1471.7187500000005,
			"height": 1.5905349045706316,
			"seed": 1127019098,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "eYOveits",
				"focus": 0.49871334879672297,
				"gap": 13.839285714285325
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
					1471.7187500000005,
					1.5905349045706316
				]
			]
		},
		{
			"type": "text",
			"version": 273,
			"versionNonce": 347724366,
			"isDeleted": false,
			"id": "FEONFoQN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5304.169182559555,
			"y": 3284.347468330955,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 644.53125,
			"height": 72,
			"seed": 486188486,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "fovJa0HO7smOMWa4M_fwk",
					"type": "arrow"
				},
				{
					"id": "UTcZxl-9an5Jl5CXc3zy6",
					"type": "arrow"
				}
			],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "fetchSpecificSchemaTableMetas:559, GmsTableMetaManager \nfetchTablesRecords:14, DefaultMetaFetcher \nqueryTables:184, TableInfoManager ",
			"rawText": "fetchSpecificSchemaTableMetas:559, GmsTableMetaManager \nfetchTablesRecords:14, DefaultMetaFetcher \nqueryTables:184, TableInfoManager ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "fetchSpecificSchemaTableMetas:559, GmsTableMetaManager \nfetchTablesRecords:14, DefaultMetaFetcher \nqueryTables:184, TableInfoManager ",
			"lineHeight": 1.2,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 177,
			"versionNonce": 270678418,
			"isDeleted": false,
			"id": "fovJa0HO7smOMWa4M_fwk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5620.765137494526,
			"y": 3116.5335732416693,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.6327286056402954,
			"height": 158.56026785714266,
			"seed": 1017493850,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "eYOveits",
				"focus": 0.00964194326255774,
				"gap": 3.949079241070649
			},
			"endBinding": {
				"elementId": "FEONFoQN",
				"focus": -0.015062713421406833,
				"gap": 9.253627232143117
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
					0.6327286056402954,
					158.56026785714266
				]
			]
		},
		{
			"type": "text",
			"version": 48,
			"versionNonce": 627400846,
			"isDeleted": false,
			"id": "epMDvryn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6333.979450416696,
			"y": 3289.4576803845266,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 328.125,
			"height": 96,
			"seed": 172449990,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "yZT76jXoVx-qXjqy6eFDk",
					"type": "arrow"
				},
				{
					"id": "371D8bXDuNnsUR2niIiBI",
					"type": "arrow"
				}
			],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "query:182, TablesAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"rawText": "query:182, TablesAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "query:182, TablesAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 55,
			"versionNonce": 1451833170,
			"isDeleted": false,
			"id": "yZT76jXoVx-qXjqy6eFDk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5944.604450416696,
			"y": 3330.7076803845266,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 377.55580357142844,
			"height": 2.6227678571426623,
			"seed": 162187034,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "epMDvryn",
				"focus": 0.05912601639542762,
				"gap": 11.819196428571558
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
					377.55580357142844,
					2.6227678571426623
				]
			]
		},
		{
			"type": "text",
			"version": 70,
			"versionNonce": 457580238,
			"isDeleted": false,
			"id": "Ky3lLZgq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6316.925878988124,
			"y": 3110.4844660988124,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 363.28125,
			"height": 24,
			"seed": 80184134,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "371D8bXDuNnsUR2niIiBI",
					"type": "arrow"
				}
			],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "TableAccessor.SELECT_TABLES_ALL",
			"rawText": "TableAccessor.SELECT_TABLES_ALL",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TableAccessor.SELECT_TABLES_ALL",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 122,
			"versionNonce": 986348818,
			"isDeleted": false,
			"id": "371D8bXDuNnsUR2niIiBI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6486.31203970241,
			"y": 3144.7701803845266,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.044642857143117,
			"height": 138.01339285714266,
			"seed": 1446979846,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Ky3lLZgq",
				"focus": 0.06742431030987348,
				"gap": 10.28571428571422
			},
			"endBinding": {
				"elementId": "epMDvryn",
				"focus": -0.07186970204203644,
				"gap": 6.674107142857338
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
					-0.044642857143117,
					138.01339285714266
				]
			]
		},
		{
			"type": "text",
			"version": 26,
			"versionNonce": 183833870,
			"isDeleted": false,
			"id": "VS2G0KzD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6524.20266470241,
			"y": 3204.747858955955,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 210.9375,
			"height": 24,
			"seed": 1306353798,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "input sql template",
			"rawText": "input sql template",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "input sql template",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 37,
			"versionNonce": 442305234,
			"isDeleted": false,
			"id": "FN2tslaP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5309.861146845264,
			"y": 3687.7654370809537,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 644.53125,
			"height": 96,
			"seed": 307626246,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "UTcZxl-9an5Jl5CXc3zy6",
					"type": "arrow"
				},
				{
					"id": "iS5sa9zxxxXu8Fy7QKzz9",
					"type": "arrow"
				},
				{
					"id": "Wj63EIp6conV8Z-epenao",
					"type": "arrow"
				}
			],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "fetchSpecificSchemaTableMetas:561, GmsTableMetaManager \nfetchColumnsRecords:20, DefaultMetaFetcher \nqueryVisibleColumns:204, TableInfoManager \nqueryColumns:214, TableInfoManager",
			"rawText": "fetchSpecificSchemaTableMetas:561, GmsTableMetaManager \nfetchColumnsRecords:20, DefaultMetaFetcher \nqueryVisibleColumns:204, TableInfoManager \nqueryColumns:214, TableInfoManager",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "fetchSpecificSchemaTableMetas:561, GmsTableMetaManager \nfetchColumnsRecords:20, DefaultMetaFetcher \nqueryVisibleColumns:204, TableInfoManager \nqueryColumns:214, TableInfoManager",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "text",
			"version": 28,
			"versionNonce": 233521998,
			"isDeleted": false,
			"id": "IcANi8yD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6353.231682559552,
			"y": 3699.606954938097,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 328.125,
			"height": 96,
			"seed": 1525587738,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "iS5sa9zxxxXu8Fy7QKzz9",
					"type": "arrow"
				},
				{
					"id": "fowu5ksDabvTjYhuGqAPl",
					"type": "arrow"
				}
			],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "query:308, ColumnsAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"rawText": "query:308, ColumnsAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "query:308, ColumnsAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 99,
			"versionNonce": 198697106,
			"isDeleted": false,
			"id": "UTcZxl-9an5Jl5CXc3zy6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5607.558528183193,
			"y": 3363.3346335095252,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.9800784131712135,
			"height": 312.07589285714266,
			"seed": 1900353222,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FEONFoQN",
				"focus": 0.06050313336526244,
				"gap": 6.987165178570194
			},
			"endBinding": {
				"elementId": "FN2tslaP",
				"focus": -0.053936929790805756,
				"gap": 12.35491071428578
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
					5.9800784131712135,
					312.07589285714266
				]
			]
		},
		{
			"type": "arrow",
			"version": 25,
			"versionNonce": 646031758,
			"isDeleted": false,
			"id": "iS5sa9zxxxXu8Fy7QKzz9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5962.428111130979,
			"y": 3750.019901366668,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 379.921875,
			"height": 2.2098214285715585,
			"seed": 1491336070,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FN2tslaP",
				"focus": 0.3243276447299484,
				"gap": 8.035714285715585
			},
			"endBinding": {
				"elementId": "IcANi8yD",
				"focus": 0.016636762732493232,
				"gap": 10.881696428572468
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
					379.921875,
					-2.2098214285715585
				]
			]
		},
		{
			"type": "text",
			"version": 36,
			"versionNonce": 988937810,
			"isDeleted": false,
			"id": "DyVQhekv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6307.372307559551,
			"y": 3553.334633509526,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 468.75,
			"height": 24,
			"seed": 1967032858,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "fowu5ksDabvTjYhuGqAPl",
					"type": "arrow"
				},
				{
					"id": "evNP4sxhBJAWxkZteYmC_",
					"type": "arrow"
				}
			],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "ColumnsAccessor.SELECT_ALL_TABLE_COLUMNS",
			"rawText": "ColumnsAccessor.SELECT_ALL_TABLE_COLUMNS",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ColumnsAccessor.SELECT_ALL_TABLE_COLUMNS",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 18,
			"versionNonce": 603015118,
			"isDeleted": false,
			"id": "fowu5ksDabvTjYhuGqAPl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6524.269628988122,
			"y": 3589.361419223812,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1272321428577925,
			"height": 99.65401785714312,
			"seed": 123963142,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "DyVQhekv",
				"focus": 0.0733693510212936,
				"gap": 12.02678571428578
			},
			"endBinding": {
				"elementId": "IcANi8yD",
				"focus": 0.03150235213909346,
				"gap": 10.591517857141753
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
					-1.1272321428577925,
					99.65401785714312
				]
			]
		},
		{
			"type": "text",
			"version": 20,
			"versionNonce": 1149395986,
			"isDeleted": false,
			"id": "D8kMerky",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6574.749539702408,
			"y": 3634.752044223812,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 210.9375,
			"height": 24,
			"seed": 2048920538,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "input sql template",
			"rawText": "input sql template",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "input sql template",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 109,
			"versionNonce": 106110478,
			"isDeleted": false,
			"id": "evNP4sxhBJAWxkZteYmC_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6784.425878988122,
			"y": 3570.0757049380977,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 461.74107142857065,
			"height": 2.8628158919677844,
			"seed": 2094101082,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "DyVQhekv",
				"focus": 0.24057239659826093,
				"gap": 8.303571428571558
			},
			"endBinding": {
				"elementId": "u74ZVsxy",
				"focus": 0.684417533488642,
				"gap": 28.169642857143117
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
					461.74107142857065,
					2.8628158919677844
				]
			]
		},
		{
			"type": "rectangle",
			"version": 137,
			"versionNonce": 310383058,
			"isDeleted": false,
			"id": "1l8wttSdKKXMWwSxXFDdZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 7264.236146845265,
			"y": 3739.0489192238124,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 355.58035714285694,
			"height": 37.020089285714675,
			"seed": 43006938,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 30,
			"versionNonce": 1654664270,
			"isDeleted": false,
			"id": "7DW1OUZ3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5337.394628988123,
			"y": 4296.4149906523835,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 644.53125,
			"height": 96,
			"seed": 958618074,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "Wj63EIp6conV8Z-epenao",
					"type": "arrow"
				},
				{
					"id": "RKe4QasYG98zqDsnFdvOu",
					"type": "arrow"
				},
				{
					"id": "XB578Cg3kVMJ1Ya_7fjAQ",
					"type": "arrow"
				}
			],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "fetchSpecificSchemaTableMetas:563, GmsTableMetaManager \nfetchIndexesRecords:26, DefaultMetaFetcher \nqueryVisibleIndexes:238, TableInfoManager \nqueryIndexes:248, TableInfoManager ",
			"rawText": "fetchSpecificSchemaTableMetas:563, GmsTableMetaManager \nfetchIndexesRecords:26, DefaultMetaFetcher \nqueryVisibleIndexes:238, TableInfoManager \nqueryIndexes:248, TableInfoManager ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "fetchSpecificSchemaTableMetas:563, GmsTableMetaManager \nfetchIndexesRecords:26, DefaultMetaFetcher \nqueryVisibleIndexes:238, TableInfoManager \nqueryIndexes:248, TableInfoManager ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "text",
			"version": 45,
			"versionNonce": 939657106,
			"isDeleted": false,
			"id": "CLPXLPeD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6367.930343273837,
			"y": 4297.5087406523835,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 328.125,
			"height": 96,
			"seed": 302976666,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "RKe4QasYG98zqDsnFdvOu",
					"type": "arrow"
				},
				{
					"id": "MPxOdAuwSfsEMCj3Xz0UI",
					"type": "arrow"
				}
			],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "query:249, IndexesAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"rawText": "query:249, IndexesAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "query:249, IndexesAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 30,
			"versionNonce": 1186034318,
			"isDeleted": false,
			"id": "Wj63EIp6conV8Z-epenao",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5614.526325416694,
			"y": 3798.4748399827404,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.0825892857146755,
			"height": 482.2209821428569,
			"seed": 1403372038,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939729,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FN2tslaP",
				"focus": 0.05503317041604038,
				"gap": 14.709402901786689
			},
			"endBinding": {
				"elementId": "7DW1OUZ3",
				"focus": -0.1362032082423509,
				"gap": 15.719168526786234
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
					1.0825892857146755,
					482.2209821428569
				]
			]
		},
		{
			"type": "text",
			"version": 36,
			"versionNonce": 1295992146,
			"isDeleted": false,
			"id": "2tV6dsbn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6351.691503988123,
			"y": 4099.412339982741,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 386.71875,
			"height": 24,
			"seed": 329831770,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "MPxOdAuwSfsEMCj3Xz0UI",
					"type": "arrow"
				},
				{
					"id": "4W9c2kimZvkRPATxrWLTx",
					"type": "arrow"
				}
			],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "IndexsAccessor.SELECT_ALL_INDEXES",
			"rawText": "IndexsAccessor.SELECT_ALL_INDEXES",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "IndexsAccessor.SELECT_ALL_INDEXES",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 44,
			"versionNonce": 490729678,
			"isDeleted": false,
			"id": "RKe4QasYG98zqDsnFdvOu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5999.950432559552,
			"y": 4358.4413578398835,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 362.02008928571377,
			"height": 7.857142857143117,
			"seed": 1419863962,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "7DW1OUZ3",
				"focus": 0.3893472931176586,
				"gap": 18.02455357142844
			},
			"endBinding": {
				"elementId": "CLPXLPeD",
				"focus": -0.026868814002752553,
				"gap": 5.9598214285715585
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
					362.02008928571377,
					-7.857142857143117
				]
			]
		},
		{
			"type": "arrow",
			"version": 26,
			"versionNonce": 1267649298,
			"isDeleted": false,
			"id": "MPxOdAuwSfsEMCj3Xz0UI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6538.59998613098,
			"y": 4132.470375697027,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.9196428571422075,
			"height": 164.28571428571377,
			"seed": 282651354,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "2tV6dsbn",
				"focus": 0.03460964100166012,
				"gap": 9.058035714285325
			},
			"endBinding": {
				"elementId": "CLPXLPeD",
				"focus": 0.055256127140283946,
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
					1.9196428571422075,
					164.28571428571377
				]
			]
		},
		{
			"type": "text",
			"version": 20,
			"versionNonce": 300197646,
			"isDeleted": false,
			"id": "Wtwdjgoc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6608.231682559552,
			"y": 4209.267250697027,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 210.9375,
			"height": 24,
			"seed": 1966347590,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "input sql template",
			"rawText": "input sql template",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "input sql template",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 41,
			"versionNonce": 1768397010,
			"isDeleted": false,
			"id": "QSn1WT9R",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 7285.943736130979,
			"y": 4090.2047506970266,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1312.5,
			"height": 192,
			"seed": 618208326,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "4W9c2kimZvkRPATxrWLTx",
					"type": "arrow"
				}
			],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "select \n        `table_schema`, `table_name`, `non_unique`, `index_schema`, `index_name`, `seq_in_index`, `column_name`,\n        `collation`, `cardinality`, `sub_part`, `packed`, `nullable`, `index_type`, `comment`, `index_comment`,\n        `index_column_type`, `index_location`, `index_table_name`, `index_status`, `version`, `flag` \nfrom \n        `indexes`\nwhere `table_schema` = ? \norder by `seq_in_index`",
			"rawText": "select \n        `table_schema`, `table_name`, `non_unique`, `index_schema`, `index_name`, `seq_in_index`, `column_name`,\n        `collation`, `cardinality`, `sub_part`, `packed`, `nullable`, `index_type`, `comment`, `index_comment`,\n        `index_column_type`, `index_location`, `index_table_name`, `index_status`, `version`, `flag` \nfrom \n        `indexes`\nwhere `table_schema` = ? \norder by `seq_in_index`",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "select \n        `table_schema`, `table_name`, `non_unique`, `index_schema`, `index_name`, `seq_in_index`, `column_name`,\n        `collation`, `cardinality`, `sub_part`, `packed`, `nullable`, `index_type`, `comment`, `index_comment`,\n        `index_column_type`, `index_location`, `index_table_name`, `index_status`, `version`, `flag` \nfrom \n        `indexes`\nwhere `table_schema` = ? \norder by `seq_in_index`",
			"lineHeight": 1.2,
			"baseline": 188
		},
		{
			"type": "text",
			"version": 48,
			"versionNonce": 1964545358,
			"isDeleted": false,
			"id": "u74ZVsxy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 7274.336593273836,
			"y": 3546.434521902383,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1417.96875,
			"height": 216,
			"seed": 1215225242,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "evNP4sxhBJAWxkZteYmC_",
					"type": "arrow"
				}
			],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "select\n        `table_schema`, `table_name`, `column_name`, `ordinal_position`, `column_default`, `is_nullable`, `data_type`,\n        `character_maximum_length`, `character_octet_length`, `numeric_precision`, `numeric_scale`, `datetime_precision`,\n        `character_set_name`, `collation_name`, `column_type`, `column_key`, `extra`, `privileges`, `column_comment`,\n        `generation_expression`, `jdbc_type`, `jdbc_type_name`, `field_length`, `version`, `status`, `flag` \nfrom \n        `columns` \nwhere `table_schema` = ? \norder by ordinal_position asc",
			"rawText": "select\n        `table_schema`, `table_name`, `column_name`, `ordinal_position`, `column_default`, `is_nullable`, `data_type`,\n        `character_maximum_length`, `character_octet_length`, `numeric_precision`, `numeric_scale`, `datetime_precision`,\n        `character_set_name`, `collation_name`, `column_type`, `column_key`, `extra`, `privileges`, `column_comment`,\n        `generation_expression`, `jdbc_type`, `jdbc_type_name`, `field_length`, `version`, `status`, `flag` \nfrom \n        `columns` \nwhere `table_schema` = ? \norder by ordinal_position asc",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "select\n        `table_schema`, `table_name`, `column_name`, `ordinal_position`, `column_default`, `is_nullable`, `data_type`,\n        `character_maximum_length`, `character_octet_length`, `numeric_precision`, `numeric_scale`, `datetime_precision`,\n        `character_set_name`, `collation_name`, `column_type`, `column_key`, `extra`, `privileges`, `column_comment`,\n        `generation_expression`, `jdbc_type`, `jdbc_type_name`, `field_length`, `version`, `status`, `flag` \nfrom \n        `columns` \nwhere `table_schema` = ? \norder by ordinal_position asc",
			"lineHeight": 1.2,
			"baseline": 212
		},
		{
			"type": "rectangle",
			"version": 236,
			"versionNonce": 1986047634,
			"isDeleted": false,
			"id": "KvkXdryQuv_j3dG7FLhJL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 7281.791950416694,
			"y": 4263.619231723812,
			"strokeColor": "#c92a2a",
			"backgroundColor": "transparent",
			"width": 355.58035714285694,
			"height": 37.020089285714675,
			"seed": 43006938,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 13,
			"versionNonce": 540326798,
			"isDeleted": false,
			"id": "vwoJLBVq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5326.300878988122,
			"y": 4841.952100027382,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 644.53125,
			"height": 72,
			"seed": 116903578,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "tyZrDXDLpIpqj7nPvU6NG",
					"type": "arrow"
				}
			],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "fetchSpecificSchemaTableMetas:565, GmsTableMetaManager \nfetchTablesExtRecords:34, DefaultMetaFetcher \nqueryTableExts:160, TableInfoManager ",
			"rawText": "fetchSpecificSchemaTableMetas:565, GmsTableMetaManager \nfetchTablesExtRecords:34, DefaultMetaFetcher \nqueryTableExts:160, TableInfoManager ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "fetchSpecificSchemaTableMetas:565, GmsTableMetaManager \nfetchTablesExtRecords:34, DefaultMetaFetcher \nqueryTableExts:160, TableInfoManager ",
			"lineHeight": 1.2,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 57,
			"versionNonce": 925961298,
			"isDeleted": false,
			"id": "4W9c2kimZvkRPATxrWLTx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6740.6423968452655,
			"y": 4105.833935964882,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 524.6428571428569,
			"height": 0.6584821428577925,
			"seed": 803506458,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "2tV6dsbn",
				"focus": -0.4757037640012841,
				"gap": 2.2321428571422075
			},
			"endBinding": {
				"elementId": "QSn1WT9R",
				"focus": 0.814498631663755,
				"gap": 20.658482142856883
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
					524.6428571428569,
					0.6584821428577925
				]
			]
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 1500649934,
			"isDeleted": false,
			"id": "E6Y8mwzs",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6304.012932559552,
			"y": 4709.551848911309,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 457.03125,
			"height": 24,
			"seed": 1540726534,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "X8WD9tA-9A1EtdpS_nREf",
					"type": "arrow"
				}
			],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "TablesExtAccessor.SELECT_TABLES_EXT_ALL",
			"rawText": "TablesExtAccessor.SELECT_TABLES_EXT_ALL",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TablesExtAccessor.SELECT_TABLES_EXT_ALL",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 37,
			"versionNonce": 1102033426,
			"isDeleted": false,
			"id": "iBnPuWst",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6349.124539702408,
			"y": 4859.094259625596,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 339.84375,
			"height": 96,
			"seed": 282203526,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "X8WD9tA-9A1EtdpS_nREf",
					"type": "arrow"
				},
				{
					"id": "tyZrDXDLpIpqj7nPvU6NG",
					"type": "arrow"
				}
			],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "query:165, TablesExtAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"rawText": "query:165, TablesExtAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "query:165, TablesExtAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 159,
			"versionNonce": 938061838,
			"isDeleted": false,
			"id": "X8WD9tA-9A1EtdpS_nREf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6507.799729760126,
			"y": 4744.3732774827395,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.25909049994515954,
			"height": 96.79687499999909,
			"seed": 282651354,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "E6Y8mwzs",
				"focus": 0.10819892128555547,
				"gap": 10.82142857143026
			},
			"endBinding": {
				"elementId": "iBnPuWst",
				"focus": -0.06357610568613506,
				"gap": 17.924107142857792
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
					0.25909049994515954,
					96.79687499999909
				]
			]
		},
		{
			"type": "text",
			"version": 63,
			"versionNonce": 1490264018,
			"isDeleted": false,
			"id": "89MdyYWt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6563.471637916693,
			"y": 4780.143366768454,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 210.9375,
			"height": 24,
			"seed": 1966347590,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "input sql template",
			"rawText": "input sql template",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "input sql template",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 36,
			"versionNonce": 127172174,
			"isDeleted": false,
			"id": "tyZrDXDLpIpqj7nPvU6NG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5980.530789702409,
			"y": 4876.806313197025,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 355.13392857142844,
			"height": 6.261160714286234,
			"seed": 705647386,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "vwoJLBVq",
				"focus": 0.1129245143705563,
				"gap": 9.698660714286234
			},
			"endBinding": {
				"elementId": "iBnPuWst",
				"focus": 0.7801075420020764,
				"gap": 13.459821428570649
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
					355.13392857142844,
					-6.261160714286234
				]
			]
		},
		{
			"type": "arrow",
			"version": 47,
			"versionNonce": 1219745170,
			"isDeleted": false,
			"id": "XB578Cg3kVMJ1Ya_7fjAQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5618.265164702403,
			"y": 4411.251067661309,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.9977678571422075,
			"height": 410.9821428571431,
			"seed": 1336433990,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "7DW1OUZ3",
				"focus": 0.12936468989326974,
				"gap": 18.836077008925713
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
					1.9977678571422075,
					410.9821428571431
				]
			]
		},
		{
			"type": "text",
			"version": 1127,
			"versionNonce": 759923854,
			"isDeleted": false,
			"id": "yXFxiAIJ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 918.2767508947645,
			"y": -266.68063281600837,
			"strokeColor": "#000000",
			"backgroundColor": "#fab005",
			"width": 59.97596740722656,
			"height": 35,
			"seed": 472118498,
			"groupIds": [
				"0QFGOmgOpHU-bfm26yX2v"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Lock",
			"rawText": "Lock",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lock",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "ellipse",
			"version": 2545,
			"versionNonce": 1116164946,
			"isDeleted": false,
			"id": "_O-Oz4FUOFYy2Y92z-rrp",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 912.5626114074062,
			"y": -227.88778989951732,
			"strokeColor": "#228be6",
			"backgroundColor": "#228be6",
			"width": 73.19664924872156,
			"height": 70.29189670381018,
			"seed": 342589026,
			"groupIds": [
				"IDJcnGBxa9Ru5HTo9abOs",
				"0QFGOmgOpHU-bfm26yX2v"
			],
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "n7oVU9wn0bxsMRM016now",
					"type": "arrow"
				}
			],
			"updated": 1684308939730,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1200,
			"versionNonce": 180863694,
			"isDeleted": false,
			"id": "T9p7czs-8B8MGY2Z14dyr",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 937.2586271821842,
			"y": -211.64005767116748,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 23.900832232090984,
			"height": 26.63008094128938,
			"seed": 1490784446,
			"groupIds": [
				"IDJcnGBxa9Ru5HTo9abOs",
				"0QFGOmgOpHU-bfm26yX2v"
			],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1174,
			"versionNonce": 950343954,
			"isDeleted": false,
			"id": "B7nayaQTv_YFjSgItZ90X",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 931.9555554705962,
			"y": -199.96773473809787,
			"strokeColor": "#ffffff",
			"backgroundColor": "#ffffff",
			"width": 34.86775741170757,
			"height": 21.838147304859902,
			"seed": 1626432034,
			"groupIds": [
				"IDJcnGBxa9Ru5HTo9abOs",
				"0QFGOmgOpHU-bfm26yX2v"
			],
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1015,
			"versionNonce": 1654798606,
			"isDeleted": false,
			"id": "2rRiSWv743k0WjhPTK6MS",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 946.9894041156267,
			"y": -192.3228261372809,
			"strokeColor": "#228be6",
			"backgroundColor": "#228be6",
			"width": 4.428986221217656,
			"height": 11.213776130421358,
			"seed": 1793509630,
			"groupIds": [
				"IDJcnGBxa9Ru5HTo9abOs",
				"0QFGOmgOpHU-bfm26yX2v"
			],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 45,
			"versionNonce": 981739218,
			"isDeleted": false,
			"id": "ffA1_DcMSBH9KI8mRb4s_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 792.6667954067673,
			"y": -530.5952942558579,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 150.43945312499977,
			"height": 264.0429687500001,
			"seed": 43086534,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					150.43945312499977,
					264.0429687500001
				]
			]
		},
		{
			"type": "arrow",
			"version": 42,
			"versionNonce": 1012131662,
			"isDeleted": false,
			"id": "n7oVU9wn0bxsMRM016now",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 443.1257797817673,
			"y": 51.32853386914212,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 473.2617187499998,
			"height": 213.2812499999999,
			"seed": 1409250138,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "X830sl7S",
				"focus": 0.7764545118596391,
				"gap": 9.629686031767278
			},
			"endBinding": {
				"elementId": "_O-Oz4FUOFYy2Y92z-rrp",
				"focus": -0.412619267813667,
				"gap": 9.06605982991293
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
					473.2617187499998,
					-213.2812499999999
				]
			]
		},
		{
			"type": "text",
			"version": 50,
			"versionNonce": 1354464402,
			"isDeleted": false,
			"id": "xLRYNnRQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2287.9807982143084,
			"y": 93.51061472232351,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 280,
			"height": 24,
			"seed": 983126170,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "代码有过修改，行号可能不对应",
			"rawText": "代码有过修改，行号可能不对应",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "代码有过修改，行号可能不对应",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 90,
			"versionNonce": 1211485582,
			"isDeleted": false,
			"id": "RAxunm1d",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2289.146162797642,
			"y": 630.9316759202397,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 550.78125,
			"height": 120,
			"seed": 272036358,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "ioZiLBLccTgK7SQ3nSRfw",
					"type": "arrow"
				},
				{
					"id": "vR9johtyPqm_OOETVIOEz",
					"type": "arrow"
				},
				{
					"id": "hyJKBxq17Z-psp5TfaWrb",
					"type": "arrow"
				}
			],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "loadAndCacheTableMeta:666, GmsTableMetaManager \nloadAndCacheTableMeta:641, GmsTableMetaManager \nfetchTableMeta:149, GmsTableMetaManager \nqueryVisibleColumns:193, TableInfoManager \nqueryColumns:222, TableInfoManager ",
			"rawText": "loadAndCacheTableMeta:666, GmsTableMetaManager \nloadAndCacheTableMeta:641, GmsTableMetaManager \nfetchTableMeta:149, GmsTableMetaManager \nqueryVisibleColumns:193, TableInfoManager \nqueryColumns:222, TableInfoManager ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "loadAndCacheTableMeta:666, GmsTableMetaManager \nloadAndCacheTableMeta:641, GmsTableMetaManager \nfetchTableMeta:149, GmsTableMetaManager \nqueryVisibleColumns:193, TableInfoManager \nqueryColumns:222, TableInfoManager ",
			"lineHeight": 1.2,
			"baseline": 116
		},
		{
			"type": "arrow",
			"version": 118,
			"versionNonce": 1493310034,
			"isDeleted": false,
			"id": "ZXMiljnvy5Bem6MzQySU4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2803.8466836309753,
			"y": 1432.819696753573,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 439.81770833333303,
			"height": 2.1223958333332575,
			"seed": 1442355270,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "wW4Mv6D1",
				"focus": 0.09026063357800862,
				"gap": 4.612024880947047
			},
			"endBinding": {
				"elementId": "rHOKmAiF",
				"focus": -0.562715547929769,
				"gap": 9.385370952387348
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
					439.81770833333303,
					-2.1223958333332575
				]
			]
		},
		{
			"type": "text",
			"version": 62,
			"versionNonce": 1132522446,
			"isDeleted": false,
			"id": "WnNpKsYp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3892.7138711309735,
			"y": 328.508987118156,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1441.40625,
			"height": 168,
			"seed": 70050054,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "43wVgzCrHdOlHnd2ICVNd",
					"type": "arrow"
				}
			],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "select \n        `table_schema`, `table_name`, `column_name`, `ordinal_position`, `column_default`, `is_nullable`, `data_type`, \n        `character_maximum_length`, `character_octet_length`, `numeric_precision`, `numeric_scale`, `datetime_precision`, \n        `character_set_name`, `collation_name`, `column_type`, `column_key`, `extra`, `privileges`, `column_comment`, \n        `generation_expression`, `jdbc_type`, `jdbc_type_name`, `field_length`, `version`, `status`, `flag` from `columns` \nwhere `table_schema` = ? and `table_name` = ? \norder by ordinal_position asc",
			"rawText": "select \n        `table_schema`, `table_name`, `column_name`, `ordinal_position`, `column_default`, `is_nullable`, `data_type`, \n        `character_maximum_length`, `character_octet_length`, `numeric_precision`, `numeric_scale`, `datetime_precision`, \n        `character_set_name`, `collation_name`, `column_type`, `column_key`, `extra`, `privileges`, `column_comment`, \n        `generation_expression`, `jdbc_type`, `jdbc_type_name`, `field_length`, `version`, `status`, `flag` from `columns` \nwhere `table_schema` = ? and `table_name` = ? \norder by ordinal_position asc",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "select \n        `table_schema`, `table_name`, `column_name`, `ordinal_position`, `column_default`, `is_nullable`, `data_type`, \n        `character_maximum_length`, `character_octet_length`, `numeric_precision`, `numeric_scale`, `datetime_precision`, \n        `character_set_name`, `collation_name`, `column_type`, `column_key`, `extra`, `privileges`, `column_comment`, \n        `generation_expression`, `jdbc_type`, `jdbc_type_name`, `field_length`, `version`, `status`, `flag` from `columns` \nwhere `table_schema` = ? and `table_name` = ? \norder by ordinal_position asc",
			"lineHeight": 1.2,
			"baseline": 164
		},
		{
			"type": "text",
			"version": 203,
			"versionNonce": 1647247378,
			"isDeleted": false,
			"id": "dH0kUqOl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3209.6409544643057,
			"y": 627.398147274406,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 328.125,
			"height": 96,
			"seed": 2002550406,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "vR9johtyPqm_OOETVIOEz",
					"type": "arrow"
				},
				{
					"id": "hulJQsrcN48p_z0E0NPbM",
					"type": "arrow"
				}
			],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "query:326, ColumnsAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"rawText": "query:326, ColumnsAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "query:326, ColumnsAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 44,
			"versionNonce": 1548632590,
			"isDeleted": false,
			"id": "ioZiLBLccTgK7SQ3nSRfw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2530.5524127976396,
			"y": 476.8008165452377,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.7421875,
			"height": 148.11197916666674,
			"seed": 1973395590,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "AqerqXBa",
				"focus": 0.06306238559456966,
				"gap": 13.390057663685866
			},
			"endBinding": {
				"elementId": "RAxunm1d",
				"focus": -0.11937761360672329,
				"gap": 6.018880208335304
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
					0.7421875,
					148.11197916666674
				]
			]
		},
		{
			"type": "arrow",
			"version": 145,
			"versionNonce": 137965010,
			"isDeleted": false,
			"id": "vR9johtyPqm_OOETVIOEz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2864.859704464306,
			"y": 683.7538302757278,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 331.4739583333335,
			"height": 0.8914001588802876,
			"seed": 28619610,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "RAxunm1d",
				"focus": -0.1048757983606999,
				"gap": 24.93229166666424
			},
			"endBinding": {
				"elementId": "dH0kUqOl",
				"focus": -0.1442429215800108,
				"gap": 13.30729166666606
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
					331.4739583333335,
					-0.8914001588802876
				]
			]
		},
		{
			"type": "text",
			"version": 38,
			"versionNonce": 362205262,
			"isDeleted": false,
			"id": "zm96V68W",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3186.2659544643066,
			"y": 419.13387086071407,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 351.5625,
			"height": 24,
			"seed": 1083139462,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "hulJQsrcN48p_z0E0NPbM",
					"type": "arrow"
				}
			],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "ColumnsAccessor.SELECT_COLUMNS",
			"rawText": "ColumnsAccessor.SELECT_COLUMNS",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ColumnsAccessor.SELECT_COLUMNS",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 31,
			"versionNonce": 1345823634,
			"isDeleted": false,
			"id": "hulJQsrcN48p_z0E0NPbM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3354.0940794643066,
			"y": 451.24324586071407,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.671875,
			"height": 164.953125,
			"seed": 1710007942,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zm96V68W",
				"focus": 0.046371855189735536,
				"gap": 8.109375
			},
			"endBinding": {
				"elementId": "dH0kUqOl",
				"focus": -0.10536352609765598,
				"gap": 11.20177641369196
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
					1.671875,
					164.953125
				]
			]
		},
		{
			"type": "arrow",
			"version": 28,
			"versionNonce": 724801166,
			"isDeleted": false,
			"id": "43wVgzCrHdOlHnd2ICVNd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3534.4065794643066,
			"y": 434.57137086071407,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 347.875,
			"height": 1.03125,
			"seed": 60389594,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939730,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "WnNpKsYp",
				"focus": -0.2932675406829354,
				"gap": 10.43229166666697
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
					347.875,
					1.03125
				]
			]
		},
		{
			"type": "text",
			"version": 49,
			"versionNonce": 73490770,
			"isDeleted": false,
			"id": "PVoQ3Qoe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2307.8440794643066,
			"y": 1012.4082849232141,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 492.1875,
			"height": 72,
			"seed": 695461702,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "hyJKBxq17Z-psp5TfaWrb",
					"type": "arrow"
				},
				{
					"id": "VL-VkuLzmTEjf1MO1s1uN",
					"type": "arrow"
				},
				{
					"id": "-VMYQfu7aLsQQRd7lKcjt",
					"type": "arrow"
				}
			],
			"updated": 1684308939731,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "fetchTableMeta:151, GmsTableMetaManager \nqueryVisibleIndexes:227, TableInfoManager \nqueryIndexes:252, TableInfoManager ",
			"rawText": "fetchTableMeta:151, GmsTableMetaManager \nqueryVisibleIndexes:227, TableInfoManager \nqueryIndexes:252, TableInfoManager ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "fetchTableMeta:151, GmsTableMetaManager \nqueryVisibleIndexes:227, TableInfoManager \nqueryIndexes:252, TableInfoManager ",
			"lineHeight": 1.2,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 15,
			"versionNonce": 1977455822,
			"isDeleted": false,
			"id": "mV0MLAto",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3232.2503294643066,
			"y": 1004.0020349232141,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 328.125,
			"height": 96,
			"seed": 1372535962,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "VL-VkuLzmTEjf1MO1s1uN",
					"type": "arrow"
				},
				{
					"id": "XAj-T1ve87Kf7TP_aVyKY",
					"type": "arrow"
				},
				{
					"id": "fhmjvme8gk-ZW0Rxrmfse",
					"type": "arrow"
				}
			],
			"updated": 1684308939731,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "query:267, IndexesAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"rawText": "query:267, IndexesAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "query:267, IndexesAccessor \nquery:103, AbstractAccessor \nquery:144, AbstractAccessor \nquery:67, MetaDbUtil ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 20,
			"versionNonce": 269313810,
			"isDeleted": false,
			"id": "hyJKBxq17Z-psp5TfaWrb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2547.0628294643066,
			"y": 764.4864099232141,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.9375,
			"height": 239.09375,
			"seed": 1868604102,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939731,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "RAxunm1d",
				"focus": 0.0644437671478133,
				"gap": 13.554734002974328
			},
			"endBinding": {
				"elementId": "PVoQ3Qoe",
				"focus": -0.023399307818200803,
				"gap": 8.828125
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
					0.9375,
					239.09375
				]
			]
		},
		{
			"type": "arrow",
			"version": 70,
			"versionNonce": 1328401166,
			"isDeleted": false,
			"id": "VL-VkuLzmTEjf1MO1s1uN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2803.5628294643066,
			"y": 1059.4314079029261,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 408.921875,
			"height": 6.037237715778019,
			"seed": 1644968986,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939731,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PVoQ3Qoe",
				"focus": 0.39213490434671183,
				"gap": 3.53125
			},
			"endBinding": {
				"elementId": "mV0MLAto",
				"focus": 0.026215941235301674,
				"gap": 19.765625
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
					408.921875,
					-6.037237715778019
				]
			]
		},
		{
			"type": "text",
			"version": 29,
			"versionNonce": 1538438354,
			"isDeleted": false,
			"id": "Fix16iuL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3919.6878294643066,
			"y": 777.3770349232141,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1476.5625,
			"height": 192,
			"seed": 1147561050,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "IQ8KHIuWbJe4o3l1f40MJ",
					"type": "arrow"
				}
			],
			"updated": 1684308939731,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "select \n        `table_schema`, `table_name`, `non_unique`, `index_schema`, `index_name`, `seq_in_index`, `column_name`, `collation`, \n        `cardinality`, `sub_part`, `packed`, `nullable`, `index_type`, `comment`, `index_comment`, `index_column_type`, \n        `index_location`, `index_table_name`, `index_status`, `version`, `flag` \nfrom \n        `indexes` \nwhere `table_schema` = ? and `table_name` = ? \norder by `seq_in_index`",
			"rawText": "select \n        `table_schema`, `table_name`, `non_unique`, `index_schema`, `index_name`, `seq_in_index`, `column_name`, `collation`, \n        `cardinality`, `sub_part`, `packed`, `nullable`, `index_type`, `comment`, `index_comment`, `index_column_type`, \n        `index_location`, `index_table_name`, `index_status`, `version`, `flag` \nfrom \n        `indexes` \nwhere `table_schema` = ? and `table_name` = ? \norder by `seq_in_index`",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "select \n        `table_schema`, `table_name`, `non_unique`, `index_schema`, `index_name`, `seq_in_index`, `column_name`, `collation`, \n        `cardinality`, `sub_part`, `packed`, `nullable`, `index_type`, `comment`, `index_comment`, `index_column_type`, \n        `index_location`, `index_table_name`, `index_status`, `version`, `flag` \nfrom \n        `indexes` \nwhere `table_schema` = ? and `table_name` = ? \norder by `seq_in_index`",
			"lineHeight": 1.2,
			"baseline": 188
		},
		{
			"type": "text",
			"version": 27,
			"versionNonce": 1973238094,
			"isDeleted": false,
			"id": "kByW0vjU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3224.4534544643066,
			"y": 864.5801599232141,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 351.5625,
			"height": 24,
			"seed": 407512774,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "IQ8KHIuWbJe4o3l1f40MJ",
					"type": "arrow"
				}
			],
			"updated": 1684308939731,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "IndexesAccessor.SELECT_INDEXES",
			"rawText": "IndexesAccessor.SELECT_INDEXES",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "IndexesAccessor.SELECT_INDEXES",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 19,
			"versionNonce": 686312082,
			"isDeleted": false,
			"id": "XAj-T1ve87Kf7TP_aVyKY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3370.7503294643066,
			"y": 886.9082849232141,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.265625,
			"height": 116.390625,
			"seed": 1712895046,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939731,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "mV0MLAto",
				"focus": -0.14440781077204315,
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
					1.265625,
					116.390625
				]
			]
		},
		{
			"type": "arrow",
			"version": 34,
			"versionNonce": 1887756174,
			"isDeleted": false,
			"id": "IQ8KHIuWbJe4o3l1f40MJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3584.0472044643066,
			"y": 868.7676599232141,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 322.9375,
			"height": 5.5,
			"seed": 1074374426,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939731,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "kByW0vjU",
				"focus": -0.7298396855668604,
				"gap": 8.03125
			},
			"endBinding": {
				"elementId": "Fix16iuL",
				"focus": -0.12600426002104279,
				"gap": 12.703125
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
					322.9375,
					5.5
				]
			]
		},
		{
			"type": "arrow",
			"version": 49,
			"versionNonce": 1852123218,
			"isDeleted": false,
			"id": "-VMYQfu7aLsQQRd7lKcjt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2524.6331419643084,
			"y": 1098.2940131598234,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.15625,
			"height": 263.296875,
			"seed": 19613394,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939731,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PVoQ3Qoe",
				"focus": 0.11561252963231392,
				"gap": 13.885728236609339
			},
			"endBinding": {
				"elementId": "wW4Mv6D1",
				"focus": -0.19331784048939965,
				"gap": 19.947474888394936
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
					-4.15625,
					263.296875
				]
			]
		},
		{
			"type": "arrow",
			"version": 20,
			"versionNonce": 1948106190,
			"isDeleted": false,
			"id": "fhmjvme8gk-ZW0Rxrmfse",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3387.6800169643084,
			"y": 1117.8408881598234,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 11.546875,
			"height": 271.765625,
			"seed": 1072423822,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684308939731,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "mV0MLAto",
				"focus": 0.06881435067344006,
				"gap": 17.83885323660934
			},
			"endBinding": {
				"elementId": "rHOKmAiF",
				"focus": -0.4853869225261494,
				"gap": 1.375209263394936
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
					11.546875,
					271.765625
				]
			]
		},
		{
			"type": "text",
			"version": 53,
			"versionNonce": 194073746,
			"isDeleted": false,
			"id": "8wza8Q9q",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -671.7485544642627,
			"y": 1167.8523278919681,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 445.3125,
			"height": 72,
			"seed": 1887528654,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "-1VGdbTdK2KJjafoPS6jV",
					"type": "arrow"
				}
			],
			"updated": 1684309207288,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "doFlush:490, OrcWriterTask \nuploadStatFile:658, OrcWriterTask \nstoreExtraFileMeta:776, OrcWriterTask ",
			"rawText": "doFlush:490, OrcWriterTask \nuploadStatFile:658, OrcWriterTask \nstoreExtraFileMeta:776, OrcWriterTask ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "doFlush:490, OrcWriterTask \nuploadStatFile:658, OrcWriterTask \nstoreExtraFileMeta:776, OrcWriterTask ",
			"lineHeight": 1.2,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 57,
			"versionNonce": 1645973842,
			"isDeleted": false,
			"id": "NBodspMp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1023.541624107166,
			"y": 1195.7541136062541,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 58.59375,
			"height": 24,
			"seed": 1828430286,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684309147473,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": ".stat",
			"rawText": ".stat",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": ".stat",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 32,
			"versionNonce": 699640914,
			"isDeleted": false,
			"id": "LND0SmlX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 24.546088392880165,
			"y": 1172.662595749111,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 632.8125,
			"height": 96,
			"seed": 1524142798,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "Jr5IQpun41AFZDtRPmqoL",
					"type": "arrow"
				}
			],
			"updated": 1684309199774,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "addOssFileAndReturnLastInsertId:656, TableMetaChanger \naddOssFileAndReturnLastInsertId:352, TableInfoManager \ninsertAndReturnLastInsertId:192, FilesAccessor \ninsertAndReturnLastInsertId:97, MetaDbUtil ",
			"rawText": "addOssFileAndReturnLastInsertId:656, TableMetaChanger \naddOssFileAndReturnLastInsertId:352, TableInfoManager \ninsertAndReturnLastInsertId:192, FilesAccessor \ninsertAndReturnLastInsertId:97, MetaDbUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "addOssFileAndReturnLastInsertId:656, TableMetaChanger \naddOssFileAndReturnLastInsertId:352, TableInfoManager \ninsertAndReturnLastInsertId:192, FilesAccessor \ninsertAndReturnLastInsertId:97, MetaDbUtil ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "text",
			"version": 30,
			"versionNonce": 2092236046,
			"isDeleted": false,
			"id": "WZGP0nC1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.1525723214056,
			"y": 1433.8567921776826,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 445.3125,
			"height": 24,
			"seed": 727661970,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "CXq4IYxGpiXOnWVoHHT7l",
					"type": "arrow"
				},
				{
					"id": "A0whTlJW0DKenUKQ42Ght",
					"type": "arrow"
				}
			],
			"updated": 1684309534442,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "storeExtraFileMeta:788, OrcWriterTask ",
			"rawText": "storeExtraFileMeta:788, OrcWriterTask ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "storeExtraFileMeta:788, OrcWriterTask ",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 29,
			"versionNonce": 1139714258,
			"isDeleted": false,
			"id": "I9mRoebe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 36.30948125002317,
			"y": 1417.3054528919681,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 421.875,
			"height": 120,
			"seed": 193313618,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "CXq4IYxGpiXOnWVoHHT7l",
					"type": "arrow"
				}
			],
			"updated": 1684309213678,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "changeOssFile:632, TableMetaChanger \nchangeOssFile:638, TableMetaChanger \nchangeOssFile:357, TableInfoManager \nchangeFile:213, FilesAccessor \nupdate:102, MetaDbUtil ",
			"rawText": "changeOssFile:632, TableMetaChanger \nchangeOssFile:638, TableMetaChanger \nchangeOssFile:357, TableInfoManager \nchangeFile:213, FilesAccessor \nupdate:102, MetaDbUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "changeOssFile:632, TableMetaChanger \nchangeOssFile:638, TableMetaChanger \nchangeOssFile:357, TableInfoManager \nchangeFile:213, FilesAccessor \nupdate:102, MetaDbUtil ",
			"lineHeight": 1.2,
			"baseline": 116
		},
		{
			"type": "text",
			"version": 34,
			"versionNonce": 709145490,
			"isDeleted": false,
			"id": "8Jy9XrYz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1006.9902848214518,
			"y": 1452.3724171776826,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 105.46875,
			"height": 24,
			"seed": 98259214,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684309216240,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "file size",
			"rawText": "file size",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "file size",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "arrow",
			"version": 42,
			"versionNonce": 404233102,
			"isDeleted": false,
			"id": "Jr5IQpun41AFZDtRPmqoL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -249.77310803569128,
			"y": 1212.1492028919681,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 265.3236607142858,
			"height": 1.015625,
			"seed": 1123748754,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684309199774,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "LND0SmlX",
				"focus": 0.21894654902092886,
				"gap": 8.995535714285666
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
					265.3236607142858,
					-1.015625
				]
			]
		},
		{
			"type": "arrow",
			"version": 21,
			"versionNonce": 1203539790,
			"isDeleted": false,
			"id": "-1VGdbTdK2KJjafoPS6jV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -451.6369473214056,
			"y": 1246.2786671776823,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.194196428571331,
			"height": 188.03571428571445,
			"seed": 442144974,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684309207288,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "8wza8Q9q",
				"focus": 0.005124377001670491,
				"gap": 6.426339285714221
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
					-6.194196428571331,
					188.03571428571445
				]
			]
		},
		{
			"type": "arrow",
			"version": 43,
			"versionNonce": 244619022,
			"isDeleted": false,
			"id": "CXq4IYxGpiXOnWVoHHT7l",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -223.28873303569128,
			"y": 1446.0554528919681,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 244.75446428571433,
			"height": 0.12276785714288962,
			"seed": 1801253458,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684309213678,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "WZGP0nC1",
				"focus": 0.0069099483473354555,
				"gap": 6.551339285714334
			},
			"endBinding": {
				"elementId": "I9mRoebe",
				"focus": 0.5159897777865822,
				"gap": 14.843750000000114
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
					244.75446428571433,
					0.12276785714288962
				]
			]
		},
		{
			"type": "text",
			"version": 21,
			"versionNonce": 1726733458,
			"isDeleted": false,
			"id": "tjniFRJm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 533.7983205357372,
			"y": 1422.6200455258968,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 375,
			"height": 24,
			"seed": 1039377746,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684309344441,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "FilesAccessor.CHANGE_FILE_RECORD",
			"rawText": "FilesAccessor.CHANGE_FILE_RECORD",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "FilesAccessor.CHANGE_FILE_RECORD",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 4,
			"versionNonce": 2073409614,
			"isDeleted": false,
			"id": "3F3o95es",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -661.4360544642627,
			"y": 1747.5544763294681,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 398.4375,
			"height": 48,
			"seed": 170293842,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "A0whTlJW0DKenUKQ42Ght",
					"type": "arrow"
				},
				{
					"id": "Jk1izuIWJnyE_Eu3kgyXR",
					"type": "arrow"
				}
			],
			"updated": 1684309538931,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "doFlush:493, OrcWriterTask \nupdateFileMeta:515, OrcWriterTask ",
			"rawText": "doFlush:493, OrcWriterTask \nupdateFileMeta:515, OrcWriterTask ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "doFlush:493, OrcWriterTask \nupdateFileMeta:515, OrcWriterTask ",
			"lineHeight": 1.2,
			"baseline": 44
		},
		{
			"type": "text",
			"version": 3,
			"versionNonce": 1091927694,
			"isDeleted": false,
			"id": "KD9VPhix",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 43.619749107165944,
			"y": 1726.661619186611,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 421.875,
			"height": 96,
			"seed": 801595410,
			"groupIds": [],
			"roundness": null,
			"boundElements": [
				{
					"id": "Jk1izuIWJnyE_Eu3kgyXR",
					"type": "arrow"
				}
			],
			"updated": 1684309538931,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "changeOssFile:638, TableMetaChanger \nchangeOssFile:357, TableInfoManager \nchangeFile:213, FilesAccessor \nupdate:102, MetaDbUtil ",
			"rawText": "changeOssFile:638, TableMetaChanger \nchangeOssFile:357, TableInfoManager \nchangeFile:213, FilesAccessor \nupdate:102, MetaDbUtil ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "changeOssFile:638, TableMetaChanger \nchangeOssFile:357, TableInfoManager \nchangeFile:213, FilesAccessor \nupdate:102, MetaDbUtil ",
			"lineHeight": 1.2,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 23,
			"versionNonce": 317694674,
			"isDeleted": false,
			"id": "A0whTlJW0DKenUKQ42Ght",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -449.23739374997695,
			"y": 1472.3089406151823,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 11.41741071428578,
			"height": 271.39508928571445,
			"seed": 1870688334,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684309534443,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "WZGP0nC1",
				"focus": -0.019590122100362144,
				"gap": 14.452148437499773
			},
			"endBinding": {
				"elementId": "3F3o95es",
				"focus": 0.0019520219604793631,
				"gap": 3.850446428571331
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
					-11.41741071428578,
					271.39508928571445
				]
			]
		},
		{
			"type": "arrow",
			"version": 39,
			"versionNonce": 2080062354,
			"isDeleted": false,
			"id": "Jk1izuIWJnyE_Eu3kgyXR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -249.0588223214055,
			"y": 1781.1259049008968,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 281.5513392857142,
			"height": 3.671875,
			"seed": 1197969806,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1684309538931,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "3F3o95es",
				"focus": 0.25533769592398997,
				"gap": 13.939732142857224
			},
			"endBinding": {
				"elementId": "KD9VPhix",
				"focus": -0.25678798062753233,
				"gap": 11.127232142857224
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
					281.5513392857142,
					3.671875
				]
			]
		},
		{
			"type": "text",
			"version": 50,
			"versionNonce": 1298242322,
			"isDeleted": false,
			"id": "eciQsokB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 528.2402848214516,
			"y": 1760.8558156151826,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 375,
			"height": 24,
			"seed": 1039377746,
			"groupIds": [],
			"roundness": null,
			"boundElements": [],
			"updated": 1684309558585,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "FilesAccessor.CHANGE_FILE_RECORD",
			"rawText": "FilesAccessor.CHANGE_FILE_RECORD",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "FilesAccessor.CHANGE_FILE_RECORD",
			"lineHeight": 1.2,
			"baseline": 20
		},
		{
			"id": "Xdda5Hq8",
			"type": "text",
			"x": -704.3936437499771,
			"y": 2116.777411597325,
			"width": 679.6875,
			"height": 192,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 1590271438,
			"version": 23,
			"versionNonce": 1210200658,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "qSABJtYlVIRLMuuDF0Gru",
					"type": "arrow"
				},
				{
					"id": "nxWCc0iL9S3Nh5Ql78ZEy",
					"type": "arrow"
				}
			],
			"updated": 1684310336343,
			"link": null,
			"locked": false,
			"text": "executeTask:562, DdlEngineDagExecutor \nexecute:93, AbstractDdlTask \nexecute:58, DdlEngineAccessorDelegate \ninvoke:69, AbstractDdlTask$1 \ninvoke:74, AbstractDdlTask$1 \nduringTransaction:85, LoadDataFromFileToObjectStorageTask \nexecuteImpl:110, LoadDataFromFileToObjectStorageTask \nloadTable:227, LoadDataFromFileToObjectStorageTask ",
			"rawText": "executeTask:562, DdlEngineDagExecutor \nexecute:93, AbstractDdlTask \nexecute:58, DdlEngineAccessorDelegate \ninvoke:69, AbstractDdlTask$1 \ninvoke:74, AbstractDdlTask$1 \nduringTransaction:85, LoadDataFromFileToObjectStorageTask \nexecuteImpl:110, LoadDataFromFileToObjectStorageTask \nloadTable:227, LoadDataFromFileToObjectStorageTask ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 188,
			"containerId": null,
			"originalText": "executeTask:562, DdlEngineDagExecutor \nexecute:93, AbstractDdlTask \nexecute:58, DdlEngineAccessorDelegate \ninvoke:69, AbstractDdlTask$1 \ninvoke:74, AbstractDdlTask$1 \nduringTransaction:85, LoadDataFromFileToObjectStorageTask \nexecuteImpl:110, LoadDataFromFileToObjectStorageTask \nloadTable:227, LoadDataFromFileToObjectStorageTask ",
			"lineHeight": 1.2
		},
		{
			"id": "srftSfLh",
			"type": "text",
			"x": 161.2871598214516,
			"y": 2127.536340168753,
			"width": 457.03125,
			"height": 120,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 800109582,
			"version": 94,
			"versionNonce": 180816846,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "qSABJtYlVIRLMuuDF0Gru",
					"type": "arrow"
				}
			],
			"updated": 1684310327696,
			"link": null,
			"locked": false,
			"text": "validOssFileMeta:677, TableMetaChanger \nvalidOssFile:389, TableInfoManager \nvalid:361, FilesAccessor \nupdate:102, MetaDbUtil \n",
			"rawText": "validOssFileMeta:677, TableMetaChanger \nvalidOssFile:389, TableInfoManager \nvalid:361, FilesAccessor \nupdate:102, MetaDbUtil \n",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 116,
			"containerId": null,
			"originalText": "validOssFileMeta:677, TableMetaChanger \nvalidOssFile:389, TableInfoManager \nvalid:361, FilesAccessor \nupdate:102, MetaDbUtil \n",
			"lineHeight": 1.2
		},
		{
			"id": "IH6ptNu9",
			"type": "text",
			"x": 886.465731250023,
			"y": 2157.4317084723248,
			"width": 292.96875,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 553734738,
			"version": 79,
			"versionNonce": 520380882,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1684310339279,
			"link": null,
			"locked": false,
			"text": "FilesAccessor.READY_FILES",
			"rawText": "FilesAccessor.READY_FILES",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "FilesAccessor.READY_FILES",
			"lineHeight": 1.2
		},
		{
			"id": "miL2xALs",
			"type": "text",
			"x": -702.9427508928342,
			"y": 2479.898226329468,
			"width": 597.65625,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 1933369170,
			"version": 52,
			"versionNonce": 629938194,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ViPBdYUU3kdMR-EbpYWGE",
					"type": "arrow"
				},
				{
					"id": "nxWCc0iL9S3Nh5Ql78ZEy",
					"type": "arrow"
				}
			],
			"updated": 1684310336343,
			"link": null,
			"locked": false,
			"text": "loadTable:229, LoadDataFromFileToObjectStorageTask ",
			"rawText": "loadTable:229, LoadDataFromFileToObjectStorageTask ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "loadTable:229, LoadDataFromFileToObjectStorageTask ",
			"lineHeight": 1.2
		},
		{
			"id": "Q8k0SUp4",
			"type": "text",
			"x": 182.0014455357374,
			"y": 2456.661619186611,
			"width": 492.1875,
			"height": 96,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 1388913938,
			"version": 12,
			"versionNonce": 1658916622,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ViPBdYUU3kdMR-EbpYWGE",
					"type": "arrow"
				}
			],
			"updated": 1684310333274,
			"link": null,
			"locked": false,
			"text": "validOssColumnMeta:699, TableMetaChanger \nvalidOSSColumnsMeta:405, TableInfoManager \nvalid:163, ColumnMetaAccessor \nupdate:102, MetaDbUtil ",
			"rawText": "validOssColumnMeta:699, TableMetaChanger \nvalidOSSColumnsMeta:405, TableInfoManager \nvalid:163, ColumnMetaAccessor \nupdate:102, MetaDbUtil ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 92,
			"containerId": null,
			"originalText": "validOssColumnMeta:699, TableMetaChanger \nvalidOSSColumnsMeta:405, TableInfoManager \nvalid:163, ColumnMetaAccessor \nupdate:102, MetaDbUtil ",
			"lineHeight": 1.2
		},
		{
			"id": "qSABJtYlVIRLMuuDF0Gru",
			"type": "arrow",
			"x": -10.498554464262725,
			"y": 2206.438404900897,
			"width": 163.4375000000001,
			"height": 2.5669642857146755,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 924732494,
			"version": 27,
			"versionNonce": 682228306,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1684310327696,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					163.4375000000001,
					-2.5669642857146755
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "Xdda5Hq8",
				"focus": -0.0076797154335407096,
				"gap": 14.207589285714334
			},
			"endBinding": {
				"elementId": "srftSfLh",
				"focus": -0.1983814506826629,
				"gap": 8.34821428571422
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "ViPBdYUU3kdMR-EbpYWGE",
			"type": "arrow",
			"x": -95.66596517854839,
			"y": 2500.712958472325,
			"width": 269.4977678571429,
			"height": 0.32366071428577925,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 836427794,
			"version": 40,
			"versionNonce": 2093998866,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1684310333274,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					269.4977678571429,
					0.32366071428577925
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "miL2xALs",
				"focus": 0.6832567611063631,
				"gap": 9.62053571428578
			},
			"endBinding": {
				"elementId": "Q8k0SUp4",
				"focus": 0.06873584041329044,
				"gap": 8.16964285714289
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "nxWCc0iL9S3Nh5Ql78ZEy",
			"type": "arrow",
			"x": -413.92489374997695,
			"y": 2314.395994186611,
			"width": 0.4910714285714448,
			"height": 156.99776785714266,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 46510290,
			"version": 21,
			"versionNonce": 1745769422,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1684310336343,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.4910714285714448,
					156.99776785714266
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "Xdda5Hq8",
				"focus": 0.14422463582829684,
				"gap": 5.618582589285779
			},
			"endBinding": {
				"elementId": "miL2xALs",
				"focus": -0.034682723216586615,
				"gap": 8.50446428571422
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "w8OontoP",
			"type": "text",
			"x": 886.2983205357374,
			"y": 2454.9875120437537,
			"width": 421.875,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 918823566,
			"version": 23,
			"versionNonce": 1400149838,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1684310386154,
			"link": null,
			"locked": false,
			"text": "ColumnMetaAccessor.READY_COLUMN_META",
			"rawText": "ColumnMetaAccessor.READY_COLUMN_META",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "ColumnMetaAccessor.READY_COLUMN_META",
			"lineHeight": 1.2
		},
		{
			"id": "unmSLjOW",
			"type": "text",
			"x": -697.3177508928342,
			"y": 2709.8235890526826,
			"width": 527.34375,
			"height": 168,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 1027460242,
			"version": 3,
			"versionNonce": 955690706,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "xmt-VczoWhylUa_sgrOYp",
					"type": "arrow"
				}
			],
			"updated": 1684310835225,
			"link": null,
			"locked": false,
			"text": "executeTask:562, DdlEngineDagExecutor \nexecute:93, AbstractDdlTask \nexecute:58, DdlEngineAccessorDelegate \ninvoke:69, AbstractDdlTask$1 \ninvoke:74, AbstractDdlTask$1 \nduringTransaction:51, UpdateFileCommitTsTask \nexecuteImpl:84, UpdateFileCommitTsTask ",
			"rawText": "executeTask:562, DdlEngineDagExecutor \nexecute:93, AbstractDdlTask \nexecute:58, DdlEngineAccessorDelegate \ninvoke:69, AbstractDdlTask$1 \ninvoke:74, AbstractDdlTask$1 \nduringTransaction:51, UpdateFileCommitTsTask \nexecuteImpl:84, UpdateFileCommitTsTask ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 164,
			"containerId": null,
			"originalText": "executeTask:562, DdlEngineDagExecutor \nexecute:93, AbstractDdlTask \nexecute:58, DdlEngineAccessorDelegate \ninvoke:69, AbstractDdlTask$1 \ninvoke:74, AbstractDdlTask$1 \nduringTransaction:51, UpdateFileCommitTsTask \nexecuteImpl:84, UpdateFileCommitTsTask ",
			"lineHeight": 1.2
		},
		{
			"id": "SMdddm72",
			"type": "text",
			"x": 179.12198125002317,
			"y": 2780.314660481254,
			"width": 492.1875,
			"height": 72,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 549087826,
			"version": 15,
			"versionNonce": 1872561298,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "xmt-VczoWhylUa_sgrOYp",
					"type": "arrow"
				}
			],
			"updated": 1684310835225,
			"link": null,
			"locked": false,
			"text": "updateFilesCommitTs:340, TableInfoManager \nupdateFilesCommitTs:283, FilesAccessor \ndelete:123, MetaDbUtil ",
			"rawText": "updateFilesCommitTs:340, TableInfoManager \nupdateFilesCommitTs:283, FilesAccessor \ndelete:123, MetaDbUtil ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "updateFilesCommitTs:340, TableInfoManager \nupdateFilesCommitTs:283, FilesAccessor \ndelete:123, MetaDbUtil ",
			"lineHeight": 1.2
		},
		{
			"id": "xmt-VczoWhylUa_sgrOYp",
			"type": "arrow",
			"x": -162.5409651785484,
			"y": 2812.078053338397,
			"width": 327.39955357142867,
			"height": 1.7299107142857792,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": {
				"type": 2
			},
			"seed": 1531251666,
			"version": 41,
			"versionNonce": 2049826638,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1684310835225,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					327.39955357142867,
					1.7299107142857792
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "unmSLjOW",
				"focus": 0.19699466986279687,
				"gap": 7.433035714285779
			},
			"endBinding": {
				"elementId": "SMdddm72",
				"focus": 0.030322103081939673,
				"gap": 14.26339285714289
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "rfhLHAlQ",
			"type": "text",
			"x": 881.7224276785945,
			"y": 2792.613767624111,
			"width": 351.5625,
			"height": 24,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"roundness": null,
			"seed": 1564271566,
			"version": 16,
			"versionNonce": 1758310482,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1684310867969,
			"link": null,
			"locked": false,
			"text": "FilesAccessor.UPDATE_COMMIT_TS",
			"rawText": "FilesAccessor.UPDATE_COMMIT_TS",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 20,
			"containerId": null,
			"originalText": "FilesAccessor.UPDATE_COMMIT_TS",
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
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 3,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 970.7552508928342,
		"scrollY": -1864.0869819098252,
		"zoom": {
			"value": 0.35
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
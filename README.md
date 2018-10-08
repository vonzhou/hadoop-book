

## 5 Hadoop IO

[例5-5 String和Text的区别 P116](StringTextComparisonTest.java)

[例5-6 遍历Text中的字符 P117](TextIterator.java)

[例5-7 实现自定义Writable，例5-8 实现RawComparator P121,例5-9 实现RawComparator比较TextPair的第一个字段 P125](TextPair.java)

[例5-10 写SequenceFile P128](SequenceFileWriteDemo.java)

```
➜  hadoop-book git:(master) ✗ export HADOOP_CLASSPATH=hadoop-examples.jar
➜  hadoop-book git:(master) ✗ hadoop SequenceFileWriteDemo numbers.seq   
18/10/08 16:30:04 INFO zlib.ZlibFactory: Successfully loaded & initialized native-zlib library
18/10/08 16:30:04 INFO compress.CodecPool: Got brand-new compressor [.deflate]
[128]	100	One, two, buckle my shoe
[173]	99	Three, four, shut the door
[220]	98	Five, six, pick up sticks
[264]	97	Seven, eight, lay them straight
[314]	96	Nine, ten, a big fat hen
[359]	95	One, two, buckle my shoe
[404]	94	Three, four, shut the door
[451]	93	Five, six, pick up sticks
[495]	92	Seven, eight, lay them straight
[545]	91	Nine, ten, a big fat hen
[590]	90	One, two, buckle my shoe
[635]	89	Three, four, shut the door
[682]	88	Five, six, pick up sticks
[726]	87	Seven, eight, lay them straight
[776]	86	Nine, ten, a big fat hen
[821]	85	One, two, buckle my shoe
[866]	84	Three, four, shut the door
[913]	83	Five, six, pick up sticks
[957]	82	Seven, eight, lay them straight
[1007]	81	Nine, ten, a big fat hen
[1052]	80	One, two, buckle my shoe
[1097]	79	Three, four, shut the door
[1144]	78	Five, six, pick up sticks
[1188]	77	Seven, eight, lay them straight
[1238]	76	Nine, ten, a big fat hen
[1283]	75	One, two, buckle my shoe
[1328]	74	Three, four, shut the door
[1375]	73	Five, six, pick up sticks
[1419]	72	Seven, eight, lay them straight
[1469]	71	Nine, ten, a big fat hen
[1514]	70	One, two, buckle my shoe
[1559]	69	Three, four, shut the door
[1606]	68	Five, six, pick up sticks
[1650]	67	Seven, eight, lay them straight
[1700]	66	Nine, ten, a big fat hen
[1745]	65	One, two, buckle my shoe
[1790]	64	Three, four, shut the door
[1837]	63	Five, six, pick up sticks
[1881]	62	Seven, eight, lay them straight
[1931]	61	Nine, ten, a big fat hen
[1976]	60	One, two, buckle my shoe
[2021]	59	Three, four, shut the door
[2088]	58	Five, six, pick up sticks
[2132]	57	Seven, eight, lay them straight
[2182]	56	Nine, ten, a big fat hen
[2227]	55	One, two, buckle my shoe
[2272]	54	Three, four, shut the door
[2319]	53	Five, six, pick up sticks
[2363]	52	Seven, eight, lay them straight
[2413]	51	Nine, ten, a big fat hen
[2458]	50	One, two, buckle my shoe
[2503]	49	Three, four, shut the door
[2550]	48	Five, six, pick up sticks
[2594]	47	Seven, eight, lay them straight
[2644]	46	Nine, ten, a big fat hen
[2689]	45	One, two, buckle my shoe
[2734]	44	Three, four, shut the door
[2781]	43	Five, six, pick up sticks
[2825]	42	Seven, eight, lay them straight
[2875]	41	Nine, ten, a big fat hen
[2920]	40	One, two, buckle my shoe
[2965]	39	Three, four, shut the door
[3012]	38	Five, six, pick up sticks
[3056]	37	Seven, eight, lay them straight
[3106]	36	Nine, ten, a big fat hen
[3151]	35	One, two, buckle my shoe
[3196]	34	Three, four, shut the door
[3243]	33	Five, six, pick up sticks
[3287]	32	Seven, eight, lay them straight
[3337]	31	Nine, ten, a big fat hen
[3382]	30	One, two, buckle my shoe
[3427]	29	Three, four, shut the door
[3474]	28	Five, six, pick up sticks
[3518]	27	Seven, eight, lay them straight
[3568]	26	Nine, ten, a big fat hen
[3613]	25	One, two, buckle my shoe
[3658]	24	Three, four, shut the door
[3705]	23	Five, six, pick up sticks
[3749]	22	Seven, eight, lay them straight
[3799]	21	Nine, ten, a big fat hen
[3844]	20	One, two, buckle my shoe
[3889]	19	Three, four, shut the door
[3936]	18	Five, six, pick up sticks
[3980]	17	Seven, eight, lay them straight
[4030]	16	Nine, ten, a big fat hen
[4075]	15	One, two, buckle my shoe
[4140]	14	Three, four, shut the door
[4187]	13	Five, six, pick up sticks
[4231]	12	Seven, eight, lay them straight
[4281]	11	Nine, ten, a big fat hen
[4326]	10	One, two, buckle my shoe
[4371]	9	Three, four, shut the door
[4418]	8	Five, six, pick up sticks
[4462]	7	Seven, eight, lay them straight
[4512]	6	Nine, ten, a big fat hen
[4557]	5	One, two, buckle my shoe
[4602]	4	Three, four, shut the door
[4649]	3	Five, six, pick up sticks
[4693]	2	Seven, eight, lay them straight
[4743]	1	Nine, ten, a big fat hen

➜  hadoop-book git:(master) ✗ hadoop fs -ls                           
Found 6 items
-rw-r--r--   1 storm supergroup    1033751 2018-09-30 11:20 1400-8.txt
drwxr-xr-x   - storm supergroup          0 2018-09-30 10:36 books
-rw-r--r--   1 storm supergroup       4788 2018-10-08 16:30 numbers.seq
drwxr-xr-x   - storm supergroup          0 2018-09-30 16:25 output
-rw-r--r--   1 storm supergroup        119 2018-09-30 10:32 qungle.txt
-rw-r--r--   1 storm supergroup        168 2018-09-30 16:25 sample.txt.gz
```

[例5-11 读SequenceFile，seek到某个位置，同步点 P130](SequenceFileReadDemo.java)    

```
➜  hadoop-book git:(master) ✗ hadoop    SequenceFileReadDemo    numbers.seq
18/10/08 16:36:40 INFO zlib.ZlibFactory: Successfully loaded & initialized native-zlib library
18/10/08 16:36:40 INFO compress.CodecPool: Got brand-new decompressor [.deflate]
[128]	100	One, two, buckle my shoe
[173]	99	Three, four, shut the door
[220]	98	Five, six, pick up sticks
[264]	97	Seven, eight, lay them straight
[314]	96	Nine, ten, a big fat hen
[359]	95	One, two, buckle my shoe
[404]	94	Three, four, shut the door
[451]	93	Five, six, pick up sticks
[495]	92	Seven, eight, lay them straight
[545]	91	Nine, ten, a big fat hen
[590]	90	One, two, buckle my shoe
[635]	89	Three, four, shut the door
[682]	88	Five, six, pick up sticks
[726]	87	Seven, eight, lay them straight
[776]	86	Nine, ten, a big fat hen
[821]	85	One, two, buckle my shoe
[866]	84	Three, four, shut the door
[913]	83	Five, six, pick up sticks
[957]	82	Seven, eight, lay them straight
[1007]	81	Nine, ten, a big fat hen
[1052]	80	One, two, buckle my shoe
[1097]	79	Three, four, shut the door
[1144]	78	Five, six, pick up sticks
[1188]	77	Seven, eight, lay them straight
[1238]	76	Nine, ten, a big fat hen
[1283]	75	One, two, buckle my shoe
[1328]	74	Three, four, shut the door
[1375]	73	Five, six, pick up sticks
[1419]	72	Seven, eight, lay them straight
[1469]	71	Nine, ten, a big fat hen
[1514]	70	One, two, buckle my shoe
[1559]	69	Three, four, shut the door
[1606]	68	Five, six, pick up sticks
[1650]	67	Seven, eight, lay them straight
[1700]	66	Nine, ten, a big fat hen
[1745]	65	One, two, buckle my shoe
[1790]	64	Three, four, shut the door
[1837]	63	Five, six, pick up sticks
[1881]	62	Seven, eight, lay them straight
[1931]	61	Nine, ten, a big fat hen
[1976]	60	One, two, buckle my shoe
[2021*]	59	Three, four, shut the door
[2088]	58	Five, six, pick up sticks
[2132]	57	Seven, eight, lay them straight
[2182]	56	Nine, ten, a big fat hen
[2227]	55	One, two, buckle my shoe
[2272]	54	Three, four, shut the door
[2319]	53	Five, six, pick up sticks
[2363]	52	Seven, eight, lay them straight
[2413]	51	Nine, ten, a big fat hen
[2458]	50	One, two, buckle my shoe
[2503]	49	Three, four, shut the door
[2550]	48	Five, six, pick up sticks
[2594]	47	Seven, eight, lay them straight
[2644]	46	Nine, ten, a big fat hen
[2689]	45	One, two, buckle my shoe
[2734]	44	Three, four, shut the door
[2781]	43	Five, six, pick up sticks
[2825]	42	Seven, eight, lay them straight
[2875]	41	Nine, ten, a big fat hen
[2920]	40	One, two, buckle my shoe
[2965]	39	Three, four, shut the door
[3012]	38	Five, six, pick up sticks
[3056]	37	Seven, eight, lay them straight
[3106]	36	Nine, ten, a big fat hen
[3151]	35	One, two, buckle my shoe
[3196]	34	Three, four, shut the door
[3243]	33	Five, six, pick up sticks
[3287]	32	Seven, eight, lay them straight
[3337]	31	Nine, ten, a big fat hen
[3382]	30	One, two, buckle my shoe
[3427]	29	Three, four, shut the door
[3474]	28	Five, six, pick up sticks
[3518]	27	Seven, eight, lay them straight
[3568]	26	Nine, ten, a big fat hen
[3613]	25	One, two, buckle my shoe
[3658]	24	Three, four, shut the door
[3705]	23	Five, six, pick up sticks
[3749]	22	Seven, eight, lay them straight
[3799]	21	Nine, ten, a big fat hen
[3844]	20	One, two, buckle my shoe
[3889]	19	Three, four, shut the door
[3936]	18	Five, six, pick up sticks
[3980]	17	Seven, eight, lay them straight
[4030]	16	Nine, ten, a big fat hen
[4075*]	15	One, two, buckle my shoe
[4140]	14	Three, four, shut the door
[4187]	13	Five, six, pick up sticks
[4231]	12	Seven, eight, lay them straight
[4281]	11	Nine, ten, a big fat hen
[4326]	10	One, two, buckle my shoe
[4371]	9	Three, four, shut the door
[4418]	8	Five, six, pick up sticks
[4462]	7	Seven, eight, lay them straight
[4512]	6	Nine, ten, a big fat hen
[4557]	5	One, two, buckle my shoe
[4602]	4	Three, four, shut the door
[4649]	3	Five, six, pick up sticks
[4693]	2	Seven, eight, lay them straight
[4743]	1	Nine, ten, a big fat hen
➜  hadoop-book git:(master) ✗ hadoop    SequenceFileReadDemo qungle.txt    
Exception in thread "main" java.io.IOException: hdfs://localhost/user/storm/qungle.txt not a SequenceFile
	at org.apache.hadoop.io.SequenceFile$Reader.init(SequenceFile.java:1939)
	at org.apache.hadoop.io.SequenceFile$Reader.initialize(SequenceFile.java:1892)
	at org.apache.hadoop.io.SequenceFile$Reader.<init>(SequenceFile.java:1841)
	at org.apache.hadoop.io.SequenceFile$Reader.<init>(SequenceFile.java:1855)
	at SequenceFileReadDemo.main(SequenceFileReadDemo.java:24)
```

命令行查看Sequnce文件：

```
➜  hadoop-book git:(master) ✗ hadoop fs -text numbers.seq | head       
18/10/08 16:43:49 INFO zlib.ZlibFactory: Successfully loaded & initialized native-zlib library
18/10/08 16:43:49 INFO compress.CodecPool: Got brand-new decompressor [.deflate]
100 One, two, buckle my shoe
99  Three, four, shut the door
98  Five, six, pick up sticks
97  Seven, eight, lay them straight
96  Nine, ten, a big fat hen
95  One, two, buckle my shoe
94  Three, four, shut the door
93  Five, six, pick up sticks
92  Seven, eight, lay them straight
91  Nine, ten, a big fat hen
```

使用hadoop自带的sort例子来排序Sequnce文件：

```
➜  hadoop-book git:(master) ✗ echo $HADOOP_HOME
/home/storm/dev/hadoop-2.8.5
➜  hadoop-book git:(master) ✗ hadoop jar  $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-2.8.5.jar sort -r 1 -inFormat org.apache.hadoop.mapreduce.lib.input.SequenceFileInputFormat \
>       -outFormat      org.apache.hadoop.mapreduce.lib.output.SequenceFileOutputFormat \
> -outKey       org.apache.hadoop.io.IntWritable        \
                -outValue       org.apache.hadoop.io.Text       \
                numbers.seq     sorted
18/10/08 16:49:32 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
18/10/08 16:49:32 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
Running on 1 nodes to sort from hdfs://localhost/user/storm/numbers.seq into hdfs://localhost/user/storm/sorted with 1 reduces.
Job started: Mon Oct 08 16:49:32 CST 2018
18/10/08 16:49:32 INFO jvm.JvmMetrics: Cannot initialize JVM Metrics with processName=JobTracker, sessionId= - already initialized
18/10/08 16:49:33 INFO input.FileInputFormat: Total input files to process : 1
18/10/08 16:49:33 INFO mapreduce.JobSubmitter: number of splits:1
18/10/08 16:49:33 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local1252114274_0001
18/10/08 16:49:34 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
18/10/08 16:49:34 INFO mapreduce.Job: Running job: job_local1252114274_0001
18/10/08 16:49:34 INFO mapred.LocalJobRunner: OutputCommitter set in config null
18/10/08 16:49:34 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 16:49:34 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 16:49:34 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
18/10/08 16:49:34 INFO mapred.LocalJobRunner: Waiting for map tasks
18/10/08 16:49:34 INFO mapred.LocalJobRunner: Starting task: attempt_local1252114274_0001_m_000000_0
18/10/08 16:49:34 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 16:49:34 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 16:49:34 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 16:49:34 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/numbers.seq:0+4788
18/10/08 16:49:34 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 16:49:34 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 16:49:34 INFO mapred.MapTask: soft limit at 83886080
18/10/08 16:49:34 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 16:49:34 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 16:49:34 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 16:49:34 INFO zlib.ZlibFactory: Successfully loaded & initialized native-zlib library
18/10/08 16:49:34 INFO compress.CodecPool: Got brand-new decompressor [.deflate]
18/10/08 16:49:34 INFO mapred.LocalJobRunner: 
18/10/08 16:49:34 INFO mapred.MapTask: Starting flush of map output
18/10/08 16:49:34 INFO mapred.MapTask: Spilling map output
18/10/08 16:49:34 INFO mapred.MapTask: bufstart = 0; bufend = 3100; bufvoid = 104857600
18/10/08 16:49:34 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214000(104856000); length = 397/6553600
18/10/08 16:49:34 INFO mapred.MapTask: Finished spill 0
18/10/08 16:49:34 INFO mapred.Task: Task:attempt_local1252114274_0001_m_000000_0 is done. And is in the process of committing
18/10/08 16:49:34 INFO mapred.LocalJobRunner: map
18/10/08 16:49:34 INFO mapred.Task: Task 'attempt_local1252114274_0001_m_000000_0' done.
18/10/08 16:49:34 INFO mapred.Task: Final Counters for attempt_local1252114274_0001_m_000000_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=302089
        FILE: Number of bytes written=678181
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=4788
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=6
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=100
        Map output records=100
        Map output bytes=3100
        Map output materialized bytes=3306
        Input split bytes=104
        Combine input records=0
        Spilled Records=100
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=345505792
    File Input Format Counters 
        Bytes Read=4788
18/10/08 16:49:34 INFO mapred.LocalJobRunner: Finishing task: attempt_local1252114274_0001_m_000000_0
18/10/08 16:49:34 INFO mapred.LocalJobRunner: map task executor complete.
18/10/08 16:49:34 INFO mapred.LocalJobRunner: Waiting for reduce tasks
18/10/08 16:49:34 INFO mapred.LocalJobRunner: Starting task: attempt_local1252114274_0001_r_000000_0
18/10/08 16:49:34 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 16:49:34 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 16:49:34 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 16:49:34 INFO mapred.ReduceTask: Using ShuffleConsumerPlugin: org.apache.hadoop.mapreduce.task.reduce.Shuffle@543f76cd
18/10/08 16:49:34 INFO reduce.MergeManagerImpl: MergerManager: memoryLimit=334338464, maxSingleShuffleLimit=83584616, mergeThreshold=220663392, ioSortFactor=10, memToMemMergeOutputsThreshold=10
18/10/08 16:49:34 INFO reduce.EventFetcher: attempt_local1252114274_0001_r_000000_0 Thread started: EventFetcher for fetching Map Completion Events
18/10/08 16:49:34 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1252114274_0001_m_000000_0 decomp: 3302 len: 3306 to MEMORY
18/10/08 16:49:34 INFO reduce.InMemoryMapOutput: Read 3302 bytes from map-output for attempt_local1252114274_0001_m_000000_0
18/10/08 16:49:34 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3302, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->3302
18/10/08 16:49:34 INFO reduce.EventFetcher: EventFetcher is interrupted.. Returning
18/10/08 16:49:34 INFO mapred.LocalJobRunner: 1 / 1 copied.
18/10/08 16:49:34 INFO reduce.MergeManagerImpl: finalMerge called with 1 in-memory map-outputs and 0 on-disk map-outputs
18/10/08 16:49:34 INFO mapred.Merger: Merging 1 sorted segments
18/10/08 16:49:34 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 3296 bytes
18/10/08 16:49:34 INFO reduce.MergeManagerImpl: Merged 1 segments, 3302 bytes to disk to satisfy reduce memory limit
18/10/08 16:49:34 INFO reduce.MergeManagerImpl: Merging 1 files, 3306 bytes from disk
18/10/08 16:49:34 WARN io.ReadaheadPool: Failed readahead on ifile
EBADF: Bad file descriptor
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posix_fadvise(Native Method)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posixFadviseIfPossible(NativeIO.java:267)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX$CacheManipulator.posixFadviseIfPossible(NativeIO.java:146)
    at org.apache.hadoop.io.ReadaheadPool$ReadaheadRequestImpl.run(ReadaheadPool.java:208)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
    at java.lang.Thread.run(Thread.java:748)
18/10/08 16:49:34 INFO reduce.MergeManagerImpl: Merging 0 segments, 0 bytes from memory into reduce
18/10/08 16:49:34 INFO mapred.Merger: Merging 1 sorted segments
18/10/08 16:49:34 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 3296 bytes
18/10/08 16:49:34 INFO mapred.LocalJobRunner: 1 / 1 copied.
18/10/08 16:49:34 INFO Configuration.deprecation: mapred.skip.on is deprecated. Instead, use mapreduce.job.skiprecords
18/10/08 16:49:34 INFO mapred.Task: Task:attempt_local1252114274_0001_r_000000_0 is done. And is in the process of committing
18/10/08 16:49:34 INFO mapred.LocalJobRunner: 1 / 1 copied.
18/10/08 16:49:34 INFO mapred.Task: Task attempt_local1252114274_0001_r_000000_0 is allowed to commit now
18/10/08 16:49:34 INFO output.FileOutputCommitter: Saved output of task 'attempt_local1252114274_0001_r_000000_0' to hdfs://localhost/user/storm/sorted/_temporary/0/task_local1252114274_0001_r_000000
18/10/08 16:49:34 INFO mapred.LocalJobRunner: reduce > reduce
18/10/08 16:49:34 INFO mapred.Task: Task 'attempt_local1252114274_0001_r_000000_0' done.
18/10/08 16:49:34 INFO mapred.Task: Final Counters for attempt_local1252114274_0001_r_000000_0: Counters: 29
    File System Counters
        FILE: Number of bytes read=308733
        FILE: Number of bytes written=681487
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=4788
        HDFS: Number of bytes written=4005
        HDFS: Number of read operations=9
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=3
    Map-Reduce Framework
        Combine input records=0
        Combine output records=0
        Reduce input groups=100
        Reduce shuffle bytes=3306
        Reduce input records=100
        Reduce output records=100
        Spilled Records=100
        Shuffled Maps =1
        Failed Shuffles=0
        Merged Map outputs=1
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=345505792
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Output Format Counters 
        Bytes Written=4005
18/10/08 16:49:34 INFO mapred.LocalJobRunner: Finishing task: attempt_local1252114274_0001_r_000000_0
18/10/08 16:49:34 INFO mapred.LocalJobRunner: reduce task executor complete.
18/10/08 16:49:35 INFO mapreduce.Job: Job job_local1252114274_0001 running in uber mode : false
18/10/08 16:49:35 INFO mapreduce.Job:  map 100% reduce 100%
18/10/08 16:49:36 INFO mapreduce.Job: Job job_local1252114274_0001 completed successfully
18/10/08 16:49:36 INFO mapreduce.Job: Counters: 35
    File System Counters
        FILE: Number of bytes read=610822
        FILE: Number of bytes written=1359668
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=9576
        HDFS: Number of bytes written=4005
        HDFS: Number of read operations=15
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=4
    Map-Reduce Framework
        Map input records=100
        Map output records=100
        Map output bytes=3100
        Map output materialized bytes=3306
        Input split bytes=104
        Combine input records=0
        Combine output records=0
        Reduce input groups=100
        Reduce shuffle bytes=3306
        Reduce input records=100
        Reduce output records=100
        Spilled Records=200
        Shuffled Maps =1
        Failed Shuffles=0
        Merged Map outputs=1
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=691011584
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Input Format Counters 
        Bytes Read=4788
    File Output Format Counters 
        Bytes Written=4005
Job ended: Mon Oct 08 16:49:36 CST 2018
The job took 3 seconds.
➜  hadoop-book git:(master) ✗ hadoop fs -ls 
Found 7 items
-rw-r--r--   1 storm supergroup    1033751 2018-09-30 11:20 1400-8.txt
drwxr-xr-x   - storm supergroup          0 2018-09-30 10:36 books
-rw-r--r--   1 storm supergroup       4788 2018-10-08 16:30 numbers.seq
drwxr-xr-x   - storm supergroup          0 2018-09-30 16:25 output
-rw-r--r--   1 storm supergroup        119 2018-09-30 10:32 qungle.txt
-rw-r--r--   1 storm supergroup        168 2018-09-30 16:25 sample.txt.gz
drwxr-xr-x   - storm supergroup          0 2018-10-08 16:49 sorted
➜  hadoop-book git:(master) ✗ hadoop fs -text sorted/part-r-00000 | head
1   Nine, ten, a big fat hen
2   Seven, eight, lay them straight
3   Five, six, pick up sticks
4   Three, four, shut the door
5   One, two, buckle my shoe
6   Nine, ten, a big fat hen
7   Seven, eight, lay them straight
8   Five, six, pick up sticks
9   Three, four, shut the door
10  One, two, buckle my shoe
```

---

第二部分  MapReduce

## 6. 开发一个MR应用

-conf 指定配置文件，运行伪分布式模式：

```
➜  hadoop-book git:(master) ✗ hadoop    fs      -conf   conf/hadoop-localhost.xml       -ls      
Found 7 items
-rw-r--r--   1 storm supergroup    1033751 2018-09-30 11:20 1400-8.txt
drwxr-xr-x   - storm supergroup          0 2018-09-30 10:36 books
-rw-r--r--   1 storm supergroup       4788 2018-10-08 16:30 numbers.seq
drwxr-xr-x   - storm supergroup          0 2018-09-30 16:25 output
-rw-r--r--   1 storm supergroup        119 2018-09-30 10:32 qungle.txt
-rw-r--r--   1 storm supergroup        168 2018-09-30 16:25 sample.txt.gz
drwxr-xr-x   - storm supergroup          0 2018-10-08 16:49 sorted
➜  hadoop-book git:(master) ✗ hadoop    fs      -conf   conf/hadoop-local.xml   -ls     | head
Found 47 items
-rw-r--r--   1 storm storm      16384 2018-10-08 17:04 .README.md.swp
drwxrwxr-x   - storm storm       4096 2018-10-08 17:05 .git
-rw-rw-r--   1 storm storm        140 2018-09-29 10:50 .gitignore
drwxrwxr-x   - storm storm       4096 2018-10-08 17:01 .idea
-rw-rw-r--   1 storm storm   21709965 2018-10-08 16:06 Hadoop- The Definitive Guide, 4th Edition.pdf
-rw-rw-r--   1 storm storm      23424 2018-10-08 16:51 README.md
drwxrwxr-x   - storm storm       4096 2018-09-29 10:50 appc
-rw-rw-r--   1 storm storm    6030082 2018-09-30 10:58 avro-examples.jar
drwxrwxr-x   - storm storm       4096 2018-09-29 11:31 book
```


[例6-4 实现Tool接口打印配置属性 P149](ConfigurationPrinter.java)

```
➜  hadoop-book git:(master) ✗ hadoop    ConfigurationPrinter    -conf   conf/hadoop-localhost.xml       \
                |       grep    yarn.resourcemanager.address=
yarn.resourcemanager.address=localhost:8032
➜  hadoop-book git:(master) ✗ hadoop    ConfigurationPrinter    -D      color=yellow    |       grep    color
color=yellow
```

[]()
[]()

[]()
[]()

[]()
[]()


## 7. MR是如何工作的

## 8. MR类型和格式

## 9. MR 特性

----


第三部分 Hadoop操作			



[]()
[]()
[]()
[]()
[]()

[]()
[]()
[]()
[]()
[]()

[]()
[]()

[]()
[]()

[]()

[]()
[]()
[]()

[]()


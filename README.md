## 2 MapReduce

例2-2 bash脚本找最高温度

```
➜  ncdc git:(master) ✗ ../../ch02-mr-intro/src/main/awk/max_temperature.sh
1901	317
1902	244
```

例2-3,2-4,2-5 Java MapReduce应用找最高温度

```
➜  hadoop-book git:(master) ✗ mvn -DskipTests=true clean compile package                            
➜  hadoop-book git:(master) ✗ export HADOOP_CLASSPATH=hadoop-examples.jar        
➜  hadoop-book git:(master) ✗ hadoop  MaxTemperature input/ncdc/sample.txt output
18/09/29 13:55:58 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
18/09/29 13:55:58 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
18/09/29 13:55:58 WARN mapreduce.JobResourceUploader: Hadoop command-line option parsing not performed. Implement the Tool interface and execute your application with ToolRunner to remedy this.
18/09/29 13:55:59 INFO input.FileInputFormat: Total input files to process : 1
18/09/29 13:55:59 INFO mapreduce.JobSubmitter: number of splits:1
18/09/29 13:55:59 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local524180858_0001
18/09/29 13:55:59 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
18/09/29 13:55:59 INFO mapreduce.Job: Running job: job_local524180858_0001
18/09/29 13:55:59 INFO mapred.LocalJobRunner: OutputCommitter set in config null
18/09/29 13:55:59 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/09/29 13:55:59 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/09/29 13:55:59 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
18/09/29 13:55:59 INFO mapred.LocalJobRunner: Waiting for map tasks
18/09/29 13:55:59 INFO mapred.LocalJobRunner: Starting task: attempt_local524180858_0001_m_000000_0
18/09/29 13:55:59 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/09/29 13:55:59 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/09/29 13:55:59 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/09/29 13:55:59 INFO mapred.MapTask: Processing split: file:/home/storm/GitHub/hadoop-book/input/ncdc/sample.txt:0+529
18/09/29 13:55:59 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/09/29 13:55:59 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/09/29 13:55:59 INFO mapred.MapTask: soft limit at 83886080
18/09/29 13:55:59 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/09/29 13:55:59 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/09/29 13:55:59 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/09/29 13:55:59 INFO mapred.LocalJobRunner: 
18/09/29 13:55:59 INFO mapred.MapTask: Starting flush of map output
18/09/29 13:55:59 INFO mapred.MapTask: Spilling map output
18/09/29 13:55:59 INFO mapred.MapTask: bufstart = 0; bufend = 45; bufvoid = 104857600
18/09/29 13:55:59 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214380(104857520); length = 17/6553600
18/09/29 13:55:59 INFO mapred.MapTask: Finished spill 0
18/09/29 13:55:59 INFO mapred.Task: Task:attempt_local524180858_0001_m_000000_0 is done. And is in the process of committing
18/09/29 13:55:59 INFO mapred.LocalJobRunner: map
18/09/29 13:55:59 INFO mapred.Task: Task 'attempt_local524180858_0001_m_000000_0' done.
18/09/29 13:55:59 INFO mapred.Task: Final Counters for attempt_local524180858_0001_m_000000_0: Counters: 17
	File System Counters
		FILE: Number of bytes read=187139
		FILE: Number of bytes written=554839
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
	Map-Reduce Framework
		Map input records=5
		Map output records=5
		Map output bytes=45
		Map output materialized bytes=61
		Input split bytes=122
		Combine input records=0
		Spilled Records=5
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=0
		Total committed heap usage (bytes)=315097088
	File Input Format Counters 
		Bytes Read=529
18/09/29 13:55:59 INFO mapred.LocalJobRunner: Finishing task: attempt_local524180858_0001_m_000000_0
18/09/29 13:55:59 INFO mapred.LocalJobRunner: map task executor complete.
18/09/29 13:55:59 INFO mapred.LocalJobRunner: Waiting for reduce tasks
18/09/29 13:55:59 INFO mapred.LocalJobRunner: Starting task: attempt_local524180858_0001_r_000000_0
18/09/29 13:55:59 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/09/29 13:55:59 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/09/29 13:55:59 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/09/29 13:55:59 INFO mapred.ReduceTask: Using ShuffleConsumerPlugin: org.apache.hadoop.mapreduce.task.reduce.Shuffle@443063ec
18/09/29 13:55:59 INFO reduce.MergeManagerImpl: MergerManager: memoryLimit=334338464, maxSingleShuffleLimit=83584616, mergeThreshold=220663392, ioSortFactor=10, memToMemMergeOutputsThreshold=10
18/09/29 13:55:59 INFO reduce.EventFetcher: attempt_local524180858_0001_r_000000_0 Thread started: EventFetcher for fetching Map Completion Events
18/09/29 13:55:59 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local524180858_0001_m_000000_0 decomp: 57 len: 61 to MEMORY
18/09/29 13:55:59 INFO reduce.InMemoryMapOutput: Read 57 bytes from map-output for attempt_local524180858_0001_m_000000_0
18/09/29 13:55:59 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 57, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->57
18/09/29 13:55:59 WARN io.ReadaheadPool: Failed readahead on ifile
EBADF: Bad file descriptor
	at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posix_fadvise(Native Method)
	at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posixFadviseIfPossible(NativeIO.java:267)
	at org.apache.hadoop.io.nativeio.NativeIO$POSIX$CacheManipulator.posixFadviseIfPossible(NativeIO.java:146)
	at org.apache.hadoop.io.ReadaheadPool$ReadaheadRequestImpl.run(ReadaheadPool.java:208)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)
18/09/29 13:55:59 INFO reduce.EventFetcher: EventFetcher is interrupted.. Returning
18/09/29 13:55:59 INFO mapred.LocalJobRunner: 1 / 1 copied.
18/09/29 13:55:59 INFO reduce.MergeManagerImpl: finalMerge called with 1 in-memory map-outputs and 0 on-disk map-outputs
18/09/29 13:55:59 INFO mapred.Merger: Merging 1 sorted segments
18/09/29 13:55:59 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 50 bytes
18/09/29 13:55:59 INFO reduce.MergeManagerImpl: Merged 1 segments, 57 bytes to disk to satisfy reduce memory limit
18/09/29 13:55:59 INFO reduce.MergeManagerImpl: Merging 1 files, 61 bytes from disk
18/09/29 13:55:59 INFO reduce.MergeManagerImpl: Merging 0 segments, 0 bytes from memory into reduce
18/09/29 13:55:59 INFO mapred.Merger: Merging 1 sorted segments
18/09/29 13:55:59 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 50 bytes
18/09/29 13:55:59 INFO mapred.LocalJobRunner: 1 / 1 copied.
18/09/29 13:55:59 INFO Configuration.deprecation: mapred.skip.on is deprecated. Instead, use mapreduce.job.skiprecords
18/09/29 13:55:59 INFO mapred.Task: Task:attempt_local524180858_0001_r_000000_0 is done. And is in the process of committing
18/09/29 13:55:59 INFO mapred.LocalJobRunner: 1 / 1 copied.
18/09/29 13:55:59 INFO mapred.Task: Task attempt_local524180858_0001_r_000000_0 is allowed to commit now
18/09/29 13:55:59 INFO output.FileOutputCommitter: Saved output of task 'attempt_local524180858_0001_r_000000_0' to file:/home/storm/GitHub/hadoop-book/output/_temporary/0/task_local524180858_0001_r_000000
18/09/29 13:55:59 INFO mapred.LocalJobRunner: reduce > reduce
18/09/29 13:55:59 INFO mapred.Task: Task 'attempt_local524180858_0001_r_000000_0' done.
18/09/29 13:55:59 INFO mapred.Task: Final Counters for attempt_local524180858_0001_r_000000_0: Counters: 24
	File System Counters
		FILE: Number of bytes read=187293
		FILE: Number of bytes written=554929
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
	Map-Reduce Framework
		Combine input records=0
		Combine output records=0
		Reduce input groups=2
		Reduce shuffle bytes=61
		Reduce input records=5
		Reduce output records=2
		Spilled Records=5
		Shuffled Maps =1
		Failed Shuffles=0
		Merged Map outputs=1
		GC time elapsed (ms)=0
		Total committed heap usage (bytes)=315097088
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Output Format Counters 
		Bytes Written=29
18/09/29 13:55:59 INFO mapred.LocalJobRunner: Finishing task: attempt_local524180858_0001_r_000000_0
18/09/29 13:55:59 INFO mapred.LocalJobRunner: reduce task executor complete.
18/09/29 13:56:00 INFO mapreduce.Job: Job job_local524180858_0001 running in uber mode : false
18/09/29 13:56:00 INFO mapreduce.Job:  map 100% reduce 100%
18/09/29 13:56:00 INFO mapreduce.Job: Job job_local524180858_0001 completed successfully
18/09/29 13:56:00 INFO mapreduce.Job: Counters: 30
	File System Counters
		FILE: Number of bytes read=374432
		FILE: Number of bytes written=1109768
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
	Map-Reduce Framework
		Map input records=5
		Map output records=5
		Map output bytes=45
		Map output materialized bytes=61
		Input split bytes=122
		Combine input records=0
		Combine output records=0
		Reduce input groups=2
		Reduce shuffle bytes=61
		Reduce input records=5
		Reduce output records=2
		Spilled Records=10
		Shuffled Maps =1
		Failed Shuffles=0
		Merged Map outputs=1
		GC time elapsed (ms)=0
		Total committed heap usage (bytes)=630194176
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=529
	File Output Format Counters 
		Bytes Written=29
➜  hadoop-book git:(master) ✗ ls -alh output 
total 20K
drwxrwxr-x  2 storm storm 4.0K Sep 29 13:55 .
drwxrwxr-x 32 storm storm 4.0K Sep 29 13:55 ..
-rw-r--r--  1 storm storm   17 Sep 29 13:55 part-r-00000
-rw-r--r--  1 storm storm   12 Sep 29 13:55 .part-r-00000.crc
-rw-r--r--  1 storm storm    0 Sep 29 13:55 _SUCCESS
-rw-r--r--  1 storm storm    8 Sep 29 13:55 ._SUCCESS.crc
➜  hadoop-book git:(master) ✗ cat output/part-r-00000 
1949	111
1950	22
```

例2-6 设置一个 Combiner

```
➜  hadoop-book git:(master) ✗ hadoop  MaxTemperatureWithCombiner input/ncdc/sample.txt output
18/09/29 15:40:47 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
18/09/29 15:40:47 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
18/09/29 15:40:47 WARN mapreduce.JobResourceUploader: Hadoop command-line option parsing not performed. Implement the Tool interface and execute your application with ToolRunner to remedy this.
18/09/29 15:40:47 INFO input.FileInputFormat: Total input files to process : 1
18/09/29 15:40:47 INFO mapreduce.JobSubmitter: number of splits:1
18/09/29 15:40:47 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local1796500479_0001
18/09/29 15:40:47 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
18/09/29 15:40:47 INFO mapreduce.Job: Running job: job_local1796500479_0001
18/09/29 15:40:47 INFO mapred.LocalJobRunner: OutputCommitter set in config null
18/09/29 15:40:47 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/09/29 15:40:47 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/09/29 15:40:47 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
18/09/29 15:40:48 INFO mapred.LocalJobRunner: Waiting for map tasks
18/09/29 15:40:48 INFO mapred.LocalJobRunner: Starting task: attempt_local1796500479_0001_m_000000_0
18/09/29 15:40:48 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/09/29 15:40:48 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/09/29 15:40:48 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/09/29 15:40:48 INFO mapred.MapTask: Processing split: file:/home/storm/GitHub/hadoop-book/input/ncdc/sample.txt:0+529
18/09/29 15:40:48 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/09/29 15:40:48 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/09/29 15:40:48 INFO mapred.MapTask: soft limit at 83886080
18/09/29 15:40:48 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/09/29 15:40:48 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/09/29 15:40:48 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/09/29 15:40:48 INFO mapred.LocalJobRunner: 
18/09/29 15:40:48 INFO mapred.MapTask: Starting flush of map output
18/09/29 15:40:48 INFO mapred.MapTask: Spilling map output
18/09/29 15:40:48 INFO mapred.MapTask: bufstart = 0; bufend = 45; bufvoid = 104857600
18/09/29 15:40:48 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214380(104857520); length = 17/6553600
18/09/29 15:40:48 INFO mapred.MapTask: Finished spill 0
18/09/29 15:40:48 INFO mapred.Task: Task:attempt_local1796500479_0001_m_000000_0 is done. And is in the process of committing
18/09/29 15:40:48 INFO mapred.LocalJobRunner: map
18/09/29 15:40:48 INFO mapred.Task: Task 'attempt_local1796500479_0001_m_000000_0' done.
18/09/29 15:40:48 INFO mapred.Task: Final Counters for attempt_local1796500479_0001_m_000000_0: Counters: 18
	File System Counters
		FILE: Number of bytes read=187140
		FILE: Number of bytes written=557005
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
	Map-Reduce Framework
		Map input records=5
		Map output records=5
		Map output bytes=45
		Map output materialized bytes=28
		Input split bytes=122
		Combine input records=5
		Combine output records=2
		Spilled Records=2
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=0
		Total committed heap usage (bytes)=315097088
	File Input Format Counters 
		Bytes Read=529
18/09/29 15:40:48 INFO mapred.LocalJobRunner: Finishing task: attempt_local1796500479_0001_m_000000_0
18/09/29 15:40:48 INFO mapred.LocalJobRunner: map task executor complete.
18/09/29 15:40:48 INFO mapred.LocalJobRunner: Waiting for reduce tasks
18/09/29 15:40:48 INFO mapred.LocalJobRunner: Starting task: attempt_local1796500479_0001_r_000000_0
18/09/29 15:40:48 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/09/29 15:40:48 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/09/29 15:40:48 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/09/29 15:40:48 INFO mapred.ReduceTask: Using ShuffleConsumerPlugin: org.apache.hadoop.mapreduce.task.reduce.Shuffle@63c5cdfc
18/09/29 15:40:48 INFO reduce.MergeManagerImpl: MergerManager: memoryLimit=334338464, maxSingleShuffleLimit=83584616, mergeThreshold=220663392, ioSortFactor=10, memToMemMergeOutputsThreshold=10
18/09/29 15:40:48 INFO reduce.EventFetcher: attempt_local1796500479_0001_r_000000_0 Thread started: EventFetcher for fetching Map Completion Events
18/09/29 15:40:48 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1796500479_0001_m_000000_0 decomp: 24 len: 28 to MEMORY
18/09/29 15:40:48 INFO reduce.InMemoryMapOutput: Read 24 bytes from map-output for attempt_local1796500479_0001_m_000000_0
18/09/29 15:40:48 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 24, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->24
18/09/29 15:40:48 INFO reduce.EventFetcher: EventFetcher is interrupted.. Returning
18/09/29 15:40:48 INFO mapred.LocalJobRunner: 1 / 1 copied.
18/09/29 15:40:48 INFO reduce.MergeManagerImpl: finalMerge called with 1 in-memory map-outputs and 0 on-disk map-outputs
18/09/29 15:40:48 INFO mapred.Merger: Merging 1 sorted segments
18/09/29 15:40:48 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 17 bytes
18/09/29 15:40:48 INFO reduce.MergeManagerImpl: Merged 1 segments, 24 bytes to disk to satisfy reduce memory limit
18/09/29 15:40:48 INFO reduce.MergeManagerImpl: Merging 1 files, 28 bytes from disk
18/09/29 15:40:48 INFO reduce.MergeManagerImpl: Merging 0 segments, 0 bytes from memory into reduce
18/09/29 15:40:48 INFO mapred.Merger: Merging 1 sorted segments
18/09/29 15:40:48 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 17 bytes
18/09/29 15:40:48 INFO mapred.LocalJobRunner: 1 / 1 copied.
18/09/29 15:40:48 INFO Configuration.deprecation: mapred.skip.on is deprecated. Instead, use mapreduce.job.skiprecords
18/09/29 15:40:48 INFO mapred.Task: Task:attempt_local1796500479_0001_r_000000_0 is done. And is in the process of committing
18/09/29 15:40:48 INFO mapred.LocalJobRunner: 1 / 1 copied.
18/09/29 15:40:48 INFO mapred.Task: Task attempt_local1796500479_0001_r_000000_0 is allowed to commit now
18/09/29 15:40:48 INFO output.FileOutputCommitter: Saved output of task 'attempt_local1796500479_0001_r_000000_0' to file:/home/storm/GitHub/hadoop-book/output/_temporary/0/task_local1796500479_0001_r_000000
18/09/29 15:40:48 INFO mapred.LocalJobRunner: reduce > reduce
18/09/29 15:40:48 INFO mapred.Task: Task 'attempt_local1796500479_0001_r_000000_0' done.
18/09/29 15:40:48 INFO mapred.Task: Final Counters for attempt_local1796500479_0001_r_000000_0: Counters: 24
	File System Counters
		FILE: Number of bytes read=187228
		FILE: Number of bytes written=557062
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
	Map-Reduce Framework
		Combine input records=0
		Combine output records=0
		Reduce input groups=2
		Reduce shuffle bytes=28
		Reduce input records=2
		Reduce output records=2
		Spilled Records=2
		Shuffled Maps =1
		Failed Shuffles=0
		Merged Map outputs=1
		GC time elapsed (ms)=0
		Total committed heap usage (bytes)=315097088
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Output Format Counters 
		Bytes Written=29
18/09/29 15:40:48 INFO mapred.LocalJobRunner: Finishing task: attempt_local1796500479_0001_r_000000_0
18/09/29 15:40:48 INFO mapred.LocalJobRunner: reduce task executor complete.
18/09/29 15:40:48 INFO mapreduce.Job: Job job_local1796500479_0001 running in uber mode : false
18/09/29 15:40:48 INFO mapreduce.Job:  map 100% reduce 100%
18/09/29 15:40:48 INFO mapreduce.Job: Job job_local1796500479_0001 completed successfully
18/09/29 15:40:48 INFO mapreduce.Job: Counters: 30
	File System Counters
		FILE: Number of bytes read=374368
		FILE: Number of bytes written=1114067
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
	Map-Reduce Framework
		Map input records=5
		Map output records=5
		Map output bytes=45
		Map output materialized bytes=28
		Input split bytes=122
		Combine input records=5
		Combine output records=2
		Reduce input groups=2
		Reduce shuffle bytes=28
		Reduce input records=2
		Reduce output records=2
		Spilled Records=4
		Shuffled Maps =1
		Failed Shuffles=0
		Merged Map outputs=1
		GC time elapsed (ms)=0
		Total committed heap usage (bytes)=630194176
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=529
	File Output Format Counters 
		Bytes Written=29
```


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

本地运行MaxTemperatureDriver：

```
➜  hadoop-book git:(master) ✗ rm -rf output 
➜  hadoop-book git:(master) ✗ hadoop    v2.MaxTemperatureDriver -conf   conf/hadoop-local.xml   \
                input/ncdc/micro        output
18/10/08 17:20:31 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
18/10/08 17:20:31 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
18/10/08 17:20:31 INFO input.FileInputFormat: Total input files to process : 1
18/10/08 17:20:31 INFO mapreduce.JobSubmitter: number of splits:1
18/10/08 17:20:31 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local1655365597_0001
18/10/08 17:20:32 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
18/10/08 17:20:32 INFO mapreduce.Job: Running job: job_local1655365597_0001
18/10/08 17:20:32 INFO mapred.LocalJobRunner: OutputCommitter set in config null
18/10/08 17:20:32 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 17:20:32 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 17:20:32 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
18/10/08 17:20:32 INFO mapred.LocalJobRunner: Waiting for map tasks
18/10/08 17:20:32 INFO mapred.LocalJobRunner: Starting task: attempt_local1655365597_0001_m_000000_0
18/10/08 17:20:32 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 17:20:32 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 17:20:32 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 17:20:32 INFO mapred.MapTask: Processing split: file:/home/storm/GitHub/hadoop-book/input/ncdc/micro/sample.txt:0+529
18/10/08 17:20:32 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 17:20:32 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 17:20:32 INFO mapred.MapTask: soft limit at 83886080
18/10/08 17:20:32 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 17:20:32 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 17:20:32 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 17:20:32 INFO mapred.LocalJobRunner: 
18/10/08 17:20:32 INFO mapred.MapTask: Starting flush of map output
18/10/08 17:20:32 INFO mapred.MapTask: Spilling map output
18/10/08 17:20:32 INFO mapred.MapTask: bufstart = 0; bufend = 45; bufvoid = 104857600
18/10/08 17:20:32 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214380(104857520); length = 17/6553600
18/10/08 17:20:32 INFO mapred.MapTask: Finished spill 0
18/10/08 17:20:32 INFO mapred.Task: Task:attempt_local1655365597_0001_m_000000_0 is done. And is in the process of committing
18/10/08 17:20:32 INFO mapred.LocalJobRunner: map
18/10/08 17:20:32 INFO mapred.Task: Task 'attempt_local1655365597_0001_m_000000_0' done.
18/10/08 17:20:32 INFO mapred.Task: Final Counters for attempt_local1655365597_0001_m_000000_0: Counters: 18
    File System Counters
        FILE: Number of bytes read=187151
        FILE: Number of bytes written=557450
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
    Map-Reduce Framework
        Map input records=5
        Map output records=5
        Map output bytes=45
        Map output materialized bytes=28
        Input split bytes=128
        Combine input records=5
        Combine output records=2
        Spilled Records=2
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=315097088
    File Input Format Counters 
        Bytes Read=529
18/10/08 17:20:32 INFO mapred.LocalJobRunner: Finishing task: attempt_local1655365597_0001_m_000000_0
18/10/08 17:20:32 INFO mapred.LocalJobRunner: map task executor complete.
18/10/08 17:20:32 INFO mapred.LocalJobRunner: Waiting for reduce tasks
18/10/08 17:20:32 INFO mapred.LocalJobRunner: Starting task: attempt_local1655365597_0001_r_000000_0
18/10/08 17:20:32 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 17:20:32 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 17:20:32 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 17:20:32 INFO mapred.ReduceTask: Using ShuffleConsumerPlugin: org.apache.hadoop.mapreduce.task.reduce.Shuffle@36dd638f
18/10/08 17:20:32 INFO reduce.MergeManagerImpl: MergerManager: memoryLimit=334338464, maxSingleShuffleLimit=83584616, mergeThreshold=220663392, ioSortFactor=10, memToMemMergeOutputsThreshold=10
18/10/08 17:20:32 INFO reduce.EventFetcher: attempt_local1655365597_0001_r_000000_0 Thread started: EventFetcher for fetching Map Completion Events
18/10/08 17:20:32 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1655365597_0001_m_000000_0 decomp: 24 len: 28 to MEMORY
18/10/08 17:20:32 INFO reduce.InMemoryMapOutput: Read 24 bytes from map-output for attempt_local1655365597_0001_m_000000_0
18/10/08 17:20:32 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 24, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->24
18/10/08 17:20:32 INFO reduce.EventFetcher: EventFetcher is interrupted.. Returning
18/10/08 17:20:32 INFO mapred.LocalJobRunner: 1 / 1 copied.
18/10/08 17:20:32 INFO reduce.MergeManagerImpl: finalMerge called with 1 in-memory map-outputs and 0 on-disk map-outputs
18/10/08 17:20:32 INFO mapred.Merger: Merging 1 sorted segments
18/10/08 17:20:32 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 17 bytes
18/10/08 17:20:32 INFO reduce.MergeManagerImpl: Merged 1 segments, 24 bytes to disk to satisfy reduce memory limit
18/10/08 17:20:32 INFO reduce.MergeManagerImpl: Merging 1 files, 28 bytes from disk
18/10/08 17:20:32 INFO reduce.MergeManagerImpl: Merging 0 segments, 0 bytes from memory into reduce
18/10/08 17:20:32 INFO mapred.Merger: Merging 1 sorted segments
18/10/08 17:20:32 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 17 bytes
18/10/08 17:20:32 INFO mapred.LocalJobRunner: 1 / 1 copied.
18/10/08 17:20:32 INFO Configuration.deprecation: mapred.skip.on is deprecated. Instead, use mapreduce.job.skiprecords
18/10/08 17:20:32 INFO mapred.Task: Task:attempt_local1655365597_0001_r_000000_0 is done. And is in the process of committing
18/10/08 17:20:32 INFO mapred.LocalJobRunner: 1 / 1 copied.
18/10/08 17:20:32 INFO mapred.Task: Task attempt_local1655365597_0001_r_000000_0 is allowed to commit now
18/10/08 17:20:32 INFO output.FileOutputCommitter: Saved output of task 'attempt_local1655365597_0001_r_000000_0' to file:/home/storm/GitHub/hadoop-book/output/_temporary/0/task_local1655365597_0001_r_000000
18/10/08 17:20:32 INFO mapred.LocalJobRunner: reduce > reduce
18/10/08 17:20:32 INFO mapred.Task: Task 'attempt_local1655365597_0001_r_000000_0' done.
18/10/08 17:20:32 INFO mapred.Task: Final Counters for attempt_local1655365597_0001_r_000000_0: Counters: 24
    File System Counters
        FILE: Number of bytes read=187239
        FILE: Number of bytes written=557507
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
    Map-Reduce Framework
        Combine input records=0
        Combine output records=0
        Reduce input groups=2
        Reduce shuffle bytes=28
        Reduce input records=2
        Reduce output records=2
        Spilled Records=2
        Shuffled Maps =1
        Failed Shuffles=0
        Merged Map outputs=1
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=315097088
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Output Format Counters 
        Bytes Written=29
18/10/08 17:20:32 INFO mapred.LocalJobRunner: Finishing task: attempt_local1655365597_0001_r_000000_0
18/10/08 17:20:32 INFO mapred.LocalJobRunner: reduce task executor complete.
18/10/08 17:20:33 INFO mapreduce.Job: Job job_local1655365597_0001 running in uber mode : false
18/10/08 17:20:33 INFO mapreduce.Job:  map 100% reduce 100%
18/10/08 17:20:33 INFO mapreduce.Job: Job job_local1655365597_0001 completed successfully
18/10/08 17:20:33 INFO mapreduce.Job: Counters: 30
    File System Counters
        FILE: Number of bytes read=374390
        FILE: Number of bytes written=1114957
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
    Map-Reduce Framework
        Map input records=5
        Map output records=5
        Map output bytes=45
        Map output materialized bytes=28
        Input split bytes=128
        Combine input records=5
        Combine output records=2
        Reduce input groups=2
        Reduce shuffle bytes=28
        Reduce input records=2
        Reduce output records=2
        Spilled Records=4
        Shuffled Maps =1
        Failed Shuffles=0
        Merged Map outputs=1
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=630194176
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Input Format Counters 
        Bytes Read=529
    File Output Format Counters 
        Bytes Written=29
➜  hadoop-book git:(master) ✗ ls output 
part-r-00000  _SUCCESS
➜  hadoop-book git:(master) ✗ cat output/part-r-00000 
1949    111
1950    22
```



[]()
[]()

[]()
[]()

[]()
[]()


## 7. MR是如何工作的

## 8. MR类型和格式

例8-1 使用默认的Mapper，Reducer会怎么样？

```
➜  hadoop-book git:(master) ✗ hadoop MinimalMapReduce ncdc-all output
18/10/08 19:03:27 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
18/10/08 19:03:27 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
18/10/08 19:03:28 INFO input.FileInputFormat: Total input files to process : 2
18/10/08 19:03:28 INFO mapreduce.JobSubmitter: number of splits:2
18/10/08 19:03:28 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local88882554_0001
18/10/08 19:03:28 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
18/10/08 19:03:28 INFO mapreduce.Job: Running job: job_local88882554_0001
18/10/08 19:03:28 INFO mapred.LocalJobRunner: OutputCommitter set in config null
18/10/08 19:03:28 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:03:28 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:03:28 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
18/10/08 19:03:28 INFO mapred.LocalJobRunner: Waiting for map tasks
18/10/08 19:03:28 INFO mapred.LocalJobRunner: Starting task: attempt_local88882554_0001_m_000000_0
18/10/08 19:03:28 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:03:28 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:03:28 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:03:28 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/ncdc-all/1902.gz:0+74105
18/10/08 19:03:28 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 19:03:28 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 19:03:28 INFO mapred.MapTask: soft limit at 83886080
18/10/08 19:03:28 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 19:03:28 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 19:03:28 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 19:03:28 INFO zlib.ZlibFactory: Successfully loaded & initialized native-zlib library
18/10/08 19:03:28 INFO compress.CodecPool: Got brand-new decompressor [.gz]
18/10/08 19:03:28 INFO mapred.LocalJobRunner: 
18/10/08 19:03:28 INFO mapred.MapTask: Starting flush of map output
18/10/08 19:03:28 INFO mapred.MapTask: Spilling map output
18/10/08 19:03:28 INFO mapred.MapTask: bufstart = 0; bufend = 948037; bufvoid = 104857600
18/10/08 19:03:28 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26188140(104752560); length = 26257/6553600
18/10/08 19:03:28 INFO mapred.MapTask: Finished spill 0
18/10/08 19:03:28 INFO mapred.Task: Task:attempt_local88882554_0001_m_000000_0 is done. And is in the process of committing
18/10/08 19:03:28 INFO mapred.LocalJobRunner: map
18/10/08 19:03:28 INFO mapred.Task: Task 'attempt_local88882554_0001_m_000000_0' done.
18/10/08 19:03:28 INFO mapred.Task: Final Counters for attempt_local88882554_0001_m_000000_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=186721
        FILE: Number of bytes written=1520021
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=74105
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=5
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=6565
        Map output records=6565
        Map output bytes=948037
        Map output materialized bytes=967712
        Input split bytes=109
        Combine input records=0
        Spilled Records=6565
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=346030080
    File Input Format Counters 
        Bytes Read=74105
18/10/08 19:03:28 INFO mapred.LocalJobRunner: Finishing task: attempt_local88882554_0001_m_000000_0
18/10/08 19:03:28 INFO mapred.LocalJobRunner: Starting task: attempt_local88882554_0001_m_000001_0
18/10/08 19:03:28 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:03:28 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:03:28 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:03:28 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/ncdc-all/1901.gz:0+73867
18/10/08 19:03:29 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 19:03:29 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 19:03:29 INFO mapred.MapTask: soft limit at 83886080
18/10/08 19:03:29 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 19:03:29 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 19:03:29 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 19:03:29 INFO mapred.LocalJobRunner: 
18/10/08 19:03:29 INFO mapred.MapTask: Starting flush of map output
18/10/08 19:03:29 INFO mapred.MapTask: Spilling map output
18/10/08 19:03:29 INFO mapred.MapTask: bufstart = 0; bufend = 947264; bufvoid = 104857600
18/10/08 19:03:29 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26188140(104752560); length = 26257/6553600
18/10/08 19:03:29 INFO mapred.MapTask: Finished spill 0
18/10/08 19:03:29 INFO mapred.Task: Task:attempt_local88882554_0001_m_000001_0 is done. And is in the process of committing
18/10/08 19:03:29 INFO mapred.LocalJobRunner: map
18/10/08 19:03:29 INFO mapred.Task: Task 'attempt_local88882554_0001_m_000001_0' done.
18/10/08 19:03:29 INFO mapred.Task: Final Counters for attempt_local88882554_0001_m_000001_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=186958
        FILE: Number of bytes written=2487007
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=147972
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=7
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=6565
        Map output records=6565
        Map output bytes=947264
        Map output materialized bytes=966954
        Input split bytes=109
        Combine input records=0
        Spilled Records=6565
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=451411968
    File Input Format Counters 
        Bytes Read=73867
18/10/08 19:03:29 INFO mapred.LocalJobRunner: Finishing task: attempt_local88882554_0001_m_000001_0
18/10/08 19:03:29 INFO mapred.LocalJobRunner: map task executor complete.
18/10/08 19:03:29 INFO mapred.LocalJobRunner: Waiting for reduce tasks
18/10/08 19:03:29 INFO mapred.LocalJobRunner: Starting task: attempt_local88882554_0001_r_000000_0
18/10/08 19:03:29 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:03:29 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:03:29 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:03:29 INFO mapred.ReduceTask: Using ShuffleConsumerPlugin: org.apache.hadoop.mapreduce.task.reduce.Shuffle@73c285ca
18/10/08 19:03:29 INFO reduce.MergeManagerImpl: MergerManager: memoryLimit=334338464, maxSingleShuffleLimit=83584616, mergeThreshold=220663392, ioSortFactor=10, memToMemMergeOutputsThreshold=10
18/10/08 19:03:29 INFO reduce.EventFetcher: attempt_local88882554_0001_r_000000_0 Thread started: EventFetcher for fetching Map Completion Events
18/10/08 19:03:29 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local88882554_0001_m_000001_0 decomp: 966950 len: 966954 to MEMORY
18/10/08 19:03:29 INFO reduce.InMemoryMapOutput: Read 966950 bytes from map-output for attempt_local88882554_0001_m_000001_0
18/10/08 19:03:29 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 966950, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->966950
18/10/08 19:03:29 WARN io.ReadaheadPool: Failed readahead on ifile
EBADF: Bad file descriptor
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posix_fadvise(Native Method)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posixFadviseIfPossible(NativeIO.java:267)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX$CacheManipulator.posixFadviseIfPossible(NativeIO.java:146)
    at org.apache.hadoop.io.ReadaheadPool$ReadaheadRequestImpl.run(ReadaheadPool.java:208)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
    at java.lang.Thread.run(Thread.java:748)
18/10/08 19:03:29 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local88882554_0001_m_000000_0 decomp: 967708 len: 967712 to MEMORY
18/10/08 19:03:29 INFO reduce.InMemoryMapOutput: Read 967708 bytes from map-output for attempt_local88882554_0001_m_000000_0
18/10/08 19:03:29 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 967708, inMemoryMapOutputs.size() -> 2, commitMemory -> 966950, usedMemory ->1934658
18/10/08 19:03:29 INFO reduce.EventFetcher: EventFetcher is interrupted.. Returning
18/10/08 19:03:29 INFO mapred.LocalJobRunner: 2 / 2 copied.
18/10/08 19:03:29 INFO reduce.MergeManagerImpl: finalMerge called with 2 in-memory map-outputs and 0 on-disk map-outputs
18/10/08 19:03:29 INFO mapred.Merger: Merging 2 sorted segments
18/10/08 19:03:29 INFO mapred.Merger: Down to the last merge-pass, with 2 segments left of total size: 1934636 bytes
18/10/08 19:03:29 INFO reduce.MergeManagerImpl: Merged 2 segments, 1934658 bytes to disk to satisfy reduce memory limit
18/10/08 19:03:29 INFO reduce.MergeManagerImpl: Merging 1 files, 1934660 bytes from disk
18/10/08 19:03:29 INFO reduce.MergeManagerImpl: Merging 0 segments, 0 bytes from memory into reduce
18/10/08 19:03:29 INFO mapred.Merger: Merging 1 sorted segments
18/10/08 19:03:29 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 1934645 bytes
18/10/08 19:03:29 INFO mapred.LocalJobRunner: 2 / 2 copied.
18/10/08 19:03:29 INFO Configuration.deprecation: mapred.skip.on is deprecated. Instead, use mapreduce.job.skiprecords
18/10/08 19:03:29 INFO mapreduce.Job: Job job_local88882554_0001 running in uber mode : false
18/10/08 19:03:29 INFO mapreduce.Job:  map 100% reduce 0%
18/10/08 19:03:29 INFO mapred.Task: Task:attempt_local88882554_0001_r_000000_0 is done. And is in the process of committing
18/10/08 19:03:29 INFO mapred.LocalJobRunner: 2 / 2 copied.
18/10/08 19:03:29 INFO mapred.Task: Task attempt_local88882554_0001_r_000000_0 is allowed to commit now
18/10/08 19:03:29 INFO output.FileOutputCommitter: Saved output of task 'attempt_local88882554_0001_r_000000_0' to hdfs://localhost/user/storm/output/_temporary/0/task_local88882554_0001_r_000000
18/10/08 19:03:29 INFO mapred.LocalJobRunner: reduce > reduce
18/10/08 19:03:29 INFO mapred.Task: Task 'attempt_local88882554_0001_r_000000_0' done.
18/10/08 19:03:29 INFO mapred.Task: Final Counters for attempt_local88882554_0001_r_000000_0: Counters: 29
    File System Counters
        FILE: Number of bytes read=4056348
        FILE: Number of bytes written=4421667
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=147972
        HDFS: Number of bytes written=1867434
        HDFS: Number of read operations=10
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=3
    Map-Reduce Framework
        Combine input records=0
        Combine output records=0
        Reduce input groups=13124
        Reduce shuffle bytes=1934666
        Reduce input records=13130
        Reduce output records=13130
        Spilled Records=13130
        Shuffled Maps =2
        Failed Shuffles=0
        Merged Map outputs=2
        GC time elapsed (ms)=32
        Total committed heap usage (bytes)=478150656
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Output Format Counters 
        Bytes Written=1867434
18/10/08 19:03:29 INFO mapred.LocalJobRunner: Finishing task: attempt_local88882554_0001_r_000000_0
18/10/08 19:03:29 INFO mapred.LocalJobRunner: reduce task executor complete.
18/10/08 19:03:30 INFO mapreduce.Job:  map 100% reduce 100%
18/10/08 19:03:30 INFO mapreduce.Job: Job job_local88882554_0001 completed successfully
18/10/08 19:03:30 INFO mapreduce.Job: Counters: 35
    File System Counters
        FILE: Number of bytes read=4430027
        FILE: Number of bytes written=8428695
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=370049
        HDFS: Number of bytes written=1867434
        HDFS: Number of read operations=22
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=5
    Map-Reduce Framework
        Map input records=13130
        Map output records=13130
        Map output bytes=1895301
        Map output materialized bytes=1934666
        Input split bytes=218
        Combine input records=0
        Combine output records=0
        Reduce input groups=13124
        Reduce shuffle bytes=1934666
        Reduce input records=13130
        Reduce output records=13130
        Spilled Records=26260
        Shuffled Maps =2
        Failed Shuffles=0
        Merged Map outputs=2
        GC time elapsed (ms)=32
        Total committed heap usage (bytes)=1275592704
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Input Format Counters 
        Bytes Read=147972
    File Output Format Counters 
        Bytes Written=1867434
➜  hadoop-book git:(master) ✗ hadoop fs -ls output
Found 2 items
-rw-r--r--   1 storm supergroup          0 2018-10-08 19:03 output/_SUCCESS
-rw-r--r--   1 storm supergroup    1867434 2018-10-08 19:03 output/part-r-00000
➜  hadoop-book git:(master) ✗ hadoop fs -text output/part-r-00000 | head
0   0029029070999991901010106004+64333+023450FM-12+000599999V0202701N015919999999N0000001N9-00781+99999102001ADDGF108991999999999999999999
0   0035029070999991902010106004+64333+023450FM-12+000599999V0201401N011819999999N0000001N9-00941+99999100551ADDGF104991999999999999999999MW1381
135 0029029070999991901010113004+64333+023450FM-12+000599999V0202901N008219999999N0000001N9-00721+99999102001ADDGF104991999999999999999999
141 0035029070999991902010113004+64333+023450FM-12+000599999V0201401N011819999999N0000001N9-01001+99999100311ADDGF104991999999999999999999MW1381
270 0029029070999991901010120004+64333+023450FM-12+000599999V0209991C000019999999N0000001N9-00941+99999102001ADDGF108991999999999999999999
282 0035029070999991902010120004+64333+023450FM-12+000599999V0201401N013919999999N0000001N9-01171+99999100121ADDGF108991999999999999999999MW1381
405 0029029070999991901010206004+64333+023450FM-12+000599999V0201801N008219999999N0000001N9-00611+99999101831ADDGF108991999999999999999999
423 0035029070999991902010206004+64333+023450FM-12+000599999V0200901N009819999999N0000001N9-01611+99999100121ADDGF108991999999999999999999MW1381
540 0029029070999991901010213004+64333+023450FM-12+000599999V0201801N009819999999N0000001N9-00561+99999101761ADDGF108991999999999999999999
564 0029029070999991902010213004+64333+023450FM-12+000599999V0200901N011819999999N0000001N9-01721+99999100121ADDGF108991999999999999999999
text: Unable to write to output stream.
➜  hadoop-book git:(master) ✗ hadoop fs -rm -r output
Deleted output
➜  hadoop-book git:(master) ✗ hadoop MinimalMapReduceWithDefaults ncdc-all output
18/10/08 19:06:39 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
18/10/08 19:06:39 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
18/10/08 19:06:39 INFO input.FileInputFormat: Total input files to process : 2
18/10/08 19:06:39 INFO mapreduce.JobSubmitter: number of splits:2
18/10/08 19:06:39 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local198992695_0001
18/10/08 19:06:39 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
18/10/08 19:06:39 INFO mapreduce.Job: Running job: job_local198992695_0001
18/10/08 19:06:39 INFO mapred.LocalJobRunner: OutputCommitter set in config null
18/10/08 19:06:39 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:06:39 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:06:39 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
18/10/08 19:06:40 INFO mapred.LocalJobRunner: Waiting for map tasks
18/10/08 19:06:40 INFO mapred.LocalJobRunner: Starting task: attempt_local198992695_0001_m_000000_0
18/10/08 19:06:40 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:06:40 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:06:40 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:06:40 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/ncdc-all/1902.gz:0+74105
18/10/08 19:06:40 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 19:06:40 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 19:06:40 INFO mapred.MapTask: soft limit at 83886080
18/10/08 19:06:40 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 19:06:40 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 19:06:40 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 19:06:40 INFO zlib.ZlibFactory: Successfully loaded & initialized native-zlib library
18/10/08 19:06:40 INFO compress.CodecPool: Got brand-new decompressor [.gz]
18/10/08 19:06:40 INFO mapred.LocalJobRunner: 
18/10/08 19:06:40 INFO mapred.MapTask: Starting flush of map output
18/10/08 19:06:40 INFO mapred.MapTask: Spilling map output
18/10/08 19:06:40 INFO mapred.MapTask: bufstart = 0; bufend = 948037; bufvoid = 104857600
18/10/08 19:06:40 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26188140(104752560); length = 26257/6553600
18/10/08 19:06:40 INFO mapred.MapTask: Finished spill 0
18/10/08 19:06:40 INFO mapred.Task: Task:attempt_local198992695_0001_m_000000_0 is done. And is in the process of committing
18/10/08 19:06:40 INFO mapred.LocalJobRunner: map
18/10/08 19:06:40 INFO mapred.Task: Task 'attempt_local198992695_0001_m_000000_0' done.
18/10/08 19:06:40 INFO mapred.Task: Final Counters for attempt_local198992695_0001_m_000000_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=186721
        FILE: Number of bytes written=1525885
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=74105
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=5
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=6565
        Map output records=6565
        Map output bytes=948037
        Map output materialized bytes=967712
        Input split bytes=109
        Combine input records=0
        Spilled Records=6565
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=15
        Total committed heap usage (bytes)=310378496
    File Input Format Counters 
        Bytes Read=74105
18/10/08 19:06:40 INFO mapred.LocalJobRunner: Finishing task: attempt_local198992695_0001_m_000000_0
18/10/08 19:06:40 INFO mapred.LocalJobRunner: Starting task: attempt_local198992695_0001_m_000001_0
18/10/08 19:06:40 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:06:40 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:06:40 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:06:40 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/ncdc-all/1901.gz:0+73867
18/10/08 19:06:40 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 19:06:40 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 19:06:40 INFO mapred.MapTask: soft limit at 83886080
18/10/08 19:06:40 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 19:06:40 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 19:06:40 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 19:06:40 INFO mapred.LocalJobRunner: 
18/10/08 19:06:40 INFO mapred.MapTask: Starting flush of map output
18/10/08 19:06:40 INFO mapred.MapTask: Spilling map output
18/10/08 19:06:40 INFO mapred.MapTask: bufstart = 0; bufend = 947264; bufvoid = 104857600
18/10/08 19:06:40 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26188140(104752560); length = 26257/6553600
18/10/08 19:06:40 INFO mapred.MapTask: Finished spill 0
18/10/08 19:06:40 INFO mapred.Task: Task:attempt_local198992695_0001_m_000001_0 is done. And is in the process of committing
18/10/08 19:06:40 INFO mapred.LocalJobRunner: map
18/10/08 19:06:40 INFO mapred.Task: Task 'attempt_local198992695_0001_m_000001_0' done.
18/10/08 19:06:40 INFO mapred.Task: Final Counters for attempt_local198992695_0001_m_000001_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=186958
        FILE: Number of bytes written=2492871
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=147972
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=7
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=6565
        Map output records=6565
        Map output bytes=947264
        Map output materialized bytes=966954
        Input split bytes=109
        Combine input records=0
        Spilled Records=6565
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=415760384
    File Input Format Counters 
        Bytes Read=73867
18/10/08 19:06:40 INFO mapred.LocalJobRunner: Finishing task: attempt_local198992695_0001_m_000001_0
18/10/08 19:06:40 INFO mapred.LocalJobRunner: map task executor complete.
18/10/08 19:06:40 INFO mapred.LocalJobRunner: Waiting for reduce tasks
18/10/08 19:06:40 INFO mapred.LocalJobRunner: Starting task: attempt_local198992695_0001_r_000000_0
18/10/08 19:06:40 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:06:40 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:06:40 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:06:40 INFO mapred.ReduceTask: Using ShuffleConsumerPlugin: org.apache.hadoop.mapreduce.task.reduce.Shuffle@468c6041
18/10/08 19:06:40 INFO reduce.MergeManagerImpl: MergerManager: memoryLimit=334338464, maxSingleShuffleLimit=83584616, mergeThreshold=220663392, ioSortFactor=10, memToMemMergeOutputsThreshold=10
18/10/08 19:06:40 INFO reduce.EventFetcher: attempt_local198992695_0001_r_000000_0 Thread started: EventFetcher for fetching Map Completion Events
18/10/08 19:06:40 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local198992695_0001_m_000001_0 decomp: 966950 len: 966954 to MEMORY
18/10/08 19:06:40 INFO reduce.InMemoryMapOutput: Read 966950 bytes from map-output for attempt_local198992695_0001_m_000001_0
18/10/08 19:06:40 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 966950, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->966950
18/10/08 19:06:40 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local198992695_0001_m_000000_0 decomp: 967708 len: 967712 to MEMORY
18/10/08 19:06:40 INFO reduce.InMemoryMapOutput: Read 967708 bytes from map-output for attempt_local198992695_0001_m_000000_0
18/10/08 19:06:40 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 967708, inMemoryMapOutputs.size() -> 2, commitMemory -> 966950, usedMemory ->1934658
18/10/08 19:06:40 WARN io.ReadaheadPool: Failed readahead on ifile
EBADF: Bad file descriptor
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posix_fadvise(Native Method)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posixFadviseIfPossible(NativeIO.java:267)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX$CacheManipulator.posixFadviseIfPossible(NativeIO.java:146)
    at org.apache.hadoop.io.ReadaheadPool$ReadaheadRequestImpl.run(ReadaheadPool.java:208)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
    at java.lang.Thread.run(Thread.java:748)
18/10/08 19:06:40 INFO reduce.EventFetcher: EventFetcher is interrupted.. Returning
18/10/08 19:06:40 INFO mapred.LocalJobRunner: 2 / 2 copied.
18/10/08 19:06:40 INFO reduce.MergeManagerImpl: finalMerge called with 2 in-memory map-outputs and 0 on-disk map-outputs
18/10/08 19:06:40 INFO mapred.Merger: Merging 2 sorted segments
18/10/08 19:06:40 INFO mapred.Merger: Down to the last merge-pass, with 2 segments left of total size: 1934636 bytes
18/10/08 19:06:40 INFO reduce.MergeManagerImpl: Merged 2 segments, 1934658 bytes to disk to satisfy reduce memory limit
18/10/08 19:06:40 INFO reduce.MergeManagerImpl: Merging 1 files, 1934660 bytes from disk
18/10/08 19:06:40 INFO reduce.MergeManagerImpl: Merging 0 segments, 0 bytes from memory into reduce
18/10/08 19:06:40 INFO mapred.Merger: Merging 1 sorted segments
18/10/08 19:06:40 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 1934645 bytes
18/10/08 19:06:40 INFO mapred.LocalJobRunner: 2 / 2 copied.
18/10/08 19:06:40 INFO mapreduce.Job: Job job_local198992695_0001 running in uber mode : false
18/10/08 19:06:40 INFO mapreduce.Job:  map 100% reduce 0%
18/10/08 19:06:40 INFO Configuration.deprecation: mapred.skip.on is deprecated. Instead, use mapreduce.job.skiprecords
18/10/08 19:06:41 INFO mapred.Task: Task:attempt_local198992695_0001_r_000000_0 is done. And is in the process of committing
18/10/08 19:06:41 INFO mapred.LocalJobRunner: 2 / 2 copied.
18/10/08 19:06:41 INFO mapred.Task: Task attempt_local198992695_0001_r_000000_0 is allowed to commit now
18/10/08 19:06:41 INFO output.FileOutputCommitter: Saved output of task 'attempt_local198992695_0001_r_000000_0' to hdfs://localhost/user/storm/output/_temporary/0/task_local198992695_0001_r_000000
18/10/08 19:06:41 INFO mapred.LocalJobRunner: reduce > reduce
18/10/08 19:06:41 INFO mapred.Task: Task 'attempt_local198992695_0001_r_000000_0' done.
18/10/08 19:06:41 INFO mapred.Task: Final Counters for attempt_local198992695_0001_r_000000_0: Counters: 29
    File System Counters
        FILE: Number of bytes read=4056348
        FILE: Number of bytes written=4427531
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=147972
        HDFS: Number of bytes written=1867434
        HDFS: Number of read operations=10
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=3
    Map-Reduce Framework
        Combine input records=0
        Combine output records=0
        Reduce input groups=13124
        Reduce shuffle bytes=1934666
        Reduce input records=13130
        Reduce output records=13130
        Spilled Records=13130
        Shuffled Maps =2
        Failed Shuffles=0
        Merged Map outputs=2
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=415760384
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Output Format Counters 
        Bytes Written=1867434
18/10/08 19:06:41 INFO mapred.LocalJobRunner: Finishing task: attempt_local198992695_0001_r_000000_0
18/10/08 19:06:41 INFO mapred.LocalJobRunner: reduce task executor complete.
18/10/08 19:06:41 INFO mapreduce.Job:  map 100% reduce 100%
18/10/08 19:06:41 INFO mapreduce.Job: Job job_local198992695_0001 completed successfully
18/10/08 19:06:41 INFO mapreduce.Job: Counters: 35
    File System Counters
        FILE: Number of bytes read=4430027
        FILE: Number of bytes written=8446287
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=370049
        HDFS: Number of bytes written=1867434
        HDFS: Number of read operations=22
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=5
    Map-Reduce Framework
        Map input records=13130
        Map output records=13130
        Map output bytes=1895301
        Map output materialized bytes=1934666
        Input split bytes=218
        Combine input records=0
        Combine output records=0
        Reduce input groups=13124
        Reduce shuffle bytes=1934666
        Reduce input records=13130
        Reduce output records=13130
        Spilled Records=26260
        Shuffled Maps =2
        Failed Shuffles=0
        Merged Map outputs=2
        GC time elapsed (ms)=15
        Total committed heap usage (bytes)=1141899264
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Input Format Counters 
        Bytes Read=147972
    File Output Format Counters 
        Bytes Written=1867434
➜  hadoop-book git:(master) ✗ hadoop fs -text output/part-r-00000 | head         
0   0029029070999991901010106004+64333+023450FM-12+000599999V0202701N015919999999N0000001N9-00781+99999102001ADDGF108991999999999999999999
0   0035029070999991902010106004+64333+023450FM-12+000599999V0201401N011819999999N0000001N9-00941+99999100551ADDGF104991999999999999999999MW1381
135 0029029070999991901010113004+64333+023450FM-12+000599999V0202901N008219999999N0000001N9-00721+99999102001ADDGF104991999999999999999999
141 0035029070999991902010113004+64333+023450FM-12+000599999V0201401N011819999999N0000001N9-01001+99999100311ADDGF104991999999999999999999MW1381
270 0029029070999991901010120004+64333+023450FM-12+000599999V0209991C000019999999N0000001N9-00941+99999102001ADDGF108991999999999999999999
282 0035029070999991902010120004+64333+023450FM-12+000599999V0201401N013919999999N0000001N9-01171+99999100121ADDGF108991999999999999999999MW1381
405 0029029070999991901010206004+64333+023450FM-12+000599999V0201801N008219999999N0000001N9-00611+99999101831ADDGF108991999999999999999999
423 0035029070999991902010206004+64333+023450FM-12+000599999V0200901N009819999999N0000001N9-01611+99999100121ADDGF108991999999999999999999MW1381
540 0029029070999991901010213004+64333+023450FM-12+000599999V0201801N009819999999N0000001N9-00561+99999101761ADDGF108991999999999999999999
564 0029029070999991902010213004+64333+023450FM-12+000599999V0200901N011819999999N0000001N9-01721+99999100121ADDGF108991999999999999999999
text: Unable to write to output stream.
```

例8-2，8-3，8-4 把整个文件作为一个记录的 InputFormat.

```
➜  hadoop-book git:(master) ✗ hadoop fs -copyFromLocal input/smallfiles smallfiles
➜  hadoop-book git:(master) ✗ hadoop fs -text smallfiles/e                                                                                                                                                  ➜  hadoop-book git:(master) ✗ hadoop jar hadoop-examples.jar SmallFilesToSequenceFileConverter -D mapreduce.job.reduces=2       smallfiles      output  
18/10/08 19:26:09 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
18/10/08 19:26:09 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
18/10/08 19:26:10 INFO input.FileInputFormat: Total input files to process : 6
18/10/08 19:26:10 INFO mapreduce.JobSubmitter: number of splits:6
18/10/08 19:26:10 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local897460502_0001
18/10/08 19:26:10 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
18/10/08 19:26:10 INFO mapreduce.Job: Running job: job_local897460502_0001
18/10/08 19:26:10 INFO mapred.LocalJobRunner: OutputCommitter set in config null
18/10/08 19:26:10 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:26:10 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:26:10 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
18/10/08 19:26:10 INFO mapred.LocalJobRunner: Waiting for map tasks
18/10/08 19:26:10 INFO mapred.LocalJobRunner: Starting task: attempt_local897460502_0001_m_000000_0
18/10/08 19:26:10 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:26:10 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:26:10 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:26:10 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/smallfiles/a:0+21
18/10/08 19:26:10 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 19:26:10 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 19:26:10 INFO mapred.MapTask: soft limit at 83886080
18/10/08 19:26:10 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 19:26:10 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 19:26:10 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 19:26:10 INFO mapred.LocalJobRunner: 
18/10/08 19:26:10 INFO mapred.MapTask: Starting flush of map output
18/10/08 19:26:10 INFO mapred.MapTask: Spilling map output
18/10/08 19:26:10 INFO mapred.MapTask: bufstart = 0; bufend = 66; bufvoid = 104857600
18/10/08 19:26:10 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214396(104857584); length = 1/6553600
18/10/08 19:26:10 INFO mapred.MapTask: Finished spill 0
18/10/08 19:26:10 INFO mapred.Task: Task:attempt_local897460502_0001_m_000000_0 is done. And is in the process of committing
18/10/08 19:26:10 INFO mapred.LocalJobRunner: map
18/10/08 19:26:10 INFO mapred.Task: Task 'attempt_local897460502_0001_m_000000_0' done.
18/10/08 19:26:10 INFO mapred.Task: Final Counters for attempt_local897460502_0001_m_000000_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=187168
        FILE: Number of bytes written=556910
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=21
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=5
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=1
        Map output records=1
        Map output bytes=66
        Map output materialized bytes=80
        Input split bytes=105
        Combine input records=0
        Spilled Records=1
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=7
        Total committed heap usage (bytes)=311427072
    File Input Format Counters 
        Bytes Read=21
18/10/08 19:26:10 INFO mapred.LocalJobRunner: Finishing task: attempt_local897460502_0001_m_000000_0
18/10/08 19:26:10 INFO mapred.LocalJobRunner: Starting task: attempt_local897460502_0001_m_000001_0
18/10/08 19:26:10 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:26:10 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:26:10 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:26:10 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/smallfiles/b:0+10
18/10/08 19:26:10 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 19:26:10 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 19:26:10 INFO mapred.MapTask: soft limit at 83886080
18/10/08 19:26:10 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 19:26:10 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 19:26:10 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 19:26:10 INFO mapred.LocalJobRunner: 
18/10/08 19:26:10 INFO mapred.MapTask: Starting flush of map output
18/10/08 19:26:10 INFO mapred.MapTask: Spilling map output
18/10/08 19:26:10 INFO mapred.MapTask: bufstart = 0; bufend = 55; bufvoid = 104857600
18/10/08 19:26:10 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214396(104857584); length = 1/6553600
18/10/08 19:26:10 INFO mapred.MapTask: Finished spill 0
18/10/08 19:26:10 INFO mapred.Task: Task:attempt_local897460502_0001_m_000001_0 is done. And is in the process of committing
18/10/08 19:26:10 INFO mapred.LocalJobRunner: map
18/10/08 19:26:10 INFO mapred.Task: Task 'attempt_local897460502_0001_m_000001_0' done.
18/10/08 19:26:10 INFO mapred.Task: Final Counters for attempt_local897460502_0001_m_000001_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=187821
        FILE: Number of bytes written=557035
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=31
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=7
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=1
        Map output records=1
        Map output bytes=55
        Map output materialized bytes=69
        Input split bytes=105
        Combine input records=0
        Spilled Records=1
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=416808960
    File Input Format Counters 
        Bytes Read=10
18/10/08 19:26:10 INFO mapred.LocalJobRunner: Finishing task: attempt_local897460502_0001_m_000001_0
18/10/08 19:26:10 INFO mapred.LocalJobRunner: Starting task: attempt_local897460502_0001_m_000002_0
18/10/08 19:26:10 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:26:10 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:26:10 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:26:10 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/smallfiles/c:0+10
18/10/08 19:26:10 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 19:26:10 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 19:26:10 INFO mapred.MapTask: soft limit at 83886080
18/10/08 19:26:10 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 19:26:10 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 19:26:10 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 19:26:10 INFO mapred.LocalJobRunner: 
18/10/08 19:26:10 INFO mapred.MapTask: Starting flush of map output
18/10/08 19:26:10 INFO mapred.MapTask: Spilling map output
18/10/08 19:26:10 INFO mapred.MapTask: bufstart = 0; bufend = 55; bufvoid = 104857600
18/10/08 19:26:10 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214396(104857584); length = 1/6553600
18/10/08 19:26:10 INFO mapred.MapTask: Finished spill 0
18/10/08 19:26:10 INFO mapred.Task: Task:attempt_local897460502_0001_m_000002_0 is done. And is in the process of committing
18/10/08 19:26:10 INFO mapred.LocalJobRunner: map
18/10/08 19:26:10 INFO mapred.Task: Task 'attempt_local897460502_0001_m_000002_0' done.
18/10/08 19:26:10 INFO mapred.Task: Final Counters for attempt_local897460502_0001_m_000002_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=188474
        FILE: Number of bytes written=557160
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=41
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=9
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=1
        Map output records=1
        Map output bytes=55
        Map output materialized bytes=69
        Input split bytes=105
        Combine input records=0
        Spilled Records=1
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=467140608
    File Input Format Counters 
        Bytes Read=10
18/10/08 19:26:10 INFO mapred.LocalJobRunner: Finishing task: attempt_local897460502_0001_m_000002_0
18/10/08 19:26:10 INFO mapred.LocalJobRunner: Starting task: attempt_local897460502_0001_m_000003_0
18/10/08 19:26:10 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:26:10 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:26:10 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:26:10 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/smallfiles/d:0+10
18/10/08 19:26:10 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 19:26:10 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 19:26:10 INFO mapred.MapTask: soft limit at 83886080
18/10/08 19:26:10 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 19:26:10 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 19:26:10 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 19:26:10 INFO mapred.LocalJobRunner: 
18/10/08 19:26:10 INFO mapred.MapTask: Starting flush of map output
18/10/08 19:26:10 INFO mapred.MapTask: Spilling map output
18/10/08 19:26:10 INFO mapred.MapTask: bufstart = 0; bufend = 55; bufvoid = 104857600
18/10/08 19:26:10 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214396(104857584); length = 1/6553600
18/10/08 19:26:10 INFO mapred.MapTask: Finished spill 0
18/10/08 19:26:10 INFO mapred.Task: Task:attempt_local897460502_0001_m_000003_0 is done. And is in the process of committing
18/10/08 19:26:10 INFO mapred.LocalJobRunner: map
18/10/08 19:26:10 INFO mapred.Task: Task 'attempt_local897460502_0001_m_000003_0' done.
18/10/08 19:26:10 INFO mapred.Task: Final Counters for attempt_local897460502_0001_m_000003_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=189127
        FILE: Number of bytes written=557285
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=51
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=11
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=1
        Map output records=1
        Map output bytes=55
        Map output materialized bytes=69
        Input split bytes=105
        Combine input records=0
        Spilled Records=1
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=7
        Total committed heap usage (bytes)=492306432
    File Input Format Counters 
        Bytes Read=10
18/10/08 19:26:10 INFO mapred.LocalJobRunner: Finishing task: attempt_local897460502_0001_m_000003_0
18/10/08 19:26:10 INFO mapred.LocalJobRunner: Starting task: attempt_local897460502_0001_m_000004_0
18/10/08 19:26:10 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:26:10 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:26:10 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:26:10 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/smallfiles/f:0+10
18/10/08 19:26:11 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 19:26:11 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 19:26:11 INFO mapred.MapTask: soft limit at 83886080
18/10/08 19:26:11 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 19:26:11 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 19:26:11 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 19:26:11 INFO mapred.LocalJobRunner: 
18/10/08 19:26:11 INFO mapred.MapTask: Starting flush of map output
18/10/08 19:26:11 INFO mapred.MapTask: Spilling map output
18/10/08 19:26:11 INFO mapred.MapTask: bufstart = 0; bufend = 55; bufvoid = 104857600
18/10/08 19:26:11 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214396(104857584); length = 1/6553600
18/10/08 19:26:11 INFO mapred.MapTask: Finished spill 0
18/10/08 19:26:11 INFO mapred.Task: Task:attempt_local897460502_0001_m_000004_0 is done. And is in the process of committing
18/10/08 19:26:11 INFO mapred.LocalJobRunner: map
18/10/08 19:26:11 INFO mapred.Task: Task 'attempt_local897460502_0001_m_000004_0' done.
18/10/08 19:26:11 INFO mapred.Task: Final Counters for attempt_local897460502_0001_m_000004_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=189780
        FILE: Number of bytes written=557410
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=61
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=13
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=1
        Map output records=1
        Map output bytes=55
        Map output materialized bytes=69
        Input split bytes=105
        Combine input records=0
        Spilled Records=1
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=7
        Total committed heap usage (bytes)=524812288
    File Input Format Counters 
        Bytes Read=10
18/10/08 19:26:11 INFO mapred.LocalJobRunner: Finishing task: attempt_local897460502_0001_m_000004_0
18/10/08 19:26:11 INFO mapred.LocalJobRunner: Starting task: attempt_local897460502_0001_m_000005_0
18/10/08 19:26:11 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:26:11 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:26:11 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:26:11 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/smallfiles/e:0+0
18/10/08 19:26:11 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 19:26:11 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 19:26:11 INFO mapred.MapTask: soft limit at 83886080
18/10/08 19:26:11 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 19:26:11 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 19:26:11 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 19:26:11 INFO mapred.LocalJobRunner: 
18/10/08 19:26:11 INFO mapred.MapTask: Starting flush of map output
18/10/08 19:26:11 INFO mapred.MapTask: Spilling map output
18/10/08 19:26:11 INFO mapred.MapTask: bufstart = 0; bufend = 45; bufvoid = 104857600
18/10/08 19:26:11 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214396(104857584); length = 1/6553600
18/10/08 19:26:11 INFO mapred.MapTask: Finished spill 0
18/10/08 19:26:11 INFO mapred.Task: Task:attempt_local897460502_0001_m_000005_0 is done. And is in the process of committing
18/10/08 19:26:11 INFO mapred.LocalJobRunner: map
18/10/08 19:26:11 INFO mapred.Task: Task 'attempt_local897460502_0001_m_000005_0' done.
18/10/08 19:26:11 INFO mapred.Task: Final Counters for attempt_local897460502_0001_m_000005_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=189921
        FILE: Number of bytes written=557525
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=61
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=15
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=1
        Map output records=1
        Map output bytes=45
        Map output materialized bytes=59
        Input split bytes=105
        Combine input records=0
        Spilled Records=1
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=11
        Total committed heap usage (bytes)=525336576
    File Input Format Counters 
        Bytes Read=0
18/10/08 19:26:11 INFO mapred.LocalJobRunner: Finishing task: attempt_local897460502_0001_m_000005_0
18/10/08 19:26:11 INFO mapred.LocalJobRunner: map task executor complete.
18/10/08 19:26:11 INFO mapred.LocalJobRunner: Waiting for reduce tasks
18/10/08 19:26:11 INFO mapred.LocalJobRunner: Starting task: attempt_local897460502_0001_r_000000_0
18/10/08 19:26:11 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:26:11 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:26:11 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:26:11 INFO mapred.ReduceTask: Using ShuffleConsumerPlugin: org.apache.hadoop.mapreduce.task.reduce.Shuffle@4060f87e
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: MergerManager: memoryLimit=367735584, maxSingleShuffleLimit=91933896, mergeThreshold=242705488, ioSortFactor=10, memToMemMergeOutputsThreshold=10
18/10/08 19:26:11 INFO reduce.EventFetcher: attempt_local897460502_0001_r_000000_0 Thread started: EventFetcher for fetching Map Completion Events
18/10/08 19:26:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local897460502_0001_m_000002_0 decomp: 59 len: 63 to MEMORY
18/10/08 19:26:11 INFO reduce.InMemoryMapOutput: Read 59 bytes from map-output for attempt_local897460502_0001_m_000002_0
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 59, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->59
18/10/08 19:26:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local897460502_0001_m_000005_0 decomp: 49 len: 53 to MEMORY
18/10/08 19:26:11 INFO reduce.InMemoryMapOutput: Read 49 bytes from map-output for attempt_local897460502_0001_m_000005_0
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 49, inMemoryMapOutputs.size() -> 2, commitMemory -> 59, usedMemory ->108
18/10/08 19:26:11 WARN io.ReadaheadPool: Failed readahead on ifile
EBADF: Bad file descriptor
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posix_fadvise(Native Method)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posixFadviseIfPossible(NativeIO.java:267)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX$CacheManipulator.posixFadviseIfPossible(NativeIO.java:146)
    at org.apache.hadoop.io.ReadaheadPool$ReadaheadRequestImpl.run(ReadaheadPool.java:208)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
    at java.lang.Thread.run(Thread.java:748)
18/10/08 19:26:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local897460502_0001_m_000004_0 decomp: 2 len: 6 to MEMORY
18/10/08 19:26:11 INFO reduce.InMemoryMapOutput: Read 2 bytes from map-output for attempt_local897460502_0001_m_000004_0
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 2, inMemoryMapOutputs.size() -> 3, commitMemory -> 108, usedMemory ->110
18/10/08 19:26:11 WARN io.ReadaheadPool: Failed readahead on ifile
EBADF: Bad file descriptor
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posix_fadvise(Native Method)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posixFadviseIfPossible(NativeIO.java:267)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX$CacheManipulator.posixFadviseIfPossible(NativeIO.java:146)
    at org.apache.hadoop.io.ReadaheadPool$ReadaheadRequestImpl.run(ReadaheadPool.java:208)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
    at java.lang.Thread.run(Thread.java:748)
18/10/08 19:26:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local897460502_0001_m_000001_0 decomp: 2 len: 6 to MEMORY
18/10/08 19:26:11 INFO reduce.InMemoryMapOutput: Read 2 bytes from map-output for attempt_local897460502_0001_m_000001_0
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 2, inMemoryMapOutputs.size() -> 4, commitMemory -> 110, usedMemory ->112
18/10/08 19:26:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local897460502_0001_m_000000_0 decomp: 70 len: 74 to MEMORY
18/10/08 19:26:11 INFO reduce.InMemoryMapOutput: Read 70 bytes from map-output for attempt_local897460502_0001_m_000000_0
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 70, inMemoryMapOutputs.size() -> 5, commitMemory -> 112, usedMemory ->182
18/10/08 19:26:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local897460502_0001_m_000003_0 decomp: 2 len: 6 to MEMORY
18/10/08 19:26:11 INFO reduce.InMemoryMapOutput: Read 2 bytes from map-output for attempt_local897460502_0001_m_000003_0
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 2, inMemoryMapOutputs.size() -> 6, commitMemory -> 182, usedMemory ->184
18/10/08 19:26:11 INFO reduce.EventFetcher: EventFetcher is interrupted.. Returning
18/10/08 19:26:11 INFO mapred.LocalJobRunner: 6 / 6 copied.
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: finalMerge called with 6 in-memory map-outputs and 0 on-disk map-outputs
18/10/08 19:26:11 INFO mapred.Merger: Merging 6 sorted segments
18/10/08 19:26:11 INFO mapred.Merger: Down to the last merge-pass, with 3 segments left of total size: 49 bytes
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: Merged 6 segments, 184 bytes to disk to satisfy reduce memory limit
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: Merging 1 files, 178 bytes from disk
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: Merging 0 segments, 0 bytes from memory into reduce
18/10/08 19:26:11 INFO mapred.Merger: Merging 1 sorted segments
18/10/08 19:26:11 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 131 bytes
18/10/08 19:26:11 INFO mapred.LocalJobRunner: 6 / 6 copied.
18/10/08 19:26:11 INFO mapreduce.Job: Job job_local897460502_0001 running in uber mode : false
18/10/08 19:26:11 INFO mapreduce.Job:  map 100% reduce 0%
18/10/08 19:26:11 INFO Configuration.deprecation: mapred.skip.on is deprecated. Instead, use mapreduce.job.skiprecords
18/10/08 19:26:11 INFO mapred.Task: Task:attempt_local897460502_0001_r_000000_0 is done. And is in the process of committing
18/10/08 19:26:11 INFO mapred.LocalJobRunner: 6 / 6 copied.
18/10/08 19:26:11 INFO mapred.Task: Task attempt_local897460502_0001_r_000000_0 is allowed to commit now
18/10/08 19:26:11 INFO output.FileOutputCommitter: Saved output of task 'attempt_local897460502_0001_r_000000_0' to hdfs://localhost/user/storm/output/_temporary/0/task_local897460502_0001_r_000000
18/10/08 19:26:11 INFO mapred.LocalJobRunner: reduce > reduce
18/10/08 19:26:11 INFO mapred.Task: Task 'attempt_local897460502_0001_r_000000_0' done.
18/10/08 19:26:11 INFO mapred.Task: Final Counters for attempt_local897460502_0001_r_000000_0: Counters: 29
    File System Counters
        FILE: Number of bytes read=190850
        FILE: Number of bytes written=557703
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=61
        HDFS: Number of bytes written=277
        HDFS: Number of read operations=18
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=3
    Map-Reduce Framework
        Combine input records=0
        Combine output records=0
        Reduce input groups=3
        Reduce shuffle bytes=208
        Reduce input records=3
        Reduce output records=3
        Spilled Records=3
        Shuffled Maps =6
        Failed Shuffles=0
        Merged Map outputs=6
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=525336576
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Output Format Counters 
        Bytes Written=277
18/10/08 19:26:11 INFO mapred.LocalJobRunner: Finishing task: attempt_local897460502_0001_r_000000_0
18/10/08 19:26:11 INFO mapred.LocalJobRunner: Starting task: attempt_local897460502_0001_r_000001_0
18/10/08 19:26:11 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:26:11 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:26:11 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:26:11 INFO mapred.ReduceTask: Using ShuffleConsumerPlugin: org.apache.hadoop.mapreduce.task.reduce.Shuffle@2bacd714
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: MergerManager: memoryLimit=367735584, maxSingleShuffleLimit=91933896, mergeThreshold=242705488, ioSortFactor=10, memToMemMergeOutputsThreshold=10
18/10/08 19:26:11 INFO reduce.EventFetcher: attempt_local897460502_0001_r_000001_0 Thread started: EventFetcher for fetching Map Completion Events
18/10/08 19:26:11 INFO reduce.LocalFetcher: localfetcher#2 about to shuffle output of map attempt_local897460502_0001_m_000002_0 decomp: 2 len: 6 to MEMORY
18/10/08 19:26:11 INFO reduce.InMemoryMapOutput: Read 2 bytes from map-output for attempt_local897460502_0001_m_000002_0
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 2, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->2
18/10/08 19:26:11 INFO reduce.LocalFetcher: localfetcher#2 about to shuffle output of map attempt_local897460502_0001_m_000005_0 decomp: 2 len: 6 to MEMORY
18/10/08 19:26:11 INFO reduce.InMemoryMapOutput: Read 2 bytes from map-output for attempt_local897460502_0001_m_000005_0
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 2, inMemoryMapOutputs.size() -> 2, commitMemory -> 2, usedMemory ->4
18/10/08 19:26:11 INFO reduce.LocalFetcher: localfetcher#2 about to shuffle output of map attempt_local897460502_0001_m_000004_0 decomp: 59 len: 63 to MEMORY
18/10/08 19:26:11 INFO reduce.InMemoryMapOutput: Read 59 bytes from map-output for attempt_local897460502_0001_m_000004_0
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 59, inMemoryMapOutputs.size() -> 3, commitMemory -> 4, usedMemory ->63
18/10/08 19:26:11 INFO reduce.LocalFetcher: localfetcher#2 about to shuffle output of map attempt_local897460502_0001_m_000001_0 decomp: 59 len: 63 to MEMORY
18/10/08 19:26:11 INFO reduce.InMemoryMapOutput: Read 59 bytes from map-output for attempt_local897460502_0001_m_000001_0
18/10/08 19:26:11 WARN io.ReadaheadPool: Failed readahead on ifile
EBADF: Bad file descriptor
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posix_fadvise(Native Method)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posixFadviseIfPossible(NativeIO.java:267)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX$CacheManipulator.posixFadviseIfPossible(NativeIO.java:146)
    at org.apache.hadoop.io.ReadaheadPool$ReadaheadRequestImpl.run(ReadaheadPool.java:208)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
    at java.lang.Thread.run(Thread.java:748)
18/10/08 19:26:11 WARN io.ReadaheadPool: Failed readahead on ifile
EBADF: Bad file descriptor
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posix_fadvise(Native Method)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posixFadviseIfPossible(NativeIO.java:267)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX$CacheManipulator.posixFadviseIfPossible(NativeIO.java:146)
    at org.apache.hadoop.io.ReadaheadPool$ReadaheadRequestImpl.run(ReadaheadPool.java:208)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
    at java.lang.Thread.run(Thread.java:748)
18/10/08 19:26:11 WARN io.ReadaheadPool: Failed readahead on ifile
EBADF: Bad file descriptor
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posix_fadvise(Native Method)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posixFadviseIfPossible(NativeIO.java:267)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX$CacheManipulator.posixFadviseIfPossible(NativeIO.java:146)
    at org.apache.hadoop.io.ReadaheadPool$ReadaheadRequestImpl.run(ReadaheadPool.java:208)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
    at java.lang.Thread.run(Thread.java:748)
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 59, inMemoryMapOutputs.size() -> 4, commitMemory -> 63, usedMemory ->122
18/10/08 19:26:11 INFO reduce.LocalFetcher: localfetcher#2 about to shuffle output of map attempt_local897460502_0001_m_000000_0 decomp: 2 len: 6 to MEMORY
18/10/08 19:26:11 INFO reduce.InMemoryMapOutput: Read 2 bytes from map-output for attempt_local897460502_0001_m_000000_0
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 2, inMemoryMapOutputs.size() -> 5, commitMemory -> 122, usedMemory ->124
18/10/08 19:26:11 INFO reduce.LocalFetcher: localfetcher#2 about to shuffle output of map attempt_local897460502_0001_m_000003_0 decomp: 59 len: 63 to MEMORY
18/10/08 19:26:11 INFO reduce.InMemoryMapOutput: Read 59 bytes from map-output for attempt_local897460502_0001_m_000003_0
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 59, inMemoryMapOutputs.size() -> 6, commitMemory -> 124, usedMemory ->183
18/10/08 19:26:11 INFO reduce.EventFetcher: EventFetcher is interrupted.. Returning
18/10/08 19:26:11 INFO mapred.LocalJobRunner: 6 / 6 copied.
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: finalMerge called with 6 in-memory map-outputs and 0 on-disk map-outputs
18/10/08 19:26:11 INFO mapred.Merger: Merging 6 sorted segments
18/10/08 19:26:11 INFO mapred.Merger: Down to the last merge-pass, with 3 segments left of total size: 48 bytes
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: Merged 6 segments, 183 bytes to disk to satisfy reduce memory limit
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: Merging 1 files, 177 bytes from disk
18/10/08 19:26:11 INFO reduce.MergeManagerImpl: Merging 0 segments, 0 bytes from memory into reduce
18/10/08 19:26:11 INFO mapred.Merger: Merging 1 sorted segments
18/10/08 19:26:11 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 130 bytes
18/10/08 19:26:11 INFO mapred.LocalJobRunner: 6 / 6 copied.
18/10/08 19:26:11 INFO mapred.Task: Task:attempt_local897460502_0001_r_000001_0 is done. And is in the process of committing
18/10/08 19:26:11 INFO mapred.LocalJobRunner: 6 / 6 copied.
18/10/08 19:26:11 INFO mapred.Task: Task attempt_local897460502_0001_r_000001_0 is allowed to commit now
18/10/08 19:26:11 INFO output.FileOutputCommitter: Saved output of task 'attempt_local897460502_0001_r_000001_0' to hdfs://localhost/user/storm/output/_temporary/0/task_local897460502_0001_r_000001
18/10/08 19:26:11 INFO mapred.LocalJobRunner: reduce > reduce
18/10/08 19:26:11 INFO mapred.Task: Task 'attempt_local897460502_0001_r_000001_0' done.
18/10/08 19:26:11 INFO mapred.Task: Final Counters for attempt_local897460502_0001_r_000001_0: Counters: 29
    File System Counters
        FILE: Number of bytes read=191570
        FILE: Number of bytes written=557880
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=61
        HDFS: Number of bytes written=553
        HDFS: Number of read operations=21
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=5
    Map-Reduce Framework
        Combine input records=0
        Combine output records=0
        Reduce input groups=3
        Reduce shuffle bytes=207
        Reduce input records=3
        Reduce output records=3
        Spilled Records=3
        Shuffled Maps =6
        Failed Shuffles=0
        Merged Map outputs=6
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=525336576
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Output Format Counters 
        Bytes Written=276
18/10/08 19:26:11 INFO mapred.LocalJobRunner: Finishing task: attempt_local897460502_0001_r_000001_0
18/10/08 19:26:11 INFO mapred.LocalJobRunner: reduce task executor complete.
18/10/08 19:26:12 INFO mapreduce.Job:  map 100% reduce 100%
18/10/08 19:26:12 INFO mapreduce.Job: Job job_local897460502_0001 completed successfully
18/10/08 19:26:12 INFO mapreduce.Job: Counters: 35
    File System Counters
        FILE: Number of bytes read=1514711
        FILE: Number of bytes written=4458908
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=388
        HDFS: Number of bytes written=830
        HDFS: Number of read operations=99
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=14
    Map-Reduce Framework
        Map input records=6
        Map output records=6
        Map output bytes=331
        Map output materialized bytes=415
        Input split bytes=630
        Combine input records=0
        Combine output records=0
        Reduce input groups=6
        Reduce shuffle bytes=415
        Reduce input records=6
        Reduce output records=6
        Spilled Records=12
        Shuffled Maps =12
        Failed Shuffles=0
        Merged Map outputs=12
        GC time elapsed (ms)=32
        Total committed heap usage (bytes)=3788505088
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Input Format Counters 
        Bytes Read=61
    File Output Format Counters 
        Bytes Written=553
➜  hadoop-book git:(master) ✗ hadoop fs -ls output
Found 3 items
-rw-r--r--   1 storm supergroup          0 2018-10-08 19:26 output/_SUCCESS
-rw-r--r--   1 storm supergroup        277 2018-10-08 19:26 output/part-r-00000
-rw-r--r--   1 storm supergroup        276 2018-10-08 19:26 output/part-r-00001
➜  hadoop-book git:(master) ✗ hadoop fs -text output/part-r-00000
hdfs://localhost/user/storm/smallfiles/a    61 61 61 61 61 61 61 61 61 61 0a 61 61 61 61 61 61 61 61 61 61
hdfs://localhost/user/storm/smallfiles/c    63 63 63 63 63 63 63 63 63 63
hdfs://localhost/user/storm/smallfiles/e    
➜  hadoop-book git:(master) ✗ hadoop fs -text output/part-r-00001
hdfs://localhost/user/storm/smallfiles/b    62 62 62 62 62 62 62 62 62 62
hdfs://localhost/user/storm/smallfiles/d    64 64 64 64 64 64 64 64 64 64
hdfs://localhost/user/storm/smallfiles/f    66 66 66 66 66 66 66 66 66 66
```

例8-5 应用MultipleOutputs，根据stationID把数据集分成多个文件

```
➜  hadoop-book git:(master) ✗ hadoop PartitionByStationUsingMultipleOutputs ncdc-all output
18/10/08 19:41:33 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
18/10/08 19:41:33 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
18/10/08 19:41:33 INFO input.FileInputFormat: Total input files to process : 2
18/10/08 19:41:33 INFO mapreduce.JobSubmitter: number of splits:2
18/10/08 19:41:33 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local1332074937_0001
18/10/08 19:41:33 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
18/10/08 19:41:33 INFO mapreduce.Job: Running job: job_local1332074937_0001
18/10/08 19:41:33 INFO mapred.LocalJobRunner: OutputCommitter set in config null
18/10/08 19:41:33 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:41:33 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:41:33 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
18/10/08 19:41:33 INFO mapred.LocalJobRunner: Waiting for map tasks
18/10/08 19:41:33 INFO mapred.LocalJobRunner: Starting task: attempt_local1332074937_0001_m_000000_0
18/10/08 19:41:33 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:41:33 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:41:33 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:41:33 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/ncdc-all/1902.gz:0+74105
18/10/08 19:41:34 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 19:41:34 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 19:41:34 INFO mapred.MapTask: soft limit at 83886080
18/10/08 19:41:34 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 19:41:34 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 19:41:34 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 19:41:34 INFO zlib.ZlibFactory: Successfully loaded & initialized native-zlib library
18/10/08 19:41:34 INFO compress.CodecPool: Got brand-new decompressor [.gz]
18/10/08 19:41:34 INFO mapred.LocalJobRunner: 
18/10/08 19:41:34 INFO mapred.MapTask: Starting flush of map output
18/10/08 19:41:34 INFO mapred.MapTask: Spilling map output
18/10/08 19:41:34 INFO mapred.MapTask: bufstart = 0; bufend = 980862; bufvoid = 104857600
18/10/08 19:41:34 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26188140(104752560); length = 26257/6553600
18/10/08 19:41:34 INFO mapred.MapTask: Finished spill 0
18/10/08 19:41:34 INFO mapred.Task: Task:attempt_local1332074937_0001_m_000000_0 is done. And is in the process of committing
18/10/08 19:41:34 INFO mapred.LocalJobRunner: map
18/10/08 19:41:34 INFO mapred.Task: Task 'attempt_local1332074937_0001_m_000000_0' done.
18/10/08 19:41:34 INFO mapred.Task: Final Counters for attempt_local1332074937_0001_m_000000_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=186721
        FILE: Number of bytes written=1558242
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=74105
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=5
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=6565
        Map output records=6565
        Map output bytes=980862
        Map output materialized bytes=1000537
        Input split bytes=109
        Combine input records=0
        Spilled Records=6565
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=340262912
    File Input Format Counters 
        Bytes Read=74105
18/10/08 19:41:34 INFO mapred.LocalJobRunner: Finishing task: attempt_local1332074937_0001_m_000000_0
18/10/08 19:41:34 INFO mapred.LocalJobRunner: Starting task: attempt_local1332074937_0001_m_000001_0
18/10/08 19:41:34 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:41:34 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:41:34 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:41:34 INFO mapred.MapTask: Processing split: hdfs://localhost/user/storm/ncdc-all/1901.gz:0+73867
18/10/08 19:41:34 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
18/10/08 19:41:34 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
18/10/08 19:41:34 INFO mapred.MapTask: soft limit at 83886080
18/10/08 19:41:34 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
18/10/08 19:41:34 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
18/10/08 19:41:34 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
18/10/08 19:41:34 INFO mapred.LocalJobRunner: 
18/10/08 19:41:34 INFO mapred.MapTask: Starting flush of map output
18/10/08 19:41:34 INFO mapred.MapTask: Spilling map output
18/10/08 19:41:34 INFO mapred.MapTask: bufstart = 0; bufend = 980089; bufvoid = 104857600
18/10/08 19:41:34 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26188140(104752560); length = 26257/6553600
18/10/08 19:41:34 INFO mapred.MapTask: Finished spill 0
18/10/08 19:41:34 INFO mapred.Task: Task:attempt_local1332074937_0001_m_000001_0 is done. And is in the process of committing
18/10/08 19:41:34 INFO mapred.LocalJobRunner: map
18/10/08 19:41:34 INFO mapred.Task: Task 'attempt_local1332074937_0001_m_000001_0' done.
18/10/08 19:41:34 INFO mapred.Task: Final Counters for attempt_local1332074937_0001_m_000001_0: Counters: 22
    File System Counters
        FILE: Number of bytes read=186958
        FILE: Number of bytes written=2558053
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=147972
        HDFS: Number of bytes written=0
        HDFS: Number of read operations=7
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=1
    Map-Reduce Framework
        Map input records=6565
        Map output records=6565
        Map output bytes=980089
        Map output materialized bytes=999779
        Input split bytes=109
        Combine input records=0
        Spilled Records=6565
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=0
        Total committed heap usage (bytes)=445644800
    File Input Format Counters 
        Bytes Read=73867
18/10/08 19:41:34 INFO mapred.LocalJobRunner: Finishing task: attempt_local1332074937_0001_m_000001_0
18/10/08 19:41:34 INFO mapred.LocalJobRunner: map task executor complete.
18/10/08 19:41:34 INFO mapred.LocalJobRunner: Waiting for reduce tasks
18/10/08 19:41:34 INFO mapred.LocalJobRunner: Starting task: attempt_local1332074937_0001_r_000000_0
18/10/08 19:41:34 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:41:34 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:41:34 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
18/10/08 19:41:34 INFO mapred.ReduceTask: Using ShuffleConsumerPlugin: org.apache.hadoop.mapreduce.task.reduce.Shuffle@5af43330
18/10/08 19:41:34 INFO reduce.MergeManagerImpl: MergerManager: memoryLimit=334338464, maxSingleShuffleLimit=83584616, mergeThreshold=220663392, ioSortFactor=10, memToMemMergeOutputsThreshold=10
18/10/08 19:41:34 INFO reduce.EventFetcher: attempt_local1332074937_0001_r_000000_0 Thread started: EventFetcher for fetching Map Completion Events
18/10/08 19:41:34 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1332074937_0001_m_000001_0 decomp: 999775 len: 999779 to MEMORY
18/10/08 19:41:34 INFO reduce.InMemoryMapOutput: Read 999775 bytes from map-output for attempt_local1332074937_0001_m_000001_0
18/10/08 19:41:34 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 999775, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->999775
18/10/08 19:41:34 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1332074937_0001_m_000000_0 decomp: 1000533 len: 1000537 to MEMORY
18/10/08 19:41:34 INFO reduce.InMemoryMapOutput: Read 1000533 bytes from map-output for attempt_local1332074937_0001_m_000000_0
18/10/08 19:41:34 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 1000533, inMemoryMapOutputs.size() -> 2, commitMemory -> 999775, usedMemory ->2000308
18/10/08 19:41:34 INFO reduce.EventFetcher: EventFetcher is interrupted.. Returning
18/10/08 19:41:34 INFO mapred.LocalJobRunner: 2 / 2 copied.
18/10/08 19:41:34 INFO reduce.MergeManagerImpl: finalMerge called with 2 in-memory map-outputs and 0 on-disk map-outputs
18/10/08 19:41:34 WARN io.ReadaheadPool: Failed readahead on ifile
EBADF: Bad file descriptor
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posix_fadvise(Native Method)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX.posixFadviseIfPossible(NativeIO.java:267)
    at org.apache.hadoop.io.nativeio.NativeIO$POSIX$CacheManipulator.posixFadviseIfPossible(NativeIO.java:146)
    at org.apache.hadoop.io.ReadaheadPool$ReadaheadRequestImpl.run(ReadaheadPool.java:208)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
    at java.lang.Thread.run(Thread.java:748)
18/10/08 19:41:34 INFO mapred.Merger: Merging 2 sorted segments
18/10/08 19:41:34 INFO mapred.Merger: Down to the last merge-pass, with 2 segments left of total size: 2000276 bytes
18/10/08 19:41:34 INFO reduce.MergeManagerImpl: Merged 2 segments, 2000308 bytes to disk to satisfy reduce memory limit
18/10/08 19:41:34 INFO reduce.MergeManagerImpl: Merging 1 files, 2000310 bytes from disk
18/10/08 19:41:34 INFO reduce.MergeManagerImpl: Merging 0 segments, 0 bytes from memory into reduce
18/10/08 19:41:34 INFO mapred.Merger: Merging 1 sorted segments
18/10/08 19:41:34 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 2000290 bytes
18/10/08 19:41:34 INFO mapred.LocalJobRunner: 2 / 2 copied.
18/10/08 19:41:34 INFO mapreduce.Job: Job job_local1332074937_0001 running in uber mode : false
18/10/08 19:41:34 INFO mapreduce.Job:  map 100% reduce 0%
18/10/08 19:41:34 INFO Configuration.deprecation: mapred.skip.on is deprecated. Instead, use mapreduce.job.skiprecords
18/10/08 19:41:34 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:41:34 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:41:34 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:41:34 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:41:35 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:41:35 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:41:35 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:41:35 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:41:35 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:41:35 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:41:35 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
18/10/08 19:41:35 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
18/10/08 19:41:36 INFO mapred.Task: Task:attempt_local1332074937_0001_r_000000_0 is done. And is in the process of committing
18/10/08 19:41:36 INFO mapred.LocalJobRunner: 2 / 2 copied.
18/10/08 19:41:36 INFO mapred.Task: Task attempt_local1332074937_0001_r_000000_0 is allowed to commit now
18/10/08 19:41:36 INFO output.FileOutputCommitter: Saved output of task 'attempt_local1332074937_0001_r_000000_0' to hdfs://localhost/user/storm/output/_temporary/0/task_local1332074937_0001_r_000000
18/10/08 19:41:36 INFO mapred.LocalJobRunner: reduce > reduce
18/10/08 19:41:36 INFO mapred.Task: Task 'attempt_local1332074937_0001_r_000000_0' done.
18/10/08 19:41:36 INFO mapred.Task: Final Counters for attempt_local1332074937_0001_r_000000_0: Counters: 29
    File System Counters
        FILE: Number of bytes read=4187648
        FILE: Number of bytes written=4558363
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=147972
        HDFS: Number of bytes written=1777168
        HDFS: Number of read operations=10
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=9
    Map-Reduce Framework
        Combine input records=0
        Combine output records=0
        Reduce input groups=6
        Reduce shuffle bytes=2000316
        Reduce input records=13130
        Reduce output records=0
        Spilled Records=13130
        Shuffled Maps =2
        Failed Shuffles=0
        Merged Map outputs=2
        GC time elapsed (ms)=17
        Total committed heap usage (bytes)=472383488
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Output Format Counters 
        Bytes Written=0
18/10/08 19:41:36 INFO mapred.LocalJobRunner: Finishing task: attempt_local1332074937_0001_r_000000_0
18/10/08 19:41:36 INFO mapred.LocalJobRunner: reduce task executor complete.
18/10/08 19:41:36 INFO mapreduce.Job:  map 100% reduce 100%
18/10/08 19:41:36 INFO mapreduce.Job: Job job_local1332074937_0001 completed successfully
18/10/08 19:41:36 INFO mapreduce.Job: Counters: 35
    File System Counters
        FILE: Number of bytes read=4561327
        FILE: Number of bytes written=8674658
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=370049
        HDFS: Number of bytes written=1777168
        HDFS: Number of read operations=22
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=11
    Map-Reduce Framework
        Map input records=13130
        Map output records=13130
        Map output bytes=1960951
        Map output materialized bytes=2000316
        Input split bytes=218
        Combine input records=0
        Combine output records=0
        Reduce input groups=6
        Reduce shuffle bytes=2000316
        Reduce input records=13130
        Reduce output records=0
        Spilled Records=26260
        Shuffled Maps =2
        Failed Shuffles=0
        Merged Map outputs=2
        GC time elapsed (ms)=17
        Total committed heap usage (bytes)=1258291200
    Shuffle Errors
        BAD_ID=0
        CONNECTION=0
        IO_ERROR=0
        WRONG_LENGTH=0
        WRONG_MAP=0
        WRONG_REDUCE=0
    File Input Format Counters 
        Bytes Read=147972
    File Output Format Counters 
        Bytes Written=0
➜  hadoop-book git:(master) ✗ hadoop fs -ls output 
Found 8 items
-rw-r--r--   1 storm supergroup     296589 2018-10-08 19:41 output/029070-99999-r-00000
-rw-r--r--   1 storm supergroup     295244 2018-10-08 19:41 output/029500-99999-r-00000
-rw-r--r--   1 storm supergroup     297135 2018-10-08 19:41 output/029600-99999-r-00000
-rw-r--r--   1 storm supergroup     295100 2018-10-08 19:41 output/029720-99999-r-00000
-rw-r--r--   1 storm supergroup     296727 2018-10-08 19:41 output/029810-99999-r-00000
-rw-r--r--   1 storm supergroup     296373 2018-10-08 19:41 output/227070-99999-r-00000
-rw-r--r--   1 storm supergroup          0 2018-10-08 19:41 output/_SUCCESS
-rw-r--r--   1 storm supergroup          0 2018-10-08 19:41 output/part-r-00000
➜  hadoop-book git:(master) ✗ hadoop fs -text output/029070-99999-r-00000 | head
0029029070999991901010106004+64333+023450FM-12+000599999V0202701N015919999999N0000001N9-00781+99999102001ADDGF108991999999999999999999
0029029070999991901010113004+64333+023450FM-12+000599999V0202901N008219999999N0000001N9-00721+99999102001ADDGF104991999999999999999999
0029029070999991901010120004+64333+023450FM-12+000599999V0209991C000019999999N0000001N9-00941+99999102001ADDGF108991999999999999999999
0029029070999991901010206004+64333+023450FM-12+000599999V0201801N008219999999N0000001N9-00611+99999101831ADDGF108991999999999999999999
0029029070999991901010213004+64333+023450FM-12+000599999V0201801N009819999999N0000001N9-00561+99999101761ADDGF108991999999999999999999
0029029070999991901010220004+64333+023450FM-12+000599999V0201801N009819999999N0000001N9-00281+99999101751ADDGF108991999999999999999999
0029029070999991901010306004+64333+023450FM-12+000599999V0202001N009819999999N0000001N9-00671+99999101701ADDGF106991999999999999999999
0029029070999991901010313004+64333+023450FM-12+000599999V0202301N011819999999N0000001N9-00331+99999101741ADDGF108991999999999999999999
0029029070999991901010320004+64333+023450FM-12+000599999V0202301N011819999999N0000001N9-00281+99999101741ADDGF108991999999999999999999
0029029070999991901010406004+64333+023450FM-12+000599999V0209991C000019999999N0000001N9-00331+99999102311ADDGF108991999999999999999999
```




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


TaskletStep Oriented Processing in Spring Batch

Many enterprise applications require batch processing to process billions of transactions every day. These big transaction sets have to be processed without performance problems. Spring Batch is a lightweight and robust batch framework to process these big data sets.

Spring Batch offers 'TaskletStep Oriented' and 'Chunk Oriented' processing style. In this article, TaskletStep Oriented Processing Model is explained.

Let us investigate fundamental Spring Batch components :

Job : An entity that encapsulates an entire batch process. Step and Tasklets are defined under a Job

Step : A domain object that encapsulates an independent, sequential phase of a batch job.

JobInstance : Batch domain object representing a uniquely identifiable job run - it's identity is given by the pair Job and JobParameters.

JobParameters : Value object representing runtime parameters to a batch job. 

JobExecution : A JobExecution refers to the technical concept of a single attempt to run a Job. An execution may end in failure or success, but the JobInstance corresponding to a given execution will not be considered complete unless the execution completes successfully.

JobRepository : An interface which responsible for persistence of batch meta-data entities. In the following sample, an in-memory repository is used via MapJobRepositoryFactoryBean.

JobLauncher : An interface exposing run method, which launches and controls the defined jobs. 

TaskLet : An interface exposing execute method, which will be a called repeatedly until it either returns RepeatStatus.FINISHED or throws an exception to signal a failure. It is used when both readers and writers are not required as the following sample.

Used Technologies : JDK 1.7.0_09, Spring 3.1.3, Spring Batch 2.1.9 and Maven 3.0.4
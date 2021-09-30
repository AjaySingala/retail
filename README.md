From the project’s root folder (retail), compile and package the project:
$ cd ~/retail
$ sbt compile
$ sbt package

To run with sbt:
1)	Change path in application.properties from "/user/hdoop" to "/home/hadoop" (for local file)
2)	Then:
$ sbt compile
$ sbt package
$ sbt "run dev"

To run with spark-submit:
1) Change path in application.properties from "/home/hdoop" to "/user/hadoop" (for HDFS)
2) Then:
$ spark-submit --class retail_db.GetDailyProductRevenue \
	--packages com.typesafe:config:1.3.2 \
	target/scala-2.12/retail_2.12-0.1.0-SNAPSHOT.jar dev


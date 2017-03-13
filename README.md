#### This is a simple testing repo
----------------------------------
This project can be open in vscode with proper plugin :)

### Run:
--------
> sbt package

> spark-submit --class "SimpleApp" --master local target/scala-2.10/simple-project_2.10-1.0.jar

## Assume:
Resource Manager: http://localhost:50070
JobTracker: http://localhost:8088
Specific Node Information: http://localhost:8042
Hdfs port 9000

[Must do]Setup hadoop port for datanode etc:
https://amodernstory.com/2014/09/23/installing-hadoop-on-mac-osx-yosemite/

Create file:
------------

> hdfs dfs -mkdir -p /user/mike
> hdfs dfs -ls /user
> hdfs dfs -put README.md /user/mike/readme.md

Snippet:
--------
$ yarn  // For resource management more information than the web interface. 
$ mapred  // Detailed information about jobs

if [ -f "${HADOOP_HDFS_HOME}"/sbin/start-dfs.sh ]; then
  "${HADOOP_HDFS_HOME}"/sbin/start-dfs.sh --config $HADOOP_CONF_DIR
fi

# start yarn daemons if yarn is present
if [ -f "${HADOOP_YARN_HOME}"/sbin/start-yarn.sh ]; then
  "${HADOOP_YARN_HOME}"/sbin/start-yarn.sh --config $HADOOP_CONF_DIR
fi


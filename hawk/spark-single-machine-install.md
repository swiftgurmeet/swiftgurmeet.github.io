---
layout: page
title: "Single Machine Install"
permalink: /singlemc/
---

## Single Machine Install

1. Install JDK 8
1. set JAVA_HOME appropriately
1. Download Apache Spark pre build with Hadoop
1. Untar somewhere, say, /opt
1. ln -s spark-1.5.2-bin-hadoop2.4 spark
1. set SPARK_HOME to /opt/spark
1. add $SPARK_HOME/bin to $PATH
1. Test by running
   `spark-shell`

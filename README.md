Kafka Manager
=============

A tool for managing [Apache Kafka](http://kafka.apache.org).


compiler version for direct usage 
Requirements
------------

1. [Kafka 0.8.*.* or 0.9.*.* or 0.10.*.*](http://kafka.apache.org/downloads.html)
2. Java 8+

Configuration
-------------

The minimum configuration is the zookeeper hosts which are to be used for kafka manager state.
This can be found in the application.conf file in conf directory.  The same file will be packaged
in the distribution zip file; you may modify settings after unzipping the file on the desired server.

    kafka-manager.zkhosts="my.zookeeper.host.com:2181"

You can specify multiple zookeeper hosts by comma delimiting them, like so:

    kafka-manager.zkhosts="my.zookeeper.host.com:2181,other.zookeeper.host.com:2181"

Alternatively, use the environment variable `ZK_HOSTS` if you don't want to hardcode any values.

    ZK_HOSTS="my.zookeeper.host.com:2181"

Starting the service
--------------------

After extracting the produced zipfile, and changing the working directory to it, you can
run the service like this:

    $ bin/kafka-manager

By default, it will choose port 9000. This is overridable, as is the location of the
configuration file. For example:

    $ bin/kafka-manager -Dconfig.file=/path/to/application.conf -Dhttp.port=8080

Again, if java is not in your path, or you need to run against a different version of java,
add the -java-home option as follows:

    $ bin/kafka-manager -java-home /usr/local/oracle-java-8

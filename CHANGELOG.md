Changes
=======
# 5.0.0 / Unreleased

### Integrations affected

* NTP

### Changes
* [FEATURE] Add a NTP Service check. See [#971][]

# 4.4.0 / 06-24-2014

### Integrations affected

* Docker
* Redis
* Memcached
* MySQL
* PostgreSQL

### Changes
* [BUGFIX] Docker: Don't raise Exception if we fail to get some Docker croup info. See [#981][]
* [BUGFIX] Docker: Don't raise Exception if no Docker containers are running. See [#980][]
* [BUGFIX] Docker: Fix integration timeout issue. See [#963][]
* [ENHANCEMENT] Let the possibility to disable metadata collection from 169.254.169.254. See [#975][]
* [FEATURE] Redis: Add a metric to track key length. See [#962][]
* [FEATURE] MySQL: Collect more metrics. See [#972][]
* [BUGFIX] MySQL: Only collect metrics from /proc on linux machines. See [#984][]
* [BUGFIX] PostgreSQL: Handle negative replication delay. See [#977][]
* [ENHANCEMENT] Collect more Memcached stats. See [#982][]
* [BUGFIX] Remove Content-Length header in CONNECT HTTP Requests (when using a proxy), as CONNECT Requests shouldn't have that header and some proxies don't support it.


# 4.3.1 / 06-03-2014

**Linux or Source Install only**

### Integrations affected
* Docker
* HAProxy

### Changes
* [IMPROVEMENT] Don't collect Docker total_ metrics by default. See [#964][]
* [BUGFIX] Report Docker CPU metrics as rate. See [#964][]
* [BUGFIX] Add HAProxy reporter name in HAProxy event's titles. See [#960][]

# 4.3.0 / 05-22-2014

### Integrations affected
* MongoDB
* Process
* CouchDB
* Docker
* HAProxy
* Marathon
* Memcached
* Mesos
* MySQL
* TokuMX
* ElasticSearch
* Network

#### Changes
* [BUGFIX] Fix incorrect open file descriptors metric name in process check: See [#904][]. Warning: As the metric name will be changed. Your dashboards will have to be updated.
* [FEATURE] Add some mongo2.2+ metrics to check: See [#951][] (Thanks to [@ckrough][])
* [FEATURE] Collect checks statuses: See [#922]
* [FEATURE] CouchDB: Support basic authentication: See [#930]
* [FEATURE] Docker: Support Docker 0.11
* [FEATURE] Docker: Collect events from the events api
* [FEATURE] HAProxy: Allow collection of metrics per host with the option `collect_status_metrics_by_host`: See [#935]
* [BUGFIX] HAProxy: Fix inaccuracy of count_per_status metric: See [#940]
* [BUGFIX] HAProxy: Update event's titles: See [#935]
* [FEATURE] Add Marathon integration: See [#921][] (Thanks to [@graemej][])
* [FEATURE] Add Mesos integration: See [#919][] (Thanks to [@graemej][])
* [FEATURE] Memcached: Add delete_misses/delete_hits: See [#928][] (Thanks to [@arthurnn][])
* [BUGFIX] MySQL: Only collect MySQL metrics from /proc on unix machines: See [#947]
* [BUGFIX] MySQL: Fix duplicate metric bug: See [#899]
* [BUGFIX] Varnish: Fix a bug that was causing tags to be continuously added in some cases.
* [FEATURE] Add an option to disable Dogstastsd: See [#927]
* [FEATURE] Memcached: Add support for local unix socket connections: See [#891][] (Thanks to [@mike-lerch][])
* [FEATURE] Add TokuMX integration: See [#933][] (Thanks to [@leifwalsh][])
* [BUGFIX] ElasticSearch: Added correct GC metrics for ES 1.x: See [#900][] (Thanks to [@joningle][])
* [FEATURE] Network: Add additional metrics for TCP: See [#949][]

# 4.2.2 / 04-25-2014

**Windows Only**

### Integrations affected
* Redis

### Changes
* [FEATURE] Support Redis check on Windows: See [#917]

# 4.2.1 / 04-09-2014

### Integrations affected
* ElasticSearch
* Nginx
* Process
* Postgres

#### Changes
* [BUGFIX] Fix bug in Dogstatsd in the bucketing change: See [#894]
* [BUGFIX] Revert to the Simple HTTP Client by default in the forwarder as it's causing 599 in some cases. It's now configurable in datadog.conf
* [FEATURE] Support for OpenShift cartridges: See [#875]
* [PERFORMANCE] Compress Dogstatsd payloads: See [#893]
* [BUGFIX] Fix process check compatibility with psutil 2.0: See [#863]
* [FEATURE] Support additional NGINX Plus metrics: See [#876]
* [PERFORMANCE] Better handling of external clusters in Elasticsearch check: See [#883]
* [BUGFIX] Fix an issue that is causing a high number of tags for postgresql metrics when custom tags are enabled.


# 4.2.0 / 03-25-2014

### Integrations affected
* Couchbase
* Docker
* ElasticSearch
* HAProxy
* Kafka consumer
* Kafka server
* MongoDB
* MySQL
* PostgreSQL
* Process
* Google Compute Engine
* JMX Checks: Cassandra, Tomcat, Solr, ActiveMq, JMX, Kafka

#### Changes
* [PERFORMANCE] Disable pup by default
* [ENHANCEMENT] Use JMXFetch 0.3.0 ( [Changelog](https://github.com/DataDog/jmxfetch/blob/master/CHANGELOG.md) )
* [ENHANCEMENT] Metric limit for JMX Checks is raised to 350 metrics per instance
* [FEATURE] Add a "configtest" command alias of "configcheck": See [#838][]
* [FEATURE] Add a Docker integration: See [#844][] (Thanks to [@steeve][])
* [FEATURE] ElasticSearch: Support for newer versions (>= 0.90.10)
* [FEATURE] ElasticSearch: Add a metric to monitor cluster status: See [#827][] (Thanks to [@igor47][])
* [FEATURE] HAProxy: Add availability metrics: See [#834][] (Thanks to [@igor47][])
* [FEATURE] Add a Kafka consumer check (Requires python 2.6 or python 2.7): See [#810][]
* [FEATURE] Add a Kafka server check: See [#810][]
* [FEATURE] MongoDB: Support SSL connections to server: See [#848][]
* [FEATURE] Collect tags and hostname for Google Compute Engine hosts
* [FEATURE] PostgreSQL: Support check on Windows
* [ENHANCEMENT] Align the reporting of StatsD metrics to fixed time intervals for consistency in aggregation
* [PERFORMANCE] StatsD events are now batched: See [#852][]
* [PERFORMANCE] Add an optional timeout parameter to Couchbase integration: See [#826][]
* [PERFORMANCE] Use Tornado CurlAsyncHTTPClient by default over the SimpleHTTPClient
* [BUGFIX] MySQL: Fixed warning on SHOW SLAVE STATUS: See [#809][] (Thanks to [@ive][])
* [BUGFIX] PostgreSQL: Reset the connection if it seems broken: See [#784][]
* [BUGFIX] Process: Do not fail on older Linux Kernels: See [#849][]
* [BUGFIX]  Windows: Do not restart pup on windows if it's not enabled: See [#815][]
* [BUGFIX] JMX Checks: Properly ensure that only one instance of JMXFetch is running



# 4.1.0 / 2014-02-04

### Integrations affected
* PostgreSQL
* ElasticSearch
* Lighttpd
* Nginx
* HAProxy
* MongoDB
* Redis
* Varnish
* Couchbase

#### Changes
* [FEATURE] Support for older versions of psycopg2
* [FEATURE] New tool to help configuring JMX Checks: See http://docs.datadoghq.com/integrations/java/
* [FEATURE] Add basic authentication to Couchbase check [#787](https://github.com/DataDog/dd-agent/issues/787)
* [FEATURE] Add basic authentication to ElasticSearch check [#806](https://github.com/DataDog/dd-agent/issues/806)
* [FEATURE] Add basic authentication to Lighttpd check
* [FEATURE] Add basic authentication to Nginx check
* [FEATURE] Calculate used session percentage in HAProxy check [#752](https://github.com/DataDog/dd-agent/pull/752) (Thanks to [@walkeran](https://github.com/walkeran))
* [FEATURE] Add an HAProxy metric that counts the number of active backends [#729](https://github.com/DataDog/dd-agent/issues/729)
* [FEATURE] Turn SSL validation in http check into an option [#770](https://github.com/DataDog/dd-agent/issues/770)
* [FEATURE] Include tags in http service check [#780](https://github.com/DataDog/dd-agent/pull/780)
* [FEATURE] Add more metrics to MongoDB check for newer versions of MongoDB [#735](https://github.com/DataDog/dd-agent/issues/735)
* [FEATURE] Support multiple mongo instances in MongoDB check [08be06f4c](https://github.com/DataDog/dd-agent/commit/b860bdfa2d8e81131204a187bdd9c3908be06f4c)
* [FEATURE] Add more metrics to MySQL check [#72](https://github.com/DataDog/dd-agent/pull/726) (Thanks to [@skingry](https://github.com/skingry) and [@ronaldbradford](https://github.com/ronaldbradford))
* [FEATURE] Add per-table metrics to Postgresql check [#760](https://github.com/DataDog/dd-agent/pull/760)
* [FEATURE] Add more metrics in process check with newer version of psutil
* [FEATURE] Allow configuration of the Redis check using a unix socket path [#730](https://github.com/DataDog/dd-agent/issues/730)
* [FEATURE] Allow multiple instances of Varnish check [#490](https://github.com/DataDog/dd-agent/issues/490)
* [FEATURE] Add the ability to add tags to an elasticsearch instance [#790](https://github.com/DataDog/dd-agent/pull/790) (Thanks to [@clly](https://github.com/clly))
* [BUGFIX] Fix automatic start of the Agent on Windows [acf368c](https://github.com/DataDog/dd-agent/commit/5877fdf0f18911c9ead6c101d24b31f19acf368c)
* [BUGFIX] Fix Gunicorn check issue where it was failing to identify the process in some cases [#706](https://github.com/DataDog/dd-agent/issues/706)
* [BUGFIX] Don’t fail on archived builds in Jenkins check [#766](https://github.com/DataDog/dd-agent/pull/766) (Thanks [@imlucas](https://github.com/imlucas))

#### Details
https://github.com/DataDog/dd-agent/compare/4.0.2...4.1.0

# 4.0.2 / 2014-01-08

**Windows Only**

#### Changes
* [BUGFIX] Fix WMI Check

#### Details
https://github.com/DataDog/dd-agent/compare/4.0.0...4.0.2



# 4.0.1 / 2013-12-17

**Linux or Source Install only**

#### Changes
* [BUGFIX] Fix Postgresql check that was sending bad values in some cases.
* [BUGFIX] Fix replication lag calculation in MySql check.

#### Details
https://github.com/DataDog/dd-agent/compare/4.0.0...4.0.1

# 4.0.0 / 2013-12-16

**This is a major version. See platform-specific pages for detailed changes.**

#### Changes
- [FEATURE] Linux/Mac OS/Source install: Visit https://github.com/DataDog/dd-agent/wiki/Agent-4.0.0-for-Linux-,-Mac-OS-and-FreeBSD
- [FEATURE] Windows: Visit https://github.com/DataDog/dd-agent/wiki/Agent-4.0.0-for-Windows

#### Details
https://github.com/DataDog/dd-agent/compare/3.10.1...4.0.0

# 3.10.1 / 2013-11-06

**Linux or Source Install only**

#### Changes
* [BUGFIX] Fix Mongo Integration for newer versions of MongoDB [#677](https://github.com/DataDog/dd-agent/issues/677)
* [BUGFIX] Fix memory metrics for Mac Os X Mavericks
* [BUGFIX] Fix tagging issues for HTTP Check [8ab75](d1e09e3605f7c09177c5a6fb4f3e2b86a698ab75)
* [BUGFIX] Fix local issues  [4230](https://github.com/DataDog/dd-agent/commit/0d41c241a763bf8edbbb3419cda43f3ba1ad4230)

#### Details
https://github.com/DataDog/dd-agent/compare/3.10.0...3.10.1

# 3.11.0 / 2013-10-08

**Windows Only**

### Integrations Affected
* Cassandra
* Tomcat
* ActiveMQ
* SolR
* Java
* MySQL
* Riak

#### Changes
* [FEATURE] Make Cassandra, Tomcat, ActiveMQ, SolR, Java and MySQL integrations work on Windows
* [FEATURE] Make pup work on Windows
* [FEATURE] Add an additional metric to the Nginx integration [#665](https://github.com/DataDog/dd-agent/pull/665) (Thanks to [@dcrosta](https://github.com/dcrosta))
* [FEATURE] Add additional metrics to Riak metrics [#643](https://github.com/DataDog/dd-agent/pull/643) (Thanks to [@stefan-mees](https://github.com/stefan-mees))
* [BUGFIX] Fix Service checks on Windows  [#632](https://github.com/DataDog/dd-agent/issues/632)

#### Details
https://github.com/DataDog/dd-agent/compare/3.9.3...3.11.0

# 3.9.3 / 2013-09-11

**Windows Only**

### Integrations Affected
* SQL Server

#### Changes
* [FEATURE] Allow optional custom tags in SQL Server check ([#654](https://github.com/DataDog/dd-agent/pull/654))
* [BUGFIX] Fix log file location on Windows XP

#### Details
https://github.com/DataDog/dd-agent/compare/3.9.2...3.9.3


# 3.10.0 / 2013-09-06

**Linux or Source Install only**

### Integrations Affected
* HTTP Check
* Mongo
* MySQL
* Network
* Process

#### Changes
* [FEATURE] GUnicorn check [#619](https://github.com/DataDog/dd-agent/pull/619)
* [FEATURE] Dogstatsd Autorestart [#624](https://github.com/DataDog/dd-agent/pull/624)
* [FEATURE] Add tags to metrics collected by the HTTP Check  [#647](https://github.com/DataDog/dd-agent/pull/647) (Thanks to [@ordenull](https://github.com/ordenull))
* [FEATURE] Allow MySQL check configuration via a MySQL config file [#590](https://github.com/DataDog/dd-agent/pull/590) (Thanks to [@micktwomey](https://github.com/micktwomey))
* [FEATURE] Filter disk, io & network metrics by device [#615](https://github.com/DataDog/dd-agent/pull/615)
* [FEATURE] Collect metrics from the MongoDB database selected in the connection string [#657](https://github.com/DataDog/dd-agent/pull/657)
* [FEATURE] Add CPU and thread utilisation metrics to the Process check [#646](https://github.com/DataDog/dd-agent/pull/646) (Thanks to [@morskoyzmey](https://github.com/morskoyzmey))
* [BUGFIX] Add a timeout to the Mongo connection [#627](https://github.com/DataDog/dd-agent/issues/627)

#### Details
https://github.com/DataDog/dd-agent/compare/3.9.0...3.10.0


# 3.9.2 / 2013-08-29

**Windows Only**

### Integrations Affected
* SQL Server

#### Changes
* [FEATURE] Default SQL Server to integrated security if no username/password is provided ([#622](https://github.com/DataDog/dd-agent/pull/622
))(Thanks to [@jamescrowley](https://github.com/jamescrowley))
* [FEATURE] Allow skipping ssl certificate validation (useful when the agent runs behind haproxy)  ([#641](https://github.com/DataDog/dd-agent/issues/641))
* [BUGFIX] Fix proxy support on Windows
* [BUGFIX] Better management of config files with the GUI

#### Details
https://github.com/DataDog/dd-agent/compare/3.9.1...3.9.2

# 3.9.1 / 2013-08-19

**Windows Only**

### Integrations Affected
* SQL Server
* IIS

#### Changes
* [FEATURE] Add a Management GUI to the Windows Agent for service and check management
* [FEATURE] Log to a log file (located in C:\ProgramData\Datadog\logs )
* [FEATURE] Create shortcuts in the Start Menu
* [BUGFIX] Fix status page
* [BUGFIX] Fix logging in the event viewer and only logs errors ([#496](https://github.com/DataDog/dd-agent/issues/496))
* [BUGFIX] Add debug info in the sql server check ([#608](https://github.com/DataDog/dd-agent/issues/608))
* [BUGFIX]IIS: By default use _Total, but allow a configurable list of sites ([6885a97bc](https://github.com/DataDog/dd-agent/commit/00053a5397581d88f29803e3f3e01276885a97bc))

#### Details
https://github.com/DataDog/dd-agent/compare/3.9.0...3.9.1


# 3.9.0 / 2013-08-05

### Integrations Affected
* HDFS
* Postgres
* MySQL
* Jenkins
* Nginx
* RedisDB

#### Changes
* [FEATURE] New HDFS check added ([#551](https://github.com/DataDog/dd-agent/pull/551)) (thanks to [@dcrosta][])
* [FEATURE] New Directory check added ([#581](https://github.com/DataDog/dd-agent/pull/581)) (thanks to [@brettlangdon][])
* [FEATURE] Events can now be sent to the Agent DogStatsD server from supported client libraries ([#532](https://github.com/DataDog/dd-agent/pull/532))
* [FEATURE] HTTP check now supports custom headers ([#541](https://github.com/DataDog/dd-agent/issues/541)) (thanks to [@tomduckering][])
* [FEATURE] Optional `response_time` metric has been added to TCP and HTTP checks
* [FEATURE] `info` command will exit with a non-zero value when errors were displayed by the command
* [FEATURE] Basic Jenkins metrics are now collected by Jenkins check ([#567](https://github.com/DataDog/dd-agent/issues/567))
* [FEATURE] A non-default port can now be specified in the MySQL check ([#575](https://github.com/DataDog/dd-agent/issues/575))
* [FEATURE] Logs now follow The BSD syslog Protocol ([#577](https://github.com/DataDog/dd-agent/issues/577))
* [BUGFIX] Expat XML Parser dependency is now installed by SmartOS Agent installation script ([#450](https://github.com/DataDog/dd-agent/issues/450))
* [BUGFIX] Fix collection of Postgres `rollbacks` metric
* [BUGFIX] Fix Postgres integration crashing when tags are None
* [BUGFIX] Fix version detection in MySQL check ([#558](https://github.com/DataDog/dd-agent/issues/558))
* [BUGFIX] MySQL InnoDB metrics are now only collected with InnoDB is enabled ([#566](https://github.com/DataDog/dd-agent/issues/566))
* [BUGFIX] The source `status` and `info` commands will no longer attempt to start the Agent ([#512](https://github.com/DataDog/dd-agent/issues/512))
* [BUGFIX] Upon a failed EC2 metadata lookup, the last successfully collected metadata will now be report ([#554](https://github.com/DataDog/dd-agent/issues/554))
* [BUGFIX] Nginx check no longer asserts number of connections ([#569](https://github.com/DataDog/dd-agent/issues/569))
* [BUGFIX] Deb and RPM `start` command will now poll the Agent status when starting instead of waiting a fixed amount of time ([#582](https://github.com/DataDog/dd-agent/issues/582))
* [BUGFIX] RedisDB check will now cast a parsed port to an integer ([#600](https://github.com/DataDog/dd-agent/pull/600))
* [BUGFIX] `supervisord` location is no longer hardcoded on Debian ([#580](https://github.com/DataDog/dd-agent/issues/580)) (Thanks to [@mastrolinux][])

#### Details
https://github.com/DataDog/dd-agent/compare/3.8.0...3.9.0


# 3.8.0 / 2013-06-19

#### Changes
* [FEATURE] Add status command to Debian
* [FEATURE] Debian version now uses its own supervisor config instead of using the system config
* [FEATURE] Add `-v` option to info command, which currently gives stack traces for errors that occurred during checks
* [FEATURE] Add I/O metrics to OS X ([#131](https://github.com/DataDog/dd-agent/issues/131))
* [BUGFIX] Log exception when dogstatsd server fails to start ([#480](https://github.com/DataDog/dd-agent/issues/480))
* [BUGFIX] Fix `Error: Invalid user name dd-agent` appearing during source install ([#521](https://github.com/DataDog/dd-agent/issues/521))
* [BUGFIX] Debian and Red Hat init.d scripts now verify that `/etc/dd-agent/datadog.conf` is present before launching supervisor([#544](https://github.com/DataDog/dd-agent/issues/544))
* [BUGFIX] Fix AttributeErrors for `timeout_event` and `status_code_event` in Riak check ([#546](https://github.com/DataDog/dd-agent/pull/546))

#### Details
https://github.com/DataDog/dd-agent/compare/3.7.2...3.8.0

# 3.7.2 / 2013-05-22

* [FEATURE] Fix redis check when used with additional tags ([#515](https://github.com/DataDog/dd-agent/issues/515))

#### Details
https://github.com/DataDog/dd-agent/compare/3.7.1...3.7.2

# 3.7.1 / 2013-05-21

#### Changes
* [FEATURE] Add basic auth support for apache check ([#410](https://github.com/DataDog/dd-agent/issues/410))
* [FEATURE] Support any redis parameter during the connection ([#276](https://github.com/DataDog/dd-agent/issues/276))
* [FEATURE] Better launching script for source install
* [BUGFIX] Fix process check (Missing import and support version 0.4 of psutil) ([#502](https://github.com/DataDog/dd-agent/issues/502))
* [BUGFIX] Fix JVM Heap issue when launching java process ( Disable memory consumption watcher by default) ([#507](https://github.com/DataDog/dd-agent/issues/507))
* [BUGFIX] Info page shows errors when failing to initialize a check.d ([#427](https://github.com/DataDog/dd-agent/issues/427))
* [BUGFIX] Added file option to supervisorctl stop arg too ([#498](https://github.com/DataDog/dd-agent/pull/498)) (Thanks to [@mastrolinux](https://github.com/mastrolinux))
* [BUGFIX] Fix mysql version detection ([#501](https://github.com/DataDog/dd-agent/issues/501))

#### Details
https://github.com/DataDog/dd-agent/compare/3.7.0...3.7.1

# 3.7.0 / 2013-05-08

#### Changes
* [FEATURE] Restart the agent if it uses too much memory ([#426](https://github.com/DataDog/dd-agent/pull/429)) (Thanks to [@echohead](https://github.com/echohead))
* [FEATURE] Port Memcache to checks.d ([#390](https://github.com/DataDog/dd-agent/pull/439))
* [FEATURE] Add a process memory check ([#434](https://github.com/DataDog/dd-agent/pull/434)) (Thanks to [@mastrolinux](https://github.com/mastrolinux))
* [FEATURE] Add a gearman check ([#435](https://github.com/DataDog/dd-agent/pull/429)) (Thanks to [@CaptTofu](https://github.com/CaptTofu))
* [FEATURE] Add a Web Info Page to check the status of the agent (http://localhost:17125/status) ([#483](https://github.com/DataDog/dd-agent/pull/483))
* [FEATURE] Create an info page for the source install ([#481](https://github.com/DataDog/dd-agent/pull/481))
* [FEATURE] Add a “warning” method to the AgentCheck class that will display warnings in the info page
* [BUGFIX] Customizable Java directory for JMX Checks ([#472](https://github.com/DataDog/dd-agent/issues/472))
* [BUGFIX] Do not try to write logs in /var/log when using the source install ([#478](https://github.com/DataDog/dd-agent/issues/478))
* [BUGFIX] Use a Unix socket in supervisor for the source installation
* [BUGFIX]  Display more information when the agent stops because there is no valid hostname  ([#475](https://github.com/DataDog/dd-agent/issues/475))

#### Details
https://github.com/DataDog/dd-agent/compare/3.6.4...3.7.0

# 3.6.4 / 2013-04-25

**Windows only**

### Bug fixes
* IIS: Use Total metrics and calculate rates in the Agent instead of using PerSec metrics. ([#465](https://github.com/DataDog/dd-agent/pull/465))
* IIS: Optionally give a list of sites to pull metrics from, defaulting to all.

#### Details
https://github.com/DataDog/dd-agent/compare/3.6.3...3.6.4

# 3.6.3 / 2013-04-14

#### Changes
* [BUGFIX} Customizable field names for cacti check ([#404](https://github.com/DataDog/dd-agent/issues/404))
* [BUGFIX} Enable replication monitoring by default for old style check configuration for mysql
* [BUGFIX} Always collect metrics for config specified queues/nodes for rabbitmq

#### Details
https://github.com/DataDog/dd-agent/compare/3.6.2...3.6.3

# 3.6.2 / 2013-04-05

#### Changes
* [FEATURE] Port MySQL to checks.d ([#408](https://github.com/DataDog/dd-agent/pull/408)) (Thanks to [@CaptTofu](https://github.com/CaptTofu))
* [FEATURE] Add KyotoTycoon Check ([#426](https://github.com/DataDog/dd-agent/pull/426)) (Thanks to [@dcrosta](https://github.com/dcrosta))
* [FEATURE] Add command line option to run a particular agent check ([#408](https://github.com/DataDog/dd-agent/pull/417))
* [BUGFIX} Force include elementtree.ElementTree in Windows install ([#423](https://github.com/DataDog/dd-agent/issues/423))
* [BUGFIX} Fix elasticsearch check for version < 0.19 ([#419](https://github.com/DataDog/dd-agent/issues/419))
* [BUGFIX} Disable HAProxy events by default
* [BUGFIX} Aggregate RabbitMq Metrics over queues and nodes
* [BUGFIX} Better hostname detection
* [BUGFIX} Fix broken json serialization in centos5 ([#422](https://github.com/DataDog/dd-agent/issues/422))

#### Details
https://github.com/DataDog/dd-agent/compare/3.6.1...3.6.2

# 3.6.1 / 2013-03-21

#### Changes
* [FEATURE] Port Jenkins to checks.d
* [FEATURE] Lighttpd check now supports Lighttpd 2.0 ([#412](https://github.com/DataDog/dd-agent/pull/412)) (Thanks to [@brettlangdon](https://github.com/brettlangdon))
* [FEATURE]Additional configurable checks.d directory ([#413](https://github.com/DataDog/dd-agent/pull/413)) (Thanks to [@brettlangdon](https://github.com/brettlangdon))
* [BUGFIX] Better Jenkins check performance (reduce CPU consumption) ([#402](https://github.com/DataDog/dd-agent/issues/402))
* [BUGFIX] Fix Graphite listener ([#415](https://github.com/DataDog/dd-agent/issues/415))
* [BUGFIX] Less logging for pup ([#414](https://github.com/DataDog/dd-agent/issues/414))

#### Details
https://github.com/DataDog/dd-agent/compare/3.6.0...3.6.1

# 3.6.0 / 2013-03-13

#### Changes
* [FEATURE] The agent can now run behind a web proxy ([#377](https://github.com/DataDog/dd-agent/pull/377))
* [FEATURE] MongoDB now supports multiple instances running on the same host ([#397](https://github.com/DataDog/dd-agent/pull/397))
* [FEATURE] Additional network metrics ([#396](https://github.com/DataDog/dd-agent/pull/396))
* [FEATURE] lighttpd check ([#385](https://github.com/DataDog/dd-agent/pull/385))
* [FEATURE] Allow pup to bind to a specific interface ([#394](https://github.com/DataDog/dd-agent/pull/394)). Thanks to [@shamada-kuuluu][]
* [FEATURE] Add a partial response in HTTP Check ([#375](https://github.com/DataDog/dd-agent/pull/375)). Thanks to [@dcrosta][]
* [FEATURE] WMI checks support advanced configuration ([#359](https://github.com/DataDog/dd-agent/pull/359))
* [FEATURE] More reliable and consistent hostname detection ([84e715c](https://github.com/DataDog/dd-agent/commit/84e715c90d806f92667640d5647bc07194b36d71))
* [BUGFIX] Better retry handling for JMX checks ([#369](https://github.com/DataDog/dd-agent/issues/369))
* [BUGFIX]  Fix JMX Python 2.4 support ([#401](https://github.com/DataDog/dd-agent/issues/401))

#### Details
https://github.com/DataDog/dd-agent/compare/3.5.1...3.6.0

# 3.5.1
This is a **RedHat-only** release.

* [BUGFIX] Fix dogstatsd crash on RedHat 5.x and its derivatives ([#381](https://github.com/DataDog/dd-agent/pull/381))

#### Details
https://github.com/DataDog/dd-agent/compare/3.5.0...3.5.1

# 3.5.0

#### Changes
* [FEATURE] Logging overhaul: Consistent locations in `/var/log/datadog/`, defaults to INFO level ([#297](https://github.com/DataDog/dd-agent/pull/297))
* [FEATURE] Add more memcached metrics ([#283](https://github.com/DataDog/dd-agent/pull/283)). Thanks to [@jkoppe][]
* [FEATURE] RabbitMQ integration ([#330](https://github.com/DataDog/dd-agent/pull/330)). Thanks to [@brettlangdon][]
* [FEATURE] Riak integration ([#332](https://github.com/DataDog/dd-agent/pull/332)). Thanks to [@stefan-mees][]
* [FEATURE] Allow source file and line in Cassandra system.log. ([#307](https://github.com/DataDog/dd-agent/pull/307))
* [FEATURE] Port CouchDB and ElasticSearch to checks.d ([#311](https://github.com/DataDog/dd-agent/pull/311))
* [FEATURE] New System Metrics: `system.mem.pct_usable` and `system.swap.pct_free` ([#334](https://github.com/DataDog/dd-agent/pull/334))
* [FEATURE] SmartOS support (see [the agent setup page](https://app.datadoghq.com/account/settings#agent))
* [FEATURE] Invoke custom emitters from the forwarder, instead of the agent, to capture statsd output ([#271](https://github.com/DataDog/dd-agent/pull/272). Thanks to [@charles-dyfis-net][])
* [FEATURE] Allow strings to be elements in dogstatsd sets ([#300](https://github.com/DataDog/dd-agent/issues/326))
* [BUGFIX] Limit the number of threads used by service checks ([#351](https://github.com/DataDog/dd-agent/issues/351))
* [PERFORMANCE] Better JMX performance ([#313](https://github.com/DataDog/dd-agent/issues/313), [#348](https://github.com/DataDog/dd-agent/issues/348))
* [BUGFIX] Fix names of some Apache metrics ([#326](https://github.com/DataDog/dd-agent/issues/326))

#### Details
https://github.com/DataDog/dd-agent/compare/3.4.4...3.5.0

# 3.4.4

#### Changes
* [BUGFIX] Fix memory leaks in redis check, and potentially in custom checks.d checks that supply duplicate tags ([#325](https://github.com/DataDog/dd-agent/issues/325))
* [BUGFIX] Fix mongo auth issue ([#318](https://github.com/DataDog/dd-agent/issues/318))
* [BUGFIX] Add configurable socket timeout to zookeeper check ([#310](https://github.com/DataDog/dd-agent/issues/310))

# 3.4.3

#### Changes
* [BUGFIX] Fix memory leaks in memcache check ([#278](https://github.com/DataDog/dd-agent/issues/278))
* [BUGFIX] Fix umask issue ([#293](https://github.com/DataDog/dd-agent/issues/293))
* [BUGFIX] Fix bad error message in CentOS 5 installation ([#320](https://github.com/DataDog/dd-agent/issues/320))

#### Details
https://github.com/DataDog/dd-agent/compare/3.4.2...3.4.3

# 3.4.2

**If you're having issues upgrading, please read the [upgrade notes](https://github.com/DataDog/dd-agent/wiki/Upgrade-Notes)**

#### Changes
* [FEATURE] Check multiple Cassandra, Tomcat and Solr instances per host
* [FEATURE] Added a `JMXCheck` base class which can be used to easily track metrics from services that support JMX.
* [BUGFIX] Create `/etc/dd-agent/conf.d` on install
* [BUGFIX] Reduce verbosity of the logs

#### Details
https://github.com/DataDog/dd-agent/compare/3.4.1...3.4.2

# 3.4.1

#### Changes
* [FEATURE] Added an `info` command  (`sudo /etc/init.d/datadog-agent info`) which prints status info about the agent processes.
* [FEATURE] Added a check for [Zookeeper](http://zookeeper.apache.org/).
* [BUGFIX] Fixes packaging bugs introduced in 3.4.0.
* [BUGFIX] Agents installed with RPM will restart on upgrade (starting with the next version).
* [BUGFIX] Fixed normalized counter rounding error.
* [BUGFIX] By default, don't open ports other than localhost.

#### Details
https://github.com/DataDog/dd-agent/compare/3.4.0...3.4.1


## 3.4.0 / 2012-11-28

#### Changes
* [FEATURE] Added FreeBSD support, thanks to [@loris][].
* [FEATURE] Removed `datadog-agent` and `datadog-agent-base` dependencies. Now you only install one package per machine (instructions are the same).
* [FEATURE] The agent now compresses payloads sent over the wire.
* [FEATURE] Allow custom `PYTHONPATH` in checks.d config ([#227][])
* [FEATURE] Added new Redis metrics.
* [FEATURE] Added normalized load, that is load per cpu.
* [FEATURE] Port Apache, NginX and Varnish checks to checks.d.
* [BUGFIX] [#290][], [#291][] - disable non-local traffic by default, suppress stack traces in 404s
* [BUGFIX] [#257][] - More useful Apache rates not averaged from the beginning of time.
* [BUGFIX] [#277][] - Run dogstatsd on older debian boxes.
* [BUGFIX] [#245][] - Expire counter values.
* [BUGFIX] [#261][] - Fix Windows checks.d location lookup.
* [BUGFIX] [#253][] - Sum Dogstream counters.
* [PERFORMANCE] Improved dogstatsd performance.
* [ENHANCEMENT] Stylistic code improvements.

#### Details
https://github.com/DataDog/dd-agent/compare/3.3.0...3.4.0

## 3.3.0 / 2012-10-25

### New Features

#### Changes
* [FEATURE] Added HTTP and TCP Service Checks ([read the docs](http://docs.datadoghq.com/guides/services_checks/))
* [FEATURE] Added the Windows Event Log Integration
* [PERFORMANCE] Use the _much_ faster simplejson library, if it's available, otherwise use the standard json library.
* [BUGFIX] Fixed disk space metrics bug
* [BUGFIX] Run dogstatsd on older OS's as well.
* [BUGFIX] Fixed host aliasing issue.
* [BUGFIX] Use a better query to get the Cacti device name.
* [BUGFIX] Ensure pup uses the same JSON parsing library as the rest of the application.

#### Details
https://github.com/DataDog/dd-agent/compare/3.2.3...3.3.0

## 3.2.3 / 2012-10-15

#### Changes
* [FEATURE] Windows support is officially added.
* [FEATURE] Added a SQL Server check.
* [FEATURE] Added an IIS check.
* [FEATURE] Track request_rate in HAProxy.
* [FEATURE] Move DogstatsD to the `datadog-agent-base` package.

#### Details
https://github.com/DataDog/dd-agent/compare/3.2.2...3.2.3

# 3.2.2 / 2012-10-05

#### Changes
* [BUGFIX] Fixes an issue with events in checks.d where only events from the last instance would be sent.

#### Details
https://github.com/DataDog/dd-agent/compare/3.2.1...3.2.2

# 3.2.1 / 2012-10-05

#### Changes
* [BUGFIX] Fixes an issue with duplicate events being created in `checks.d` checks.

#### Details
https://github.com/DataDog/dd-agent/compare/3.2.0...3.2.1

## 3.2.0 / 2012-10-05

#### Changes
* [FEATURE] Add new AgentCheck interface for all future checks.
* [FEATURE] Split checks and configuration with `checks.d`/`conf.d`.

#### Details
https://github.com/DataDog/dd-agent/compare/3.1.7...3.2.0

# 3.1.7 / 2012-09-28

#### Changes
* [BUGFIX] Fixes the case where you have the `python-redis` module and the check will run with default host/port even if you don't have any redis configuration. Fixes case [#200](https://github.com/DataDog/dd-agent/issues/200).

#### Details
https://github.com/DataDog/dd-agent/compare/3.1.6...3.1.7

# 3.1.6 / 2012-09-27

#### Changes
* [BUGFIX] Fixes memcached integration bug running under Python 2.4 [#201](https://github.com/DataDog/dd-agent/issues/201)
* [BUGFIX] Removes token from the Cassandra Stats, because it is not always a number. Fixes case [#202](https://github.com/DataDog/dd-agent/issues/202)

#### Details
https://github.com/DataDog/dd-agent/compare/3.1.5...3.1.6

# 3.1.5 / 2012-09-21

#### Changes
* [BUGFIX] Fixes network traffic reporting bug introduced in 3.1.4. If you're running 3.1.4 we recommended that you upgrade.

#### Details
https://github.com/DataDog/dd-agent/compare/3.1.4...3.1.5

# 3.1.4 / 2012-09-21

#### Changes
* [FEATURE] memcached and nginx checks now support multiple instances per host.
* [FEATURE] Statsd: Added `sets` metric type. Read the [docs](http://docs.datadoghq.com/guides/metrics/#sets).
* [FEATURE] Statsd: Now supports multiple metrics per packet.
* [FEATURE] Some under the hood work to support more platforms.
* [FEATURE] Bug fixes
* [BUGFIX] Fixes invalid configuration parsing in the case of pure JVM metrics.

#### Details
https://github.com/DataDog/dd-agent/compare/3.1.3...3.1.4

# 3.1.3

#### Changes
* [BUGFIX] Fixes invalid configuration parsing in the case of pure JVM metrics.

# 3.1.2

#### Changes
* [FEATURE] Dogstream (parsing logs with dd-agent) supports parsing classes in addition to parsing functions.

# 3.1.1

#### Changes
* [FEATURE] Multi-instance JMX check
* [FEATURE] dogstatsd counters now send 0 for up to 10 minutes after the last increment(). They work with alerts.
* [BUGFIX] [part 1 of [#16][]5](https://github.com/DataDog/dd-agent/issues/165) dogstatsd's average is fixed
* [BUGFIX] HAProxy logging level was logging debug messages by default.

# 3.1.0

#### Changes
* [FEATURE] Deploy Pup along with the Agent (though Pup doesn't run on CentOS 5)
* [FEATURE] Added a one line install script
* [FEATURE] HAProxy integration
* [BUGFIX] Run the Agent on Redhat reboots
* [BUGFIX] [#150](https://github.com/DataDog/dd-agent/issues/150) - Fix Pexpect dependency
* [BUGFIX] Small fixes to the HAProxy and Elastic Search integrations.
* [BUGFIX] Fixed a couple of host aliasing issues.

### Notes

* This version depends on Supervisor version 3 instead of version 2.3.
* [changeset](https://github.com/DataDog/dd-agent/compare/3.0.5...3.1.0)

# 3.0.5

#### Changes
* [BUGFIX] Incorrect version dependencies between `datadog-agent` and `datadog-agent-base`.
* [BUGFIX] [#130](https://github.com/DataDog/dd-agent/issues/130) Fixes a crash when changing the listening port of the forwarder.

### How to upgrade from 3.0.4 on Debian and Ubuntu

When we released datadog-agent 3.0.4 we made a mistake and messed up the version dependency between packages. As a result, whenever you run `apt-get upgrade` or `apt-get dist-upgrade` and 3.0.4 is installed you may get the following error:

`E: Couldn't configure pre-depend datadog-agent-base for datadog-agent, probably a dependency cycle.`

If that's the case, don't panic: there is a simple fix. Simply run:

    sudo apt-get update
    sudo apt-get remove datadog-agent
    sudo apt-get install datadog-agent

to get the new versions up-and-running.

# 3.0.4

#### Changes
* [FEATURE] [#112](https://github.com/DataDog/dd-agent/issues/112) Thanks to [@charles-dyfis-net](https://github.com/charles-dyfis-net), the agent supports extra `emitters`. An emitter is an output for events and metrics.
* [FEATURE] [#117](https://github.com/DataDog/dd-agent/issues/117) Thanks to [@rl-0x0](https://github.com/rl-0x0), the agent can now parse supervisord logs and turn them into events and metrics.
* [FEATURE] [#121](https://github.com/DataDog/dd-agent/issues/121) Thanks to [@charles-dyfis-net](https://github.com/charles-dyfis-net), the agent supports custom checks. Check out our README for more details.

# 3.0.3

#### Changes
* [BUGFIX] [#82](https://github.com/DataDog/dd-agent/issues/82) Now proudly runs on Amazon Web Services Linux.
* [FEATURE] [#110](https://github.com/DataDog/dd-agent/issues/110) More ElasticSearch metrics

# 3.0.2

#### Changes
* [BUGFIX] [#105](https://github.com/DataDog/dd-agent/issues/105) Fix for ElasticSearch 0.18

# 3.0.1

#### Changes
* [BUGFIX] Support for ElasticSearch 0.18
* [BUGFIX] [#95](https://github.com/DataDog/dd-agent/issues/95) Fix for incorrect supervisord configuration on debian. More details [here](https://github.com/DataDog/dd-agent/wiki/How-to-fix-supervisor) to test whether you are affected.

# 3.0.0

* **This is a major version**
#### Changes
* [FEATURE] [dogstatsd](http://api.datadoghq.com/guides/dogstatsd), a drop-in replacement of statsd with tagging magic, bundled with the agent. Compatible with all statsd clients.
* [FEATURE] [#21](https://github.com/DataDog/dd-agent/issues/21) Support for ElasticSearch 0.19

# 2.2.28

#### Changes
* [FEATURE] [#83](https://github.com/DataDog/dd-agent/issues/83) Support authenticated connections to redis. Simply use the following stanza in `/etc/dd-agent/datadog.conf` to support multiple servers

    redis_urls: host:port, password[@host][]:port

# 2.2.27

#### Changes
* [BUGFIX] [#80](https://github.com/DataDog/dd-agent/issues/80) Agent now runs happily in locales with different radix separator
* [FEATURE] [#73](https://github.com/DataDog/dd-agent/issues/73) Allow checks to record tag metrics

# 2.2.26

#### Changes
* [BUGFIX][#76](https://github.com/DataDog/dd-agent/issues/76) Fixes nagios perfdata parsing (if templates contained brackets)

# 2.2.25

#### Changes
* [BUGFIX] [#68](https://github.com/DataDog/dd-agent/issues/68) Fixes off-by-one dog parsing error
* [BUGFIX] [#65](https://github.com/DataDog/dd-agent/issues/65) More robust uninstall script on Debian & Ubuntu
* [FEATURE] [#71](https://github.com/DataDog/dd-agent/issues/71) Supports for network metrics on Mac OS X
* [FEATURE] [#62](https://github.com/DataDog/dd-agent/issues/62) Sends instance-related EC2 metadata to Datadog to enable host aliases

# 2.2.24

#### Changes
* [BUGFIX] fixes used memory metric
* [BUGFIX] fixes mongo support on Ubuntu 11.10 (with pymongo 1.11)
* [BUGFIX] fixes IO metrics on Ubuntu 12.04 (thanks [@dcrosta][])

# 2.2.22

#### Changes
* [FEATURE] Supports Varnish 2.x

# 2.2.21

If you use ganglia, you want this version.

#### Changes
* [PERFORMANCE] major ganglia speedup, getting telnetlib out of the equation

# 2.2.20

#### Changes
* [BUGFIX] fixes MongoDB support, broken in 2.2.19.

# 2.2.19

#### Changes
* [BUGFIX] varnish support is now xml-based, to not break when reading bitmap values ([#42][])
* [BUGFIX] less verbose errors in dogstream ([#55][])
* [FEATURE] Now capturing master/slave changes in Mongo

# 2.2.18

#### Changes
* [BUGFIX] When using `use_ec2_instance_id: yes` on a non-ec2 box, don't hang! (introduced with 2.2.17)
* [FEATURE] Initial Varnish support

# 2.2.17

#### Changes
* [BUGFIX] On CentOS, pid was always saved in /tmp/dd-agent.pid ([#51][])
* **CONFIGURATION CHANGE**: When running on EC2, the instance id will be used in lieu of the hostname, unless `use_ec2_instance_id` is set no `no`.

# 2.2.16

#### Changes
* [FEATURE] Agent auto-detects the fact that it is running on Amazon EC2
* [FEATURE] Agent supports [custom event parsers](wiki/Log-Parsing)

# 2.2.15

#### Changes
* [BUGFIX] Fixes MongoDB configuration parsing.

# 2.2.14

#### Changes
* [BUGFIX] Used memory was not reported on 2.2.12 when running the agent on Debian Lenny.
* [BUGFIX] Cacti memory is reported in MB, not in bytes.

# 2.2.12

#### Changes
* [BUGFIX] Cacti check should fail gracefully if it cannot find RRD files.

# 2.2.11

#### Changes
* [BUGFIX] Prevent counters from wrapping ([#23](/DataDog/dd-agent/pull/30))
* [BUGFIX] Collect shared memory metric, accessible in Datadog via system.mem.shared.

# 2.2.10

#### Changes
* [BUGFIX] On CentOS5, when both `datadog-agent` and `datadog-agent-base` are installed, `datadog-agent-base` runs with the stock 2.4 python, which allows python modules that support integrations (e.g. mysql) to be installed with yum.

# 2.2.9 (minor)

#### Changes
* [FEATURE] Added support for [cacti](http://www.cacti.net)
* [FEATURE] Added support for new memory metrics: `system.mem.buffers`, `system.mem.cached`, `system.mem.buffers`, `system.mem.usable`, `system.mem.total`

#### Details
  https://github.com/DataDog/dd-agent/issues?milestone=1&state=closed

<!--- The following link definition list is generated by PimpMyChangelog --->
[#16]: https://github.com/DataDog/dd-agent/issues/16
[#21]: https://github.com/DataDog/dd-agent/issues/21
[#23]: https://github.com/DataDog/dd-agent/issues/23
[#42]: https://github.com/DataDog/dd-agent/issues/42
[#51]: https://github.com/DataDog/dd-agent/issues/51
[#55]: https://github.com/DataDog/dd-agent/issues/55
[#62]: https://github.com/DataDog/dd-agent/issues/62
[#65]: https://github.com/DataDog/dd-agent/issues/65
[#68]: https://github.com/DataDog/dd-agent/issues/68
[#71]: https://github.com/DataDog/dd-agent/issues/71
[#72]: https://github.com/DataDog/dd-agent/issues/72
[#73]: https://github.com/DataDog/dd-agent/issues/73
[#76]: https://github.com/DataDog/dd-agent/issues/76
[#80]: https://github.com/DataDog/dd-agent/issues/80
[#82]: https://github.com/DataDog/dd-agent/issues/82
[#83]: https://github.com/DataDog/dd-agent/issues/83
[#95]: https://github.com/DataDog/dd-agent/issues/95
[#105]: https://github.com/DataDog/dd-agent/issues/105
[#110]: https://github.com/DataDog/dd-agent/issues/110
[#112]: https://github.com/DataDog/dd-agent/issues/112
[#117]: https://github.com/DataDog/dd-agent/issues/117
[#121]: https://github.com/DataDog/dd-agent/issues/121
[#130]: https://github.com/DataDog/dd-agent/issues/130
[#131]: https://github.com/DataDog/dd-agent/issues/131
[#150]: https://github.com/DataDog/dd-agent/issues/150
[#165]: https://github.com/DataDog/dd-agent/issues/165
[#200]: https://github.com/DataDog/dd-agent/issues/200
[#201]: https://github.com/DataDog/dd-agent/issues/201
[#202]: https://github.com/DataDog/dd-agent/issues/202
[#227]: https://github.com/DataDog/dd-agent/issues/227
[#245]: https://github.com/DataDog/dd-agent/issues/245
[#253]: https://github.com/DataDog/dd-agent/issues/253
[#257]: https://github.com/DataDog/dd-agent/issues/257
[#261]: https://github.com/DataDog/dd-agent/issues/261
[#271]: https://github.com/DataDog/dd-agent/issues/271
[#276]: https://github.com/DataDog/dd-agent/issues/276
[#277]: https://github.com/DataDog/dd-agent/issues/277
[#278]: https://github.com/DataDog/dd-agent/issues/278
[#283]: https://github.com/DataDog/dd-agent/issues/283
[#290]: https://github.com/DataDog/dd-agent/issues/290
[#291]: https://github.com/DataDog/dd-agent/issues/291
[#293]: https://github.com/DataDog/dd-agent/issues/293
[#297]: https://github.com/DataDog/dd-agent/issues/297
[#300]: https://github.com/DataDog/dd-agent/issues/300
[#307]: https://github.com/DataDog/dd-agent/issues/307
[#310]: https://github.com/DataDog/dd-agent/issues/310
[#311]: https://github.com/DataDog/dd-agent/issues/311
[#313]: https://github.com/DataDog/dd-agent/issues/313
[#318]: https://github.com/DataDog/dd-agent/issues/318
[#320]: https://github.com/DataDog/dd-agent/issues/320
[#325]: https://github.com/DataDog/dd-agent/issues/325
[#326]: https://github.com/DataDog/dd-agent/issues/326
[#330]: https://github.com/DataDog/dd-agent/issues/330
[#332]: https://github.com/DataDog/dd-agent/issues/332
[#334]: https://github.com/DataDog/dd-agent/issues/334
[#348]: https://github.com/DataDog/dd-agent/issues/348
[#351]: https://github.com/DataDog/dd-agent/issues/351
[#359]: https://github.com/DataDog/dd-agent/issues/359
[#369]: https://github.com/DataDog/dd-agent/issues/369
[#375]: https://github.com/DataDog/dd-agent/issues/375
[#377]: https://github.com/DataDog/dd-agent/issues/377
[#381]: https://github.com/DataDog/dd-agent/issues/381
[#385]: https://github.com/DataDog/dd-agent/issues/385
[#390]: https://github.com/DataDog/dd-agent/issues/390
[#394]: https://github.com/DataDog/dd-agent/issues/394
[#396]: https://github.com/DataDog/dd-agent/issues/396
[#397]: https://github.com/DataDog/dd-agent/issues/397
[#401]: https://github.com/DataDog/dd-agent/issues/401
[#402]: https://github.com/DataDog/dd-agent/issues/402
[#404]: https://github.com/DataDog/dd-agent/issues/404
[#408]: https://github.com/DataDog/dd-agent/issues/408
[#410]: https://github.com/DataDog/dd-agent/issues/410
[#412]: https://github.com/DataDog/dd-agent/issues/412
[#413]: https://github.com/DataDog/dd-agent/issues/413
[#414]: https://github.com/DataDog/dd-agent/issues/414
[#415]: https://github.com/DataDog/dd-agent/issues/415
[#419]: https://github.com/DataDog/dd-agent/issues/419
[#422]: https://github.com/DataDog/dd-agent/issues/422
[#423]: https://github.com/DataDog/dd-agent/issues/423
[#426]: https://github.com/DataDog/dd-agent/issues/426
[#427]: https://github.com/DataDog/dd-agent/issues/427
[#434]: https://github.com/DataDog/dd-agent/issues/434
[#435]: https://github.com/DataDog/dd-agent/issues/435
[#450]: https://github.com/DataDog/dd-agent/issues/450
[#465]: https://github.com/DataDog/dd-agent/issues/465
[#472]: https://github.com/DataDog/dd-agent/issues/472
[#475]: https://github.com/DataDog/dd-agent/issues/475
[#478]: https://github.com/DataDog/dd-agent/issues/478
[#480]: https://github.com/DataDog/dd-agent/issues/480
[#481]: https://github.com/DataDog/dd-agent/issues/481
[#483]: https://github.com/DataDog/dd-agent/issues/483
[#490]: https://github.com/DataDog/dd-agent/issues/490
[#496]: https://github.com/DataDog/dd-agent/issues/496
[#498]: https://github.com/DataDog/dd-agent/issues/498
[#501]: https://github.com/DataDog/dd-agent/issues/501
[#502]: https://github.com/DataDog/dd-agent/issues/502
[#507]: https://github.com/DataDog/dd-agent/issues/507
[#512]: https://github.com/DataDog/dd-agent/issues/512
[#515]: https://github.com/DataDog/dd-agent/issues/515
[#521]: https://github.com/DataDog/dd-agent/issues/521
[#532]: https://github.com/DataDog/dd-agent/issues/532
[#541]: https://github.com/DataDog/dd-agent/issues/541
[#544]: https://github.com/DataDog/dd-agent/issues/544
[#546]: https://github.com/DataDog/dd-agent/issues/546
[#551]: https://github.com/DataDog/dd-agent/issues/551
[#554]: https://github.com/DataDog/dd-agent/issues/554
[#558]: https://github.com/DataDog/dd-agent/issues/558
[#566]: https://github.com/DataDog/dd-agent/issues/566
[#567]: https://github.com/DataDog/dd-agent/issues/567
[#569]: https://github.com/DataDog/dd-agent/issues/569
[#575]: https://github.com/DataDog/dd-agent/issues/575
[#577]: https://github.com/DataDog/dd-agent/issues/577
[#580]: https://github.com/DataDog/dd-agent/issues/580
[#581]: https://github.com/DataDog/dd-agent/issues/581
[#582]: https://github.com/DataDog/dd-agent/issues/582
[#590]: https://github.com/DataDog/dd-agent/issues/590
[#600]: https://github.com/DataDog/dd-agent/issues/600
[#608]: https://github.com/DataDog/dd-agent/issues/608
[#615]: https://github.com/DataDog/dd-agent/issues/615
[#619]: https://github.com/DataDog/dd-agent/issues/619
[#622]: https://github.com/DataDog/dd-agent/issues/622
[#624]: https://github.com/DataDog/dd-agent/issues/624
[#627]: https://github.com/DataDog/dd-agent/issues/627
[#632]: https://github.com/DataDog/dd-agent/issues/632
[#641]: https://github.com/DataDog/dd-agent/issues/641
[#643]: https://github.com/DataDog/dd-agent/issues/643
[#646]: https://github.com/DataDog/dd-agent/issues/646
[#647]: https://github.com/DataDog/dd-agent/issues/647
[#654]: https://github.com/DataDog/dd-agent/issues/654
[#657]: https://github.com/DataDog/dd-agent/issues/657
[#665]: https://github.com/DataDog/dd-agent/issues/665
[#677]: https://github.com/DataDog/dd-agent/issues/677
[#706]: https://github.com/DataDog/dd-agent/issues/706
[#729]: https://github.com/DataDog/dd-agent/issues/729
[#730]: https://github.com/DataDog/dd-agent/issues/730
[#735]: https://github.com/DataDog/dd-agent/issues/735
[#752]: https://github.com/DataDog/dd-agent/issues/752
[#760]: https://github.com/DataDog/dd-agent/issues/760
[#766]: https://github.com/DataDog/dd-agent/issues/766
[#770]: https://github.com/DataDog/dd-agent/issues/770
[#780]: https://github.com/DataDog/dd-agent/issues/780
[#784]: https://github.com/DataDog/dd-agent/issues/784
[#787]: https://github.com/DataDog/dd-agent/issues/787
[#790]: https://github.com/DataDog/dd-agent/issues/790
[#806]: https://github.com/DataDog/dd-agent/issues/806
[#809]: https://github.com/DataDog/dd-agent/issues/809
[#810]: https://github.com/DataDog/dd-agent/issues/810
[#815]: https://github.com/DataDog/dd-agent/issues/815
[#826]: https://github.com/DataDog/dd-agent/issues/826
[#827]: https://github.com/DataDog/dd-agent/issues/827
[#834]: https://github.com/DataDog/dd-agent/issues/834
[#838]: https://github.com/DataDog/dd-agent/issues/838
[#844]: https://github.com/DataDog/dd-agent/issues/844
[#848]: https://github.com/DataDog/dd-agent/issues/848
[#849]: https://github.com/DataDog/dd-agent/issues/849
[#852]: https://github.com/DataDog/dd-agent/issues/852
[#863]: https://github.com/DataDog/dd-agent/issues/863
[#875]: https://github.com/DataDog/dd-agent/issues/875
[#876]: https://github.com/DataDog/dd-agent/issues/876
[#883]: https://github.com/DataDog/dd-agent/issues/883
[#891]: https://github.com/DataDog/dd-agent/issues/891
[#893]: https://github.com/DataDog/dd-agent/issues/893
[#894]: https://github.com/DataDog/dd-agent/issues/894
[#899]: https://github.com/DataDog/dd-agent/issues/899
[#900]: https://github.com/DataDog/dd-agent/issues/900
[#904]: https://github.com/DataDog/dd-agent/issues/904
[#917]: https://github.com/DataDog/dd-agent/issues/917
[#919]: https://github.com/DataDog/dd-agent/issues/919
[#921]: https://github.com/DataDog/dd-agent/issues/921
[#922]: https://github.com/DataDog/dd-agent/issues/922
[#927]: https://github.com/DataDog/dd-agent/issues/927
[#928]: https://github.com/DataDog/dd-agent/issues/928
[#930]: https://github.com/DataDog/dd-agent/issues/930
[#933]: https://github.com/DataDog/dd-agent/issues/933
[#935]: https://github.com/DataDog/dd-agent/issues/935
[#940]: https://github.com/DataDog/dd-agent/issues/940
[#947]: https://github.com/DataDog/dd-agent/issues/947
[#949]: https://github.com/DataDog/dd-agent/issues/949
[#951]: https://github.com/DataDog/dd-agent/issues/951
[#960]: https://github.com/DataDog/dd-agent/issues/960
[#962]: https://github.com/DataDog/dd-agent/issues/962
[#963]: https://github.com/DataDog/dd-agent/issues/963
[#964]: https://github.com/DataDog/dd-agent/issues/964
[#971]: https://github.com/DataDog/dd-agent/issues/971
[#972]: https://github.com/DataDog/dd-agent/issues/972
[#975]: https://github.com/DataDog/dd-agent/issues/975
[#977]: https://github.com/DataDog/dd-agent/issues/977
[#980]: https://github.com/DataDog/dd-agent/issues/980
[#981]: https://github.com/DataDog/dd-agent/issues/981
[#982]: https://github.com/DataDog/dd-agent/issues/982
[#984]: https://github.com/DataDog/dd-agent/issues/984
[@CaptTofu]: https://github.com/CaptTofu
[@arthurnn]: https://github.com/arthurnn
[@brettlangdon]: https://github.com/brettlangdon
[@charles-dyfis-net]: https://github.com/charles-dyfis-net
[@ckrough]: https://github.com/ckrough
[@clly]: https://github.com/clly
[@dcrosta]: https://github.com/dcrosta
[@echohead]: https://github.com/echohead
[@graemej]: https://github.com/graemej
[@host]: https://github.com/host
[@igor47]: https://github.com/igor47
[@imlucas]: https://github.com/imlucas
[@ive]: https://github.com/ive
[@jamescrowley]: https://github.com/jamescrowley
[@jkoppe]: https://github.com/jkoppe
[@joningle]: https://github.com/joningle
[@leifwalsh]: https://github.com/leifwalsh
[@loris]: https://github.com/loris
[@mastrolinux]: https://github.com/mastrolinux
[@micktwomey]: https://github.com/micktwomey
[@mike-lerch]: https://github.com/mike-lerch
[@morskoyzmey]: https://github.com/morskoyzmey
[@ordenull]: https://github.com/ordenull
[@rl-0x0]: https://github.com/rl-0x0
[@ronaldbradford]: https://github.com/ronaldbradford
[@shamada-kuuluu]: https://github.com/shamada-kuuluu
[@skingry]: https://github.com/skingry
[@steeve]: https://github.com/steeve
[@stefan-mees]: https://github.com/stefan-mees
[@tomduckering]: https://github.com/tomduckering
[@walkeran]: https://github.com/walkeran

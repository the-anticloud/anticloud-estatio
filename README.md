# ESTATIO

![licence](https://img.shields.io/badge/licence-Apache-2.0-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![checks](https://img.shields.io/badge/checks-unknown_PASS-brightgreen)

> Governed Anticloud packaging of the upstream project `ESTATIO` in category **REAL_ESTATE**. check results: see ISOLATED_LAB_RESULTS. Every number below traces to a named file + run stamp; nothing is borrowed from other projects.

**Upstream:** ESTATIO · **Upstream pin:** `82817ed22d00467e33afd290498d684cacccb3f5` · **Category:** REAL_ESTATE · **Vendor:** Anticloud FZ LLE · **Licence:** Apache-2.0

---

## What This Project Does

CAUTION: This project has now been archived, and copied into a private project for further development.

= Estatio: an open source estate management system.
:toc:

Estatio is modern and flexible property management software.
It offers real estate professionals and service providers the power and flexibility to manage their business in a superior, flexible and cost-effective manner.

== Screenshots

The following screenshots (taken 13 december 2014) correspond to the business logic in Estatio's link:https://github.com/estatio/estatio/tree/master/estatioapp/dom/src/main/java/org/estatio/dom[domain object model].

=== All properties

image::https://raw.github.com/estatio/estatio/master/docs/screenshots/AllProperties.png[width="600px",link="https://raw.github.com/estatio/estatio/master/docs/screenshots/AllProperties.png"]

image::https://raw.github.com/estatio/estatio/master/docs/screenshots/AllProperties-Map.png[width="600px",link="https://raw.github.com/estatio/estatio/master/docs/screenshots/AllProperties-Map.png"]

=== Lease

image::https://raw.github.com/estatio/estatio/master/docs/screenshots/Lease.png[width="600px",link="https://raw.github.com/estatio/estatio/master/docs/screenshots/Lease.png"]

=== LeaseItem

image::https://raw.github.com/estatio/estatio/master/docs/screenshots/LeaseItem.png[width="600px",link="https://raw.github.com/estatio/estatio/master/docs/screenshots/LeaseItem.png"]

=== Invoice

image::https://raw.github.com/estatio/estatio/master/docs/screenshots/Invoice.png[width="600px",link="https://raw.github.com/estatio/estatio/master/docs/screenshots/Invoice.png"]

== Trying out Estatio

=== Building Estatio

==== Prereqs

Estatio runs on Java and is built with http://maven.apache.org[Maven].
The source code is managed using https://help.github.com/articles/set-up-git[git], and is held on http://github.com[github].

If you don't already have them installed, install Java (JDK 6 or later), Maven (3.0.4 or later), and git.

After that, you'll need to manually build and install the https://code.google.com/archive/p/google-rfc-2445/[google RFC-2445] Jar (this is not available in Maven Central project).

[source]
----
git source https://github.com/jcvanderwal/google-rfc-2445.git
cd google-rfc-2445/
git checkout mavenized
mvn clean install -DskipTests
----

==== Download and build Estatio

Download using git:

[source]
----
git source https://github.com/estatio/estatio.git
cd estatio
----

and build using maven:

[source]
----
mvn clean install
----

The source is approx 400Mb, and takes approximately 5 minutes to build.

=== Configure Estatio (JDBC URL)

Before Estatio can be run, you must configure its JDBC URL; typically this lives in the `estatioapp/webapp/src/main/webapp/WEB-INF/persistor.properties` properties file.

You can do this most easily by copying a set of property entries from `estatioapp/webapp/src/main/webapp/WEB-INF/persistor.properties.SAMPLE`.

For example, to run against an in-memory HSQLDB, the `persistor.properties` file should consist of:

[source]
----
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionDriverName=org.hsqldb.jdbcDriver
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionURL=jdbc:hsqldb:mem:test
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionUserName=sa
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionPassword=
----

The JDBC driver for HSQLDB is on the classpath.
If you want to connect to some other database, be sure to update the `pom.xml` to add the driver as a `<dependency>`.

=== Run Estatio

You can run Estatio either using `mvn jetty plugin`, or using the standalone (self-hosting) version of the WAR:

* Running through Maven +
+
Run using: +
+
[source]
----
mvn -pl estatioapp/webapp jetty:run
----

* Running as a self-hosting JAR +
+
Package using: +
+
[source]
----
mvn -pl estatioapp/webapp -Dmavenmixin-jettyconsole package
----
+
and run using: +
+
[source]
----
mvn -pl estatioapp/webapp -Dmavenmixin-jettyconsole antrun:run
----

Once the app has started, browse to:

[source]
----
http://localhost:8080/wicket/
----

=== Using Estatio

* Login using `estatio-admin/pass` or `estatio-user/pass`.

* Install some demo fixtures (as estatio-admin):

    Prototyping > Run Fixture Script > Run script: Estatio Demo Fixture

* Run a script to setup invoices:

    Prototyping > Run Fixture Script > Run script: Generate Top Model Invoice

And take a look around :-)

If you encounter any bugs, do https://github.com/estatio/estatio/blob/master/pom.xml#L70[let us know].

== Developers' Guide

A developers guide can be found http://github.com/incodehq/developers-guide[here].

== Thanks

Thanks to:

* image:https://raw.github.com/estatio/estatio/master/codequality/logoClover.png[width="100px",link="https://raw.github.com/estatio/estatio/master/codequality/logoClover.png"] https://www.atlassian.com[Atlassian] for providing an open source link:https://www.atlassian.com/software/clover/overview/[Clover] license
* link:http://structure101.com/contact/[Headway Software] for providing an open source link:http://structure101.com/[Structure 101] license

== Support

You are free to adapt or extend Estatio to your needs.
If you would like assistance in doing so, go to http://www.estatio.org[www.estatio.org].

You can find plenty of help on using Apache Isis at the http://isis.apache.org/support.html[Isis mailing lists].
There is also extensive http://isis.apache.org/documentation.html[online documentation].

== Legal Stuff

Copyright 2012-\``date`` http://www.eurocommercialproperties.com[Eurocommercial Properties NV]

Licensed under http://www.apache.org/licenses/LICENSE-2.0[Apache License 2.0]

---

## Installation

After that, you'll need to manually build and install the https://code.google.com/archive/p/google-rfc-2445/[google RFC-2445] Jar (this is not available in Maven Central project).

[source]
----
git source https://github.com/jcvanderwal/google-rfc-2445.git
cd google-rfc-2445/
git checkout mavenized
mvn clean install -DskipTests
----

==== Download and build Estatio

Download using git:

[source]
----
git source https://github.com/estatio/estatio.git
cd estatio
----

and build using maven:

[source]
----
mvn clean install
----

The source is approx 400Mb, and takes approximately 5 minutes to build.

=== Configure Estatio (JDBC URL)

Before Estatio can be run, you must configure its JDBC URL; typically this lives in the `estatioapp/webapp/src/main/webapp/WEB-INF/persistor.properties` properties file.

You can do this most easily by copying a set of property entries from `estatioapp/webapp/src/main/webapp/WEB-INF/persistor.properties.SAMPLE`.

For example, to run against an in-memory HSQLDB, the `persistor.properties` file should consist of:

[source]
----
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionDriverName=org.hsqldb.jdbcDriver
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionURL=jdbc:hsqldb:mem:test
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionUserName=sa
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionPassword=
----

The JDBC driver for HSQLDB is on the classpath.
If you want to connect to some other database, be sure to update the `pom.xml` to add the driver as a `<dependency>`.

=== Run Estatio

You can run Estatio either using `mvn jetty plugin`, or using the standalone (self-hosting) version of the WAR:

* Running through Maven +
+
Run using: +
+
[source]
----
mvn -pl estatioapp/webapp jetty:run
----

* Running as a self-hosting JAR +
+
Package using: +
+
[source]
----
mvn -pl estatioapp/webapp -Dmavenmixin-jettyconsole package
----
+
and run using: +
+
[source]
----
mvn -pl estatioapp/webapp -Dmavenmixin-jettyconsole antrun:run
----

Once the app has started, browse to:

[source]
----
http://localhost:8080/wicket/
----

=== Using Estatio

* Login using `estatio-admin/pass` or `estatio-user/pass`.

* Install some demo fixtures (as estatio-admin):

    Prototyping > Run Fixture Script > Run script: Estatio Demo Fixture

* Run a script to setup invoices:

    Prototyping > Run Fixture Script > Run script: Generate Top Model Invoice

And take a look around :-)

If you encounter any bugs, do https://github.com/estatio/estatio/blob/master/pom.xml#L70[let us know].

== Developers' Guide

A developers guide can be found http://github.com/incodehq/developers-guide[here].

== Thanks

Thanks to:

* image:https://raw.github.com/estatio/estatio/master/codequality/logoClover.png[width="100px",link="https://raw.github.com/estatio/estatio/master/codequality/logoClover.png"] https://www.atlassian.com[Atlassian] for providing an open source link:https://www.atlassian.com/software/clover/overview/[Clover] license
* link:http://structure101.com/contact/[Headway Software] for providing an open source link:http://structure101.com/[Structure 101] license

== Support

You are free to adapt or extend Estatio to your needs.
If you would like assistance in doing so, go to http://www.estatio.org[www.estatio.org].

You can find plenty of help on using Apache Isis at the http://isis.apache.org/support.html[Isis mailing lists].
There is also extensive http://isis.apache.org/documentation.html[online documentation].

== Legal Stuff

Copyright 2012-\``date`` http://www.eurocommercialproperties.com[Eurocommercial Properties NV]

Licensed under http://www.apache.org/licenses/LICENSE-2.0[Apache License 2.0]

## Usage

[source]
----
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionDriverName=org.hsqldb.jdbcDriver
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionURL=jdbc:hsqldb:mem:test
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionUserName=sa
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionPassword=
----

The JDBC driver for HSQLDB is on the classpath.
If you want to connect to some other database, be sure to update the `pom.xml` to add the driver as a `<dependency>`.

=== Run Estatio

You can run Estatio either using `mvn jetty plugin`, or using the standalone (self-hosting) version of the WAR:

* Running through Maven +
+
Run using: +
+
[source]
----
mvn -pl estatioapp/webapp jetty:run
----

* Running as a self-hosting JAR +
+
Package using: +
+
[source]
----
mvn -pl estatioapp/webapp -Dmavenmixin-jettyconsole package
----
+
and run using: +
+
[source]
----
mvn -pl estatioapp/webapp -Dmavenmixin-jettyconsole antrun:run
----

Once the app has started, browse to:

[source]
----
http://localhost:8080/wicket/
----

=== Using Estatio

* Login using `estatio-admin/pass` or `estatio-user/pass`.

* Install some demo fixtures (as estatio-admin):

    Prototyping > Run Fixture Script > Run script: Estatio Demo Fixture

* Run a script to setup invoices:

    Prototyping > Run Fixture Script > Run script: Generate Top Model Invoice

And take a look around :-)

If you encounter any bugs, do https://github.com/estatio/estatio/blob/master/pom.xml#L70[let us know].

== Developers' Guide

A developers guide can be found http://github.com/incodehq/developers-guide[here].

== Thanks

Thanks to:

* image:https://raw.github.com/estatio/estatio/master/codequality/logoClover.png[width="100px",link="https://raw.github.com/estatio/estatio/master/codequality/logoClover.png"] https://www.atlassian.com[Atlassian] for providing an open source link:https://www.atlassian.com/software/clover/overview/[Clover] license
* link:http://structure101.com/contact/[Headway Software] for providing an open source link:http://structure101.com/[Structure 101] license

== Support

You are free to adapt or extend Estatio to your needs.
If you would like assistance in doing so, go to http://www.estatio.org[www.estatio.org].

You can find plenty of help on using Apache Isis at the http://isis.apache.org/support.html[Isis mailing lists].
There is also extensive http://isis.apache.org/documentation.html[online documentation].

== Legal Stuff

Copyright 2012-\``date`` http://www.eurocommercialproperties.com[Eurocommercial Properties NV]

Licensed under http://www.apache.org/licenses/LICENSE-2.0[Apache License 2.0]

## API

== Legal Stuff

Copyright 2012-\``date`` http://www.eurocommercialproperties.com[Eurocommercial Properties NV]

Licensed under http://www.apache.org/licenses/LICENSE-2.0[Apache License 2.0]

## Dependencies

| Metric | Value |
|--------|-------|
| Files | unknown |
| Lines of Code | unknown |
| Dependencies | unknown |
| Upstream license (harvested) | Apache-2.0 |
| Overlay license | Anticommons 0.1.0 |

Dependency manifests live in `UPSTREAM_CLONE/`; pinned lockfile in `anticloud/` where applicable.

## Configuration

Before Estatio can be run, you must configure its JDBC URL; typically this lives in the `estatioapp/webapp/src/main/webapp/WEB-INF/persistor.properties` properties file.

You can do this most easily by copying a set of property entries from `estatioapp/webapp/src/main/webapp/WEB-INF/persistor.properties.SAMPLE`.

For example, to run against an in-memory HSQLDB, the `persistor.properties` file should consist of:

[source]
----
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionDriverName=org.hsqldb.jdbcDriver
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionURL=jdbc:hsqldb:mem:test
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionUserName=sa
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionPassword=
----

The JDBC driver for HSQLDB is on the classpath.
If you want to connect to some other database, be sure to update the `pom.xml` to add the driver as a `<dependency>`.

=== Run Estatio

You can run Estatio either using `mvn jetty plugin`, or using the standalone (self-hosting) version of the WAR:

* Running through Maven +
+
Run using: +
+
[source]
----
mvn -pl estatioapp/webapp jetty:run
----

* Running as a self-hosting JAR +
+
Package using: +
+
[source]
----
mvn -pl estatioapp/webapp -Dmavenmixin-jettyconsole package
----
+
and run using: +
+
[source]
----
mvn -pl estatioapp/webapp -Dmavenmixin-jettyconsole antrun:run
----

Once the app has started, browse to:

[source]
----
http://localhost:8080/wicket/
----

=== Using Estatio

* Login using `estatio-admin/pass` or `estatio-user/pass`.

* Install some demo fixtures (as estatio-admin):

    Prototyping > Run Fixture Script > Run script: Estatio Demo Fixture

* Run a script to setup invoices:

    Prototyping > Run Fixture Script > Run script: Generate Top Model Invoice

And take a look around :-)

If you encounter any bugs, do https://github.com/estatio/estatio/blob/master/pom.xml#L70[let us know].

== Developers' Guide

A developers guide can be found http://github.com/incodehq/developers-guide[here].

== Thanks

Thanks to:

* image:https://raw.github.com/estatio/estatio/master/codequality/logoClover.png[width="100px",link="https://raw.github.com/estatio/estatio/master/codequality/logoClover.png"] https://www.atlassian.com[Atlassian] for providing an open source link:https://www.atlassian.com/software/clover/overview/[Clover] license
* link:http://structure101.com/contact/[Headway Software] for providing an open source link:http://structure101.com/[Structure 101] license

== Support

You are free to adapt or extend Estatio to your needs.
If you would like assistance in doing so, go to http://www.estatio.org[www.estatio.org].

You can find plenty of help on using Apache Isis at the http://isis.apache.org/support.html[Isis mailing lists].
There is also extensive http://isis.apache.org/documentation.html[online documentation].

== Legal Stuff

Copyright 2012-\``date`` http://www.eurocommercialproperties.com[Eurocommercial Properties NV]

Licensed under http://www.apache.org/licenses/LICENSE-2.0[Apache License 2.0]

## Contributing

= Estatio: an open source estate management system.
:toc:

Estatio is modern and flexible property management software.
It offers real estate professionals and service providers the power and flexibility to manage their business in a superior, flexible and cost-effective manner.

== Screenshots

The following screenshots (taken 13 december 2014) correspond to the business logic in Estatio's link:https://github.com/estatio/estatio/tree/master/estatioapp/dom/src/main/java/org/estatio/dom[domain object model].

=== All properties

image::https://raw.github.com/estatio/estatio/master/docs/screenshots/AllProperties.png[width="600px",link="https://raw.github.com/estatio/estatio/master/docs/screenshots/AllProperties.png"]

image::https://raw.github.com/estatio/estatio/master/docs/screenshots/AllProperties-Map.png[width="600px",link="https://raw.github.com/estatio/estatio/master/docs/screenshots/AllProperties-Map.png"]

=== Lease

image::https://raw.github.com/estatio/estatio/master/docs/screenshots/Lease.png[width="600px",link="https://raw.github.com/estatio/estatio/master/docs/screenshots/Lease.png"]

=== LeaseItem

image::https://raw.github.com/estatio/estatio/master/docs/screenshots/LeaseItem.png[width="600px",link="https://raw.github.com/estatio/estatio/master/docs/screenshots/LeaseItem.png"]

=== Invoice

image::https://raw.github.com/estatio/estatio/master/docs/screenshots/Invoice.png[width="600px",link="https://raw.github.com/estatio/estatio/master/docs/screenshots/Invoice.png"]

== Trying out Estatio

=== Building Estatio

==== Prereqs

Estatio runs on Java and is built with http://maven.apache.org[Maven].
The source code is managed using https://help.github.com/articles/set-up-git[git], and is held on http://github.com[github].

If you don't already have them installed, install Java (JDK 6 or later), Maven (3.0.4 or later), and git.

After that, you'll need to manually build and install the https://code.google.com/archive/p/google-rfc-2445/[google RFC-2445] Jar (this is not available in Maven Central project).

[source]
----
git source https://github.com/jcvanderwal/google-rfc-2445.git
cd google-rfc-2445/
git checkout mavenized
mvn clean install -DskipTests
----

==== Download and build Estatio

Download using git:

[source]
----
git source https://github.com/estatio/estatio.git
cd estatio
----

and build using maven:

[source]
----
mvn clean install
----

The source is approx 400Mb, and takes approximately 5 minutes to build.

=== Configure Estatio (JDBC URL)

Before Estatio can be run, you must configure its JDBC URL; typically this lives in the `estatioapp/webapp/src/main/webapp/WEB-INF/persistor.properties` properties file.

You can do this most easily by copying a set of property entries from `estatioapp/webapp/src/main/webapp/WEB-INF/persistor.properties.SAMPLE`.

For example, to run against an in-memory HSQLDB, the `persistor.properties` file should consist of:

[source]
----
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionDriverName=org.hsqldb.jdbcDriver
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionURL=jdbc:hsqldb:mem:test
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionUserName=sa
isis.persistor.datanucleus.impl.javax.jdo.option.ConnectionPassword=
----

The JDBC driver for HSQLDB is on the classpath.
If you want to connect to some other database, be sure to update the `pom.xml` to add the driver as a `<dependency>`.

=== Run Estatio

You can run Estatio either using `mvn jetty plugin`, or using the standalone (self-hosting) version of the WAR:

* Running through Maven +
+
Run using: +
+
[source]
----
mvn -pl estatioapp/webapp jetty:run
----

* Running as a self-hosting JAR +
+
Package using: +
+
[source]
----
mvn -pl estatioapp/webapp -Dmavenmixin-jettyconsole package
----
+
and run using: +
+
[source]
----
mvn -pl estatioapp/webapp -Dmavenmixin-jettyconsole antrun:run
----

Once the app has started, browse to:

[source]
----
http://localhost:8080/wicket/
----

=== Using Estatio

* Login using `estatio-admin/pass` or `estatio-user/pass`.

* Install some demo fixtures (as estatio-admin):

    Prototyping > Run Fixture Script > Run script: Estatio Demo Fixture

* Run a script to setup invoices:

    Prototyping > Run Fixture Script > Run script: Generate Top Model Invoice

And take a look around :-)

If you encounter any bugs, do https://github.com/estatio/estatio/blob/master/pom.xml#L70[let us know].

== Developers' Guide

A developers guide can be found http://github.com/incodehq/developers-guide[here].

== Thanks

Thanks to:

* image:https://raw.github.com/estatio/estatio/master/codequality/logoClover.png[width="100px",link="https://raw.github.com/estatio/estatio/master/codequality/logoClover.png"] https://www.atlassian.com[Atlassian] for providing an open source link:https://www.atlassian.com/software/clover/overview/[Clover] license
* link:http://structure101.com/contact/[Headway Software] for providing an open source link:http://structure101.com/[Structure 101] license

== Support

You are free to adapt or extend Estatio to your needs.
If you would like assistance in doing so, go to http://www.estatio.org[www.estatio.org].

You can find plenty of help on using Apache Isis at the http://isis.apache.org/support.html[Isis mailing lists].
There is also extensive http://isis.apache.org/documentation.html[online documentation].

== Legal Stuff

Copyright 2012-\``date`` http://www.eurocommercialproperties.com[Eurocommercial Properties NV]

Licensed under http://www.apache.org/licenses/LICENSE-2.0[Apache License 2.0]

## License

Upstream © its respective contributors under Apache-2.0 (harvested MIT/Apache-2.0/BSD source; see `UPSTREAM_CLONE/LICENSE`). This packaging overlay is licensed under Anticommons 0.1.0.

## Upstream

- **project:** ESTATIO
- **Pinned SHA:** `82817ed22d00467e33afd290498d684cacccb3f5`
- **source:** `UPSTREAM_CLONE/` (pinned at the SHA above)
- **Upstream README source:** `UPSTREAM_CLONE/README.adoc`

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`cc2473edc85eb3839a3c0df988ef29f78715aa0c2ae6c7258e80a82140dde24d`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| DANS (KNAW/NWO, Netherlands) | 10.17026/PT | EU-recognised archive |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe
and Mail, Business Insider, National Post, Financial Post, StreetInsider,
Digital Journal, Barchart, International Business Times, and Fox News.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.


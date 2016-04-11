## DEFINITION ##

"Bush leaguer"

(noun)

1. Also called busher. Baseball.

    a player in a minor league.
    an incompetent player, as one who behaves or plays as if he or she belonged in a minor league.

2. a person who performs at an inferior level or in an inferior manner.


---------------------------------------------------

## QUICKSTART ##


To setup with Eclipse (tested on Ubuntu 14.04):

    Install JDK Java8. sudo apt-get install oracle-java8-installer
    Get Spark.
        Download 1.1.0 for Hadoop 2.4. We will not be using Hadoop even though this build supports it.
        Untar the spark tarball. (E.g., in ~/dev)
        Test the installation with ./bin/run-example SparkPi

    Right-click on pom.xml, choose Maven-> install.
    This will now download Spark jars; it will take a while.
    It will also set your Eclipse project's source level to Java 8.

Dataset

    ratings.csv is generated from ratings.ods, which is a spreadsheet for synthesizing data sets to test and fine tune your model.
    Adjust ratings.ods and save as CSV. See readme.txt in data directory for instructions.

Cassandra

    Run Cassandra: sudo /usr/bin/cassandra
    Then create schema by running attached SQL as follows:
        In workspace root, run cqlsh -f ./collabfilter/src/sql/collab_filter_schema.sql

Running tests:

    Run collabfilter.CollabFilterCassandraDriver.main or the CollabFilterTest unit test.



Maintaining a list of domains that IT recruiter scumbags send from makes it easy to filter messages into their own folder.  It's easy to process the list into formats suitable for different mail systems: gmail and sieve rulesets are currently supported.

GMail support is achieved via filters, you can import gmailFilters.xml from the filters page in the interface.

- Filters have a max query length, so we break them up into chunks of 70.
- By default we add a "Recruitment" label and archive any matches, you'll probably want to edit the filters created.
- If you reimport the filters, the originals remain.
- Update the XML based on domains.txt by running domains2gmail.rb


Use the 'addnew.sh' script to add emails and domains.  This takes care of duplicate checking & sorting and automatically strips any username@ portion of the string you feed it.

./scumboxer/toolbox/addnew.sh shinysuit@noisyrecruiters.com

or

./scumboxer/toolbox/addnew.sh -p shinysuit@noisyrecruiters.com


## ROADMAP ##

- Impliment text-analysis engine to recognize common recruiter communication patterns/terms
- Centralize domain database to facilitate a crowdsourced blacklist of scumbag company domains
- Create auto-replier that responds to recruiting spam with an obfuscated link to something awful

# Demo-iDAAS-Connect-Aggregator
Demo of iDAAS Connect Aggregator Capabilities

iDAAS Connect is intended ONLY to enable iDAAS connectivity. iDAAS-Connect-Aggregator specifically ONLY deals with enabling 
iDAAS to all sorts of third party connectivity. For example: RDBMS, Kafka, Mainframe, Files, SFTP, etc.
plus dozens of others are supported.

This is a demonstration of some of the capabilities that iDAAS-Connect-Aggregator can enable and support. 
Currently this demo has a CSV parsing with aggregation with Kafka Topic Push.

The intent of these artifacts to enable
resources to work locally: <br/>
1. platform-addons: needed software to run locally. This currently contains amq-streams-1.5 (which is the upstream of Kafka 2.5)<br/>
2. platform-scripts: support running kafka, creating/listing and deleting topics needed for this solution
and also building and packaging the solution as well. All the scripts are named to describe their capabilities <br/>
3. platform-testdata: sample transactions to leverage for using the platform. <br/>

## Scenario: CSV File Processing
This repository follows a very common general implementation of processing a CSV file from a filesystem. The intent is to pick up
a bar '|' delimited file and process it into a structure and persist the data into a topic.

### Integration Data Flow Steps
 
1. Every 1 minute the defined directory is looked at for any .CSV file, if found the file is processed into a matching structure.
2. The data structure is being aggregated (according to aggregation logic) then persisted into a kafka topic. 
    
## Builds
This section will cover both local and automated builds.

### Local Builds
Within the code base you can find the local build commands in the /platform-scripts directory
1.  Run the build-solution.sh script
It will run the maven commands to build and then package up the solution. The package will use the usual settings
in the pom.xml file. It pulls the version and concatenates the version to the output jar it builds.
Additionally, there is a copy statement to remove any specific version, so it outputs idaas-connect-hl7.jar

### Automated Builds
Automated Builds are going to be done in Azure Pipelines

## Ongoing Enhancements
We maintain all enhancements within the Git Hub portal under the 
<a href="https://github.com/RedHat-Healthcare/iDAAS-Connect-Aggregator/projects" target="_blank">projects tab</a>

## Defects/Bugs
All defects or bugs should be submitted through the Git Hub Portal under the 
<a href="https://github.com/RedHat-Healthcare/iDAAS-Connect-Aggregatort/issues" target="_blank">issues tab</a>

## Chat and Collaboration
You can always leverage <a href="https://redhathealthcare.zulipchat.com" target="_blank">Red Hat Healthcare's ZuilpChat area</a>
and find all the specific areas for iDAAS-Connect-Aggregator. We look forward to any feedback!!

If you would like to contribute feel free to, contributions are always welcome!!!! 

Happy using and coding....
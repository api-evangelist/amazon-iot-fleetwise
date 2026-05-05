---
title: "Generating insights from vehicle data with AWS IoT FleetWise: Introduction (Part 1)"
url: "https://aws.amazon.com/blogs/iot/generating-insights-from-vehicle-data-with-aws-iot-fleetwise-part1/"
date: "Mon, 16 Jan 2023 14:30:23 +0000"
author: "Katja-Maja Kroedel"
feed_url: "https://aws.amazon.com/blogs/iot/tag/aws-iot-fleetwise/feed/"
---
<div> 
 <p><em>This blog post is written by Senior IoT Specialist Solutions Architect Andrei Svirida.</em></p> 
 <p>Automakers, fleet operators, and automotive suppliers are digitalizing their products and services, and vehicle data is fueling this digitalization in several ways. First, access to vehicle data allows evolutionary improvement of existing business processes. One example of this is faster detection of quality-related issues and analysis of their root causes. Second, access to vehicle data is foundational for mega trends like Advanced Driver Assistance Systems (ADAS), power-train electrification, and the mobility sharing economy.</p> 
 <p>However, managing vast amounts of vehicle data can be challenging from the technical (e.g., proprietary Electronic Control Units (ECU) data formats), economical (e.g., connectivity costs), and organizational (e.g., data silos) perspectives.</p> 
 <p><a href="https://aws.amazon.com/iot-fleetwise/">AWS IoT FleetWise</a> is a fully managed AWS service which makes it easier and more cost efficient to collect, transform, and transfer vehicle data to the cloud. Once transferred, automakers can use the data to build applications by capabilities of AWS such as analytics and machine learning.</p> 
 <p>In this blog, you will first get an overview of the use cases enabled by vehicle data access, as well as the typical implementation challenges. Then, you will learn how to use AWS IoT FleetWise to manage vehicle data in a cost-efficient, secure, and scalable way. Finally, we will introduce an example solution for battery health monitoring using AWS IoT FleetWise. This blog is the first part of a blog series. In the second part, you will get an implementation guide on how to set up and run the battery health monitoring solution in your own AWS account.</p> 
 <h2>Use cases for near-real time vehicle data processing</h2> 
 <p>Let’s take a look at some example use cases enabled by near-real time access to the vehicle data.</p> 
 <h3>Vehicle issue prevention</h3> 
 <p>Access to vehicle data in near-real time enables automakers and fleet operators to provide a better driving experience and improve vehicle quality. For example, consider the scenario of an electric vehicle (EV) battery overheating.</p> 
 <p>EV battery temperature is a critical metric that should be continuously analyzed for the entire vehicle fleet. In order to avoid costly continuous data ingestion, you may want to optimize the data collection by setting a threshold on EV battery temperature. If the threshold is breached, the alarm will be triggered. Based on this alarm, an automatic process for detailed collection and analysis of the vehicle data from the Battery Management System (BMS) will begin.</p> 
 <p>The results of this analysis will be provided to the automaker’s quality engineering department, enabling fast assessment of the criticality and possible root causes of the issue. Based on the root cause analysis, the automaker can then take short-term actions to support the driver affected by the issue, as well as mid-term actions to improve vehicle quality.</p> 
 <h3>Optimization loop for Advanced Driver Assistance Systems (ADAS)</h3> 
 <p>ADAS requires vehicles to have both awareness and perception. Awareness is the ability to sense the environment using the vehicle sensors (e.g., camera or Lidar). Perception is the ability to collect data from the vehicle sensors and process that data to understand the world around the vehicle.</p> 
 <p>In order to understand the vehicle sensor data, machine learning models must be constantly retrained and optimized. The purpose of such optimization is to minimize the amount of “unknowns”, (i.e., objects or situations that vehicle perception cannot process). The best data set for retraining is the data extracted from a production vehicle.</p> 
 <p>Until now, extracting data for ADAS optimization from production vehicles at scale was cost-prohibitive due to high connectivity costs or high manual effort.</p> 
 <h2>Implementation challenges</h2> 
 <p>To implement data-driven use cases, automakers and fleet operators must be able to access and process vehicle data fleet-wide and in near-real time. To ensure efficient implementation, vehicle data must be available in standardized formats to facilitate analysis across various types and models of the vehicles. Automotive customers face the following challenges when implementing data-driven use cases:</p> 
 <h3>Implementation complexity due to proprietary data formats</h3> 
 <p>An ECU is an embedded system in a vehicle which controls one or more vehicle components. ECUs are capable of both emitting the data (e.g., vehicle’s BMS sending current battery temperature via CAN bus) and receiving data (e.g., air conditioning system receiving a stop command via CAN bus). ECUs communicate with other vehicle components via vehicle networks. Examples of vehicle networks include CAN, LIN, FlexRay and Ethernet. For Ethernet networks examples of protocols are DDS and SOME/IP. The data formats used in a vehicle vary depending on ECU type and the vehicle network.</p> 
 <p>The variety of data formats leads to high complexity of systems needed to analyze vehicle-wide and fleet-wide vehicle data. This complexity results in a high implementation and maintenance effort, often preventing or slowing down implementation of data-driven use cases.</p> 
 <h3>Accessing vehicle data at scale is cost-prohibitive</h3> 
 <p>Even when the access to vehicle data is technically possible, scaling access to the whole vehicle fleet is often not economically feasible due to high connectivity costs. For this reason, automakers are often prevented from implementing use cases that require fleet-wide access to the vehicle data.</p> 
 <h3>Limited availability of knowledge about ECU data formats</h3> 
 <p>Knowledge of vehicle data formats is often locked in organizational silos. This makes it difficult for teams within the organization to collaborate effectively to innovate based on vehicle data.</p> 
 <p>For example, the application development team might run into difficulties implementing a battery monitoring mobile app for customers. The reason could be that the application development team does not know how to decode BMS data, as this knowledge is only available on the BMS engineering team.</p> 
 <h2>How AWS IoT FleetWise helps to overcome challenges in implementing data-driven use cases</h2> 
 <p>By using AWS IoT FleetWise, customers can overcome the challenges outlined in the previous section with lower development and operational effort.</p> 
 <h3>Unlock standardized access to vehicle data</h3> 
 <p>AWS IoT FleetWise enables automakers and fleet operators to collect vehicle data from multiple vehicle data sources in a standardized way. After storing the collected vehicle data in a purpose-built database such as <a href="https://aws.amazon.com/timestream/?whats-new-cards.sort-by=item.additionalFields.postDateTime&amp;whats-new-cards.sort-order=desc&amp;amazon-timestream-blogs.sort-by=item.additionalFields.createdDate&amp;amazon-timestream-blogs.sort-order=desc">Amazon Timestream</a> or object storage like <a href="https://aws.amazon.com/s3/">Amazon Simple Storage Service (S3)</a> (available after General Availability (GA)), vehicle data can be efficiently queried.</p> 
 <p>For example, using AWS IoT FleetWise, a fleet operator can collect the “Charging Current” metric for a set of heterogeneous vehicles from different manufacturers and store the collected data in Amazon Timestream. Now fleet-wide queries for “Charging Current” metric are possible.</p> 
 <h3>Reduce data volume for cloud ingestion</h3> 
 <p>AWS IoT FleetWise helps to reduce data volume by providing intelligent data filtering capabilities. With AWS IoT FleetWise, you can reduce data volume in two ways.</p> 
 <p>First, you can configure the vehicle to collect only the signals, that are required for the purpose of your use cases. Second, you can configure AWS IoT FleetWise to collect the signals only under certain conditions. Examples for such conditions are scheduled collection (e.g., only between 1PM and 2PM on a specific date) or condition-based collection (e.g., only when battery temperature is above the threshold).</p> 
 <h3>Make vehicle data actionable in near-real time</h3> 
 <p>With AWS IoT FleetWise customers can build solutions acting on the vehicle data in near-real time. For that purpose, AWS IoT FleetWise provides capabilities for ingesting and storing the vehicle data to AWS. The data ingestion allows secure, scalable, and cost-efficient connectivity for any size fleet.</p> 
 <p>After the data is ingested, AWS IoT FleetWise will orchestrate storing the data in a purpose-built database or object storage.</p> 
 <h3>Accelerate innovation</h3> 
 <p>With AWS IoT FleetWise you can accelerate innovation by giving all entitled teams in your company access to the vehicle data. Examples of teams who can benefit from access to the vehicle data include vehicle engineering, quality engineering, application development, sales, and marketing.</p> 
 <h2>Logical architecture of solutions based on AWS IoT FleetWise</h2> 
 <p>Now that we have learned about the capabilities of AWS IoT FleetWise, let us dive deeper into the logical architecture and involved personas. The following image represents a logical architecture of a solution based on AWS IoT FleetWise.</p> 
 <div class="wp-caption alignnone" id="attachment_8687" style="width: 1034px;">
  <img alt="Logical architecture for AWS IoT FleetWise solutions" height="615" src="https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2022/07/08/image001-1-1024x615.png" width="1024" />
  <p class="wp-caption-text" id="caption-attachment-8687">Logical architecture for AWS IoT FleetWise solutions</p>
 </div> 
 <h3>Personas</h3> 
 <p>Two personas who directly interact with AWS IoT FleetWise service are Data Engineer and Vehicle Engineer:</p> 
 <ul> 
  <li>Data Engineer has a task to make the raw data from the vehicles usable by the stakeholders inside the organization. Specific stakeholders may vary depending on the use case.One example is a Quality Assurance department, who is interested in using vehicle data (e.g., temperature sensors) for the root cause analysis of vehicle quality issues. Another example is a team developing an EV battery health monitoring solution, who needs access to BMS system data each time EV battery temperature is above specific threshold.</li> 
  <li>Vehicle Engineer has a detailed knowledge of the vehicle ECUs and vehicle networks. In particular, the Vehicle Engineer is aware of both the signals provided by an individual ECU as well as encoding of these signals in a specific vehicle network (e.g., CAN bus).</li> 
 </ul> 
 <h3>Architectural layers</h3> 
 <p>In order to understand the functionality of AWS IoT FleetWise we will discuss the individual layers of the architecture above.</p> 
 <h3>Collect, transform, and transfer of vehicle data (vehicle-side)</h3> 
 <p>AWS IoT FleetWise Edge Agent is a <a href="https://github.com/aws/aws-iot-fleetwise-edge/blob/main/README.md">C++ software</a> to collect, decode, normalize, cache, and ingest vehicle data to AWS. It supports multiple deployment options, such as vehicle gateways (e.g. <a href="https://www.nxp.com/products/processors-and-microcontrollers/arm-processors/s32g-vehicle-network-processors/s32g2-processors-for-vehicle-networking:S32G2">NXP S32G2</a>), infotainment systems, telecommunication control units or aftermarket devices. At the time of publishing, it supports <a href="https://docs.aws.amazon.com/iot-fleetwise/latest/APIReference/API_CreateDecoderManifest.html">decoding for CAN Bus and OBD2 messages.</a> AWS IoT FleetWise Edge Agent is <a href="https://github.com/aws/aws-iot-fleetwise-edge/blob/main/README.md">available on GitHub</a> under <a href="https://github.com/aws/aws-iot-fleetwise-edge/blob/main/LICENSE">Amazon Software License 1.0.</a></p> 
 <h3>Transport vehicle data to the cloud</h3> 
 <p>To transfer the data over to the cloud, Edge Agent uses <a href="https://aws.amazon.com/iot-core/">AWS IoT Core</a>. It provides a secure, scalable, and cost-efficient MQTT/TLS connectivity.</p> 
 <h3>Orchestrate vehicle data collection</h3> 
 <p>Fleet Operators can use AWS IoT FleetWise service to build and run vehicle data collection pipelines, both for the purpose of manual ad-hoc analysis as well as automated continuous vehicle data processing. They can use the following features of AWS IoT FleetWise:</p> 
 <ul type="disc"> 
  <li>Manage <a href="https://docs.aws.amazon.com/iot-fleetwise/latest/developerguide/campaigns.html">data collection campaigns</a>. A data collection campaign defines which vehicle data and under which conditions shall be collected.</li> 
  <li>Route the vehicle data to the purpose-built database or storage services. At the time of publishing of this blog, AWS IoT FleetWise supports Amazon Timestream service. Amazon S3 will be supported after GA.</li> 
 </ul> 
 <h3>Model signals and vehicles</h3> 
 <p>Before a Data Engineer can create a data collection pipeline, the Vehicle Engineer builds a virtual representation of the vehicles in the cloud. Three key concepts for vehicle modelling with AWS IoT FleetWise are Signal catalog, Vehicle model and Decoder Manifest.</p> 
 <ul type="disc"> 
  <li><a href="https://docs.aws.amazon.com/iot-fleetwise/latest/developerguide/signal-catalogs.html">Signal catalog</a> is a central, company-wide repository of vehicle signals organized in a hierarchical way. It allows you to abstract underlying vehicle implementation details and establish a “common language” across the vehicle fleet.For example, the current charging rate of an EV could be modeled as sensor with data type “float” and addressable by the full qualified name “Powertrain.Battery.Charging.ChargeRate”. The signal catalog is based on <a href="https://covesa.github.io/vehicle_signal_specification/">COVESA`s Vehicle Signal Specification (VSS)</a>.</li> 
  <li>The <a href="https://docs.aws.amazon.com/iot-fleetwise/latest/developerguide/vehicle-models.html">Vehicle model </a>refers to a subset of the signals from the signal catalog with a purpose to model a vehicle type sharing the same signals.</li> 
  <li><a href="https://docs.aws.amazon.com/iot-fleetwise/latest/developerguide/decoder-manifests.html">Decoder manifest</a> contains decoding instructions to transform binary data from the vehicle networks (e.g., CAN) into human-readable.<br /> In an example of CAN bus-based communication, decoder manifest could contain instructions on how to transform a binary CAN bus message with Message id 123 and value 0x0011000 to value 17 of BMS.Battery.BatteryTemperature.</li> 
 </ul> 
 <h3>Store vehicle data</h3> 
 <p>AWS IoT FleetWise stores the collected vehicle data in purpose-built storage services:</p> 
 <ul type="disc"> 
  <li><a href="https://aws.amazon.com/timestream">Amazon Timestream</a> is a fast, scalable, and server-less time series database. We recommend using it to store vehicle data that requires near real-time processing.</li> 
  <li><a href="https://aws.amazon.com/s3/">Amazon S3</a> is a cloud object storage with industry-leading scalability, data availability, security, and performance. We recommend using it to store vehicle data which requires batch processing.</li> 
 </ul> 
 <h3>Analyze and act on vehicle data</h3> 
 <p>Once the vehicle data is stored, it can be analyzed using AWS services for <a href="https://docs.aws.amazon.com/whitepapers/latest/aws-overview/analytics.html">Analytics</a>, <a href="https://docs.aws.amazon.com/whitepapers/latest/aws-overview/machine-learning.html">Machine Learning</a> and <a href="https://docs.aws.amazon.com/whitepapers/latest/aws-overview/application-integration.html">Application Integration</a>, or visualized using <a href="https://aws.amazon.com/grafana/">Amazon Managed Grafana</a> (visualization and dashboarding) or <a href="https://aws.amazon.com/quicksight/">Amazon QuickSight</a> (business intelligence).</p> 
 <h2>Introducing an example solution for battery health monitoring</h2> 
 <p>Now, let’s review an example solution that implements the logical architecture outlined before. You can use this solution to monitor health of the battery in an EV and to notify the driver once the health issue is detected. Below you see an architecture of the solution:</p> 
 <div class="wp-caption alignnone" id="attachment_8688" style="width: 1034px;">
  <img alt="Sample solution for for battery health monitoring" height="575" src="https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2022/07/08/image002-1024x575.png" width="1024" />
  <p class="wp-caption-text" id="caption-attachment-8688">Sample solution for for battery health monitoring</p>
 </div> 
 <p>The solution includes the following components:</p> 
 <h3>1. Vehicle engineer models vehicles and configures decoding rules</h3> 
 <p>First, the Vehicle Engineer uses their deep knowledge of the vehicle design to configure the necessary cloud resources for the AWS IoT FleetWise service (via AWS Management console, AWS CLI or AWS APIs). These resources include <a href="https://docs.aws.amazon.com/iot-fleetwise/latest/developerguide/signal-catalogs.html"> Signal catalog </a> , <a href="https://docs.aws.amazon.com/iot-fleetwise/latest/developerguide/vehicle-models.html"> Vehicle model </a> , <a href="https://docs.aws.amazon.com/iot-fleetwise/latest/developerguide/decoder-manifests.html"> Decoder manifest </a> , and <a href="https://docs.aws.amazon.com/iot-fleetwise/latest/developerguide/vehicles.html"> Vehicle instances </a> .</p> 
 <h3>2. Data engineer starts vehicle data collection campaign</h3> 
 <p>Now, the Data Engineer can initiate a data collection campaign in AWS IoT FleetWise (via <a href="https://docs.aws.amazon.com/iot-fleetwise/latest/developerguide/create-campaign-console.html"> AWS Management console </a> , <a href="https://docs.aws.amazon.com/iot-fleetwise/latest/developerguide/create-campaign-cli.html"> AWS CLI </a> or <a href="https://docs.aws.amazon.com/iot-fleetwise/latest/APIReference/API_CreateCampaign.html">AWS APIs</a>). The campaign configuration contains data like:</p> 
 <ul type="disc"> 
  <li>Unique names of the vehicle signals to be collected and transferred to the cloud</li> 
  <li>For time-based campaigns, a sampling rate for the signal collection</li> 
  <li>For condition-based campaigns, a logical expression used to recognize what data to collect (e.g., <code> $variable.BatteryTemperature &gt; 40.0</code>)</li> 
 </ul> 
 <h3>3. AWS IoT FleetWise sends campaign configuration to the Edge Agent running on the vehicle.</h3> 
 <p><a href="https://aws.amazon.com/iot-core/"> AWS IoT Core </a> service provides secure and scalable transport of data between AWS cloud and the Edge Agent.</p> 
 <h3>4. The Edge Agent runs the data collection campaign</h3> 
 <p>First, the Edge Agent collects the signals specified in the campaign configuration from the vehicle network. In case of intermittent connectivity, the Edge Agent will temporarily store the vehicle data and continue the ingestion once connectivity is available.</p> 
 <h3>5.The Edge Agent ingests the collected vehicle data to the AWS.</h3> 
 <p>AWS IoT Core service provides secure and scalable transport of data between the Edge Agent and AWS cloud.</p> 
 <h3>6. AWS IoT FleetWise stores vehicle data</h3> 
 <p>For data persistence we will use Amazon Timestream, a fast, scalable, and server-less time series database.</p> 
 <h3>7. Battery health detection service analyses vehicle data</h3> 
 <p>The battery health detection component is implemented using an <a href="https://aws.amazon.com/lambda/"> AWS Lambda </a> function. The <a href="https://aws.amazon.com/eventbridge/"> Amazon EventBridge </a> service will be configured to run the AWS Lambda function at a regular rate.</p> 
 <p>On each run the AWS Lambda function queries the vehicle data and analyzes the results to identify the battery health issues. For each identified battery health issue, the AWS Lambda function will ingest a message into <a href="https://aws.amazon.com/kinesis/data-streams/"> Amazon Kinesis Data Streams </a>.</p> 
 <h3>8. Battery management service acts on battery health data</h3> 
 <p>The battery management component will be implemented using an AWS Lambda function. It will process the battery health insights from the data stream. For each insight that requires a user notification, it will retrieve the driver’s contact data from <a href="https://aws.amazon.com/dynamodb/"> Amazon DynamoDB </a> and send a notification request to an <a href="https://aws.amazon.com/sqs/"> Amazon Simple Queue Service (SQS) </a></p> 
 <h3>9. Notification handler service sends an SMS notification to the driver</h3> 
 <p>The notification handler service reads the notification request from Amazon SQS, enriches the Vehicle Identification Number (VIN) data of the vehicle with the contact data of the current vehicle driver, and sends a message to the driver via <a href="https://aws.amazon.com/sns/"> Amazon Simple Notification Service (SNS) </a></p> 
 <h2>Summary and next steps</h2> 
 <p>In this first part of the blog post, you have learned about the use cases, technical capabilities, and a logical architecture of a solution based on AWS IoT FleetWise. Then, we reviewed an architecture of an example solution for battery health monitoring. In the second part of this blog post, we will walk you through the implementation steps for the example solution in your AWS account.</p> 
 <h2>About the author</h2> 
 <p><img alt="" class="alignleft size-full wp-image-8880" height="221" src="https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2022/07/13/image001-1.jpg" width="150" />Andrei Svirida is Senior Specialist Solutions Architect at Amazon Web Services. He is passionate about enabling companies of all sizes and industries to become data-driven businesses. To that end, he helps AWS customers to architect and build secure and scalable solutions on AWS, focusing on IoT, Analytics and Data Engineering. Prior to joining AWS, Andrei worked at KUKA AG as Head for IoT Delivery and as VP in in-house consulting at Deutsche Telekom AG. Andrei has a computer science background and more then 18 years of industry experience.</p> 
</div>

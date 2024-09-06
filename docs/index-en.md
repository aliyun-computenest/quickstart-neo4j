<h1>Neo4j Community Edition Service Instance Deployment Document </h1>

<h2> Overview </h2>

<p>Neo4j is an embedded, disk-based, fully transactional Java persistence engine. Neo4j provides a community version of the service on the computing nest. You can quickly deploy the Neo4j service on the computing nest and implement O & M monitoring without configuring your own cloud host, so that you can easily build your own applications based on Neo4j. This topic describes how to activate the Neo4j Community Edition service on the computing nest, as well as the deployment process and usage instructions. </p>

<h2> Billing instructions </h2>

<p> The cost of Neo4j Community Edition on the calculation nest mainly involves:</p>

<ul>
<li> Selected vCPU and Memory Specifications </li>
<li> Disk capacity </li>
<li> Internet bandwidth </li>
</ul>

<p> Billing methods include:</p>

<ul>
<li> Pay-As-You-Go (hourly)</li>
<li> monthly package </li>
</ul>

<p> The estimated cost is visible in real time when the instance is created. </p>

<h2> Deployment Architecture </h2>

<p>Neo4j uses a stand-alone deployment architecture. </p>

<h2> Permissions required for RAM accounts </h2>

<p> The Neo4j service needs to access and create resources such as ECS and VPC. If you use a RAM user to create a service instance, you need to add the corresponding resource permissions to the account of the RAM user before creating the service instance. For more information about how to add RAM permissions, see <a href = "https://help.aliyun.com/document_detail/121945.html"> Authorize RAM users </a>. The required permissions are shown in the following table. </p>

<table>
<thead>
<tr>
<th> Permission policy name </th>
<th> Remarks </th>
</tr>
</thead>
<tbody>
<tr>
<td>AliyunECSFullAccess</td>
<td> Permissions to manage ECS </td>
</tr>
<tr>
<td>AliyunVPCFullAccess</td>
<td> Permissions for managing VPC networks </td>
</tr>
<tr>
<td>AliyunROSFullAccess</td>
<td> Manage permissions for Resource Orchestration Services (ROS) </td>
</tr>
<tr>
<td>AliyunComputeNestUserFullAccess</td>
<td> Manage user-side permissions for the compute nest service (ComputeNest) </td>
</tr>
<tr>
<td>AliyunCloudMonitorFullAccess</td>
<td> Permissions to manage CloudMonitor (CloudMonitor) </td>
</tr>
</tbody>
</table>

<h2> Deployment process </h2>

<h3> Deployment steps </h3>

<p> Click <a href = "https://computenest.console.aliyun.com/user/cn-hangzhou/serviceInstanceCreate?ServiceId=service-fe1bbe81bdac493eb99b"> Deployment link </a> to go to the service instance deployment page, and fill in the parameters according to the prompts on the page to complete the deployment. </p>

<h3> Deployment parameters </h3>

<p> When you create a service instance, you need to configure the service instance information. The details of the Neo4j Community Edition service instance input parameters are described below. </p>

<table>
<thead>
<tr>
<th> Parameter group </th>
<th> Parameter item </th>
<th> Example </th>
<th> Description </th>
</tr>
</thead>
<tbody>
<tr>
<td> Select a template </td>
<td></td>
<td> Three-node version </td>
<td> Template schema type </td>
</tr>
<tr>
<td> Service instance name </td>
<td></td>
<td>test</td>
<td> Name of the instance </td>
</tr>
<tr>
<td> Region </td>
<td></td>
<td> China (Hangzhou)</td>
<td> Select the region of the service instance. We recommend that you select the region nearby to obtain better network latency. </td>
</tr>
<tr>
<td> Availability Zone Configuration </td>
<td> Deployment area </td>
<td> Availability Zone I</td>
<td> Different available regions in the region </td>
</tr>
<tr>
<td> Payment type configuration </td>
<td> Payment type </td>
<td> Pay-As-You-Go or Subscription </td>
</tr>
<tr>
<td> Select an existing basic resource configuration </td>
<td>VPC ID</td>
<td>vpc-xxx</td>
<td> Select the ID of the VPC. </td>
</tr>
<tr>
<td> Select an existing basic resource configuration </td>
<td> Switch ID</td>
<td>vsw-xxx</td>
<td> Select the switch ID. If the switch cannot be found, try switching the region and zone. </td>
</tr>
<tr>
<td>ECS instance configuration </td>
<td> Instance type </td>
<td>ecs.g7.large</td>
<td> Instance type, which can be selected according to actual needs </td>
</tr>
<tr>
<td>ECS instance configuration </td>
<td> System disk space </td>
<td>40</td>
<td> System disk space can be selected according to actual needs </td>
</tr>
<tr>
<td>ECS instance configuration </td>
<td> Data disk space </td>
<td>40</td>
<td> Data disk space, which can be selected according to actual needs </td>
</tr>
<tr>
<td>ECS instance configuration </td>
<td> Instance password </td>
<td><strong><em>*</strong></em>*</td>
<td> Set the instance password. It is 8 to 30 characters in length and must contain three items (uppercase letters, lowercase letters, numbers, ()'~!@#$%^& *-+ ={}[]:;' <>,.?/special symbols)</td>
</tr>
<tr>
<td>ECS instance configuration </td>
<td> Enable public IP</td>
<td>true</td>
<td> Whether to enable public IP</td>
</tr>
</tbody>
</table>

<p><img src="1.jpg" alt="1.jpg" /></p>

<h3> Verify Results </h3>

<ol>
<li> View the service instance.
After the service instance is created successfully, the deployment time takes about 2 minutes. After the deployment is complete, the corresponding service instance is displayed on the page. </li>
</ol>

<p><img src="2.jpg" alt="2.jpg" /></p>

<ol start="2">
<li> Access Neo4j through a service instance </li>
</ol>

<p><img src="3.jpg" alt="3.jpg" />
After entering the corresponding service instance, you can obtain the PublicEndpoint, PrivateEndpoint, and InstallPath on the page. </p>

<p><strong><em> Note:</em></strong></p>

<pre><code> The ECS security group opens the 7474 port by default. If you want to connect to the database from a browser through the Internet, you need to open the security group 7687 port.
</code></pre>

<h3> Using Neo4j</h3>

<p> Visit the Neo4j website to learn how to use Neo4j:<a href = "https://neo4j.com/docs/">Neo4j Usage Documentation </a></p>

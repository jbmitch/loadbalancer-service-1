---

copyright:
  years: 2017
lastupdated: "2017-08-21"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Sample Configuration Flow
The GUI screens in this section are mock-up screens only. The actual screens may vary. 

1. Begin by logging into your IBM Softlayer Bluemix account using your regular login ID. Click **Add New** to begin.

2. Pick your data center and review the plan information, then click **Next**. 

3. Select the subnet which can be reached by your back-end compute servers (VSI, bare metal).

	Select the private subnet to which the load balancer will connect. This subnet must have network connectivity with backend servers hosting your application. This means that the backend servers can be on the same subnet as the one you select for the load balancer, or the backend servers can be on the subnet(s) that have Layer-3 connectivity with the selected subnet (you may have to enable “VLAN Spanning” in this case). 
	
	Note that the corresponding public subnet is selected by the implementation automatically. The load balancer uses two IP addresses from the private subnet, and three IP addresses from the public subnet. If not enough IP addresses are available, the order of subsequent provisioning will fail.
	
4. Configure the load balancer name and description. Also, specify the front-end and back-end protocol and port mappings. You can add up to four ports. You may select HTTP, HTTPS or TCP as your front-end protocol. 

	HTTPS traffic must be terminated. As a result, your back-end protocol options are HTTP (for incoming HTTP and HTTPS) or TCP. The front-end port numbers must be unique. A default health check automatically is associated with each of the back-end port. The default load balancing method used is 'round robin' and stickiness is disabled. Optionally, you can change the load balancing method and enable client session stickiness per port.

	For HTTPS protocol configurations, you may refer to your pre-existing certificate in the certificate store, or you may upload a new certificate.

5. Next, associate your application servers (that is, the compute instances hosting your application) to the load balancer. Ensure that these backend servers have network connectivity with the private subnet you chose in step ‘3’.

6. Accept the Master Service Agreement and click **Create** to create your service.

7. You will be directed to the summary table, which displays the load balancer service instance you just created. Please pay attention to the **Status** field. A status of 'Pending' implies that an operation is in progress in the background. No new configuration changes can be accepted until the operation completes and its status changes to ‘Running’. You may need to refresh your screen to see the latest status.
 
8. Clicking on the service name on this page takes you to the service overview. 
	
9. You can also navigate to **Server instances** and **Protocols** tabs to edit your existing configuration.

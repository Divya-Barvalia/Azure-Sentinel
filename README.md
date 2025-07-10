<h1 align="center">🌐 Monitoring and Investigating Endpoints with Azure Sentinel</h1>

<p align="center">
  A full-stack investigation of malicious login attempts in an Azure-hosted Windows VM, leveraging Microsoft Sentinel, KQL, and watchlists for Geopgraphical-IP threat mapping.
</p>

<hr/>

<h2>📝 Summary</h2>

<p>
  This project focuses on deploying a Windows VM in Azure, collecting security logs from it, and leveraging Microsoft Sentinel to analyze and visualize attack patterns. Using Kusto Query Language (KQL), a watchlist, and a custom workbook, the project mapped attacker IPs to global locations and created a real-time threat intel dashboard. It demonstrates a complete monitoring pipeline—from raw event collection to geospatial analysis in a SIEM environment.
</p>

<hr/>

<h2>📌 Workflow & Integrations</h2>

<ol>
  <li>
    ✅ <strong>Set up an Azure account</strong><br/>
    <img src="screenshots/step1.png" alt="Azure account setup" width="600"/>
  </li>
  <li>
    🗂️ <strong>Created a resource group</strong><br/>
    <img src="screenshots/step2.png" alt="Resource group creation" width="600"/>
  </li>
  <li>
    🌐 <strong>Deployed a virtual network (VNet) within the resource group</strong><br/>
    <img src="screenshots/step3.png" alt="Virtual network setup" width="600"/>
  </li>
  <li>
    💻 <strong>Created a Windows 10 pro VM for and linked to the resource group and VNet</strong><br/>
    <img src="screenshots/step4.png" alt="VM deployment" width="600"/>
  </li>
  <li>
    🔐 <strong>Connected to the VM via Remote Desktop Protocol (RDP)</strong><br/>
    <img src="screenshots/step5.png" alt="RDP session" width="600"/>
  </li>
  <li>
    📶 <strong>Verified connectivity by pinging the VM’s public IP from local PC</strong><br/>
    <img src="screenshots/step6.png" alt="Ping verification" width="600"/>
  </li>
  <li>
    📋 <strong>Viewed failed login attempts using Windows Event Viewer</strong><br/>
    Filtered for <code>Event ID 4625</code> to isolate failed logon attempts.<br/>
    <img src="screenshots/step7.png" alt="Event viewer logs" width="600"/>
  </li>
  <li>
    📊 <strong>Created a Log Analytics Workspace and linked it to Microsoft Sentinel</strong><br/>
    <img src="screenshots/step8.png" alt="Sentinel workspace creation" width="600"/>
  </li>
  <li>
    📦 <strong>Downloaded Windows Security Events via the Microsoft Sentinel Content Hub</strong><br/>
    <img src="screenshots/step9.png" alt="Security events content pack" width="600"/>
  </li>
  <li>
    🛠️ <strong>Created a Data Collection Rule (DCR) using the Azure Monitoring Agent</strong><br/>
    <img src="screenshots/step10.png" alt="DCR setup" width="600"/>
  </li>
  <li>
    🧪 <strong>Queried logs with Kusto Query Language (KQL)</strong><br/>
    Used KQL to search for failed logon attempts and analyze trends.<br/>
    <img src="screenshots/step11.png" alt="KQL security event query" width="600"/>
  </li>
  <li>
    🌍 <strong>Created a threat intelligence watchlist with known attacker IPs and geolocations</strong><br/>
    <img src="screenshots/step12.png" alt="Watchlist creation" width="600"/>
  </li>
  <li>
    📡 <strong>Executed a KQL query to match login attempts with known malicious IPs from the watchlist</strong><br/>
    This helped identify attacker locations.<br/>
    <img src="screenshots/step13.png" alt="KQL + Watchlist for attacker mapping" width="600"/>
  </li>
  <li>
    🗺️ <strong>Built a workbook in Sentinel to visualize attacker locations</strong><br/>
    Used the advanced editor and <code>geo_ip</code> enrichment to map over 50,000 IP ranges.<br/>
    <img src="screenshots/step14.png" alt="Sentinel map workbook" width="600"/>
  </li>
</ol>

<hr/>

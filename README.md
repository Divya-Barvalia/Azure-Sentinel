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
    🗂️ <strong>Created a resource group within Microsoft Azure</strong><br/>
    <img src="Screenshots/Resource-Group.png" width="800"/>
  </li>
  <li>
    🌐 <strong>Deployed a virtual network (VNet) within the resource group</strong><br/>
    <img src="Screenshots/Group-VNET.png" width="800"/>
  </li>
  <li>
    💻 <strong>Created a Windows 10 pro VM for and linked to the resource group and VNet</strong><br/>
    <img src="Screenshots/Win10Client.png" width="600"/>
  </li>
  <li>
    🔐 <strong>Connected to the VM via Remote Desktop Protocol (RDP)</strong><br/>
  </li>
  <li>
    📶 <strong>Verified connectivity by pinging the VM’s public IP from local PC</strong><br/>
    <img src="Screenshots/TestVM-Running.png"  width="400"/>
  </li>
  <li>
    📋 <strong>Viewed failed login attempts using Windows Event Viewer</strong><br/>
    Filtered for <code>Event ID 4625</code> to isolate failed logon attempts.<br/>
    <img src="Screenshots/BadLogin-OnVM.png"  width="600"/>
  </li>
  <li>
    📊 <strong>Created a Log Analytics Workspace and linked it to Microsoft Sentinel</strong><br/>
    <img src="Screenshots/SentinelWorkspace.png"  width="600"/>
  </li>
  <li>
    📦 <strong>Downloaded Windows Security Events via the Microsoft Sentinel Content Hub</strong><br/>
    <img src="Screenshots/Sentinel-ContentHub.png" width="500"/>
  </li>
  <li>
    🛠️ <strong>Created a Data Collection Rule (DCR) using the Azure Monitoring Agent</strong><br/>
    <img src="Screenshots/CollectionRule.png"  width="600"/>
  </li>
  <li>
    🧪 <strong>Queried logs with Kusto Query Language (KQL)</strong><br/>
    Used KQL to search for failed logon attempts and analyze trends.<br/>
    <img src="Screenshots/BadLogin-SentinelLogged.png" width="700"/><img src="Screenshots/Search2.png" width="700"/><img src="Screenshots/Search3.png" width="350"/><img src="Screenshots/Search4-Events.png" width="700"/>
  </li>
  <li>
    🌍 <strong>Created a threat intelligence watchlist with known attacker IPs and geolocations that mapped over 50,000 IP ranges.</strong><br/>
    <img src="Screenshots/SentinelWatchlist.png"  width="600"/>
  </li>
  <li>
    📡 <strong>Executed a KQL query to match login attempts with known malicious IPs from the watchlist</strong><br/>
    This helped identify attacker locations.<br/>
    <img src="Screenshots/Watchlist-Search.png"  width="600"/>
  </li>
  <li>
    🗺️ <strong>Built a workbook in Sentinel to visualize attacker locations</strong><br/>
    Used the advanced editor and <code>geo_ip</code> enrichment.<br/>
    <img src="Screenshots/AttackMap.png"  width="350"/>
  </li>
</ol>

<hr/>

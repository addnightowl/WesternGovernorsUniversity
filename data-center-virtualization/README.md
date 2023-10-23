# D087 - Data Center Virtualization

<!-- 
A. SYSTEMS ANALYSIS OF CURRENT ENVIRONMENT

Augusta Crissy Detective Games’ expected server resource requirements will rise in the future as demand for their new virtual reality escape room game soars. To keep up with the increased traffic, more servers will have to be set up and brought online. It will be costly to install more physical servers in the future due to data center capacity constraints. The project manager has requested that a design plan and a prototype be developed for the data center virtualization project, as the company requires assurances that a solution can be created and operated in accordance with the expected benefits, anticipated growth, and resource requirements.

ACDG IT infrastructure is currently comprised of two on-premises networks:

1. A single ADMIN network that provides administrative access to all switches, a storage area network (SAN), and various computer systems for patches, updates, maintenance, backups, game updates, and other general support.

2. A single DATA network for customer gaming play.

a. Staff members do not have access to the ADMIN network; instead, they can only connect to the game play network through the DATA network.

Current Limitations & Solutions:

I. Scalability:

a. Although ACDG has the proper server capacity and technical specifications to support its current games and growing demands. The company cannot keep up with future gaming demands with the current on-premises infrastructure due to the lack of physical space, costly server additions and maintenance, and the inability to scale resources in real-time.

b. A virtualized environment lowers capital expenses and operating costs, minimizes downtime, and enables rapid resource provisioning with the click of a button.

II. Network Management:

a. The current network is overburdened with numerous resources, posing multiple security risks to the company's IT assets as well as current and prospective subscribers. Employees' ability to complete important job-related tasks is hampered by limited network connections.

b. A virtualized environment simplifies data center management by allowing all resources to be accessed from a centralized server. A virtual environment also allows for the provision of a real Software-Defined Data Center.

III. Availability:

a. In the event of a hardware breakdown or natural disaster, the current network lacks logical isolation and redundancy.

b. A virtualized environment optimizes IT productivity, reliability, agility, and availability while also improving business continuity and disaster recovery.

Given the ACDG requirements and current network configurations, the limited scalability, network management, and availability justify why a virtualized environment will be feasible for future growth aspirations.

B. VIRTUALIZATION SOLUTION

According to the configuration provided in the Company Overview and Requirements document, a virtualized environment will be deployed to an ESXi host in accordance with the company's requirements.

HOW THE SOLUTION MEETS BUSINESS NEEDS

Our proposed solution summarizes several of the benefits of virtualization and should thus serve as an adequate example of virtualization's strengths. To properly meet business requirements, this solution should be installed in conjunction with a vSphere Datacenter. This would enable full active directory integration and a significantly expanded feature set than is now offered in the free ESXi edition.

HOW THE SOLUTION MEETS THE TECHNICAL REQUIREMENTS

A single VMWare ESXi hypervisor will be utilized to demonstrate a virtualized environment - Proof of Concept. The ESXi server is equipped with sufficient capabilities to run four Windows virtual machines (VM’s) and one virtual router. To support the infrastructure, the network will be configured utilizing ESXi's default virtual switch (vSwitch0) and securely segregated within additional port groups (VLAN’s).

Virtual hardware allocations and network segregation for each VM within ESXi for our proposed solution, includes:

1. ESXi - Virtual Switch (vSwitch0) and Port Groups:

· VLANs created in ESXi within Port Groups and linked to vSwitch0.

1. Public (VLAN 0) – [WAN in pfSense].

2. DEV (VLAN 2) – [LAN in pfSense].

3. SysADMIN (VLAN 3) – [OPT1 in pfSense].

4. Management Network (Default in ESXi)

2. Router: pfSense

· vCPU Cores - 1

· RAM (GB) - 1

· Storage (GB) - 8

· Network Adapters - Public (VLAN 0), DEV (VLAN 2), SysADMIN (VLAN 3)

· ISO - ISO [datastore1] iso/pfSense-CE-2.4.4-RELEASE-p3-amd64.iso

3. DC01: Windows Server 2019 Standard

· vCPU Cores - 2

· RAM (GB) - 4

· Storage (GB) - 40

· Network Adapters - Public DEV (VLAN 2), SysADMIN (VLAN 3)

· ISO - ISO [datastore1] iso/Windows_Server_2019_Eval.iso

· VMware Tools - ISO [datastore1] iso/ESX_VMTools_ForWindows.iso

· Domain: augustacrissy.lab

· DHCP - Enabled

· DNS - Enabled

· RDP - Enabled

4. JMP01: Windows 10 – Enterprise

· vCPU Cores - 2

· RAM (GB) - 4

· Storage (GB) - 32

· Network Adapters - DEV (VLAN 2), SysADMIN (VLAN 3)

· ISO - ISO [datastore1] iso/Windows10_EnterpriseEval.iso

· VMware Tools - ISO [datastore1] iso/ESX_VMTools_ForWindows.iso

· Domain: augustacrissy.lab

· RDP - Enabled

5. IIS01: Windows Server 2019 Datacenter

· vCPU Cores - 2

· RAM (GB) - 4

· Storage (GB) - 40

· Network Adapters - Public (VLAN 0), Public (VLAN 0), DEV (VLAN 2), SysADMIN (VLAN 3)

· ISO - ISO [datastore1] iso/Windows_Server_2019_Eval.iso

· VMware Tools - ISO [datastore1] iso/ESX_VMTools_ForWindows.iso

· Domain: augustacrissy.lab

· NIC Teaming - IIS01_NIC_TEAM

· Network Load Balancing (NLB) - Configure to IP Address on Public network-(172.16.0.66)

· RDP - Enabled

6. IIS02: Windows Server 2019 Datacenter

· vCPU Cores - 2

· RAM (GB) - 4

· Storage (GB) - 40

· Network Adapters - Public (VLAN 0), Public (VLAN 0), DEV (VLAN 2), SysADMIN (VLAN 3)

· ISO - ISO [datastore1] iso/Windows_Server_2019_Eval.iso

· VMware Tools - ISO [datastore1] iso/ESX_VMTools_ForWindows.iso

· Domain: augustacrissy.lab

· NIC Teaming - IIS02_NIC_TEAM

· Network Load Balancing (NLB) - Configure to IP Address on Public network-(172.16.0.66)

· RDP - Enabled -->
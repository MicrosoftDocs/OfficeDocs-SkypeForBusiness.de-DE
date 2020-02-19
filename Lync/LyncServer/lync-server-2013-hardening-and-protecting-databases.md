---
title: 'Lync Server 2013: Sichern und schützen von Datenbanken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f222e92da686792a48ccceeaf1686d96f0406e50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="9ae5c-102">Härten und schützen der Datenbanken von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ae5c-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ae5c-103">_**Letztes Änderungsstand des Themas:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="9ae5c-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="9ae5c-104">Microsoft lync Server 2013 hängt auch von SQL Server Datenbanken zum Speichern von Benutzerinformationen, Konferenzstatus, Archivierungsdaten und Anruf Detail Datensätzen (CDRs) ab.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="9ae5c-105">Sie können die Verfügbarkeit von lync Server 2013 Daten in lync Server Back-End-Datenbanken maximieren, indem Sie die Anwendungsdaten auf eine Weise partitionieren, die die Fehlertoleranz verbessert und die Problembehandlung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="9ae5c-106">Um diese Ziele zu erreichen, partitionieren Sie die Anwendungsdaten nach folgendem:</span><span class="sxs-lookup"><span data-stu-id="9ae5c-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="9ae5c-107">**Mithilfe der bewährten Methoden**   für die Server Partitionierung werden Betriebssystem-, Anwendungs-und Programmdateien von ihren Datendateien getrennt.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="9ae5c-108">**Durch das Speichern von Transaktionsprotokolldateien und Datenbankdateien**   werden diese Dateien separat gespeichert, um die Fehlertoleranz zu erhöhen und die Wiederherstellung zu optimieren und Sie auf einem verschlüsselten Datenträger oder Volume zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="9ae5c-109">**Verwenden von Server Clustering**   Cluster die Back-End-Server zur Optimierung lync Server 2013 Systemverfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="9ae5c-110">**Sicherstellen, dass alle Datensicherungen verschlüsselt und ordnungsgemäß behandelt**   werden verlorene, verworfene oder verlegte Sicherungsmedien können eine erhebliche Bedrohung für die Datensicherheit für lync Server 2013 Bereitstellungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="9ae5c-111">Auf einem beliebigen lync Server 2013 Server mit Ausnahme von Standard Edition-Server kann auf die SQL Server Express Instanz (RTCLOCAL-Instanz) nicht remote zugegriffen werden, und es werden keine lokalen Firewall-Ausnahmen erstellt, außer SQL Server Express auf einem Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="9ae5c-112">Auf einem Standard Edition-Server sind sowohl die Back-End-Datenbank als auch der zentrale Verwaltungsspeicher (CMS) so eingerichtet, dass Sie Remote verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="9ae5c-113">Um SQL Server Datenbanken zu verhärten, können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="9ae5c-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="9ae5c-114">Passen Sie die SQL Server Express Firewall auf Standard Edition-Servern an, wodurch der Umfang von Servern eingeschränkt wird, die Remote auf die Datenbank zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-114">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="9ae5c-115">Standardmäßig kann eine beliebige IP-Adresse Remote auf die Datenbank zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-115">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="9ae5c-116">Verwenden Sie SQL Server Konfigurations-Manager, um die Protokolle, IP-Adressen und Ports für SQL Server Remotezugriff anzugeben:</span><span class="sxs-lookup"><span data-stu-id="9ae5c-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="9ae5c-117">Lync Server 2013 verwendet das TCP/IP-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="9ae5c-118">Er unterstützt IP Version 4 (IPv4), jedoch nicht IP Version 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="9ae5c-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9ae5c-119">Lync Server 2013 können in einem Netzwerk mit aktiviertem dualen IP-Stack funktionieren.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="9ae5c-120">Lync Server 2013 unterstützt mehrere IP-Adressen (Multi-Homed-Netzwerk-Adresskarten).</span><span class="sxs-lookup"><span data-stu-id="9ae5c-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="9ae5c-121">Sie können angeben, dass SQL Server nur bestimmte IP-Adressen (einzelne Adressen oder Subnetze) abhören und nur bestimmte Protokolle verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="9ae5c-122">Lync Server 2013 unterstützt statische und dynamische SQL Server Ports.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="9ae5c-123">Führen Sie SQL Server auf einem statischen (nicht-standardmäßigen) Port aus, und führen Sie SQL Server Browser nicht aus (damit der Abhör Port dem Client nicht gemeldet werden kann).</span><span class="sxs-lookup"><span data-stu-id="9ae5c-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="9ae5c-124">Dies erfordert eine benutzerdefinierte Konfiguration für jeden SQL Server Client, einschließlich Front-End-Server, Monitoring Server, Archivierungsserver und Verwaltungskonsole (Ausführung lync Server-Verwaltungsshell, lync Server-Systemsteuerung oder Topologie-Generator) und alle anderen Server mit lync Server Datenbanken).</span><span class="sxs-lookup"><span data-stu-id="9ae5c-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ae5c-125">Der Zugriff auf Datenbanken muss auf vertrauenswürdige Datenbankadministratoren limitiert sein.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="9ae5c-126">Ein böswilliger Datenbankadministrator kann Daten in die Datenbanken einfügen oder ändern, um Rechte über die lync Server 2013 Server zu erwerben oder vertrauliche Informationen von den Diensten abzurufen, selbst wenn dem Datenbankadministrator kein direkter Zugriff gewährt wurde oder Steuerung der lync Server 2013 Server.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="9ae5c-127">Ausführliche Informationen zu benutzerdefinierten Konfigurationen und zum Härten SQL Server Datenbanken finden Sie im NextHop-Blog Artikel "Verwenden von lync Server 2010 mit einer benutzerdefinierten SQL Server Netzwerk [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008)Konfiguration" unter.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ae5c-128">Sie können auch Betriebssysteme und Anwendungsserver verhärten, und Sie können mithilfe von Gruppenrichtlinien Sicherheitssperren in ihrer lync Server-Bereitstellung implementieren.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="9ae5c-129">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Härten und schützen von Servern und Anwendungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


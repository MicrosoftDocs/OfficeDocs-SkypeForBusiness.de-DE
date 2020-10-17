---
title: 'Lync Server 2013: Anforderungen zum Veröffentlichen einer Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9f4186a351876b874a8b84963f9923369511f65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511822"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="224c1-102">Anforderungen zum Veröffentlichen einer Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="224c1-102">Requirements to publish a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="224c1-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="224c1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="224c1-104">In diesem Thema werden die Infrastruktur-und Softwareanforderungen beschrieben, die für die Veröffentlichung einer Topologie spezifisch sind, sei es mithilfe des Topologie-Generators oder der Befehlszeilenschnittstelle für die lync Server 2013 Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="224c1-104">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="224c1-105">Diese Anforderungen gelten zusätzlich zu den allgemeinen Betriebssystem-, Software-und Berechtigungsanforderungen für alle lync Server 2013 Verwaltungstools.</span><span class="sxs-lookup"><span data-stu-id="224c1-105">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="224c1-106">Stellen Sie sicher, dass Sie alle Anforderungen an die Verwaltungstools erfüllen, bevor Sie eine Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="224c1-106">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="224c1-107">Sie müssen den Topologie-Generator auf einem Computer ausführen, der der gleichen Domäne oder Gesamtstruktur der lync Server 2013 Bereitstellung beigetreten ist, die Sie erstellen, damit Active Directory-Domänendienste Vorbereitungsschritte bereits abgeschlossen sind, sodass Sie die Verwaltungstools auf diesem Computer verwenden können, um die Topologie erfolgreich zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="224c1-107">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="224c1-p102">Die in der Topologie definierten Computer müssen mit der Domäne (mit Ausnahme der Edgeserver) und in AD DS verbunden werden. Die Computer müssen beim Veröffentlichen der Topologie jedoch nicht online sein.</span><span class="sxs-lookup"><span data-stu-id="224c1-p102">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS. However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="224c1-110">Die Dateifreigabe für den Pool muss erstellt worden und für Remotebenutzer verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="224c1-110">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="224c1-111">Zum Veröffentlichen eines Enterprise Edition-Front-End-Pool muss der SQL Server basierte Back-End-Server der Domäne hinzugefügt werden, in der Sie die Server bereitstellen, Online und mit den entsprechenden Firewallregeln konfiguriert, um Sie Remotebenutzern zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="224c1-111">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="224c1-112">Ausführliche Informationen zum Angeben von Firewall-Ausnahmen finden Sie unter [Understanding Firewall Requirements for SQL Server with lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="224c1-112">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="224c1-113">Weitere Informationen zum Konfigurieren von SQL Server finden Sie unter [configure SQL Server for lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="224c1-113">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="224c1-114">Standard Edition-Server verfügt über eine zusammengefasste Datenbank, in der die veröffentlichte Konfiguration akzeptiert wird.</span><span class="sxs-lookup"><span data-stu-id="224c1-114">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="224c1-115">Sie müssen zuerst die Setup Aufgabe <STRONG>Prepare First Standard Edition-Server</STRONG> im lync Server-Bereitstellungs-Assistenten ausführen.</span><span class="sxs-lookup"><span data-stu-id="224c1-115">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="224c1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="224c1-116">See Also</span></span>


[<span data-ttu-id="224c1-117">Veröffentlichen der Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="224c1-117">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="224c1-118">Delegieren von Setup Berechtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="224c1-118">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="224c1-119">Softwareanforderungen für Verwaltungstools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="224c1-119">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="224c1-120">Betriebssystemunterstützung für Server und Tools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="224c1-120">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="224c1-121">Für die Einrichtung und Verwaltung von lync Server 2013 erforderliche Administrator Rechte und-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="224c1-121">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


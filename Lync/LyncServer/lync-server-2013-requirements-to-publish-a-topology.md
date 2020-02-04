---
title: 'Lync Server 2013: Anforderungen an das Veröffentlichen einer Topologie'
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
ms.openlocfilehash: 0f1422df35ebbe9f368dc8aa3d121caf740e7033
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="bdb14-102">Anforderungen an das Veröffentlichen einer Topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdb14-102">Requirements to publish a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdb14-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bdb14-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bdb14-104">In diesem Thema werden die Infrastruktur-und Softwareanforderungen beschrieben, die für das Veröffentlichen einer Topologie spezifisch sind, sei es mithilfe des Topologie-Generators oder der Befehlszeilenschnittstelle der lync Server 2013-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="bdb14-104">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="bdb14-105">Diese Anforderungen gelten zusätzlich zu den allgemeinen Betriebssystem-, Software-und Berechtigungsanforderungen, die für alle lync Server 2013-Verwaltungstools gelten.</span><span class="sxs-lookup"><span data-stu-id="bdb14-105">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="bdb14-106">Stellen Sie sicher, dass Sie die Anforderungen aller administrativen Tools erfüllen, bevor Sie eine Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="bdb14-106">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="bdb14-107">Sie müssen den Topology Builder auf einem Computer ausführen, der mit der gleichen Domäne oder Gesamtstruktur der von Ihnen erstellten lync Server 2013-Bereitstellung verbunden ist, damit die Schritte zur Vorbereitung der Active Directory-Domänendienste bereits abgeschlossen sind, sodass Sie die Verwaltungstools auf verwenden können. dieser Computer, um Ihre Topologie erfolgreich zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="bdb14-107">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="bdb14-108">Die in der Topologie definierten Computer müssen der Domäne, mit Ausnahme von Edgeserver und in AD DS, beigetreten sein.</span><span class="sxs-lookup"><span data-stu-id="bdb14-108">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS.</span></span> <span data-ttu-id="bdb14-109">Die Computer müssen jedoch nicht online sein, wenn Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="bdb14-109">However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="bdb14-110">Die Dateifreigabe für den Pool muss erstellt und für Remotebenutzer verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="bdb14-110">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="bdb14-111">Zum Veröffentlichen eines Enterprise Edition-Front-End-Pools muss der auf SQL Server basierende Back-End-Server mit der Domäne verbunden sein, in der Sie die Server online bereitstellen, und mit den entsprechenden Firewallregeln konfiguriert werden, um ihn Remotebenutzern zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="bdb14-111">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="bdb14-112">Details zum Angeben von Firewall-Ausnahmen finden Sie unter [Grundlegendes zu Firewall-Anforderungen für SQL Server mit lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bdb14-112">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="bdb14-113">Weitere Informationen zum Konfigurieren von SQL Server finden Sie unter [Konfigurieren von SQL Server für lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="bdb14-113">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bdb14-114">Der Standard Edition-Server verfügt über eine Datenbank, die die veröffentlichte Konfiguration akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="bdb14-114">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="bdb14-115">Sie müssen zuerst im lync Server-Bereitstellungs-Assistenten die Aufgabe " <STRONG>First Standard Edition-Server vorbereiten</STRONG> " ausführen.</span><span class="sxs-lookup"><span data-stu-id="bdb14-115">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="bdb14-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdb14-116">See Also</span></span>


[<span data-ttu-id="bdb14-117">Veröffentlichen der Topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdb14-117">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="bdb14-118">Delegieren von Setupberechtigungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdb14-118">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="bdb14-119">Softwareanforderungen für Verwaltungstools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdb14-119">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="bdb14-120">Betriebssystemunterstützung für Server und Tools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdb14-120">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="bdb14-121">Erforderliche Administratorrechte und Gruppenmitgliedschaften für die Installation und Verwaltung von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdb14-121">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


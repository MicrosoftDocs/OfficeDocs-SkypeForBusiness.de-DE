---
title: Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers – Aufgaben am zentralen Standort
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9aa6d38ec873652feae6ef6a374ee5b771520b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="10c01-102">Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am zentralen Standort</span><span class="sxs-lookup"><span data-stu-id="10c01-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10c01-103">_**Letztes Änderungsdatum des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="10c01-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="10c01-104">Führen Sie die Aufgaben in diesem Abschnitt auf der zentralen Website aus.</span><span class="sxs-lookup"><span data-stu-id="10c01-104">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="10c01-105">Wenn Sie einen Überlebenden Verzweigungs Server bereitstellen, überspringen Sie die erste Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="10c01-105">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="10c01-106">Bevor Sie die Aufgaben in diesem Abschnitt ausführen, müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="10c01-106">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="10c01-107">Lync Server muss am zentralen Standort eingerichtet sein.</span><span class="sxs-lookup"><span data-stu-id="10c01-107">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="10c01-108">Ein Installationstechniker auf der Zweigstelle muss der RTCUniversalSBATechnicians-Gruppe hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="10c01-108">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="10c01-109">Darüber hinaus empfehlen wir, dass Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="10c01-109">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="10c01-110">Stellen Sie einen DHCP-Server an jeder Verzweigungs Website bereit, damit Clients IP-Adressen abrufen können.</span><span class="sxs-lookup"><span data-stu-id="10c01-110">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="10c01-111">Als Alternative zum Bereitstellen eines DHCP-Servers an jeder Verzweigungs Website aktivieren Sie lync Server DHCP auf der Survivable Branch-Appliance oder dem Überlebenden Verzweigungs Server mithilfe des Cmdlets "lync Server-Verwaltungsshell" <STRONG>-Cmdlet-CsRegistrarConfiguration – EnableDHCPServer $true</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="10c01-111">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="10c01-112">Ausführliche Informationen finden Sie im Abschnitt "Hardware-und Software Anforderungen" in der Planning-Dokumentation unter den Anforderungen an die <A href="lync-server-2013-branch-site-resiliency-requirements.md">Stabilität der Zweigstelle für lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="10c01-112">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="10c01-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="10c01-113">In This Section</span></span>

  - [<span data-ttu-id="10c01-114">Hinzufügen einer Survivable Branch Appliance zu Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10c01-114">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="10c01-115">Hinzufügen von Zweigstellenstandorten zur Topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10c01-115">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="10c01-116">Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10c01-116">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Bereitstellen von Survivable Branch Appliance-oder Server zentralen-Standortaufgaben
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
ms.openlocfilehash: e39b0d9e4d10f4e28afa2a01e02dc2fab4c842bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="6e472-102">Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013-zentralen Websiteaufgaben</span><span class="sxs-lookup"><span data-stu-id="6e472-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e472-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6e472-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6e472-104">Führen Sie die Aufgaben in diesem Abschnitt am zentralen Standort aus.</span><span class="sxs-lookup"><span data-stu-id="6e472-104">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="6e472-105">Wenn Sie ein Survivable Branch Server bereitstellen, überspringen Sie den ersten Vorgang.</span><span class="sxs-lookup"><span data-stu-id="6e472-105">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="6e472-106">Bevor Sie die Aufgaben in diesem Abschnitt ausführen, müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="6e472-106">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="6e472-107">Lync Server müssen am zentralen Standort eingerichtet sein.</span><span class="sxs-lookup"><span data-stu-id="6e472-107">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="6e472-108">Ein Installationstechniker am Zweigstellenstandort muss der Gruppe "Gruppe" rtcuniversalsbatechnicians "hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6e472-108">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="6e472-109">Darüber hinaus wird empfohlen, dass Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="6e472-109">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="6e472-110">Bereitstellen eines DHCP-Servers an jedem Zweigstellenstandort, um Clients das Abrufen von IP-Adressen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6e472-110">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="6e472-111">Als Alternative zur Bereitstellungeines DHCP-Servers an jedem Zweigstellenstandort aktivieren Sie lync Server DHCP auf dem Survivable Branch Appliance oder Survivable Branch Server mithilfe des lync Server-Verwaltungsshell Cmdlets " <STRONG>Gruppe-CsRegistrarConfiguration – EnableDHCPServer $true</STRONG>".</span><span class="sxs-lookup"><span data-stu-id="6e472-111">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="6e472-112">Ausführliche Informationen finden Sie im Abschnitt "Hardware-und Software Anforderungen" der Anforderungen an die <A href="lync-server-2013-branch-site-resiliency-requirements.md">Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6e472-112">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6e472-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6e472-113">In This Section</span></span>

  - [<span data-ttu-id="6e472-114">Hinzufügen eines Survivable Branch Appliance zu Active Directory in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e472-114">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="6e472-115">Hinzufügen von Zweigstellenstandorten zu Ihrer Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e472-115">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="6e472-116">Definieren einer Survivable Branch Appliance oder eines Servers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e472-116">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


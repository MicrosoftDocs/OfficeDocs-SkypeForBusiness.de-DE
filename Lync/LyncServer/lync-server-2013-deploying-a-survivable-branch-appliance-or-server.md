---
title: 'Lync Server 2013: Bereitstelleneiner Survivable Branch Appliance oder eines Servers'
description: 'Lync Server 2013: Bereitstelleneiner Survivable Branch Appliance oder eines Servers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c8610ab85b61d33a5f181f1d5f51d0e5095f49
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558591"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="a5eda-103">Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5eda-103">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5eda-104">_**Letztes Änderungsstand des Themas:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="a5eda-104">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="a5eda-105">Belastbare Enterprise-VoIP bezieht sich auf die Ausfallsicherheit von Zweigstellenstandorten, also auf die Möglichkeit, den Zweigstellenbenutzern kontinuierliche Enterprise-VoIP-Dienste bereitzustellen, falls der Link zum zentralen Standort nicht mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a5eda-105">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="a5eda-106">Für kleine und mittlere Zweigstellenstandorte (Zweigstellen mit 25 bis 1.000 Benutzern) wird die Bereitstellungeines Survivable Branch Appliance empfohlen, mit dem das Telefon Festnetz (Public Switched Telephone Network, PSTN) mithilfe des integrierten PSTN-Gateways oder eines SIP-Trunks an einen Telefonanbieter beendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5eda-106">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="a5eda-107">Ein Survivable Branch Appliance ist ein Gerät eines Drittanbieters, das einen Blade-Server mit dem Windows Server 2008 R2-Betriebssystem, lync Server 2013 Registrierungsstelle, Vermittlungsserver Software und einem PSTN-Gateway in einem einzigen Gerätegehäuse enthält.</span><span class="sxs-lookup"><span data-stu-id="a5eda-107">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="a5eda-108">Für Zweigstellen mit 1.000 bis 5.000-Benutzern und ohne ausfallsicheres WAN empfehlen wir eine Survivable Branch Server, die mit einem PSTN-Gateway oder einem SIP-Trunk an einen Telefonanbieter verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="a5eda-108">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="a5eda-109">Ein Survivable Branch Server ist ein Windows Server-basierter Computer, auf dem die Registrierungsstellen-und Vermittlungsserver Software installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a5eda-109">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5eda-110">Für Zweigstellenstandorte mit mehr als 5.000 Benutzern und dedizierten lync Server Administratoren wird eine vollständige lync Server 2013-Bereitstellung empfohlen, die sich von der des zentralen Standorts unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="a5eda-110">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="a5eda-111">Ausführliche Informationen zur Auswahl der besten ausfallsicherheitslösung für die Zweigstellenstandorte in Ihrer Organisation, einschließlich Voraussetzungen und Planungsüberlegungen, finden Sie unter Anforderungen an die <A href="lync-server-2013-branch-site-resiliency-requirements.md">Ausfallsicherheit an Zweigstellenstandorten für lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a5eda-111">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a5eda-112">Benutzer, die in einer lync Server Survivable Branch Appliance verwaltet werden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a5eda-112">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a5eda-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a5eda-113">In This Section</span></span>

  - [<span data-ttu-id="a5eda-114">Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013-zentralen Websiteaufgaben</span><span class="sxs-lookup"><span data-stu-id="a5eda-114">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="a5eda-115">Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013-Branch-Standort Aufgabe</span><span class="sxs-lookup"><span data-stu-id="a5eda-115">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="a5eda-116">Konfigurieren von Benutzern für Ausfallsicherheit für Zweigstellenstandorte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5eda-116">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="a5eda-117">Privatbenutzer auf einem Survivable Branch Appliance oder Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5eda-117">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="a5eda-118">Anhänge: Survivable Branch Appliances und Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5eda-118">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a5eda-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5eda-119">See Also</span></span>


[<span data-ttu-id="a5eda-120">Bereitstellen von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5eda-120">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


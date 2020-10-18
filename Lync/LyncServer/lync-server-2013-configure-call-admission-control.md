---
title: 'Lync Server 2013: Konfigurieren der Anrufsteuerung'
description: 'Lync Server 2013: Konfigurieren der Anrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c6da7e20f45e61f7364af3e8b749def05bd29fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575171"
---
# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="adda4-103">Konfigurieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adda4-103">Configure call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adda4-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="adda4-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="adda4-105">Anrufsteuerung (Call Admission Control, CAC) ist eine Lösung, die bestimmt, ob eine Echtzeitsitzung basierend auf der verfügbaren Bandbreite erstellt werden kann, um eine schlechte Audio-und Videoqualität für Benutzer in überlasteten Netzwerken zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="adda4-105">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="adda4-106">Die Anrufsteuerung steuert den echtzeitdatenverkehr nur für Audio und Video und wirkt sich nicht auf den Datenverkehr aus.</span><span class="sxs-lookup"><span data-stu-id="adda4-106">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="adda4-107">CAC kann den Anruf über einen Internet Pfad weiterleiten, wenn der standardmäßige WAN-Pfad nicht über die erforderliche Bandbreite verfügt.</span><span class="sxs-lookup"><span data-stu-id="adda4-107">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="adda4-108">Ausführliche Informationen finden Sie unter [Planning for Call Admission Control in lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="adda4-108">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="adda4-109">Dieser Abschnitt enthält eine Reihe von Beispielverfahren, die veranschaulichen, wie Sie die Anrufsteuerung in Ihrem Netzwerk bereitstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="adda4-109">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="adda4-110">Bevor Sie die Anrufsteuerung bereitstellen, müssen Sie alle erforderlichen Informationen für Ihre Unternehmensnetzwerk Topologie sammeln, wie unter <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Beispiel: Sammeln Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013</A> in der Planungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="adda4-110">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="adda4-111">Stellen Sie außerdem sicher, dass die Komponenten für die Anrufsteuerung installiert und aktiviert wurden, wie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and configure a Front-End-Pool or Standard Edition-Server in lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="adda4-111">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="adda4-112">Alle CAC-Bereitstellungs-und-Verwaltungsbeispiele in diesem Abschnitt werden mithilfe der lync Server-Verwaltungsshell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="adda4-112">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="adda4-113">Alternativ können Sie auch den Abschnitt <STRONG>Netzwerkkonfiguration</STRONG> von lync Server-Systemsteuerung verwenden, um die Anrufsteuerung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="adda4-113">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="adda4-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="adda4-114">In This Section</span></span>

  - [<span data-ttu-id="adda4-115">Konfigurieren von netzwerkregionen für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adda4-115">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="adda4-116">Erstellen von Bandbreitenrichtlinien Profilen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adda4-116">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="adda4-117">Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adda4-117">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="adda4-118">Zuordnen von Subnetzen zu Netzwerkstandorten für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adda4-118">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="adda4-119">Erstellen von Netzwerk Regions Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adda4-119">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="adda4-120">Erstellen von Netzwerk interregions-Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adda4-120">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="adda4-121">Erstellen von standortübergreifenden Netzwerkrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adda4-121">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="adda4-122">Aktivieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adda4-122">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="adda4-123">Prüfliste zur Bereitstellung der Anrufsteuerung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adda4-123">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


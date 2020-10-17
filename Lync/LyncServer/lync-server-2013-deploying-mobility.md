---
title: 'Lync Server 2013: Deploying Mobility'
description: 'Lync Server 2013: Deploying Mobility.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying mobility
ms:assetid: f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690055(v=OCS.15)
ms:contentKeyID: 48185805
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf927b950f8b94884fb91224a87e196fc815fca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545201"
---
# <a name="deploying-mobility-in-lync-server-2013"></a><span data-ttu-id="436c9-103">Bereitstellen von Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="436c9-103">Deploying mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="436c9-104">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="436c9-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="436c9-105">Wenn Sie das lync Server 2013 Mobilitätsfeature bereitstellen, können mobile Benutzer unterstützte mobile Geräte für lync-Funktionen wie Instant Messaging (Sofortnachrichten), Anwesenheit und Kontakte verwenden.</span><span class="sxs-lookup"><span data-stu-id="436c9-105">When you deploy the Lync Server 2013 mobility feature, mobile users can use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span>

<span data-ttu-id="436c9-106">Ausführliche Informationen zu den Anforderungen für die Bereitstellung des Mobilitätsfeatures finden Sie unter [Planning for Mobility in lync Server 2013](lync-server-2013-planning-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="436c9-106">For details about requirements for deploying the mobility feature, see [Planning for mobility in Lync Server 2013](lync-server-2013-planning-for-mobility.md).</span></span>

<span data-ttu-id="436c9-107">Dieser Abschnitt führt Sie durch die Schritte zum Bereitstellen und Überprüfen der Mobilitäts-und automatischen Ermittlungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="436c9-107">This section guides you through the steps for deploying and verifying the mobility and automatic discovery features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="436c9-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="436c9-108">In This Section</span></span>

  - [<span data-ttu-id="436c9-109">Erstellen von DNS-Einträgen für den AutoErmittlungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="436c9-109">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>](lync-server-2013-creating-dns-records-for-the-autodiscover-service.md)

  - [<span data-ttu-id="436c9-110">Ändern von Zertifikaten für Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="436c9-110">Modifying certificates for mobility in Lync Server 2013</span></span>](lync-server-2013-modifying-certificates-for-mobility.md)

  - [<span data-ttu-id="436c9-111">Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="436c9-111">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)

  - [<span data-ttu-id="436c9-112">Konfigurieren der AutoErmittlung in lync Server 2013 für Mobilität mit hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="436c9-112">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-mobility-with-hybrid-deployments.md)

  - [<span data-ttu-id="436c9-113">Überprüfen der Mobilitätsbereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="436c9-113">Verifying your mobility deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-mobility-deployment.md)

  - [<span data-ttu-id="436c9-114">Konfigurieren von Push-Benachrichtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="436c9-114">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)

  - [<span data-ttu-id="436c9-115">Konfigurieren von mobilitätsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="436c9-115">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


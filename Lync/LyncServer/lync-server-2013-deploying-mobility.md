---
title: 'Lync Server 2013: Deploying Mobility'
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
ms.openlocfilehash: f70b94d5a529a3fce46ac2b199e079f6be1e5bd0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mobility-in-lync-server-2013"></a><span data-ttu-id="1e4fd-102">Bereitstellen von Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e4fd-102">Deploying mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e4fd-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1e4fd-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1e4fd-104">Wenn Sie das lync Server 2013 Mobilitätsfeature bereitstellen, können mobile Benutzer unterstützte mobile Geräte für lync-Funktionen wie Instant Messaging (Sofortnachrichten), Anwesenheit und Kontakte verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e4fd-104">When you deploy the Lync Server 2013 mobility feature, mobile users can use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span>

<span data-ttu-id="1e4fd-105">Ausführliche Informationen zu den Anforderungen für die Bereitstellung des Mobilitätsfeatures finden Sie unter [Planning for Mobility in lync Server 2013](lync-server-2013-planning-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="1e4fd-105">For details about requirements for deploying the mobility feature, see [Planning for mobility in Lync Server 2013](lync-server-2013-planning-for-mobility.md).</span></span>

<span data-ttu-id="1e4fd-106">Dieser Abschnitt führt Sie durch die Schritte zum Bereitstellen und Überprüfen der Mobilitäts-und automatischen Ermittlungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="1e4fd-106">This section guides you through the steps for deploying and verifying the mobility and automatic discovery features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1e4fd-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1e4fd-107">In This Section</span></span>

  - [<span data-ttu-id="1e4fd-108">Erstellen von DNS-Einträgen für den AutoErmittlungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e4fd-108">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>](lync-server-2013-creating-dns-records-for-the-autodiscover-service.md)

  - [<span data-ttu-id="1e4fd-109">Ändern von Zertifikaten für Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e4fd-109">Modifying certificates for mobility in Lync Server 2013</span></span>](lync-server-2013-modifying-certificates-for-mobility.md)

  - [<span data-ttu-id="1e4fd-110">Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e4fd-110">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)

  - [<span data-ttu-id="1e4fd-111">Konfigurieren der AutoErmittlung in lync Server 2013 für Mobilität mit hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="1e4fd-111">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-mobility-with-hybrid-deployments.md)

  - [<span data-ttu-id="1e4fd-112">Überprüfen der Mobilitätsbereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e4fd-112">Verifying your mobility deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-mobility-deployment.md)

  - [<span data-ttu-id="1e4fd-113">Konfigurieren von Push-Benachrichtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e4fd-113">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)

  - [<span data-ttu-id="1e4fd-114">Konfigurieren von mobilitätsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e4fd-114">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


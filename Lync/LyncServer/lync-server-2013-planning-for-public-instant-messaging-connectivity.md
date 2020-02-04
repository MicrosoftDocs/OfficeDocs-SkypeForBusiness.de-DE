---
title: 'Lync Server 2013: Planen der öffentlichen Instant Messaging-Konnektivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7885d17e708f2073006131862f06d93d9057fb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="659a9-102">Planen der öffentlichen Instant Messaging-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="659a9-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="659a9-103">_**Letztes Änderungsdatum des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="659a9-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="659a9-104">Die öffentliche Instant Messaging-Konnektivität ist eine Klasse des Föderations-und ist so konfiguriert, dass Ihre internen und externen lync Server 2013-Benutzer Kontakte aus einem der folgenden hinzufügen können:</span><span class="sxs-lookup"><span data-stu-id="659a9-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="659a9-105">Messenger-Kontakte</span><span class="sxs-lookup"><span data-stu-id="659a9-105">Messenger contacts</span></span>

  - <span data-ttu-id="659a9-106">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="659a9-106">Yahoo\!</span></span> <span data-ttu-id="659a9-107">Kontakte</span><span class="sxs-lookup"><span data-stu-id="659a9-107">contacts</span></span>

  - <span data-ttu-id="659a9-108">America Online (AOL)-Kontakte</span><span class="sxs-lookup"><span data-stu-id="659a9-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="659a9-109">Ab dem 1. September, 2012, ist die Microsoft lync Public Chat-Benutzerabonnementlizenz (PIC USL) nicht mehr für den Kauf für neue oder erneuernde Vereinbarungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="659a9-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="659a9-110">Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden</span><span class="sxs-lookup"><span data-stu-id="659a9-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="659a9-111">Messenger bis zum Shutdown-Datum des Diensts.</span><span class="sxs-lookup"><span data-stu-id="659a9-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="659a9-112">Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="659a9-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="659a9-113">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="659a9-113">has been announced.</span></span> <span data-ttu-id="659a9-114">Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="659a9-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="659a9-115">Bei der PIC-USL handelt es sich um eine pro Benutzer/Monat-Abonnementlizenz, die für lync Server oder Office Communications Server für die Föderation mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="659a9-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="659a9-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="659a9-116">Messenger.</span></span> <span data-ttu-id="659a9-117">Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung nicht verlängert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="659a9-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="659a9-118">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="659a9-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="659a9-119">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="659a9-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="659a9-120">Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen über Chat und Sprache zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="659a9-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="659a9-121">Für diese Föderations Klasse sind die folgenden Planungsüberlegungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="659a9-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="659a9-122">Benutzer von Windows Live Messenger können neben Instant Messaging auch eine Peer-to-Peer-Audio/visuelle Kommunikation mit lync Server 2013-Benutzern führen.</span><span class="sxs-lookup"><span data-stu-id="659a9-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="659a9-123">Ihre Edgeserver müssen bestimmte Port-und Protokollanforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="659a9-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="659a9-124">Ausführliche Informationen finden Sie unter [ermitteln externer A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="659a9-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="659a9-125">Yahoo Instant Messaging hat keine eindeutigen Anforderungen, außer denen, die normalerweise bei der Planung und Bereitstellung des typischen Edgeserver verwendet werden, der Föderation bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="659a9-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="659a9-126">Für America Online ist es erforderlich, dass Ihr Edge-Server-Zertifikat, das dem Access-Edgedienst zugewiesen ist, über eine erweiterte Client-Schlüsselverwendung verfügt.</span><span class="sxs-lookup"><span data-stu-id="659a9-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="659a9-127">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="659a9-127">In This Section</span></span>

  - [<span data-ttu-id="659a9-128">Zertifikats Zusammenfassung – öffentliche Instant Messaging-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="659a9-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="659a9-129">Port Zusammenfassung – öffentliche Instant Messaging-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="659a9-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="659a9-130">[DNS-Zusammenfassung – öffentliche Instant Messaging-Konnektivität in lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="659a9-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


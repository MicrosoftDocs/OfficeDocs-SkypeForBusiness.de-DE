---
title: 'Lync Server 2013: Planen der Verbindung mit öffentlichen Instant Messaging-Diensten'
description: 'Lync Server 2013: Planen der Verbindung mit öffentlichen Instant Messaging-Diensten.'
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
ms.openlocfilehash: 9a020a291a39d78aea9271926c99b508a8cd9827
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549291"
---
# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="34d4f-103">Planen der Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34d4f-103">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34d4f-104">_**Letztes Änderungsstand des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="34d4f-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="34d4f-105">Die Verbindung mit öffentlichen Instant Messaging-Diensten ist eine Klasse von Verbund und wird so konfiguriert, dass Ihre internen und externen lync Server 2013-Benutzer Kontakte aus einem der folgenden Elemente hinzufügen können:</span><span class="sxs-lookup"><span data-stu-id="34d4f-105">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="34d4f-106">Messenger-Kontakte</span><span class="sxs-lookup"><span data-stu-id="34d4f-106">Messenger contacts</span></span>

  - <span data-ttu-id="34d4f-107">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="34d4f-107">Yahoo\!</span></span> <span data-ttu-id="34d4f-108">contacts</span><span class="sxs-lookup"><span data-stu-id="34d4f-108">contacts</span></span>

  - <span data-ttu-id="34d4f-109">America Online (AOL)-Kontakte</span><span class="sxs-lookup"><span data-stu-id="34d4f-109">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="34d4f-110">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity User Subscription License (PIC USL) nicht mehr für den Kauf für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="34d4f-110">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="34d4f-111">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="34d4f-111">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="34d4f-112">Messenger bis zum Datum der Beendigung des Diensts.</span><span class="sxs-lookup"><span data-stu-id="34d4f-112">Messenger until the service shutdown date.</span></span> <span data-ttu-id="34d4f-113">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="34d4f-113">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="34d4f-114">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="34d4f-114">has been announced.</span></span> <span data-ttu-id="34d4f-115">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="34d4f-115">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="34d4f-116">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server erforderlich ist, um mit Yahoo! zu verbünden.</span><span class="sxs-lookup"><span data-stu-id="34d4f-116">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="34d4f-117">Messenger.</span><span class="sxs-lookup"><span data-stu-id="34d4f-117">Messenger.</span></span> <span data-ttu-id="34d4f-118">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die nicht erneuert wird.</span><span class="sxs-lookup"><span data-stu-id="34d4f-118">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="34d4f-119">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="34d4f-119">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="34d4f-120">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34d4f-120">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="34d4f-121">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer über Chat und Voice Hunderte von Millionen von Benutzern erreichen können.</span><span class="sxs-lookup"><span data-stu-id="34d4f-121">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="34d4f-122">Für diese Partnerverbundklasse sind die folgenden Planungsüberlegungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="34d4f-122">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="34d4f-123">Windows Live Messenger-Benutzer können über Peer-to-Peer-Audio/visuelle Kommunikation mit lync Server 2013-Benutzern sowie Chatnachrichten verfügen.</span><span class="sxs-lookup"><span data-stu-id="34d4f-123">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="34d4f-124">Ihre Edgeserver müssen bestimmte Port-und Protokollanforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="34d4f-124">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="34d4f-125">Ausführliche Informationen finden Sie unter [bestimmen der externen A/V-Firewall und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34d4f-125">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="34d4f-126">Yahoo Instant Messaging hat keine eindeutigen Anforderungen, außer denen, die in der Regel für die Planung und Bereitstellung der typischen Edgeserver verwendet werden, die den Verbund bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="34d4f-126">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="34d4f-127">Für America Online ist es erforderlich, dass Ihr Edgeserver Zertifikat, das dem Zugriffs-Edgedienst zugewiesen ist, über eine verstärkte Schlüsselverwendung für Clients verfügt (EKU).</span><span class="sxs-lookup"><span data-stu-id="34d4f-127">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="34d4f-128">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="34d4f-128">In This Section</span></span>

  - [<span data-ttu-id="34d4f-129">Zertifikatzusammenfassung für die Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34d4f-129">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="34d4f-130">Port Zusammenfassung – Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34d4f-130">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="34d4f-131">[DNS-Zusammenfassung – Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="34d4f-131">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


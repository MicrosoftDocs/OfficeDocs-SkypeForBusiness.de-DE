---
title: 'Lync Server 2013: Unterstützung von Funktionen für öffentlichen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3e3207d1a7a12f4db379e4d58615cffdfb45036
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-instant-messaging-support-in-lync-server-2013"></a><span data-ttu-id="d780f-102">Unterstützung von Funktionen für öffentlichen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d780f-102">Public instant messaging support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d780f-103">_**Letztes Änderungsdatum des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="d780f-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="d780f-104">Lync Server 2013 unterstützt die Verwendung von lizenzierten öffentlichen Instant Messaging (im)-Verbindungs Anbietern sowie die Verwendung des Extensible Messaging and Presence Protocol (XMPP) zur Implementierung eines speziellen Föderations Typs, mit dem ein lync-Server auf das konfigurierte XMPP zugreifen kann. Domänen Partner mithilfe des lync 2013-Clients.</span><span class="sxs-lookup"><span data-stu-id="d780f-104">Lync Server 2013 supports the use of licensed public instant messaging (IM) connectivity providers, as well as the use of eXtensible Messaging and Presence Protocol (XMPP) to implement a special type of federation that enables a Lync Server to access configured XMPP domain partners by using the Lync 2013 client.</span></span>

<div>

## <a name="public-im-connectivity-provider-support"></a><span data-ttu-id="d780f-105">Unterstützung für öffentliche Chat-Konnektivitäts-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d780f-105">Public IM Connectivity Provider Support</span></span>

<span data-ttu-id="d780f-106">Die derzeit unterstützten öffentlichen Instant Messaging-Verbindungspartner sind:</span><span class="sxs-lookup"><span data-stu-id="d780f-106">The currently supported public instant messaging connectivity partners are:</span></span>

  - <span data-ttu-id="d780f-107">America Online</span><span class="sxs-lookup"><span data-stu-id="d780f-107">America Online</span></span>

  - <span data-ttu-id="d780f-108">Windows Live</span><span class="sxs-lookup"><span data-stu-id="d780f-108">Windows Live</span></span>

  - <span data-ttu-id="d780f-109">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="d780f-109">Yahoo\!</span></span>

<span data-ttu-id="d780f-110">Für die Kommunikation mit Windows Live-Benutzern unterstützt lync Server 2013 Peer-to-Peer-Chats sowie Audio-und Videoanrufe.</span><span class="sxs-lookup"><span data-stu-id="d780f-110">For communications with Windows Live users, Lync Server 2013 supports peer-to-peer IM and audio and video calls.</span></span> <span data-ttu-id="d780f-111">Für die Kommunikation mit AOL und\!Yahoo unterstützt lync Server 2013 Peer-to-Peer-Chats.</span><span class="sxs-lookup"><span data-stu-id="d780f-111">For communications with AOL and Yahoo\!, Lync Server 2013 supports peer-to-peer IM.</span></span> <span data-ttu-id="d780f-112">Möglicherweise ist eine separate Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d780f-112">A separate license may be required.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="d780f-113">Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d780f-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="d780f-114">Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden</span><span class="sxs-lookup"><span data-stu-id="d780f-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d780f-115">Messenger, bis der Dienst das Datum beendet hat.</span><span class="sxs-lookup"><span data-stu-id="d780f-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="d780f-116">Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="d780f-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="d780f-117">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="d780f-117">has been announced.</span></span> <span data-ttu-id="d780f-118">Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d780f-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="d780f-119">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d780f-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="d780f-120">Messenger.</span><span class="sxs-lookup"><span data-stu-id="d780f-120">Messenger.</span></span> <span data-ttu-id="d780f-121">Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</span><span class="sxs-lookup"><span data-stu-id="d780f-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="d780f-122">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="d780f-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d780f-123">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d780f-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="d780f-124">Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="d780f-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a><span data-ttu-id="d780f-125">Unterstützung für XMPP-Föderation</span><span class="sxs-lookup"><span data-stu-id="d780f-125">XMPP Federation Support</span></span>

<span data-ttu-id="d780f-126">Die XMPP-Föderation unterstützt die Kommunikation von lync-Benutzern mit konfigurierten XMPP-Domänenbenutzern, die einen öffentlichen Anbieter wie GTalk verwenden.</span><span class="sxs-lookup"><span data-stu-id="d780f-126">XMPP federation supports Lync users communication with configured XMPP domain users who use a public provider, such as GTalk.</span></span> <span data-ttu-id="d780f-127">Die Kommunikation mit diesen Benutzern kann Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="d780f-127">Communications with these users can include the following:</span></span>

  - <span data-ttu-id="d780f-128">Peer-zu-Peer-Chat und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="d780f-128">Peer-to-peer IM and presence</span></span>

  - <span data-ttu-id="d780f-129">Erstellen von XMPP-verbundkontakten im lync-Client</span><span class="sxs-lookup"><span data-stu-id="d780f-129">Creation of XMPP federated contacts in the Lync client</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Unterstützung für öffentliche Chatnachrichten'
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
ms.openlocfilehash: 026ceb24ef3e046d6d800db4ba82381c8905b99d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512402"
---
# <a name="public-instant-messaging-support-in-lync-server-2013"></a><span data-ttu-id="b6f19-102">Unterstützung für öffentliche Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6f19-102">Public instant messaging support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6f19-103">_**Letztes Änderungsstand des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="b6f19-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="b6f19-104">Lync Server 2013 unterstützt die Verwendung von lizenzierten öffentlichen Instant Messaging-Verbindungs Anbietern sowie die Verwendung von "XMPP" (Extensible Messaging and Presence Protocol) zur Implementierung eines speziellen Verbund Typs, der einem lync Server ermöglicht, über den lync 2013-Client auf konfigurierte XMPP-Domänen Partner zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b6f19-104">Lync Server 2013 supports the use of licensed public instant messaging (IM) connectivity providers, as well as the use of eXtensible Messaging and Presence Protocol (XMPP) to implement a special type of federation that enables a Lync Server to access configured XMPP domain partners by using the Lync 2013 client.</span></span>

<div>

## <a name="public-im-connectivity-provider-support"></a><span data-ttu-id="b6f19-105">Unterstützung öffentlicher Instant_Messaging-Dienste</span><span class="sxs-lookup"><span data-stu-id="b6f19-105">Public IM Connectivity Provider Support</span></span>

<span data-ttu-id="b6f19-106">Derzeit unterstützte Partner für Verbindungen mit öffentlichen Instant Messaging-Diensten:</span><span class="sxs-lookup"><span data-stu-id="b6f19-106">The currently supported public instant messaging connectivity partners are:</span></span>

  - <span data-ttu-id="b6f19-107">America Online</span><span class="sxs-lookup"><span data-stu-id="b6f19-107">America Online</span></span>

  - <span data-ttu-id="b6f19-108">Windows Live</span><span class="sxs-lookup"><span data-stu-id="b6f19-108">Windows Live</span></span>

  - <span data-ttu-id="b6f19-109">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="b6f19-109">Yahoo\!</span></span>

<span data-ttu-id="b6f19-110">Für die Kommunikation mit Windows Live-Benutzern unterstützt lync Server 2013 Peer-zu-Peer-Chat-und Audio-und Videoanrufe.</span><span class="sxs-lookup"><span data-stu-id="b6f19-110">For communications with Windows Live users, Lync Server 2013 supports peer-to-peer IM and audio and video calls.</span></span> <span data-ttu-id="b6f19-111">Für die Kommunikation mit AOL und Yahoo \! unterstützt lync Server 2013 Peer-to-Peer-Chat.</span><span class="sxs-lookup"><span data-stu-id="b6f19-111">For communications with AOL and Yahoo\!, Lync Server 2013 supports peer-to-peer IM.</span></span> <span data-ttu-id="b6f19-112">Möglicherweise ist eine separate Lizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b6f19-112">A separate license may be required.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="b6f19-113">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b6f19-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="b6f19-114">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b6f19-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="b6f19-115">Messenger, bis der Dienst das Datum heruntergefahren hat.</span><span class="sxs-lookup"><span data-stu-id="b6f19-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="b6f19-116">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="b6f19-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="b6f19-117">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="b6f19-117">has been announced.</span></span> <span data-ttu-id="b6f19-118">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b6f19-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="b6f19-119">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b6f19-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="b6f19-120">Messenger.</span><span class="sxs-lookup"><span data-stu-id="b6f19-120">Messenger.</span></span> <span data-ttu-id="b6f19-121">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="b6f19-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="b6f19-122">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="b6f19-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="b6f19-123">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b6f19-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="b6f19-124">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="b6f19-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a><span data-ttu-id="b6f19-125">Unterstützung des XMPP-Verbunds</span><span class="sxs-lookup"><span data-stu-id="b6f19-125">XMPP Federation Support</span></span>

<span data-ttu-id="b6f19-p105">Der XMPP-Verbund unterstützt die Kommunikation von Lync-Benutzern mit konfigurierten XMPP-Domänenbenutzern, die einen öffentlichen Anbieter wie GTalk nutzen. Die Kommunikation mit diesen Benutzern kann Folgendes beinhalten:</span><span class="sxs-lookup"><span data-stu-id="b6f19-p105">XMPP federation supports Lync users communication with configured XMPP domain users who use a public provider, such as GTalk. Communications with these users can include the following:</span></span>

  - <span data-ttu-id="b6f19-128">Peer-zu-Peer-Sofortnachrichten und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="b6f19-128">Peer-to-peer IM and presence</span></span>

  - <span data-ttu-id="b6f19-129">Erstellung von XMPP-Verbundkontakten auf dem Lync-Client</span><span class="sxs-lookup"><span data-stu-id="b6f19-129">Creation of XMPP federated contacts in the Lync client</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


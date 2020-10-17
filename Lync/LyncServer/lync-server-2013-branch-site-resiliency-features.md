---
title: 'Lync Server 2013: Features für Ausfallsicherheit für Zweigstellenstandorte'
description: 'Lync Server 2013: Features für Ausfallsicherheit für Zweigstellenstandorte.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a498751ce99d0e8e85d6cbe53915c864e64440bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552201"
---
# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="c9264-103">Ausfallsicherheit für Zweigstellenstandorte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9264-103">Branch-site resiliency features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9264-104">_**Letztes Änderungsstand des Themas:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="c9264-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="c9264-105">Wenn Sie Ausfallsicherheit für Zweigstellenstandorte bereitstellen, sollten die folgenden VoIP-Funktionen weiterhin verfügbar sein, wenn die WAN-Leitung zwischen einem Zweigstellenstandort und einem zentralen Standort ausfällt oder der zentrale Standort nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c9264-105">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="c9264-106">Eingehende und ausgehende PSTN-Anrufe (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="c9264-106">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="c9264-107">Enterprise-Anrufe zwischen Benutzern, die sich entweder am selben oder an zwei verschiedenen Standorten befinden</span><span class="sxs-lookup"><span data-stu-id="c9264-107">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="c9264-108">Grundlegende Anrufbehandlung, einschließlich Halten, Wiederaufnahme und Übergabe</span><span class="sxs-lookup"><span data-stu-id="c9264-108">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="c9264-109">Instant Messaging mit zwei Teilnehmern</span><span class="sxs-lookup"><span data-stu-id="c9264-109">Two-party instant messaging</span></span>

  - <span data-ttu-id="c9264-110">Anrufweiterleitung, gleichzeitiges Klingeln von Endgeräten, Anrufdelegierung und Teamanrufdienste – jedoch nur, wenn beide Teilnehmer für die Anrufdelegierung (z. B. ein Manager und der Administrator des Managers) oder alle Teammitglieder am selben Standort konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="c9264-110">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="c9264-111">Kommunikationsdatensätze (KDS)</span><span class="sxs-lookup"><span data-stu-id="c9264-111">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="c9264-112">PSTN-Einwahlkonferenzen mit automatischer Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="c9264-112">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="c9264-113">Voicemailfunktionen, sofern Sie Einstellungen für die Voicemailumleitung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c9264-113">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="c9264-114">(Ausführliche Informationen finden Sie unter Anforderungen an die [Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span><span class="sxs-lookup"><span data-stu-id="c9264-114">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="c9264-115">Benutzerauthentifizierung und -autorisierung</span><span class="sxs-lookup"><span data-stu-id="c9264-115">User authentication and authorization</span></span>

<span data-ttu-id="c9264-116">Die folgenden Funktionen stehen nur zur Verfügung, wenn es sich bei ihrer ausfallsicherheitslösung um eine umfassende lync Server-Bereitstellung am Zweigstellenstandort handelt:</span><span class="sxs-lookup"><span data-stu-id="c9264-116">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="c9264-117">IM-, Web- und A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="c9264-117">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="c9264-118">Anwesenheits- und DND-basiertes Routing (Telefon soll bei eingehenden Anrufen an Ihre Durchwahlnummern mit dem Status "Nicht stören" nicht klingen)</span><span class="sxs-lookup"><span data-stu-id="c9264-118">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="c9264-119">Aktualisieren der Einstellungen für die Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="c9264-119">Updating call forwarding settings</span></span>

  - <span data-ttu-id="c9264-120">Reaktionsgruppenanwendung und Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="c9264-120">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="c9264-121">Die Einrichtung neuer Telefone und Clients, jedoch nur, wenn Active Directory-Domänendienste am Zweigstellenstandort vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c9264-121">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="c9264-122">9-1-1 (erweitert) (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="c9264-122">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="c9264-123">Wenn E9-1-1 bereitgestellt wird und der SIP-Trunk am zentralen Standort nicht zur Verfügung steht, weil die WAN-Verbindung nicht verfügbar ist, leitet der Survivable Branch Appliance E9-1 -1-Anrufe an das lokale Zweigstellen Gateway weiter.</span><span class="sxs-lookup"><span data-stu-id="c9264-123">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="c9264-124">Zum Aktivieren dieser Funktion muss die Weiterleitung von Anrufen an das lokale Gateway bei einem WAN-Ausfall in den VoIP-Richtlinien der Zweigstellenbenutzer festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c9264-124">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9264-125">SBA (Survivable Branch Office) wird für XMPP nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c9264-125">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="c9264-126">Benutzer, die in einer SBA-Konfiguration verwaltet werden, können IMS nicht senden oder Anwesenheitsinformationen mit XMPP-Kontakten sehen.</span><span class="sxs-lookup"><span data-stu-id="c9264-126">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


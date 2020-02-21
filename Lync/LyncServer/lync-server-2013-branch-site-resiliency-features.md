---
title: 'Lync Server 2013: Features für Ausfallsicherheit für Zweigstellenstandorte'
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
ms.openlocfilehash: aa8e54578ba2e81f7e2e847994e92e13bb8010ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="bd343-102">Ausfallsicherheit für Zweigstellenstandorte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd343-102">Branch-site resiliency features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd343-103">_**Letztes Änderungsstand des Themas:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="bd343-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="bd343-104">Wenn Sie Ausfallsicherheit für Zweigstellenstandorte bereitstellen, sollten die folgenden VoIP-Funktionen weiterhin verfügbar sein, wenn die WAN-Leitung zwischen einem Zweigstellenstandort und einem zentralen Standort ausfällt oder der zentrale Standort nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bd343-104">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="bd343-105">Eingehende und ausgehende PSTN-Anrufe (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="bd343-105">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="bd343-106">Enterprise-Anrufe zwischen Benutzern, die sich entweder am selben oder an zwei verschiedenen Standorten befinden</span><span class="sxs-lookup"><span data-stu-id="bd343-106">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="bd343-107">Grundlegende Anrufbehandlung, einschließlich Halten, Wiederaufnahme und Übergabe</span><span class="sxs-lookup"><span data-stu-id="bd343-107">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="bd343-108">Instant Messaging mit zwei Teilnehmern</span><span class="sxs-lookup"><span data-stu-id="bd343-108">Two-party instant messaging</span></span>

  - <span data-ttu-id="bd343-109">Anrufweiterleitung, gleichzeitiges Klingeln von Endgeräten, Anrufdelegierung und Teamanrufdienste – jedoch nur, wenn beide Teilnehmer für die Anrufdelegierung (z. B. ein Manager und der Administrator des Managers) oder alle Teammitglieder am selben Standort konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="bd343-109">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="bd343-110">Kommunikationsdatensätze (KDS)</span><span class="sxs-lookup"><span data-stu-id="bd343-110">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="bd343-111">PSTN-Einwahlkonferenzen mit automatischer Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="bd343-111">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="bd343-112">Voicemailfunktionen, sofern Sie Einstellungen für die Voicemailumleitung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bd343-112">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="bd343-113">(Ausführliche Informationen finden Sie unter Anforderungen an die [Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span><span class="sxs-lookup"><span data-stu-id="bd343-113">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="bd343-114">Benutzerauthentifizierung und -autorisierung</span><span class="sxs-lookup"><span data-stu-id="bd343-114">User authentication and authorization</span></span>

<span data-ttu-id="bd343-115">Die folgenden Funktionen stehen nur zur Verfügung, wenn es sich bei ihrer ausfallsicherheitslösung um eine umfassende lync Server-Bereitstellung am Zweigstellenstandort handelt:</span><span class="sxs-lookup"><span data-stu-id="bd343-115">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="bd343-116">IM-, Web- und A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="bd343-116">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="bd343-117">Anwesenheits- und DND-basiertes Routing (Telefon soll bei eingehenden Anrufen an Ihre Durchwahlnummern mit dem Status "Nicht stören" nicht klingen)</span><span class="sxs-lookup"><span data-stu-id="bd343-117">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="bd343-118">Aktualisieren der Einstellungen für die Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="bd343-118">Updating call forwarding settings</span></span>

  - <span data-ttu-id="bd343-119">Reaktionsgruppenanwendung und Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="bd343-119">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="bd343-120">Die Einrichtung neuer Telefone und Clients, jedoch nur, wenn Active Directory-Domänendienste am Zweigstellenstandort vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bd343-120">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="bd343-121">9-1-1 (erweitert) (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="bd343-121">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="bd343-122">Wenn E9-1-1 bereitgestellt wird und der SIP-Trunk am zentralen Standort nicht zur Verfügung steht, weil die WAN-Verbindung nicht verfügbar ist, leitet der Survivable Branch Appliance E9-1 -1-Anrufe an das lokale Zweigstellen Gateway weiter.</span><span class="sxs-lookup"><span data-stu-id="bd343-122">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="bd343-123">Zum Aktivieren dieser Funktion muss die Weiterleitung von Anrufen an das lokale Gateway bei einem WAN-Ausfall in den VoIP-Richtlinien der Zweigstellenbenutzer festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bd343-123">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd343-124">SBA (Survivable Branch Office) wird für XMPP nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bd343-124">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="bd343-125">Benutzer, die in einer SBA-Konfiguration verwaltet werden, können IMS nicht senden oder Anwesenheitsinformationen mit XMPP-Kontakten sehen.</span><span class="sxs-lookup"><span data-stu-id="bd343-125">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


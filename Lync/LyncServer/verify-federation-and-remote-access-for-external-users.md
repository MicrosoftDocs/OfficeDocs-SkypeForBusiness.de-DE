---
title: Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer
description: Überprüfen Sie den Partnerverbund und den Remotezugriff für externe Benutzer.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ac36f2e1b6c5ddfd889810ba2a3ab4d82b7ae33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555071"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="2e007-103">Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="2e007-103">Verify federation and remote access for external users</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e007-104">_**Letztes Änderungsstand des Themas:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="2e007-104">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="2e007-105">Nachdem Sie die partnerverbundroute zum lync Server 2013 Edgeserver gewechselt haben, sollten Sie einige Funktionstests durchführen, um zu überprüfen, ob der Verbund wie erwartet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2e007-105">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="2e007-106">Tests für den Zugriff durch externe Benutzer sollten alle Typen von externen Benutzern enthalten, die von Ihrer Organisation unterstützt werden, einschließlich einer oder aller der folgenden.</span><span class="sxs-lookup"><span data-stu-id="2e007-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="2e007-107">Testen der Konnektivität externer Benutzer und des externen Zugriffs</span><span class="sxs-lookup"><span data-stu-id="2e007-107">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="2e007-108">Benutzer aus mindestens einer Verbunddomäne, einem internen Benutzer auf lync Server 2013 und einem Benutzer in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2e007-108">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="2e007-109">Testen von Chatnachrichten, Anwesenheit, Audio/Video (A/V) und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="2e007-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="2e007-110">Benutzer aller öffentlichen Sofortnachrichten-Dienstanbieter, die von Ihrer Organisation unterstützt werden (und für die die Bereitstellung abgeschlossen ist), die mit einem Benutzer auf lync Server 2013 und einem Benutzer in lync Server 2010 kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="2e007-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="2e007-111">Stellen Sie sicher, dass anonyme Benutzer in der Lage sind, an Konferenzen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="2e007-111">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="2e007-112">Ein Benutzer, der auf lync Server 2010 unter Verwendung des Remotebenutzerzugriffs (Anmeldung bei lync Server 2010 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in lync Server 2013 und einem Benutzer auf lync Server 2010 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="2e007-112">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="2e007-113">Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="2e007-113">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="2e007-114">Ein Benutzer, der auf lync Server 2013 unter Verwendung des Remotebenutzerzugriffs (Anmeldung bei lync Server 2013 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in lync Server 2013 und einem Benutzer auf lync Server 2010 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="2e007-114">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="2e007-115">Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="2e007-115">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33eb8fddaef96da047a6e87f1961b2fbea73c29d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="9c696-102">Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="9c696-102">Verify federation and remote access for external users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c696-103">_**Letztes Änderungsdatum des Themas:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="9c696-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="9c696-104">Nach dem Übergang der Föderations Route zum lync Server 2013-Edgeserver sollten Sie einige Funktionstests durchführen, um zu überprüfen, ob der Verbund wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9c696-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="9c696-105">Tests für den Zugriff durch externe Benutzer sollten alle externen Benutzertypen enthalten, die von Ihrer Organisation unterstützt werden, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="9c696-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="9c696-106">Testen der Konnektivität externer Benutzer und des externen Zugriffs</span><span class="sxs-lookup"><span data-stu-id="9c696-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="9c696-107">Benutzer aus mindestens einer Verbunddomäne, einem internen Benutzer in lync Server 2013 und einem Benutzer in lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9c696-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="9c696-108">Testen Sie Instant Messaging (im), Anwesenheitsinformationen, Audio/Video (A/V) und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="9c696-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="9c696-109">Benutzer jedes öffentlichen Chat Dienstanbieters, die von Ihrer Organisation unterstützt werden (und für die Bereitstellung abgeschlossen wurde), die mit einem Benutzer in lync Server 2013 und einem Benutzer in lync Server 2010 kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="9c696-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="9c696-110">Überprüfen Sie, ob anonyme Benutzer an Konferenzen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="9c696-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="9c696-111">Ein Benutzer, der auf lync Server 2010 mithilfe des Remotebenutzerzugriffs (Anmeldung bei lync Server 2010 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in lync Server 2013 und einem Benutzer in lync Server 2010 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="9c696-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="9c696-112">Testen Sie Chat, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="9c696-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="9c696-113">Ein Benutzer, der auf lync Server 2013 mithilfe des Remotebenutzerzugriffs (Anmeldung bei lync Server 2013 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in lync Server 2013 und einem Benutzer in lync Server 2010 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="9c696-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="9c696-114">Testen Sie Chat, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="9c696-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


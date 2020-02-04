---
title: Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3a87063503d373c8ef318633c5113624fef00b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a><span data-ttu-id="fb121-102">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb121-102">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb121-103">_**Letztes Änderungsdatum des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="fb121-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="fb121-p101">VoIP-Richtlinien, PSTN-Verwendungsdatensätze und VoIP-Routen stehen in enger Beziehung zueinander. Zur Konfiguration von VoIP-Richtlinien wird eine Reihe von Anruffunktionen ausgewählt. Anschließend wird die Richtlinie einem Satz von PSTN-Verwendungsdatensätzen zugewiesen, in denen die Rechte für die Benutzer oder Gruppen festgelegt sind, denen die VoIP-Richtlinie zugewiesen wird. Auch VoIP-Routen werden PSTN-Verwendungsdatensätze zugewiesen, um Routen und die für ihre Verwendung autorisierten Benutzer einander zuzuordnen. Benutzer können also nur Anrufe über Routen tätigen, für die sie passende PSTN-Verwendungsdatensätze besitzen.</span><span class="sxs-lookup"><span data-stu-id="fb121-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>

<span data-ttu-id="fb121-108">Der empfohlene Workflow für eine neue Enterprise-VoIP-Bereitstellung besteht darin, zunächst eine VoIP-Richtlinie mit den geeigneten PSTN-Verwendungsdatensätzen zu konfigurieren und anschließend den einzelnen PSTN-Verwendungsdatensätzen die entsprechenden Routen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="fb121-108">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fb121-109">Außerdem können Sie VoIP-Richtlinien auf <EM>Benutzerebene</EM> erstellen und sie einzelnen Benutzern oder Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fb121-109">You can also create voice policies with <EM>user</EM> scope and assign them to individual users or groups.</span></span>



</div>

<span data-ttu-id="fb121-110">Die einzelnen Schritte zur Durchführung dieser Aufgaben finden Sie in den Verfahren in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="fb121-110">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fb121-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fb121-111">In This Section</span></span>

  - [<span data-ttu-id="fb121-112">Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und -berechtigungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb121-112">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [<span data-ttu-id="fb121-113">Anzeigen von PSTN-Nutzungsdaten Sätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb121-113">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)

  - [<span data-ttu-id="fb121-114">Konfigurieren von VoIP-Routen für ausgehende Anrufe in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb121-114">Configuring voice routes for outbound calls in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [<span data-ttu-id="fb121-115">Exportieren und Importieren einer VoIP-Routingkonfiguration in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb121-115">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [<span data-ttu-id="fb121-116">Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb121-116">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [<span data-ttu-id="fb121-117">Testen des VoIP-Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb121-117">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


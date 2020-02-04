---
title: 'Lync Server 2013: Einrichten von Benutzerrichtlinien für die Archivierung in lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa8f377c2a78275419c7d4906a51a9550864b8ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="c8bb9-102">Einrichten von Benutzerrichtlinien für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8bb9-102">Setting up user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8bb9-103">_**Letztes Änderungsdatum des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="c8bb9-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="c8bb9-104">Das Aktivieren oder Deaktivieren der Archivierung für bestimmte Benutzer, die in lync Server 2013 verwaltet werden, erfordert das Erstellen und Konfigurieren einer oder mehrerer Benutzerrichtlinien und das anschließende Anwenden der entsprechenden Richtlinie auf bestimmte Benutzer oder Benutzergruppen.</span><span class="sxs-lookup"><span data-stu-id="c8bb9-104">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="c8bb9-105">Benutzerrichtlinien setzen Website-und globale Richtlinien außer Kraft, allerdings nur für Benutzer, die in lync Server 2013 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="c8bb9-105">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="c8bb9-106">Benutzer sind immer in lync Server beheimatet.</span><span class="sxs-lookup"><span data-stu-id="c8bb9-106">Users are always homed in Lync Server.</span></span> <span data-ttu-id="c8bb9-107">Wenn die Microsoft Exchange-Integration aktiviert ist, müssen Benutzer, deren Postfächer in Microsoft Exchange Server 2013 enthalten sind, ihre Archivierungsrichtlinien nicht in lync Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="c8bb9-107">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="c8bb9-108">Diese Benutzer mit Archivierung werden von Exchange in-situ-Speicher verwaltet.</span><span class="sxs-lookup"><span data-stu-id="c8bb9-108">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="c8bb9-109">Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für Global-, Website-und Benutzerrichtlinien, finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c8bb9-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8bb9-110">Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-in-situ-Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="c8bb9-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="c8bb9-111">Die Archivierung für diese Benutzer setzt voraus, dass ihre Postfächer an einem in-situ-Speicher abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c8bb9-111">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="c8bb9-112">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c8bb9-112">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="c8bb9-113">Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8bb9-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="c8bb9-114">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Konfigurieren von Archivierungsoptionen in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c8bb9-114">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c8bb9-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c8bb9-115">In This Section</span></span>

  - [<span data-ttu-id="c8bb9-116">Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8bb9-116">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="c8bb9-117">Anwenden einer lync Server-Archivierungsrichtlinie auf einen Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8bb9-117">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Verwalten der Archivierung von interner und externer Kommunikation
description: Verwalten der Archivierung der internen und externen Kommunikation.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 857e4772d93ead01c3914b2ee04b71bddb1feed4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564131"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="91354-103">Verwalten der Archivierung von interner und externer Kommunikation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91354-103">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91354-104">_**Letztes Änderungsstand des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="91354-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="91354-105">In lync Server 2013 verwenden Sie Archivierungsrichtlinien, um die Archivierung für die interne Kommunikation und die externe Kommunikation zu aktivieren und zu deaktivieren, wenn Sie Microsoft Exchange Integration nicht verwenden oder wenn Sie über Benutzer verfügen, die nicht in Exchange 2013 mit ihren Postfächern in In-Place Aufbewahrung abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="91354-105">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="91354-106">Dies umfasst die folgenden Archivierungsrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="91354-106">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="91354-107">Eine globale Richtlinie, die bei der Bereitstellung von lync Server 2013 standardmäßig erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="91354-107">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="91354-108">Optionale Richtlinien auf Standort- und Benutzerebene, die Sie erstellen und verwenden können, um festzulegen, wie die Archivierung für bestimmte Standorte oder Benutzer umgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="91354-108">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="91354-109">Sie richten die Archivierungsrichtlinien zunächst bei der Bereitstellung der Archivierung ein, können diese aber nach der Bereitstellung ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="91354-109">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="91354-110">In lync Server 2013 Systemsteuerung können Sie auf der Seite **Archivierungsrichtlinie** der Gruppe **Archivierung und Überwachung** Richtlinien auf globaler Ebene, auf Standortebene und auf Benutzerebene verwalten.</span><span class="sxs-lookup"><span data-stu-id="91354-110">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="91354-111">Wenn Sie Ihren lync Server Speicher in Exchange 2013 Speicher integrieren, haben die Exchange-Benutzerrichtlinien Vorrang vor den lync Server 2013 Archivierungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="91354-111">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="91354-112">Ausführliche Informationen zur Implementierung von Richtlinien, einschließlich der Hierarchie der Richtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="91354-112">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="91354-113">Zur Steuerung der Archivierungsimplementierung müssen Sie Optionen in den Archivierungskonfigurationen auswählen, beispielsweise um festzulegen, ob Sofortnachrichten oder Konferenzinhalte archiviert werden, wie der kritische Modus verwendet wird, sowie Löschoptionen.</span><span class="sxs-lookup"><span data-stu-id="91354-113">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="91354-114">Standardmäßig sind in der globalen Archivierungskonfiguration oder in Standortarchivierungs- oder Poolarchivierungskonfigurationen keine Optionen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="91354-114">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="91354-115">Sie sollten alle geeigneten Optionen in den Archivierungskonfigurationen festlegen, bevor Sie die Archivierung für die interne oder externe Kommunikation in den Archivierungsrichtlinien aktivieren.</span><span class="sxs-lookup"><span data-stu-id="91354-115">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="91354-116">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration options in lync Server 2013 für Ihre Organisation, Standorte und Pools</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="91354-116">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="91354-117">Wenn Sie Microsoft Exchange Integration für Ihre Bereitstellung aktivieren, Steuern Exchange-Richtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden, und lassen ihre Postfächer In-Place halten.</span><span class="sxs-lookup"><span data-stu-id="91354-117">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="91354-118">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung Exchange Server Integration</A> in die Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="91354-118">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="91354-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="91354-119">In This Section</span></span>

  - [<span data-ttu-id="91354-120">Erstellen einer Archivierungsrichtlinie in lync Server 2013 zum Aktivieren oder Deaktivieren der Archivierung interner oder externer Kommunikation für bestimmte Websites oder Benutzer</span><span class="sxs-lookup"><span data-stu-id="91354-120">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)

  - [<span data-ttu-id="91354-121">Ändern einer Archivierungsrichtlinie in lync Server 2013 zum Aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation für Ihre Organisation, Websites oder Benutzer</span><span class="sxs-lookup"><span data-stu-id="91354-121">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [<span data-ttu-id="91354-122">Anwenden einer Archivierungsrichtlinie auf Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91354-122">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="91354-123">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server Integration</span><span class="sxs-lookup"><span data-stu-id="91354-123">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="91354-124">Löschen einer Archivierungsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91354-124">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


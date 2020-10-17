---
title: 'Lync Server 2013: Konfigurieren und Zuweisen von Archivierungsrichtlinien'
description: 'Lync Server 2013: Konfigurieren und Zuweisen von Archivierungsrichtlinien.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebe08715433e04e56758c7fb09b331065fbd6f44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570911"
---
# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="e7e27-103">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7e27-103">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7e27-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e7e27-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e7e27-105">In lync Server 2013 verwenden Sie Richtlinien, um die Archivierung für die interne Kommunikation und die externe Kommunikation für Benutzer zu aktivieren und zu deaktivieren, die in lync Server 2013 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="e7e27-105">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="e7e27-106">Dies umfasst die folgenden Archivierungsrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="e7e27-106">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="e7e27-107">Eine globale Richtlinie, die bei der Bereitstellung von lync Server 2013 standardmäßig erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e7e27-107">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="e7e27-108">Optionale Richtlinien auf Standort- und Benutzerebene, die Sie erstellen und verwenden können, um festzulegen, wie die Archivierung für bestimmte Standorte oder Benutzer umgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="e7e27-108">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="e7e27-109">Sie richten die Archivierungsrichtlinien zunächst bei der Bereitstellung der Archivierung ein, können diese aber nach der Bereitstellung ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="e7e27-109">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="e7e27-110">In lync Server 2013 Systemsteuerung können Sie auf der Seite **Archivierungsrichtlinie** der Gruppe **Archivierung und Überwachung** Richtlinien auf globaler Ebene, auf Standortebene und auf Benutzerebene verwalten.</span><span class="sxs-lookup"><span data-stu-id="e7e27-110">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7e27-111">Zur Steuerung der Archivierungsimplementierung müssen Sie Optionen in den Archivierungskonfigurationen auswählen, beispielsweise um festzulegen, ob Sofortnachrichten oder Konferenzinhalte archiviert werden, wie der kritische Modus verwendet wird, sowie Löschoptionen.</span><span class="sxs-lookup"><span data-stu-id="e7e27-111">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="e7e27-112">Standardmäßig sind in der globalen Archivierungskonfiguration oder in Standortarchivierungs- oder Poolarchivierungskonfigurationen keine Optionen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e7e27-112">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="e7e27-113">Sie sollten alle geeigneten Optionen in den Archivierungskonfigurationen festlegen, bevor Sie die Archivierung für die interne oder externe Kommunikation in den Archivierungsrichtlinien aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e7e27-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="e7e27-114">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration options in lync Server 2013 für Ihre Organisation, Standorte und Pools</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e7e27-114">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="e7e27-115">Wenn Sie Ihren lync Server Speicher in Exchange 2013 Speicher integrieren, haben die Exchange-Benutzerrichtlinien Vorrang vor den lync Server 2013 Archivierungsrichtlinien, jedoch nur für die Benutzer, die in Exchange 2013 verwaltet werden, deren Postfächer In-Place Aufbewahrungsverfahren abgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="e7e27-115">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="e7e27-116">Ausführliche Informationen zur Implementierung von Richtlinien, einschließlich der Hierarchie der Richtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e7e27-116">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="e7e27-117">Ausführliche Informationen zum Verwalten von Richtlinien nach der Bereitstellung finden Sie unter [Managing the Archiving of Internal and External Communications in lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e7e27-117">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e7e27-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e7e27-118">In This Section</span></span>

  - [<span data-ttu-id="e7e27-119">Konfigurieren der globalen Richtlinie für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7e27-119">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="e7e27-120">Einrichten von Standortrichtlinien für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7e27-120">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="e7e27-121">Einrichten von Archivierungsrichtlinien für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7e27-121">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


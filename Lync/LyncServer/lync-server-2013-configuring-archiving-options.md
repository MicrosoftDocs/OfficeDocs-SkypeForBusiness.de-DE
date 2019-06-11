---
title: 'Lync Server 2013: Konfigurieren von Archivierungsoptionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98356b53940c6189abac5a4b554769093f84dd2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="f836b-102">Konfigurieren von Archivierungsoptionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f836b-102">Configuring Archiving options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f836b-103">_**Letztes Änderungsdatum des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="f836b-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="f836b-104">In der lync Server 2013-Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um anzugeben, wie die Archivierung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f836b-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="f836b-105">Dies umfasst die folgenden Archivierungs Konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="f836b-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="f836b-106">Eine globale Konfiguration, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f836b-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="f836b-107">Optionale Konfigurationen auf Websiteebene und auf Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Websites oder Pools implementiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f836b-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="f836b-108">Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="f836b-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="f836b-109">In der lync Server 2013-Systemsteuerung können Sie auf \*\*\*\* der Seite Archivierungs-und Überwachungsgruppe auf der Seite Archivierungs **-und Überwachungs** Einstellungen Konfigurationen auf globaler Ebene, Websiteebene und Poolebene verwalten.</span><span class="sxs-lookup"><span data-stu-id="f836b-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="f836b-110">Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [wie funktioniert die Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellung Dokumentation oder Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f836b-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="f836b-111">Details zum Verwalten von Konfigurationen nach der Bereitstellung finden Sie unter [Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Websites und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f836b-111">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f836b-112">Um die Archivierung verwenden zu können, müssen Sie Archivierungsrichtlinien so konfigurieren, dass Sie angeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f836b-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="f836b-113">Standardmäßig ist die Archivierung für die interne oder externe Kommunikation nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f836b-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="f836b-114">Bevor Sie die Archivierung in einer beliebigen Richtlinie aktivieren, sollten Sie die geeigneten Archivierungs Konfigurationen für Ihre Bereitstellung und optional für bestimmte Websites und Pools angeben, wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f836b-114">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="f836b-115">Details zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f836b-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="f836b-116">Wenn Sie die Microsoft Exchange-Integration nicht für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie Archivierungsrichtlinien so konfigurieren, dass Sie angeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für beide aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f836b-116">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="f836b-117">Standardmäßig ist die Archivierung für die Archivierung von Daten bei der Verwendung von lync Server 2013-Archivierungsdatenbanken nicht für die interne oder externe Kommunikation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f836b-117">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="f836b-118">Bevor Sie die Archivierung in einer beliebigen Richtlinie aktivieren, sollten Sie die geeigneten Archivierungs Konfigurationen für Ihre Bereitstellung und optional für bestimmte Websites und Pools angeben, wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f836b-118">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="f836b-119">Details zum Aktivieren der Archivierung zur Verwendung mit lync Server 2013-Archivierungsdatenbanken finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f836b-119">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f836b-120">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f836b-120">In This Section</span></span>

  - [<span data-ttu-id="f836b-121">Konfigurieren von Archivierungsoptionen auf globaler Ebene in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f836b-121">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="f836b-122">Konfigurieren von Archivierungsoptionen für eine Website in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f836b-122">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="f836b-123">Konfigurieren von Archivierungsoptionen für einen Pool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f836b-123">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


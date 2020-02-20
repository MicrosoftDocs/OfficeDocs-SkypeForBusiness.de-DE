---
title: 'Lync Server 2013: Konfigurieren von Archivierungsoptionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 873b7775c889f5d866e21f04c1f154a3158ea99d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="0d8e9-102">Konfigurieren von Archivierungsoptionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d8e9-102">Configuring Archiving options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d8e9-103">_**Letztes Änderungsstand des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="0d8e9-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="0d8e9-104">In lync Server 2013 Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um anzugeben, wie die Archivierung implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="0d8e9-105">Dies schließt die folgenden Archivierungskonfigurationen ein:</span><span class="sxs-lookup"><span data-stu-id="0d8e9-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="0d8e9-106">Eine globale Konfiguration, die standardmäßig erstellt wird, wenn Sie lync Server 2013 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="0d8e9-107">Optionale Konfigurationen auf Standort- und Poolebene, die Sie zum Angeben der Implementierungsart für spezielle Standorte oder Pools erstellen und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="0d8e9-108">Sie legen Archivierungskonfigurationen anfangs fest, wenn Sie Archivierungen bereitstellen, Sie können jedoch nach der Bereitstellung Konfigurationen ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="0d8e9-109">In lync Server 2013 Systemsteuerung können Sie die Seite **Archivierungskonfiguration** der Gruppe **Archivierung und Überwachung** verwenden, um Konfigurationen auf globaler Ebene, auf Standortebene und auf Poolebene zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="0d8e9-110">Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="0d8e9-111">Ausführliche Informationen zum Verwalten von Konfigurationen nach der Bereitstellung finden Sie unter [Managing Archiving Configuration options in lync Server 2013 für Ihre Organisation, Standorte und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-111">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d8e9-112">Für die Verwendung der Archivierung müssen Sie Archivierungsrichtlinien konfigurieren, um anzugeben, ob die Archivierung für die interne Kommunikation, für externe Kommunikationen oder für Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="0d8e9-113">Standardmäßig ist die Archivierung weder für die interne noch für die externe Kommunikation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="0d8e9-114">Bevor Sie die Archivierung in Richtlinien aktivieren, sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellung und optional für spezielle Standorte und Pools angeben, wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-114">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="0d8e9-115">Ausführliche Informationen zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="0d8e9-116">Wenn Sie Microsoft Exchange Integration nicht für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie Archivierungsrichtlinien konfigurieren, um anzugeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für beides aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-116">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="0d8e9-117">Standardmäßig ist die Archivierung für die interne oder externe Kommunikation für die Archivierung von Daten nicht aktiviert, wenn lync Server 2013 Archivierungsdatenbanken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-117">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="0d8e9-118">Vor dem Aktivieren der Archivierung in sämtlichen Richtlinien sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellungen und optional für bestimmte Standorte und Pools angeben, wie dies in diesem Abschnitt beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-118">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="0d8e9-119">Ausführliche Informationen zum Aktivieren der Archivierung für die Verwendung mit lync Server 2013-Archivierungsdatenbanken finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-119">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0d8e9-120">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0d8e9-120">In This Section</span></span>

  - [<span data-ttu-id="0d8e9-121">Konfigurieren von Archivierungsoptionen auf globaler Ebene in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d8e9-121">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="0d8e9-122">Konfigurieren von Archivierungsoptionen für eine Website in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d8e9-122">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="0d8e9-123">Konfigurieren von Archivierungsoptionen für einen Pool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d8e9-123">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


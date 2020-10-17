---
title: 'Lync Server 2013: Verwalten von Archivierungs Konfigurationsoptionen für Ihre Organisation, Standorte und Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fd9b777f3c7dbfc008f0b985a9c1512aaeb52d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498362"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="8a717-102">Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Standorte und Pools</span><span class="sxs-lookup"><span data-stu-id="8a717-102">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a717-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8a717-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8a717-104">In lync Server 2013 Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um anzugeben, wie die Archivierung implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="8a717-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="8a717-105">Dies schließt die folgenden Archivierungskonfigurationen ein:</span><span class="sxs-lookup"><span data-stu-id="8a717-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="8a717-106">Eine globale Konfiguration, die standardmäßig erstellt wird, wenn Sie lync Server 2013 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8a717-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="8a717-107">Optionale Konfigurationen auf Standort- und Poolebene, die Sie zum Angeben der Implementierungsart für spezielle Standorte oder Pools erstellen und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8a717-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="8a717-108">Sie legen Archivierungskonfigurationen anfangs fest, wenn Sie Archivierungen bereitstellen, Sie können jedoch nach der Bereitstellung Konfigurationen ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="8a717-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="8a717-109">In lync Server 2013 Systemsteuerung können Sie die Seite **Archivierungskonfiguration** der Gruppe **Archivierung und Überwachung** verwenden, um Konfigurationen auf globaler Ebene, auf Standortebene und auf Poolebene zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="8a717-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="8a717-110">Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8a717-110">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a717-111">Für die Verwendung der Archivierung müssen Sie Archivierungsrichtlinien konfigurieren, um anzugeben, ob die Archivierung für die interne Kommunikation, für externe Kommunikationen oder für alle Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8a717-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="8a717-112">Standardmäßig ist die Archivierung weder für die interne noch für die externe Kommunikation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8a717-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="8a717-113">Wenn Sie Microsoft Exchange Integration verwenden, müssen Sie Exchange 2013 aktivieren und konfigurieren, um die Archivierung für alle Benutzer zu unterstützen, die in Exchange 2013 verwaltet werden, deren Postfächer In-Place Aufbewahrungsspeicher abgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="8a717-113">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="8a717-114">Bevor Sie die Archivierung aktivieren, sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellung und optional auch für bestimmte Standorte und Pools festlegen, so wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8a717-114">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="8a717-115">Ausführliche Informationen zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8a717-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="8a717-116">**So zeigen Sie Informationen zur Archivierungskonfiguration mithilfe von Windows PowerShell-Cmdlets an**</span><span class="sxs-lookup"><span data-stu-id="8a717-116">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="8a717-117">Sie können die Informationen zur Archivierungskonfiguration mit Windows PowerShell und dem Cmdlet **Get-CsArchivingConfiguration** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8a717-117">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="8a717-118">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="8a717-118">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8a717-119">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="8a717-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="8a717-120">Verwenden Sie im lync Server-Verwaltungsshell den folgenden Befehl, um Informationen zu allen Archivierungs Konfigurationseinstellungen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="8a717-120">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="8a717-121">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8a717-121">In This Section</span></span>

  - [<span data-ttu-id="8a717-122">Erstellen einer Archivierungskonfiguration in lync Server 2013 zur Verwaltung der Archivierung für bestimmte Standorte oder Pools</span><span class="sxs-lookup"><span data-stu-id="8a717-122">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="8a717-123">Aktivieren oder Deaktivieren der Archivierung von Chat-oder Konferenzsitzungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a717-123">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="8a717-124">Aktivieren oder Deaktivieren der Löschung archivierter Daten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a717-124">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="8a717-125">Aktivieren oder Deaktivieren des kritischen Modus in lync Server 2013 zum Blockieren oder Zulassen von Chat-und Webkonferenz Sitzungen, wenn die Archivierung fehlschlägt</span><span class="sxs-lookup"><span data-stu-id="8a717-125">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="8a717-126">Aktivieren oder Deaktivieren des Sendens von Archivierungs Haftungsausschlüssen an Verbundpartner in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a717-126">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="8a717-127">Aktivieren oder Deaktivieren der Integration von lync Server 2013 mit Exchange-Speicher</span><span class="sxs-lookup"><span data-stu-id="8a717-127">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="8a717-128">Löschen einer Archivierungskonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a717-128">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a717-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a717-129">See Also</span></span>


[<span data-ttu-id="8a717-130">Verwalten der Lync Server 2013-Archivierung</span><span class="sxs-lookup"><span data-stu-id="8a717-130">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


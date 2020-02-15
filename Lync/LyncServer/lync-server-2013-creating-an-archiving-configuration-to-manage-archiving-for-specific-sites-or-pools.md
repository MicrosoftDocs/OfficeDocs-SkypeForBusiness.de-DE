---
title: 'Lync Server 2013: Erstellen einer Archivierungskonfiguration für die Verwaltung der Archivierung für bestimmte Standorte oder Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5c9e12c01efe461da65fc9b87b4a1f87d526e52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a><span data-ttu-id="c7a77-102">Erstellen einer Archivierungskonfiguration in lync Server 2013 zur Verwaltung der Archivierung für bestimmte Standorte oder Pools</span><span class="sxs-lookup"><span data-stu-id="c7a77-102">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7a77-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c7a77-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c7a77-104">In lync Server 2013 Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um zu steuern, wie die Archivierung in Ihrer Bereitstellung implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c7a77-104">In Lync Server 2013 Control Panel, you use Archiving configurations to control how archiving is implemented in your deployment.</span></span> <span data-ttu-id="c7a77-105">Dies schließt die folgenden Archivierungskonfigurationen ein:</span><span class="sxs-lookup"><span data-stu-id="c7a77-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="c7a77-106">Eine globale Konfiguration, die standardmäßig erstellt wird, wenn Sie lync Server 2013 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c7a77-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="c7a77-107">Optionale Konfigurationen auf Standort- und Poolebene, die Sie zum Angeben der Implementierungsart für spezielle Standorte oder Pools erstellen und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c7a77-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="c7a77-108">Sie legen Archivierungskonfigurationen anfangs fest, wenn Sie Archivierungen bereitstellen, Sie können jedoch nach der Bereitstellung Konfigurationen ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="c7a77-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="c7a77-109">Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7a77-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7a77-110">Für die Verwendung der Archivierung müssen Sie Archivierungsrichtlinien konfigurieren, um anzugeben, ob die Archivierung für die interne Kommunikation, für externe Kommunikationen oder für Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7a77-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="c7a77-111">Standardmäßig ist die Archivierung weder für die interne noch für die externe Kommunikation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c7a77-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="c7a77-112">Bevor Sie die Archivierung in Richtlinien aktivieren, sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellung und optional für spezielle Standorte und Pools angeben, wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c7a77-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="c7a77-113">Ausführliche Informationen zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7a77-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="c7a77-114">Wenn Sie nach der Bereitstellung der Archivierung, die Sie Microsoft Exchange Integration zum Speichern von Archivierungsdaten und-Dateien auf Exchange 2013 Servern verwenden möchten und alle Ihre Benutzer auf Ihren Exchange 2013 Servern verwaltet werden, entscheiden, sollten Sie die SQL Server Datenbankkonfiguration entfernen. aus Ihrer Topologie.</span><span class="sxs-lookup"><span data-stu-id="c7a77-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="c7a77-115">Sie müssen den Topologie-Generator verwenden, um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="c7a77-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="c7a77-116">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-changing-archiving-database-options.md">Ändern von Archivierungsdatenbank Optionen in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7a77-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a><span data-ttu-id="c7a77-117">So erstellen Sie eine Archivierungskonfiguration für einen Standort oder einen Pool</span><span class="sxs-lookup"><span data-stu-id="c7a77-117">To create an archiving configuration for a site or pool</span></span>

1.  <span data-ttu-id="c7a77-118">Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c7a77-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c7a77-119">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c7a77-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c7a77-120">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c7a77-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c7a77-121">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c7a77-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="c7a77-122">Klicken Sie auf der Seite **Archivierungskonfiguration** auf **neu**, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c7a77-122">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="c7a77-123">Um eine Standort Archivierungskonfiguration zu erstellen, klicken Sie auf **Standortkonfiguration** , und wählen Sie dann unter **Standort auswählen**den Standort aus, der für die Archivierung konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7a77-123">To create a site archiving configuration, click **Site Configuration** and then, in **Select a site**, select the site to be configured for archiving.</span></span>
    
      - <span data-ttu-id="c7a77-124">Um eine Pool Archivierungskonfiguration zu erstellen, klicken Sie auf **Poolkonfiguration** , und wählen Sie dann in **Pool auswählen**den Pool aus, der für die Archivierung konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7a77-124">To create a pool archiving configuration, click **Pool Configuration** and then, in **Select a pool**, select the pool to be configured for archiving.</span></span>

5.  <span data-ttu-id="c7a77-125">Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c7a77-125">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="c7a77-126">Um nur Sofortnachrichtensitzungen zu archivieren, klicken Sie auf **Sofortnachrichtensitzungen archivieren**.</span><span class="sxs-lookup"><span data-stu-id="c7a77-126">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="c7a77-127">Klicken Sie auf **Chat-und Webkonferenz Sitzungen archivieren**, um die Archivierung für Sofortnachrichten-und Webkonferenzen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c7a77-127">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="c7a77-128">Um die Archivierung für die Richtlinie zu deaktivieren, klicken Sie auf **Archivierung deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="c7a77-128">To disable archiving for the policy, click **Disable archiving**.</span></span>

6.  <span data-ttu-id="c7a77-129">Gehen Sie unter **Neue Archivierungseinstellung** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="c7a77-129">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="c7a77-130">Aktivieren Sie das Kontrollkästchen **Instant Messaging- oder Webkonferenzsitzungen bei Archivierungsfehlern blockieren**, um die Aktivität zu blockieren, wenn die Archivierung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c7a77-130">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="c7a77-131">Um Exchange Server zum Speichern von Archivierungsdaten zu verwenden, klicken Sie auf das Kontrollkästchen **Integration der Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="c7a77-131">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="c7a77-132">Zum Aktivieren des Löschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c7a77-132">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="c7a77-133">Klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c7a77-133">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="c7a77-134">Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c7a77-134">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="c7a77-135">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c7a77-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c7a77-136">Erstellen von Archivierungs Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c7a77-136">Creating Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c7a77-137">Die Archivierungs Konfigurationseinstellungen können mithilfe von Windows PowerShell und dem Cmdlet New-CsArchivingConfiguration erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c7a77-137">Archiving configuration settings can be created by using Windows PowerShell and the New-CsArchivingConfiguration cmdlet.</span></span> <span data-ttu-id="c7a77-138">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c7a77-138">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c7a77-139">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="c7a77-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a><span data-ttu-id="c7a77-140">So erstellen Sie eine neue Auflistung von Archivierungs Konfigurationseinstellungen für eine Website</span><span class="sxs-lookup"><span data-stu-id="c7a77-140">To create a new collection of archiving configuration settings for a site</span></span>

  - <span data-ttu-id="c7a77-141">Mit dem folgenden Befehl wird eine neue Auflistung von Archivierungs Konfigurationseinstellungen für den Standort "Redmond" erstellt:</span><span class="sxs-lookup"><span data-stu-id="c7a77-141">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a><span data-ttu-id="c7a77-142">So erstellen Sie eine neue Auflistung von Archivierungs Konfigurationseinstellungen, die nur die Sofortnachrichten Archivierung zulassen</span><span class="sxs-lookup"><span data-stu-id="c7a77-142">To create a new collection of archiving configuration settings that only allow IM archiving</span></span>

  - <span data-ttu-id="c7a77-143">Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7a77-143">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="c7a77-144">Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein.</span><span class="sxs-lookup"><span data-stu-id="c7a77-144">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="c7a77-145">Um beispielsweise eine Sammlung von Archivierungs Konfigurationseinstellungen zu erstellen, die standardmäßig die Archivierung von Chatsitzungen erlauben, verwenden Sie nur einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="c7a77-145">For example, to create a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions, only use a command like this:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a><span data-ttu-id="c7a77-146">So geben Sie beim Erstellen von Archivierungs Konfigurationseinstellungen mehrere Eigenschaftswerte an</span><span class="sxs-lookup"><span data-stu-id="c7a77-146">To specify multiple property values when creating archiving configuration settings</span></span>

  - <span data-ttu-id="c7a77-147">Mehrere Eigenschaftswerte können durch die Angabe mehrerer Parameter geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c7a77-147">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="c7a77-148">Mit diesem Befehl werden beispielsweise die neuen Einstellungen so konfiguriert, dass Chatnachrichten archiviert werden, und das sofortige Messaging des Archivierungsdiensts blockiert wird nicht zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="c7a77-148">For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

<span data-ttu-id="c7a77-149">Weitere Informationen finden Sie im Hilfethema zum [New-CsArchivingConfiguration-](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c7a77-149">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7a77-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7a77-150">See Also</span></span>


[<span data-ttu-id="c7a77-151">Funktionsweise der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7a77-151">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="c7a77-152">Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Standorte und Pools</span><span class="sxs-lookup"><span data-stu-id="c7a77-152">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Erstellen einer Archivierungskonfiguration zum Verwalten der Archivierung für bestimmte Websites oder Pools'
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
ms.openlocfilehash: 3b0495a15d19adba9ac21fb7817347a16b78bc13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a><span data-ttu-id="c8eb5-102">Erstellen einer Archivierungskonfiguration in lync Server 2013 zum Verwalten der Archivierung für bestimmte Websites oder Pools</span><span class="sxs-lookup"><span data-stu-id="c8eb5-102">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8eb5-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c8eb5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c8eb5-104">In der lync Server 2013-Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um zu steuern, wie die Archivierung in Ihrer Bereitstellung implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-104">In Lync Server 2013 Control Panel, you use Archiving configurations to control how archiving is implemented in your deployment.</span></span> <span data-ttu-id="c8eb5-105">Dies umfasst die folgenden Archivierungs Konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="c8eb5-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="c8eb5-106">Eine globale Konfiguration, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="c8eb5-107">Optionale Konfigurationen auf Websiteebene und auf Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Websites oder Pools implementiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="c8eb5-108">Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="c8eb5-109">Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8eb5-110">Um die Archivierung verwenden zu können, müssen Sie Archivierungsrichtlinien so konfigurieren, dass Sie angeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="c8eb5-111">Standardmäßig ist die Archivierung für die interne oder externe Kommunikation nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="c8eb5-112">Bevor Sie die Archivierung in einer beliebigen Richtlinie aktivieren, sollten Sie die geeigneten Archivierungs Konfigurationen für Ihre Bereitstellung und optional für bestimmte Websites und Pools angeben, wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="c8eb5-113">Details zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="c8eb5-114">Wenn Sie nach der Bereitstellung der Archivierung entscheiden, dass Sie die Microsoft Exchange-Integration zum Speichern von Archivierungsdaten und-Dateien auf Exchange 2013-Servern verwenden möchten und alle Ihre Benutzer auf Ihren Exchange 2013-Servern gespeichert sind, sollten Sie die SQL Server-Datenbankkonfiguration entfernen. aus Ihrer Topologie.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="c8eb5-115">Dazu müssen Sie den Topology Builder verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="c8eb5-116">Ausführliche Informationen finden Sie unter Ändern der Optionen für die <A href="lync-server-2013-changing-archiving-database-options.md">Archivierungsdatenbank in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a><span data-ttu-id="c8eb5-117">So erstellen Sie eine Archivierungskonfiguration für eine Website oder einen Pool</span><span class="sxs-lookup"><span data-stu-id="c8eb5-117">To create an archiving configuration for a site or pool</span></span>

1.  <span data-ttu-id="c8eb5-118">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8eb5-119">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c8eb5-120">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c8eb5-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c8eb5-121">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="c8eb5-122">Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c8eb5-122">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="c8eb5-123">Wenn Sie eine Website Archivierungskonfiguration erstellen möchten, klicken Sie auf **Websitekonfiguration** , und wählen Sie dann unter **Website auswählen**die Website aus, die für die Archivierung konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-123">To create a site archiving configuration, click **Site Configuration** and then, in **Select a site**, select the site to be configured for archiving.</span></span>
    
      - <span data-ttu-id="c8eb5-124">Wenn Sie eine Pool Archivierungskonfiguration erstellen möchten, klicken Sie auf **Poolkonfiguration** , und wählen Sie dann in **Pool auswählen**den Pool aus, der für die Archivierung konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-124">To create a pool archiving configuration, click **Pool Configuration** and then, in **Select a pool**, select the pool to be configured for archiving.</span></span>

5.  <span data-ttu-id="c8eb5-125">Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c8eb5-125">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="c8eb5-126">Klicken Sie auf **Chatsitzungen archivieren**, um die Archivierung ausschließlich für Chatsitzungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-126">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="c8eb5-127">Klicken Sie auf **Chat- und Webkonferenzsitzungen archivieren**, um sowohl Chatsitzungen als auch Konferenzen zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-127">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="c8eb5-128">Klicken Sie auf **Archivierung deaktivieren**, um die Archivierung für die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-128">To disable archiving for the policy, click **Disable archiving**.</span></span>

6.  <span data-ttu-id="c8eb5-129">Führen Sie außerdem in **Neue Archivierungseinstellung** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c8eb5-129">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="c8eb5-130">Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-130">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="c8eb5-131">Wenn Sie Microsoft Exchange Server zum Speichern von Archivierungsdaten verwenden möchten, klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** .</span><span class="sxs-lookup"><span data-stu-id="c8eb5-131">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="c8eb5-132">Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c8eb5-132">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="c8eb5-133">Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-133">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="c8eb5-134">Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-134">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="c8eb5-135">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c8eb5-136">Erstellen von Archivierungs Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c8eb5-136">Creating Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c8eb5-137">Die Archivierungs Konfigurationseinstellungen können mithilfe von Windows PowerShell und dem Cmdlet New-CsArchivingConfiguration erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-137">Archiving configuration settings can be created by using Windows PowerShell and the New-CsArchivingConfiguration cmdlet.</span></span> <span data-ttu-id="c8eb5-138">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-138">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c8eb5-139">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a><span data-ttu-id="c8eb5-140">So erstellen Sie eine neue Sammlung von Archivierungs Konfigurationseinstellungen für eine Website</span><span class="sxs-lookup"><span data-stu-id="c8eb5-140">To create a new collection of archiving configuration settings for a site</span></span>

  - <span data-ttu-id="c8eb5-141">Mit dem folgenden Befehl wird eine neue Auflistung von Archivierungskonfigurationseinstellungen für den Standort „Redmond“ erstellt:</span><span class="sxs-lookup"><span data-stu-id="c8eb5-141">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a><span data-ttu-id="c8eb5-142">So erstellen Sie eine neue Sammlung von Archivierungs Konfigurationseinstellungen, die nur die Chat Archivierung zulassen</span><span class="sxs-lookup"><span data-stu-id="c8eb5-142">To create a new collection of archiving configuration settings that only allow IM archiving</span></span>

  - <span data-ttu-id="c8eb5-143">Da im vorherigen Befehl keine weiteren Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in der neuen Auflistung von Konfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-143">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="c8eb5-144">Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein.</span><span class="sxs-lookup"><span data-stu-id="c8eb5-144">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="c8eb5-145">Wenn Sie beispielsweise eine Sammlung von Archivierungs Konfigurationseinstellungen erstellen möchten, die standardmäßig die Archivierung von Instant Messaging-Sitzungen zulassen, verwenden Sie nur einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="c8eb5-145">For example, to create a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions, only use a command like this:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a><span data-ttu-id="c8eb5-146">So geben Sie beim Erstellen von Archivierungs Konfigurationseinstellungen mehrere Eigenschaftswerte an</span><span class="sxs-lookup"><span data-stu-id="c8eb5-146">To specify multiple property values when creating archiving configuration settings</span></span>

  - <span data-ttu-id="c8eb5-p108">Mehrere Eigenschaftswerte können geändert werden, indem Sie mehrere Parameter angeben. Beispielsweise werden mit dem folgenden Befehl die neuen Einstellungen so konfiguriert, dass Chatsitzungen archiviert werden und Chats blockiert werden, falls der Archivierungsdienst nicht verfügbar ist:</span><span class="sxs-lookup"><span data-stu-id="c8eb5-p108">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

<span data-ttu-id="c8eb5-149">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="c8eb5-149">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8eb5-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8eb5-150">See Also</span></span>


[<span data-ttu-id="c8eb5-151">Funktionsweise der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8eb5-151">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="c8eb5-152">Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, ihre Websites und Pools</span><span class="sxs-lookup"><span data-stu-id="c8eb5-152">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


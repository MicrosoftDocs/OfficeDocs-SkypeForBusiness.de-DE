---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren der Löschung archivierter Daten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 308ba7b91fbe776ed49d72c54e2986ad95d080fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500942"
---
# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a><span data-ttu-id="58d99-102">Aktivieren oder Deaktivieren der Löschung archivierter Daten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58d99-102">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58d99-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="58d99-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="58d99-104">In lync Server 2013 Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um die Bereinigung zu aktivieren und zu deaktivieren und zu konfigurieren, wie das Löschen implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="58d99-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable purging and configure how purging is implemented.</span></span> <span data-ttu-id="58d99-105">Dies schließt die folgenden Archivierungskonfigurationen ein:</span><span class="sxs-lookup"><span data-stu-id="58d99-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="58d99-106">Eine globale Konfiguration, die standardmäßig erstellt wird, wenn Sie lync Server 2013 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="58d99-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="58d99-107">Optionale Konfigurationen auf Standort- und Poolebene, die Sie zum Angeben der Implementierungsart für spezielle Standorte oder Pools erstellen und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="58d99-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="58d99-108">Sie legen Archivierungskonfigurationen anfangs fest, wenn Sie Archivierungen bereitstellen, Sie können jedoch nach der Bereitstellung Konfigurationen ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="58d99-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="58d99-109">Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="58d99-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58d99-110">Um die Archivierung für Benutzer zu verwenden, die in lync Server 2013 verwaltet werden, müssen Sie Archivierungsrichtlinien konfigurieren, um anzugeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für beides aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="58d99-110">To use archiving for users who are homed on Lync Server 2013 you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="58d99-111">In der Standardeinstellung ist die Archivierung weder für die interne noch für die externe Kommunikation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="58d99-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="58d99-112">Bevor Sie die Archivierung mithilfe von Richtlinien aktivieren, sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellung und optional auch für bestimmte Standorte und Pools festlegen, so wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58d99-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="58d99-113">Ausführliche Informationen zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="58d99-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="58d99-114">Wenn Sie nach der Bereitstellung der Archivierung, die Sie Microsoft Exchange Integration zum Speichern von Archivierungsdaten und-Dateien auf Exchange 2013 Servern verwenden möchten und alle Ihre Benutzer auf Ihren Exchange 2013 Servern verwaltet werden, entscheiden, sollten Sie die SQL Server Datenbankkonfiguration aus Ihrer Topologie entfernen.</span><span class="sxs-lookup"><span data-stu-id="58d99-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="58d99-115">Sie müssen den Topologie-Generator verwenden, um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="58d99-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="58d99-116">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-changing-archiving-database-options.md">Ändern von Archivierungsdatenbank Optionen in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="58d99-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a><span data-ttu-id="58d99-117">So aktivieren oder deaktivieren Sie den Löschvorgang für die Archivierung</span><span class="sxs-lookup"><span data-stu-id="58d99-117">To enable or disable purging for archiving</span></span>

1.  <span data-ttu-id="58d99-118">Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="58d99-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="58d99-119">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="58d99-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="58d99-120">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="58d99-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="58d99-121">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="58d99-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="58d99-122">Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der entsprechenden globalen, Standort- oder Poolkonfiguration. Klicken Sie dann auf **Bearbeiten** und auf **Details anzeigen**, und gehen Sie anschließend folgendermaßen vor.</span><span class="sxs-lookup"><span data-stu-id="58d99-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="58d99-123">Zum Aktivieren des Löschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="58d99-123">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
        
          - <span data-ttu-id="58d99-124">Zum Löschen aller Datensätze klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie die Anzahl der Tage an.</span><span class="sxs-lookup"><span data-stu-id="58d99-124">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="58d99-125">Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="58d99-125">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
      - <span data-ttu-id="58d99-126">Zum Deaktivieren des Löschvorgangs deaktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="58d99-126">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>

5.  <span data-ttu-id="58d99-127">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="58d99-127">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="58d99-128">Aktivieren oder Deaktivieren des Löschens von Archivierungsdaten mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="58d99-128">Enabling or Disabling the Purging of Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="58d99-129">Das Aktivieren und Deaktivieren der automatischen Bereinigung von Archivierungsdaten kann mit Windows PowerShell und dem Cmdlet " **CsArchivingConfiguration** " verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="58d99-129">Enabling and disabling the automated purging of archiving data can be managed by using Windows PowerShell and the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="58d99-130">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="58d99-130">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="58d99-131">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="58d99-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a><span data-ttu-id="58d99-132">So aktivieren Sie das Löschen aller Archivierungsdaten</span><span class="sxs-lookup"><span data-stu-id="58d99-132">To enable the purging of all archiving data</span></span>

  - <span data-ttu-id="58d99-133">Um das Löschen aller Archivierungsdaten zu ermöglichen, legen Sie die **"enablepurging"** -Eigenschaft auf true ($true) fest.</span><span class="sxs-lookup"><span data-stu-id="58d99-133">To enable the purging of all archiving data set the **EnablePurging** property to true ($True).</span></span> <span data-ttu-id="58d99-134">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="58d99-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    <span data-ttu-id="58d99-135">Nach dem Ausführen dieses Befehls werden lync Server alle Archivierungsdaten Sätze, die älter sind als der für die **"keeparchivingdatafordays"** -Eigenschaft angegebene Wert, jeden Tag gelöscht.</span><span class="sxs-lookup"><span data-stu-id="58d99-135">After this command is run, then every day Lync Server will purge all archiving records older than the value specified for the **KeepArchivingDataForDays** property.</span></span>

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a><span data-ttu-id="58d99-136">So aktivieren Sie das Löschen von exportierten Archivierungsdaten</span><span class="sxs-lookup"><span data-stu-id="58d99-136">To enable the purging only of exported archiving data</span></span>

  - <span data-ttu-id="58d99-137">Zum Begrenzen des Löschvorgangs auf Archivierungsdaten Sätze, die in eine Datendatei exportiert wurden (mithilfe des [Export-CsArchivingData-](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) Cmdlets), müssen Sie auch die "purgeexportedarchivesonly"-Eigenschaft auf true ($true) festlegen.</span><span class="sxs-lookup"><span data-stu-id="58d99-137">To limit purging to archiving records that have been exported to a data file (by using the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet) you must also set the PurgeExportedArchivesOnly property to True ($True).</span></span> <span data-ttu-id="58d99-138">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="58d99-138">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    <span data-ttu-id="58d99-139">Nach Ausführung dieses Befehls löscht lync Server nur Archivierungsdaten Sätze, die zwei Kriterien erfüllen: 1) Sie sind älter als der für die **"keeparchivingdatafordays"** -Eigenschaft angegebene Wert; und 2) Sie wurden mit dem **Export-CsArchivingData-** Cmdlet exportiert.</span><span class="sxs-lookup"><span data-stu-id="58d99-139">After this command is run, Lync Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the **KeepArchivingDataForDays** property; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a><span data-ttu-id="58d99-140">So deaktivieren Sie das Löschen aller Archivierungsdaten</span><span class="sxs-lookup"><span data-stu-id="58d99-140">To disable the purging of all archiving data</span></span>

  - <span data-ttu-id="58d99-141">Wenn Sie das automatische Löschen von Archivierungsdaten Sätzen deaktivieren möchten, legen Sie die **"enablepurging"** -Eigenschaft auf false ($false) fest.</span><span class="sxs-lookup"><span data-stu-id="58d99-141">To disable the automated purging of archiving records, set the **EnablePurging** property to False ($False).</span></span> <span data-ttu-id="58d99-142">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="58d99-142">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

<span data-ttu-id="58d99-143">Weitere Informationen, einschließlich zusätzlicher Optionen zum Löschen von Archivierungsdaten, finden Sie im Hilfethema für das Cmdlet " [setCsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) ".</span><span class="sxs-lookup"><span data-stu-id="58d99-143">For more information, including additional options for purging archiving data, see the help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="58d99-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58d99-144">See Also</span></span>


[<span data-ttu-id="58d99-145">Funktionsweise der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58d99-145">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="58d99-146">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58d99-146">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[<span data-ttu-id="58d99-147">Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Standorte und Pools</span><span class="sxs-lookup"><span data-stu-id="58d99-147">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


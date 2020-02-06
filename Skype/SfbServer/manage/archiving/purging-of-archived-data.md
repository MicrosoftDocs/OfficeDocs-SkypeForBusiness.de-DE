---
title: Verwalten der Bereinigung archivierter Daten in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie das Löschen archivierter Daten für Skype for Business Server verwalten.'
ms.openlocfilehash: 7953c6085183e3ace0e395f0c8751897acd49380
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818877"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="2db97-103">Verwalten der Bereinigung archivierter Daten in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2db97-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="2db97-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie das Löschen archivierter Daten für Skype for Business Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="2db97-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="2db97-105">Die Archivierungsdatenbank ist nicht für die langfristige Aufbewahrung vorgesehen, und Skype for Business Server bietet keine e-Discovery-Lösung (Suche) für archivierte Daten, sodass Daten in andere Speicher verschoben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="2db97-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="2db97-106">Skype for Business Server bietet ein Sitzungs Export Tool, mit dem Sie archivierte Daten in durchsuchbare Transkripte exportieren können.</span><span class="sxs-lookup"><span data-stu-id="2db97-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="2db97-107">Sie müssen festlegen, wann archivierte und exportierte Daten gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2db97-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="2db97-108">Weitere Informationen zum Exportieren von Daten mithilfe des Cmdlets **Export-CsArchivingData** finden Sie unter [Exportieren von archivierten Daten in Skype for Business Server](export-archived-data.md).</span><span class="sxs-lookup"><span data-stu-id="2db97-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="2db97-109">Löschen von Daten über die Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="2db97-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="2db97-110">So löschen Sie archivierte Daten über die Systemsteuerung:</span><span class="sxs-lookup"><span data-stu-id="2db97-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="2db97-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="2db97-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="2db97-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2db97-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2db97-113">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="2db97-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="2db97-114">Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten** und auf **Details anzeigen** und führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="2db97-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="2db97-115">Aktivieren Sie zum Starten des Löschvorgangs das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2db97-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="2db97-116">Wenn Sie alle Datensätze löschen möchten, klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie die Anzahl der Tage an.</span><span class="sxs-lookup"><span data-stu-id="2db97-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="2db97-117">Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="2db97-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="2db97-118">Deaktivieren Sie zum Beenden des Löschvorgangs das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="2db97-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="2db97-119">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2db97-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="2db97-120">Löschen von Daten über die Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2db97-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="2db97-121">Mit den folgenden Windows PowerShell-Cmdlets können Sie archivierte Daten löschen:</span><span class="sxs-lookup"><span data-stu-id="2db97-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="2db97-122">Mit dem Cmdlet **Set-CsArchivingConfiguration** und dem Parameter EnablePurging können Sie das Löschen archivierter Daten aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2db97-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="2db97-123">Mit **Invoke-CsArchivingDatabasePurge** können Sie Datensätze manuell aus der Archivierungsdatenbank löschen.</span><span class="sxs-lookup"><span data-stu-id="2db97-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="2db97-124">Der folgende Befehl ermöglicht beispielsweise, alle archivierten Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="2db97-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="2db97-125">Nachdem dieser Befehl ausgeführt wurde, löscht Skype for Business Server alle Archivierungsdaten Sätze, die älter als der für den "keeparchivingdatafordays"-Parameter angegebene Wert sind.</span><span class="sxs-lookup"><span data-stu-id="2db97-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="2db97-126">Der folgende Befehl beschränkt das Löschen auf archivierte Datensätze, die (mit dem Cmdlet **Export-CSArchivingData**) in eine Datendatei exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2db97-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="2db97-127">Außerdem müssen Sie den Parameter PurgeExportedArchivesOnly auf „True“ ($True) setzen:</span><span class="sxs-lookup"><span data-stu-id="2db97-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="2db97-128">Nachdem dieser Befehl ausgeführt wurde, werden von Skype for Business Server nur Archivierungsdaten Sätze bereinigt, die zwei Kriterien erfüllen: 1) Sie sind älter als der für den "keeparchivingdatafordays"-Parameter angegebene Wert; und 2) Sie wurden mit dem Cmdlet **Export-CsArchivingData** exportiert.</span><span class="sxs-lookup"><span data-stu-id="2db97-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="2db97-129">Setzen Sie zum Deaktivieren der automatischen Löschung archivierter Datensätze den Parameter „EnablePurging“ auf „False“ ($False).</span><span class="sxs-lookup"><span data-stu-id="2db97-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="2db97-130">Im folgenden Beispiel wird das **Invoke-CsArchivingDatabasePurge-** Cmdlet verwendet, um alle Datensätze, die mehr als 24 Stunden alt sind, aus der Archivierungsdatenbank auf ATL-SQL-001.contoso.com zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2db97-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="2db97-131">Um sicherzustellen, dass alle Datensätze gelöscht werden (also auch Datensätze, die nicht exportiert wurden), wird der Parameter „PurgeExportedArchivesOnly“ auf „False“ ($False) festgelegt:</span><span class="sxs-lookup"><span data-stu-id="2db97-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```

---
title: Angeben der Beibehaltung von CDR-Daten in Skype for Business Server
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
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Daten zur Anrufdetailaufzeichnung für Skype for Business Server verwalten.'
ms.openlocfilehash: 7cb9926ee8ec124b2fc75a69653c43c0150b6446
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817674"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="b8117-103">Angeben der Beibehaltung von CDR-Daten in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b8117-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="b8117-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Daten zur Anrufdetailaufzeichnung für Skype for Business Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="b8117-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="b8117-p101">In der Standardeinstellung werden Daten zur Aufzeichnung von Kommunikationsdatensätzen (KDS) nach 60 Tagen gelöscht. Sie können die Einstellungen auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** verwenden, um die Daten für einen längeren oder kürzeren Zeitraum zu speichern. Wenn Sie KDS deaktivieren, werden auch Daten gelöscht, die bei aktivierter KDS-Datenerfassung aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="b8117-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8117-p102">Sie sollten die Aufzeichnung von Kommunikationsdatensätzen (KDS) und QoE-Daten (Quality of Experience) so konfigurieren, dass Daten für die gleiche Anzahl von Tagen gespeichert werden. Die Berichte zu den aufgezeichneten Kommunikationsdatensätzen (KDS), verfügbar auf der Webseite für Monitoring Server-Berichte, umfassen KDS- und QoE-Informationen zu jedem Anruf. Wenn die Zeit bis zum Löschen für KDS und QoE abweicht, umfassen einige Anrufe möglicherweise nur KDS-Daten, während andere ausschließlich QoE-Daten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b8117-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="b8117-111">Verwenden Sie die folgenden Verfahren, um Bereinigungseinstellungen für KDS-Daten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b8117-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="b8117-112">So geben Sie die Beibehaltungsdauer für KDS-Daten an</span><span class="sxs-lookup"><span data-stu-id="b8117-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="b8117-113">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .</span><span class="sxs-lookup"><span data-stu-id="b8117-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="b8117-114">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b8117-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b8117-115">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.</span><span class="sxs-lookup"><span data-stu-id="b8117-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="b8117-116">Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="b8117-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="b8117-117">Wählen Sie **Bereinigung von KDS-Aufzeichnungen aktivieren** aus, um die Bereinigung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b8117-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="b8117-118">Wählen Sie unter **Maximale Aufbewahrungsdauer für KDS-Aufzeichnungen (in Tagen):** die maximale Anzahl von Tagen aus, für die KDS-Aufzeichnungen gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b8117-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="b8117-119">Wählen Sie unter **Maximale Aufbewahrungsdauer von Fehlerberichtsdaten (in Tagen):** die maximale Anzahl von Tagen, für die Fehlerberichte gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b8117-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="b8117-120">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="b8117-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b8117-121">Angeben der CDR-Aufbewahrung mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b8117-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="b8117-122">Sie können CdR-Aufbewahrungseinstellungen mithilfe von Windows PowerShell und dem Cmdlet "Satz-CsCdrConfiguration" erstellen.</span><span class="sxs-lookup"><span data-stu-id="b8117-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="b8117-123">Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="b8117-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b8117-124">Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="b8117-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b8117-125">Der Vorgang ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="b8117-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="b8117-126">So geben Sie die Beibehaltungsdauer für KDS-Daten für einen bestimmten Standort an</span><span class="sxs-lookup"><span data-stu-id="b8117-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="b8117-127">Mit diesem Befehl werden KDS-Daten für den Standort „Redmond“ bereinigt und außerdem wird für den Standort konfiguriert, dass sowohl KDS-Daten als auch Fehlerberichtdaten 20 Tage lang aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="b8117-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="b8117-128">So geben Sie die Beibehaltungsdauer für KDS-Daten für mehrere Standorte an</span><span class="sxs-lookup"><span data-stu-id="b8117-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="b8117-129">Mit diesem Befehl wird die Beibehaltung von KDS-Daten für alle in einer Organisation verwendeten KDS-Konfigurationseinstellungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="b8117-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="b8117-130">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="b8117-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b8117-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8117-131">See also</span></span>

[<span data-ttu-id="b8117-132">Anrufdetailaufzeichnung (CDR) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b8117-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)

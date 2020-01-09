---
title: Ändern der Einstellungen für die Qualität der Benutzerfreundlichkeit in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Beibehaltung von QoE-Daten in Skype for Business Server angeben.'
ms.openlocfilehash: c597c0e5e3fbd2a8a92304ffd55d866a15c121a9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992040"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="2f395-103">Ändern der Einstellungen für die Qualität der Benutzerfreundlichkeit in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2f395-103">Modify Quality of Experience settings in Skype for Business Server</span></span>

<span data-ttu-id="2f395-104">**Zusammenfassung:** Erfahren Sie, wie Sie die Aufbewahrung von QoE-Daten in Skype for Business Server angeben.</span><span class="sxs-lookup"><span data-stu-id="2f395-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>

<span data-ttu-id="2f395-p101">In der Standardeinstellung werden QoE-Daten (Quality of Experience, Erlebnisqualität) nach 60 Tagen gelöscht. Sie können die Einstellungen auf der Seite **QoE-Daten** verwenden, um die Daten für einen längeren oder kürzeren Zeitraum zu speichern. Wenn Sie QoE deaktivieren, werden auch Daten gelöscht, die bei aktivierter QoE-Datenerfassung aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="2f395-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

> [!NOTE]
> <span data-ttu-id="2f395-p102">Sie sollten die Aufzeichnung von Kommunikationsdatensätzen (KDS) und QoE-Daten so konfigurieren, dass Daten für die gleiche Anzahl von Tagen gespeichert werden. Die Berichte zu den aufgezeichneten Kommunikationsdatensätzen (KDS), verfügbar auf der Webseite für Überwachungsberichte, umfassen KDS- und QoE-Informationen zu jedem Anruf. Wenn die Zeit bis zum Löschen für KDS und QoE abweicht, umfassen einige Anrufe möglicherweise nur KDS-Daten, während andere ausschließlich QoE-Daten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2f395-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>

<span data-ttu-id="2f395-111">Das nachfolgende Verfahren beschreibt, wie Sie die Löscheinstellungen für QoE-Daten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2f395-111">The following procedure describes how to configure purge settings for QoE data.</span></span>

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2f395-112">So legen Sie die Beibehaltung von QoE-Daten mithilfe der Skype for Business Server-Systemsteuerung fest</span><span class="sxs-lookup"><span data-stu-id="2f395-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="2f395-p103">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="2f395-p103">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="2f395-115">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2f395-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="2f395-116">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="2f395-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="2f395-117">Klicken Sie auf der Seite **QoE-Daten** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2f395-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5. <span data-ttu-id="2f395-118">Wählen Sie die Option **Löschen für QoE aktivieren** aus, um die Löschung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2f395-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6. <span data-ttu-id="2f395-119">Wählen Sie unter **Maximale Speicherdauer für die QuE-Aufzeichnung (Tage)** die maximale Anzahl von Tagen aus, für die QoE-Daten gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2f395-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7. <span data-ttu-id="2f395-120">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2f395-120">Click **Commit**.</span></span>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2f395-121">Angeben der QoE-Aufbewahrung mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2f395-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2f395-122">Sie können QoE-Aufbewahrungseinstellungen mithilfe von Windows PowerShell und dem Cmdlet " **Satz-CsQoEConfiguration** " erstellen.</span><span class="sxs-lookup"><span data-stu-id="2f395-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="2f395-123">Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="2f395-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2f395-124">Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="2f395-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="2f395-125">Der Vorgang ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="2f395-125">The process is the same in Skype for Business Server.</span></span>

### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="2f395-126">So geben Sie die QoE-Aufbewahrung für einen speziellen Standort an</span><span class="sxs-lookup"><span data-stu-id="2f395-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="2f395-127">Dieser Befehl ermöglicht das Löschen von QoE-Daten für den Standort Redmond. Zudem wird damit für die QoE-Daten eine Aufbewahrungsdauer von 20 Tagen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2f395-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="2f395-128">So geben Sie die QoE-Aufbewahrung für mehrere Standorte an</span><span class="sxs-lookup"><span data-stu-id="2f395-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="2f395-129">Mit diesem Befehl wird die Beibehaltung von QoE-Daten für alle in einer Organisation verwendeten QoE-Konfigurationseinstellungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2f395-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

<span data-ttu-id="2f395-130">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="2f395-130">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f395-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f395-131">See also</span></span>

[<span data-ttu-id="2f395-132">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="2f395-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

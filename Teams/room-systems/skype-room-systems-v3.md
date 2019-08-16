---
title: Übersicht über die Verwaltung für Microsoft Teams-Chatrooms
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Übersicht über das Management für Microsoft Teams-Chatrooms.
ms.openlocfilehash: db1569f86ba0066691b6797517351087307cf38a
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427874"
---
# <a name="management-overview"></a><span data-ttu-id="a9ccd-103">Verwaltung (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="a9ccd-103">Management overview</span></span> 

<span data-ttu-id="a9ccd-104">Es ist wichtig, dass Sie kontinuierliche Wartung und Vorgänge entwickeln und ausführen, um sicherzustellen, dass Ihre Microsoft Teams rooms-Systeme für Ihre Benutzer verfügbar sind und eine hervorragende Benutzererfahrung bieten.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="a9ccd-105">Überwachung</span><span class="sxs-lookup"><span data-stu-id="a9ccd-105">Monitoring</span></span> 

<span data-ttu-id="a9ccd-106">Das Überwachen von Microsoft Teams rooms Systems umfasst zwei Hauptaktivitäten:</span><span class="sxs-lookup"><span data-stu-id="a9ccd-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

-  <span data-ttu-id="a9ccd-107">Überwachung von Geräten, Anwendungen und Peripheriegeräten</span><span class="sxs-lookup"><span data-stu-id="a9ccd-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="a9ccd-108">Qualitäts-und Zuverlässigkeitsüberwachung (CQD)</span><span class="sxs-lookup"><span data-stu-id="a9ccd-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="a9ccd-109">Geräte-, Anwendungs-und Peripheriegeräte Überwachung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a9ccd-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="a9ccd-110">Um sicherzustellen, dass die Benutzer die Microsoft Teams-Zimmereinheiten verwenden können, müssen die Einheiten aktiviert sein, mit dem Netzwerk verbunden sein, wobei die Microsoft Teams rooms-Anwendung ordnungsgemäß konfiguriert ist und mit funktionierenden Peripheriegeräten verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="a9ccd-111">Informationen zum Status der Microsoft Teams rooms-Anwendung und verbundenen Peripheriegeräte werden von der Microsoft Teams rooms-Anwendung in das Windows-Ereignisprotokoll geschrieben und in [verstehen der Protokolleinträge](azure-monitor-manage.md#understand-the-log-entries)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="a9ccd-112">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="a9ccd-112">**Setting**</span></span>|<span data-ttu-id="a9ccd-113">**Ermöglicht**</span><span class="sxs-lookup"><span data-stu-id="a9ccd-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9ccd-114">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (DWORD) 1</span><span class="sxs-lookup"><span data-stu-id="a9ccd-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="a9ccd-115">Ermöglicht das Starten von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="a9ccd-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="a9ccd-116">Power Management-\> auf AC, schalten Sie den Bildschirm nach 10 Minuten aus.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="a9ccd-117">Power Management-\> auf AC, niemals System in den Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="a9ccd-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="a9ccd-118">Ermöglicht Microsoft Teams-Räumen, die angefügten anzeigen zu deaktivieren und automatisch zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="a9ccd-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="a9ccd-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="a9ccd-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="a9ccd-120">Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="a9ccd-121">Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="a9ccd-122">Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="a9ccd-123">Ermöglicht die ständige Anmeldung des Skype-Kontos</span><span class="sxs-lookup"><span data-stu-id="a9ccd-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="a9ccd-124">Das Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren eines Dateielements](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)erläutert.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="a9ccd-125">Remoteverwaltung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9ccd-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="a9ccd-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="a9ccd-126"></span></span>

<span data-ttu-id="a9ccd-127">Wir empfehlen, Microsoft Operations Manager Suite zum Überwachen Ihrer Microsoft Teams rooms-Systeme zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="a9ccd-128">Anleitungen zum Einrichten der Überwachung und grundlegender Warnungen finden Sie unter [Bereitstellen der Microsoft Teams rooms-Verwaltung mit Azure Monitor](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="a9ccd-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="a9ccd-129">Anhand dieser Anleitung können Sie ein einfach zu bedienendes Dashboard erstellen, um Probleme mit Ihren Microsoft Teams-Räumen für Ihre Bereitstellung zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="a9ccd-130">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="a9ccd-130">Decision points</span></span>|<ul><li><span data-ttu-id="a9ccd-131">Vergewissern Sie sich, dass Sie die Operations Management Suite verwenden, um die Bereitstellung von Microsoft Teams Rooms zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="a9ccd-132">Wählen Sie die Ziel Verteilerliste aus, die Sie für e-Mail-Benachrichtigungen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="a9ccd-133">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a9ccd-133">Next steps</span></span>|<ul><li><span data-ttu-id="a9ccd-134">Definieren Ihres Überwachungs Ansatzes für Qualität und Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="a9ccd-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="a9ccd-135">Qualitäts-und Zuverlässigkeitsüberwachung (CQD)</span><span class="sxs-lookup"><span data-stu-id="a9ccd-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="a9ccd-136">Wir empfehlen, dass Sie die laufenden Überwachungsverfahren zur betrieblichen Qualitäts-und Zuverlässigkeitsüberwachung im Rahmen ihrer Bereitstellung implementieren, um den Trend der Anruf-und Besprechungs Qualität und-Zuverlässigkeit zu überwachen, alle bedenklichen Bereiche zu identifizieren und auf eine Lösung hinzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="a9ccd-137">Wenn Sie Ihre Gebäudeinformationen auf CQD hochladen, können Sie die Trends für die Anrufqualität und-Zuverlässigkeit auf pro-Gebäude-Ebene untersuchen, wodurch es einfacher ist, Gebäude zu vergleichen und ihre Aufmerksamkeit auf bestimmte Probleme zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span>

<span data-ttu-id="a9ccd-138">Wir empfehlen, dass Sie das [Review-Handbuch für die Qualität der Benutzerfreundlichkeit](https://aka.ms/qerguide) überprüfen und befolgen, um Qualitäts-und Zuverlässigkeits Trends zu identifizieren und einen Aktionsplan zum Beheben dieser Informationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-138">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="a9ccd-139">Aktualisieren der Office-Anwendung Microsoft Teams Rooms und Microsoft Teams rooms</span><span class="sxs-lookup"><span data-stu-id="a9ccd-139">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="a9ccd-140">Wir empfehlen, dass Sie die Anwendung Microsoft Teams rooms OS und Microsoft Teams rooms aktualisieren, um von Produktupdates und Verbesserungen profitieren zu können.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-140">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="a9ccd-141">Detaillierte Anleitungen finden Sie unter [Verwalten von Microsoft Teams-Räumen](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="a9ccd-141">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="a9ccd-142">Windows-Updates</span><span class="sxs-lookup"><span data-stu-id="a9ccd-142">Windows Updates</span></span>

<span data-ttu-id="a9ccd-143">Microsoft Teams rooms läuft unter Windows 10 Enterprise-oder Windows 10 Enterprise (VL) und empfängt dieselben Windows-Updates und Betriebssystem-Builds wie ein Standard-Desktop.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-143">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="a9ccd-144">Weitere Informationen finden Sie unter [Verwalten von Windows-Updates](updates.md) .</span><span class="sxs-lookup"><span data-stu-id="a9ccd-144">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="a9ccd-145">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="a9ccd-145">Troubleshooting</span></span>

<span data-ttu-id="a9ccd-146">Wir empfehlen, dass Sie die Operations Management Suite-Benachrichtigung so einrichten, wie es im obigen Abschnitt beschrieben ist, damit Ihr Betriebsteam und Ihr Helpdesk über alle Probleme mit Microsoft Teams rooms benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-146">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="a9ccd-147">Die für die PowerShell-Remoteverwaltung verfügbaren Optionen werden in der [Remoteverwaltung mithilfe von PowerShell](room-systems-v2-operations.md#remote-management-using-powershell)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-147">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="a9ccd-148">Für den Fall, dass ein Peripheriegerät getrennt wird, müssen Sie sich möglicherweise auf lokale "Smart Hands" oder IT-Unterstützung verlassen, um die Geräte zu untersuchen und erneut zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-148">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="a9ccd-149">Weitere Informationen zur Problembehandlung und zum Administratormodus finden Sie unter [Verwalten von Microsoft Teams-Räumen](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="a9ccd-149">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="a9ccd-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9ccd-150">See also</span></span>

[<span data-ttu-id="a9ccd-151">Microsoft Teams Rooms-Hilfe</span><span class="sxs-lookup"><span data-stu-id="a9ccd-151">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="a9ccd-152">Planen von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="a9ccd-152">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="a9ccd-153">Bereitstellen von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="a9ccd-153">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="a9ccd-154">Konfigurieren einer Microsoft Teams rooms-Konsole</span><span class="sxs-lookup"><span data-stu-id="a9ccd-154">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="a9ccd-155">Remoteverwaltung einer Microsoft Teams rooms-Konsoleneinstellungen mit einer XML-Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="a9ccd-155">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)

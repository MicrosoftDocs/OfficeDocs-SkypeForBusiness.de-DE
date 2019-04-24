---
title: Übersicht über die Verwaltung für Microsoft-Teams Räume
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Übersicht über die Verwaltung für Microsoft-Teams Chatrooms.
ms.openlocfilehash: a06ffc6bb0aa69b493c95a516946c322034913f8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32208246"
---
# <a name="management-overview"></a><span data-ttu-id="34b02-103">Verwaltung (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="34b02-103">Management overview</span></span> 

<span data-ttu-id="34b02-104">Es ist wichtig, dass Sie entwickeln und Ausführen von laufenden Wartung und erleben Sie die Vorgänge, um sicherzustellen, dass die Microsoft-Teams Chatrooms Systeme für Ihre Benutzer verfügbar sind und einen hervorragendes Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="34b02-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="34b02-105">Überwachung</span><span class="sxs-lookup"><span data-stu-id="34b02-105">Monitoring</span></span> 

<span data-ttu-id="34b02-106">Überwachen von Microsoft-Teams Räume-Systemen umfasst zwei wichtige Aktivitäten:</span><span class="sxs-lookup"><span data-stu-id="34b02-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

-  <span data-ttu-id="34b02-107">Gerät, Anwendung und Überwachen von Peripheriegeräte</span><span class="sxs-lookup"><span data-stu-id="34b02-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="34b02-108">Qualität und Zuverlässigkeit Überwachung (CQD)</span><span class="sxs-lookup"><span data-stu-id="34b02-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="34b02-109">Microsoft-Teams Chatrooms Gerät, Anwendung und Überwachen von Peripheriegeräte</span><span class="sxs-lookup"><span data-stu-id="34b02-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="34b02-110">Die Einheiten, um sicherzustellen, dass Benutzer die Einheiten für die Microsoft-Teams Chatrooms verwenden können, müssen auf, mit dem Netzwerk verbunden ist, mit der Microsoft-Teams Chatrooms Anwendung ordnungsgemäß konfiguriert und funktionsfähig Peripheriegeräte hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="34b02-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="34b02-111">Informationen zum Status der Anwendung Microsoft Teams Chatrooms und der verbundenen Peripheriegeräte wird von der Anwendung Microsoft Teams Rooms in der Windows-Ereignisprotokoll geschrieben und in [die Protokolleinträge verstehen](azure-monitor.md#understand-the-log-entries)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="34b02-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="34b02-112">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="34b02-112">**Setting**</span></span>|<span data-ttu-id="34b02-113">**Ermöglicht**</span><span class="sxs-lookup"><span data-stu-id="34b02-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="34b02-114">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon automatische Anmeldung = (Dword) 1</span><span class="sxs-lookup"><span data-stu-id="34b02-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="34b02-115">Microsoft-Teams Chatrooms starten aktiviert</span><span class="sxs-lookup"><span data-stu-id="34b02-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="34b02-116">Strom-Management -\> AC, deaktivieren Sie auf Bildschirm nach 10 Minuten</span><span class="sxs-lookup"><span data-stu-id="34b02-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="34b02-117">Strom-Management -\> auf AC, setzen Sie nie System in den Energiesparmodus</span><span class="sxs-lookup"><span data-stu-id="34b02-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="34b02-118">Microsoft-Teams Chatrooms angefügte zeigt deaktivieren und Reaktivieren von automatisch aktiviert</span><span class="sxs-lookup"><span data-stu-id="34b02-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="34b02-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="34b02-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="34b02-120">Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto.</span><span class="sxs-lookup"><span data-stu-id="34b02-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="34b02-121">Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="34b02-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="34b02-122">Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.</span><span class="sxs-lookup"><span data-stu-id="34b02-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="34b02-123">Ermöglicht die ständige Anmeldung des Skype-Kontos</span><span class="sxs-lookup"><span data-stu-id="34b02-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="34b02-124">Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren einer Dateielement](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)erläutert.</span><span class="sxs-lookup"><span data-stu-id="34b02-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="34b02-125">Remoteverwaltung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="34b02-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="34b02-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="34b02-126"></span></span>

<span data-ttu-id="34b02-127">Es wird empfohlen, dass Sie Microsoft Operations Manager-Suite verwenden, um die Microsoft-Teams Chatrooms Systeme überwachen.</span><span class="sxs-lookup"><span data-stu-id="34b02-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="34b02-128">Anleitungen für Überwachung und Warnungen grundlegende einrichten finden Sie unter [Bereitstellen von Microsoft Teams Chatrooms Management mit Azure überwachen](../../deploy/deploy-clients/azure-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="34b02-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](../../deploy/deploy-clients/azure-monitor.md).</span></span> 

<span data-ttu-id="34b02-129">Dieser Anleitung können Sie ein Dashboard einfach zu verwendende, um Probleme mit Ihrem Microsoft-Teams Chatrooms Einheiten in Ihrer Bereitstellung zu erkennen erstellen.</span><span class="sxs-lookup"><span data-stu-id="34b02-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/><span data-ttu-id="34b02-130">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="34b02-130">Decision points</span></span>|<ul><li><span data-ttu-id="34b02-131">Vergewissern Sie sich, dass Sie zum Überwachen der bereitstellungs von Microsoft-Teams Chatrooms Vorgänge Management-Suite verwenden.</span><span class="sxs-lookup"><span data-stu-id="34b02-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="34b02-132">Entscheiden Sie, die Ziel-Verteilerliste, die Sie für e-Mail-Benachrichtigungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="34b02-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/><span data-ttu-id="34b02-133">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="34b02-133">Next steps</span></span>|<ul><li><span data-ttu-id="34b02-134">Definieren Sie die Qualität und Zuverlässigkeit Ansatz monitoring.</span><span class="sxs-lookup"><span data-stu-id="34b02-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="34b02-135">Qualität und Zuverlässigkeit Überwachung (CQD)</span><span class="sxs-lookup"><span data-stu-id="34b02-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="34b02-136">Es wird empfohlen, dass Sie laufenden Betrieb Qualität und Zuverlässigkeit Verfahren als Teil der Bereitstellung zum Überwachen der Trend Anruf und Besprechung Qualität und Zuverlässigkeit, Überwachung, die alle Bereiche identifiziert und arbeiten in Richtung einer Lösung implementieren.</span><span class="sxs-lookup"><span data-stu-id="34b02-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="34b02-137">Wenn Sie Ihre Informationen zum Erstellen von in CQD hochladen können Sie Anruf Qualität und Zuverlässigkeit Trends auf einer Ebene pro Erstellen von untersuchen sie einfach zu vergleichen Gebäude und konzentrieren Sie sich Ihre Aufmerksamkeit zu bestimmten Problemen.</span><span class="sxs-lookup"><span data-stu-id="34b02-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="34b02-138">Laden Sie weitere Informationen der [Monitor-CQD für Skype für Online-Bereitstellung von Business und Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span><span class="sxs-lookup"><span data-stu-id="34b02-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="34b02-139">Es wird empfohlen, dass Sie überprüfen, und führen Sie die [Erfahrung überprüfen Handbuch für Quality of](https://aka.ms/qerguide) um Trends für die Qualität und Zuverlässigkeit zu identifizieren, und eines Aktionsplans erstellen zu deren Lösung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34b02-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="34b02-140">Aktualisieren der Anwendung Microsoft Teams Chatrooms OS und Microsoft Teams Räume</span><span class="sxs-lookup"><span data-stu-id="34b02-140">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="34b02-141">Es wird empfohlen, dass Sie die Anwendung Microsoft-Teams Chatrooms OS und Microsoft Teams Chatrooms von Produktupdates und Verbesserungen profitieren aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="34b02-141">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="34b02-142">Ausführliche Anleitungen finden Sie unter [Verwalten von Microsoft Teams Chatrooms](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="34b02-142">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="34b02-143">Windows-Updates</span><span class="sxs-lookup"><span data-stu-id="34b02-143">Windows Updates</span></span>

<span data-ttu-id="34b02-144">Microsoft Teams Räume auf Windows 10 Enterprise IoT oder Windows 10 Enterprise (VL) ausgeführt wird und die gleichen Windows-Updates und OS Builds als standard Desktop empfängt.</span><span class="sxs-lookup"><span data-stu-id="34b02-144">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="34b02-145">Einzelheiten finden Sie unter [Verwalten von Windows-Updates](updates.md) .</span><span class="sxs-lookup"><span data-stu-id="34b02-145">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="34b02-146">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="34b02-146">Troubleshooting</span></span>

<span data-ttu-id="34b02-147">Es wird empfohlen, dass Sie Operationen Management Suite Warnungen, wie oben beschrieben, damit Ihre Vorgänge Teams und der Helpdesk Probleme, wenn Microsoft Teams Chatrooms benachrichtigt werden, eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="34b02-147">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="34b02-148">Die Optionen für die Remoteverwaltung PowerShell haben Sie werden in die [Remoteverwaltung mithilfe von PowerShell](room-systems-v2-operations.md#remote-management-using-powershell)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34b02-148">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="34b02-149">Den Fall, dass eine Peripheriegeräte getrennt ist, müssen Sie "intelligente Zeiger" lokale oder IT-Support zu untersuchen und schließen Sie die Geräte abhängig.</span><span class="sxs-lookup"><span data-stu-id="34b02-149">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="34b02-150">Weitere Informationen zu Problembehandlung und Admin-Modus finden Sie unter [Verwalten von Microsoft Teams Chatrooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="34b02-150">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="34b02-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34b02-151">See also</span></span>

[<span data-ttu-id="34b02-152">Microsoft Teams Rooms-Hilfe</span><span class="sxs-lookup"><span data-stu-id="34b02-152">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="34b02-153">Planen der Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="34b02-153">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="34b02-154">Bereitstellen von Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="34b02-154">Deploy Microsoft Teams Rooms</span></span>](../../deploy/deploy-clients/room-systems-v2.md)

[<span data-ttu-id="34b02-155">Konfigurieren einer Microsoft-Teams Räume-Konsole</span><span class="sxs-lookup"><span data-stu-id="34b02-155">Configure a Microsoft Teams Rooms console</span></span>](../../deploy/deploy-clients/console.md)

[<span data-ttu-id="34b02-156">Verwalten einer Microsoft-Teams Chatrooms Konsolenstamm Remote mit einer XML-Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="34b02-156">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)

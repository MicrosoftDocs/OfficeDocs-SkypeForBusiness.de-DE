---
title: Übersicht über die Verwaltung für Skype Raum Systemen v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Übersicht über die dokumentverwaltung für Skype Raum Systemen v2.
ms.openlocfilehash: 81ad0e43f68127e3a178434ebdd8ac8a43c94adc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21014903"
---
# <a name="management-overview"></a><span data-ttu-id="f6b2f-103">Übersicht über die Verwaltung</span><span class="sxs-lookup"><span data-stu-id="f6b2f-103">Management overview</span></span> 

<span data-ttu-id="f6b2f-104">Es ist wichtig, dass Sie entwickeln und Ausführen von laufenden Wartung und erleben Sie die Vorgänge, um sicherzustellen, dass Ihre Skype Raum v2-basierte Systeme für Ihre Benutzer verfügbar sind und einen hervorragendes Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Skype Room Systems v2 systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="f6b2f-105">Überwachung</span><span class="sxs-lookup"><span data-stu-id="f6b2f-105">Monitoring</span></span> 

<span data-ttu-id="f6b2f-106">Überwachung Skype Raum v2-basierte Systeme besteht aus zwei wichtige Aktivitäten:</span><span class="sxs-lookup"><span data-stu-id="f6b2f-106">Monitoring Skype Room Systems v2 systems consists of two key activities:</span></span>

-  <span data-ttu-id="f6b2f-107">Gerät, Anwendung und Überwachen von Peripheriegeräte</span><span class="sxs-lookup"><span data-stu-id="f6b2f-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="f6b2f-108">Qualität und Zuverlässigkeit Überwachung (CQD)</span><span class="sxs-lookup"><span data-stu-id="f6b2f-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="f6b2f-109">Skype Raum Systeme, Version 2, Gerät, Anwendung und Überwachen von Peripheriegeräte</span><span class="sxs-lookup"><span data-stu-id="f6b2f-109">Skype Room Systems v2 device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="f6b2f-110">Die Einheiten, um sicherzustellen, dass Benutzer die Skype Raum Systemen v2 Einheiten verwenden können, müssen auf, mit dem Netzwerk verbunden ist, mit der Skype Raum Systemen v2 Anwendung ordnungsgemäß konfiguriert und funktionsfähig Peripheriegeräte hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-110">To ensure that users are able to use the Skype Room Systems v2 units, the units must be on, connected to the network with the Skype Room Systems v2 application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="f6b2f-111">Informationen zum Status der Skype Raum Systemen v2 Anwendung und der verbundenen Peripheriegeräte wird von der Skype Raum Systemen v2-Anwendung in der Windows-Ereignisprotokoll geschrieben und [in diesem Artikel](oms.md#understand-the-log-entries)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-111">Information about the state of the Skype Room Systems v2 application and connected peripheral devices is written by the Skype Room Systems v2 application to the Windows event log and documented [in this article](oms.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="f6b2f-112">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="f6b2f-112">**Setting**</span></span>|<span data-ttu-id="f6b2f-113">**Ermöglicht**</span><span class="sxs-lookup"><span data-stu-id="f6b2f-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f6b2f-114">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon automatische Anmeldung = (Dword) 1</span><span class="sxs-lookup"><span data-stu-id="f6b2f-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="f6b2f-115">Ermöglicht das Skype Raum Systemen v2 starten</span><span class="sxs-lookup"><span data-stu-id="f6b2f-115">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="f6b2f-116">Strom-Management -\> AC, deaktivieren Sie auf Bildschirm nach 10 Minuten</span><span class="sxs-lookup"><span data-stu-id="f6b2f-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="f6b2f-117">Strom-Management -\> auf AC, setzen Sie nie System in den Energiesparmodus</span><span class="sxs-lookup"><span data-stu-id="f6b2f-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="f6b2f-118">Skype-Chatroom-Systemen v2 angefügte zeigt deaktivieren und Reaktivieren von automatisch aktiviert</span><span class="sxs-lookup"><span data-stu-id="f6b2f-118">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="f6b2f-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="f6b2f-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="f6b2f-p101">Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto. Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten. Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann. </span><span class="sxs-lookup"><span data-stu-id="f6b2f-p101">Or equivalent means of disabling password expiration on the local account. Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password. Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="f6b2f-123">Ermöglicht die ständige Anmeldung des Skype-Kontos</span><span class="sxs-lookup"><span data-stu-id="f6b2f-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="f6b2f-124">Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren einer Dateielement](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)erläutert.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="f6b2f-125">Remoteverwaltung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6b2f-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="f6b2f-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="f6b2f-126"></span></span>


<span data-ttu-id="f6b2f-127">Es wird empfohlen, dass Sie Microsoft Operations Manager-Suite verwenden, um Ihre Skype Raum v2 Systeme überwachen.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Skype Room Systems v2 systems.</span></span> <span data-ttu-id="f6b2f-128">Anleitungen für Überwachung und Warnungen grundlegende einrichten finden Sie unter [Bereitstellen von Skype Raum v2 systemverwaltung mit OMS](../../deploy/deploy-clients/with-oms.md).</span><span class="sxs-lookup"><span data-stu-id="f6b2f-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Skype Room Systems v2 management with OMS](../../deploy/deploy-clients/with-oms.md).</span></span> 

<span data-ttu-id="f6b2f-129">Dieser Anleitung können Sie ein Dashboard einfach zu verwendende, um Probleme mit Ihrer Skype Raum Systemen v2 Einheiten in Ihrer Bereitstellung zu erkennen erstellen.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Skype Room Systems v2 units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/><span data-ttu-id="f6b2f-130">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="f6b2f-130">Decision points</span></span>|<ul><li><span data-ttu-id="f6b2f-131">Vergewissern Sie sich, dass Sie Vorgänge Management Suite zum Überwachen der Skype Raum Systemen v2-bereitstellungs verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-131">Confirm that you'll use Operations Management Suite to monitor your Skype Room Systems v2 deployment.</span></span></li><li><span data-ttu-id="f6b2f-132">Entscheiden Sie, die Ziel-Verteilerliste, die Sie für e-Mail-Benachrichtigungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/><span data-ttu-id="f6b2f-133">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f6b2f-133">Next steps</span></span>|<ul><li><span data-ttu-id="f6b2f-134">Definieren Sie die Qualität und Zuverlässigkeit Ansatz monitoring.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="f6b2f-135">Qualität und Zuverlässigkeit Überwachung (CQD)</span><span class="sxs-lookup"><span data-stu-id="f6b2f-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="f6b2f-136">Es wird empfohlen, dass Sie laufenden Betrieb Qualität und Zuverlässigkeit Verfahren als Teil der Bereitstellung zum Überwachen der Trend Anruf und Besprechung Qualität und Zuverlässigkeit, Überwachung, die alle Bereiche identifiziert und arbeiten in Richtung einer Lösung implementieren.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="f6b2f-137">Wenn Sie Ihre Informationen zum Erstellen von in CQD hochladen können Sie Anruf Qualität und Zuverlässigkeit Trends auf einer Ebene pro Erstellen von untersuchen sie einfach zu vergleichen Gebäude und konzentrieren Sie sich Ihre Aufmerksamkeit zu bestimmten Problemen.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="f6b2f-138">Laden Sie weitere Informationen der [Monitor-CQD für Skype für Online-Bereitstellung von Business und Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span><span class="sxs-lookup"><span data-stu-id="f6b2f-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="f6b2f-139">Es wird empfohlen, dass Sie überprüfen, und führen Sie die [Erfahrung überprüfen Handbuch für Quality of](https://aka.ms/qerguide) um Trends für die Qualität und Zuverlässigkeit zu identifizieren, und eines Aktionsplans erstellen zu deren Lösung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a><span data-ttu-id="f6b2f-140">Aktualisieren der Skype Raum Systemen v2 OS und Skype Raum Systeme-Anwendung</span><span class="sxs-lookup"><span data-stu-id="f6b2f-140">Updating the Skype Room Systems v2 OS and Skype Room Systems application</span></span> 

<span data-ttu-id="f6b2f-141">Es wird empfohlen, dass Sie die Skype Raum Systemen v2 OS und Skype Raum Systemen v2 Anwendung von Produktupdates und Verbesserungen profitieren zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-141">We recommend that you update the Skype Room Systems v2 OS and Skype Room Systems v2 application to benefit from product updates and improvements.</span></span> <span data-ttu-id="f6b2f-142">Ausführliche Anleitungen finden Sie unter [Verwalten von Skype Raum Systemen v2](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="f6b2f-142">For detailed guidance, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="troubleshooting"></a><span data-ttu-id="f6b2f-143">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f6b2f-143">Troubleshooting</span></span>

<span data-ttu-id="f6b2f-144">Es wird empfohlen, dass Sie Operationen Management Suite Warnungen, wie oben beschrieben, damit Ihre Vorgänge Teams und der Helpdesk Probleme v2 Skype Raum Systeme benachrichtigt werden, eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-144">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Skype Room Systems v2 issues.</span></span> <span data-ttu-id="f6b2f-145">Die Optionen für die Remoteverwaltung PowerShell haben Sie werden in die [Remoteverwaltung mithilfe von PowerShell](room-systems-v2-operations.md#remote-management-using-powershell)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-145">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="f6b2f-146">Den Fall, dass eine Peripheriegeräte getrennt ist, müssen Sie "intelligente Zeiger" lokale oder IT-Support zu untersuchen und schließen Sie die Geräte abhängig.</span><span class="sxs-lookup"><span data-stu-id="f6b2f-146">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="f6b2f-147">Weitere Informationen zu Problembehandlung und Admin-Modus finden Sie unter [Verwalten von Skype Raum Systemen v2](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="f6b2f-147">For more information about troubleshooting and admin mode, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 

## <a name="see-also"></a><span data-ttu-id="f6b2f-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6b2f-148">See also</span></span>

[<span data-ttu-id="f6b2f-149">Skype Raum Systeme Version 2-Hilfe</span><span class="sxs-lookup"><span data-stu-id="f6b2f-149">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="f6b2f-150">Planung für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="f6b2f-150">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="f6b2f-151">Bereitstellen von Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="f6b2f-151">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)

[<span data-ttu-id="f6b2f-152">Konfigurieren einer Konsole für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="f6b2f-152">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)

[<span data-ttu-id="f6b2f-153">Verwalten einer Skype Room Systems v2-Konsoleneinstellung auf einem Remote-Gerät mit einer XML-Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="f6b2f-153">Manage a Skype Room Systems v2 console settings remotely with an XML configuration file</span></span>](xml-config-file.md)

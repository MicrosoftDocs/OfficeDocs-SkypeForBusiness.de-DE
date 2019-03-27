---
title: Übersicht über die Verwaltung für Skype Raum Systemen v2
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
description: Übersicht über die dokumentverwaltung für Skype Raum Systemen v2.
ms.openlocfilehash: edd73c6ecf973d0d066b5f46d949a792bc0910c5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880285"
---
# <a name="management-overview"></a>Verwaltung (Übersicht) 

Es ist wichtig, dass Sie entwickeln und Ausführen von laufenden Wartung und erleben Sie die Vorgänge, um sicherzustellen, dass Ihre Skype Raum v2-basierte Systeme für Ihre Benutzer verfügbar sind und einen hervorragendes Benutzer bereitzustellen. 

## <a name="monitoring"></a>Überwachung 

Überwachung Skype Raum v2-basierte Systeme besteht aus zwei wichtige Aktivitäten:

-  Gerät, Anwendung und Überwachen von Peripheriegeräte

-  Qualität und Zuverlässigkeit Überwachung (CQD)

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a>Skype Raum Systeme, Version 2, Gerät, Anwendung und Überwachen von Peripheriegeräte

Die Einheiten, um sicherzustellen, dass Benutzer die Skype Raum Systemen v2 Einheiten verwenden können, müssen auf, mit dem Netzwerk verbunden ist, mit der Skype Raum Systemen v2 Anwendung ordnungsgemäß konfiguriert und funktionsfähig Peripheriegeräte hergestellt werden. 


Informationen zum Status der Skype Raum Systemen v2 Anwendung und der verbundenen Peripheriegeräte wird von der Skype Raum Systemen v2-Anwendung in der Windows-Ereignisprotokoll geschrieben und in [die Protokolleinträge verstehen](azure-monitor.md#understand-the-log-entries)dokumentiert. 

|**Einstellung**|**Ermöglicht**|
|:-----|:-----|
|HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon automatische Anmeldung = (Dword) 1  <br/> |Ermöglicht das Skype Raum Systemen v2 starten  <br/> |
|Strom-Management -\> AC, deaktivieren Sie auf Bildschirm nach 10 Minuten  <br/> Strom-Management -\> auf AC, setzen Sie nie System in den Energiesparmodus  <br/> |Skype-Chatroom-Systemen v2 angefügte zeigt deaktivieren und Reaktivieren von automatisch aktiviert  <br/> |
|net accounts /maxpwage:unlimited  <br/> Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto. Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten. Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.  <br/> |Ermöglicht die ständige Anmeldung des Skype-Kontos  <br/> |
   
Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren einer Dateielement](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)erläutert.
  
## <a name="remote-management-using-powershell"></a>Remoteverwaltung mit PowerShell
<a name="RemotePS"> </a>


Es wird empfohlen, dass Sie Microsoft Operations Manager-Suite verwenden, um Ihre Skype Raum v2 Systeme überwachen. Anleitungen zum Einrichten der Überwachung und grundlegende Warnungen finden Sie unter [Bereitstellen von Skype Raum v2 systemverwaltung mit Azure Monitor](../../deploy/deploy-clients/azure-monitor.md). 

Dieser Anleitung können Sie ein Dashboard einfach zu verwendende, um Probleme mit Ihrer Skype Raum Systemen v2 Einheiten in Ihrer Bereitstellung zu erkennen erstellen. 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Vergewissern Sie sich, dass Sie Vorgänge Management Suite zum Überwachen der Skype Raum Systemen v2-bereitstellungs verwenden.</li><li>Entscheiden Sie, die Ziel-Verteilerliste, die Sie für e-Mail-Benachrichtigungen verwenden.</li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Definieren Sie die Qualität und Zuverlässigkeit Ansatz monitoring.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Qualität und Zuverlässigkeit Überwachung (CQD)

Es wird empfohlen, dass Sie laufenden Betrieb Qualität und Zuverlässigkeit Verfahren als Teil der Bereitstellung zum Überwachen der Trend Anruf und Besprechung Qualität und Zuverlässigkeit, Überwachung, die alle Bereiche identifiziert und arbeiten in Richtung einer Lösung implementieren. 

Wenn Sie Ihre Informationen zum Erstellen von in CQD hochladen können Sie Anruf Qualität und Zuverlässigkeit Trends auf einer Ebene pro Erstellen von untersuchen sie einfach zu vergleichen Gebäude und konzentrieren Sie sich Ihre Aufmerksamkeit zu bestimmten Problemen. Laden Sie weitere Informationen der [Monitor-CQD für Skype für Online-Bereitstellung von Business und Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15). 

Es wird empfohlen, dass Sie überprüfen, und führen Sie die [Erfahrung überprüfen Handbuch für Quality of](https://aka.ms/qerguide) um Trends für die Qualität und Zuverlässigkeit zu identifizieren, und eines Aktionsplans erstellen zu deren Lösung beschrieben. 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a>Aktualisieren der Skype Raum Systemen v2 OS und Skype Raum Systeme-Anwendung 

Es wird empfohlen, dass Sie die Skype Raum Systemen v2 OS und Skype Raum Systemen v2 Anwendung von Produktupdates und Verbesserungen profitieren zu aktualisieren. Ausführliche Anleitungen finden Sie unter [Verwalten von Skype Raum Systemen v2](room-systems-v2-operations.md#software-updates). 

## <a name="windows-updates"></a>Windows-Updates

Skype Raum System v2 (SRS v2) auf Windows 10 Enterprise IoT oder Windows 10 Enterprise (VL) ausgeführt wird und die gleichen Windows-Updates und OS Builds als standard Desktop empfängt. Einzelheiten finden Sie unter [Verwalten von Windows-Updates](updates.md) .


## <a name="troubleshooting"></a>Problembehandlung

Es wird empfohlen, dass Sie Operationen Management Suite Warnungen, wie oben beschrieben, damit Ihre Vorgänge Teams und der Helpdesk Probleme v2 Skype Raum Systeme benachrichtigt werden, eingerichtet. Die Optionen für die Remoteverwaltung PowerShell haben Sie werden in die [Remoteverwaltung mithilfe von PowerShell](room-systems-v2-operations.md#remote-management-using-powershell)beschrieben. Den Fall, dass eine Peripheriegeräte getrennt ist, müssen Sie "intelligente Zeiger" lokale oder IT-Support zu untersuchen und schließen Sie die Geräte abhängig. 

Weitere Informationen zu Problembehandlung und Admin-Modus finden Sie unter [Verwalten von Skype Raum Systemen v2](room-systems-v2-operations.md#admin-mode-and-device-management). 


## <a name="see-also"></a>Siehe auch

[Skype Raum Systeme Version 2-Hilfe](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[Bereitstellen von Skype Room Systems v2](../../deploy/deploy-clients/room-systems-v2.md)

[Konfigurieren einer Konsole für Skype Room Systems v2](../../deploy/deploy-clients/console.md)

[Verwalten einer Skype Room Systems v2-Konsoleneinstellung auf einem Remote-Gerät mit einer XML-Konfigurationsdatei](xml-config-file.md)

---
title: Planen der Verwaltung von Microsoft Teams Rooms mit Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: In diesem Artikel werden Planungsüberlegungen zur Verwendung von Azure Monitor zum Verwalten von Microsoft Teams rooms-Geräten in Ihrer Skype for Business-oder Teams-Implementierung erläutert.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 16a962d7414407cf5f2f5734b7a2f39a56f7d281
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137605"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planen der Verwaltung von Microsoft Teams Rooms mit Azure Monitor
 
 In diesem Artikel werden Planungsüberlegungen zur Verwendung von Azure Monitor zum Verwalten von Microsoft Teams rooms-Geräten in Ihrer Microsoft Teams-oder Skype for Business-Implementierung erläutert.
  
[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) ist eine Sammlung von Verwaltungsdiensten, die von Anfang an in der Cloud entwickelt wurden. Anstatt lokale Ressourcen bereitzustellen und zu verwalten, werden Azure Monitor-Komponenten vollständig in Azure gehostet. Die Konfiguration ist minimal, und Sie können innerhalb weniger Minuten buchstäblich in Betrieb sein. Mit einigen Anpassungsarbeiten kann Sie die Verwaltung von Microsoft Teams rooms-Konferenzsystemen unterstützen, indem Sie Echtzeitbenachrichtigungen über den Systemstatus oder Fehler für einzelne Raumsysteme bereitstellen und diese potenziell auf die Verwaltung von Tausenden von Microsoft Teams rooms-Konferenzräumen skalieren können.
  
Dieser Artikel enthält eine Erläuterung der Best Practices für Anforderungen, Entwurf/Architektur und Implementierung, die für die Implementierung der Azure Monitor-basierten Verwaltung von Microsoft Teams rooms-Konferenz Geräten erforderlich sind, und enthält Links zu detaillierten Artikeln zur Implementierung von Azure Monitor für Microsoft Teams-Räume sowie zu wichtigen Referenzinformationen für die laufende Überwachung von Microsoft Teams-Chatrooms. 
  
## <a name="functional-overview"></a>Funktionsübersicht

![Diagramm der Microsoft Teams rooms-Verwaltung mit Azure Monitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Die Microsoft Teams rooms-App auf dem Konsolengerät schreibt Ereignisse in das Windows-Ereignisprotokoll. Nach der Installation übergibt ein Microsoft-Überwachungs-Agent die Informationen an den Azure Monitor-Dienst. 
  
Nach der ordnungsgemäßen Konfiguration analysiert die Protokollanalyse die in den Ereignisbeschreibungen eingebettete JSON-Nutzlast, um zu beschreiben, wie die einzelnen Microsoft Teams Room-Systeme funktionieren und welche Fehler erkannt werden. 
  
Ein Administrator, der Azure Monitor verwendet, kann Benachrichtigungen zu Microsoft Teams rooms-Systemen erhalten, die offline sind oder App-, Konnektivitäts-oder Hardwarefehler aufweisen, und wissen, ob ein System neu gestartet werden muss. Jeder Systemstatus wird häufig aktualisiert, sodass diese Benachrichtigungen in der Nähe von Echtzeitupdates sind.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor-Anforderungen

Sie müssen über ein gültiges Azure-Abonnement für Azure Monitor verfügen, um die Protokollanalyse Funktion verwenden zu können. Weitere Informationen finden Sie unter [Erste Schritte mit einem Protokollanalyse-Arbeitsbereich](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) , um ein Abonnement für Ihre Organisation zu erstellen.
  
Sie sollten sich nach Bedarf über die Verwendung des Ansicht-Designers für die Protokollanalyse vertraut machen. Diese Details finden Sie unter [Ansichten in der Protokollanalyse](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) .
  
### <a name="related-tasks"></a>Verwandte Aufgaben

1. Nachdem Sie die Azure Monitor-Protokollanalyse abonniert haben, müssen Sie benutzerdefinierte Felder erstellen (wie unter " [benutzerdefinierte Felder zuordnen](azure-monitor-deploy.md#Custom_fields)" beschrieben), die zum Analysieren der Informationen benötigt werden, die von Microsoft Teams rooms-Konsolen gesendet werden. Dies umfasst das Verständnis des JSON-Schemas, [das unter verstehen der Protokolleinträge](azure-monitor-manage.md#understand-the-log-entries)dokumentiert ist.
    
2. Entwickeln Sie in der Protokollanalyse eine Microsoft Teams rooms-Verwaltungsansicht. Sie können entweder [ein Dashboard für Microsoft Teams rooms erstellen, indem Sie die Import-Methode verwenden](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) oder [ein Dashboard für Microsoft Teams-Räume manuell erstellen](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Konsolenanforderungen für einzelne Microsoft Teams-Chatrooms

Bei jeder Microsoft Teams rooms-Konsole handelt es sich um eine APP, die auf einem Surface pro-Gerät im Kioskmodus ausgeführt wird (normalerweise ist Sie so konfiguriert, dass Sie die einzige APP ist, die auf dem Gerät ausgeführt werden kann). Wie bei jeder Windows-App schreibt die Microsoft Teams rooms-App Ereignisse wie Start-und Hardwarefehler in das Windows-Ereignisprotokoll. Durch Hinzufügen eines Microsoft Monitor-Agents auf dem Microsoft Teams rooms-Gerät können diese Ereignisse erfasst werden. (Weitere Informationen finden Sie unter [Verbinden von Windows-Computern mit dem Protokollanalyse Dienst in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) .)
  
## <a name="ongoing-management"></a>Laufende Verwaltung

Bei der Verwendung von Azure Monitor zum Verwalten Ihrer Microsoft Teams rooms-Geräte müssen Sie die Informationen verstehen, die in den von Azure Monitor verwendeten Ereignisprotokollen enthalten sind. Details zu diesen Gesundheits Meldungen finden Sie Untergrund [Legendes zu den Protokolleinträgen](azure-monitor-manage.md#understand-the-log-entries) .
  
### <a name="related-tasks"></a>Verwandte Aufgaben

- Informieren Sie sich über die Warnungen, die von Microsoft Teams rooms generiert wurden, und wie Sie diese beheben können (siehe Abschnitt " [verstehen der Protokolleinträge](azure-monitor-manage.md#understand-the-log-entries)").
    
## <a name="see-also"></a>Siehe auch

[Bereitstellen von Microsoft Teams rooms Management mit Azure Monitor](azure-monitor-deploy.md)
  
[Verwalten von Microsoft Teams rooms-Geräten mit Azure Monitor](azure-monitor-manage.md)
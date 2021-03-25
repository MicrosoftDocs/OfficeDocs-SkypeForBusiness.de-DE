---
title: Planen der Verwaltung von Microsoft Teams-Räumen mit Azure Monitor
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
description: In diesem Artikel werden Überlegungen zur Planung der Verwendung von Azure Monitor zum Verwalten von Microsoft Teams Rooms-Geräten in Ihrer Skype for Business- oder Teams-Implementierung erläutert.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56b22dddfc475efc83fb5bb3ef5734743b1eb0c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117583"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planen der Verwaltung von Microsoft Teams-Räumen mit Azure Monitor
 
 In diesem Artikel werden Überlegungen zur Planung der Verwendung von Azure Monitor zum Verwalten von Microsoft Teams Rooms-Geräten in Ihrer Microsoft Teams- oder Skype for Business-Implementierung erläutert.
  
[Azure Monitor](/azure/azure-monitor/overview) ist eine Sammlung von Verwaltungsdiensten, die von Anfang an in der Cloud entwickelt wurden. Anstatt lokale Ressourcen zu bereitstellen und zu verwalten, werden Azure Monitor-Komponenten vollständig in Azure gehostet. Die Konfiguration ist minimal, und Sie können in wenigen Minuten im wahrsten Sinne des Wortes ausgeführt werden. Mit einigen Anpassungsarbeiten kann es bei der Verwaltung von Microsoft Teams Rooms-Konferenzsystemen helfen, indem Benachrichtigungen über den Systemzustand oder Fehler für einzelne Raumsysteme in Echtzeit angezeigt werden, und es kann potenziell bis zur Verwaltung tausender Microsoft Teams Rooms-Konferenzräume skaliert werden.
  
In diesem Artikel werden die bewährten Methoden für Anforderungen, Entwurf/Architektur und Implementierung erläutert, die zum Implementieren der azure monitorbasierten Verwaltung von Microsoft Teams Rooms-Konferenzgeräten erforderlich sind, sowie Links zu detaillierten Artikeln zur Implementierung von Azure Monitor für Microsoft Teams Rooms sowie wichtige Referenzinformationen für die laufende Überwachung von Microsoft Teams Rooms-Räumen. 
  
## <a name="functional-overview"></a>Funktionsübersicht

![Diagramm der Verwaltung von Microsoft Teams-Räumen mit Azure Monitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Die Microsoft Teams Rooms-App auf dem Konsolengerät schreibt Ereignisse in das Windows-Ereignisprotokoll. Ein Microsoft Monitoring-Agent übergibt die Informationen nach der Installation an den Azure Monitor-Dienst. 
  
Nach der ordnungsgemäßen Konfiguration analysiert Log Analytics die in die Ereignisbeschreibungen eingebettete JSON-Nutzlast, um zu beschreiben, wie jedes Microsoft Teams Rooms-System funktioniert und welche Fehler erkannt werden. 
  
Ein Administrator, der Azure Monitor verwendet, kann Benachrichtigungen über Microsoft Teams Rooms-Systeme erhalten, die offline sind oder app-, Konnektivitäts- oder Hardwarefehler auftreten, sowie wissen, ob ein System neu gestartet werden muss. Jeder Systemstatus wird häufig aktualisiert, sodass diese Benachrichtigungen nah an Echtzeitupdates sind.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor-Anforderungen

Sie müssen über ein gültiges Azure-Abonnement für Azure Monitor verfügen, um das Feature Log Analytics verwenden zu können. Informationen [zum Erstellen eines](/azure/azure-monitor/learn/quick-create-workspace) Abonnements für Ihre Organisation finden Sie unter Erste Schritte mit einem Log Analytics-Arbeitsbereich.
  
Sie sollten sich bei Bedarf mit der Verwendung des Log Analytics-Ansichts-Designers vertraut machen. Diese Details finden Sie unter Ansichten [in der Protokollanalyse.](/azure/azure-monitor/platform/view-designer)
  
### <a name="related-tasks"></a>Verwandte Aufgaben

1. Nachdem Sie Azure Monitor Log Analytics abonniert haben, erstellen Sie benutzerdefinierte Felder (wie [unter](azure-monitor-deploy.md#Custom_fields)Benutzerdefinierte Felder schildern beschrieben), die zum Analysieren der Informationen erforderlich sind, die von Microsoft Teams Rooms-Konsolen gesendet werden. Dazu gehört auch das Unter Verstehen der Protokolleinträge dokumentierte [JSON-Schema.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Entwickeln Sie eine Microsoft Teams Rooms-Verwaltungsansicht in Log Analytics. Sie können entweder [ein Microsoft Teams Rooms-Dashboard](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) mithilfe der Importmethode erstellen oder [ein Microsoft Teams Rooms-Dashboard manuell erstellen.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Anforderungen an die Konsole für einzelne Microsoft Teams-Räume

Jede Microsoft Teams Rooms-Konsole ist eine App, die auf einem Surface Pro-Gerät im Kioskmodus ausgeführt wird (normalerweise ist sie so konfiguriert, dass sie die einzige App ist, die auf dem Gerät ausgeführt werden kann). Wie bei jeder Windows-App schreibt die Microsoft Teams Rooms-App Ereignisse wie Start- und Hardwarefehler in das Windows-Ereignisprotokoll. Wenn Sie einen Microsoft Monitor-Agent auf Ihrem Microsoft Teams Rooms-Gerät hinzufügen, können diese Ereignisse gesammelt werden. (Details finden Sie unter Verbinden [von Windows-Computern](/azure/azure-monitor/platform/agent-windows) mit dem Protokollanalysedienst in Azure.)
  
## <a name="ongoing-management"></a>Laufende Verwaltung

Während Sie Azure Monitor zum Verwalten Ihrer Microsoft Teams Rooms-Geräte verwenden, müssen Sie die Informationen verstehen, die in den ereignisprotokollen enthalten sind, die von Azure Monitor verwendet werden. Details [zu diesen Integritätsmeldungen](azure-monitor-manage.md#understand-the-log-entries) finden Sie unter Verstehen der Protokolleinträge.
  
### <a name="related-tasks"></a>Verwandte Aufgaben

- Informationen zu den von Microsoft Teams Rooms generierten Benachrichtigungen und deren Behebung (siehe Abschnitt "Verstehen [der Protokolleinträge")](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>Mehr dazu

[Bereitstellen der Verwaltung von Microsoft Teams-Räumen mit Azure Monitor](azure-monitor-deploy.md)
  
[Verwalten von Microsoft Teams Rooms-Geräten mit Azure Monitor](azure-monitor-manage.md)
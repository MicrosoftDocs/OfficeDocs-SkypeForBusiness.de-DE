---
title: Planen Microsoft Teams-Räume der Überwachung mit Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: In diesem Artikel werden Planungsüberlegungen für die Verwendung von Azure Monitor zum überwachen von Microsoft Teams-Räume in Ihrer Skype for Business oder Teams erläutert.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 13c16234773792f9dc394723521224123c5e2141
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015205"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Planen Microsoft Teams-Räume der Überwachung mit Azure Monitor
 
 In diesem Artikel werden Überlegungen zur Planung der Verwendung von Azure Monitor zum Verwalten Microsoft Teams-Räume-Geräten in Ihrer Microsoft Teams oder Skype for Business behandelt.

> [!NOTE]
> Sie können auch [die Integritätsüberwachung Ihrer Teams-Räume](../alerts/device-health-status.md) über Teams Admin Center einrichten.

[Azure Monitor](/azure/azure-monitor/overview) ist eine Sammlung von Überwachungsdiensten, die von Anfang an in der Cloud entwickelt wurden. Anstatt lokale Ressourcen bereitstellen und verwalten zu müssen, werden Azure Monitor-Komponenten vollständig in Azure gehostet. Die Konfiguration ist minimal und kann in wenigen Minuten ausgeführt werden. Mit einigen Anpassungen kann die Überwachung von Microsoft Teams-Räume durch die Bereitstellung von Benachrichtigungen über den Systemzustand oder Fehler für einzelne Raumsysteme unterstützt werden, und es kann bis zur Verwaltung Tausender Von-Raum-Microsoft Teams-Räume.
  
In diesem Artikel werden die bewährten Methoden für Anforderungen, Entwurf/Architektur und Implementierung erläutert, die zum Implementieren der auf Azure Monitor basierenden Überwachung von Microsoft Teams-Räume. Darüber hinaus finden Sie Links zu detaillierten Artikeln zur Implementierung des Azure Monitor for Microsoft Teams-Räume sowie informationen zu wichtigen Referenzinformationen für die fortlaufende Überwachung Microsoft Teams-Räume Räumen.
  
## <a name="functional-overview"></a>Funktionsübersicht

![Diagramm der Microsoft Teams-Räume mit Azure Monitor.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Die Microsoft Teams-Räume-App schreibt Ereignisse in das Windows Ereignisprotokoll. Nach der Installation übergibt ein Microsoft Monitoring-Agent die Informationen an den Azure Monitor-Dienst.
  
Nach der ordnungsgemäßen Konfiguration analysiert Log Analytics die in den Ereignisbeschreibungen eingebettete JSON-Nutzlast, um zu beschreiben, wie Microsoft Teams-Räume und welche Fehler erkannt werden.
  
Ein Administrator, der den Azure Monitor verwendet, kann Benachrichtigungen über Microsoft Teams-Räume erhalten, die offline sind oder App-, Konnektivitäts- oder Hardwarefehler auftreten, und er kann auch wissen, ob ein System neu gestartet werden muss. Jeder Systemstatus wird häufig aktualisiert, sodass sich diese Benachrichtigungen in Der Nähe von Echtzeitupdates befinden.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor-Anforderungen

Sie müssen über ein gültiges Azure-Abonnement für Azure Monitor verfügen, um die Protokollanalysefeatures verwenden zu können. Informationen [zum Erstellen eines](/azure/azure-monitor/learn/quick-create-workspace) Abonnements für Ihre Organisation finden Sie unter Erste Schritte mit einem Protokollanalysearbeitsbereich.
  
Sie sollten sich mit der Verwendung des Protokollanalyseansicht-Designers vertraut machen. Einzelheiten [dazu finden Sie unter](/azure/azure-monitor/platform/view-designer) Ansichten in der Protokollanalyse.
  
### <a name="related-tasks"></a>Verwandte Aufgaben

1. Nachdem Sie die Azure Monitor Log Analytics abonniert haben, erstellen Sie benutzerdefinierte Felder (wie [unter](azure-monitor-deploy.md#Custom_fields)Zuordnung benutzerdefinierter Felder beschrieben), die zum Analysieren der informationen erforderlich sind, die von der Überwachungsprotokollanalyse Microsoft Teams-Räume. Dies umfasst auch das Verständnis des JSON-Schemas, das unter [Grundlegendes zu Protokolleinträgen dokumentiert ist.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Entwickeln Sie eine Microsoft Teams-Räume-Verwaltungsansicht in der Protokollanalyse. Sie können [ein Microsoft Teams-Räume manuell erstellen.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>Individuelle Microsoft Teams-Räume Anforderungen

Microsoft Teams-Räume ist eine App, die auf einem Rechengerät im Kioskmodus ausgeführt wird. Wie jede Windows-App schreibt die Microsoft Teams-Räume-App Ereignisse wie Start- und Hardwarefehler in das Windows-Ereignisprotokoll. Durch das Hinzufügen eines Microsoft Monitor-Agents auf Microsoft Teams-Räume können diese Ereignisse erfasst werden. (Weitere [Verbinden Windows finden Sie unter Installieren von Computern](/azure/azure-monitor/platform/agent-windows) mit dem Protokollanalysedienst in Azure.)
  
## <a name="ongoing-management"></a>Laufende Verwaltung

Während Sie Azure Monitor zum Überwachen Ihrer Microsoft Teams-Räume verwenden, müssen Sie die Informationen verstehen, die in den Ereignisprotokollen enthalten sind, die von Azure Monitor verwendet werden. Details [zu diesen Integritätsmeldungen](azure-monitor-manage.md#understand-the-log-entries) finden Sie unter Verstehen der Protokolleinträge.
  
### <a name="related-tasks"></a>Verwandte Aufgaben

- Verstehen der von der Anmeldung generierten Microsoft Teams-Räume und deren Behebung (siehe Abschnitt "Verstehen [der Protokolleinträge")](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>Mehr dazu

[Bereitstellen Microsoft Teams-Räume Verwaltung mit Azure Monitor](azure-monitor-deploy.md)
  
[Verwalten Microsoft Teams-Räume mit Azure Monitor](azure-monitor-manage.md)

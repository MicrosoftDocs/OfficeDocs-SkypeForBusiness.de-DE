---
title: Planen Microsoft Teams-Räume Verwaltung mit Azure Monitor
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
description: In diesem Artikel werden Überlegungen zur Planung der Verwendung von Azure Monitor zum Verwalten Microsoft Teams-Räume-Geräten in Ihrer Skype for Business oder Teams behandelt.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56b22dddfc475efc83fb5bb3ef5734743b1eb0c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117583"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planen Microsoft Teams-Räume Verwaltung mit Azure Monitor
 
 In diesem Artikel werden Überlegungen zur Planung der Verwendung von Azure Monitor zum Verwalten Microsoft Teams-Räume Geräten in Ihrer Microsoft Teams oder Skype for Business behandelt.
  
[Azure Monitor](/azure/azure-monitor/overview) ist eine Sammlung von Verwaltungsdiensten, die von Anfang an in der Cloud entwickelt wurden. Anstatt lokale Ressourcen bereitstellen und verwalten zu müssen, werden Azure Monitor-Komponenten vollständig in Azure gehostet. Die Konfiguration ist minimal, und Sie können in wenigen Minuten buchstäblich im Betrieb sein. Mit einigen Anpassungsarbeiten kann die Verwaltung von Microsoft Teams-Räume-Konferenzsystemen durch die Bereitstellung von Echtzeitbenachrichtigungen über den Systemzustand oder Fehler für einzelne Raumsysteme unterstützt werden, und es kann potenziell bis zur Verwaltung tausender Microsoft Teams-Räume-Konferenzräume skaliert werden.
  
Dieser Artikel enthält eine Erläuterung der bewährten Methoden für Anforderungen, Entwurf/Architektur und Implementierung, die für die Implementierung der auf Azure Monitor basierenden Verwaltung von Microsoft Teams-Räume-Konferenzgeräten erforderlich sind, und enthält Links zu detaillierten Artikeln zur Implementierung des Azure Monitor für Microsoft Teams-Räume sowie Informationen zu wichtigen Referenzinformationen zur laufenden Überwachung von Microsoft Teams-Räume-Räumen. 
  
## <a name="functional-overview"></a>Funktionsübersicht

![Diagramm der Microsoft Teams-Räume mit Azure Monitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Die Microsoft Teams-Räume-App auf dem Konsolengerät schreibt Ereignisse in das Windows Ereignisprotokoll. Nach der Installation übergibt ein Microsoft Monitoring-Agent die Informationen an den Azure Monitor-Dienst. 
  
Nach der ordnungsgemäßen Konfiguration analysiert Log Analytics die in die Ereignisbeschreibungen eingebettete JSON-Nutzlast, um zu beschreiben, wie die einzelnen Microsoft Teams-Räume funktionieren und welche Fehler erkannt werden. 
  
Ein Administrator, der Azure Monitor verwendet, kann Benachrichtigungen über Microsoft Teams-Räume-Systeme erhalten, die offline sind oder App-, Konnektivitäts- oder Hardwarefehler auftreten, und er weiß, ob ein System neu gestartet werden muss. Jeder Systemstatus wird häufig aktualisiert, sodass sich diese Benachrichtigungen in Der Nähe von Echtzeitupdates befinden.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor-Anforderungen

Sie müssen über ein gültiges Azure-Abonnement für Azure Monitor verfügen, um das Protokollanalysefeature verwenden zu können. Informationen zum Erstellen eines Abonnements [für Ihre Organisation](/azure/azure-monitor/learn/quick-create-workspace) finden Sie unter Erste Schritte mit einem Protokollanalysearbeitsbereich.
  
Sie sollten sich bei Bedarf mit der Verwendung des Log Analytics View-Designers vertraut machen. Einzelheiten [dazu finden Sie unter](/azure/azure-monitor/platform/view-designer) Ansichten in der Protokollanalyse.
  
### <a name="related-tasks"></a>Verwandte Aufgaben

1. Nachdem Sie die Azure Monitor Log Analytics abonniert haben, erstellen Sie benutzerdefinierte Felder (wie [unter](azure-monitor-deploy.md#Custom_fields)Zuordnung benutzerdefinierter Felder beschrieben), die zum Analysieren der Informationen erforderlich sind, die von den Microsoft Teams-Räume gesendet werden. Dies umfasst auch das Verständnis des JSON-Schemas, das unter [Grundlegendes zu Protokolleinträgen dokumentiert ist.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Entwickeln Sie eine Microsoft Teams-Räume-Verwaltungsansicht in der Protokollanalyse. Sie können entweder [ein Microsoft Teams-Räume-Dashboard mithilfe](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) der Importmethode erstellen oder manuell [ein Microsoft Teams-Räume erstellen.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Anforderungen Microsoft Teams-Räume einzelnen Konsolen

Bei jeder Microsoft Teams-Räume handelt es sich um eine App, die auf einem Surface Pro-Gerät im Kioskmodus ausgeführt wird (normalerweise ist sie so konfiguriert, dass sie die einzige App ist, die auf dem Gerät ausgeführt werden kann). Wie jede Windows-App schreibt die Microsoft Teams-Räume-App Ereignisse wie Start- und Hardwarefehler in das Windows-Ereignisprotokoll. Wenn Sie einen Microsoft Monitor-Agent auf Ihrem Microsoft Teams-Räume-Gerät hinzufügen, können diese Ereignisse erfasst werden. (Weitere Verbinden Windows finden Sie unter Installieren von Computern mit dem [Protokollanalysedienst in Azure.)](/azure/azure-monitor/platform/agent-windows)
  
## <a name="ongoing-management"></a>Laufende Verwaltung

Während Sie Azure Monitor zum Verwalten Ihrer Microsoft Teams-Räume-Geräte verwenden, müssen Sie die Informationen verstehen, die in den Ereignisprotokollen enthalten sind, die von Azure Monitor verwendet werden. Details [zu diesen Integritätsmeldungen](azure-monitor-manage.md#understand-the-log-entries) finden Sie unter Verstehen der Protokolleinträge.
  
### <a name="related-tasks"></a>Verwandte Aufgaben

- Hier erhalten Sie Informationen zu den von Microsoft Teams-Räume generierten Benachrichtigungen und deren Behebung (siehe Abschnitt "Verstehen [der Protokolleinträge")](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>Mehr dazu

[Bereitstellen Microsoft Teams-Räume Verwaltung mit Azure Monitor](azure-monitor-deploy.md)
  
[Verwalten Microsoft Teams-Räume mit Azure Monitor](azure-monitor-manage.md)
---
title: Planen Microsoft Teams-Räume Überwachung mit Azure Monitor
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
- Teams_ITAdmin_Rooms
description: In diesem Artikel werden Planungsüberlegungen für die Verwendung von Azure Monitor zum Überwachen Microsoft Teams-Räume in Ihrer Skype for Business- oder Teams-Implementierung erläutert.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac3ac3af4e4f162238af0e9bf38c45569302fdfb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269570"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Planen Microsoft Teams-Räume Überwachung mit Azure Monitor
 
 In diesem Artikel werden Planungsüberlegungen für die Verwendung von Azure Monitor zum Verwalten Microsoft Teams-Räume Geräten in Microsoft Teams oder Skype for Business Implementierung erläutert.

> [!NOTE]
> Sie können auch die [Integritätsüberwachung von Teams-Räume](../alerts/device-health-status.md) mithilfe des Teams Admin Centers einrichten.

[Azure Monitor](/azure/azure-monitor/overview) ist eine Sammlung von Überwachungsdiensten, die von Anfang an in der Cloud entwickelt wurden. Anstatt lokale Ressourcen bereitzustellen und zu verwalten, werden Azure Monitor-Komponenten vollständig in Azure gehostet. Die Konfiguration ist minimal, und Sie können in wenigen Minuten betriebsbereit sein. Mit einigen Anpassungsarbeiten kann es bei der Überwachung Microsoft Teams-Räume helfen, indem es Benachrichtigungen über den Systemstatus oder Fehler für einzelne Raumsysteme bereitstellt, und es kann bis zur Verwaltung von Tausenden von Microsoft Teams-Räume skaliert werden.
  
Dieser Artikel enthält eine Erläuterung der Anforderungen, des Entwurfs/der Architektur und der bewährten Methoden für die Implementierung der Azure Monitor-basierten Überwachung von Microsoft Teams-Räume. Es enthält außerdem Links zu detaillierten Artikeln zur Implementierung von Azure Monitor für Microsoft Teams-Räume und wichtige Referenzinformationen für die fortlaufende Überwachung von Microsoft Teams-Räume Räumen.
  
## <a name="functional-overview"></a>Funktionsübersicht

![Diagramm der Microsoft Teams-Räume-Verwaltung mithilfe von Azure Monitor.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Die Microsoft Teams-Räume-App schreibt Ereignisse in das Windows-Ereignisprotokoll. Nach der Installation übergibt ein Microsoft Monitoring-Agent die Informationen an den Azure Monitor-Dienst.
  
Nach der ordnungsgemäßen Konfiguration analysiert Log Analytics die in die Ereignisbeschreibungen eingebettete JSON-Nutzlast, um zu beschreiben, wie Microsoft Teams-Räume funktioniert und welche Fehler erkannt werden.
  
Ein Administrator, der Azure Monitor verwendet, kann Benachrichtigungen über Microsoft Teams-Räume erhalten, die offline sind oder App-, Konnektivitäts- oder Hardwarefehler haben, und wissen, ob ein System neu gestartet werden muss. Jeder Systemstatus wird häufig aktualisiert, sodass diese Benachrichtigungen in der Nähe von Echtzeitupdates sind.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor-Anforderungen

Sie müssen über ein gültiges Azure-Abonnement für Azure Monitor verfügen, um Log Analytics-Features verwenden zu können. Informationen zum Erstellen eines Abonnements für Ihre Organisation finden Sie unter ["Erste Schritte mit einem Log Analytics-Arbeitsbereich](/azure/azure-monitor/learn/quick-create-workspace) ".
  
Sie sollten sich mit der Verwendung des Log Analytics-Ansichts-Designers vertraut machen. Diese Details finden Sie [unter Ansichten in Log Analytics](/azure/azure-monitor/platform/view-designer) .
  
### <a name="related-tasks"></a>Verwandte Aufgaben

1. Nachdem Sie Azure Monitor Log Analytics abonniert haben, erstellen Sie benutzerdefinierte Felder (wie unter ["Benutzerdefinierte Felder](azure-monitor-deploy.md#Custom_fields) zuordnen" beschrieben), die zum Analysieren der Informationen erforderlich sind, die von Microsoft Teams-Räume gesendet werden. Dies umfasst das Verständnis des JSON-Schemas, [das in "Grundlegendes zu den Protokolleinträgen](azure-monitor-manage.md#understand-the-log-entries)" dokumentiert ist.
    
2. Entwickeln Sie eine Microsoft Teams-Räume Verwaltungsansicht in Log Analytics. Sie können [ein Microsoft Teams-Räume-Dashboard manuell erstellen](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>Individuelle Microsoft Teams-Räume Anforderungen

Microsoft Teams-Räume ist eine App, die auf einem Computegerät im Kioskmodus ausgeführt wird. Wie bei jeder Windows-App schreibt die Microsoft Teams-Räume-App Ereignisse wie Start- und Hardwarefehler in das Windows-Ereignisprotokoll. Durch das Hinzufügen eines Microsoft Monitor-Agents auf Microsoft Teams-Räume können diese Ereignisse erfasst werden. (Ausführliche Informationen finden Sie [unter Verbinden von Windows-Computern mit dem Log Analytics-Dienst in Azure](/azure/azure-monitor/platform/agent-windows) .)
  
## <a name="ongoing-management"></a>Laufende Verwaltung

Während Sie Azure Monitor verwenden, um Ihre Microsoft Teams-Räume zu überwachen, müssen Sie die Informationen in den von Azure Monitor verwendeten Ereignisprotokollen verstehen. Ausführliche Informationen zu diesen [Integritätsmeldungen finden Sie unter "Grundlegendes zu den Protokolleinträgen](azure-monitor-manage.md#understand-the-log-entries) ".
  
### <a name="related-tasks"></a>Verwandte Aufgaben

- Grundlegendes zu den von Microsoft Teams-Räume generierten Warnungen und deren Behebung (siehe Abschnitt "[Grundlegendes zu den Protokolleinträgen](azure-monitor-manage.md#understand-the-log-entries)")
    
## <a name="see-also"></a>Siehe auch

[Bereitstellen Microsoft Teams-Räume-Verwaltung mit Azure Monitor](azure-monitor-deploy.md)
  
[Verwalten Microsoft Teams-Räume Geräte mit Azure Monitor](azure-monitor-manage.md)

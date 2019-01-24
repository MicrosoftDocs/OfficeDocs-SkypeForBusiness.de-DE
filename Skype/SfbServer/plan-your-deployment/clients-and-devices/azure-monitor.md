---
title: Planen der Verwaltung von Skype Raum Systemen v2 mit Azure Monitor
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: In diesem Artikel werden planungsüberlegungen für die Verwendung von Azure Monitor Skype Raum Systemen v2 Geräte in Ihrer Skype für Business oder Teams Implementierung verwalten.
ms.openlocfilehash: 53f77f1353668e4887a6ff41efd040dc8f418c7e
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "29448462"
---
# <a name="plan-skype-room-systems-v2-management-with-azure-monitor"></a>Planen der Verwaltung von Skype Raum Systemen v2 mit Azure Monitor
 
 In diesem Artikel werden planungsüberlegungen für die Verwendung von Azure Monitor Skype Raum Systemen v2 Geräte in Ihrer Skype für die Implementierung von Business Server verwalten.
  
[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) ist eine Auflistung von Rights Management Services, die in der Cloud ab dem Anfang entwickelt wurden. Statt bereitstellen und Verwalten von lokalen Ressourcen, werden Azure Monitor Komponenten vollständig in Azure gehostet. Konfiguration ist gering, und Sie können ausgeführt werden und als solches innerhalb weniger Minuten. Einige Arbeit Anpassung können sie bei der Verwaltung von Skype Raum v2 Conferencing-basierte Systeme durch Bereitstellen der Systemintegrität oder Fehler in Echtzeit Benachrichtigungen für einzelne Raum Systeme hilfreich, und es kann potenziell vertikales Skalieren zur Verwaltung von Tausende von Skype Raum Systemen Konferenzräume v2.
  
Dieser Artikel enthält eine Erörterung der Anforderungen, Design-Architektur und Implementierung bewährte Methoden für die Implementierung von Azure Monitor basierend Verwaltung von Skype Raum Systemen v2 Konferenz Geräten und enthält Links zu ausführlichen Artikeln auf Implementieren von Azure Monitor für Skype Raum Systemen v2 und kritische Referenzinformationen für die laufende Überwachung der Skype Raum Systemen v2 Chatrooms. 
  
## <a name="functional-overview"></a>Funktionsübersicht

![Diagramm der SRS-Verwaltung mithilfe von Azure Monitor](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Die Skype Raum Systemen v2 app auf dem Gerät Konsole schreibt Ereignisse in der Windows-Ereignisprotokoll. Ein Microsoft-Monitoring-Agent, einmal installiert, übergibt die Informationen an Azure-Überwachungsdienst. 
  
Einmal ordnungsgemäß konfiguriert, Log Analytics analysiert die JSON-Nutzlast eingebettet in den Ereignisdetails Beschreibungen der wird beschrieben, wie jedes Skype Raum Systemen v2 System funktioniert und welche Fehler erkannt werden. 
  
Ein Administrator mit Azure Systemmonitor sind finde Benachrichtigungen über Skype Raum v2-basierte Systeme, die offline sind oder app, Diensten oder Hardwarefehler auftritt als auch feststellen, ob ein System muss neu gestartet werden. Jede Systemstatus wird regelmäßig aktualisiert, sodass diese Benachrichtigungen nahezu in Echtzeit Updates sind.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor-Anforderungen

Sie benötigen ein gültiges Azure-Abonnement für Azure Monitor Protokoll Analytics-Feature verwenden. Unter Erste Schritte mit einem Log Analytics-Arbeitsbereich erfahren Sie, wie Sie ein Abonnement für Ihre Organisation erstellen.
  
Sie sollten sich nach Bedarf zur Verwendung von Log Analytics Ansichts-Designer vertraut machen. Diese Details finden Sie unter [Ansichten im Protokoll Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) .
  
### <a name="related-tasks"></a>Verwandte Aufgaben

1. Nachdem Azure Monitor Protokoll Analytics abonniert haben, Erstellen der benutzerdefinierten Felder (wie in [benutzerdefinierte Felder zuordnen](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)beschrieben) benötigt, um die Informationen zu analysieren, die von Skype Raum Systemen v2 Konsolen gesendet werden soll. Dazu gehören Grundlegendes zum Schema der JSON in [die Protokolleinträge verstehen](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)dokumentiert.
    
2. Entwickeln einer Skype Raum Systemen v2 Management-Ansicht im Protokoll Analytics. Sie können entweder [eine Skype Raum Systemen v2 Dashboard mithilfe der Importmethode erstellen](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method) ), oder [Erstellen Sie manuell einen Skype Raum Systemen v2 Dashboard](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-manually).
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a>Einzelne Skype Raum Systemen v2 Konsole Anforderungen

Jede Skype Raum Systemen v2-Konsole ist eine app auf einem Surface Pro Gerät im Kioskmodus ausgeführt (normalerweise konfiguriert ist die einzige app handeln, die auf dem Gerät ausgeführt werden können). Wie bei jeder Windows-app schreibt die Skype Raum Systemen v2 app Ereignisse wie beim Starten und Hardware Fehlern im Windows-Ereignisprotokoll. Hinzufügen eines Microsoft Monitor-Agents auf dem Gerät des Skype Raum Systemen v2 ermöglicht diese Ereignisse gesammelt werden. (Einzelheiten finden Sie unter [mit dem Protokoll Analytics-Dienst in Azure-Computern mit Windows verbinden](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) .)
  
## <a name="ongoing-management"></a>Laufende Verwaltung

Bei Verwendung von Azure Monitor Ihrer Skype Raum Systemen v2-Geräte verwalten, müssen Sie verstehen, die Informationen in den Ereignisprotokollen von Azure Monitor verwendet. Finden Sie auf diese Nachrichten Health Einzelheiten in [die Protokolleinträge verstehen](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries) .
  
### <a name="related-tasks"></a>Verwandte Aufgaben

- Verstehen von Skype Raum Systemen v2 und zu deren Behebung (finden Sie im Abschnitt [zu verstehen der Protokolleinträge](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)) generierte Benachrichtigungen
    
## <a name="see-also"></a>Siehe auch

[Bereitstellen von Skype Raum v2 systemverwaltung mit Azure Monitor](../../deploy/deploy-clients/azure-monitor.md)
  
[Verwalten von Skype Raum Systemen v2 Geräte mit Azure Monitor](../../manage/skype-room-systems-v2/azure-monitor.md)
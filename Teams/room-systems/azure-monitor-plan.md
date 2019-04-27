---
title: Planen der Verwaltung von Microsoft-Teams Chatrooms mit Azure Monitor
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection: M365-voice
description: In diesem Artikel werden planungsüberlegungen für die Verwendung von Azure Monitor zum Verwalten von Microsoft-Teams Chatrooms Geräte in Ihrer Skype für Business oder Teams Implementierung.
ms.openlocfilehash: 67a74d0bd02465d1a84856238e3e65a049b23ab4
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362834"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Planen der Verwaltung von Microsoft-Teams Chatrooms mit Azure Monitor
 
 In diesem Artikel werden planungsüberlegungen für die Verwendung von Azure Monitor zum Verwalten von Microsoft-Teams Chatrooms Geräte in Ihrem Microsoft-Teams oder Skype für Business-Implementierung.
  
[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) ist eine Auflistung von Rights Management Services, die in der Cloud ab dem Anfang entwickelt wurden. Statt bereitstellen und Verwalten von lokalen Ressourcen, werden Azure Monitor Komponenten vollständig in Azure gehostet. Konfiguration ist gering, und Sie können ausgeführt werden und als solches innerhalb weniger Minuten. Mit einigen Arbeit Anpassung können sie bei der Verwaltung von Microsoft-Teams Chatrooms Videokonferenzsysteme durch Bereitstellen der Systemintegrität oder Fehler in Echtzeit Benachrichtigungen für einzelne Raum Systeme hilfreich, und es kann potenziell vertikales Skalieren zur Verwaltung von Tausende von Microsoft-Teams Konferenzräume Chatrooms.
  
Dieser Artikel enthält eine Erörterung der Anforderungen, Design-Architektur und Implementierung bewährte Methoden für die Implementierung von Azure Monitor basierend Verwaltung von Microsoft-Teams Chatrooms Konferenz Geräten und enthält Links zu ausführlichen Artikeln auf Implementieren von Azure Monitor für Microsoft-Teams Rooms und kritische Referenzinformationen für die laufende Überwachung der Microsoft-Teams Chatrooms Chatrooms. 
  
## <a name="functional-overview"></a>Funktionsübersicht

![Diagramm der Microsoft-Teams Chatrooms Management mit Azure Systemmonitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Die Microsoft-Teams Chatrooms app auf dem Gerät Konsole schreibt Ereignisse in der Windows-Ereignisprotokoll. Ein Microsoft-Monitoring-Agent, einmal installiert, übergibt die Informationen an Azure-Überwachungsdienst. 
  
Einmal ordnungsgemäß konfiguriert, Log Analytics analysiert die JSON-Nutzlast eingebettet in den Ereignisdetails Beschreibungen der wird beschrieben, wie jede Microsoft-Teams Chatrooms System funktioniert und welche Fehler erkannt werden. 
  
Ein Administrator mit Azure Systemmonitor sind finde Benachrichtigungen von Microsoft-Teams Räume-Systemen, die offline sind oder app, Diensten oder Hardwarefehler auftritt als auch feststellen, ob ein System muss neu gestartet werden. Jede Systemstatus wird regelmäßig aktualisiert, sodass diese Benachrichtigungen nahezu in Echtzeit Updates sind.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor-Anforderungen

Sie benötigen ein gültiges Azure-Abonnement für Azure Monitor Protokoll Analytics-Feature verwenden. Finden Sie unter [Erste Schritte mit einem Protokoll Analytics Arbeitsbereich](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) , um ein Abonnement für Ihre Organisation zu erstellen.
  
Sie sollten sich nach Bedarf zur Verwendung von Log Analytics Ansichts-Designer vertraut machen. Diese Details finden Sie unter [Ansichten im Protokoll Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) .
  
### <a name="related-tasks"></a>Verwandte Aufgaben

1. Nachdem Azure Monitor Protokoll Analytics abonniert haben, Erstellen der benutzerdefinierten Felder (wie in [benutzerdefinierte Felder zuordnen](azure-monitor-deploy.md#Custom_fields)beschrieben) benötigt, um die Informationen zu analysieren, die von Microsoft-Teams Chatrooms Konsolen gesendet werden soll. Dazu gehören Grundlegendes zum Schema der JSON in [die Protokolleinträge verstehen](azure-monitor-manage.md#understand-the-log-entries)dokumentiert.
    
2. Entwickeln einer Microsoft-Teams Chatrooms Management-Ansicht im Protokoll Analytics. Sie können entweder [Erstellen Sie ein Dashboard Microsoft Teams Chatrooms mithilfe der Importmethode](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) oder [ein Dashboard Microsoft Teams Chatrooms manuell erstellen](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Einzelne Teams Räume-MMC-Anforderungen

Jede Microsoft-Teams Räume-Konsole ist eine app auf einem Surface Pro Gerät im Kioskmodus ausgeführt (normalerweise konfiguriert ist die einzige app handeln, die auf dem Gerät ausgeführt werden können). Wie bei jeder Windows-app schreibt die Microsoft-Teams Chatrooms app Ereignisse wie beim Starten und Hardware Fehlern im Windows-Ereignisprotokoll. Hinzufügen eines Microsoft Monitor-Agents auf dem Gerät Microsoft Teams Chatrooms kann diese Ereignisse gesammelt werden. (Einzelheiten finden Sie unter [mit dem Protokoll Analytics-Dienst in Azure-Computern mit Windows verbinden](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) .)
  
## <a name="ongoing-management"></a>Laufende Verwaltung

Bei Verwendung von Azure Monitor Ihrer Microsoft Teams Räume-Geräte verwalten, müssen Sie verstehen, die Informationen in den Ereignisprotokollen von Azure Monitor verwendet. Finden Sie auf diese Nachrichten Health Einzelheiten in [die Protokolleinträge verstehen](azure-monitor-manage.md#understand-the-log-entries) .
  
### <a name="related-tasks"></a>Verwandte Aufgaben

- Grundlegendes zu den vom Microsoft-Teams Rooms und zu deren Behebung (finden Sie im Abschnitt [zu verstehen der Protokolleinträge](azure-monitor-manage.md#understand-the-log-entries)) generierten Warnungen
    
## <a name="see-also"></a>Siehe auch

[Bereitstellen von Microsoft-Teams Chatrooms Management mit Azure Monitor](azure-monitor-deploy.md)
  
[Verwalten von Microsoft-Teams Chatrooms Geräte mit Azure Monitor](azure-monitor-manage.md)
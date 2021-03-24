---
title: Planen der Anrufdatenconnector-| Hybridanalyse für die Überwachung des Anrufqualitätsdashboards
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Übersicht über die Verwendung von Skype for Business Online-Telemetrietools zum Überwachen einer lokalen Implementierung in einem Hybridszenario.
ms.openlocfilehash: f47f0969d102408299678842b18bb503eaf6aea0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110551"
---
# <a name="plan-call-data-connector"></a>Planen des Anrufdatenconnectors

## <a name="overview"></a>Übersicht

In diesem Thema werden Vorteile, Planungsüberlegungen und Anforderungen für die Implementierung von Skype for Business Server Call Data Connector beschrieben. Weitere Informationen zum Konfigurieren des Anrufdatenconnector finden Sie unter [Configure Call Data Connector](configure-call-data-connector.md).


Der Anrufdatenconnector vereinfacht die Anrufüberwachung in einer Hybridumgebung erheblich, da Sie nicht mehr verschiedene Gruppen von lokalen und Onlinetools verwenden müssen, um die Anrufqualität aller Benutzer zu überwachen. Unabhängig davon, ob Ihre Benutzer lokal oder online zu Hause sind, können Sie wählen, ob Sie die Anrufqualität für Ihre gesamte Organisation online anzeigen möchten.

Mit dem Anrufdatenconnector können Sie die folgenden Aufgaben mit einem einzigen Toolset ausführen:

- Überwachen Sie Ihre Benutzeroberfläche in Microsoft Teams, Skype for Business Online und Skype for Business Server.

- Anzeigen und Beheben von Problemen in Ihrem Netzwerk.

- Weisen Sie Helpdesk- und Administratorrollen für die Anrufanalyse zu, damit Sie Helpdeskmitarbeitern das Anzeigen und Beheben ihrer Aufgabenbereiche ermöglichen können.

Mit dem Anrufdatenconnector gibt Skype for Business Server Anrufdaten an den Clouddienst weiter, sodass Sie die Skype for Business Online Call Analytics (CA) und die Tools für das Anrufqualitätsdashboard (Call Quality Dashboard, CQD) nutzen können, wie im folgenden Diagramm dargestellt:

![SfB Cloud Voicemail](../../sfbserver2019/media/call-data-connector-plan-1.png)

Der Server pusht sowohl QoE-Daten (Quality of Experience) als auch Daten zur Aufzeichnung von Anrufdetails (Call Detail Recording, CDR) an den Onlinedienst.

Mit den Tools Call Analytics und CQD können Sie die Qualität von Anrufen überwachen und Verbindungsprobleme mit Microsoft Teams und Skype for Business-Diensten wie folgt behandeln:

- Die Anrufanalyse konzentriert sich auf Qualitätsprobleme bei bestimmten Anrufen. Es enthält detaillierte Informationen zu Anrufen und Besprechungen für jeden Benutzer in einem Skype for Business-Konto.  Mit der Anrufanalyse können Sie einem Helpdeskoperator Berechtigungen zuweisen, der Anrufe dann überwachen kann, ohne Zugriff auf das restliche Skype for Business Admin Center zu haben.

- Das Dashboard für die Anrufqualität konzentriert sich auf die Netzwerkleistung und Probleme in einer Organisation. Skype for Business-Administratoren und Netzwerktechniker verwenden dieses Tool zur Problembehandlung und Optimierung der Netzwerkleistung.

Weitere Informationen finden Sie unter [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).

Natürlich sollten Sie einige Daten zur Anrufqualität lokal speichern. Dies kann beispielsweise der Fall sein, wenn Sie eine Drittanbieterlösung mit angepassten Berichten und Workflows verwenden.  Mit dem Anrufdatenconnector können Sie das Senden von Daten an den Onlinedienst konfigurieren und gleichzeitig eine Kopie der Daten auf ihrem lokalen Server speichern, wie im folgenden Diagramm dargestellt:

![SfB Cloud Voicemail](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird davon ausgegangen, dass Skype for Business Server bereits in einer unterstützten Topologie bereitgestellt ist.  Weitere Informationen zum Bereitstellen von Skype for Business Server und unterstützten Topologien finden Sie unter [Topology Basics](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md). Zum Konfigurieren des Anrufdatenconnector müssen Sie:

- Aktivieren Sie die Hybridkonnektivität. Wenn Sie Skype for Business Server bereits bereitgestellt haben und Den Anrufdatenconnector aktivieren möchten, müssen Sie sicherstellen, dass eine Hybridkonnektivität zwischen Ihren lokalen und Onlineumgebungen eingerichtet ist. Dies wird manchmal als geteilte Domänenkonfiguration bezeichnet.

   Weitere Informationen finden Sie unter [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) und [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- Authentifizieren Sie sich bei Ihrer Microsoft 365- oder Office 365-Organisation, und stellen Sie sicher, dass Die folgenden Rollen aktiviert sind:

  - Skype for Business Server-Administrator
  - Globaler Microsoft 365- oder Office 365-Administrator

- Wenn Sie dies noch nicht getan haben, aktivieren Sie das Anrufqualitätsdashboard, wie unter Aktivieren und Verwenden des Anrufqualitätsdashboards für Microsoft Teams und [Skype for Business Online beschrieben.](/microsoftteams/turning-on-and-using-call-quality-dashboard)

- Aktivieren Sie den Front-End-Pool für die Überwachung mit lokalen LCSCdr- und QoEMetrics-Datenbanken. Ohne diesen Parameter verfügen Anrufdatenconnector nicht über Metrikdaten, mit deren Hilfe sie arbeiten können.

> [!IMPORTANT]
> Der Anrufdatenconnector funktioniert nicht, wenn die Überwachung im Front-End-Pool nicht aktiviert ist.

- Ordnungsgemäß konfigurierte [Server-zu-Server-Authentifizierung](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md). 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Vergleich von Lokalen und Onlineberichten zum Anrufqualitätsdashboard (CQD)

| Featureberichte | Skype for Business Online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Metrik für die Anwendungsfreigabe |Ja | Eingeschränkt |
| Informationen zum Erstellen von Kunden| Ja | Ja |
| Drilldownanalysen | Ja | Nein |
| Metriken zur Medienzuverlässigkeit | Ja | Eingeschränkt |
| Out-of-the-Box-Berichte | Ja | Ja |
| Übersicht über Berichte | Ja | Nein |
| Berichte pro Benutzer | Ja | Ja |
| Anpassung des Berichtssatzs <br> (Berichte hinzufügen, löschen, ändern) | Ja | Ja |
| Videobasierte Bildschirmfreigabemetriken | Ja | Nein |
| Daten-APIs für programmgesteuerten Zugriff <br> zu CQD | Nein | Ja |
||||
---
title: Plan Call Data Connector | Anrufqualität Dashboard Monitoring Hybrid Analytics
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Übersicht über die Verwendung Skype for Business Online Telemetrie-Tools zum Überwachen einer lokalen Implementierung in einem Hybrid Szenario.
ms.openlocfilehash: dc129ed99e1ed69e3faf5d2a7b6923f818c482eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160589"
---
# <a name="plan-call-data-connector"></a>Planen des Connectors für die Anrufdaten

## <a name="overview"></a>Übersicht

In diesem Thema werden die Vorteile, Planungsüberlegungen und Anforderungen für die Implementierung Skype for Business Server Anrufdaten-Konnektors beschrieben. Weitere Informationen zum Konfigurieren des Anruf datenkonnektors finden Sie unter [configure Call Data Connector](configure-call-data-connector.md).

> [!NOTE]
> Im öffentlichen Preview-Release steht nur das anrufanalyse-Dashboard zur Verfügung.

Call Data Connector vereinfacht die Anrufüberwachung in einer Hybridumgebung erheblich, da Sie nicht mehr unterschiedliche Sätze von lokalen und Online Tools verwenden müssen, um die Anrufqualität Ihrer Benutzer zu überwachen. Unabhängig davon, ob Ihre Benutzer lokal oder online verwaltet werden, können Sie die Anrufqualität für Ihre gesamte Organisation online anzeigen.

Mit dem Call Data Connector können Sie die folgenden Aufgaben mithilfe eines einzelnen Toolsets ausführen:

- Überwachen Sie die Benutzeroberfläche in Microsoft Teams, Skype for Business Online und Skype for Business Server.

- Anzeigen und Beheben von Problemen in Ihrem Netzwerk

- Zuweisen von Helpdesk-und Administratorrollen für die anrufanalyse, sodass Sie Helpdesk-Mitarbeitern die Möglichkeit geben können, ihre Zuständigkeitsbereiche anzuzeigen und zu beheben.

Mit dem Anrufdaten-Konnektor legt das Skype for Business Server Anrufdaten an den clouddienst weiter, damit Sie die Tools für die Skype for Business Online Call Analytics (ca) und CQD (Call Quality Dashboard) nutzen können, wie im folgenden Diagramm dargestellt:

![SFB Cloud Voicemail](../../sfbserver2019/media/call-data-connector-plan-1.png)

Der Server drückt sowohl QoE-(Quality of Experience) als auch KDS-Daten (Call Detail Recording) an den Onlinedienst aus.

Mit den Tools für die anrufanalyse und das CQD können Sie die Qualität von Anrufen überwachen und Verbindungsprobleme mit Microsoft Teams und Skype for Business Diensten wie folgt beheben:

- Die anrufanalyse konzentriert sich auf Qualitätsprobleme mit bestimmten anrufen. Es werden detaillierte Informationen zu anrufen und Besprechungen für jeden Benutzer in einem Skype for Business Konto angezeigt.  Mit der anrufanalyse können Sie einer Helpdesk-Vermittlungsstelle Berechtigungen zuweisen, die Anrufe dann überwachen können, ohne Zugriff auf den Rest des Skype for Business admin Centers zu haben.

- Das Dashboard für die Anrufqualität konzentriert sich auf die Netzwerkleistung und die Probleme in einer Organisation. Skype for Business Administratoren und Netzwerktechniker verwenden dieses Tool zur Problembehandlung und Optimierung der Netzwerkleistung.

Weitere Informationen finden Sie unter [anrufanalyse und Anruf Qualitäts Dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).

Natürlich möchten Sie möglicherweise einige Daten zur Anrufqualität lokal speichern. Dies kann beispielsweise der Fall sein, wenn Sie eine Drittanbieterlösung mit angepassten Berichten und Workflows verwenden.  Mit Call Data Connector können Sie das Senden von Daten an den Onlinedienst konfigurieren und gleichzeitig eine Kopie der Daten auf dem lokalen Server speichern, wie im folgenden Diagramm dargestellt:

![SFB Cloud Voicemail](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Voraussetzungen

Bei den folgenden Anforderungen wird vorausgesetzt, dass Sie bereits Skype for Business Server in einer unterstützten Topologie bereitgestellt haben.  Weitere Informationen zum Bereitstellen von Skype for Business Server und unterstützten Topologien finden Sie unter [Topologie Basics](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics). Zum Konfigurieren von Call Data Connector müssen Sie Folgendes tun:

- Aktivieren Sie die Hybrid Konnektivität. Wenn Sie bereits Skype for Business Server bereitgestellt haben und den Anruf Datenkonnektor aktivieren möchten, müssen Sie sicherstellen, dass Sie eine hybride Konnektivität zwischen Ihren lokalen und Online-Umgebungen eingerichtet haben. Dies wird manchmal als geteilte Domänenkonfiguration bezeichnet.

   Weitere Informationen finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Office 365](plan-hybrid-connectivity.md) und [Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Office 365](configure-hybrid-connectivity.md).

- Authentifizieren Sie sich bei Ihrem Office 365 Mandanten, und stellen Sie sicher, dass die folgenden Rollen aktiviert sind:

  - Skype for Business Server Administrator
  - Office 365 globaler Administrator

- Wenn Sie dies noch nicht getan haben, aktivieren Sie das Anruf qualitätsdashboard wie unter [aktivieren und Verwenden des Anruf Qualitäts Dashboards für Microsoft Teams und Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard)beschrieben.

- Aktivieren Sie den Front-End-Pool für die Überwachung mit lokalen LCSCdr-und QoEMetrics-Datenbanken. Ohne diesen Parameter verfügt der Anrufdaten-Konnektor nicht über Metrikdaten, mit denen Sie arbeiten können.

> [!IMPORTANT]
> Der Anrufdaten-Konnektor funktioniert nicht, wenn die Überwachung im Front-End-Pool nicht aktiviert ist.

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Vergleich von CQD-Berichten (on-premises und Online Call Quality Dashboard)

| Funktions Berichte | Skype for Business Online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Metrik für die Anwendungsfreigabe |Ja | Beschränkt |
| Informationen zum Kunden Gebäude| Ja | Ja |
| Drilldown-Analyse | Ja | Nein |
| Metriken für die Medien Zuverlässigkeit | Ja | Beschränkt |
| Out-of-the-Box-Berichte | Ja | Ja |
| Übersicht Berichte | Ja | Nein |
| Berichte pro Benutzer | Ja | Ja |
| Anpassung des Berichtssatzes <br> (hinzufügen, löschen, Ändern von Berichten) | Ja | Ja |
| Metriken für die Video basierte Bildschirmfreigabe | Ja | Nein |
| Daten-APIs für den programmatischen Zugriff <br> zu CQD | Nein | Ja |
||||

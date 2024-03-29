---
title: Plan Call Data Connector | Überwachung der Hybridanalyse des Anrufqualitätsdashboards
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Übersicht über die Verwendung Skype for Business Online-Telemetrietools zur Überwachung einer lokalen Implementierung in einem Hybridszenario.
ms.openlocfilehash: 2584453ca120c3dce9b4b0ce432e244cd15ec53b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013329"
---
# <a name="plan-call-data-connector"></a>Planen des Anrufdatenconnectors

## <a name="overview"></a>Übersicht

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In diesem Thema werden Vorteile, Planungsüberlegungen und Anforderungen für die Implementierung Skype for Business Server Anrufdatenkonnektors beschrieben. Weitere Informationen zum Konfigurieren des Anrufdatenkonnektors finden Sie unter [Configure Call Data Connector](configure-call-data-connector.md).


Der Anrufdatenkonnektor vereinfacht die Anrufüberwachung in einer Hybridumgebung erheblich, da Sie nicht mehr verschiedene Gruppen von lokalen und Onlinetools verwenden müssen, um die Anrufqualität für alle Ihre Benutzer zu überwachen. Unabhängig davon, ob Ihre Benutzer lokal oder online verwaltet werden, können Sie die Anrufqualität für Ihre gesamte Organisation online anzeigen.

Mit dem Anrufdaten-Connector können Sie die folgenden Aufgaben mithilfe eines einzelnen Toolsets ausführen:

- Überwachen Sie Ihre Benutzererfahrung über Microsoft Teams, Skype for Business Online und Skype for Business Server hinweg.

- Anzeigen und Beheben von Problemen in Ihrem Netzwerk.

- Weisen Sie Helpdesk- und Administratorrollen für die Anrufanalyse zu, damit Sie Helpdesk-Mitarbeitern ermöglichen können, ihre Zuständigkeitsbereiche anzuzeigen und zu beheben.

Mit dem Anrufdatenkonnektor übergibt der Skype for Business Server Anrufdaten an den Clouddienst, sodass Sie die Tools Skype for Business Onlineanrufanalyse (CA) und des Anrufqualitätsdashboards (Call Quality Dashboard, CQD) nutzen können, wie im folgenden Diagramm dargestellt:

![SfB Cloud-Voicemail Diagramm.](../../sfbserver2019/media/call-data-connector-plan-1.png)

Der Server sendet sowohl QoE-Daten (Quality of Experience) als auch KDS-Daten (Call Detail Recording) an den Onlinedienst.

Mit den Anrufanalyse- und CQD-Tools können Sie die Qualität von Anrufen überwachen und Verbindungsprobleme mit Microsoft Teams und Skype for Business Diensten wie folgt behandeln:

- Die Anrufanalyse konzentriert sich auf Qualitätsprobleme bei bestimmten Anrufen. Es enthält detaillierte Informationen zu Anrufen und Besprechungen für jeden Benutzer in einem Skype for Business Konto.  Mit der Anrufanalyse können Sie einem Helpdesk-Operator Berechtigungen zuweisen, der dann Anrufe überwachen kann, ohne Zugriff auf den Rest des Skype for Business Admin Centers zu haben.

- Das Anrufqualitäts-Dashboard konzentriert sich auf die Netzwerkleistung und Probleme in einer Organisation. Skype for Business Administratoren und Netzwerktechniker dieses Tool zur Problembehandlung und Optimierung der Netzwerkleistung verwenden.

Weitere Informationen finden Sie unter [Microsoft Teams: Überwachen und Verbessern der Anrufqualität.](/monitor-call-quality-qos)

Natürlich möchten Sie möglicherweise einige Daten zur Anrufqualität lokal beibehalten. Dies kann beispielsweise der Fall sein, wenn Sie eine Drittanbieterlösung mit angepassten Berichten und Workflows verwenden.  Mit dem Anrufdatenkonnektor können Sie das Senden von Daten an den Onlinedienst konfigurieren und gleichzeitig eine Kopie der Daten auf Ihrem lokalen Server beibehalten, wie im folgenden Diagramm dargestellt:

![SfB Cloud-Voicemail.](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Anforderungen

Bei den folgenden Anforderungen wird davon ausgegangen, dass Sie bereits Skype for Business Server in einer unterstützten Topologie bereitgestellt haben.  Weitere Informationen zum Bereitstellen von Skype for Business Server und unterstützten Topologien finden Sie unter [Topologiegrundlagen.](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) Zum Konfigurieren des Anrufdatenkonnektors müssen Sie:

- Hybridkonnektivität aktivieren. Wenn Sie bereits Skype for Business Server bereitgestellt haben und den Anrufdatenkonnektor aktivieren möchten, müssen Sie sicherstellen, dass die Hybridkonnektivität zwischen Ihrer lokalen und Onlineumgebung eingerichtet ist. Dies wird manchmal als Konfiguration für geteilte Domänen bezeichnet.

   Weitere Informationen finden Sie unter Planen der [Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](plan-hybrid-connectivity.md) und Konfigurieren der [Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](configure-hybrid-connectivity.md).

- Authentifizieren Sie sich bei Ihrer Microsoft 365 oder Office 365 Organisation, und stellen Sie sicher, dass die folgenden Rollen aktiviert sind:

  - Skype for Business Server Administrator
  - Microsoft 365 oder Office 365 globaler Administrator

- Wenn dies noch nicht geschehen ist, aktivieren Sie das Anrufqualitäts-Dashboard, wie unter [Aktivieren und Verwenden des Anrufqualitäts-Dashboards für Microsoft Teams und Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard)beschrieben.

- Aktivieren Sie den Front-End-Pool für die Überwachung mit lokalen LCSCdr- und QoEMetrics-Datenbanken. Ohne dies verfügt der Anrufdatenkonnektor nicht über Metrikendaten, mit denen er arbeiten kann.

> [!IMPORTANT]
> Der Anrufdatenkonnektor funktioniert nicht, wenn die Überwachung im Front-End-Pool nicht aktiviert ist.

- Ordnungsgemäß konfigurierte [Server-zu-Server-Authentifizierung.](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Vergleich von lokalen und Online-Anrufqualitäts-Dashboard-Berichten (CQD)

| Featureberichte | Skype for Business Online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Metrik "Anwendungsfreigabe" |Ja | Begrenzte |
| Kunden-Gebäudeinformationen| Ja | Ja |
| Drilldownanalyse | Ja | Nein |
| Metriken zur Mediensicherheit | Ja | Begrenzte |
| Sofort einsatzbereite Berichte | Ja | Ja |
| Übersichtsberichte | Ja | Nein |
| Berichte pro Benutzer | Ja | Ja |
| Anpassung des Berichtssatzes <br> (Berichte hinzufügen, löschen, ändern) | Ja | Ja |
| Videobasierte Bildschirmfreigabemetriken | Ja | Nein |
| Daten-APIs für den programmgesteuerten Zugriff <br> zu CQD | Nein | Ja |
||||

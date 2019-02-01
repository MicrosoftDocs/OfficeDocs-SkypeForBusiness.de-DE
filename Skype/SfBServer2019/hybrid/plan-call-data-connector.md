---
title: Planen der Anruf Daten Connector | Rufen Sie Monitoring Hybrid Analytics Qualitätsdashboard
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Übersicht über die Verwendung von Skype für Business Online Telemetrie-Tools zum Überwachen von einer lokale Implementierung in einer Hybrid-Szenario.
ms.openlocfilehash: 4e38f7d190cd30c1f0e39dc4cdfa5166ba6a929d
ms.sourcegitcommit: 183a2e40af762e6ab36f05ee8ed31a98e8b8be57
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2019
ms.locfileid: "29690445"
---
# <a name="plan-call-data-connector"></a>Planen der Anruf Data Connector

## <a name="overview"></a>Übersicht

In diesem Thema werden die Vorteile, Planungsaspekte, und Anforderungen für die Implementierung von Skype für Business Server rufen Sie Daten Connector. Weitere Informationen zum Konfigurieren von Data Connector aufrufen finden Sie unter [Call Data Connector konfigurieren](configure-call-data-connector.md).

> [!NOTE]
> Unter public Preview-Version steht nur aufrufen Analytics Dashboard.

Anruf Data Connector vereinfacht die Anruf-Überwachung in einer hybridumgebung, da Sie nicht mehr benötigen, um verschiedene Sätze von lokalen und online-Tools verwenden, um alle Ihre Benutzer die Anrufqualität zu überwachen. Ob Ihre Benutzer lokal verwaltete oder online sind, können Sie die Anrufqualität für die gesamte Organisation online anzeigen.

Mit Data Connector aufrufen, können Sie die folgenden Aufgaben ausführen, mithilfe einer einzelnen Toolset:

- Überwachen Sie Ihre Benutzer wünschen über Microsoft-Teams, Skype für Business Online und Skype für Business Server.

- Zeigen Sie an und beheben Sie Probleme in Ihrem Netzwerk.

- Zuweisen von Helpdesk und Administrator Rollen für aufrufen, Analyse, sodass Mitarbeiter anzeigen und beheben Verantwortungsbereich Helpdesk Webinhalte.

Mit Anrufen Data Connector schiebt die Skype für Business Server Anrufdaten an den Clouddienst, damit Sie die Skype für Business Online aufrufen Analytics (CA), und rufen Sie Quality Dashboard (CQD) Tools nutzen können wie im folgenden Diagramm dargestellt:

![SfB Cloud-Voicemail](../../sfbserver2019/media/call-data-connector-plan-1.png)

Der Server legt Quality of Experience (QoE) und Aufzeichnung von Kommunikationsdatensätzen (KDS) Daten auf den online-Dienst.

Die Analytics aufrufen und CQD Tools können Sie die Qualität von Anrufen zu überwachen und Problembehandlung für Verbindungsprobleme mit Microsoft-Teams und Skype für BusinessServices wie folgt:

- Rufen Sie Analytics konzentriert sich auf Qualitätsprobleme bei bestimmten Anrufe. Es zeigt detaillierte Informationen zu Anrufe und Besprechungen für jeden Benutzer in einer Skype für Business-Konto.  Mit Analysen aufrufen können Sie Berechtigungen für einen Helpdesk-Operator zuweisen, die dann Anrufe überwachen können, ohne dass der Zugriff auf den Rest der der Skype für Business Admin Center.

- Rufen Sie Qualitätsdashboard konzentriert sich auf die Leistung des Netzwerks und Probleme innerhalb einer Organisation. Skype für Administratoren in Unternehmen und Netzwerktechniker mit diesem Tool können Sie beheben und Optimieren der Leistung des Netzwerks.

Weitere Informationen finden Sie unter [Analytics aufrufen, und rufen Sie Qualitätsdashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).

Sie möchten natürlich einige Anrufqualität Daten lokal speichern. Dies möglicherweise die Groß-/Kleinschreibung, z. B., wenn Sie ein Drittanbieter-Lösung mit benutzerdefinierte Berichte und Workflows.  Anruf Data Connector können Sie sendende von Daten an den online-Dienst konfigurieren und eine Kopie der Daten auf dem lokalen Server auch weiterhin, wie im folgenden Diagramm dargestellt:

![SfB Cloud-Voicemail](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Anforderungen

Die folgenden Anforderungen wird davon ausgegangen, dass Sie bereits Skype für Business Server in einer unterstützten Topologie bereitgestellt haben.  Weitere Informationen zur Bereitstellung von Skype für Business Server und unterstützten Topologien finden Sie unter [Grundlagen der Topologie](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics). Um Call Data Connector zu konfigurieren, müssen Sie folgende Aktionen ausführen:

- Aktivieren Sie Hybrid-Diensten. Wenn Sie Skype bereits für Business Server bereitgestellt haben, und rufen Sie Data Connector aktivieren möchten, müssen Sie sicherstellen, dass Sie hybridkonnektivität zwischen Ihrer lokalen und online-Umgebung eingerichtet haben. Dies ist eine geteilte Domänenkonfiguration bezeichnet.

   Weitere Informationen finden Sie unter [hybridkonnektivität zwischen Skype für Business Server und Office 365 planen](plan-hybrid-connectivity.md) und [Konfigurieren von hybridkonnektivität zwischen Skype für Business Server und Office 365](configure-hybrid-connectivity.md).

- Authentifizieren sich bei Ihrem Office 365-Mandanten, und stellen Sie sicher, dass Sie die folgenden Rollen aktiviert haben:

  - Skype für Business Server-Administrator
  - Office 365 globaler Administrator

- Wenn Sie dies nicht bereits geschehen ist, aktivieren Sie rufen Qualitätsdashboard gemäß [einschalten, und rufen Sie Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verwenden](/microsoftteams/turning-on-and-using-call-quality-dashboard).

- Aktivieren Sie den Front-End-Pool für Überwachung, mit lokalen LcsCDR und QoEMetrics-Datenbanken. Ohne diese keine Call Data Connector metrische Daten entwickelt.

> [!IMPORTANT]
> Anruf Data Connector ist nicht funktionsfähig, wenn die Überwachung auf dem Front-End-Pool nicht aktiviert ist.

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Vergleich zwischen lokalen und online aufrufen Quality Dashboard (CQD)-Berichte

| Feature-Berichte | Skype for Business Online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Anwendungsfreigabemetrik |Ja | Begrenzt |
| Erstellen von Kundeninformationen| Ja  | Ja  |
| Drilldown-Analyse | Festlegen einer internationalen Nummer als Standardeinwahlnummer (die in der Besprechungseinladung angegeben ist) für einen Benutzer | Nein |
| Medienzuverlässigkeitsmetriken | Ja | Begrenzt |
| Sofort einsatzbereite Berichte | Ja  | Ja  |
| Übersichtsberichte | Ja | Nein |
| Pro Benutzerberichte | Ja  | Ja  |
| Anpassen von Berichten set <br> (Fügen Sie hinzu, löschen Sie, ändern Sie Berichte) | Ja  | Ja |
| Videobasierte Bildschirmfreigabe-Metriken | Festlegen einer internationalen Nummer als Standardeinwahlnummer (die in der Besprechungseinladung angegeben ist) für einen Benutzer | Nein |
| Daten-APIs für den programmgesteuerten Zugriff <br> zu CQD | Nein | Ja |
||||

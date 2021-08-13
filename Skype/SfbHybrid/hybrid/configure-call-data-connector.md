---
title: Konfigurieren des Anrufdatenconnectors
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
description: Anweisungen zum Konfigurieren des Anrufdatenkonnektors, mit dem Telemetriedaten aus Skype for Business lokalen Umgebungen mit Skype for Business Onlinetools angezeigt werden können.
ms.openlocfilehash: bc9346919e3f70d8fe8fe3e43e61a0e715cf0eb9bf52534a2beb2f8604b920f8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323687"
---
# <a name="configure-call-data-connector"></a>Konfigurieren des Anrufdatenconnectors

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


In diesem Artikel wird beschrieben, wie Sie den Anrufdaten-Connector konfigurieren – ein einzelnes Toolset, das das Anzeigen Skype for Business Server Anrufqualitätsdaten mithilfe Skype for Business Tools für das Onlineanrufqualitäts-Dashboard (Online Call Quality Dashboard, CQD) und die Anrufanalyse ermöglicht.

Weitere Informationen zu den Vorteilen und Voraussetzungen des Anrufdatenkonnektors, z. B. Rollenanforderungen und das Einrichten einer Hybridkonnektivität, finden Sie unter [Plan Call Data Connector.](plan-call-data-connector.md)

## <a name="enable-monitoring"></a>Aktivieren der Überwachung
 
Sie müssen die Datensammlung für die Aufzeichnung von Kommunikationsdatensätzen (KDS) und QoE (Quality of Experience) in Ihrer Front-End-Poolüberwachung mit lokalen LCSCdr- und QoEMetrics-Datenbanken konfigurieren. andernfalls erhalten die Anrufanalyse- und Anrufqualitäts-Dashboards keine Daten, mit denen sie arbeiten können. Führen Sie vor dem Konfigurieren des Anrufdatenkonnektors die schritte unter [Bereitstellen der Überwachung in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) aus, um sowohl KDS als auch QoE sowie die grundlegende Überwachung zu konfigurieren.

> [!IMPORTANT]
> Der Anrufdatenkonnektor funktioniert nicht, wenn die Überwachung im Front-End-Pool nicht aktiviert ist.

## <a name="enable-call-data-connector"></a>Aktivieren des Anrufdatenkonnektors

Zum Konfigurieren und Aktivieren des Anrufdatenconnectors verwenden Sie die folgenden Cmdlets:

| Cmdlet| Beschreibung|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Ein Online-Cmdlet, mit dem ein Onlinedatensammler eingerichtet wird.|
| Get-CsCloudCallDataConnection | Ein Online-Cmdlet, das einen vorhandenen Onlinedatensammlungscomputer abruft.|  
| Get-CsCloudCallDataConnector | Ein lokales Cmdlet, das die vom cmdlet New-CsCloudCallDataConnection erstellten Verbindungsinformationen abruft. |
| Set-CsCloudCallDataConnector | Ein lokales Cmdlet, das eine lokale Kopie der vom Cmdlet New-CsCloudCallDataConnection erstellten Verbindungsinformationen speichert. |  
| Set-CsCloudCallDataConnectorConfiguration | Ein lokales Cmdlet, mit dem Sie den Connector aktivieren oder deaktivieren und die Bereichsebene anpassen können.|

> [!NOTE]
> Verwenden Sie das Cmdlet "Remove-csclouddatconnectorconfiguration", um Ihre Konfiguration zu löschen und von vorn zu beginnen.

### <a name="configure-your-environment"></a>Konfigurieren Ihrer Umgebung 

Um Ihre Umgebung so zu konfigurieren, dass ein Onlinedatensammler aktiviert wird, müssen Sie sich zuerst als Administrator bei Skype for Business Online PowerShell anmelden. Weitere Informationen finden Sie unter [Verwalten von Skype for Business Online mit Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Es gibt zwei Methoden für die Anmeldung bei Skype for Business Online PowerShell:

- Aus der Skype for Business Server 2019-Verwaltungsshell (empfohlene Methode)
- Aus einer anderen PowerShell-Sitzung

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Melden Sie sich über die Skype for Business Server-Verwaltungsshell bei Skype for Business Online-PowerShell an (empfohlene Methode).

1. Wenn Sie den Connector zum ersten Mal aktivieren, führen Sie den folgenden Befehl aus:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Wenn Sie einen Fehler erhalten, dass die Verbindung bereits vorhanden ist, bedeutet dies, dass die Anrufdatenverbindung bereits für Ihren Mandanten vorhanden ist. Führen Sie in diesem Fall den folgenden Befehl aus: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Melden Sie sich über eine andere PowerShell-Sitzung bei Skype for Business Online-PowerShell an (optionale Methode).

1.  Wenn Sie den Connector zum ersten Mal aktivieren, führen Sie den folgenden Befehl aus: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Wenn Sie einen Fehler erhalten, dass die Verbindung bereits vorhanden ist, bedeutet dies, dass die Anrufdatenverbindung bereits für Ihren Mandanten vorhanden ist. Führen Sie in diesem Fall den folgenden Befehl aus: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

Die Ausgabe der obigen Befehle enthält einen Tokenwert, den Sie beim Konfigurieren Ihrer lokalen Umgebung wie folgt benötigen:

Geben Sie in der Skype for Business Server Verwaltungsshell den folgenden Befehl an:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Konfigurieren des Bereichs

Sie können den Anrufdatenkonnektor für einen bestimmten Standort oder für die gesamte Skype for Business Server Bereitstellung mithilfe des Cmdlets Set-CsCloudCallDataConnectorConfiguration in der Skype for Business Server Verwaltungsshell aktivieren. Mit dem folgenden Befehl wird beispielsweise der Anrufdatenkonnektor auf globaler Ebene aktiviert:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Zusätzlich zu den globalen Einstellungen können die Konfigurationseinstellungen des Anrufdatenkonnektors dem Standortbereich zugewiesen werden. Dies bietet zusätzliche Verwaltungsflexibilität, wenn es um die Überwachung geht. Beispielsweise kann ein Administrator die Anrufdatenkonnektorweiterleitung für den Standort Redmond aktivieren, aber die Anrufdatenkonnektorweiterleitung für den Standort Dublin deaktivieren, wie im folgenden Beispiel gezeigt:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Einstellungen, die auf Standortebene konfiguriert sind, haben Vorrang vor einstellungen, die auf globaler Ebene konfiguriert sind. Angenommen, die Anrufdatenkonnektorweiterleitung ist auf globaler Ebene aktiviert, aber auf Standortebene deaktiviert (für den Standort Redmond). Das bedeutet, dass die Aufzeichnung von Kommunikationsdatensätzen und QoE-Informationen für Benutzer am Standort Redmond nicht weitergeleitet wird. Benutzer an anderen Standorten (d. h. Benutzer, die über die globalen Einstellungen anstelle der Einstellungen für den Standort Redmond verwaltet werden) lassen jedoch die Aufzeichnung von Kommunikationsdatensätzen und QoE-Informationen weiterleiten.

Werte für die am häufigsten verwendeten Einstellungen, die vom Anrufdatenkonnektor verwendet werden, sind in der folgenden Tabelle aufgeführt:  

|Eigenschaft|Beschreibung|Standardwert|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Gibt an, ob der Anrufdatenkonnektor aktiviert ist. Wenn "True", werden Überwachungsdatensätze an die Onlineüberwachung weitergeleitet.  <br/> |$False  <br/> |
| Identität | Bestimmt die Bereichsebene für den Befehl: global oder standort.   | Globalen  |

## <a name="disable-call-data-connector"></a>Deaktivieren des Anrufdatenkonnektors

Durch das Deaktivieren des Anrufdatenkonnektors wird weder die Zuordnung des Überwachungsspeichers vom Front-End-Pool noch die Deinstallation oder anderweitige Auswirkung auf die Back-End-Überwachungsdatenbank entfernt. Wenn Sie den Anrufdaten-Connector deaktivieren, beenden Sie Skype for Business Server, Anrufdaten in die Cloud hochzuladen. 

Sie deaktivieren den Anrufdatenkonnektor mithilfe des Cmdlets Set-CsCloudCallDataConnectorConfiguration in der Skype for Business Server Verwaltungsshell. Mit dem folgenden Befehl wird beispielsweise der Anrufdatenconnector auf globaler Ebene deaktiviert, indem die Eigenschaft EnableCallDataConnector auf $False festgelegt wird:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Wenn Sie das Hochladen von Anrufdaten in die Cloud fortsetzen möchten, legen Sie die Eigenschaft EnableCallDataConnector wieder auf $True fest, wie im folgenden Beispiel gezeigt:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Anzeigen lokaler Daten über das Onlinedashboard

 Nachdem der Anrufdatenkonnektor aktiviert wurde, können Sie Ihre lokalen Anrufdaten im Anrufanalysedashboard oder im Anrufqualitätsdashboard anzeigen, wie unter ["Verwenden der Anrufanalyse"](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) beschrieben, um Probleme mit schlechter Qualität zu beheben und das [Anrufqualitäts-Dashboard für Microsoft Teams und Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)zu aktivieren und zu verwenden.

## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zu den Cmdlets finden Sie mit dem Befehl Get-Help in der Skype for Business Server Verwaltungsshell. Beispiel:

Get-Help Get-CsCloudCallDataConnector | Mehr

Get-Help Set-CsCloudCallDataConnector | Mehr

Get-Help Set-CsCloudCallDataConnectorConfiguration | Mehr
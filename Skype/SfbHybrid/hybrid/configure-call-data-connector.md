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
ms.localizationpriority: medium
ms.collection: ''
description: Anweisungen zum Konfigurieren des Anrufdatenconnectors, mit dem Telemetriedaten von Skype for Business lokal mithilfe Skype for Business Onlinetools angezeigt werden können.
ms.openlocfilehash: 0d92d31798cd4b3fb5a1b4c555ff0ff00c2bdf31
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156933"
---
# <a name="configure-call-data-connector"></a>Konfigurieren des Anrufdatenconnectors

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


In diesem Artikel wird beschrieben, wie Sie den Anrufdatenconnector konfigurieren – ein einzelnes Toolset, das die Anzeige Skype for Business Server Anrufqualitätsdaten mithilfe von Microsoft Call Quality Dashboard (CQD) und Anrufanalysetools (Call Analytics, CA) ermöglicht.

Weitere Informationen zu den Vorteilen und Voraussetzungen von Call Data Connector, z. B. Rollenanforderungen und Einrichten der Hybridkonnektivität, finden Sie unter [Plan Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Überwachung aktivieren
 
Sie müssen die Aufzeichnung von Anrufdaten (KDS) und die QoE-Datensammlung (Quality of Experience) in Ihrem Front-End-Pool-Monitoring mit lokalen LCSCdr- und QoEMetrics-Datenbanken konfigurieren. andernfalls erhalten die Anrufanalyse- und Anrufqualitätsdashboards keine Daten, mit der sie arbeiten können. Bevor Sie den Anrufdatenconnector konfigurieren, führen Sie die Schritte aus, die unter [Bereitstellen der Überwachung in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) zum Konfigurieren von KDS und QoE sowie der grundlegenden Überwachung bereitgestellt werden.

> [!IMPORTANT]
> Der Anrufdatenconnector funktioniert nicht, wenn die Überwachung im Front-End-Pool nicht aktiviert ist.

## <a name="enable-call-data-connector"></a>Aktivieren des Anrufdatenconnectors

Zum Konfigurieren und Aktivieren des Anrufdatenconnectors verwenden Sie die folgenden Cmdlets:

| Cmdlet| Beschreibung|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Ein Online-Cmdlet, mit dem ein Onlinedatensammler erstellt wird.|
| Get-CsCloudCallDataConnection | Ein Online-Cmdlet, das einen vorhandenen Onlinedatensammler abruft.|  
| Get-CsCloudCallDataConnector | Ein lokales Cmdlet, das die vom New-CsCloudCallDataConnection-Cmdlet erstellten Verbindungsinformationen abruft. |
| Set-CsCloudCallDataConnector | Ein lokales Cmdlet, das eine lokale Kopie der vom cmdlet New-CsCloudCallDataConnection erstellten Verbindungsinformationen speichert. |  
| Set-CsCloudCallDataConnectorConfiguration | Ein lokales Cmdlet, mit dem Sie den Connector aktivieren oder deaktivieren und die Bereichsebene anpassen können.|

> [!NOTE]
> Um Ihre Konfiguration zu löschen und von vorne zu beginnen, verwenden Sie bitte das Cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Konfigurieren Ihrer Umgebung 

Um Ihre Umgebung so zu konfigurieren, dass ein Onlinedatensammler aktiviert wird, müssen Sie sich zuerst als Administrator beim Microsoft Teams PowerShell-Modul anmelden. Weitere Informationen finden Sie unter [Microsoft Teams PowerShell Overview](/microsoftteams/teams-powershell-overview).

Es gibt zwei Methoden für die Anmeldung beim Microsoft Teams PowerShell-Modul:

- Aus der Skype for Business Server 2019-Verwaltungsshell (empfohlene Methode)
- Aus einer anderen PowerShell-Sitzung

#### <a name="log-in-to-microsoft-teams-powershell-module-from-the-skype-for-business-server-management-shell-recommended-method"></a>Anmelden beim Microsoft Teams PowerShell-Modul über die Skype for Business Server-Verwaltungsshell (empfohlene Methode)

1. Wenn Sie den Connector zum ersten Mal aktivieren, führen Sie den folgenden Befehl aus:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Wenn eine Fehlermeldung angezeigt wird, dass die Verbindung bereits vorhanden ist, bedeutet dies, dass die Verbindung mit den Anrufdaten für Ihren Mandanten bereits vorhanden ist. Führen Sie in diesem Fall den folgenden Befehl aus: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-microsoft-teams-powershell-module-from-another-powershell-session-optional-method"></a>Anmelden beim Microsoft Teams PowerShell-Modul aus einer anderen PowerShell-Sitzung (optionale Methode)

1.  Wenn Sie den Connector zum ersten Mal aktivieren, führen Sie den folgenden Befehl aus: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Wenn eine Fehlermeldung angezeigt wird, dass die Verbindung bereits vorhanden ist, bedeutet dies, dass die Verbindung mit den Anrufdaten für Ihren Mandanten bereits vorhanden ist. Führen Sie in diesem Fall den folgenden Befehl aus: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

Die Ausgabe der oben genannten Befehle enthält einen Tokenwert, den Sie beim Konfigurieren Ihrer lokalen Umgebung wie folgt benötigen:

Geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl an:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Konfigurieren des Bereichs

Sie können den Anrufdatenconnector für einen bestimmten Standort oder die gesamte Skype for Business Server Bereitstellung aktivieren, indem Sie das cmdlet Set-CsCloudCallDataConnectorConfiguration innerhalb der Skype for Business Server-Verwaltungsshell verwenden. Der folgende Befehl aktiviert beispielsweise den Anrufdatenconnector auf globaler Ebene:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Zusätzlich zu den globalen Einstellungen können konfigurationseinstellungen des Anrufdatenconnectors dem Standortbereich zugewiesen werden. Dies bietet zusätzliche Verwaltungsflexibilität bei der Überwachung. Beispielsweise kann ein Administrator die Anrufdaten-Connector-Weiterleitung für den Standort Redmond aktivieren, aber die Anrufdaten-Connector-Weiterleitung für den Dublin-Standort deaktivieren, wie im folgenden Beispiel gezeigt:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Auf Standortebene konfigurierte Einstellungen haben Vorrang vor Einstellungen, die auf globaler Ebene konfiguriert sind. Angenommen, die Anrufdatenkonnektor-Weiterleitung ist im globalen Bereich aktiviert, aber im Standortbereich deaktiviert (für den Standort "Redmond"). Das bedeutet, dass die Aufzeichnung von Kommunikationsdatensätzen und QoE-Informationen nicht für Benutzer am Standort Redmond weitergeleitet werden. Benutzer an anderen Standorten (d. h. Benutzer, die über die globalen Einstellungen anstelle der Standorteinstellungen von Redmond verwaltet werden) werden jedoch ihre Aufzeichnung von Anrufdetails und QoE-Informationen weitergeleitet.

Werte für die am häufigsten verwendeten Einstellungen, die vom Anrufdatenconnector verwendet werden, sind in der folgenden Tabelle aufgeführt:  

|Eigenschaft|Beschreibung|Standardwert|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Gibt an, ob der Anrufdatenconnector aktiviert ist. Bei "True" werden die Überwachungsdatensätze an die Onlineüberwachung weitergeleitet.  <br/> |$False  <br/> |
| Identität | Bestimmt die Bereichsebene für den Befehl: global oder standort.   | global  |

## <a name="disable-call-data-connector"></a>Deaktivieren des Anrufdatenconnectors

Durch das Deaktivieren des Anrufdatenconnectors wird weder die Zuordnung des Überwachungsspeichers zum Front-End-Pool deaktiviert noch die Back-End-Überwachungsdatenbank deinstalliert oder anderweitig beeinflusst. Wenn Sie den Anrufdatenconnector deaktivieren, verhindern Sie, dass Skype for Business Server Anrufdaten in die Cloud hochlädt. 

Sie deaktivieren den Anrufdatenconnector mithilfe des cmdlets Set-CsCloudCallDataConnectorConfiguration innerhalb der Skype for Business Server-Verwaltungsshell. Der folgende Befehl deaktiviert beispielsweise den Anrufdatenconnector auf globaler Ebene, indem die Eigenschaft "EnableCallDataConnector" auf $False festgelegt wird:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Wenn Sie das Hochladen von Anrufdaten in die Cloud fortsetzen möchten, legen Sie die EnableCallDataConnector-Eigenschaft wieder auf $True fest, wie im folgenden Beispiel gezeigt:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Anzeigen lokaler Daten über das Onlinedashboard

 Nachdem der Anrufdatenconnector aktiviert wurde, können Sie Ihre lokalen Anrufdaten im Anrufanalyse-Dashboard oder im Anrufqualitätsdashboard anzeigen, wie unter ["Anrufanalyse verwenden" beschrieben, um Probleme mit schlechter Qualität zu beheben](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality), und [das Anrufqualitäts-Dashboard für Microsoft Teams und Skype for Business Online aktivieren und verwenden](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Weitere Informationen

Für weitere Informationen zu den Cmdlets können Sie den Befehl Get-Help aus der Skype for Business Server-Verwaltungsshell verwenden. Zum Beispiel:

Get-Help Get-CsCloudCallDataConnector | mehr

Get-Help Set-CsCloudCallDataConnector | mehr

Get-Help Set-CsCloudCallDataConnectorConfiguration | mehr

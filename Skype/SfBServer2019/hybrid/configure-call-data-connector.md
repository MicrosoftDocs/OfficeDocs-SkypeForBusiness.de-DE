---
title: Konfigurieren von Anruf Daten Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Informationen zum Konfigurieren von Anrufen Daten Connector, der für lokale Skype für Business Online-Tools mit angezeigt werden, um Business Telemetrie von Skype werden können.
ms.openlocfilehash: 959bb182da91029fd43ebc3ccb99fb5a69d820b2
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838823"
---
# <a name="configure-call-data-connector"></a>Konfigurieren von Anruf Daten Connector

In diesem Artikel wird beschrieben, wie Call Data Connector – ein einzelnes Toolset konfigurieren, die dem Skype für Server aufrufen Qualität Geschäftsdaten verwenden Skype für Business Online aufrufen Quality Dashboard (CQD) und Aufrufen Analytics (CA) Tools angezeigt wird. 

> [!NOTE]
> Unter public Preview-Version steht nur aufrufen Analytics Dashboard.

Weitere Informationen zu aufrufen Data Connector Vorteile und die erforderlichen Komponenten, beispielsweise Rolle Anforderungen und Einrichten von hybridkonnektivität finden Sie unter [Planen der Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Aktivieren der Überwachung
 
Sie müssen Call Data Recording (CDR) konfigurieren und Datensammlung Quality of Experience (QoE) in Ihrer Front-End-pool-Überwachung, mit lokalen Datenbanken LCSCdr und QoEMetrics; Andernfalls wird nicht die Analytics aufrufen und die Qualität-Dashboards aufrufen entwickelt Abrufen von Daten. Bevor Sie Configure Anruf Data Connector führen Sie die Schritte in [Deploy Überwachung in Skype für Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) sowohl KDS und QoE sowie grundlegende Überwachung konfigurieren.

> [!IMPORTANT]
> Anruf Data Connector ist nicht funktionsfähig, wenn die Überwachung auf dem Front-End-Pool nicht aktiviert ist.

## <a name="enable-call-data-connector"></a>Anruf Daten Connector aktivieren

Zum Konfigurieren und Aktivieren von Data Connector aufrufen, verwenden Sie die folgenden Cmdlets:

| Cmdlet| Beschreibung|
| :-----------------|---------------:|
| Neue CsCloudCallDataConnection | Ein online-Cmdlet, das ein online Sammlungssatzes herstellt.|
| Get-CsCloudCallDataConnection | Ein online-Cmdlet, die vorhandenen online Sammlungen abruft.|  
| Get-CsCloudCallDataConnector | Eine lokale-Cmdlet, das die Verbindungsinformationen, die vom Cmdlet New-CsCloudCallDataConnection erstellt werden abgerufen. |
| Set-CsCloudCallDataConnector | Eine lokale-Cmdlet, das die Verbindungsinformationen, die durch das Cmdlet "New-CsCloudCallDataConnection" erstellt eine lokale Kopie gespeichert. |  
| Set-CsCloudCallDataConnectorConfiguration | Eine lokale-Cmdlet, mit dem Sie aktivieren oder deaktivieren den Connector und Anwendungsebene anpassen.|

### <a name="configure-your-environment"></a>Konfigurieren der Umgebung 

Zum Konfigurieren Ihrer Umgebung, um eine Sammlung online zu aktivieren, müssen Sie zuerst zu Skype für Business Online PowerShell als Administrator anmelden. Weitere Informationen finden Sie unter [Verwalten von Skype für Business Online mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Es gibt zwei Methoden für die Anmeldung beim Skype für Business Online PowerShell:

- Aus der Skype für Business Server 2019-Verwaltungsshell (empfohlene Methode)
- Aus einer anderen PowerShell-Sitzung

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Melden Sie sich bei Skype für Business Online PowerShell aus der Skype für Business Server-Verwaltungsshell (empfohlene Methode)

1. Wenn die Verbindung zum ersten Mal zu aktivieren, führen Sie den folgenden Befehl ein:

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Wenn Sie eine Fehlermeldung, die die Verbindung bereits vorhanden ist erhalten, bedeutet dies, dass für Ihre Mandanten die Anruf-Datenverbindung bereits vorhanden ist. In diesem Fall führen Sie den Befehl aus: 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Melden Sie sich bei Skype für Business Online PowerShell aus einer anderen PowerShell-Sitzung (optional-Methode)

1.  Wenn die Verbindung zum ersten Mal zu aktivieren, führen Sie den folgenden Befehl ein: 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  Wenn Sie eine Fehlermeldung, die die Verbindung bereits vorhanden ist erhalten, bedeutet dies, dass für Ihre Mandanten die Anruf-Datenverbindung bereits vorhanden ist. In diesem Fall führen Sie den Befehl aus: 

    ```
    Get-CsCloudCallDataConnection  
    ```

Die Ausgabe des obigen Befehle enthält einen Tokenwert, die Sie benötigen, wenn Sie Ihre lokale Umgebung wie folgt konfigurieren:

Geben Sie von innerhalb der Skype für Business Server-Verwaltungsshell den folgenden Befehl ein:

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Konfigurieren Sie den Bereich

Sie können Daten Connector rufen Sie mithilfe des Set-CsCloudCallDataConnectorConfiguration-Cmdlets in der Skype für Business Server-Verwaltungsshell für einen bestimmten Standort oder für Ihre gesamte Skype für Business Server-Bereitstellung aktivieren. Beispielsweise kann der folgende Befehl rufen Sie Data Connector auf globaler Ebene:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Zusätzlich zu den globalen Einstellungen für können Call Data Connector-Konfigurationseinstellungen, die auf Standortebene zugewiesen werden. Dies bietet zusätzliche Management-Flexibilität, wenn es für die Überwachung stammt. Beispielsweise kann der Administrator aktivieren Sie die Weiterleitung von Anrufen Data Connector für den Standort Redmond jedoch Call Data Connector-Weiterleitung für die Website Dublin deaktivieren, wie im folgenden Beispiel dargestellt:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen. Nehmen wir beispielsweise bei Weiterleitung von Anrufen Data Connector auf globaler Ebene aktiviert ist, jedoch auf Standortebene (für den Standort Redmond) deaktiviert. Das bedeutet, die Aufzeichnung von kommunikationsdatensätzen und QoE-Informationen aufrufen werden nicht für Benutzer in den Standort Redmond weitergeleitet. Allerdings haben Benutzer an anderen Standorten (d. h., Benutzer, die durch die globalen Einstellungen anstelle der Redmond-websiteeinstellungen verwaltet) ihre KDS- und QoE-Informationen weitergeleitet.

Werte für den am häufigsten verwendeten Einstellungen aufrufen Data Connector werden in der folgenden Tabelle aufgeführt:  

|Eigenschaft|Beschreibung|Standardwert|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Gibt an, ob Call Data Connector aktiviert ist. Bei True werden Datensätze Überwachung auf die Überwachung der online weitergeleitet.  <br/> |$False  <br/> |
| Identität  | Bestimmt die Bereichsebene für den Befehl: global oder Standort.   | globale  |

## <a name="disable-call-data-connector"></a>Anruf Daten Connector deaktivieren

Deaktivieren Data Connector rufen Sie den Speicher für überwachen aus dem Front-End-Pool nicht aufheben, noch ist es deinstallieren oder anderweitig beeinträchtigt die Überwachung Back-End-Datenbank. Wenn Sie rufen Sie Data Connector deaktivieren, verhindern, dass Sie Skype für Business Server hochladen Anrufdaten in der Cloud. 

Deaktivieren Sie Call Data Connector mithilfe des Set-CsCloudCallDataConnectorConfiguration-Cmdlets in der Skype für Business Server-Verwaltungsshell. Beispielsweise deaktiviert der folgende Befehl rufen Sie Data Connector auf globaler Ebene, indem es die EnableCallDataConnector-Eigenschaft auf $False festlegen:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Wenn Sie Hochladen von Daten in die Cloud fortsetzen möchten, werden die EnableCallDataConnector-Eigenschaft wieder auf $True festgelegt, wie im folgenden Beispiel dargestellt:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Anzeigen der lokale Daten über das online-dashboard

 Nach dem Aufrufen der Data-Connector aktiviert ist, können Sie auf das Dashboard Analytics rufen Sie wie beschrieben in [Verwendung aufrufen Analytics schlechten Qualität Beheben von Problemen mit](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)Ihrer lokalen Anrufdaten anzeigen.


## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen in den Cmdlets können Sie den Befehl Get-Help aus der Skype für Business Server-Verwaltungsshell verwenden. Beispiel:

Get-Help Get-CsCloudCallDataConnector | Weitere

Get-Help Set-CsCloudCallDataConnector | Weitere

Get-Help Set-CsCloudCallDataConnectorConfiguration | Weitere
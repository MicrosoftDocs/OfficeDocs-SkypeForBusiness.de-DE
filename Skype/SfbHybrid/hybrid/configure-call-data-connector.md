---
title: Konfigurieren des Connectors für die Anrufdaten
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Anweisungen zum Konfigurieren des Anruf datenconnectors, mit dem die Telemetrie aus Skype for Business lokal mit Skype for Business Online Tools angezeigt werden kann.
ms.openlocfilehash: 4d472ce49a3059df7286c647b013abe321b9fd15
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963043"
---
# <a name="configure-call-data-connector"></a>Konfigurieren des Connectors für die Anrufdaten

In diesem Artikel wird beschrieben, wie Sie den Anruf Datenkonnektor konfigurieren – ein einzelnes Toolset, mit dem Skype for Business Server Daten zur Anrufqualität mithilfe von Skype for Business Online CQD-und Call Analytics (ca)-Tools angezeigt werden können.

Weitere Informationen zu den Vorteilen und Voraussetzungen des Anruf datenconnectors, wie beispielsweise die Rollenanforderungen und das Einrichten von Hybrid Konnektivität, finden Sie unter [Plan Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Überwachung aktivieren
 
Sie müssen die Datenerfassung für die Aufzeichnung von Datensätzen (KDS) und QoE-Daten (Quality of Experience) in der Front-End-Pool Überwachung mit lokalen LCSCdr-und QoEMetrics-Datenbanken konfigurieren. Andernfalls erhalten die Dashboards für anrufanalyse und Anrufqualität keine Daten, mit denen Sie arbeiten können. Führen Sie vor dem Konfigurieren von Call Data Connector die Schritte unter [Deploy Monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) aus, um sowohl KDS als auch QoE sowie die grundlegende Überwachung zu konfigurieren.

> [!IMPORTANT]
> Der Anrufdaten-Konnektor funktioniert nicht, wenn die Überwachung im Front-End-Pool nicht aktiviert ist.

## <a name="enable-call-data-connector"></a>Aktivieren von Anrufdaten-Konnektor

Zum Konfigurieren und Aktivieren von Call Data Connector verwenden Sie die folgenden Cmdlets:

| Cmdlet| Beschreibung|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Ein Online-Cmdlet, das einen Online-Datensammelpunkt einrichtet.|
| Get-CsCloudCallDataConnection | Ein Online-Cmdlet, mit dem ein vorhandener Online Datensammler abgerufen wird.|  
| Get-CsCloudCallDataConnector | Ein lokales Cmdlet, das die vom New-CsCloudCallDataConnection-Cmdlet erstellten Verbindungsinformationen abruft. |
| Gruppe-CsCloudCallDataConnector | Ein lokales Cmdlet, mit dem eine lokale Kopie der Verbindungsinformationen gespeichert wird, die mit dem Cmdlet New-CsCloudCallDataConnection erstellt wurden. |  
| Gruppe-CsCloudCallDataConnectorConfiguration | Ein lokales Cmdlet, mit dem Sie den Connector aktivieren oder deaktivieren und die Bereichsebene anpassen können.|

> [!NOTE]
> Verwenden Sie das Cmdlet Remove-csclouddatconnectorconfiguration, um die Konfiguration zu löschen und neu zu starten.

### <a name="configure-your-environment"></a>Konfigurieren der Umgebung 

Um Ihre Umgebung so zu konfigurieren, dass ein Online-Datensammelpunkt aktiviert wird, müssen Sie sich zunächst bei Skype for Business Online PowerShell als Administrator anmelden. Weitere Informationen finden Sie unter [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Es gibt zwei Methoden für die Anmeldung bei Skype for Business Online PowerShell:

- Von der Skype for Business Server 2019-Verwaltungsshell (empfohlene Methode)
- Aus einer anderen PowerShell-Sitzung

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Anmelden bei Skype for Business Online PowerShell über die Skype for Business Server-Verwaltungsshell (empfohlene Methode)

1. Wenn der Connector zum ersten Mal aktiviert wird, führen Sie den folgenden Befehl aus:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Wenn Sie eine Fehlermeldung erhalten, dass die Verbindung bereits vorhanden ist, bedeutet dies, dass die Anrufdaten Verbindung bereits für Ihren Mandanten vorhanden ist. Führen Sie in diesem Fall den folgenden Befehl aus: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Anmelden bei Skype for Business Online PowerShell aus einer anderen PowerShell-Sitzung (optionale Methode)

1.  Wenn der Connector zum ersten Mal aktiviert wird, führen Sie den folgenden Befehl aus: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Wenn Sie eine Fehlermeldung erhalten, dass die Verbindung bereits vorhanden ist, bedeutet dies, dass die Anrufdaten Verbindung bereits für Ihren Mandanten vorhanden ist. Führen Sie in diesem Fall den folgenden Befehl aus: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

Die Ausgabe der obigen Befehle enthält einen Tokenwert, den Sie beim Konfigurieren Ihrer lokalen Umgebung wie folgt benötigen:

Geben Sie in der Skype for Business Server Verwaltungsshell den folgenden Befehl an:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Konfigurieren des Bereichs

Sie können den Anruf Datenkonnektor für einen bestimmten Standort oder für die gesamte Skype for Business Server-Bereitstellung mithilfe des Cmdlets "CsCloudCallDataConnectorConfiguration" in der Skype for Business Server-Verwaltungsshell aktivieren. Mit dem folgenden Befehl wird beispielsweise der Anrufdaten-Konnektor auf globaler Ebene aktiviert:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Zusätzlich zu den globalen Einstellungen können Konfigurationseinstellungen für den Anruf Datenconnector dem Standortbereich zugewiesen werden. Dies bietet zusätzliche Flexibilität bei der Verwaltung im Hinblick auf die Überwachung. Beispielsweise kann ein Administrator die Weiterleitung des Anruf datenconnectors für den Standort "Redmond" aktivieren, aber die Weiterleitung des Anruf datenconnectors für den Standort Dublin deaktivieren, wie im folgenden Beispiel dargestellt:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Auf Standortebene konfigurierte Einstellungen haben Vorrang vor den auf globaler Ebene konfigurierten Einstellungen. Nehmen wir beispielsweise an, dass die Weiterleitung des Anruf datenconnectors auf globaler Ebene aktiviert, aber auf Standortebene (für den Standort "Redmond") deaktiviert ist. Das bedeutet, dass die Aufzeichnung von Kommunikationsdatensätzen und QoE-Informationen nicht für Benutzer am Standort "Redmond" weitergeleitet werden. Benutzern an anderen Standorten (also Benutzern, die von den globalen Einstellungen anstelle der Einstellungen für den Standort "Redmond" verwaltet werden) werden jedoch die Aufzeichnung von Kommunikationsdatensätzen und QoE-Informationen weitergeleitet.

Die Werte für die am häufigsten verwendeten Einstellungen, die von Call Data Connector verwendet werden, sind in der folgenden Tabelle dargestellt:  

|Eigenschaft|Beschreibung|Standardwert|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Gibt an, ob der Anrufdaten-Konnektor aktiviert ist. Bei true werden Überwachungsdatensätze an die Online Überwachung weitergeleitet.  <br/> |$False  <br/> |
| Identität | Legt die Bereichsebene für den Befehl fest: Global oder Site.   | globalen  |

## <a name="disable-call-data-connector"></a>Anrufdaten Verbindung deaktivieren

Durch die Deaktivierung des Anruf datenconnectors wird der Überwachungsspeicher nicht vom Front-End-Pool aufgehoben, es wird auch keine Deinstallation oder anderweitige Auswirkung auf die Datenbank der Back-End-Datenbank Wenn Sie den Anrufdaten-Konnektor deaktivieren, beenden Sie Skype for Business Server vom Hochladen von Anrufdaten in die Cloud. 

Sie können den Anrufdaten-Konnektor mithilfe des Cmdlets "CsCloudCallDataConnectorConfiguration" in der Skype for Business Server Verwaltungsshell deaktivieren. Mit dem folgenden Befehl wird beispielsweise der Anrufdaten-Konnektor auf globaler Ebene deaktiviert, indem die EnableCallDataConnector-Eigenschaft auf $false festgesetzt wird:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Wenn Sie das Hochladen von Anrufdaten in die Cloud fortsetzen möchten, legen Sie die EnableCallDataConnector-Eigenschaft wie im folgenden Beispiel gezeigt auf $true zurück:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Anzeigen lokaler Daten über das Online Dashboard

 Nachdem der Anrufdaten-Konnektor aktiviert wurde, können Sie Ihre lokalen Anrufdaten im anrufanalyse-Dashboard oder im Anruf qualitätsdashboard anzeigen, wie unter [Verwenden der anrufanalyse zur Behandlung schlechter Qualität](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) und [aktivieren und Verwenden des Dashboards für die Anrufqualität für Microsoft Teams und Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)beschrieben.

## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zu den Cmdlets finden Sie im Get-Help-Befehl in der Skype for Business Server-Verwaltungsshell. Beispiel:

Get-Help Get-CsCloudCallDataConnector | Weitere

Get-Help-Gruppe-CsCloudCallDataConnector | Weitere

Get-Help-Gruppe-CsCloudCallDataConnectorConfiguration | Weitere

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
description: Anweisungen zum Konfigurieren des Anrufdatenconnector, mit dem Telemetriedaten von Skype for Business lokal mithilfe von Skype for Business Online-Tools angezeigt werden können.
ms.openlocfilehash: f78d59d02964bd826fc705bc193cae3e21b293a5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118994"
---
# <a name="configure-call-data-connector"></a>Konfigurieren des Anrufdatenconnectors

In diesem Artikel wird beschrieben, wie Sie den Anrufdatenconnector konfigurieren – ein einzelnes Toolset, das das Anzeigen von Skype for Business Server-Anrufqualitätsdaten mithilfe des Skype for Business Online Call Quality Dashboard (CQD) und der Anrufanalysetools ermöglicht.

Weitere Informationen zu den Vorteilen und Voraussetzungen des Anrufdatenconnector, z. B. Rollenanforderungen und einrichten von Hybridkonnektivität, finden Sie unter [Plan Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Aktivieren der Überwachung
 
Sie müssen die #A0 (Call Data Recording, CdR) und die QoE-Datensammlung (Quality of Experience) in Ihrem Front-End-Pool monitoring mit lokalen LCSCdr- und QoEMetrics-Datenbanken konfigurieren. Andernfalls erhalten die Anrufanalyse- und Anrufqualitätsdashboards keine Daten für die Arbeit. Führen Sie vor dem Konfigurieren des Anrufdatenconnector die unter Bereitstellen der Überwachung [in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) bereitgestellten Schritte aus, um sowohl CDR als auch QoE sowie grundlegende Überwachung zu konfigurieren.

> [!IMPORTANT]
> Der Anrufdatenconnector funktioniert nicht, wenn die Überwachung im Front-End-Pool nicht aktiviert ist.

## <a name="enable-call-data-connector"></a>Aktivieren des Anrufdatenconnector

Zum Konfigurieren und Aktivieren des Anrufdatenconnector verwenden Sie die folgenden Cmdlets:

| Cmdlet| Beschreibung|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Ein Online-Cmdlet, das einen Onlinedatensammler aufbaut.|
| Get-CsCloudCallDataConnection | Ein Online-Cmdlet, das einen vorhandenen Onlinedatensammler abruft.|  
| Get-CsCloudCallDataConnector | Ein lokales Cmdlet, das die verbindungsinformationen abruft, die vom cmdlet New-CsCloudCallDataConnection werden. |
| Set-CsCloudCallDataConnector | Ein lokales Cmdlet, das eine lokale Kopie der verbindungsinformationen speichert, die vom cmdlet New-CsCloudCallDataConnection werden. |  
| Set-CsCloudCallDataConnectorConfiguration | Ein lokales Cmdlet, mit dem Sie den Connector aktivieren oder deaktivieren und die Bereichsebene anpassen können.|

> [!NOTE]
> Um Ihre Konfiguration zu löschen und von vorn zu beginnen, verwenden Sie das Cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Konfigurieren Ihrer Umgebung 

Um Ihre Umgebung so zu konfigurieren, dass ein Onlinedatensammler aktiviert wird, müssen Sie sich zunächst als Administrator bei Skype for Business Online PowerShell anmelden. Weitere Informationen finden Sie [unter Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Es gibt zwei Methoden für die Anmeldung bei Skype for Business Online PowerShell:

- Aus der Skype for Business Server 2019-Verwaltungsshell (empfohlene Methode)
- Aus einer anderen PowerShell-Sitzung

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Melden Sie sich über die Skype for Business Server-Verwaltungsshell bei Skype for Business Online PowerShell an (empfohlene Methode)

1. Wenn Sie den Connector zum ersten Mal aktivieren, führen Sie den folgenden Befehl aus:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Wenn Sie einen Fehler erhalten, dass die Verbindung bereits vorhanden ist, bedeutet dies, dass die Anrufdatenverbindung bereits für Ihren Mandanten vorhanden ist. Führen Sie in diesem Fall den Befehl aus: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Melden Sie sich über eine andere PowerShell-Sitzung bei Skype for Business Online PowerShell an (optionale Methode)

1.  Wenn Sie den Connector zum ersten Mal aktivieren, führen Sie den folgenden Befehl aus: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Wenn Sie einen Fehler erhalten, dass die Verbindung bereits vorhanden ist, bedeutet dies, dass die Anrufdatenverbindung bereits für Ihren Mandanten vorhanden ist. Führen Sie in diesem Fall den Befehl aus: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

Die Ausgabe der obigen Befehle enthält einen Tokenwert, den Sie beim Konfigurieren Ihrer lokalen Umgebung wie folgt benötigen:

Geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl an:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Konfigurieren des Bereichs

Sie können den Anrufdatenconnector für einen bestimmten Standort oder die gesamte Skype for Business Server-Bereitstellung mithilfe des cmdlets Set-CsCloudCallDataConnectorConfiguration in der Skype for Business Server-Verwaltungsshell aktivieren. Der folgende Befehl aktiviert beispielsweise den Anrufdatenconnector auf globaler Ebene:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Zusätzlich zu den globalen Einstellungen können Konfigurationseinstellungen für den Anrufdatenconnector dem Standortbereich zugewiesen werden. Dies bietet zusätzliche Verwaltungsflexibilität bei der Überwachung. Beispielsweise kann ein Administrator die Weiterleitung von Anrufdatenconnector für den Standort "Redmond" aktivieren, aber die Anrufdatenconnector-Weiterleitung für den Standort Dublin deaktivieren, wie im folgenden Beispiel gezeigt:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Auf Standortbereich konfigurierte Einstellungen haben Vorrang vor auf globaler Ebene konfigurierten Einstellungen. Angenommen, die Weiterleitung von Anrufdatenconnector ist auf globaler Ebene aktiviert, aber auf Standortseite deaktiviert (für den Standort Redmond). Das bedeutet, dass Die Aufzeichnung von Anrufdetails und QoE-Informationen nicht für Benutzer am Standort Redmond weitergeleitet werden. Benutzer an anderen Standorten (d. h. Von den globalen Einstellungen verwaltete Benutzer anstelle der Standorteinstellungen für Redmond) werden jedoch ihre Aufzeichnung der Anrufdetails und QoE-Informationen weitergeleitet.

Werte für die am häufigsten verwendeten Einstellungen, die vom Anrufdatenconnector verwendet werden, werden in der folgenden Tabelle angezeigt:  

|Eigenschaft|Beschreibung|Standardwert|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Gibt an, ob der Anrufdatenconnector aktiviert ist. Bei True werden Überwachungsdatensätze an die Onlineüberwachung weitergeleitet.  <br/> |$False  <br/> |
| Identität | Bestimmt die Bereichsebene für den Befehl: global oder standort.   | global  |

## <a name="disable-call-data-connector"></a>Deaktivieren des Anrufdatenconnector

Durch das Deaktivieren des Anrufdatenconnector wird weder die Zuordnung des Überwachungsspeichers zum Front-End-Pool aufgehoben noch die Back-End-Überwachungsdatenbank deinstalliert oder anderweitig beeinflusst. Wenn Sie den Anrufdatenconnector deaktivieren, verhindern Sie, dass Skype for Business Server Anrufdaten in die Cloud hochladet. 

Sie deaktivieren den Anrufdatenconnector mithilfe des Set-CsCloudCallDataConnectorConfiguration in der Skype for Business Server-Verwaltungsshell. Der folgende Befehl deaktiviert beispielsweise den Anrufdatenconnector auf globaler Ebene, indem die EnableCallDataConnector-Eigenschaft auf $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Wenn Sie das Hochladen von Anrufdaten in die Cloud fortsetzen möchten, legen Sie die EnableCallDataConnector-Eigenschaft wieder auf $True, wie im folgenden Beispiel gezeigt:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Anzeigen von lokalen Daten über das Onlinedashboard

 Nachdem der Anrufdatenconnector aktiviert ist, können Sie Ihre lokalen Anrufdaten im Anrufanalysedashboard oder im Anrufqualitätsdashboard anzeigen, wie unter  [Verwenden](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) der Anrufanalyse beschrieben, um Probleme mit schlechter Qualität zu beheben und das Anrufqualitätsdashboard für Microsoft Teams und [Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)zu aktivieren und zu verwenden.

## <a name="for-more-information"></a>Weitere Informationen

Für weitere Informationen zu den Cmdlets können Sie den Befehl Get-Help der Skype for Business Server Management Shell verwenden. Zum Beispiel:

Get-Help Get-CsCloudCallDataConnector | mehr

Get-Help Set-CsCloudCallDataConnector | mehr

Get-Help Set-CsCloudCallDataConnectorConfiguration | mehr
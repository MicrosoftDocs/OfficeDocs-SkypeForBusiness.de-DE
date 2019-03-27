---
title: Konfigurieren von SharePoint Server für die Suche nach archivierten Skype for Business-Daten
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Zusammenfassung: Konfigurieren von SharePoint Server, um die Suche nach Daten, die von Exchange Server und Skype für Business Server archiviert.'
ms.openlocfilehash: b9e08c5681b35b71ac7543115ee008a97e207bb7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884978"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Konfigurieren von SharePoint Server für die Suche nach archivierten Skype for Business-Daten
 
**Zusammenfassung:** Konfigurieren von SharePoint Server, um die Suche nach Daten, die von Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server archiviert.
  
Einer der wichtigsten Vorteile zum Speichern von instant messaging und webkonferenzaufzeichnungen in Exchange Server und nicht Skype für Business Server ist, dass das Speichern von Daten in den gleichen Speicherort Administratoren ein einzelnes Tool zum Suchen nach archivierten Exchange-Daten verwenden können und/oder archivierten Skype für Business Server-Daten. Da alle, die die Daten in der gleichen gespeichert werden (Exchange) platzieren kann jedem Tool, das für Exchange Archivdaten suchen kann auch für archivierte Skype für Business Server-Daten suchen.
  
Ein Tool, das die Suche nach archivierten Daten erleichtert ist Microsoft SharePoint Server 2013. Wenn Sie SharePoint verwenden, um nach Skype für Business Server-Daten suchen möchten, müssen Sie zuerst alle Schritte zum Konfigurieren der Exchange-Archivierung in Skype für Business Server ausführen. Nach der Exchange-Server und Skype für Business Server erfolgreich integriert wurden, müssen Sie die Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) klicken Sie dann auf dem SharePoint-Server installieren. Die heruntergeladene Datei (EWSManagedAPI.msi) kann in einem beliebigen Ordner auf Ihrem SharePoint-Server gespeichert werden.
  
Wenn die Datei vollständig heruntergeladen ist, führen Sie auf dem SharePoint-Server folgendes Verfahren aus:
  
1. Öffnen Sie ein Befehlsfenster. Klicken Sie dazu auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** und klicken Sie dann auf **Als Administrator ausführen**.
    
2. Verwenden Sie im Befehlsfenster den Befehl cd, um das aktuelle Verzeichnis in den Ordner zu ändern, in dem die Datei „EWSManagedAPI.msi“ gespeichert wurde. Angenommen, wenn Sie die Datei, um C:\Downloads gespeichert haben Geben Sie im Befehlsfenster den folgenden Befehl ein und drücken Sie die EINGABETASTE:
    
   ```
   cd C:\Downloads
   ```

3. Zum Installieren der API geben Sie den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Nachdem die API installiert wurde, setzen Sie IIS zurück, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:
    
   ```
   iisreset
   ```

Nach der Installation von Exchange-Webdienste müssen Sie dann auf Server-zu-Server-Authentifizierung zwischen SharePoint Server und Exchange Server konfigurieren. Zu diesem Zweck zuerst öffnen Sie die SharePoint-Verwaltungsshell und führen Sie die folgende Reihe von Befehlen:
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Achten Sie darauf, den URI für Ihren AutoErmittlungsdienst zu verwenden. Verwenden Sie nicht den Beispiel-URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1. 
  
Nachdem Sie den tokenherausgeber erstellt und den Sicherheitstokendienst konfiguriert haben, führen Sie diese Befehle, wie sichergestellt werden kann, ersetzen die URL der SharePoint-Website für die Beispiel-URLhttp://atl-sharepoint-001:
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Konfigurieren der Server-zu-Server-Authentifizierung für Exchange Server, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden (unter der Annahme, dass Exchange auf Laufwerk C: installiert wurde, und das alles den Standardordnerpfad verwendet):
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Nach der Konfiguration der partneranwendung wird empfohlen, dass Sie beenden und neu (Internet Information Services, IIS) auf allen Exchange-Postfach und Client Access-Servern starten. Mit einem Befehl wie den folgenden, der den Dienst auf dem Computer Atl-Exchange-001 neu gestartet wird, können Sie IIS neu starten:
  
```
iisreset atl-exchange-001
```

Dieser Befehl kann aus in der Exchange-Verwaltungsshell oder aus einem beliebigen anderen Befehlsfenster ausgeführt werden.
  
Führen Sie dann einen Befehl ähnlich dem folgenden, die dem angegebenen Benutzer (in diesem Beispiel "Kenmyer") das Recht, Ermittlung in Exchange bietet:
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Nachdem zwischen Exchange und SharePoint Server-zu-Server-Authentifizierung hergestellt wurde, besteht der nächste Schritt zum Erstellen einer eDiscovery-Website in SharePoint. Kann durch Ausführen von Befehlen etwa wie folgt aus der SharePoint-Verwaltungsshell erfolgen:
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> „eDiscovery“ steht für „electronic Discovery“ (elektronische Ermittlung) und bezeichnet in der Regel das Durchsuchen von elektronischen Archiven nach Elementen, die in einem Gerichtsverfahren als Beweismittel zulässig sind. 
  
Wenn die neue Website bereit ist, besteht der nächste Schritt so konfigurieren Sie Exchange Server um dementsprechend Quelle für SharePoint zu fungieren. Sie können hierzu auf der Seite SharePoint-Zentraladministration die folgenden Schritte ausführen:
  
1. Klicken Sie auf der Seite „Zentraladministration“ auf **Dienstanwendungen verwalten** und dann auf **Suchdienstanwendung**.
    
2. Klicken Sie auf der Seite „Suchdienstanwendung: Suchverwaltung“ auf **Ergebnisquellen** und dann auf **Neue Ergebnisquelle**.
    
3. Geben Sie im Bereich **Neue Ergebnisquelle** im Feld **Name** einen Namen für die neue Ergebnisquelle ein (z. B. **Microsoft Exchange**). Wählen Sie **Exchange** als die ergebnisquelle **Protokoll**, und geben Sie die Web Services Quell-URL für Ihre Exchange-Server im Feld **Exchange Quell-URL** . Die Quell-URL sollte in etwa wie folgt aussehen:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Stellen Sie sicher, dass **AutoErmittlung verwenden** nicht ausgewählt ist, und klicken Sie auf **OK**.
    
Schließlich erstellen Sie eine neue eDiscovery-Fall und eine neue eDiscovery festlegen, indem Sie die folgende Schritte aus, von der Ermittlung der SharePoint-Website (z. B. ausfüllenhttps://atl-sharepoint-001/sites/discovery):
  
1. Klicken Sie auf der Seite **Websiteinhalte** auf Neuen Fall erstellen.
    
2. Geben Sie auf der Seite „Websiteinhalte: Neue SharePoint-Website“ im Feld **Titel** den E-Mail-Alias des Benutzers (z. B. **kenmyer**) ein und geben Sie im Feld **Websiteadresse** dieselbe URL ein. Das Ergebnis ist eine ähnliche URL wie die folgende:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Klicken Sie auf **Erstellen**.
    
4. Wenn die Seite „eDiscovery-Satz“ angezeigt wird, klicken Sie unter **Identifizieren und beibehalten: eDiscovery-Sätze** auf **Neues Element**.
    
5. Geben Sie auf der Seite „Neu: eDiscovery-Satz“ im Feld **Name für eDiscovery-Satz** den E-Mail-Alias des Benutzers ein. Geben Sie **eDiscovery Lync\\*** im **Filter** ein, und klicken Sie dann auf **Hinzufügen &amp; Quellen verwalten**.
    
6. Auf der hinzufügen &amp; Quellen verwalten Seite, geben Sie in das erste Textfeld unter **Postfächer**e-Mail-Alias des Benutzers ein. Klicken Sie neben dem Textfeld auf das Symbol „Postfach überprüfen“, um sicherzustellen, dass SharePoint eine Verbindung mit dem angegebenen Postfach herstellen kann.
    
7. Klicken Sie anschließend auf **OK**.
    
8. Klicken Sie auf der Seite „eDiscovery-Satz“ auf **Speichern**, um den neuen eDiscovery-Satz zu speichern.
    
An dieser Stelle können Sie das angegebene Postfach (Kenmyer) durchsuchen und/oder aktivieren In-Place-Haltebereiche genauso wie bei anderen SharePoint Inhalte oder ergebnisquellen Quellen dies.
  


---
title: Konfigurieren SharePoint Servers für die Suche nach archivierten Skype for Business Daten
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Zusammenfassung: Konfigurieren von SharePoint Server, um nach Daten zu suchen, die von Exchange Server und Skype for Business Server archiviert wurden.'
---

# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Konfigurieren SharePoint Servers für die Suche nach archivierten Skype for Business Daten
 
**Zusammenfassung:** Konfigurieren Sie SharePoint Server, um nach Daten zu suchen, die bis Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server archiviert wurden.
  
Einer der hauptvorteile beim Speichern von Chat- und Webkonferenztranskripten in Exchange Server anstelle von Skype for Business Server besteht darin, dass administratoren mithilfe eines einzigen Tools nach archivierten Exchange und/oder archivierten Daten suchen können. Skype for Business Server Daten. Da alle Daten am selben Ort (Exchange) gespeichert sind, kann jedes Tool, das nach archivierten Exchange Daten suchen kann, auch nach archivierten Skype for Business Server Daten suchen.
  
Ein Tool, das die Suche nach archivierten Daten erleichtert, ist Microsoft SharePoint Server 2013. Wenn Sie SharePoint verwenden möchten, um nach Skype for Business Server Daten zu suchen, müssen Sie zunächst alle Schritte zum Konfigurieren Exchange Archivierung in Skype for Business Server ausführen. Nachdem Exchange Server und Skype for Business Server erfolgreich integriert wurden, müssen Sie die [Exchange Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) auf Ihrem SharePoint Server installieren. Die heruntergeladene Datei (EWSManagedAPI.msi) kann in einem beliebigen Ordner auf Ihrem SharePoint Server gespeichert werden.
  
Nachdem die Datei vollständig heruntergeladen wurde, führen Sie auf dem SharePoint-Server folgendes Verfahren aus:
  
1. Öffnen Sie ein Befehlsfenster. Klicken Sie dazu auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.
    
2. Verwenden Sie im Befehlsfenster den Befehl cd, um das aktuelle Verzeichnis zu dem Ordner zu ändern, in dem die Datei "EWSManagedAPI.msi" gespeichert wurde. Wenn Sie die Datei beispielsweise in "C:\Downloads" gespeichert haben, geben Sie den folgenden Befehl im Befehlsfenster ein, und drücken Sie dann die EINGABETASTE:
    
   ```console
   cd C:\Downloads
   ```

3. Geben Sie zum Installieren der API den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Nachdem die API installiert wurde, setzen Sie IIS zurück, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:
    
   ```console
   iisreset
   ```

Nachdem Exchange Webdienste installiert wurde, müssen Sie die Server-zu-Server-Authentifizierung zwischen SharePoint Server und Exchange Server konfigurieren. Öffnen Sie dazu zunächst die SharePoint Verwaltungsshell, und führen Sie den folgenden Befehlssatz aus:
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Achten Sie darauf, den URI für Ihren AutoErmittlungsdienst zu verwenden. Verwenden Sie nicht den Beispiel-URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1. 
  
Nachdem Sie den Tokenherausgeber erstellt und den Tokendienst konfiguriert haben, führen Sie diese Befehle aus, und stellen Sie sicher, dass Sie die URL Ihrer SharePoint-Website durch die Beispiel-URL `http://atl-sharepoint-001`ersetzen:
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Um die Server-zu-Server-Authentifizierung für Exchange Server zu konfigurieren, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus (vorausgesetzt, dass Exchange auf Laufwerk C installiert wurde und den Standardordnerpfad verwendet):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Nach dem Konfigurieren der Partneranwendung wird empfohlen, Internetinformationsdienste (IIS) auf allen Exchange Postfach- und Clientzugriffsservern zu beenden und neu zu starten. Sie können IIS mithilfe eines Befehls wie diesem neu starten, der den Dienst auf dem Computer atl-exchange-001 neu startet:
  
```powershell
iisreset atl-exchange-001
```

Dieser Befehl kann in der Exchange Verwaltungsshell oder in einem beliebigen anderen Befehlsfenster ausgeführt werden.
  
Führen Sie als Nächstes einen Befehl ähnlich dem folgenden aus, der dem angegebenen Benutzer (in diesem Beispiel Kenmyer) das Recht gibt, die Ermittlung auf Exchange durchzuführen:
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Nachdem die Server-zu-Server-Authentifizierung zwischen Exchange und SharePoint eingerichtet wurde, besteht der nächste Schritt darin, eine eDiscovery-Website in SharePoint zu erstellen. Dies kann durch Ausführen von Befehlen erfolgen, die denen in der SharePoint Verwaltungsshell ähneln:
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "eDiscovery" steht für "electronic Discovery" (elektronische Ermittlung) und bezeichnet in der Regel das Durchsuchen von elektronischen Archiven nach Elementen, die in einem Gerichtsverfahren als Beweismittel zulässig sind. 
  
Wenn die neue Website bereit ist, besteht der nächste Schritt darin, Exchange Server so zu konfigurieren, dass sie als Ergebnisquelle für SharePoint fungiert. Führen Sie dazu das folgende Verfahren auf der Seite SharePoint Zentraladministration aus:
  
1. Klicken Sie auf der Seite "Zentraladministration" auf **Dienstanwendungen verwalten** und dann auf **Suchdienstanwendung**.
    
2. Klicken Sie auf der Seite  "Suchdienstanwendung: Suchverwaltung" auf **Ergebnisquellen** und dann auf **Neue Ergebnisquelle**.
    
3. Geben Sie im Bereich **Neue Ergebnisquelle** im Feld **Name** einen Namen für die neue Ergebnisquelle ein (z. B. **Microsoft Exchange**). Wählen Sie **Exchange** als Ergebnisquellprotokoll aus, und geben Sie dann die Webdienstquell-URL für Ihren Exchange-Server in das Feld **Exchange Quell-URL** ein. Die Quell-URL sollte in etwa wie folgt aussehen:
    
    `https://atl-exchange-001.litwareinc.com/ews/exchange.asmx`
    
4. Stellen Sie sicher, dass **AutoErmittlung verwenden** nicht ausgewählt ist, und klicken Sie dann **OK**.
    
Erstellen Sie schließlich einen neuen eDiscovery-Fall und einen neuen eDiscovery-Satz, indem Sie das folgende Verfahren auf der SharePoint Discovery-Website ausführen (z. B.`https://atl-sharepoint-001/sites/discovery`):
  
1. Klicken Sie auf der Seite "Websiteinhalte" auf **Neuen Fall erstellen**.
    
2. Geben Sie auf der Seite "Websiteinhalte: Neue SharePoint-Website" im Feld **Titel** den E-Mail-Alias des Benutzers (z. B. **kenmyer**) ein, und geben Sie im Feld **Websiteadresse** dieselbe URL ein. Das Ergebnis ist eine ähnliche URL wie die folgende:
    
    `https://atl-sharepoint-001/sites/eDiscovery/kenmyer`
    
3. Klicken Sie auf **Erstellen**.
    
4. Wenn die Seite "eDiscovery-Satz" angezeigt wird, klicken Sie unter **Identifizieren und beibehalten: eDiscovery-Sätze** auf **Neues Element**.
    
5. Geben Sie auf der Seite "Neu: eDiscovery-Satz" im Feld **Name für eDiscovery-Satz** den E-Mail-Alias des Benutzers ein. Geben Sie **eDiscovery Lync\\** _ in das Feld _ *Filter** ein, und klicken Sie dann auf **"Quellen verwalten hinzufügen&amp;**".
    
6. Geben Sie auf der Seite "Quellen &amp; verwalten" den E-Mail-Alias des Benutzers im ersten Textfeld unter **"Postfächer" ein**. Klicken Sie neben dem Textfeld auf das Symbol "Postfach überprüfen", um sicherzustellen, dass SharePoint eine Verbindung mit dem angegebenen Postfach herstellen kann.
    
7. Klicken Sie auf **OK**.
    
8. Klicken Sie auf der Seite "eDiscovery-Satz" auf **Speichern**, um den neuen eDiscovery-Satz zu speichern.
    
An diesem Punkt können Sie das angegebene Postfach (kenmyer) durchsuchen und/oder In-Place auf die gleiche Weise für alle anderen SharePoint Inhalte oder Ergebnisquellen aktivieren.
  


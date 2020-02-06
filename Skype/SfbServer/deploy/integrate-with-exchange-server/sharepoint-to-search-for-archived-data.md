---
title: Konfigurieren von SharePoint Server für die Suche nach archivierten Skype for Business-Daten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Zusammenfassung: Konfigurieren Sie SharePoint Server für die Suche nach Daten, die von Exchange Server und Skype for Business Server archiviert werden.'
ms.openlocfilehash: 1ca6ee7f398ddc8e0d9b8d51658dd65556225490
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797016"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Konfigurieren von SharePoint Server für die Suche nach archivierten Skype for Business-Daten
 
**Zusammenfassung:** Konfigurieren Sie SharePoint Server für die Suche nach Daten, die von Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server archiviert werden.
  
Einer der Hauptvorteile für das Speichern von Instant Messaging-und Webkonferenz Protokollen in Exchange Server anstelle von Skype for Business Server besteht darin, dass Administratoren mithilfe eines einzigen Tools nach archivierten Exchange-Daten und/oder archivierten Skype for Business Server-Daten suchen können. Da alle Daten an derselben Stelle (Exchange) gespeichert sind, können alle Tools, die nach archivierten Exchange-Daten suchen können, auch nach archivierten Skype for Business Server-Daten suchen.
  
Ein Tool, mit dem Sie nach archivierten Daten einfach suchen können, ist Microsoft SharePoint Server 2013. Wenn Sie SharePoint für die Suche nach Skype for Business Server-Daten verwenden möchten, müssen Sie zunächst alle Schritte ausführen, die bei der Konfiguration der Exchange-Archivierung in Skype for Business Server erforderlich sind. Nachdem Exchange Server und Skype for Business Server erfolgreich integriert wurden, müssen Sie die verwaltete API für Exchange [-Webdienste](https://go.microsoft.com/fwlink/p/?LinkId=258305) auf dem SharePoint-Server installieren. Die heruntergeladene Datei (EWSManagedAPI.msi) kann in einem beliebigen Ordner auf Ihrem SharePoint-Server gespeichert werden.
  
Wenn die Datei vollständig heruntergeladen ist, führen Sie auf dem SharePoint-Server folgendes Verfahren aus:
  
1. Öffnen Sie ein Befehlsfenster. Klicken Sie dazu auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** und klicken Sie dann auf **Als Administrator ausführen**.
    
2. Verwenden Sie im Befehlsfenster den Befehl cd, um das aktuelle Verzeichnis in den Ordner zu ändern, in dem die Datei „EWSManagedAPI.msi“ gespeichert wurde. Wenn Sie beispielsweise die Datei auf C:\Downloads gespeichert haben, geben Sie den folgenden Befehl im Befehlsfenster ein, und drücken Sie dann die EINGABETASTE:
    
   ```console
   cd C:\Downloads
   ```

3. Zum Installieren der API geben Sie den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Nachdem die API installiert wurde, setzen Sie IIS zurück, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:
    
   ```console
   iisreset
   ```

Nachdem Exchange-Webdienste installiert wurden, müssen Sie die Server-zu-Server-Authentifizierung zwischen SharePoint Server und Exchange Server konfigurieren. Öffnen Sie dazu zunächst die SharePoint-Verwaltungsshell, und führen Sie die folgenden Befehlssätze aus:
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Achten Sie darauf, den URI für Ihren AutoErmittlungsdienst zu verwenden. Verwenden Sie den Beispiel-URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1nicht. 
  
Nachdem Sie den Token-Aussteller erstellt und den Tokendienst konfiguriert haben, führen Sie diese Befehle aus, und stellen Sie sicher, dass Sie die URL Ihrer SharePoint-Website für die Beispiel-URL ersetzen.http://atl-sharepoint-001:
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Wenn Sie die Server-zu-Server-Authentifizierung für Exchange Server konfigurieren möchten, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen ähnlichen Befehl aus (vorausgesetzt, Exchange wurde auf Laufwerk C: installiert und verwendet den Standardordnerpfad):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Nachdem Sie die Partneranwendung konfiguriert haben, empfiehlt es sich, Internet Informationsdienste (IIS) auf allen Exchange-Post Fach-und Clientzugriffsservern zu beenden und neu zu starten. Sie können IIS neu starten, indem Sie einen ähnlichen Befehl verwenden, mit dem der Dienst auf dem Computer "ATL-Exchange-001" neu gestartet wird:
  
```powershell
iisreset atl-exchange-001
```

Dieser Befehl kann in der Exchange-Verwaltungsshell oder in einem anderen Befehlsfenster ausgeführt werden.
  
Führen Sie als nächstes einen Befehl aus, der dem folgenden ähnelt, wodurch der angegebene Benutzer (in diesem Beispiel kenmyer) das Recht hat, eine Ermittlung in Exchange durchzuführen:
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Nachdem die Server-zu-Server-Authentifizierung zwischen Exchange und SharePoint hergestellt wurde, besteht der nächste Schritt darin, eine eDiscovery-Website in SharePoint zu erstellen. Dies kann durch Ausführen von Befehlen ähnlich wie in der SharePoint-Verwaltungsshell erfolgen:
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> „eDiscovery“ steht für „electronic Discovery“ (elektronische Ermittlung) und bezeichnet in der Regel das Durchsuchen von elektronischen Archiven nach Elementen, die in einem Gerichtsverfahren als Beweismittel zulässig sind. 
  
Wenn die neue Website fertig ist, besteht der nächste Schritt darin, Exchange Server so zu konfigurieren, dass Sie als ergebnisquelle für SharePoint fungiert. Sie können dies tun, indem Sie auf der Seite SharePoint-zentral Administration die folgenden Schritte ausführen:
  
1. Klicken Sie auf der Seite „Zentraladministration“ auf **Dienstanwendungen verwalten** und dann auf **Suchdienstanwendung**.
    
2. Klicken Sie auf der Seite „Suchdienstanwendung: Suchverwaltung“ auf **Ergebnisquellen** und dann auf **Neue Ergebnisquelle**.
    
3. Geben Sie im Bereich **Neue Ergebnisquelle** im Feld **Name** einen Namen für die neue Ergebnisquelle ein (z. B. **Microsoft Exchange**). Wählen Sie **Exchange** als Ergebnis Quell **Protokoll**aus, und geben Sie dann im Feld **Exchange-Quell-URL** die URL des Webdienste-Quellcodes für Ihren Exchange-Server ein. Die Quell-URL sollte in etwa wie folgt aussehen:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Stellen Sie sicher, dass **AutoErmittlung verwenden** nicht ausgewählt ist, und klicken Sie auf **OK**.
    
Erstellen Sie schließlich einen neuen eDiscovery-Fall und einen neuen eDiscovery-Satz, indem Sie das folgende Verfahren auf der SharePoint-Ermittlungs Website ausführen (beispielsweisehttps://atl-sharepoint-001/sites/discovery):
  
1. Klicken Sie auf der Seite **Websiteinhalte** auf Neuen Fall erstellen.
    
2. Geben Sie auf der Seite „Websiteinhalte: Neue SharePoint-Website“ im Feld **Titel** den E-Mail-Alias des Benutzers (z. B. **kenmyer**) ein und geben Sie im Feld **Websiteadresse** dieselbe URL ein. Das Ergebnis ist eine ähnliche URL wie die folgende:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Klicken Sie auf **Erstellen**.
    
4. Wenn die Seite „eDiscovery-Satz“ angezeigt wird, klicken Sie unter **Identifizieren und beibehalten: eDiscovery-Sätze** auf **Neues Element**.
    
5. Geben Sie auf der Seite „Neu: eDiscovery-Satz“ im Feld **Name für eDiscovery-Satz** den E-Mail-Alias des Benutzers ein. Geben Sie **eDiscovery\\lync*** in das Feld **Filter** ein, und klicken Sie dann auf **Verwalten von Quellen hinzufügen &amp; **.
    
6. Geben Sie auf &amp; der Seite Manage sources hinzufügen den e-Mail-Alias des Benutzers im ersten Textfeld unter **Postfächer**ein. Klicken Sie neben dem Textfeld auf das Symbol „Postfach überprüfen“, um sicherzustellen, dass SharePoint eine Verbindung mit dem angegebenen Postfach herstellen kann.
    
7. Klicken Sie anschließend auf **OK**.
    
8. Klicken Sie auf der Seite „eDiscovery-Satz“ auf **Speichern**, um den neuen eDiscovery-Satz zu speichern.
    
An diesem Punkt können Sie das angegebene Postfach (kenmyer) durchsuchen und/oder in-situ-Speicher auf die gleiche Weise aktivieren wie für andere SharePoint-Inhalte oder-Ergebnisquellen.
  


---
title: 'Lync Server 2013: Konfigurieren Microsoft SharePoint Server 2013 für die Suche nach archivierten lync Server 2013 Daten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04e9599e0790c3d3468273ba27ea26f28ed3d766
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>Konfigurieren Microsoft SharePoint Server 2013 für die Suche nach archivierten Microsoft lync Server 2013 Daten

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-04_

Einer der Hauptvorteile für das Speichern von Instant Messaging-und Webkonferenz-Transkripten in Microsoft Exchange Server 2013 anstelle von Microsoft lync Server 2013 besteht darin, dass Administratoren mithilfe eines einzigen Tools nach archivierten Exchange-Daten suchen und/oder lync Server Daten archiviert haben. Da alle Daten an derselben Stelle (Exchange) gespeichert werden, kann jedes Tool, das nach archivierten Exchange-Daten suchen kann, auch nach archivierten lync Server Daten suchen.

Ein Tool, mit dem die Suche nach archivierten Daten erleichtert wird, ist Microsoft SharePoint Server 2013. Wenn Sie SharePoint zum Suchen nach lync Server Daten verwenden möchten, müssen Sie zunächst alle Schritte zum Konfigurieren der Exchange-Archivierung in lync Server durchführen. Nachdem Exchange 2013 und lync Server 2013 erfolgreich integriert wurden, müssen Sie die Exchange Webdienste Managed API-Version 2,0 auf Ihrem SharePoint Server installieren; das Setupprogramm für diese API kann im Microsoft Download Center heruntergeladen werden ([https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305)). Die heruntergeladene Datei (Datei "ewsmanagedapi. msi) kann in einem beliebigen Ordner auf Ihrem SharePoint-Server gespeichert werden.

Nachdem die Datei vollständig heruntergeladen wurde, führen Sie auf dem SharePoint-Server folgendes Verfahren aus:

1.  Öffnen Sie ein Befehlsfenster. Klicken Sie dazu auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

2.  Verwenden Sie im Befehlsfenster den Befehl **cd**, um das aktuelle Verzeichnis zu dem Ordner zu ändern, in dem die Datei "EWSManagedAPI.msi" gespeichert wurde. Wenn Sie die Datei beispielsweise in C:\\Downloads gespeichert haben, geben Sie den folgenden Befehl in das Befehlsfenster ein, und drücken Sie dann die EINGABETASTE:
    
        cd C:\Downloads

3.  Zum Installieren der API geben Sie den folgenden Befehl ein und drücken dann die EINGABETASTE:
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  Nachdem die API installiert wurde, setzen Sie IIS zurück, indem Sie folgenden Befehl eingeben und die EINGABETASTE drücken:
    
        iisreset

Nachdem Sie Exchange Webdienste installiert haben, müssen Sie die Server-zu-Server-Authentifizierung zwischen SharePoint Server 2013 und Exchange 2013 konfigurieren. Öffnen Sie dazu zunächst die SharePoint 2013-Verwaltungsshell, und führen Sie den folgenden Befehl aus:

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> Achten Sie darauf, den URI für Ihren AutoErmittlungsdienst zu verwenden. Verwenden Sie nicht den Beispiel- https://autodiscover.litwareinc.com/autodiscover/metadata/json/1URI.



</div>

Nachdem Sie den Token-Aussteller erstellt und den Tokendienst konfiguriert haben, führen Sie diese Befehle aus, und stellen Sie sicher, dass Sie die URL Ihrer SharePoint-Website für die Beispiel-URL ersetzen.http://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Zum Konfigurieren der Server-zu-Server-Authentifizierung für Exchange 2013 öffnen Sie den Exchange-Verwaltungsshell und führen Sie einen Befehl wie den folgenden aus (vorausgesetzt, dass Exchange auf Laufwerk C: installiert wurde und der Standardordnerpfad verwendet wird):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

Nach dem Konfigurieren der Partneranwendung wird empfohlen, Internet Information Services (IIS) auf allen Exchange-Postfachservern und Clientzugriffsservern zu beenden und neu zu starten. Sie können IIS mithilfe eines Befehls, der dem folgenden ähnelt, neu starten, um den Dienst auf dem Computer mit ATL-Exchange-001 neu zu starten:

    iisreset atl-exchange-001

Dieser Befehl kann in der Exchange-Verwaltungsshell oder in einem anderen Befehlsfenster ausgeführt werden.

Führen Sie als nächstes einen Befehl wie den folgenden aus, der dem angegebenen Benutzer (in diesem Beispiel kenmyer) das Recht gibt, die Ermittlung in Exchange durchzuführen:

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Nachdem die Server-zu-Server-Authentifizierung zwischen Exchange und SharePoint hergestellt wurde, besteht der nächste Schritt darin, eine eDiscovery-Website in SharePoint zu erstellen. Dies kann durch Ausführen von Befehlen ähnlich wie im SharePoint-Verwaltungsshell geschehen:

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> "eDiscovery" steht für "electronic Discovery" (elektronische Ermittlung) und bezeichnet in der Regel das Durchsuchen von elektronischen Archiven nach Elementen, die in einem Gerichtsverfahren als Beweismittel zulässig sind.



</div>

Wenn die neue Website verfügbar ist, besteht der nächste Schritt darin, Exchange 2013 zu konfigurieren, die als ergebnisquelle für SharePoint fungieren. Sie können dies tun, indem Sie das folgende Verfahren auf der Seite SharePoint 2013 zentral Administration ausführen:

1.  Klicken Sie auf der Seite "Zentraladministration" auf **Dienstanwendungen verwalten** und dann auf **Suchdienstanwendung**.

2.  Klicken Sie auf der Seite  "Suchdienstanwendung: Suchverwaltung" auf **Ergebnisquellen** und dann auf **Neue Ergebnisquelle**.

3.  Geben Sie im Bereich **Neue Ergebnisquelle ** im Feld **Name** einen Namen für die neue Ergebnisquelle ein (z. B. **Microsoft Exchange**). Wählen Sie **Exchange** als Ergebnis Quell **Protokoll**aus, und geben Sie dann im Feld **Exchange-Quell-URL** die Webdienste-Quell-URL für Ihren Exchange-Server ein. Die Quell-URL sollte in etwa wie folgt aussehen:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  Stellen Sie sicher, dass **AutoErmittlung verwenden** nicht ausgewählt ist, und klicken Sie dann **OK**.

Erstellen Sie schließlich einen neuen eDiscovery-Fall und eine neue eDiscovery-Gruppe, indem Sie das folgende Verfahren auf der SharePoint Discovery-Website ausführen (beispielsweisehttps://atl-sharepoint-001/sites/discovery):

1.  Klicken Sie auf der Seite "Websiteinhalte" auf **Neuen Fall erstellen**.

2.  Geben Sie auf der Seite "Websiteinhalte: Neue SharePoint-Website" im Feld **Titel** den E-Mail-Alias des Benutzers (z. B. **kenmyer**) ein, und geben Sie im Feld **Websiteadresse** dieselbe URL ein. Das Ergebnis ist eine ähnliche URL wie die folgende:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  Klicken Sie auf **Erstellen**.

4.  Wenn die Seite "eDiscovery-Satz" angezeigt wird, klicken Sie unter **Identifizieren und beibehalten: eDiscovery-Sätze** auf **Neues Element**.

5.  Geben Sie auf der Seite "Neu: eDiscovery-Satz" im Feld **Name für eDiscovery-Satz** den E-Mail-Alias des Benutzers ein. Geben Sie **eDiscovery\* lync** in das Feld **Filter** ein, und klicken Sie dann auf **& Quellen verwalten hinzufügen**.

6.  Geben Sie auf der Seite "Quellen hinzufügen und verwalten" unter **Postfächer** im ersten Textfeld den den E-Mail-Alias des Benutzers ein. Klicken Sie neben dem Textfeld auf das Symbol "Postfach überprüfen", um sicherzustellen, dass SharePoint eine Verbindung mit dem angegebenen Postfach herstellen kann.

7.  Klicken Sie auf **OK**.

8.  Klicken Sie auf der Seite "eDiscovery-Satz" auf **Speichern**, um den neuen eDiscovery-Satz zu speichern.

An dieser Stelle können Sie das angegebene Postfach (kenmyer) durchsuchen und/oder in-Place-Aufbewahrungen auf die gleiche Weise aktivieren wie für andere SharePoint-Inhalte oder-Ergebnisquellen.

</div>

<span> </span>

</div>

</div>

</div>


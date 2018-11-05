---
title: Konfigurieren von Microsoft SharePoint Server 2013 zum Suchen nach archivierten Microsoft Lync Server 2013-Daten
TOCTitle: Konfigurieren von Microsoft SharePoint Server 2013 zum Suchen nach archivierten Microsoft Lync Server 2013-Daten
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49890639
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Microsoft SharePoint Server 2013 zum Suchen nach archivierten Microsoft Lync Server 2013-Daten

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Ein Hauptvorteil des Speicherns von Instant Messaging- und Webkonferenzaufzeichnungen in Microsoft Exchange Server 2013 statt in Microsoft Lync Server 2013 besteht darin, dass das Speichern von Daten am selben Speicherort Administratoren ermöglicht, ein einzelnes Tool zum Suchen nach archivierten Exchange-Daten und/oder archivierten Lync Server-Daten zu verwenden. Da sich alle Daten am selben Speicherort befinden (Exchange) kann jedes Tool für die Suche nach archivierten Exchange-Daten auch zur Suche nach archivierten Lync Server-Daten verwendet werden.

Mit Microsoft SharePoint Server 2013 können archivierte Daten einfach durchsucht werden. Wenn Sie SharePoint für die Suche nach Lync Server-Daten verwenden möchten, müssen Sie zunächst alle Schritte der Konfiguration der Exchange-Archivierung in Lync Server ausführen. Nachdem Exchange 2013 und Lync Server 2013 erfolgreich integriert wurden, müssen Sie Exchange Web Services Managed API Version 2.0 auf Ihrem SharePoint-Server installieren. Das Setupprogramm für diese API kann im Microsoft Download Center ([http://go.microsoft.com/fwlink/?linkid=258305\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=258305%26clcid=0x407)). heruntergeladen werden. Die heruntergeladene Datei (EWSManagedAPI.msi) kann in einem beliebigen Ordner auf Ihrem SharePoint-Server gespeichert werden.

Nachdem die Datei vollständig heruntergeladen wurde, führen Sie auf dem SharePoint-Server folgendes Verfahren aus:

1.  Öffnen Sie ein Befehlsfenster. Klicken Sie dazu auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.

2.  Verwenden Sie im Befehlsfenster den Befehl **cd**, um das aktuelle Verzeichnis zu dem Ordner zu ändern, in dem die Datei "EWSManagedAPI.msi" gespeichert wurde. Wenn Sie die Datei beispielsweise in "C:\\Downloads" gespeichert haben, geben Sie im Befehlsfenster den folgenden Befehl ein, und drücken Sie die EINGABETASTE:
    
        cd C:\Downloads

3.  Zum Installieren der API geben Sie den folgenden Befehl ein und drücken dann die EINGABETASTE:
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  Nachdem die API installiert wurde, setzen Sie IIS zurück, indem Sie folgenden Befehl eingeben und die EINGABETASTE drücken:
    
        iisreset

Nachdem Exchange Web Services installiert wurde, müssen Sie die Server-zu-Server-Authentifizierung zwischen SharePoint Server 2013 und Exchange 2013 konfigurieren. Öffnen Sie dazu die SharePoint 2013-Verwaltungsshell und Management Shell, und führen Sie den folgenden Befehlssatz aus:

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()


> [!NOTE]
> Achten Sie darauf, den URI für Ihren AutoErmittlungsdienst zu verwenden. Verwenden Sie nicht die Beispiels-URI "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1".



Nachdem Sie den Tokenherausgeber erstellt und den Tokendienst konfiguriert haben, führen Sie diese Befehle aus. Ersetzen Sie dabei die Beispiels-URL "http://atl-sharepoint-001" durch die URL Ihrer SharePoint-Website:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Zum Konfigurieren der Server-zu-Server-Authentifizierung für Exchange 2013 öffnen Sie die Exchange-Verwaltungsshell und führen einen ähnlichen Befehl wie den folgenden aus (vorausgesetzt, Exchange wurde auf dem Laufwerk "C:" installiert und verwendet den Standardordnerpfad):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

Nach dem Konfigurieren der Partneranwendung wird empfohlen, IIS (Internet Information Services auf all Ihren Exchange-Postfach und -Clientzugriffsservern anzuhalten und neu zu starten. Sie können IIS mit einem Befehl wie diesen starten. Dadurch wird der Dienst auf dem Computer "atl-exchange-001" neu gestartet:

    iisreset atl-exchange-001

Dieser Befehl kann in der Exchange-Verwaltungsshell oder einem beliebigen anderen Befehlsfenster ausgeführt werden.

Führen Sie danach einen ähnlichen Befehl wie den folgenden aus, der dem angegebenen Benutzer (in diesem Beispiel "kenmyer") das Recht zur Verwendung der Ermittlung in Exchange gewährt:

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Nachdem die Server-zu-Server-Authentifizierung zwischen Exchange und SharePoint eingerichtet wurde, folgt als nächster Schritt das Erstellen einer eDiscovery-Website in SharePoint. Dazu werden in der SharePoint-Verwaltungsshell ähnliche Befehle wie die folgenden ausgeführt:

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"


> [!NOTE]
> "eDiscovery" steht für "electronic Discovery" (elektronische Ermittlung) und bezeichnet in der Regel das Durchsuchen von elektronischen Archiven nach Elementen, die in einem Gerichtsverfahren als Beweismittel zulässig sind.



Wenn die neue Website fertig ist, folgt als nächster Schritt die Konfiguration von Exchange 2013 als Ergebnisquelle für SharePoint. Führen Sie dazu in der SharePoint 2013-Zentraladministration folgendes Verfahren aus:

1.  Klicken Sie auf der Seite "Zentraladministration" auf **Dienstanwendungen verwalten** und dann auf **Suchdienstanwendung**.

2.  Klicken Sie auf der Seite "Suchdienstanwendung: Suchverwaltung" auf **Ergebnisquellen** und dann auf **Neue Ergebnisquelle**.

3.  Geben Sie im Bereich **Neue Ergebnisquelle** im Feld **Name** einen Namen für die neue Ergebnisquelle ein (z. B. **Microsoft Exchange**). Wählen Sie **Exchange** als **Ergebnisquellenprotokoll**, und geben Sie dann die Webdienst-Quell-URL für Ihren Exchange-Server in das Feld **Exchange-Quell-URL** ein. Die Quell-URL sollte in etwa wie folgt aussehen:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  Stellen Sie sicher, dass **AutoErmittlung verwenden** nicht ausgewählt ist, und klicken Sie dann **OK**.

Erstellen Sie schließlich einen neuen AutoErmittlungs-Fall und einen neuen AutoErmittlungs-Satz, indem Sie auf der SharePoint Discovery-Website (z. B. "https://atl-sharepoint-001/sites/discovery) folgendes Verfahren ausführen:

1.  Klicken Sie auf der Seite "Websiteinhalte" auf **Neuen Fall erstellen**.

2.  Geben Sie auf der Seite "Websiteinhalte: Neue SharePoint-Website" im Feld **Titel** den E-Mail-Alias des Benutzers (z. B. **kenmyer**) ein, und geben Sie im Feld **Websiteadresse** dieselbe URL ein. Das Ergebnis ist eine ähnliche URL wie die folgende:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  Klicken Sie auf **Erstellen**.

4.  Wenn die Seite "eDiscovery-Satz" angezeigt wird, klicken Sie unter **Identifizieren und beibehalten: eDiscovery-Sätze** auf **Neues Element**.

5.  Geben Sie auf der Seite "Neu: eDiscovery-Satz" im Feld **Name für eDiscovery-Satz** den E-Mail-Alias des Benutzers ein. Geben Sie im Feld **FiltereDiscovery Lync\*** ein, und klicken Sie dann auf **Quellen hinzufügen und verwalten**.

6.  Geben Sie auf der Seite "Quellen hinzufügen und verwalten" unter **Postfächer** im ersten Textfeld den den E-Mail-Alias des Benutzers ein. Klicken Sie neben dem Textfeld auf das Symbol "Postfach überprüfen", um sicherzustellen, dass SharePoint eine Verbindung mit dem angegebenen Postfach herstellen kann.

7.  Klicken Sie auf **OK**.

8.  Klicken Sie auf der Seite "eDiscovery-Satz" auf **Speichern**, um den neuen eDiscovery-Satz zu speichern.

Jetzt können Sie das angegebene Postfach (kenmyer) durchsuchen und/oder das Compliance-Archiv ebenso aktivieren wie für andere SharePoint-Inhalte oder Ergebnisquellen.


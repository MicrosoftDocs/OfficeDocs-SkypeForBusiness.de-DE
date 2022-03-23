---
title: Durchführen einer eDiscovery-Untersuchung von Inhalten
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: Hier erfahren Sie, was zu tun ist, wenn Sie eDiscovery ausführen müssen, z. B. wenn Sie alle elektronisch gespeicherten Informationen für juristische Verfahren einreichen müssen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 85124047c5bb894eb4eb4177fad0e0cfee53dfc3
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711769"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams

Große Unternehmen werden häufig mit hohen Bußerforderungen rechnen müssen, die die Übermittlung aller elektronisch gespeicherten Informationen erfordern. Microsoft Teams-Inhalt kann während eDiscovery-Untersuchungen durchsucht und verwendet werden.

## <a name="overview"></a>Übersicht

Alle Microsoft Teams 1:1- oder Gruppenchats werden bis zu den Postfächern der jeweiligen Benutzer journaliert. Alle Standardkanalnachrichten werden bis zum Gruppenpostfach, das das Team darstellt, journaliert. In Standardkanäle hochgeladene Dateien werden unter die eDiscovery-Funktionalität für SharePoint Online und OneDrive for Business.

eDiscovery von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [eDiscovery privater Kanäle](#ediscovery-of-private-and-shared-channels).

Nicht alle Teams sind eDiscoverable. Die folgende Tabelle enthält die Inhaltstypen, nach der Sie mithilfe der Microsoft eDiscovery-Tools suchen können:

| Inhaltstyp | eDiscoverable | Hinweise |
|:--- | :--- |:--- |
|Audioaufzeichnungen | Nein | |
|Karteninhalt|Ja|Weitere [Informationen finden Sie unter Suchen nach](#search-for-card-content) Karteninhalten.|
|Chatlinks | Ja | |
|Chatnachrichten | Ja |Dies umfasst Inhalte in Teams Standardkanälen, 1:1-Chats, 1:N-Gruppenchats und Chats mit Gastbenutzerteilnehmern.  |
|Codeausschnitte | Nein | |
|Bearbeitete Nachrichten | Ja | Wenn der Benutzer in der Warteschleife ist, bleiben auch frühere Versionen bearbeiteter Nachrichten erhalten. |
|Emojis, GIFs und Aufkleber | Ja | |
|Feedbenachrichtigungen | Nein | |
|Inlinebilder | Ja | |
|Endloskomponenten| Ja|Der Inhalt einer Schleifenkomponente wird in einer FLUID-Datei gespeichert, die im OneDrive for Business des Benutzers gespeichert ist, der die Komponente für Schleife sendet. Dies bedeutet, dass Sie eine OneDrive bei der Suche nach Inhalten in Schleifenkomponenten als Datenquelle verwenden müssen. |
|Chatunterhaltungen in Besprechungen | Ja | |
|<sup>Besprechungsmetadaten1</sup> | Ja |  |
|Name des Kanals | Ja | |
|Chatnachrichten in privaten und freigegebenen Kanälen | Ja | |
|Anführungszeichen | Ja | Inhalte, die in Anführungszeichen angegeben werden, können durchsucht werden. Die Suchergebnisse deuten jedoch nicht darauf hin, dass der Inhalt zitiert wurde. |
|Reaktionen (z. B. "Likes", "Herzen" und andere Reaktionen) | Nein | |
|Betreff | Ja | |
|Tabellen | Ja | |
||||

<sup>1</sup> Besprechungs- (und Anruf-)Metadaten umfassen Folgendes:

- Start- und Endzeit der Besprechung und Dauer der Besprechung
- Teilnahme an Besprechungen und Verlassen von Ereignissen für jeden Teilnehmer
- VOIP-Teilnahmen/-Anrufe
- Anonyme Verknüpfungen
- Partnerbenutzer-Joins
- Gastbenutzer tritt bei

Hier ist ein Beispiel für eine Chat-Unterhaltung zwischen Teilnehmern während einer Besprechung.

![Unterhaltung zwischen Teilnehmern in Teams.](media/MeetingIMConversations.png)

[!div class="mx-imgBorder"]

Hier ist ein Beispiel für die Compliancekopie derselben Chat-Unterhaltung, die in einem eDiscovery-Tool angezeigt wird.

![Unterhaltung zwischen Teilnehmern in eDiscovery-Suchergebnissen.](media/MeetingImConversation2.png)

Hier sehen Sie ein Beispiel für die Besprechungsmetadaten.

  > [!div class="mx-imgBorder"]
  > ![Die Besprechungsmetadaten aus der Compliancekopie.](media/conversationOption3.png)

Weitere Informationen zum Durchführen einer eDiscovery-Untersuchung finden Sie unter [Erste Schritte mit Core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery).

Microsoft Teams Daten werden als Chat oder Unterhaltungen in der eDiscovery Excel Discovery-Exportausgabe angezeigt. Sie können die Datei `.pst` in einem Outlook, um diese Nachrichten nach dem Export anzeigen zu können.

Wenn Sie die PST-Datei für das Team anzeigen, befinden sich alle Unterhaltungen im Ordner Teamchat unter Unterhaltungsverlauf. Der Titel der Nachricht enthält den Teamnamen und den Kanalnamen. Die folgende Abbildung zeigt beispielsweise eine Nachricht von Bob, der den Standardkanal Project Produktionsspezifikationen an das Team gesendet hat.

![Screenshot eines Teamchatordners im Postfach eines Benutzers in Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Private Chats im Postfach eines Benutzers werden im Ordner Teamchat unter Unterhaltungsverlauf gespeichert.

## <a name="ediscovery-of-private-and-shared-channels"></a>eDiscovery von privaten und freigegebenen Kanälen

Konformitätskopien von Nachrichten in privaten und freigegebenen Kanälen werden je nach Kanaltyp an verschiedene Postfächer gesendet. Das bedeutet, dass Sie verschiedene Postfachspeicherorte basierend auf dem Kanaltyp durchsuchen müssen, in dem ein Benutzer Mitglied ist.

- **Private Kanäle.** Compliancekopien werden an das Postfach aller Mitglieder der Mitglieder des privaten Kanals gesendet. Das bedeutet, dass Sie das Benutzerpostfach durchsuchen müssen, wenn Sie in Nachrichten privater Kanäle nach Inhalten suchen.

- **Freigegebene Kanäle**. Compliancekopien werden an ein Systempostfach gesendet, das dem übergeordneten Team zugeordnet ist. Da Teams die eDiscovery-Suche eines einzelnen Systempostfachs für einen freigegebenen Kanal nicht unterstützt, müssen Sie das Postfach nach dem übergeordneten Team durchsuchen (indem Sie den Namen des Teampostfachs auswählen), wenn Sie in freigegebenen Kanälen nach Nachrichteninhalten suchen.

Jeder private und freigegebene Kanal verfügt über eine SharePoint Website, die von der übergeordneten Teamwebsite getrennt ist. Das bedeutet, dass Dateien in privaten und gemeinsam genutzten Kanälen auf einer eigenen Website gespeichert und unabhängig vom übergeordneten Team verwaltet werden. Dies bedeutet, dass Sie bei der Suche nach Inhalten in Dateien und Anlagen von Kanalnachrichten die bestimmte Website identifizieren und durchsuchen müssen, die einem Kanal zugeordnet ist.

Verwenden Sie die folgenden Abschnitte, um den privaten oder freigegebenen Kanal zu identifizieren, der in Ihre eDiscovery-Suche enthalten sein soll.

### <a name="identifying-the-members-of-a-private-channel"></a>Identifizieren der Mitglieder eines privaten Kanals

Verwenden Sie das Verfahren in diesem Abschnitt, um die Mitglieder eines privaten Kanals zu identifizieren, damit Sie eDiscovery-Tools verwenden können, um das Postfach des Mitglieds nach Inhalten in privaten Kanalnachrichten zu durchsuchen.

Stellen Sie vor dem Ausführen dieser Schritte sicher, dass Sie die neueste Version des Teams [PowerShell-Moduls installiert](teams-powershell-overview.md) haben.

1. Führen Sie den folgenden Befehl aus, um die Gruppen-ID des Teams zu erhalten, das die freigegebenen Kanäle enthält, die Sie durchsuchen möchten.

   ```powershell
   Get-Team -DisplayName <display name of the the parent team>
   ```

   > [!TIP]
   > Führen Sie **das Cmdlet Get-Team** ohne Parameter aus, um eine Liste aller Teams in Ihrer Organisation anzeigen. Die Liste enthält die Gruppen-ID und den Anzeigenamen für jedes Team.

2. Führen Sie den folgenden Befehl aus, um eine Liste der privaten Kanäle im übergeordneten Team zu erhalten. Verwenden Sie die Gruppen-ID für das Team, das Sie in Schritt 1 erhalten haben.

   ```PowerShell
    Get-TeamChannel -GroupId <parent team GroupId> -MembershipType Private
   ```

3. Führen Sie den folgenden Befehl aus, um eine Liste der Besitzer und Mitglieder privater Kanäle für einen bestimmten privaten Kanal zu erhalten.

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. Fügen Sie die Postfächer von Besitzern und Mitgliedern eines privaten Kanals als Teil Ihrer [eDiscovery-Suchabfrage in Core eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery) oder beim Identifizieren und Sammeln von Angehörigerinhalten [in](/microsoft-365/compliance/add-custodians-to-case) Ihrem Advanced eDiscovery.

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>Identifizieren der SharePoint für private und freigegebene Kanäle

Wie zuvor erläutert, werden in privaten und freigegebenen Kanälen freigegebene Dateien (sowie an Kanalnachrichten angefügte Dateien) in der Websitesammlung gespeichert, die dem Kanal zugeordnet ist. Verwenden Sie das In diesem Abschnitt beschriebene Verfahren, um die URL der Website zu identifizieren, die einem bestimmten privaten oder freigegebenen Kanal zugeordnet ist. Anschließend können Sie mithilfe von eDiscovery-Tools nach Inhalten auf der Website suchen.

Bevor Sie diese Schritte ausführen, installieren [Sie die SharePoint Online-Verwaltungsshell, und stellen Sie eine Verbindung mit SharePoint Online herzustellen](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

1. Führen Sie optional folgendes aus, um eine Liste aller SharePoint, die freigegebenen Kanälen im übergeordneten Team zugeordnet sind, zu erhalten.

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > Die Benennungskonvention der URL für eine Website, die privaten und freigegebenen Kanälen zugeordnet ist, ist `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]`. Die URL für den freigegebenen Kanal namens "Partner Collaboration", der sich im übergeordneten Team "Engineer Team" in der Contoso-Organisation `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration`befindet, ist beispielsweise .

2. Führen Sie die folgenden PowerShell-Befehle aus, um die URL für alle SharePoint anzuzeigen, die den privaten und freigegebenen Kanälen in Ihrer Organisation zugeordnet sind. Die Ausgabe des Skripts enthält auch die Gruppen-ID des übergeordneten Teams, die Sie benötigen, um die Befehle in Schritt 3 auszuführen.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > SharePoint Für Websites privater Kanäle, die vor dem 28. Juni 2021 `"TEAMCHANNEL#0"` erstellt wurden, wird der Wert für die benutzerdefinierte Vorlagen-ID verwendet. Verwenden Sie zum Anzeigen privater Kanäle, die nach diesem Datum erstellt wurden, `"TEAMCHANNEL#1"` den -Wert, wenn Sie die beiden vorherigen Skripts ausführen. Freigegebene Kanäle verwenden nur den Wert von `"TEAMCHANNEL#1"`.

3. Führen Sie für jedes übergeordnete Team die folgenden PowerShell-Befehle aus, um die Websites für private und freigegebene Kanäle zu identifizieren, `$groupID` wobei die Gruppen-ID des übergeordneten Teams ist.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. Fügen Sie die einem privaten oder freigegebenen Kanal zugeordnete Website als Teil Ihrer [eDiscovery-Suchabfrage in Core eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery) oder beim Identifizieren und Sammeln von Inhalten von Daten in [Advanced eDiscovery.](/microsoft-365/compliance/add-custodians-to-case)

## <a name="search-for-content-for-guest-users"></a>Suchen nach Inhalten für Gastbenutzer

Sie können eDiscovery-Tools verwenden, um nach Inhalten Teams, die mit Gastbenutzern in Ihrer Organisation in Zusammenhang stehen, zu suchen. Teams Chatinhalt, der einem Gastbenutzer zugeordnet ist, wird an einem cloudbasierten Speicherort beibehalten und kann mithilfe von eDiscovery durchsucht werden. Dies schließt die Suche nach Inhalten in 1:1- und 1:N-Chatunterhaltungen ein, bei denen ein Gastbenutzer mit anderen Benutzern in Ihrer Organisation Teilnehmer ist. Sie können auch nach Nachrichten in privaten Kanälen suchen, bei denen ein Gastbenutzer Teilnehmer ist, und in Unterhaltungen mit *Gastchats* nach Inhalten suchen, bei denen nur Gastbenutzer die Teilnehmer sind.

So suchen Sie nach Inhalten für Gastbenutzer:

1. Verbinden Sie Azure AD PowerShell. Anweisungen finden Sie im Abschnitt "Verbinden dem Azure Active Directory PowerShell" in Verbinden, Microsoft 365 [PowerShell zu finden](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Stellen Sie sicher, dass Sie die Schritte 1 und 2 im vorherigen Thema abgeschlossen haben.

2. Nachdem Sie erfolgreich eine Verbindung mit Azure AD PowerShell hergestellt haben, führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen (User Principal Name, UPN) für alle Gastbenutzer in Ihrer Organisation anzeigen. Sie müssen den UPN des Gastbenutzers verwenden, wenn Sie die Suche in Schritt 4 erstellen.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Anstatt eine Liste der Benutzerprinzipalnamen auf dem Computerbildschirm anzuzeigen, können Sie die Ausgabe des Befehls an eine Textdatei umleiten. Sie können dies durch Anfügen an `> filename.txt` den vorherigen Befehl tun. Die Textdatei mit den Benutzerprinzipalnamen wird im aktuellen Ordner gespeichert.

3. Stellen Sie in einem Windows PowerShell Fenster eine Verbindung mit Security & Compliance Center PowerShell herstellen. Anweisungen finden Sie unter [Verbinden Security & Compliance Center-PowerShell](/powershell/exchange/connect-to-scc-powershell). Sie können eine Verbindung mit oder ohne mehrstufige Authentifizierung herstellen.

4. Erstellen Sie eine Inhaltssuche, die nach allen Inhalten (wie Chatnachrichten und E-Mail-Nachrichten) sucht, an denen der angegebene Gastbenutzer Teilnehmer war, indem Sie den folgenden Befehl ausführen.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Um beispielsweise nach Inhalten zu suchen, die der Gastbenutzerin Sara Davis zugeordnet sind, führen Sie den folgenden Befehl aus.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Weitere Informationen zur Verwendung von PowerShell zum Erstellen von Inhaltssuchen finden Sie unter [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).

5. Führen Sie den folgenden Befehl aus, um die in Schritt 4 erstellte Inhaltssuche zu starten:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com) , und klicken Sie dann **auf Alle Inhalte** >  **anzeigen.**

7. Wählen Sie in der Liste der Suchbegriffe die Suche aus, die Sie in Schritt 4 erstellt haben, um die Flyoutseite anzeigen.

8. Auf der Flyoutseite haben Sie folgende Optionen:

   - Klicken **Sie auf Ergebnisse anzeigen** , um die Suchergebnisse anzuzeigen und eine Vorschau des Inhalts anzuzeigen.

   - Klicken Sie neben **dem Feld** Abfrage auf **Bearbeiten** , um die Datei zu bearbeiten, und führen Sie die Suche dann erneut aus. Sie können z. B. eine Suchabfrage hinzufügen, um die Ergebnisse zu eindingen.

   - Klicken **Sie auf Ergebnisse exportieren** , um die Suchergebnisse zu exportieren und herunterzuladen.

## <a name="search-for-card-content"></a>Suchen nach Karteninhalten

Karteninhalte, die von Apps in Teams-Kanälen, 1:1-Chats und 1xN-Chats generiert werden, werden in Postfächern gespeichert und können durchsucht werden. Eine *Karte* ist ein UI-Container für kurze Inhalte. Karten können mehrere Eigenschaften und Anlagen aufweisen, und sie können Schaltflächen enthalten, die Kartenaktionen auslösen können. Weitere Informationen finden Sie unter [Karten](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Wie bei Teams Inhalten, in denen Karteninhalte gespeichert werden, basierend auf dem Ort, an dem die Karte verwendet wurde. Inhalte für Karten, die in einem Teams Kanal verwendet werden, werden im Postfach Teams Gruppe gespeichert. Karteninhalte für 1:1- und 1xN-Chats werden in den Postfächern der Chatteilnehmer gespeichert.

Um nach Karteninhalten zu suchen, können Sie die Suchbedingungen `kind:microsoftteams` oder `itemclass:IPM.SkypeTeams.Message` verwenden. Bei der Überprüfung von Suchergebnissen haben Karteninhalte, die von Bots in einem Teams-Kanal generiert werden, die E-Mail-Eigenschaft Absender **/**`<appname>@teams.microsoft.com`Autor als , `appname` wobei der Name der App steht, die den Karteninhalt generiert hat. Wenn Karteninhalte von einem Benutzer generiert wurden, wird der Benutzer durch den Wert Absender **/** Autor identifiziert.

Beim Anzeigen von Karteninhalten in den Ergebnissen der Inhaltssuche wird der Inhalt als Anlage der Nachricht angezeigt. Die Anlage hat den Namen `appname.html`. Dabei `appname` steht für den Namen der App, die den Karteninhalt generiert hat. Die folgenden Screenshots zeigen, wie Der Karteninhalt (für eine App mit dem Namen Asana) in Teams und in den Ergebnissen einer Suche angezeigt wird.

### <a name="card-content-in-teams"></a>Karteninhalt in Teams

![Karteninhalt in Teams Kanalnachricht.](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>Karteninhalt in Suchergebnissen
  
![Gleicher Karteninhalt in den Ergebnissen einer Inhaltssuche.](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Zum Anzeigen von Bildern aus Karteninhalten in den Suchergebnissen (z. B. die Häkchen im vorherigen Screenshot) müssen Sie bei Teams angemeldet sein (https://teams.microsoft.com)auf einer anderen Registerkarte in derselben Browsersitzung, die Sie zum Anzeigen der Suchergebnisse verwenden. Andernfalls werden Bildplatzhalter angezeigt.

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft 365 eDiscovery-Lösungen](/microsoft-365/compliance/ediscovery)
- [Erste Schritte mit Core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams Workflow in Advanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

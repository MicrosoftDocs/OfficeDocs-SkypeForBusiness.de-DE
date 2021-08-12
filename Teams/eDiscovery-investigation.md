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
description: Hier erfahren Sie, was sie tun müssen, wenn Sie eDiscovery ausführen müssen, z. B. wenn Sie alle elektronisch gespeicherten Informationen für juristische Verfahren einreichen müssen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a895b804d78dd3fe5ff45fac40457eaed2cf9c43d80e85137ad2a570c1e2018d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322587"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams

Große Unternehmen werden häufig mit hohen Bußerforderungen rechnen müssen, die die Übermittlung aller elektronisch gespeicherten Informationen erfordern. Microsoft Teams können während eDiscovery-Untersuchungen durchsucht und verwendet werden.

## <a name="overview"></a>Übersicht

Alle Microsoft Teams 1:1- oder Gruppenchats werden in den Postfächern der jeweiligen Benutzer journaliert. Alle Standardmäßigen Kanalnachrichten werden im Journal bis zum Gruppenpostfach journaliert, das das Team darstellt. In Standardkanäle hochgeladene Dateien werden unter die eDiscovery-Funktionalität für SharePoint Online und OneDrive for Business.

eDiscovery von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [eDiscovery privater Kanäle.](#ediscovery-of-private-channels)

Nicht alle Teams sind eDiscoverable. In der folgenden Tabelle sind die Inhaltstypen aufgeführt, nach deren Hilfe Sie mithilfe der Microsoft eDiscovery-Tools suchen können:

| Inhaltstyp | eDiscoverable | Hinweise |
|:--- | :--- |:--- |
|Audioaufzeichnungen | Nein | |
|Karteninhalt|Ja|Weitere [Informationen finden Sie unter Suchen nach](#search-for-card-content) Karteninhalten.|
|Chatlinks | Ja | |
|Chatnachrichten | Ja |Dies umfasst Inhalte in Teams Kanälen, 1:1-Chats, 1:N-Gruppenchats und Chats mit Gastbenutzerteilnehmern.  |
|Codeausschnitte | Nein | |
|Bearbeitete Nachrichten | Ja | Wenn der Benutzer in der Warteschleife ist, bleiben auch frühere Versionen bearbeiteter Nachrichten erhalten. |
|Emojis, GIFs und Aufkleber | Ja | |
|Inlinebilder | Ja | |
|Chatunterhaltungen in Besprechungen | Ja | |
|Besprechungsmetadaten<sup>1</sup> | Ja |  |
|Name des Kanals | Nein | |
|Nachrichten in privaten Kanälen | Ja | |
|Anführungszeichen | Ja | Inhalte, die in Anführungszeichen angegeben werden, können durchsucht werden. Die Suchergebnisse deuten jedoch nicht darauf hin, dass der Inhalt zitiert wurde. |
|Reaktionen (z. B. "Likes", "Herzen" und andere Reaktionen) | Nein | |
|Betreff | Ja | |
|Tabellen | Ja | |
|Feedbenachrichtigungen | Nein | |
|||

<sup>1</sup> Besprechungs- (und Anruf-)Metadaten umfassen Folgendes:

- Start- und Endzeit der Besprechung und Dauer der Besprechung
- Teilnahme an Besprechungen und Verlassen von Ereignissen für jeden Teilnehmer
- VOIP-Teilnahme/-Anrufe
- Anonyme Teilnahme
- Partnerbenutzer bei der Teilnahme
- Gastbenutzer beitreten

  Die Abbildung zeigt ein Beispiel für Besprechungsmetadaten.

  > [!div class="mx-imgBorder"]
  > ![Bild der Metadaten der CVR-Datensatz-Besprechung.](media/conversationOption3.png)

Hier ist ein Beispiel für eine Unterhaltung im Zusammenhang mit einer Unterhaltung zwischen Teilnehmern während der Besprechung.

![Unterhaltung zwischen Teilnehmern in Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Unterhaltung zwischen Teilnehmern in eDiscovery-Suchergebnissen.](media/MeetingImConversation2.png)

Weitere Informationen zum Durchführen einer eDiscovery-Untersuchung finden Sie unter [Erste Schritte mit Core eDiscovery.](/microsoft-365/compliance/get-started-core-ediscovery)

Microsoft Teams daten werden als Chat oder Unterhaltungen in der eDiscovery Excel-Exportausgabe angezeigt. Sie können die Datei `.pst` in einem Outlook, um diese Nachrichten nach dem Export anzeigen.

Wenn Sie die PST-Datei für das Team anzeigen, befinden sich alle Unterhaltungen im Ordner Teamchat unter Unterhaltungsverlauf. Der Titel der Nachricht enthält den Teamnamen und den Kanalnamen. Die folgende Abbildung zeigt beispielsweise eine Nachricht von Bob, der den Standardkanal Project Produktionsspezifikationen gesendet hat.

![Screenshot eines Teamchatordners im Postfach eines Benutzers in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Private Chats im Postfach eines Benutzers werden im Ordner Teamchat unter Unterhaltungsverlauf gespeichert.

## <a name="ediscovery-of-private-channels"></a>eDiscovery von privaten Kanälen

Einträge für Nachrichten, die in einem privaten Kanal gesendet werden, werden an das Postfach aller Mitglieder des privaten Kanals und nicht an ein Gruppenpostfach übermittelt. Die Titel der Einträge sind so formatiert, dass sie angeben, von welchem privaten Kanal sie gesendet wurden.

Da jeder private Kanal über eine eigene SharePoint-Website verfügt, die von der übergeordneten Teamwebsite getrennt ist, werden Dateien in einem privaten Kanal unabhängig vom übergeordneten Team verwaltet.

Teams unterstützt die eDiscovery-Suche eines einzelnen Kanals innerhalb eines Teams nicht, daher muss das gesamte Team durchsucht werden. Um eine eDiscovery-Suche nach Inhalten in einem privaten Kanal durchzuführen, suchen Sie im gesamten Team, in der Websitesammlung, die dem privaten Kanal zugeordnet ist (um Dateien zu enthalten), und in Postfächern privater Kanalmitglieder (um Nachrichten zu enthalten).

Verwenden Sie die folgenden Schritte, um Dateien und Nachrichten in einem privaten Kanal zu identifizieren, die in Ihre eDiscovery-Suche miteinbehebbar sein sollen.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Schließen Sie Dateien privater Kanäle in eine eDiscovery-Suche ein

Bevor Sie diese Schritte ausführen, installieren Sie die SharePoint Online-Verwaltungsshell, und stellen Sie [eine Verbindung mit SharePoint Online herzustellen.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. Führen Sie die folgenden Schritte aus, um eine Liste aller SharePoint, die privaten Kanälen im Team zugeordnet sind, zu erhalten.

    ```PowerShell
    Get-SPOSite
    ```

2. Führen Sie das folgende PowerShell-Skript aus, um eine Liste aller SharePoint-Websitesammlungs-URLs zu erhalten, die privaten Kanälen im Team und der ID der übergeordneten Teamgruppe zugeordnet sind.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Führen Sie für jedes Team oder jede Gruppen-ID das folgende PowerShell-Skript aus, um alle relevanten Websites privater Kanäle zu identifizieren, wobei $groupID die Gruppen-ID des Teams ist.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Schließen Sie Nachrichten privater Kanäle in eine eDiscovery-Suche ein

Stellen Sie vor dem Ausführen dieser Schritte sicher, dass Sie die neueste Version des Teams [PowerShell-Moduls installiert](teams-powershell-overview.md) haben.

1. Führen Sie den folgenden Befehl aus, um eine Liste der privaten Kanäle im Team zu erhalten.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Führen Sie den folgenden Befehl aus, um eine Liste der Mitglieder privater Kanäle zu erhalten.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Fügen Sie die Postfächer aller Mitglieder aus jedem privaten Kanal im Team als Teil Ihrer [eDiscovery-Suchabfrage ein.](/microsoft-365/compliance/search-for-content-in-core-ediscovery)

## <a name="search-for-content-for-guest-users"></a>Suchen nach Inhalten für Gastbenutzer

Sie können eDiscovery-Tools verwenden, um nach Inhalten Teams, die mit Gastbenutzern in Ihrer Organisation in Zusammenhang stehen, zu suchen. Teams Chatinhalt, der einem Gastbenutzer zugeordnet ist, wird an einem cloudbasierten Speicherort beibehalten und kann mithilfe von eDiscovery durchsucht werden. Dies schließt die Suche nach Inhalten in 1:1- und 1:N-Chatunterhaltungen ein, bei denen ein Gastbenutzer mit anderen Benutzern in Ihrer Organisation Teilnehmer ist. Sie können auch nach Nachrichten in privaten Kanälen suchen, bei denen ein Gastbenutzer teilnehmer ist, und in Unterhaltungen mit *Gastchats* nach Inhalten suchen, bei denen nur Gastbenutzer die Teilnehmer sind.

So suchen Sie nach Inhalten für Gastbenutzer:

1. Verbinden Azure AD PowerShell. Anweisungen finden Sie im Abschnitt "Verbinden dem Azure Active Directory PowerShell" in Verbinden, [Microsoft 365 PowerShell zu finden.](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) Stellen Sie sicher, dass Sie die Schritte 1 und 2 im vorherigen Thema abgeschlossen haben.

2. Nachdem Sie erfolgreich eine Verbindung mit Azure AD PowerShell hergestellt haben, führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen (User Principal Name, UPN) für alle Gastbenutzer in Ihrer Organisation anzeigen. Sie müssen den UPN des Gastbenutzers verwenden, wenn Sie die Suche in Schritt 4 erstellen.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Anstatt eine Liste der Benutzerprinzipalnamen auf dem Computerbildschirm anzuzeigen, können Sie die Ausgabe des Befehls an eine Textdatei umleiten. Sie können dies durch Anfügen `> filename.txt` an den vorherigen Befehl tun. Die Textdatei mit den Benutzerprinzipalnamen wird im aktuellen Ordner gespeichert.

3. Stellen Sie in einem Windows PowerShell Fenster eine Verbindung mit Security & Compliance Center-PowerShell herstellen. Anweisungen finden Sie unter [Verbinden Security & Compliance Center in PowerShell.](/powershell/exchange/connect-to-scc-powershell) Sie können eine Verbindung mit oder ohne mehrstufige Authentifizierung herstellen.

4. Erstellen Sie eine Inhaltssuche, die nach allen Inhalten (z. B. Chatnachrichten und E-Mail-Nachrichten) sucht, an denen der angegebene Gastbenutzer teilnehmer war, indem Sie den folgenden Befehl ausführen.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Um beispielsweise nach Inhalten zu suchen, die der Gastbenutzerin Sara Davis zugeordnet sind, würden Sie den folgenden Befehl ausführen.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Weitere Informationen zur Verwendung von PowerShell zum Erstellen von Inhaltssuchen finden Sie unter [New-ComplianceSearch.](/powershell/module/exchange/new-compliancesearch)

5. Führen Sie den folgenden Befehl aus, um die in Schritt 4 erstellte Inhaltssuche zu starten:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com) , und klicken Sie dann auf **Alle**  >  **Inhaltssuche anzeigen**.

7. Wählen Sie in der Liste der Suchbegriffe die Suche aus, die Sie in Schritt 4 erstellt haben, um die Flyoutseite anzeigen.

8. Auf der Flyoutseite haben Sie folgende Optionen:

   - Klicken **Sie auf Ergebnisse anzeigen,** um die Suchergebnisse anzuzeigen und eine Vorschau des Inhalts anzuzeigen.

   - Klicken Sie neben **dem Feld** Abfrage auf **Bearbeiten,** um die Datei zu bearbeiten, und führen Sie die Suche dann erneut aus. Sie können z. B. eine Suchabfrage hinzufügen, um die Ergebnisse zu eindingen.

   - Klicken **Sie auf Ergebnisse exportieren,** um die Suchergebnisse zu exportieren und herunterzuladen.

## <a name="search-for-card-content"></a>Suchen nach Karteninhalten

Karteninhalte, die von Apps in Teams Kanälen, 1:1-Chats und 1xN-Chats generiert werden, werden in Postfächern gespeichert und können durchsucht werden. Eine *Karte* ist ein UI-Container für kurze Inhalte. Karten können mehrere Eigenschaften und Anlagen aufweisen, und sie können Schaltflächen enthalten, die Kartenaktionen auslösen können. Weitere Informationen finden Sie unter [Karten](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Wie bei Teams Inhalten, in denen Karteninhalte gespeichert werden, basierend auf dem Ort, an dem die Karte verwendet wurde. Inhalte für Karten, die in einem Teams Kanal verwendet werden, werden im Postfach Teams Gruppe gespeichert. Karteninhalte für 1:1- und 1xN-Chats werden in den Postfächern der Chatteilnehmer gespeichert.

Um nach Karteninhalten zu suchen, können Sie die `kind:microsoftteams` `itemclass:IPM.SkypeTeams.Message` Suchbedingungen oder verwenden. Bei der Überprüfung von Suchergebnissen haben Karteninhalte, die von Bots in einem Teams-Kanal generiert werden, die E-Mail-Eigenschaft **Absender/Autor** als , wobei der Name der App steht, die den Karteninhalt `<appname>@teams.microsoft.com` `appname` generiert hat. Wenn Karteninhalte von einem Benutzer generiert wurden, wird der Benutzer durch den Wert **Absender/Autor** identifiziert.

Beim Anzeigen von Karteninhalten in den Ergebnissen der Inhaltssuche wird der Inhalt als Anlage der Nachricht angezeigt. Die Anlage hat den Namen `appname.html` . Dabei steht für den Namen der `appname` App, die den Karteninhalt generiert hat. Die folgenden Screenshots zeigen, wie der Karteninhalt (für eine App namens Asana) in Teams und in den Ergebnissen einer Suche angezeigt wird.

**Karteninhalt in Teams**

![Karteninhalt in Teams Kanalnachricht](media/CardContentTeams.png)

**Karteninhalt in Suchergebnissen**
  
![Gleicher Karteninhalt in den Ergebnissen einer Inhaltssuche](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Um zu diesem Zeitpunkt Bilder aus Karteninhalten in den Suchergebnissen anzuzeigen (z. B. die Häkchen im vorherigen Screenshot), müssen Sie bei Teams angemeldet sein (auf einer anderen Registerkarte in derselben Browsersitzung, die Sie zum Anzeigen der Suchergebnisse https://teams.microsoft.com) verwenden. Andernfalls werden Bildplatzhalter angezeigt.

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft 365 eDiscovery-Lösungen](/microsoft-365/compliance/ediscovery)
- [Erste Schritte mit Core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams eines Workflows in Advanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

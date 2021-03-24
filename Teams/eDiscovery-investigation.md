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
description: Erfahren Sie, was Sie tun müssen, wenn Sie eDiscovery ausführen müssen, z. B. wenn Sie alle elektronisch gespeicherten Informationen für juristische Schritte einreichen müssen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3990b96981a65bb4d706cc3141abee10102c0839
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094055"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams

Große Unternehmen sind häufig gerichtlich mit hohen Strafen bezingbar, die die Übermittlung aller elektronisch gespeicherten Informationen (ESI) erfordern. Microsoft Teams-Inhalte können während eDiscovery-Untersuchungen durchsucht und verwendet werden.

## <a name="overview"></a>Übersicht

Alle Microsoft Teams 1:1- oder Gruppenchats werden in den Postfächern der jeweiligen Benutzer journaliert. Alle Standardkanalnachrichten werden bis zum Gruppenpostfach journaliert, das das Team darstellt. In Standardkanäle hochgeladene Dateien werden unter den eDiscovery-Funktionen für SharePoint Online und OneDrive for Business behandelt.

eDiscovery von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [eDiscovery von privaten Kanälen.](#ediscovery-of-private-channels)

Nicht alle Teams-Inhalte sind eDiscoverable. In der folgenden Tabelle sind die Inhaltstypen aufgeführt, nach deren Inhalt Sie mithilfe der Microsoft eDiscovery-Tools suchen können:

| Inhaltstyp | eDiscoverable | Hinweise |
|:--- | :--- |:--- |
|Audioaufzeichnungen | Nein | |
|Karteninhalt|Ja|Weitere [Informationen finden Sie unter](#search-for-card-content) Suchen nach Karteninhalten.|
|Chatlinks | Ja | |
|Chatnachrichten | Ja |Dies umfasst Inhalte in Teams-Kanälen, 1:1-Chats, 1:N-Gruppenchats und Chats mit Gastbenutzerteilnehmern.  |
|Codeausschnitte | Nein | |
|Bearbeitete Nachrichten | Ja | Wenn sich der Benutzer im Halteraum befindet, bleiben auch frühere Versionen bearbeiteter Nachrichten erhalten. |
|Emojis, GIFs und Aufkleber | Ja | |
|Inlinebilder | Ja | |
|Chatunterhaltungen in Besprechungen | Ja | |
|Besprechungsmetadaten<sup>1</sup> | Ja |  |
|Name des Kanals | Nein | |
|Nachrichten des privaten Kanals | Ja | |
|Anführungszeichen | Ja | Zitierte Inhalte sind durchsuchbar. Suchergebnisse deuten jedoch nicht darauf hin, dass der Inhalt zitiert wurde. |
|Reaktionen (z. B. Likes, Herzen und andere Reaktionen) | Nein | |
|Betreff | Ja | |
|Tabellen | Ja | |
|||

<sup>1</sup> Besprechungsmetadaten (und Anrufmetadaten) umfassen Folgendes:

- Start- und Endzeit der Besprechung sowie Dauer der Besprechung
- Teilnehmen an Besprechungen und Verlassen von Ereignissen für jeden Teilnehmer
- VOIP-Teilnahme/-Anrufe
- Anonyme Teilnahme
- Partnerated user join
- Teilnahme von Gastbenutzern

  Die Abbildung zeigt ein Beispiel für Besprechungsmetadaten.

  > [!div class="mx-imgBorder"]
  > ![Bild ist der CvR-Datensatz für Besprechungsmetadaten.](media/conversationOption3.png)

Hier sehen Sie ein Beispiel für eine Unterhaltung zwischen Teilnehmern während der Besprechung.

![Unterhaltung zwischen Teilnehmern in Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Unterhaltung zwischen Teilnehmern in eDiscovery-Suchergebnissen.](media/MeetingImConversation2.png)

Weitere Informationen zum Durchführen einer eDiscovery-Untersuchung finden Sie unter [Erste Schritte mit Core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery).

Microsoft Teams-Daten werden in der Excel eDiscovery-Exportausgabe als Chat oder Unterhaltungen angezeigt. Sie können die Datei in Outlook öffnen, um diese Nachrichten nach dem `.pst` Exportieren anzeigen zu können.

Beim Anzeigen der PST-Datei für das Team werden alle Unterhaltungen im Ordner Teamchat unter Unterhaltungsverlauf gespeichert. Der Titel der Nachricht enthält den Teamnamen und den Kanalnamen. Die folgende Abbildung zeigt z. B. eine Meldung von Bob, der den Project 7-Standardkanal des Manufacturing Specs-Teams gesendet hat.

![Screenshot eines Teamchatordners im Postfach eines Benutzers in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Private Chats im Postfach eines Benutzers werden im Ordner Teamchat unter Unterhaltungsverlauf gespeichert.

## <a name="ediscovery-of-private-channels"></a>eDiscovery privater Kanäle

Einträge für Nachrichten, die in einem privaten Kanal gesendet werden, werden an das Postfach aller Mitglieder des privaten Kanals und nicht an ein Gruppenpostfach übermittelt. Die Titel der Einträge sind so formatiert, dass sie angeben, von welchem privaten Kanal sie gesendet wurden.

Da jeder private Kanal über eine eigene SharePoint-Website verfügt, die von der übergeordneten Teamwebsite getrennt ist, werden Dateien in einem privaten Kanal unabhängig vom übergeordneten Team verwaltet.

Teams unterstützt keine eDiscovery-Suche nach einem einzelnen Kanal innerhalb eines Teams, daher muss das gesamte Team durchsucht werden. Um eine eDiscovery-Suche von Inhalten in einem privaten Kanal durchzuführen, suchen Sie im gesamten Team, in der Websitesammlung, die dem privaten Kanal zugeordnet ist (um Dateien zu enthalten) und postfächern von Mitgliedern des privaten Kanals (um Nachrichten zu enthalten).

Verwenden Sie die folgenden Schritte, um Dateien und Nachrichten in einem privaten Kanal zu identifizieren, die in Ihre eDiscovery-Suche miteinbebegriffen werden sollen.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Schließen Sie Dateien des privaten Kanals in eine eDiscovery-Suche ein.

Installieren Sie vor dem Ausführen dieser Schritte die [SharePoint Online-Verwaltungsshell, und stellen Sie eine Verbindung mit SharePoint Online ein.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. Führen Sie folgendes aus, um eine Liste aller SharePoint-Websitesammlungen zu erhalten, die privaten Kanälen im Team zugeordnet sind.

    ```PowerShell
    Get-SPOSite
    ```

2. Führen Sie das folgende PowerShell-Skript aus, um eine Liste aller URLs der SharePoint-Websitesammlung zu erhalten, die privaten Kanälen im Team und der übergeordneten Teamgruppen-ID zugeordnet sind.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Führen Sie für jedes Team oder jede Gruppen-ID das folgende PowerShell-Skript aus, um alle relevanten Websites des privaten Kanals zu identifizieren, wobei $groupID die Gruppen-ID des Teams ist.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Schließen Sie Nachrichten des privaten Kanals in eine eDiscovery-Suche ein.

Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Die neueste Version des [Teams PowerShell-Moduls installiert](teams-powershell-overview.md) ist.

1. Führen Sie den folgenden Befehl aus, um eine Liste der privaten Kanäle im Team zu erhalten.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Führen Sie den folgenden Befehl aus, um eine Liste der Mitglieder des privaten Kanals zu erhalten.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Fügen Sie die Postfächer aller Mitglieder aus jedem privaten Kanal im Team als Teil Ihrer [eDiscovery-Suchabfrage ein.](/microsoft-365/compliance/search-for-content-in-core-ediscovery)

## <a name="search-for-content-for-guest-users"></a>Suchen nach Inhalten für Gastbenutzer

Sie können eDiscovery-Tools verwenden, um nach Teams-Inhalten im Zusammenhang mit Gastbenutzern in Ihrer Organisation zu suchen. Teams-Chatinhalte, die einem Gastbenutzer zugeordnet sind, bleiben an einem cloudbasierten Speicherort erhalten und können mithilfe von eDiscovery durchsucht werden. Dazu gehört auch die Suche nach Inhalten in 1:1- und 1:N-Chatunterhaltungen, bei denen ein Gastbenutzer mit anderen Benutzern in Ihrer Organisation teiln. Sie können auch nach Nachrichten im privaten Kanal suchen, bei denen ein Gastbenutzer Teilnehmer ist, und nach Inhalten in *Gast-:Gastchatunterhaltungen* suchen, bei denen die einzigen Teilnehmer Gastbenutzer sind.

So suchen Sie nach Inhalten für Gastbenutzer:

1. Stellen Sie eine Verbindung mit Azure AD PowerShell bereit. Anweisungen finden Sie im Abschnitt "Herstellen einer Verbindung mit azure Active Directory PowerShell" unter Herstellen einer Verbindung mit [Microsoft 365 mit PowerShell.](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) Stellen Sie sicher, dass Sie Schritt 1 und Schritt 2 im vorherigen Thema abgeschlossen haben.

2. Nachdem Sie erfolgreich eine Verbindung mit Azure AD PowerShell hergestellt haben, führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen (User Principal Name, UPN) für alle Gastbenutzer in Ihrer Organisation anzeigen. Sie müssen den UPN des Gastbenutzers verwenden, wenn Sie die Suche in Schritt 4 erstellen.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Anstatt eine Liste der Benutzernamen auf dem Computerbildschirm anzuzeigen, können Sie die Ausgabe des Befehls an eine Textdatei umleiten. Dazu fügen Sie den `> filename.txt` vorherigen Befehl an. Die Textdatei mit den Namen des Prinzipalbenutzers wird im aktuellen Ordner gespeichert.

3. Stellen Sie in einem anderen Windows PowerShell eine Verbindung mit Security & Compliance Center PowerShell ein. Anweisungen finden Sie unter Herstellen einer Verbindung mit [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell). Sie können eine Verbindung mit oder ohne mehrstufige Authentifizierung herstellen.

4. Erstellen Sie eine Inhaltssuche, die nach allen Inhalten (z. B. Chatnachrichten und E-Mail-Nachrichten) sucht, bei der der angegebene Gastbenutzer teilnehmer war, indem Sie den folgenden Befehl ausführen.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Wenn Sie beispielsweise nach Inhalten suchen möchten, die der Gastbenutzerin Sara Davis zugeordnet sind, führen Sie den folgenden Befehl aus.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Weitere Informationen zur Verwendung von PowerShell zum Erstellen von Inhaltssuchen finden Sie unter [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).

5. Führen Sie den folgenden Befehl aus, um die Inhaltssuche zu starten, die Sie in Schritt 4 erstellt haben:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie dann **auf Alle**  >  **Inhaltssuche anzeigen.**

7. Wählen Sie in der Liste der Suchbegriffe die Suche aus, die Sie in Schritt 4 erstellt haben, um die Flyoutseite anzeigen zu können.

8. Auf der Flyoutseite können Sie die folgenden Schritte tun:

   - Klicken **Sie auf Ergebnisse anzeigen,** um die Suchergebnisse anzuzeigen und eine Vorschau des Inhalts anzuzeigen.

   - Klicken Sie neben dem **Feld** Abfrage auf **Bearbeiten,** um sie zu bearbeiten, und führen Sie die Suche dann erneut aus. Sie können z. B. eine Suchabfrage hinzufügen, um die Ergebnisse zu einengt.

   - Klicken **Sie auf Ergebnisse exportieren,** um die Suchergebnisse zu exportieren und herunterzuladen.

## <a name="search-for-card-content"></a>Suchen nach Karteninhalten

Karteninhalte, die von Apps in Teams-Kanälen, 1:1-Chats und 1xN-Chats generiert werden, werden in Postfächern gespeichert und können durchsucht werden. Eine *Karte* ist ein UI-Container für kurze Inhalte. Karten können mehrere Eigenschaften und Anlagen aufweisen und Schaltflächen enthalten, die Kartenaktionen auslösen können. Weitere Informationen finden Sie unter [Karten](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Wie bei anderen Teams-Inhalten basiert der Karteninhalt auf dem Ort, an dem die Karte verwendet wurde. Inhalte für Karten, die in einem Teams-Kanal verwendet werden, werden im Gruppenpostfach von Teams gespeichert. Karteninhalte für 1:1- und 1xN-Chats werden in den Postfächern der Chatteilnehmer gespeichert.

Um nach Karteninhalten zu suchen, können Sie die `kind:microsoftteams` Suchbedingungen oder `itemclass:IPM.SkypeTeams.Message` verwenden. Bei der Überprüfung der Suchergebnisse verfügt der von Bots in einem Teams-Kanal generierte Karteninhalt über die E-Mail-Eigenschaft **Absender/Autor** als , wobei sich der Name der App befindet, die den `<appname>@teams.microsoft.com` `appname` Karteninhalt generiert hat. Wenn Karteninhalte von einem Benutzer generiert wurden, identifiziert der Wert des **Absenders/Autors** den Benutzer.

Beim Anzeigen von Karteninhalten in den Suchergebnissen für Inhalte wird der Inhalt als Anlage zur Nachricht angezeigt. Die Anlage trägt den Namen `appname.html` , wobei sich der Name der App `appname` befindet, die den Karteninhalt generiert hat. Die folgenden Screenshots zeigen, wie Karteninhalte (für eine App namens Asana) in Teams und in den Ergebnissen einer Suche angezeigt werden.

**Karteninhalt in Teams**

![Card content in Teams channel message](media/CardContentTeams.png)

**Karteninhalt in Suchergebnissen**
  
![Derselbe Karteninhalt in den Ergebnissen einer Inhaltssuche](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Zum Anzeigen von Bildern aus Karteninhalten in den Suchergebnissen (z. B. die Häkchen im vorherigen Screenshot) müssen Sie bei Teams angemeldet sein (auf einer anderen Registerkarte in derselben Browsersitzung, die Sie zum Anzeigen der Suchergebnisse https://teams.microsoft.com) verwenden. Andernfalls werden Bildplatzhalter angezeigt.

## <a name="advanced-ediscovery"></a>Advanced eDiscovery

Einige Microsoft Teams-Inhalte können auch mithilfe des Advanced [eDiscovery-Workflows](/microsoft-365/compliance/overview-ediscovery-20)durchsucht und beibehalten werden. Während eDiscovery eine Reihe von Such-, Halte- und Exportfunktionen bietet, bietet Advanced eDiscovery Complianceadministratoren mehr Tools, um Datenquellen zu identifizieren und deren Inhalte zu analysieren.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Erweiterter eDiscovery- Custodian-Workflow für Teams-Inhalte

Custodians ist möglicherweise Mitglied verschiedener Teams. Sie können Teams-Inhalte erfassen, die für diese Custodians relevant sind. Anweisungen zum Custodian-Workflow finden Sie unter [Hinzufügen von Custodians zu einem advanced eDiscovery-Fall.](/microsoft-365/compliance/add-custodians-to-case)

Klicken Sie nach dem Hinzufügen eines Custodians auf die Schaltfläche **Weiter** und dann **auf die** Schaltfläche Hinzufügen. Anschließend wird ein Fenster angezeigt, in dem Sie aufgefordert werden, weitere Speicherorte auszuwählen, in dem alle Mitgliedschaften des Custodians und die entsprechenden SharePoint-Websitespeicherorte für ihre Daten angezeigt werden. Aus allen diesen Datenquellen und Teams können Sie den Inhalt auswählen, den Sie für eDiscovery verwenden möchten, und dann diesen Benutzer und alle von Ihnen identifizierten Datenquellen in den Halteraum setzen.

Sie können auswählen, ob deren #A0, deren #A1 oder beides enthalten sein soll. Exchange-Inhalte umfassen alle Anwendungsinhalte in den Postfächern des Benutzers, z. B. deren E-Mails, die in ihrem Postfach gespeicherten Teams-Inhalte und vieles mehr. Der #A0 enthält nicht nur den Inhalt des Benutzers, sondern auch alle #A1, die auf OneDrive gespeichert sind, wie 1:1-Chats, 1:N-Chats und in Chats freigegebene Dateien.

Sie haben auch die Möglichkeit, jedes Team zuzuordnen, in dem der Custodian Mitglied ist, sodass Kanalchatnachrichten und Dateien, auf die der Custodian Zugriff hat, einbezogen werden. Darüber hinaus kann jedes andere Team einem Custodian zugeordnet werden.

> [!NOTE]
> eDiscovery von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [eDiscovery von privaten Kanälen.](#ediscovery-of-private-channels)

### <a name="placing-a-data-source-on-hold"></a>Platzieren einer Datenquelle im Halteraum

Wenn kein bestimmter Benutzer als Custodian bestimmt werden soll, können Sie eine gesamte Datenquelle in den Halteraum setzen. Weitere Informationen zu haltebaren Daten finden Sie unter [Verwalten von Halte halte in Advanced eDiscovery](/microsoft-365/compliance/managing-holds).

Wenn Sie einen Halteraum für Teams-Inhalte erstellen, können Sie alle Speicherorte auswählen, die Sie in Ihren Halteraum ein- und aussuchen möchten. Auch wenn Benutzer Inhalte löschen oder ändern, werden im Halteraum Kopien aller früheren Versionen dieses Inhalts beibehalten.

Sie können auch eine optionale Abfrage verwenden, um Bedingungen für den Haltebereich basierend auf Schlüsselwörtern, Datumsbereich, Autor und vielen anderen Kriterien zu festlegen. Wenn Sie keine Schlüsselwörter angeben, unterliegt alles aus dieser Datenquelle dem Halteraum.

### <a name="advanced-ediscovery-searches"></a>Erweiterte eDiscovery-Suchbegriffe

Teams-Inhalte können auch durchsucht werden. Weitere Informationen zu Suchbegriffen finden Sie unter Sammeln von [Daten für einen Fall in Advanced eDiscovery](/microsoft-365/compliance/collecting-data-for-ediscovery). Eine Suche gibt eine gesamte Unterhaltung zurück, wenn auch nur eine Nachricht der Suchabfrage entspricht.

Beim Erstellen einer Suchabfrage können Sie Custodians auswählen, damit alle quellen, die Sie bereits ausgewählt haben, durchsucht werden. Sie können auch nicht verwahrungsfreie Quellen durchsuchen, z. B. eine Teams-Website, die keinem Benutzer zugeordnet ist. Optionale Abfragen sind auch verfügbar, um Ihre Suche innerhalb des Teams-Inhalts zu eindinnen.

Nachdem Sie eine Suche erstellt und ausgewählt haben, wird ein Fenster mit weiteren Details und Aktionen angezeigt, die Sie für die ausgewählte Suche ausführen können. Wenn Sie  auf die Schaltfläche Statistik klicken, können Sie Statistiken zu Ihrer Suche anzeigen, einschließlich Aufschlüsselungen nach Standorttypen, der ursprünglichen Quelle für den Inhalt und der Frage, ob sich der Inhalt in einem Gruppenpostfach, dem einzelnen Benutzerpostfach oder einer SharePoint-Website befindet. Daher können Sie eine Aufschlüsselung der Quellen sehen, die zu Ihren Suchergebnissen beitragen. Darüber hinaus ist eine **Ansicht Abfragen** verfügbar, damit Sie sehen können, welche einzelnen Schlüsselwörter zu Ihren Ergebnissen beitragen.

Nach Abschluss der Suche können Sie  auf die Schaltfläche Ergebnisse hinzufügen klicken, um den Satz zu überprüfen, und sie zu einem Überprüfungssatz hinzufügen. Weitere Informationen zu Überprüfungssätzen finden Sie weiter unten in diesem Artikel unter Verwalten von Überprüfungssätzen [in Advanced eDiscovery-](/microsoft-365/compliance/managing-review-sets) und [Review Sets-Workflows.](#review-sets-workflow)

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Normale Überprüfungssätze und Unterhaltungsüberprüfungssätze

Wenn Sie einem Überprüfungssatz eine Suche hinzufügen, können Sie aus einem normalen Überprüfungssatz oder einem Unterhaltungsüberprüfungssatz auswählen.

Ein normaler Überprüfungssatz ähnelt einem Export. Es stellt die einzelnen Dateien für den Inhalt von `.msg` Teams zur Und stellt den Inhalt in einer einfachen Ansicht vor. Normalerweise verwenden Sie einen normalen Überprüfungssatz, wenn Sie planen, die Dateien später mit anderen Softwaretools erneut zu bearbeiten.

Ein Unterhaltungsüberprüfungssatz bietet eine intuitivere Threadansicht der Unterhaltungen. verknüpfte Nachrichten werden in der richtigen Reihenfolge zusammen angezeigt.

> [!div class="mx-imgBorder"]
> ![Screenshot der Unterhaltungsüberprüfungssatz](media/conversationOptions2.png)

Funktionen wie "Redaction" sind in beiden Arten von Überprüfungssätzen verfügbar. Weitere Informationen zu Überprüfungssätzen finden Sie unter [Überprüfen von Unterhaltungen in erweiterter eDiscovery](/microsoft-365/compliance/conversation-review-sets).

#### <a name="collection-options"></a>Sammlungsoptionen

Beim Hinzufügen zu einem Überprüfungssatz stehen mehrere Optionen  als Kontrollkästchen unter dem Abschnitt Sammlungsoptionen des Fensters zur Verfügung, darunter Optionen zum Abrufen von Unterhaltungen **und** **Teams-Unterhaltungen.** Wenn Sie diese Optionen aktivieren, werden alle einzelnen Teams-Nachrichten, die Teil Ihres Überprüfungssets sind, ebenfalls mit zusätzlichen Nachrichten angezeigt, die sie für den Kontext umgeben. Wenn Ihre Abfrage z. B. spezifisch ist und als Ergebnis nur eine Nachricht zurückgegeben wird, gibt das Aktivieren dieser Optionen auch mehrere Nachrichten zurück, die zu der Nachricht führen und die der Abfrage entsprechen.

Viele wahrheitsbezogene Kriterien werden verwendet, um festzustellen, ob zusätzliche Nachrichten Kontext für Nachrichten bereitstellen, die Ihrer Abfrage entsprechen. Bei Teams-Inhalten ruft das Aktivieren dieser Optionen beispielsweise die übergeordnete Nachricht und alle untergeordneten Nachrichten ab, da die Nachrichten threaded sind.

Nachrichtenzeitstempel werden ebenfalls überprüft. Wenn eine Nachricht ihrer Abfrage entspricht, werden benachbarte Nachrichten, die innerhalb von vier Stunden oder innerhalb von vier Stunden folgen, als Teil der Unterhaltung betrachtet und ebenfalls in die Ergebnisse einbezogen.

Wenn Sie sicher sein müssen, welche Kontextnachrichten mit Übereinstimmungen zu Ihrer Suchabfrage zurückgegeben werden, müssen Sie diese Optionen nicht verwenden. Sie können entweder alle Inhalte sammeln oder den Datumsbereich Der Suchbereich kann so verbreitert werden, dass mehr Nachrichten als Ergebnis Ihrer Abfrage zurückgegeben werden.

### <a name="review-sets-workflow"></a>Workflow zum Überprüfen von Sätzen

Sie können vorhandene Überprüfungssätze anzeigen oder neue erstellen, indem Sie auf die Registerkarte **Überprüfen von Sätzen** klicken. Weitere Informationen zu Überprüfungssätzen finden Sie unter [Verwalten von Überprüfungssätzen in Advanced eDiscovery](/microsoft-365/compliance/managing-review-sets).

Zusätzlich zu Dokumenten können Sie E-Mails, Teams-Nachrichten, Yammer Nachrichten und andere Inhalte zu Ihrem Überprüfungssatz hinzufügen. Innerhalb eines Überprüfungssets können Sie auch viele derselben Vorgänge ausführen, die Sie auch in anderen Kontexten ausführen können, z. B. das Durchsuchen von Inhalten und das Erstellen benutzerdefinierter Abfragen. Diese Vorgänge gelten nur für Elemente, die dem Überprüfungssatz hinzugefügt wurden.

Die **Schaltfläche Überprüfungssätze** verwalten bietet zusätzliche Optionen wie Analyse, Zusammenfassungsberichte, die Hinzugefügte Auslastungssätze und so weiter.

Wenn Sie auf Visualisierungen und Diagramme Ihrer Daten zugreifen möchten, klicken **Sie** oben rechts auf Individuelle Ergebnisse \> Suchprofilansicht.  Sie können in diesen Diagrammen auf Keile klicken, um interaktiv den Inhaltstyp auszuwählen, den Sie abfragen möchten. Sie können z. B. auswählen, dass nur Teams-Inhalte abgefragt werden sollen. Sie können diese Abfragen auch genauso speichern wie manuell geschriebene Abfragen.

#### <a name="summary-view-text-view-and-annotate-view"></a>Zusammenfassungsansicht, Textansicht und Anmerkungsansicht

Wenn Sie im Überprüfungssatz auf eine Teams-Unterhaltung klicken, wird die Zusammenfassungsansicht **angezeigt,** in der eine gesamte Teams-Unterhaltung als Liste von Nachrichten angezeigt wird, mit denen Sie einzeln interagieren können. Klicken Sie auf den Abwärtspfeil rechts neben einer Nachricht, um ein Kontextmenü anzuzeigen, in dem Sie Nachrichtendetails anzeigen oder die einzelne Datei `.msg` herunterladen können. Wenn Sie auf Nachrichtendetails klicken, wird eine Zusammenfassung der Metadaten oder die vollständigen Metadaten der Nachricht angezeigt.

Wenn Sie eine PDF herunterladen möchten, klicken Sie oben rechts in der Zusammenfassungsansicht auf die Downloadschaltfläche.

Klicken Sie **auf die Registerkarte** Textansicht, um eine Nur-Text-Ansicht des extrahierten Texts der Teams-Unterhaltung anzeigen zu können. Dieser Nur-Text-Inhalt eignet sich für den Export, und Sie können ganz einfach mit anderen Softwaretools damit arbeiten.

Klicken Sie auf die Registerkarte **Anmerkungsansicht,** um auf Anmerkungsfeatures zu zugreifen. Auf dieser Registerkarte werden die Inhalte in einem Format angezeigt, das einer Teams-Unterhaltung ähnelt, es gibt aber auch weitere Bearbeitungsoptionen. Es gibt ein Bleistifttool, mit dem Sie Notizen erstellen, auf der Nachricht zeichnen oder feinkörnige Kratzer für Redaktionszwecke durchführen können. Es gibt auch ein **Tool** für die Flächenrotaktion, mit dem Sie ein Rechteck zeichnen können, das den Bereich verriert und als "Redacted" kennzeichnet.

Hier ist ein Beispiel für eine redacted-Datei für Unterhaltungen im Thread zwischen Benutzern.

> [!div class="mx-imgBorder"]
> ![Screenshot der redacted file](media/RedactedFileExample.png)

Unten auf der Registerkarte **Anmerkungsansicht** befindet sich die Schaltfläche **"Dokumente markieren",** auf der der Taggingbereich angezeigt wird. In diesem Bereich können Sie ein Tag auf alle Nachrichten in der Teams-Unterhaltung anwenden. Sie können eine Unterhaltung als reaktionsfähig oder nicht reaktionsfähig, privilegiert oder nicht privilegiert beschriften, unabhängig davon, ob sie "Interessante Elemente" enthält, ob sie in den Export einbezogen werden soll und ob sie weitere Überprüfungen benötigt. Sie können auch andere anpassbare Tags verwalten und anwenden.

#### <a name="action-menu"></a>Menü 'Aktion'

Im Fenster "Überprüfungssätze" können Sie  den Inhalt exportieren, indem Sie auf \> **Aktionsexport klicken.** Beim Exportieren stehen viele Optionen zur Verfügung.

Wenn Sie eine Datei exportieren möchten, die alle Metadaten für alle Teams-Nachrichten enthält, klicken Sie, um das **Kontrollkästchen Datei laden** zu aktivieren. Klicken Sie zum Hinzufügen von Tags, die Sie auf den Inhalt angewendet haben, in ihre Datei, um das Kontrollkästchen **Kategorien** zu aktivieren.

Verwenden Sie die **Option Systemeigene** Dateien, um Dateien im systemeigenen Format zu exportieren. Sie können eine Unterhaltung als eine Datei oder alle einzelnen Chatnachrichten in ihren eigenen separaten Dateien exportieren.

Mit **der Option Textdateien** können Sie Nur-Text-Versionen von Inhalten speichern. Weitere Informationen zum Abrufen einer Nur-Text-Ansicht von Teams-Unterhaltungen im Überprüfungssatz finden Sie oben unter [Zusammenfassungsansicht,](#summary-view-text-view-and-annotate-view) Textansicht und Anmerkungsansicht.

Wenn Sie auf den Inhalt redactions [](#summary-view-text-view-and-annotate-view) angewendet haben, wie im Abschnitt Zusammenfassungsansicht, Textansicht und Anmerkungsansicht oben beschrieben, können Sie die Option **Redacted Natives** durch konvertierte PDFs ersetzen auswählen, um die systemeigenen Dateien durch konvertierte Kopien in PDF zu ersetzen.

Sie können auswählen, ob Sie in einen von Microsoft bereitgestellten Azure-Blob-Speichercontainer exportieren möchten, oder Sie können Einen eigenen Azure Blob-Speichercontainer bereitstellen.

Wenn Sie mit dem Exportvorgang beginnen möchten, klicken Sie auf die **Schaltfläche** Exportieren. Weitere [Informationen dazu,](/microsoft-365/compliance/download-export-jobs) wie Sie auf den Azure-Blob-Speichercontainer zugreifen und die exportierten Inhalte herunterladen können, nachdem der Export abgeschlossen ist, finden Sie unter Herunterladen von Exportaufträgen.

> [!NOTE]
> Das Exportieren kann einen längeren Zeitraum dauern. Um den Status des Exportvorgangs nachverfolgt zu haben, verlassen Sie die Registerkarte **Überprüfungssätze,** und klicken Sie **auf** die Registerkarte Exporte.

## <a name="related-topics"></a>Verwandte Themen

- [eDiscovery in Microsoft 365](/microsoft-365/compliance/ediscovery)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
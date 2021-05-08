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
ms.openlocfilehash: ca1a679fbdce7ca2840c41266053cf13f1452fe0
ms.sourcegitcommit: 84d99b266dea2a972774d781b92eccc67d6c197a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197530"
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

Wenn Sie die PST-Datei für das Team anzeigen, werden alle Unterhaltungen im Ordner Teamchat unter Unterhaltungsverlauf gespeichert. Der Titel der Nachricht enthält den Teamnamen und den Kanalnamen. Die folgende Abbildung zeigt beispielsweise eine Nachricht von Bob, der den Standardkanal Project Produktionsspezifikationen gesendet hat.

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

## <a name="advanced-ediscovery"></a>Advanced eDiscovery

Einige Microsoft Teams können auch mithilfe des Inhaltsworkflows durchsucht [Advanced eDiscovery beibehalten werden.](/microsoft-365/compliance/overview-ediscovery-20) Während eDiscovery eine Reihe von Such-, Halte- und Exportfunktionen bietet, bietet Advanced eDiscovery Complianceadministratoren mehr Tools zum Identifizieren von Datenquellen und Analysieren ihrer Inhalte.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Advanced eDiscovery von Wasser-Workflow Teams Inhalten

100 000 Mitarbeiter sind möglicherweise Mitglied verschiedener Teams. Sie können alle Teams erfassen, die für diese Inhalte relevant sind. Anweisungen zum Workflow für Wasser finden Sie unter [Hinzufügen von Custodians zu einem Advanced eDiscovery Fall.](/microsoft-365/compliance/add-custodians-to-case)

Nachdem Sie einen Custodian hinzugefügt haben, klicken Sie auf **die Schaltfläche Weiter** und dann auf die **Schaltfläche** Hinzufügen. Anschließend wird ein Fenster angezeigt, in dem Sie aufgefordert werden, weitere Speicherorte auszuwählen, in denen alle Mitgliedschaften des Lektors und die entsprechenden SharePoint-Websitespeicherorte für ihre Daten angezeigt werden. Aus all diesen Datenquellen und Teams können Sie den Inhalt auswählen, den Sie für eDiscovery verwenden möchten, und dann diesen Benutzer und alle datenquellen, die Sie identifiziert haben, in den Halteraum setzen.

Sie können auswählen, ob die Exchange, deren Inhalt OneDrive oder beides enthalten sein soll. Exchange-Inhalt enthält alle Anwendungsinhalte in den Postfächern des Benutzers, z. B. seine E-Mails, den Teams-Inhalt, der in seinen Postfächern gespeichert ist, und so weiter. Der OneDrive-Inhalt umfasst nicht nur den Inhalt des Benutzers, sondern auch alle Teams-Inhalte, die in OneDrive gespeichert sind, z. B. 1:1-Chats, 1:N-Chats und in Chats freigegebene Dateien.

Sie haben auch die Möglichkeit, alle Teams zuzuordnen, in die der Benachrichtigungsschwader Mitglied ist, damit Kanalchatnachrichten und Dateien einbezogen werden, auf die der Benachrichtigungsverwahrungs-Mitarbeiter zugreifen kann. Darüber hinaus kann jedes andere Team einem Custodian zugeordnet werden.

> [!NOTE]
> eDiscovery von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [eDiscovery privater Kanäle.](#ediscovery-of-private-channels)

### <a name="placing-a-data-source-on-hold"></a>Platzieren einer Datenquelle im Halteraum

Wenn kein bestimmter Benutzer als Verwaltungsbenutzer bestimmt werden kann, können Sie eine gesamte Datenquelle in den Halteraum setzen. Weitere Informationen zu Halte halten finden Sie unter [Verwalten von Halte Advanced eDiscovery.](/microsoft-365/compliance/managing-holds)

Beim Erstellen eines halteraums für Teams können Sie alle Speicherorte auswählen, die Sie in Ihren Halteraum einhalten möchten. Auch wenn Benutzer Inhalte löschen oder ändern, werden im Halteraum Kopien aller früheren Versionen dieses Inhalts beibehalten.

Sie können auch eine optionale Abfrage verwenden, um Bedingungen für den Haltebereich basierend auf Schlüsselwörtern, Datumsbereich, Autor und vielen anderen Kriterien festlegen. Wenn Sie keine Schlüsselwörter angeben, unterliegen alle Daten aus dieser Datenquelle dem Halteraum.

### <a name="advanced-ediscovery-searches"></a>Advanced eDiscovery suchen

Teams Inhalt kann auch durchsucht werden. Weitere Informationen zu Suchbegriffen finden Sie unter [Sammeln von Daten für einen Fall in Advanced eDiscovery.](/microsoft-365/compliance/collecting-data-for-ediscovery) Eine Suche gibt eine gesamte Unterhaltung zurück, wenn auch nur eine Nachricht der Suchabfrage entspricht.

Beim Erstellen einer Suchabfrage können Sie 100er-Dateien auswählen, sodass alle bereits ausgewählten Quellen durchsucht werden. Sie können auch Nicht-Örtliche Quellen durchsuchen, z. B. eine Teams, die keinem Benutzer zugeordnet ist. Optionale Abfragen stehen auch zur Verfügung, um Ihre Suche innerhalb der vorhandenen Teams einengt.

Nachdem Sie eine Suche erstellt und ausgewählt haben, wird ein Fenster mit weiteren Details und Aktionen angezeigt, die Sie für die ausgewählte Suche ausführen können. Wenn Sie  auf die Schaltfläche Statistik klicken, können Sie Statistiken zu Ihrer Suche anzeigen, einschließlich Aufschlüsselungen nach Standorttypen, der ursprünglichen Quelle für den Inhalt und ob sich der Inhalt in einem Gruppenpostfach, im Postfach eines einzelnen Benutzers oder auf einer SharePoint-Website befindet. Daher können Sie eine Aufschlüsselung der Quellen sehen, die zu Ihren Suchergebnissen beitragen. Außerdem ist eine Ansicht **Abfragen** verfügbar, damit Sie sehen können, welche einzelnen Schlüsselwörter zu Ihren Ergebnissen beitragen.

Nach Abschluss der Suche können Sie  auf die Schaltfläche Ergebnisse für Überarbeitungssatz hinzufügen klicken und sie einem Überprüfungssatz hinzufügen. Weitere Informationen zu Überprüfungssätzen finden Sie unter Verwalten von Überprüfungssätzen [in Advanced eDiscovery](/microsoft-365/compliance/managing-review-sets) und Workflow [für Überprüfungssätze](#review-sets-workflow) weiter unten in diesem Artikel.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Normale Überprüfungssätze und Unterhaltungsüberprüfungssätze

Wenn Sie einem Überarbeitungssatz eine Suche hinzufügen, können Sie aus einem normalen Bewertungssatz oder einem Unterhaltungsüberprüfungssatz auswählen.

Ein normaler Überprüfungssatz ähnelt einem Export. Sie stellt die einzelnen `.msg` Dateien für den Teams und stellt den Inhalt in einer einfachen Ansicht vor. Normalerweise verwenden Sie einen normalen Überprüfungssatz, wenn Sie planen, die Dateien später mit anderen Softwaretools erneut zu bearbeiten.

Ein Unterhaltungsüberprüfungssatz bietet eine intuitivere, threadierte Ansicht der Unterhaltungen. Verwandte Nachrichten werden zusammen in der richtigen Reihenfolge angezeigt.

> [!div class="mx-imgBorder"]
> ![Screenshot des Unterhaltungsüberprüfungs-Sets](media/conversationOptions2.png)

Funktionen wie redaction sind in beiden Arten von Überprüfungssätzen verfügbar. Weitere Informationen zu Überprüfungssätzen finden Sie unter [Überprüfen von Unterhaltungen in erweiterter eDiscovery.](/microsoft-365/compliance/conversation-review-sets)

#### <a name="collection-options"></a>Sammlungsoptionen

Beim Hinzufügen zu einem Überarbeitungssatz stehen verschiedene Optionen  als Kontrollkästchen unter dem  Abschnitt Sammlungsoptionen des Fensters zur Verfügung, darunter Optionen zum Abrufen von Unterhaltungen und Teams **Unterhaltungen.** Wenn Sie diese Optionen aktivieren, werden alle Teams Nachrichten, die Teil Ihres Überprüfungssets sind, ebenfalls mit zusätzlichen Kontextmeldungen angezeigt. Wenn Ihre Abfrage beispielsweise spezifisch ist und als Ergebnis nur eine Nachricht zurückgegeben wird, werden durch Aktivieren dieser Optionen auch mehrere Nachrichten zurückgegeben, die zu der Nachricht führen und dieser folgen, die ihrer Abfrage entsprechen.

Viele logische Kriterien werden verwendet, um zu ermitteln, ob zusätzliche Nachrichten Kontext für Nachrichten bereitstellen, die Ihrer Abfrage entsprechen. Beispielsweise werden bei Teams durch Aktivieren dieser Optionen die übergeordnete Nachricht und alle untergeordneten Nachrichten abgerufen, weil die Nachrichten threaded werden.

Nachrichtenzeitstempel werden ebenfalls überprüft. Wenn eine Nachricht Ihrer Abfrage entspricht, werden benachbarte Nachrichten, die ihr innerhalb von vier Stunden vorangehen oder die innerhalb von vier Stunden folgen, als Teil der Unterhaltung betrachtet und ebenfalls in die Ergebnisse einbezogen.

Wenn Sie sicher sein müssen, welche kontextbezogenen Nachrichten mit Übereinstimmungen mit Ihrer Suchabfrage zurückgegeben werden, müssen Sie diese Optionen nicht verwenden. Sie können entweder den ganzen Inhalt sammeln oder den Datumsbereich der Suche so ausweiten, dass als Ergebnis ihrer Abfrage weitere Nachrichten zurückgegeben werden.

### <a name="review-sets-workflow"></a>Workflow für Überprüfungssätze

Sie können vorhandene Rezensionssätze anzeigen oder neue erstellen, indem Sie auf die Registerkarte **Rezensionssätze** klicken. Weitere Informationen zu Überprüfungssätzen finden Sie unter [Verwalten von Überprüfungssätzen in Advanced eDiscovery.](/microsoft-365/compliance/managing-review-sets)

Zusätzlich zu Dokumenten können Sie E-Mails, Teams Nachrichten, Yammer Nachrichten und andere Inhalte zu Ihrem Überprüfungssatz hinzufügen. Innerhalb eines Überprüfungssets können Sie auch viele derselben Vorgänge ausführen, die Sie auch in anderen Kontexten ausführen können, z. B. Durchsuchen von Inhalten und Erstellen benutzerdefinierter Abfragen. Diese Vorgänge gelten nur für Elemente, die dem Überarbeitungssatz hinzugefügt wurden.

Die **Schaltfläche "Überprüfungssätze** verwalten" bietet zusätzliche Optionen wie Analysen, zusammenfassungsberichte, die hinzugefügten Ladesätze und so weiter.

Wenn Sie auf Visualisierungen und Diagramme Ihrer Daten zugreifen möchten, klicken **Sie** oben rechts auf Individuelle Ergebnisse \> Suchprofilansicht.  Sie können in diesen Diagrammen auf Keile klicken, um interaktiv den Typ des Inhalts auszuwählen, den Sie abfragen möchten. Beispielsweise können Sie auswählen, dass nur Inhalte Teams werden. Sie können diese Abfragen auch genauso speichern, wie Sie Abfragen speichern würden, die Sie manuell schreiben.

#### <a name="summary-view-text-view-and-annotate-view"></a>Zusammenfassungsansicht, Textansicht und Anmerkungsansicht

Wenn Sie im Überarbeitungssatz auf eine Teams-Unterhaltung klicken, wird die Zusammenfassungsansicht **angezeigt,** die eine gesamte Teams-Unterhaltung als Liste von Nachrichten anzeigt, mit denen Sie einzeln interagieren können. Klicken Sie rechts neben einer Nachricht auf den Abwärtspfeil, um ein Kontextmenü anzuzeigen, in dem Sie Nachrichtendetails anzeigen oder die einzelne Datei `.msg` herunterladen können. Wenn Sie auf Nachrichtendetails klicken, wird eine Zusammenfassung der Metadaten oder der vollständigen Metadaten der Nachricht angezeigt.

Wenn Sie eine PDF-Datei herunterladen möchten, klicken Sie oben rechts in der Zusammenfassungsansicht auf die Schaltfläche "Herunterladen".

Klicken Sie **auf die Registerkarte Textansicht,** um eine Nur-Text-Ansicht des extrahierten Texts der Unterhaltung Teams anzeigen. Dieser Nur-Text-Inhalt eignet sich für den Export, und Sie können damit ganz einfach andere Softwaretools verwenden.

Klicken Sie auf die **Registerkarte Ansicht kommentieren,** um auf Anmerkungsfeatures zu zugreifen. Auf dieser Registerkarte wird der Inhalt in einem Format angezeigt, das einem Teams ähnelt, aber es gibt auch noch weitere Optionen zum Bearbeiten. Es gibt ein Bleistifttool, mit dem Sie Notizen erstellen, auf die Nachricht zeichnen oder zu Rot-für-Rot-Aktionszwecken fein absetzen können. Es gibt auch ein **Redaction-Tool** für den Bereich, mit dem Sie ein Rechteck zeichnen können, das den Bereich schwarz ausriert, und es als "Rotfakte" kennzeichnet.

Hier ist ein Beispiel für eine rot markierte Datei für unterhaltungsthreads zwischen Benutzern.

> [!div class="mx-imgBorder"]
> ![Screenshot der rot markierten Datei](media/RedactedFileExample.png)

Am unteren Rand der Registerkarte **Anmerkungsansicht** befindet sich die Schaltfläche **Dokumente markieren,** auf der der Markierungsbereich angezeigt wird. In diesem Bereich können Sie eine Markierung auf alle Nachrichten in der Unterhaltung Teams anwenden. Sie können eine Unterhaltung als reaktionsschnell oder nicht reaktionsschnell, privilegierte oder nicht privilegierte Unterhaltungen beschriften, ganz gleich, ob sie "Interessante Elemente" enthält, ob sie in den Export einbezogen werden soll und ob sie einer weiteren Überprüfung bedarf. Sie können auch andere anpassbare Kategorien verwalten und anwenden.

#### <a name="action-menu"></a>Aktionsmenü

Im Fenster mit den Überprüfungssätzen können Sie den Inhalt exportieren, indem Sie auf **Aktionsexport** \> **klicken.** Beim Exportieren stehen viele Optionen zur Verfügung.

Wenn Sie eine Datei exportieren möchten, die alle Metadaten für Teams Nachrichten enthält, klicken Sie, um **das** Kontrollkästchen Datei laden zu aktivieren. Wenn Sie tags, die Sie auf den Inhalt angewendet haben, in Ihre Datei hinzufügen möchten, klicken Sie, um das Kontrollkästchen **Kategorien** zu aktivieren.

Verwenden Sie die **Option Native** Dateien, um Dateien in ihrem nativen Format zu exportieren. Sie können eine Unterhaltung als eine Datei oder alle einzelnen Chatnachrichten in eigenen separaten Dateien exportieren.

Mit **der Option Textdateien** können Sie Nur-Text-Versionen von Inhalten speichern. Weitere Informationen dazu, wie Sie eine Nur-Text-Ansicht Teams Unterhaltungen im Überarbeitungssatz erhalten, finden Sie oben unter Zusammenfassungsansicht, Textansicht und [Anmerkungsansicht.](#summary-view-text-view-and-annotate-view)

Wenn Sie wie oben im Abschnitt [Zusammenfassungsansicht,](#summary-view-text-view-and-annotate-view) Textansicht und Anmerkungsansicht beschrieben Redactions auf den Inhalt angewendet haben, können Sie die Option Native Dateien durch konvertierte **PDFs** ersetzen aktivieren, um die systemeigenen Dateien durch konvertierte Kopien in PDF zu ersetzen.

Sie können in einen von Microsoft bereitgestellten Azure BLOB-Speichercontainer exportieren, oder Sie können einen eigenen Azure BLOB-Speichercontainer bereitstellen.

Wenn Sie bereit sind, den Exportvorgang zu starten, klicken Sie auf **die Schaltfläche** Exportieren. Weitere [Informationen dazu,](/microsoft-365/compliance/download-export-jobs) wie Sie nach Abschluss des Exports auf den Azure BLOB-Speichercontainer zugreifen und Ihre exportierten Inhalte herunterladen können, finden Sie unter Herunterladen von Exportaufträgen.

> [!NOTE]
> Das Exportieren kann eine längere Zeit dauern. Um den Status des Exportvorgangs nachverfolgt zu können, verlassen Sie die Registerkarte **Überprüfen von Sätzen,** und klicken Sie auf die **Registerkarte** Exporte.

## <a name="related-topics"></a>Verwandte Themen

- [eDiscovery in Microsoft 365](/microsoft-365/compliance/ediscovery)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
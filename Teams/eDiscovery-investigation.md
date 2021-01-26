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
description: Hier erfahren Sie, was Sie tun müssen, wenn Sie eDiscovery ausführen müssen, z. B. wenn Sie alle elektronisch gespeicherten Informationen für juristische Verfahren einreichen müssen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa6b1212fda3983cc612885e41aa1131bb6f496d
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980459"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams

Große Unternehmen werden häufig mit hohen Juristischen Bußerforderungen ausgesetzt, die die Einsendung aller elektronisch gespeicherten Informationen (Electronically Stored Information, ESI) erfordern. Microsoft Teams-Inhalte können während eDiscovery-Untersuchungen durchsucht und verwendet werden.

## <a name="overview"></a>Übersicht

Alle Microsoft Teams 1:1- oder Gruppenchats werden in einem Journal bis zu den Postfächern der jeweiligen Benutzer angezeigt. Alle Standardkanalnachrichten werden bis zum Gruppenpostfach, das das Team darstellt, in einem Journal angezeigt. In Standardkanäle hochgeladene Dateien werden unter den eDiscovery-Funktionen für SharePoint Online und OneDrive for Business behandelt.

eDiscovery von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [eDiscovery privater Kanäle.](#ediscovery-of-private-channels)

Nicht alle Inhalte von Teams sind eDiscoverable. Die folgende Tabelle zeigt die Inhaltstypen, nach deren Hilfe Sie mithilfe der Microsoft eDiscovery-Tools suchen können:

| Inhaltstyp | eDiscoverable | Hinweise |
|:--- | :--- |:--- |
|Audioaufzeichnungen | Nein | |
|Karteninhalt|Ja|Weitere [Informationen finden Sie unter "Suchen nach Karteninhalten".](#search-for-card-content)|
|Chatlinks | Ja | |
|Chatnachrichten | Ja |Dies umfasst Inhalte in Teams-Kanälen, 1:1-Chats, 1:N-Gruppenchats und Chats mit Gastbenutzerteilnehmern.  |
|Codeausschnitte | Nein | |
|Bearbeitete Nachrichten | Ja | Wenn sich der Benutzer im Halteraum befindet, werden auch frühere Versionen bearbeiteter Nachrichten beibehalten. |
|Emojis, GIFs und Aufkleber | Ja | |
|Inlinebilder | Ja | |
|Chatunterhaltungen in Besprechungen | Ja | |
|Besprechungsmetadaten<sup>1</sup> | Ja |  |
|Name des Kanals | Nein | |
|Nachrichten in privaten Kanälen | Ja | |
|Angebote | Ja | Zitierte Inhalte können durchsucht werden. Die Suchergebnisse deuten jedoch nicht darauf hin, dass der Inhalt zitiert wurde. |
|Reaktionen (z. B. "Likes", "Herzen" und andere Reaktionen) | Nein | |
|Betreff | Ja | |
|Tabellen | Ja | |
|||

<sup>1 Metadaten</sup> für Besprechungen (und Anrufe) umfassen Folgendes:

- Start- und Endzeit und Dauer der Besprechung
- Teilnehmen an besprechungen und Ereignisse für jeden Teilnehmer verlassen
- VOIP-Teilnahme/-Anrufe
- Anonyme Teilnahme
- Verbundbenutzer beitreten
- Gastbenutzer beitreten

  Die Abbildung zeigt ein Beispiel für Besprechungsmetadaten.

  > [!div class="mx-imgBorder"]
  > ![Bild der Metadaten der CVR-Aufzeichnungen für Besprechungen.](media/conversationOption3.png)

Hier sehen Sie ein Beispiel für eine Unterhaltung zwischen Teilnehmern während der Besprechung.

![Unterhaltung zwischen Teilnehmern in Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Unterhaltung zwischen Teilnehmern in eDiscovery-Suchergebnissen.](media/MeetingImConversation2.png)

Weitere Informationen zum Durchführen einer eDiscovery-Untersuchung finden Sie unter ["Erste Schritte mit Core eDiscovery".](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)

Microsoft Teams-Daten werden als Chat oder Unterhaltungen in der Excel eDiscovery-Exportausgabe angezeigt. Sie können die Datei `.pst` in Outlook öffnen, um diese Nachrichten nach dem Export anzeigen.

Wenn Sie die DATEI "PST" für das Team anzeigen, werden alle Unterhaltungen im Ordner "Teamchat" unter "Unterhaltungsverlauf" gespeichert. Der Titel der Nachricht enthält den Teamnamen und den Kanalnamen. Die folgende Abbildung zeigt beispielsweise eine Nachricht von Bob, der den Standardkanal von Project 7 des Teams für Fertigungsspezifikationen gesendet hat.

![Screenshot eines Teamchatordners im Postfach eines Benutzers in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Private Chats im Postfach eines Benutzers werden im Ordner "Teamchat" unter "Unterhaltungsverlauf" gespeichert.

## <a name="ediscovery-of-private-channels"></a>eDiscovery privater Kanäle

Einträge für Nachrichten, die in einem privaten Kanal gesendet werden, werden an das Postfach aller Mitglieder des privaten Kanals und nicht an ein Gruppenpostfach übermittelt. Die Titel der Einträge sind so formatiert, dass sie angeben, von welchem privaten Kanal sie gesendet wurden.

Da jeder private Kanal über eine eigene SharePoint-Website verfügt, die von der übergeordneten Teamwebsite getrennt ist, werden Dateien in einem privaten Kanal unabhängig vom übergeordneten Team verwaltet.

Teams unterstützt keine eDiscovery-Suche eines einzelnen Kanals innerhalb eines Teams, daher muss das gesamte Team durchsucht werden. Um eine eDiscovery-Suche nach Inhalten in einem privaten Kanal durchzuführen, suchen Sie im Team, in der Websitesammlung, die dem privaten Kanal zugeordnet ist (um Dateien zu enthalten), und nach Postfächern von Mitgliedern privater Kanäle (um Nachrichten mit zu verwenden).

Verwenden Sie die folgenden Schritte, um Dateien und Nachrichten in einem privaten Kanal zu identifizieren, die in Ihre eDiscovery-Suche miteinbehebbar sein sollen.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Schließen Sie private Kanaldateien in eine eDiscovery-Suche ein.

Bevor Sie diese Schritte ausführen, installieren Sie die [SharePoint Online-Verwaltungsshell, und stellen Sie eine Verbindung mit SharePoint Online herzustellen.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. Führen Sie Folgendes aus, um eine Liste aller SharePoint-Websitesammlungen zu erhalten, die privaten Kanälen im Team zugeordnet sind.

    ```PowerShell
    Get-SPOSite
    ```

2. Führen Sie das folgende PowerShell-Skript aus, um eine Liste aller SHAREPoint-Websitesammlungs-URLs, die privaten Kanälen im Team zugeordnet sind, und die ID der übergeordneten Teamgruppe zu erhalten.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Führen Sie für jede Team- oder Gruppen-ID das folgende PowerShell-Skript aus, um alle relevanten Websites privater Kanäle zu identifizieren, wobei $groupID die Gruppen-ID des Teams ist.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Schließen Sie Nachrichten privater Kanäle in eine eDiscovery-Suche ein

Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie die neueste Version des [Teams -PowerShell-Moduls installiert](teams-powershell-overview.md) haben.

1. Führen Sie den folgenden Befehl aus, um eine Liste der privaten Kanäle im Team zu erhalten.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Führen Sie den folgenden Befehl aus, um eine Liste der Mitglieder privater Kanäle zu erhalten.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Fügen Sie die Postfächer aller Mitglieder aus jedem privaten Kanal im Team in Ihre [eDiscovery-Suchabfrage ein.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)

## <a name="search-for-content-for-guest-users"></a>Suchen nach Inhalten für Gastbenutzer

Sie können eDiscovery-Tools verwenden, um nach Teams-Inhalten zu suchen, die sich auf Gastbenutzer in Ihrer Organisation bezogen. Teams-Chatinhalte, die einem Gastbenutzer zugeordnet sind, bleiben an einem cloudbasierten Speicherort erhalten und können mithilfe von eDiscovery durchsucht werden. Dies schließt die Suche nach Inhalten in Chatunterhaltungen zwischen 1:1 und 1:N ein, bei denen ein Gastbenutzer mit anderen Benutzern in Ihrer Organisation teilt. Sie können auch nach Nachrichten in privaten Kanälen suchen, an denen ein Gastbenutzer beteiligt ist, und nach Inhalten in Gast-:Gast-Chat-Unterhaltungen suchen, bei denen nur Gastbenutzer die Teilnehmer sind. 

So suchen Sie nach Inhalten für Gastbenutzer:

1. Stellen Sie eine Verbindung mit Azure AD PowerShell bereit. Anweisungen finden Sie im Abschnitt "Herstellen einer Verbindung mit Azure Active Directory PowerShell" in "Herstellen einer Verbindung mit [Microsoft 365 mit PowerShell".](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) Stellen Sie sicher, dass Sie Schritt 1 und Schritt 2 im vorherigen Thema abgeschlossen haben.

2. Nachdem Sie erfolgreich eine Verbindung mit Azure AD PowerShell hergestellt haben, führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen (User Principal Name, UPN) für alle Gastbenutzer in Ihrer Organisation anzeigen. Sie müssen den UPN des Gastbenutzers verwenden, wenn Sie die Suche in Schritt 4 erstellen.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Statt eine Liste der Benutzerprinzipalnamen auf dem Computerbildschirm anzuzeigen, können Sie die Ausgabe des Befehls an eine Textdatei umleiten. Dazu können Sie den `> filename.txt` vorherigen Befehl anfügen. Die Textdatei mit den Benutzerprinzipalnamen wird im aktuellen Ordner gespeichert.

3. Stellen Sie in Windows PowerShell Fenster eine Verbindung mit Security & Compliance Center PowerShell herzustellen. Anweisungen finden Sie unter "Herstellen einer Verbindung mit [Security & Compliance Center PowerShell".](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Sie können eine Verbindung mit oder ohne mehrstufige Authentifizierung herstellen.

4. Erstellen Sie eine Inhaltssuche, die nach allen Inhalten (z. B. Chatnachrichten und E-Mail-Nachrichten) sucht, an der der angegebene Gastbenutzer teilnehmer war, indem Sie den folgenden Befehl ausführen.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Um beispielsweise nach Inhalten zu suchen, die der Gastbenutzerin Sara Davis zugeordnet sind, führen Sie den folgenden Befehl aus.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Weitere Informationen zur Verwendung von PowerShell zum Erstellen von Inhaltssuchen finden Sie unter ["New-ComplianceSearch".](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

5. Führen Sie den folgenden Befehl aus, um die in Schritt 4 erstellte Inhaltssuche zu starten:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com) "Alle Inhaltssuche anzeigen", **und** klicken  >  **Sie dann auf "Alle Inhalte anzeigen".**

7. Wählen Sie in der Liste der Suchbegriffe die Suche aus, die Sie in Schritt 4 erstellt haben, um die Flyoutseite anzeigen.

8. Auf der Flyoutseite können Sie die folgenden Schritte tun:

   - Klicken Sie **auf "Ergebnisse anzeigen",** um die Suchergebnisse anzuzeigen und eine Vorschau des Inhalts anzuzeigen.

   - Klicken Sie neben dem **Feld "Abfrage"** **auf** "Bearbeiten", um die Suche zu bearbeiten, und führen Sie dann die Suche erneut aus. Sie können z. B. eine Suchabfrage hinzufügen, um die Ergebnisse zu einengt.

   - Klicken Sie **auf "Ergebnisse exportieren",** um die Suchergebnisse zu exportieren und herunterzuladen.

## <a name="search-for-card-content"></a>Suchen nach Karteninhalten

Karteninhalte, die von Apps in Teams-Kanälen, 1:1-Chats und 1xN-Chats generiert werden, werden in Postfächern gespeichert und können durchsucht werden. Eine *Karte* ist ein Benutzeroberflächencontainer für kurze Inhalte. Karten können mehrere Eigenschaften und Anlagen aufweisen und Schaltflächen enthalten, die Kartenaktionen auslösen können. Weitere Informationen finden Sie unter ["Karten"](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Wie andere Teams-Inhalte basiert der Ort, an dem Karteninhalte gespeichert werden, auf dem Ort, an dem die Karte verwendet wurde. Inhalte für Karten, die in einem Kanal in Teams verwendet werden, werden im Gruppenpostfach von Teams gespeichert. Karteninhalte für 1:1- und 1xN-Chats werden in den Postfächern der Chatteilnehmer gespeichert.

Um nach Karteninhalten zu suchen, können Sie die `kind:microsoftteams` `itemclass:IPM.SkypeTeams.Message` Suchbedingungen verwenden. Bei der Überprüfung der Suchergebnisse hat der von Bots in einem Teamkanal generierte Karteninhalt die E-Mail-Eigenschaft **"Absender/Autor"** als , wobei sich der Name der App befindet, die den Karteninhalt `<appname>@teams.microsoft.com` `appname` generiert hat. Wenn Karteninhalte von einem Benutzer generiert wurden, wird der Benutzer durch den Wert **"Absender/Autor"** identifiziert.

Beim Anzeigen von Karteninhalten in inhaltssuchergebnissen wird der Inhalt als Anlage der Nachricht angezeigt. Die Anlage hat den Namen der App, die `appname.html` den `appname` Karteninhalt generiert hat. Die folgenden Screenshots zeigen, wie Karteninhalte (für eine App namens Asana) in Teams und in den Ergebnissen einer Suche angezeigt werden.

**Karteninhalte in Teams**

![Card content in Teams channel message](media/CardContentTeams.png)

**Karteninhalte in Suchergebnissen**
  
![Derselbe Karteninhalt in den Ergebnissen einer Inhaltssuche](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Um derzeit Bilder aus Karteninhalten in den Suchergebnissen anzuzeigen (z. B. die Häkchen im vorherigen Screenshot), müssen Sie bei Teams angemeldet sein (auf einer anderen Registerkarte in derselben Browsersitzung, die Sie zum Anzeigen der Suchergebnisse https://teams.microsoft.com) verwenden. Andernfalls werden Bildplatzhalter angezeigt.

## <a name="advanced-ediscovery"></a>Advanced eDiscovery

Einige Microsoft Teams-Inhalte können auch mithilfe des erweiterten [eDiscovery-Workflows](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)durchsucht und beibehalten werden. Während eDiscovery eine Reihe von Such-, Halte- und Exportfunktionen bietet, bietet Advanced eDiscovery Complianceadministratoren mehr Tools zum Identifizieren von Datenquellen und Analysieren ihrer Inhalte.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Advanced eDiscovery custodian workflow for Teams content

Wasser kann ein Mitglied verschiedener Teams sein. Sie können Teams-Inhalte erfassen, die für diese Custodians relevant sind. Anweisungen zum Workflow für Ausgabevermittler finden Sie unter "Hinzufügen von [Mittlern zu einem erweiterten eDiscovery-Fall".](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)

Klicken Sie nach dem Hinzufügen eines Custodians auf die Schaltfläche **"Weiter"** und dann auf **die Schaltfläche "Hinzufügen".** Anschließend wird ein Fenster angezeigt, in dem Sie aufgefordert werden, weitere Speicherorte auszuwählen, in denen alle Mitgliedschaften des Zugehörigkeitsverwahrungsmitglieds und die entsprechenden Speicherorte für die zugehörigen SharePoint-Websitedaten angezeigt werden. In all diesen Datenquellen und Teams können Sie den Inhalt auswählen, den Sie für eDiscovery verwenden möchten, und dann diesen Benutzer und alle von Ihnen identifizierten Datenquellen in einen Haltespeicher setzen.

Sie können auswählen, ob ihre Exchange-Inhalte, deren #A0 oder beides enthalten sein soll. Die Inhalte von Exchange umfassen alle Anwendungsinhalte in den Postfächern des Benutzers, z. B. deren E-Mails, die teams-Inhalte, die in ihrem Postfach gespeichert sind, und so weiter. Die #A0 umfassen nicht nur die Inhalte des Benutzers, sondern auch alle Teams-Inhalte, die auf OneDrive gespeichert sind, z. B. 1:1-Chats, 1:N-Chats und in Chats freigegebene Dateien.

Sie haben auch die Möglichkeit, alle Teams zuzuordnen, in deren Mitglied der Benachrichtigungsverwahrung die Kanalchatnachrichten und Dateien, auf die der Benachrichtigungsverwaderer zugreifen kann, eingeschlossen werden. Darüber hinaus kann jedes andere Team einem 1000-Mitarbeiter zugeordnet werden.

> [!NOTE]
> eDiscovery von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [eDiscovery privater Kanäle.](#ediscovery-of-private-channels)

### <a name="placing-a-data-source-on-hold"></a>Platzieren einer Datenquelle im Halteraum

Wenn kein bestimmter Benutzer als Verwaltungsverwaltungsbenutzer bestimmt werden soll, können Sie eine gesamte Datenquelle in den Halteraum setzen. Weitere Informationen zu Halte-E-Mails finden Sie unter ["Verwalten von Halte hält in Advanced eDiscovery".](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)

Wenn Sie einen Halteraum für Teams-Inhalte erstellen, können Sie alle Speicherorte auswählen, die Sie in Ihren Halteraum aufsuchen möchten. Auch wenn Benutzer Inhalte löschen oder ändern, werden im Halteraum Kopien aller vorherigen Versionen dieses Inhalts beibehalten.

Sie können auch eine optionale Abfrage verwenden, um Bedingungen für den Haltebereich basierend auf Schlüsselwörtern, Datumsbereich, Autor und vielen anderen Kriterien festlegen. Wenn Sie keine Schlüsselwörter angeben, unterliegen alle Daten aus dieser Datenquelle dem Halteraum.

### <a name="advanced-ediscovery-searches"></a>Erweiterte eDiscovery-Suchen

Der Inhalt von Teams kann auch durchsucht werden. Weitere Informationen zu Suchen finden Sie unter "Sammeln von Daten [für einen Fall in Der erweiterten eDiscovery".](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery) Eine Suche gibt eine gesamte Unterhaltung zurück, wenn auch nur eine Nachricht der Suchabfrage entspricht.

Wenn Sie eine Suchabfrage erstellen, können Sie 00er auswählen, damit alle quellen, die Sie bereits ausgewählt haben, durchsucht werden. Sie können auch Quellen durchsuchen, die nicht in den Schutz der Benutzer stehen, z. B. eine Teams-Website, die keinem Benutzer zugeordnet ist. Optionale Abfragen sind auch verfügbar, um Ihre Suche innerhalb der Inhalte von Teams zu eindinnen.

Nachdem Sie eine Suche erstellt und ausgewählt haben, wird ein Fenster mit weiteren Details und Aktionen angezeigt, die Sie für die ausgewählte Suche ausführen können. Wenn Sie  auf die Schaltfläche "Statistik" klicken, können Sie Statistiken zu Ihrer Suche anzeigen, einschließlich Aufschlüsselungen nach Standorttypen, der ursprünglichen Quelle für den Inhalt und ob sich der Inhalt in einem Gruppenpostfach, dem einzelnen Benutzerpostfach oder einer SharePoint-Website befindet. Daher können Sie eine Aufschlüsselung der Quellen sehen, die zu Ihren Suchergebnissen beitragen. Darüber hinaus ist eine **Ansicht "Abfragen"** verfügbar, damit Sie sehen können, welche einzelnen Schlüsselwörter zu Ihren Ergebnissen beitragen.

Nachdem Sie die Suche endgültig festgelegt  haben, können Sie auf die Schaltfläche "Ergebnisse hinzufügen, um die Gruppe zu überprüfen" klicken und sie einem Überarbeitungssatz hinzufügen. Weitere Informationen zu Überprüfungssätzen finden Sie unter "Verwalten von Überprüfungssätzen in den Workflows ["Erweiterte eDiscovery"](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) und ["Überprüfungssätze"](#review-sets-workflow) weiter unten in diesem Artikel.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Normale Überprüfungssätze und Unterhaltungsüberprüfungssätze

Beim Hinzufügen einer Suche zu einem Bewertungssatz können Sie aus einem normalen Bewertungssatz oder einem Unterhaltungsüberprüfungssatz auswählen.

Ein normaler Überprüfungssatz ähnelt einem Export. Sie stellt die einzelnen Dateien für die Inhalte von Teams zur Anzeige der `.msg` Inhalte in einer einfachen Ansicht zur Anzeige zur Ansicht vor. Normalerweise verwenden Sie einen normalen Überprüfungssatz, wenn Sie planen, die Dateien später mit anderen Softwaretools erneut zu bearbeiten.

Ein Unterhaltungsüberprüfungssatz bietet eine intuitivere Ansicht der Unterhaltungen mit Threads. Verknüpfte Nachrichten werden zusammen in der richtigen Reihenfolge angezeigt.

> [!div class="mx-imgBorder"]
> ![Screenshot des Unterhaltungsüberprüfungssets](media/conversationOptions2.png)

Funktionen wie Redaction sind in beiden Arten von Überprüfungssätzen verfügbar. Weitere Informationen zu Überprüfungssätzen finden Sie unter ["Überprüfen von Unterhaltungen in erweiterter eDiscovery".](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)

#### <a name="collection-options"></a>Sammlungsoptionen

Beim Hinzufügen zu einem Überarbeitungssatz stehen verschiedene Optionen  als Kontrollkästchen im Abschnitt  "Sammlungsoptionen" des Fensters zur Verfügung, darunter Optionen für Abruf von Unterhaltungen und **Teams-Unterhaltungen.** Wenn Sie diese Optionen aktivieren, werden auch alle einzelnen Teams-Nachrichten, die Teil Ihres Überprüfungssets sind, mit zusätzlichen Nachrichten angezeigt, die den Kontext enthalten. Wenn Ihre Abfrage z. B. spezifisch ist und als Ergebnis nur eine Nachricht zurückgegeben wird, werden durch Aktivieren dieser Optionen auch mehrere Nachrichten zurückgegeben, die zu der Nachricht führen und dieser folgen, die ihrer Abfrage entsprechen.

Viele logische Kriterien werden verwendet, um zu bestimmen, ob zusätzliche Nachrichten Kontext für Nachrichten bereitstellen, die Ihrer Abfrage entsprechen. Beispielsweise werden bei Teams-Inhalten, wenn diese Optionen aktiviert werden, die übergeordnete Nachricht und alle untergeordneten Nachrichten abgerufen, weil die Nachrichten threaded werden.

Nachrichtenzeitstempel werden ebenfalls überprüft. Wenn eine Nachricht Ihrer Abfrage entspricht, werden benachbarte Nachrichten, die ihr innerhalb von vier Stunden vorangehen oder die innerhalb von 4 Stunden folgen, als Teil der Unterhaltung betrachtet und ebenfalls in die Ergebnisse einbezogen.

Wenn Sie sicher sein müssen, welche kontextbezogenen Nachrichten mit Übereinstimmungen mit Ihrer Suchabfrage zurückgegeben werden, müssen Sie diese Optionen nicht verwenden. Sie können entweder alle Inhalte sammeln oder den Datumsbereich der Suche ausweiten, sodass als Ergebnis Ihrer Abfrage weitere Nachrichten zurückgegeben werden.

### <a name="review-sets-workflow"></a>Workflow für Überprüfungssätze

Sie können vorhandene Bewertungssätze anzeigen oder neue erstellen, indem Sie auf die Registerkarte **"Bewertungssätze"** klicken. Weitere Informationen zu Überprüfungssätzen finden Sie unter ["Verwalten von Überprüfungssätzen in Der erweiterten eDiscovery".](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)

Zusätzlich zu Dokumenten können Sie E-Mails, Teams-Nachrichten, Yammer-Nachrichten und andere Inhalte zu Ihrem Überprüfungssatz hinzufügen. Innerhalb eines Überprüfungssets können Sie auch viele derselben Vorgänge ausführen, die Sie auch in anderen Kontexten ausführen können, z. B. das Durchsuchen von Inhalten und das Erstellen von benutzerdefinierten Abfragen. Diese Vorgänge gelten nur für Elemente, die dem Überarbeitungssatz hinzugefügt wurden.

Die **Schaltfläche "Überprüfungssätze** verwalten" bietet zusätzliche Optionen, z. B. Analyse, Zusammenfassungsberichte, wie viele Ladesätze hinzugefügt wurden, und so weiter.

Wenn Sie auf Visualisierungen und Diagramme Ihrer Daten zugreifen möchten, klicken **Sie** oben rechts auf die Profilansicht für die Suche \>  einzelner Ergebnisse. Sie können in diesen Diagrammen auf Keile klicken, um interaktiv den Inhaltstyp auszuwählen, den Sie abfragen möchten. Sie können z. B. auswählen, dass nur Der Inhalt von Teams abgefragt werden soll. Sie können diese Abfragen auch genauso wie manuell geschriebene Abfragen speichern.

#### <a name="summary-view-text-view-and-annotate-view"></a>Zusammenfassungsansicht, Textansicht und Ansicht mit Anmerkungen

Wenn Sie in der Gruppe der Überprüfungen auf eine Unterhaltung in Teams klicken, wird die Zusammenfassungsansicht **angezeigt,** in der eine gesamte Team-Unterhaltung als Liste von Nachrichten angezeigt wird, mit denen Sie einzeln interagieren können. Klicken Sie rechts neben einer Nachricht auf den Abwärtspfeil, um ein Kontextmenü anzuzeigen, in dem Sie Nachrichtendetails anzeigen oder die einzelne Datei `.msg` herunterladen können. Wenn Sie auf die Nachrichtendetails klicken, wird eine Zusammenfassung der Metadaten oder der vollständigen Metadaten der Nachricht angezeigt.

Wenn Sie eine PDF herunterladen möchten, klicken Sie oben rechts in der Zusammenfassungsansicht auf die Schaltfläche "Herunterladen".

Klicken Sie **auf die Registerkarte "Textansicht",** um eine Nur-Text-Ansicht des extrahierten Texts der Teams-Unterhaltung anzeigen. Dieser Nur-Text-Inhalt eignet sich für den Export, und Sie können damit ganz einfach andere Softwaretools verwenden.

Klicken Sie auf die Registerkarte **Ansicht kommentieren,** um auf Anmerkungsfeatures zu zugreifen. Auf dieser Registerkarte wird der Inhalt in einem Format angezeigt, das einer Unterhaltung in Teams ähnelt, aber es gibt auch weitere Optionen für die Bearbeitung. Es gibt ein Bleistifttool, mit dem Sie Notizen erstellen, auf die Nachricht zeichnen oder zu Redactionzwecken fein abfingen können. Es gibt auch ein **Area-Redaction-Tool,** mit dem Sie ein Rechteck zeichnen können, das den Bereich auss blacked und als "Redacted" kennzeichnet.

Hier ist ein Beispiel für eine rot markierte Datei für unterhaltungsthreads zwischen Benutzern.

> [!div class="mx-imgBorder"]
> ![Screenshot einer rot markierten Datei](media/RedactedFileExample.png)

Am unteren Rand der Registerkarte "Ansicht mit **Anmerkungen"** befindet sich die Schaltfläche **"Dokumente markieren",** auf der der Taggingpanel angezeigt wird. In diesem Bereich können Sie eine Markierung auf alle Nachrichten in der Unterhaltung in Teams anwenden. Sie können eine Unterhaltung als reaktionsfähig oder nicht reaktionsfähig, privilegierte oder nicht privilegierte Unterhaltung beschriften, ganz gleich, ob sie "Interessante Elemente" enthält, ob sie in den Export einbezogen werden soll und ob sie weitere Überprüfungen benötigt. Sie können auch andere anpassbare Tags verwalten und anwenden.

#### <a name="action-menu"></a>Aktionsmenü

Innerhalb des Fensters mit den Überprüfungssätzen können Sie den Inhalt exportieren, indem Sie auf **"Aktionsexport"** \> **klicken.** Beim Exportieren stehen viele Optionen zur Verfügung.

Wenn Sie eine Datei exportieren möchten, die alle Metadaten aller Teams-Nachrichten enthält, klicken Sie, um das Kontrollkästchen **"Datei laden"** zu aktivieren. Wenn Sie der Datei Tags hinzufügen möchten, die Sie auf den Inhalt angewendet haben, klicken Sie, um das Kontrollkästchen **"Kategorien"** zu aktivieren.

Verwenden Sie die **Option "Native** Dateien", um Dateien in ihrem systemeigenen Format zu exportieren. Sie können eine Unterhaltung als eine Datei oder alle einzelnen Chatnachrichten in eigenen separaten Dateien exportieren.

Mit **der Option "Textdateien"** können Sie Nur-Text-Versionen von Inhalten speichern. Weitere Informationen dazu, wie Sie eine Nur-Text-Ansicht von Teams-Unterhaltungen im Überarbeitungssatz erhalten, finden Sie oben in der Zusammenfassungsansicht, der Textansicht und der [Anmerkungsansicht.](#summary-view-text-view-and-annotate-view)

Wenn Sie auf den Inhalt Wie im Abschnitt "Zusammenfassungsansicht", "Textansicht" und "Anmerkungsansicht" oben beschrieben, Redactions auf den Inhalt angewendet haben, können Sie die Option "Natives ersetzen durch konvertierte **PDFs** ersetzen" aktivieren, um die systemeigenen Dateien durch konvertierte Kopien in PDF zu ersetzen. [](#summary-view-text-view-and-annotate-view)

Sie können in einen von Microsoft bereitgestellten Azure-BLOB-Speichercontainer exportieren, oder Sie können Ihren eigenen Azure Blob Storage Container bereitstellen.

Wenn Sie mit dem Exportvorgang beginnen möchten, klicken Sie auf die **Schaltfläche "Exportieren".** Weitere Informationen dazu, wie Sie nach Abschluss des Exports auf den Azure-BLOB-Speichercontainer zugreifen und ihre exportierten Inhalte herunterladen können, finden Sie unter ["Exportaufträge](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) herunterladen".

> [!NOTE]
> Der Export kann längere Zeit dauern. Um den Status des Exportvorgangs nachverfolgt zu werden, verlassen Sie die Registerkarte **"Überprüfen-Sätze",** und klicken Sie auf die Registerkarte **"Exporte".**

## <a name="related-topics"></a>Verwandte Themen

- [eDiscovery in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

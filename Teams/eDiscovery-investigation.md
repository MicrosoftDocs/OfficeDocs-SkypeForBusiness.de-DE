---
title: Durchführen einer eDiscovery-Untersuchung von Inhalten
author: v-tophillips
ms.author: v-tophillips
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
description: Erfahren Sie, was Sie tun müssen, wenn Sie eDiscovery durchführen müssen, z. B. wenn Sie alle elektronisch gespeicherten Informationen für rechtliche Verfahren übermitteln müssen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac4aa6e8182342f36da0434aaf78123937d6d8ce
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616411"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams

Große Unternehmen sind häufig Strafverfahren ausgesetzt, die die Einreichung aller elektronisch gespeicherten Informationen (ESI) verlangen. Microsoft Teams-Inhalte können während eDiscovery-Untersuchungen durchsucht und verwendet werden.

## <a name="overview"></a>Übersicht

Alle Microsoft Teams 1:1- oder Gruppenchats werden bis zu den Postfächern der jeweiligen Benutzer aufgezeichnet. Alle Standardkanalnachrichten werden bis zum Gruppenpostfach aufgezeichnet, das das Team darstellt. Dateien, die in Standardkanäle hochgeladen werden, werden unter die eDiscovery-Funktionalität für SharePoint Online und OneDrive for Business abgedeckt.

eDiscovery von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [eDiscovery privater Kanäle](#ediscovery-of-private-and-shared-channels).

Nicht alle Teams-Inhalte sind eDiscoverable. In der folgenden Tabelle sind die Inhaltstypen aufgeführt, nach denen Sie mithilfe von Microsoft eDiscovery-Tools suchen können:

|Inhaltstyp|eDiscoverable|Hinweise|
|---|---|---|
|Audioaufzeichnungen|Ja||
|Karteninhalt|Ja|Weitere Informationen finden [Sie unter "Nach Karteninhalt suchen](#search-for-card-content) ".|
|Chatlinks|Ja||
|Chatnachrichten|Ja|Dazu gehören Inhalte in standardmäßigen Teams-Kanälen, 1:1-Chats, 1:N-Gruppenchats und Chats mit Gastbenutzerteilnehmern.|
|Codeausschnitte|Nein||
|Bearbeitete Nachrichten|Ja|Wenn sich der Benutzer im Haltebereich befindet, bleiben auch frühere Versionen bearbeiteter Nachrichten erhalten.|
|Emojis, GIFs und Aufkleber|Ja||
|Feedbenachrichtigungen|Nein||
|Inlinebilder|Ja||
|Schleifenkomponenten|Ja|Inhalt in einer Schleifenkomponente wird in einer FLUID-Datei gespeichert, die im OneDrive for Business Konto des Benutzers gespeichert wird, der die Schleifenkomponente sendet. Dies bedeutet, dass Sie OneDrive als Datenquelle bei der Suche nach Inhalten in Schleifenkomponenten einschließen müssen.|
|Chatunterhaltungen für Besprechungen|Ja||
|Besprechungsmetadaten<sup>1</sup>|Ja||
|Name des Kanals|Ja||
|Zitate|Ja|Zitierte Inhalte können durchsucht werden. Die Suchergebnisse deuten jedoch nicht darauf hin, dass der Inhalt zitiert wurde.|
|Reaktionen (z. B. Likes, Herzen und andere Reaktionen)|Ja|Reaktionen werden nach dem 1. Juni 2022 für alle gewerblichen Kunden unterstützt. Reaktionen vor diesem Datum sind für eDiscovery nicht verfügbar. Government Cloud Support ist geplant. Es gibt keine gesetzliche Aufbewahrungspflicht für Reaktionen.|
|Betreff|Ja||
|Tabellen|Ja||

<sup>1</sup> Besprechungs- (und Anruf)-Metadaten umfassen Folgendes:

- Start- und Endzeit der Besprechung und Dauer
- Teilnahme an und Verlassen von Besprechungen für jeden Teilnehmer
- VOIP-Joins/-Anrufe
- Anonyme Teilnahmen
- Verbundbenutzerbeitritte
- Gastbenutzer tritt bei

Hier ist ein Beispiel für eine Chatunterhaltung zwischen Teilnehmern während einer Besprechung.

![Unterhaltung zwischen Teilnehmern in Teams.](media/MeetingIMConversations.png)

[!div class="mx-imgBorder"]

Hier ist ein Beispiel für die Konformitätskopie derselben Chatunterhaltung, die in einem eDiscovery-Tool angezeigt wird.

![Unterhaltung zwischen Teilnehmern in eDiscovery-Suchergebnissen.](media/MeetingImConversation2.png)

Hier ist ein Beispiel für die Besprechungsmetadaten.

  > [!div class="mx-imgBorder"]
  > ![Die Besprechungsmetadaten aus der Compliancekopie.](media/conversationOption3.png)

Weitere Informationen zum Durchführen einer eDiscovery-Untersuchung finden [Sie unter "Erste Schritte mit eDiscovery (Standard)](/microsoft-365/compliance/get-started-core-ediscovery)".

Microsoft Teams-Daten werden als Chatnachrichten oder Unterhaltungen in der Excel eDiscovery-Exportausgabe angezeigt. Sie können die `.pst` Datei in Outlook öffnen, um diese Nachrichten anzuzeigen, nachdem Sie sie exportiert haben.

Beim Anzeigen der PST-Datei für das Team befinden sich alle Unterhaltungen im Ordner "Teamchat" unter "Aufgezeichnete Unterhaltungen". Der Titel der Nachricht enthält den Teamnamen und den Kanalnamen. Die folgende Abbildung zeigt z. B. eine Nachricht von Bob, der den Project 7-Standardkanal des Manufacturing Specs-Teams angezeigt hat.

![Screenshot eines Teamchatordners im Postfach eines Benutzers in Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Private Chats im Postfach eines Benutzers werden im Ordner "Teamchat" unter "Aufgezeichnete Unterhaltungen" gespeichert.

## <a name="ediscovery-of-private-and-shared-channels"></a>eDiscovery privater und freigegebener Kanäle

Compliancekopien von Nachrichten in privaten und freigegebenen Kanälen werden je nach Kanaltyp an verschiedene Postfächer gesendet. Dies bedeutet, dass Sie unterschiedliche Postfachspeicherorte basierend auf dem Kanaltyp durchsuchen müssen, in dem ein Benutzer Mitglied ist.

- **Private Kanäle**. Compliancekopien werden an das Postfach aller Mitglieder des privaten Kanals gesendet. Dies bedeutet, dass Sie das Benutzerpostfach durchsuchen müssen, wenn Sie nach Inhalten in Nachrichten in privaten Kanälen suchen.

- **Freigegebene Kanäle**. Compliancekopien werden an ein Systempostfach gesendet, das dem übergeordneten Team zugeordnet ist. Da Teams keine eDiscovery-Suche eines einzelnen Systempostfachs für einen freigegebenen Kanal unterstützt, müssen Sie das Postfach nach dem übergeordneten Team durchsuchen (indem Sie den Namen des Teampostfachs auswählen), wenn Sie in freigegebenen Kanälen nach Nachrichteninhalten suchen.

Jeder private und freigegebene Kanal verfügt über eine eigene SharePoint-Website, die von der übergeordneten Teamwebsite getrennt ist. Das bedeutet, dass Dateien in privaten und freigegebenen Kanälen auf einer eigenen Website gespeichert und unabhängig vom übergeordneten Team verwaltet werden. Dies bedeutet, dass Sie die bestimmte Website identifizieren und durchsuchen müssen, die einem Kanal zugeordnet ist, wenn Sie nach Inhalten in Dateien und Kanalnachrichtenanlagen suchen.

Verwenden Sie die folgenden Abschnitte, um den privaten oder freigegebenen Kanal zu identifizieren, der in Ihre eDiscovery-Suche einbezogen werden soll.

### <a name="identifying-the-members-of-a-private-channel"></a>Identifizieren der Mitglieder eines privaten Kanals

Verwenden Sie das Verfahren in diesem Abschnitt, um Mitglieder eines privaten Kanals zu identifizieren, damit Sie eDiscovery-Tools verwenden können, um das Postfach des Mitglieds nach Inhalten in Nachrichten in privaten Kanälen zu durchsuchen.

Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie die [neueste Version des Teams PowerShell-Moduls](teams-powershell-overview.md) installiert haben.

1. Führen Sie den folgenden Befehl aus, um die Gruppen-ID des Teams abzurufen, das die freigegebenen Kanäle enthält, die Sie durchsuchen möchten.

   ```powershell
   Get-Team -DisplayName <display name of the the parent team>
   ```

   > [!TIP]
   > Führen Sie das **Cmdlet "Get-Team** " ohne Parameter aus, um eine Liste aller Teams in Ihrer Organisation anzuzeigen. Die Liste enthält die Gruppen-ID und den DisplayName für jedes Team.

2. Führen Sie den folgenden Befehl aus, um eine Liste der privaten Kanäle im übergeordneten Team abzurufen. Verwenden Sie die Gruppen-ID für das Team, das Sie in Schritt 1 erhalten haben.

   ```PowerShell
    Get-TeamChannel -GroupId <parent team GroupId> -MembershipType Private
   ```

3. Führen Sie den folgenden Befehl aus, um eine Liste der Besitzer und Mitglieder eines privaten Kanals abzurufen.

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. Schließen Sie die Postfächer von Besitzern und Mitgliedern eines privaten Kanals als Teil Ihrer [eDiscovery-Suchabfrage in eDiscovery (Standard)](/microsoft-365/compliance/search-for-content-in-core-ediscovery) oder beim [Identifizieren und Sammeln von Verwahrerinhalten in eDiscovery (Premium)](/microsoft-365/compliance/add-custodians-to-case) ein.

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>Identifizieren der SharePoint-Website für private und freigegebene Kanäle

Wie zuvor erläutert, werden Dateien, die in privaten und freigegebenen Kanälen (und an Kanalnachrichten angefügte Dateien) freigegeben wurden, in der Websitesammlung gespeichert, die dem Kanal zugeordnet ist. Verwenden Sie das Verfahren in diesem Abschnitt, um die URL für die Website zu identifizieren, die einem bestimmten privaten oder freigegebenen Kanal zugeordnet ist. Anschließend können Sie eDiscovery-Tools verwenden, um nach Inhalten auf der Website zu suchen.

Bevor Sie diese Schritte ausführen, [installieren Sie die SharePoint Online-Verwaltungsshell, und stellen Sie eine Verbindung mit SharePoint Online her](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

1. Führen Sie optional Folgendes aus, um eine Liste aller SharePoint-Websitesammlungen abzurufen, die freigegebenen Kanälen im übergeordneten Team zugeordnet sind.

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > Die Benennungskonvention der URL für eine Website, die privaten und freigegebenen Kanälen zugeordnet ist, lautet `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]`. Beispielsweise lautet `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration`die URL für den freigegebenen Kanal mit dem Namen "Partnerzusammenarbeit", der sich im übergeordneten Team "Technikerteam" in der Contoso-Organisation befindet.

2. Führen Sie die folgenden PowerShell-Befehle aus, um die URL für alle SharePoint-Websites anzuzeigen, die den privaten und freigegebenen Kanälen in Ihrer Organisation zugeordnet sind. Die Ausgabe des Skripts enthält auch die Gruppen-ID des übergeordneten Teams, die Sie zum Ausführen der Befehle in Schritt 3 benötigen.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > SharePoint-Websites für private Kanäle, die vor dem 28. Juni 2021 erstellt wurden, verwenden den Wert `"TEAMCHANNEL#0"` für die benutzerdefinierte Vorlagen-ID. Um private Kanäle anzuzeigen, die nach diesem Datum erstellt wurden, verwenden Sie den Wert `"TEAMCHANNEL#1"` , wenn Sie die vorherigen beiden Skripts ausführen. Freigegebene Kanäle verwenden nur den Wert von `"TEAMCHANNEL#1"`.

3. Führen Sie für jedes übergeordnete Team die folgenden PowerShell-Befehle aus, um die privaten und freigegebenen Kanalwebsites zu identifizieren, wobei `$groupID` sich die Gruppen-ID des übergeordneten Teams befindet.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. Schließen Sie die Website, die einem privaten oder freigegebenen Kanal zugeordnet ist, als Teil Ihrer [eDiscovery-Suchabfrage in eDiscovery (Standard)](/microsoft-365/compliance/search-for-content-in-core-ediscovery) oder beim [Identifizieren und Sammeln von Verwahrerinhalten in eDiscovery (Premium)](/microsoft-365/compliance/add-custodians-to-case) ein.

## <a name="search-for-content-for-guest-users"></a>Suchen nach Inhalten für Gastbenutzer

Sie können eDiscovery-Tools verwenden, um nach Teams-Inhalten im Zusammenhang mit Gastbenutzern in Ihrer Organisation zu suchen. Teams-Chatinhalte, die einem Gastbenutzer zugeordnet sind, bleiben an einem cloudbasierten Speicherort erhalten und können mithilfe von eDiscovery gesucht werden. Dazu gehört die Suche nach Inhalten in 1:1- und 1:N-Chatunterhaltungen, in denen ein Gastbenutzer ein Teilnehmer mit anderen Benutzern in Ihrer Organisation ist. Sie können auch nach Nachrichten in privaten Kanälen suchen, in denen ein Gastbenutzer ein Teilnehmer ist, und in *Gastchatunterhaltungen* nach Inhalten suchen, bei denen die einzigen Teilnehmer Gastbenutzer sind.

So suchen Sie nach Inhalten für Gastbenutzer:

1. Stellen Sie eine Verbindung mit Azure AD PowerShell her. Anweisungen hierzu finden Sie im Abschnitt "Verbinden mit dem Azure Active Directory PowerShell" unter ["Herstellen einer Verbindung mit Microsoft 365 mit PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)". Stellen Sie sicher, dass Sie Schritt 1 und Schritt 2 im vorherigen Artikel ausführen.

2. Nachdem Sie die Verbindung mit Azure AD PowerShell erfolgreich hergestellt haben, führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen (USER Principal Name, UPN) für alle Gastbenutzer in Ihrer Organisation anzuzeigen. Sie müssen den UPN des Gastbenutzers verwenden, wenn Sie die Suche in Schritt 4 erstellen.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Anstatt eine Liste der Benutzerprinzipalnamen auf dem Computerbildschirm anzuzeigen, können Sie die Ausgabe des Befehls in eine Textdatei umleiten. Sie können dies tun, indem Sie den vorherigen Befehl anfügen `> filename.txt` . Die Textdatei mit den Benutzerprinzipalnamen wird im aktuellen Ordner gespeichert.

3. Stellen Sie in einem anderen Windows PowerShell Fenster eine Verbindung mit Security & Compliance Center PowerShell her. Anweisungen finden [Sie unter Herstellen einer Verbindung mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell). Sie können eine Verbindung mit oder ohne mehrstufige Authentifizierung herstellen.

4. Erstellen Sie eine Inhaltssuche, die nach allen Inhalten (z. B. Chatnachrichten und E-Mail-Nachrichten) sucht, in denen der angegebene Gastbenutzer ein Teilnehmer war, indem Sie den folgenden Befehl ausführen.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Um beispielsweise nach Inhalten zu suchen, die der Gastbenutzerin Sara Davis zugeordnet sind, führen Sie den folgenden Befehl aus.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Weitere Informationen zur Verwendung von PowerShell zum Erstellen von Inhaltssuchen finden Sie unter [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).

5. Führen Sie den folgenden Befehl aus, um die Inhaltssuche zu starten, die Sie in Schritt 4 erstellt haben:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie dann auf **"Alle** > **Inhaltssuche anzeigen"**.

7. Wählen Sie in der Liste der Suchvorgänge die Suche aus, die Sie in Schritt 4 erstellt haben, um die Flyoutseite anzuzeigen.

8. Auf der Flyoutseite können Sie folgende Aktionen ausführen:

   - Klicken Sie auf **"Ergebnisse anzeigen** ", um die Suchergebnisse anzuzeigen und eine Vorschau des Inhalts anzuzeigen.

   - Klicken Sie neben dem **Abfragefeld** auf **"Bearbeiten** ", um die Suche zu bearbeiten, und führen Sie die Suche erneut aus. Sie können z. B. eine Suchabfrage hinzufügen, um die Ergebnisse einzugrenzen.

   - Klicken Sie auf **"Ergebnisse exportieren** ", um die Suchergebnisse zu exportieren und herunterzuladen.

## <a name="search-for-card-content"></a>Nach Karteninhalten suchen

Karteninhalte, die von Apps in Teams-Kanälen, 1:1-Chats und 1xN-Chats generiert werden, werden in Postfächern gespeichert und können durchsucht werden. Eine *Karte* ist ein UI-Container für kurze Inhalte. Karten können mehrere Eigenschaften und Anlagen aufweisen und Schaltflächen enthalten, die Kartenaktionen auslösen können. Weitere Informationen finden Sie unter [Karten](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Wie andere Teams-Inhalte basiert der Speicherort von Karteninhalten darauf, wo die Karte verwendet wurde. Inhalte für Karten, die in einem Teams-Kanal verwendet werden, werden im Teams-Gruppenpostfach gespeichert. Karteninhalte für 1:1- und 1xN-Chats werden in den Postfächern der Chatteilnehmer gespeichert.

Um nach Karteninhalten zu suchen, können Sie die `kind:microsoftteams` `itemclass:IPM.SkypeTeams.Message` Oder Suchbedingungen verwenden. Beim Überprüfen von Suchergebnissen weist der von Bots in einem Teams-Kanal generierte Karteninhalt die E-Mail-Eigenschaft **"Absender/Autor** " auf, `<appname>@teams.microsoft.com`wobei `appname` der Name der App, die den Karteninhalt generiert hat, angegeben ist. Wenn Karteninhalte von einem Benutzer generiert wurden, identifiziert der Wert von **Absender/Autor** den Benutzer.

Beim Anzeigen von Karteninhalten in Inhaltssuchergebnissen wird der Inhalt als Anlage zur Nachricht angezeigt. Der Name der Anlage ist `appname.html`dabei `appname` der Name der App, die den Karteninhalt generiert hat. Die folgenden Screenshots zeigen, wie Karteninhalte (für eine App namens Asana) in Teams und in den Ergebnissen einer Suche angezeigt werden.

### <a name="card-content-in-teams"></a>Karteninhalte in Teams

![Karteninhalt in Teams-Kanalnachricht.](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>Karteninhalt in Suchergebnissen

![Der gleiche Karteninhalt in den Ergebnissen einer Inhaltssuche.](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Um Bilder aus Karteninhalten zu diesem Zeitpunkt in Suchergebnissen anzuzeigen (z. B. die Häkchen im vorherigen Screenshot), müssen Sie auf einer anderen Registerkarte in derselben Browsersitzung bei Teams (at <https://teams.microsoft.com>) angemeldet sein, die Sie zum Anzeigen der Suchergebnisse verwenden. Andernfalls werden Bildplatzhalter angezeigt.

## <a name="ediscovery-in-federated-and-non-federated-environments"></a>eDiscovery in Verbund- und Nicht-Verbundumgebungen

Administratoren können eDiscovery verwenden, um nach Inhalten in Chatnachrichten in einer Teams-Besprechung in Verbundumgebungen (als *externer Zugriff* bezeichnet) und Nicht-Verbundumgebungen (als *Gastzugriff* bezeichnet) basierend auf den folgenden Einschränkungen zu suchen:

- **Partnerverbund**: In einer Teams-Besprechung mit Benutzern aus Ihrer Organisation und Benutzern aus einer externen Organisation (die externen Zugriff in Ihrer Organisation haben), können Administratoren in beiden Organisationen nach Inhalten in Chatnachrichten aus der Besprechung suchen.

- Nicht verbunden: In einer Teams-Besprechung mit Benutzern aus Ihrer Organisation und Gastbenutzern können nur Administratoren in der Organisation, die die **Teams-Besprechung** hosten, nach Inhalten in Chatnachrichten aus der Besprechung suchen.

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft 365 eDiscovery-Lösungen](/microsoft-365/compliance/ediscovery)
- [Erste Schritte mit eDiscovery (Standard)](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams-Workflow in eDiscovery (Premium)](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

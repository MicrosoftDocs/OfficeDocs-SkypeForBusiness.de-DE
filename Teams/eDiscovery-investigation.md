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
description: Erfahren Sie, wie Sie vorgehen müssen, wenn Sie eDiscovery ausführen müssen, beispielsweise wenn Sie alle elektronisch gespeicherten Informationen für gerichtliche Verfahren übermitteln müssen.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 53f3f1f3d8146b06b69a70dbbf7c00bdb979c43c
ms.sourcegitcommit: b6aeaa3d98c29bdc120db8ccfcb7ff2c11d246af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570824"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Durchführen einer eDiscovery-Untersuchung von Inhalt in Microsoft Teams

Große Unternehmen sind häufig hohen strafrechtlichen Verfahren ausgesetzt, die die Übermittlung aller elektronisch gespeicherten Informationen (ESI) fordern. Microsoft Teams-Inhalte können während eDiscovery-Untersuchungen durchsucht und verwendet werden.

## <a name="overview"></a>Übersicht

Alle Microsoft Teams 1:1-oder Gruppen-Chats werden in den Postfächern der jeweiligen Benutzer erfasst. Alle Standardkanal Nachrichten werden in das Gruppenpostfach, das das Team darstellt, in Journalen erfasst. Dateien, die in Standardkanälen hochgeladen werden, werden von der eDiscovery-Funktion für SharePoint Online und OneDrive for Business abgedeckt.

eDiscovery von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [eDiscovery privater Kanäle](#ediscovery-of-private-channels).

Nicht alle Teams-Inhalte sind eDiscoverable. In der folgenden Tabelle sind die Inhaltstypen aufgeführt, die mithilfe von eDiscovery gefunden werden können.

| Inhaltstyp | eDiscoverable | Hinweise |
|:--- | --- |:--- |
| Teams-Chatnachrichten | Ja |  |
| Private Kanal Nachrichten | Ja | |
| Name des Kanals | Nein | |
| Chat Unterhaltungen von Besprechungen | Ja | |
| Besprechungs Metadaten<sup>1</sup> | Ja |  |
| Bearbeitete Nachrichten | Ja | Wenn der Benutzer in Wartestellung ist, bleiben frühere Versionen bearbeiteter Nachrichten erhalten. |
| Emojis, GIFs, Aufkleber | Ja | |
| Code Ausschnitte | Nein | |
| Chat-Links | Ja | |
| Reaktionen (likes, Hearts usw.) | Nein | |
| Inline Bilder | Ja | |
| Tabellen | Ja | |
| Betreff | Ja | |
| Anführungszeichen | Ja | Zitierte Inhalte sind durchsuchbar. Suchergebnisse deuten jedoch nicht darauf hin, dass der Inhalt zitiert wurde. |
| Audioaufzeichnungen | Nein | |

<sup>1</sup> zu den Besprechungs Metadaten gehören die folgenden:

- Start-und Endzeit der Besprechung oder des Anrufs und Dauer
- Anruf-/Besprechungsteilnahme und Abwesenheits Ereignisse für jeden Teilnehmer
- VoIP-Join/-Anrufe
- Anonyme Verknüpfung
- Föderationsbenutzer-Join
- Gastbenutzer Beitritt

Das Bild zeigt ein Beispiel für die Metadaten.

> [!div class="mx-imgBorder"]
> ![Das Bild ist der CVR Records-Besprechungs Metadaten.](media/conversationOption3.png)

Im folgenden finden Sie ein Beispiel für Chat Unterhaltungen zwischen Teilnehmern während der Besprechung.

![Konversation zwischen Teilnehmern in Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Unterhaltung zwischen Teilnehmern in eDiscovery-Suchergebnissen](media/MeetingImConversation2.png)

Wenn Sie eine eDiscovery-Untersuchung mit Microsoft Teams-Inhalten durchführen möchten, lesen Sie Schritt 1 unter [Erste Schritte mit der zentralen eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery).

Microsoft Teams-Daten werden als Chatnachrichten oder Unterhaltungen in der Excel-eDiscovery-Exportausgabe angezeigt. Sie können die `.pst` Datei in Outlook öffnen, um diese Nachrichten nach dem Export anzuzeigen.

Wenn Sie die PST-Datei für das Team anzeigen, werden alle Unterhaltungen im Teamchat-Ordner unter Konversationsprotokoll gespeichert. Der Titel der Nachricht enthält den Namen des Teams und den Kanalnamen. Die folgende Abbildung zeigt beispielsweise eine Nachricht von Bob, die dem Project 7-Standardkanal des Teams "Manufacturing Specs" eine Nachricht gesendet hat.

![Screenshot eines Team-Chat-Ordners im Postfach eines Benutzers in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Private Chats im Postfach eines Benutzers werden im Ordner "Team-Chat" unter "Konversationsprotokoll" gespeichert.

## <a name="ediscovery-of-private-channels"></a>eDiscovery privater Kanäle

Einträge für Nachrichten, die in einem privaten Kanal gesendet werden, werden an das Postfach aller Mitglieder des privaten Kanals und nicht an ein Gruppenpostfach übermittelt. Die Titel der Einträge sind so formatiert, dass sie angeben, von welchem privaten Kanal sie gesendet wurden.

Da jeder private Kanal über eine eigene SharePoint-Websitesammlung verfügt, die von der übergeordneten Teamwebsite getrennt ist, werden Dateien in einem privaten Kanal unabhängig vom übergeordneten Team verwaltet.

Teams unterstützt keine eDiscovery-Suche in einem einzelnen Kanal innerhalb eines Teams, sodass das gesamte Team durchsucht werden muss. Wenn Sie eine eDiscovery-Suche nach Inhalten in einem privaten Kanal durchführen möchten, suchen Sie im Team, in der Websitesammlung, die dem privaten Kanal zugeordnet ist (um Dateien einzubeziehen), und Postfächern privater Kanalmitglieder (zum Einbeziehen von Nachrichten).

Führen Sie die folgenden Schritte aus, um Dateien und Nachrichten in einem privaten Kanal zu identifizieren, die Sie in Ihre eDiscovery-Suche einbeziehen möchten.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Einbeziehen privater Kanaldateien in eine eDiscovery-Suche

Bevor Sie diese Schritte ausführen, installieren Sie die [SharePoint Online-Verwaltungsshell, und stellen Sie eine Verbindung mit SharePoint Online her](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

1. Führen Sie die folgenden Schritte aus, um eine Liste aller SharePoint-Websitesammlungen abzurufen, die privaten Kanälen im Team zugeordnet sind.

    ```PowerShell
    Get-SPOSite
    ```

2. Führen Sie das folgende PowerShell-Skript aus, um eine Liste aller URLs einer SharePoint-Websitesammlung abzurufen, die privaten Kanälen im Team zugeordnet sind, und die Gruppen-ID der übergeordneten Gruppe.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Führen Sie für jede Team-oder Gruppen-ID das folgende PowerShell-Skript aus, um alle relevanten privaten Kanal Websites zu identifizieren, wobei $GroupID die Gruppen-ID des Teams ist.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Einbeziehen privater Kanal Nachrichten in eine eDiscovery-Suche

Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass die [neueste Version des Teams PowerShell-Moduls](teams-powershell-overview.md) installiert ist.

1. Führen Sie die folgenden Schritte aus, um eine Liste privater Kanäle im Team abzurufen.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Führen Sie die folgenden Schritte aus, um eine Liste privater Kanalmitglieder abzurufen.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Fügen Sie die Postfächer aller Mitglieder aus jedem privaten Kanal im Team als Teil ihrer eDiscovery-Suchabfrage ein.

## <a name="advanced-ediscovery"></a>Advanced eDiscovery

Einige Microsoft Teams-Inhalte können auch mithilfe des [erweiterten eDiscovery-Workflows](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)durchsucht und aufbewahrt werden. EDiscovery bietet eine Reihe von Such-, halte-und Exportfunktionen, und erweiterte eDiscovery bietet Compliance-Administratoren weitere Tools, um Datenquellen zu identifizieren und deren Inhalt zu analysieren.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Erweiterter eDiscovery-Depotbank-Workflow für Team Inhalte

Depotbanks können Mitglied in verschiedenen Teams sein. Sie können die für diese Depotbank relevanten Team Inhalte erfassen. Hintergrundinformationen und Anweisungen zum Depotbank-Workflow finden Sie unter [Advanced eDiscovery-Workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).

Nachdem Sie eine Depotbank hinzugefügt haben, klicken Sie auf die Schaltfläche **weiter** und dann auf die Schaltfläche **Hinzufügen** . Daraufhin wird ein Fenster eingeblendet, in dem Sie aufgefordert werden, weitere Speicherorte auszuwählen, auf denen alle Mitgliedschaften des Depotbank-Mitglieds und die entsprechenden SharePoint-Websitespeicher Orte für Ihre Daten angezeigt werden. Aus all diesen Datenquellen und Teams können Sie den Inhalt auswählen, den Sie für eDiscovery verwenden möchten, und dann diesen Benutzer und alle Datenquellen, die Sie in der Warteschleife identifiziert haben, platzieren.

Sie können auswählen, ob Sie den Exchange-Inhalt, dessen OneDrive-Inhalt oder beides einbeziehen möchten. Exchange-Inhalt enthält alle Anwendungsinhalte in den Postfächern des Benutzers, beispielsweise die e-Mail-Adresse, die Team Inhalte, die in Ihrem Postfach gespeichert sind usw. Der OneDrive-Inhalt enthält nicht nur die Inhalte des Benutzers, sondern auch alle in OneDrive gespeicherten Team Inhalte, wie etwa 1:1-Chats, 1: N-Chats und in Chats freigegebene Dateien.

Sie haben auch die Möglichkeit, ein beliebiges Team zu assoziieren, dem die Depotbank angehört, sodass Kanal-Chat-Nachrichten und-Dateien, auf die die Depotbank zugreifen kann, enthalten sind. Darüber hinaus kann jedes andere Team einer Depotbank zugeordnet werden. Weitere Informationen finden Sie unter [Hinzufügen von depotbanks zu einem erweiterten eDiscovery-Fall](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).

> [!NOTE]
> eDiscovery von Nachrichten und Dateien in [privaten Kanälen](private-channels.md) funktioniert anders als in Standardkanälen. Weitere Informationen finden Sie unter [eDiscovery privater Kanäle](#ediscovery-of-private-channels).

### <a name="placing-a-data-source-on-hold"></a>Speichern einer Datenquelle

Wenn kein bestimmter Benutzer als Depotbank festgelegt werden kann, können Sie eine gesamte Datenquelle in Wartestellung setzen. Weitere Informationen zu Haltebereichen finden Sie unter [Verwalten von Aufbewahrungen in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).

Beim Erstellen eines haltebereichs für Teams-Inhalte können Sie alle Speicherorte auswählen, die Sie in ihren Haltebereich einbeziehen möchten. Auch wenn Benutzer Inhalte löschen oder ändern, behält der Haltebereich Kopien aller vorherigen Versionen dieses Inhalts bei.

Sie können auch eine optionale Abfrage verwenden, um die Bedingungen für den Haltebereich auf Grundlage von Stichwörtern, Datumsbereich, Autor und vielen anderen Kriterien festzulegen. Wenn Sie keine Stichwörter angeben, unterliegt alles aus dieser Datenquelle dem Haltebereich.

### <a name="advanced-ediscovery-searches"></a>Erweiterte eDiscovery-Suchvorgänge

Teams-Inhalte können auch durchsucht werden. Weitere Informationen zu Suchvorgängen finden Sie unter [Sammeln von Daten für einen Fall in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery). Eine Suche gibt eine ganze Konversation zurück, wenn auch nur eine Nachricht mit der Suchabfrage übereinstimmt.

Wenn Sie eine Suchabfrage erstellen, können Sie depotbanks auswählen, damit alle Quellen, die Sie bereits ausgewählt haben, durchsucht werden. Sie können auch nicht-Freiheitsentzug-Quellen wie eine Teamwebsite durchsuchen, die keinem Benutzer zugeordnet ist. Optional sind auch Abfragen verfügbar, mit denen Sie die Suche innerhalb des Teams-Inhalts einschränken können.

Nachdem Sie eine Suche erstellt und markiert haben, wird ein Fenster mit zusätzlichen Details und Aktionen angezeigt, die Sie für die ausgewählte Suche übernehmen können. Wenn Sie auf die Schaltfläche **Statistik** klicken, können Sie Statistiken zu Ihrer Suche anzeigen, einschließlich der Untergliederungen entsprechend den Standorttypen, der ursprünglichen Quelle für den Inhalt und der Frage, ob sich der Inhalt in einem Gruppenpostfach, dem einzelnen Benutzerpostfach oder einer SharePoint-Website befindet. So können Sie eine Aufschlüsselung der Quellen sehen, die zu Ihren Suchergebnissen beitragen. Es steht auch eine Ansicht **Abfragen** zur Verfügung, damit Sie sehen können, welche einzelnen Stichwörter zu ihren Ergebnissen beitragen.

Nachdem Sie die Suche abgeschlossen haben, können Sie auf die Schaltfläche **zu überprüfende Ergebnisse hinzufügen** klicken und Sie einem Überprüfungs Satz hinzufügen. Weitere Informationen zu Überprüfungs Sätzen finden Sie weiter unten in diesem Artikel unter Verwalten von Überprüfungs [Sätzen in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) -und [Review Sets-Workflow](#review-sets-workflow) .

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Normale Überprüfungs Sätze und Konversations Überprüfungs Sätze

Beim Hinzufügen einer Suche zu einem Überprüfungs Satz können Sie aus einem normalen Überprüfungs Satz oder einem Konversations Überprüfungs Satz auswählen.

Ein normaler Überprüfungs Satz ähnelt einem Export; Sie stellt die einzelnen `.msg` Dateien für den Team Inhalt bereit und zeigt den Inhalt in einer einfachen Ansicht an. In der Regel verwenden Sie einen normalen Überprüfungs Satz, wenn Sie beabsichtigen, andere Software Tools zu verwenden, um die Dateien später erneut zu verarbeiten.

Eine Konversations Überprüfungsgruppe bietet eine intuitivere Threadansicht der Unterhaltungen. Verwandte Nachrichten werden in der richtigen Reihenfolge zusammen angezeigt.

> [!div class="mx-imgBorder"]
> ![Screenshot der Konversations Überprüfungsgruppe](media/conversationOptions2.png)

Funktionen wie "Bearbeiten" stehen in beiden Arten von Überprüfungs Sätzen zur Verfügung. Weitere Informationen zu Überprüfungs Sätzen finden Sie unter [Überprüfen von Unterhaltungen in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).

#### <a name="collection-options"></a>Sammlungsoptionen

Wenn Sie zu einem Überprüfungs Satz hinzugefügt werden, stehen verschiedene Optionen als Kontrollkästchen unter dem Abschnitt **Sammlungsoptionen** des Fensters zur Verfügung, einschließlich **Konversations Abrufoptionen** und **Teams-Konversationen**. Wenn Sie diese Optionen aktivieren, werden alle einzelnen Teams-Nachrichten, die Teil des Überprüfungs Satzes sind, auch mit zusätzlichen Nachrichten angezeigt, die Sie für den Kontext umgeben. Wenn Ihre Abfrage beispielsweise spezifisch ist und nur eine Nachricht als Ergebnis zurückgegeben wird, gibt die Aktivierung dieser Optionen auch mehrere Nachrichten zurück, die zur und nach der Nachricht führen, die mit der Abfrage übereinstimmte.

Viele logische Kriterien werden verwendet, um zu ermitteln, ob zusätzliche Nachrichten Kontext für Nachrichten bereitstellen, die Ihrer Abfrage entsprechen. Für Teams-Inhalte können Sie beispielsweisedurch Aktivieren dieser Optionen die übergeordnete Nachricht und alle untergeordneten Nachrichten abrufen, weil die Nachrichten mit einem Thread versendet werden.

Nachrichtenzeitstempel werden ebenfalls überprüft. Wenn eine Nachricht Ihrer Abfrage entspricht, werden benachbarte Nachrichten, die ihr innerhalb einer Spanne von 4 Stunden vorangestellt sind oder innerhalb einer Spanne von 4 Stunden folgen, als Teil der Konversation betrachtet und auch in die Ergebnisse einbezogen.

Wenn Sie sicher sein müssen, welche kontextbezogenen Nachrichten mit Übereinstimmungen mit Ihrer Suchabfrage zurückgegeben werden, müssen Sie diese Optionen nicht verwenden. Sie können entweder alle Inhalte sammeln, oder Sie können den Datumsbereich der Suche erweitern, damit mehr Nachrichten als Ergebnis Ihrer Abfrage zurückgegeben werden.

### <a name="review-sets-workflow"></a>Überprüfungs Satz-Workflow

Sie können vorhandene Überprüfungs Sätze anzeigen oder neue erstellen, indem Sie auf die Registerkarte **Überprüfungs Sätze** klicken. Weitere Informationen zu Überprüfungs Sätzen finden Sie unter [Verwalten von Überprüfungs Sätzen in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).

Zusätzlich zu Dokumenten können Sie Ihrem Überprüfungs Satz e-Mails, Team Nachrichten, Jammer Meldungen und andere Inhalte hinzufügen. In einem Überprüfungs Satz können Sie auch viele der Vorgänge ausführen, die Sie in anderen Kontexten ausführen können, beispielsweisedurch suchen von Inhalten und Erstellen benutzerdefinierter Abfragen. Diese Vorgänge gelten nur für Elemente, die dem Überprüfungs Satz hinzugefügt wurden.

Die Schaltfläche " **Überprüfungs Sätze verwalten** " bietet zusätzliche Optionen wie Analyse, Zusammenfassungsberichte, wie viele Auslastungs Sätze hinzugefügt wurden usw.

Wenn Sie auf Visualisierungen und Diagramme Ihrer Daten zugreifen möchten **Individual results** , klicken Sie \> oben rechts auf **Suchprofil Ansicht** für einzelne Ergebnisse. Sie können auf Keile in diesen Diagrammen klicken, um interaktiv den Inhaltstyp auszuwählen, den Sie Abfragen möchten. So können Sie beispielsweise auswählen, dass nur Team Inhalte abgefragt werden sollen. Sie können diese Abfragen auch so speichern, wie Sie Abfragen speichern, die Sie manuell schreiben.

#### <a name="summary-view-text-view-and-annotate-view"></a>Zusammenfassungsansicht, Textansicht und Beschriftungsansicht

Wenn Sie im Überprüfungs Satz auf eine Teams-Unterhaltung klicken, wird die **Zusammenfassungsansicht** angezeigt, in der eine ganze Teams-Konversation als Liste von Nachrichten angezeigt wird, mit denen Sie einzeln interagieren können. Klicken Sie auf den Abwärtspfeil rechts neben einer Nachricht, um ein Kontextmenü anzuzeigen, das es Ihnen ermöglicht, Nachrichtendetails anzuzeigen oder die einzelne Datei herunterzuladen `.msg` . Wenn Sie auf Nachrichtendetails klicken, wird eine Zusammenfassung der Metadaten oder der vollständigen Metadaten der Nachricht angezeigt.

Wenn Sie eine PDF-Datei herunterladen möchten, klicken Sie oben rechts in der Zusammenfassungsansicht auf die Schaltfläche herunterladen.

Klicken Sie auf die Registerkarte **Text Ansicht** , um eine nur-Text-Ansicht des extrahierten Texts der Teams-Unterhaltung anzuzeigen. Dieser nur-Text-Inhalt ist für den Export geeignet und Sie können mit anderen Software Tools problemlos damit arbeiten.

Klicken Sie auf die Registerkarte **Ansicht kommentieren** , um auf die Anmerkungs Features zuzugreifen. Auf dieser Registerkarte wird der Inhalt in einem Format angezeigt, das einer Team Unterhaltung ähnelt, es gibt aber auch zusätzliche Optionen für die Bearbeitung. Es gibt ein Bleistifttool, das Sie verwenden können, um Notizen zu machen, auf die Nachricht zu zeichnen oder feinkörniges kratzen zu tun. Es gibt auch ein **Bereich** -Tool, mit dem Sie ein Rechteck zeichnen können, das den Bereich schwärzt und als "redigiert" markiert.

Im folgenden finden Sie ein Beispiel für eine Datei, die für eine Multithread-Konversation zwischen Benutzern fungiert.

> [!div class="mx-imgBorder"]
> ![Screenshot von "redigierte Datei"](media/RedactedFileExample.png)

Am unteren Rand der Registerkarte " **Ansicht kommentieren** " befindet sich die Schaltfläche " **Dokumente markieren** ", auf der der Bereich "Tagging" angezeigt wird. In diesem Bereich können Sie eine Kategorie auf alle Nachrichten innerhalb der Teams-Unterhaltung anwenden. Sie können eine Unterhaltung als "reaktionsfähig" oder "nicht reagierend", "privilegiert" oder "nicht privilegiert" kennzeichnen, unabhängig davon, ob Sie "interessante Elemente" enthält, ob Sie im Export enthalten sein sollte und ob Sie weitere Überprüfung benötigen. Sie können auch andere anpassbare Tags verwalten und anwenden.

#### <a name="action-menu"></a>Menü "Aktion"

Im Fenster "Überprüfungs Sätze" können Sie den Inhalt exportieren, indem Sie auf " **Aktion** \> **exportieren**" klicken. Beim Exportieren stehen viele Optionen zur Verfügung.

Wenn Sie eine Datei exportieren möchten, die alle Metadaten für alle Teams-Nachrichten enthält, aktivieren Sie das Kontrollkästchen **Datei laden** . Wenn Sie alle auf den Inhalt angewendeten Tags in Ihre Datei einbeziehen möchten, aktivieren Sie das Kontrollkästchen **Markierungen** .

Verwenden Sie die Option **systemeigene Dateien** , um Dateien in ihrem systemeigenen Format zu exportieren. Sie können eine Unterhaltung als eine Datei oder alle einzelnen Chatnachrichten in eigenen separaten Dateien exportieren.

Mit der Option " **Textdateien** " können Sie nur-Text-Versionen von Inhalten speichern. Weitere Informationen dazu, wie Sie eine nur-Text-Ansicht von Teams-Unterhaltungen im Überprüfungs Satz erhalten, finden Sie unter [Zusammenfassungsansicht, Textansicht und Ansicht](#summary-view-text-view-and-annotate-view) oben mit Anmerkungen.

Wenn Sie den Inhalt, wie in der Ansicht " [Zusammenfassung", "Textansicht" und "kommentieren](#summary-view-text-view-and-annotate-view) " oben beschrieben, auf den Inhalt angewendet haben, können Sie die Option " **mit konvertierten PDF** -Dateien ersetzen" die nativen Dateien durch konvertierte Kopien in PDF ersetzen auswählen.

Sie können auswählen, ob Sie in einen von Microsoft bereitgestellten Azure BLOB-Speichercontainer exportieren möchten, oder Sie können einen eigenen Azure BLOB-Speichercontainer bereitstellen.

Wenn Sie den Exportvorgang beginnen möchten, klicken Sie auf die Schaltfläche **exportieren** . Weitere Informationen dazu, wie Sie auf den Azure BLOB-Speichercontainer zugreifen und die exportierten Inhalte herunterladen können, nachdem der Export abgeschlossen ist, finden Sie unter [Herunterladen von Exportaufträgen](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) .

> [!NOTE]
> Der Export kann eine längere Zeit dauern. Wenn Sie den Status des Exportvorgangs nachvollziehen möchten, beenden Sie die Registerkarte **Überprüfungs Sätze** , und klicken Sie auf die Registerkarte **Export** .

## <a name="related-topics"></a>Verwandte Themen

- [eDiscovery in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

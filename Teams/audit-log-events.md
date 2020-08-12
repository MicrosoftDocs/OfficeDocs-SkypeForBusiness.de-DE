---
title: Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anwara
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Microsoft Teams-Daten aus dem Überwachungsprotokoll abrufen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64b2e2f28b33a3f0518dbf4f2f07a4be3053d342
ms.sourcegitcommit: 3814db70796888f15ea47d7810e1621a92992870
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "46634611"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Das Überwachungsprotokoll kann Ihnen bei der Untersuchung bestimmter Aktivitäten in den Microsoft 365-Diensten helfen. Für Microsoft Teams sind hier einige der Aktivitäten, die überwacht werden:

- Teamerstellung
- Löschung von Teams
- Hinzufügen von Kanälen
- Ändern von Einstellungen

Eine vollständige Liste der zu überwachenden Teams-Aktivitäten finden Sie unter [Team](#teams-activities) Aktivitäten und [Schichten in den Teamaktivitäten (in der Vorschau)](#shifts-in-teams-activities).

> [!NOTE]
> Überwachungsereignisse von privaten Kanälen werden auch so protokolliert, wie Sie für Teams und Standardkanäle gelten.

## <a name="turn-on-auditing-in-teams"></a>Aktivieren der Überwachung in Microsoft Teams

Bevor Sie sich die Überwachungsdaten ansehen können, müssen Sie zuerst die Überwachung im [Security & Compliance Center](https://protection.office.com)aktivieren. Wenn Sie Hilfe beim Aktivieren der Überwachung benötigen, lesen Sie [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).

> [!IMPORTANT]
> Überwachungsdaten sind nur ab dem Zeitpunkt verfügbar, an dem Sie die Überwachung aktiviert haben.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Abrufen von Microsoft Teams-Daten aus dem Überwachungsprotokoll

1. Um Überwachungsprotokolle abzurufen, navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775). Wählen Sie unter **Suchen**die Option **Überwachungsprotokoll Suche**aus.
2. Verwenden Sie die Option **Suchen**, um nach den Aktivitäten, Datumswerten und Benutzern zu filtern, die Sie überwachen möchten.
3. Exportieren Sie die Ergebnisse zur weiteren Analyse nach Excel.

> [!IMPORTANT]
> Überwachungsdaten werden nur im Überwachungsprotokoll angezeigt, wenn die Überwachung aktiviert ist.

Die Zeitdauer, in der ein Überwachungsdatensatz aufbewahrt und im Überwachungsprotokoll durchsucht werden kann, hängt von Ihrem Microsoft 365-oder Office 365-Abonnement und insbesondere von der Art der Lizenz ab, die Benutzern zugewiesen ist. Weitere Informationen finden Sie in der [Dienstbeschreibung zum Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="tips-for-searching-the-audit-log"></a>Tipps zum Durchsuchen des Überwachungsprotokolls

Hier finden Sie Tipps zum Suchen nach Teams-Aktivitäten im Überwachungsprotokoll.

![Screenshot der Such Seite des Überwachungsprotokolls](media/audit-log-search-page.png)

- Sie können bestimmte Aktivitäten auswählen, nach denen Sie suchen möchten, indem Sie auf den Aktivitätsnamen klicken. Sie können aber auch nach allen Aktivitäten in einer Gruppe (beispielsweise **Datei-und Ordner Aktivitäten**) suchen, indem Sie auf den Gruppennamen klicken. Wenn eine Aktivität ausgewählt ist, können Sie darauf klicken, um die Auswahl abzubrechen. Sie können auch das Suchfeld verwenden, um die Aktivitäten anzuzeigen, die das eingegebene Schlüsselwort enthalten.<br>
    ![Screenshot der Überwachungsprotokoll Suche](media/audit-log-search.png)
- Zum Anzeigen von Ereignissen für Aktivitäten, die mit Cmdlets ausgeführt werden, wählen Sie **Ergebnisse für alle Aktivitäten anzeigen** in der Liste **Aktivitäten** aus. Wenn Sie den Namen des Vorgangs für diese Aktivitäten kennen, suchen Sie nach allen Aktivitäten, und Filtern Sie die Ergebnisse, indem Sie den Namen des Vorgangs in das Feld in der Spalte **Aktivität** eingeben. Weitere Informationen finden Sie unter [Schritt 3: Filtern der Suchergebnisse](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance?view=o365-worldwide#step-3-filter-the-search-results).
- Wenn Sie die aktuellen Suchkriterien löschen möchten, klicken Sie auf **Löschen**. Der Datumsbereich kehrt auf den Standardwert der letzten sieben Tage zurück. Sie können auch auf **Alle löschen klicken, um die Ergebnisse für alle Aktivitäten anzuzeigen** , um alle ausgewählten Aktivitäten abzubrechen.
- Wenn 5.000-Ergebnisse gefunden werden, können Sie wahrscheinlich davon ausgehen, dass mehr als 5.000-Ereignisse vorhanden sind, die die Suchkriterien erfüllt haben. Sie können die Suchkriterien verfeinern und die Suche erneut ausführen, um weniger Ergebnisse zurückzugeben, oder Sie können alle Suchergebnisse exportieren, indem Sie **Ergebnisse exportieren**,  >  **alle Ergebnisse herunterladen**auswählen.

Schauen Sie sich [dieses Video](https://www.youtube.com/embed/UBxaRySAxyE) zur Verwendung der Audioprotokoll-Suche an. Treten Sie Ansuman Acharya, einem Programmmanager für Teams, bei, da er veranschaulicht, wie eine Überwachungsprotokoll Suche nach Teams durchführen kann.

## <a name="use-cloud-app-security-to-set-activity-policies"></a>Verwenden der Cloud-App-Sicherheit zum Einrichten von Aktivitätsrichtlinien

Mithilfe der Sicherheitsintegration der [Microsoft Cloud-App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) können Sie [Aktivitätsrichtlinien](https://docs.microsoft.com/cloud-app-security/user-activity-policies) so einrichten, dass eine Vielzahl automatisierter Prozesse mithilfe der APIs des App-Anbieters erzwungen wird. Mit diesen Richtlinien können Sie bestimmte Aktivitäten, die von verschiedenen Benutzern durchgeführt werden, überwachen oder unerwartet höhere Raten einer bestimmten Art von Aktivität befolgen.

Nachdem Sie eine Richtlinie für die Aktivitätserkennung festgestellt haben, beginnt Sie mit dem Generieren von Benachrichtigungen. Benachrichtigungen werden nur für Aktivitäten generiert, die nach dem Erstellen der Richtlinie auftreten. Im folgenden finden Sie einige Beispielszenarien für die Verwendung von Aktivitätsrichtlinien in der Cloud-App-Sicherheit, um die Aktivitäten von Teams zu überwachen.

### <a name="external-user-scenario"></a>Szenario eines externen Benutzers

Ein Szenario, auf das Sie möglicherweise im geschäftlichen Bereich achten sollten, ist das Hinzufügen externer Benutzer zu ihrer Teamumgebung. Wenn externe Benutzer aktiviert sind, ist es ratsam, deren Anwesenheit zu überwachen.  Sie können die [Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) verwenden, um potenzielle Bedrohungen zu erkennen.

![Screenshot einer Liste von Ereignissen, die durch Massenlöschungen ausgelöst werden](media/TeamsExternalUserAddPolicy.png)

Der Screenshot dieser Richtlinie zum Überwachen des Hinzufügens externer Benutzer ermöglicht Ihnen, die Richtlinie zu benennen, den Schweregrad entsprechend Ihren geschäftlichen Anforderungen festzulegen, ihn als (in diesem Fall) eine einzelne Aktivität festzulegen und dann die Parameter festzulegen, die speziell nur das Hinzufügen nicht interner Benutzer überwachen und diese Aktivität auf Teams beschränken.

Die Ergebnisse dieser Richtlinie können im Aktivitätsprotokoll angezeigt werden:

![Screenshot einer Liste von Ereignissen, die durch Massenlöschungen ausgelöst werden](media/TeamsExternalUserList.png)

Hier können Sie die Übereinstimmungen mit der von Ihnen eingerichteten Richtlinie überprüfen und nach Bedarf Anpassungen vornehmen oder die Ergebnisse exportieren, um Sie anderweitig zu verwenden.

### <a name="mass-delete-scenario"></a>Massen Lösch Szenario

Wie bereits erwähnt, können Sie Lösch Szenarien überwachen. Es ist möglich, eine Richtlinie zu erstellen, die das Massenlöschen von Teams-Websites überwacht. In diesem Beispiel wird eine Warnungs basierte Richtlinie eingerichtet, um das Massenlöschen von Teams in einer Spanne von 30 Minuten zu erkennen.

![Screenshot der Seite "Richtlinie erstellen" mit der Einrichtung einer Richtlinie für die Löschung von Massen Teams](media/TeamsMassDeletePolicy.png)

Wie der Screenshot zeigt, können Sie für diese Richtlinie viele verschiedene Parameter festlegen, um die Löschungen von Teams zu überwachen, einschließlich Schweregrad, einzelne oder wiederholte Aktionen und Parameter, die dies auf Teams und das Löschen von Websites einschränken. Dies kann unabhängig von einer Vorlage erfolgen, oder es ist möglich, dass Sie je nach Ihren organisatorischen Anforderungen eine Vorlage erstellen, auf der diese Richtlinie basiert.

Nachdem Sie eine Richtlinie eingerichtet haben, die für Ihr Unternehmen funktionieren wird, können Sie die Ergebnisse im Aktivitätsprotokoll überprüfen, wenn Ereignisse ausgelöst werden:

![Screenshot einer Liste von Ereignissen, die durch Massenlöschungen ausgelöst werden](media/TeamsMassDeleteList.png)

Sie können nach unten auf die Richtlinie filtern, die Sie festgelegt haben, um die Ergebnisse dieser Richtlinie anzuzeigen. Wenn die Ergebnisse, die Sie im Aktivitätsprotokoll erhalten, nicht zufrieden stellend sind (vielleicht sehen Sie viele Ergebnisse oder gar nichts), kann dies Ihnen helfen, die Abfrage zu optimieren, damit Sie relevanter für das ist, was Sie benötigen.

### <a name="alert-and-governance-scenario"></a>Benachrichtigungs-und Governance-Szenario

Sie können Benachrichtigungen festlegen und e-Mails an Administratoren und andere Benutzer senden, wenn eine Aktivitätsrichtlinie ausgelöst wird. Sie können automatisierte Governance-Aktionen wie das Sperren eines Benutzers oder die automatische Anmeldung eines Benutzers einrichten. Dieses Beispiel zeigt, wie ein Benutzerkonto angehalten werden kann, wenn eine Aktivitätsrichtlinie ausgelöst wird, und bestimmt, dass ein Benutzer zwei oder mehr Teams in 30 Minuten gelöscht hat.

![Screenshot von Benachrichtigungs-und Governance-Aktionen für eine Aktivitätsrichtlinie](media/audit-log-governance.png)

## <a name="use-cloud-app-security-to-set-anomaly-detection-policies"></a>Verwenden der Cloud-App-Sicherheit zum Einrichten von Erkennungsrichtlinien für Anomalien

[Anomalie-Erkennungsrichtlinien](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy) in der Cloud-App-Sicherheit bieten integrierte Benutzer-und Entitäts Verhaltensanalysen (UEBA) und Maschinelles Lernen (ml), damit Sie eine erweiterte Bedrohungserkennung über Ihre Cloud-Umgebung sofort ausführen können. Da Sie automatisch aktiviert werden, bieten die neuen Erkennungsrichtlinien für Anomalien unmittelbare Ergebnisse, indem Sie sofortige Erkennungen bereitstellen, die auf zahlreiche Verhaltensanomalien für Ihre Benutzer und die mit Ihrem Netzwerk verbundenen Computer und Geräte abzielen. Darüber hinaus machen die neuen Richtlinien mehr Daten aus dem Sicherheits Erkennungsmodul für die Cloud-app verfügbar, damit Sie den Ermittlungsprozess beschleunigen und permanente Bedrohungen enthalten können.

Wir arbeiten daran, Teams-Ereignisse in Anomalie-Erkennungsrichtlinien zu integrieren. Im Moment können Sie Anomalie-Erkennungsrichtlinien für andere Office-Produkte einrichten und Aktionen für Benutzer ergreifen, die diesen Richtlinien entsprechen.

## <a name="teams-activities"></a>Teams-Aktivitäten

Im folgenden finden Sie eine Liste aller Ereignisse, die für Benutzer-und Administratoraktivitäten in Teams im Microsoft 365-Überwachungsprotokoll protokolliert werden. Die Tabelle enthält den Anzeigenamen, der in der Spalte " **Aktivitäten** " angezeigt wird, und den Namen des entsprechenden Vorgangs, der in den detaillierten Informationen zu einem Überwachungsdatensatz und in der CSV-Datei angezeigt wird, wenn Sie die Suchergebnisse exportieren.

|Anzeigename  |Vorgang|Beschreibung |
|---------|---------|---------|
|Bot zum Team hinzugefügt   |BotAddedToTeam        |Ein Benutzer fügt einen bot zu einem Team hinzu.        |
|Hinzufügen von Kanälen   |ChannelAdded         |Ein Benutzer fügt einem Team einen Kanal hinzu.         |
|Connector hinzugefügt  |ConnectorAdded          |Ein Benutzer fügt einen Verbinder zu einem Kanal hinzu.        |
|Mitglieder hinzugefügt    |MemberAdded         |Ein Teambesitzer fügt Mitglieder zu einem Team-, Kanal-oder Gruppen-Chat hinzu.         |
|Registerkarte hinzugefügt    |TabAdded         |Ein Benutzer fügt einem Kanal eine Registerkarte hinzu.        |
|Kanaleinstellung geändert    |ChannelSettingChanged         |Der ChannelSettingChanged-Vorgang wird protokolliert, wenn die folgenden Aktivitäten von einem Teammitglied ausgeführt werden. Für jede dieser Aktivitäten wird eine Beschreibung der geänderten Einstellung (in Klammern angezeigt) in der Spalte **Element** in den Suchergebnissen des Überwachungsprotokolls angezeigt. <ul><li>Ändert den Namen eines Team Kanals (**Kanalname**).</li><li>Ändert die Beschreibung eines Team Kanals (**Kanalbeschreibung**).</li> </ul>      |
|Organisations Einstellung geändert   |TeamsTenantSettingChanged         |Der TeamsTenantSettingChanged-Vorgang wird protokolliert, wenn die folgenden Aktivitäten von einem globalen Administrator im Microsoft 365 Admin Center ausgeführt werden. Diese Aktivitäten wirken sich auf organisationsweite Teams-Einstellungen aus. Weitere Informationen finden Sie unter [Verwalten von Teams-Einstellungen für Ihre Organisation](enable-features-office-365.md). <br>Für jede dieser Aktivitäten wird in den Suchergebnissen des Überwachungsprotokolls in der Spalte **Element** eine Beschreibung der geänderten Einstellung (in Klammern angezeigt) angezeigt.<ul><li>Aktiviert oder deaktiviert Teams für die Organisation (**Microsoft Teams**).</li><li>Aktiviert oder deaktiviert die Interoperabilität zwischen Microsoft Teams und Skype for Business für die Organisation (**Interoperabilität von Skype for Business**).</li><li>Aktiviert oder deaktiviert die organigrammansicht in Microsoft Teams-Clients (**organigrammansicht**).</li><li>Aktiviert oder deaktiviert die Möglichkeit für Teammitglieder, private Besprechungen zu planen (**private Besprechung planen**).</li><li>Aktiviert oder deaktiviert die Möglichkeit für Teammitglieder, Kanal Besprechungen zu planen (**Kanal Besprechung planen**).</li><li>Aktiviert oder deaktiviert Videoanrufe in Teambesprechungen (**Video für Skype-Besprechungen**).</li><li>Aktiviert oder deaktiviert die Bildschirmfreigabe in Microsoft Teams-Meetups für die Organisation (**Bildschirmfreigabe für Skype-Besprechungen**).</li><li>Aktiviert oder deaktiviert die Möglichkeit, animierte Bilder (so genannte Giphys) zu Team Unterhaltungen hinzuzufügen (**animierte Bilder**).</li><li>Ändert die Inhalts Bewertungseinstellung für die Organisation (**Inhaltsbewertung**). Die Inhaltsbewertung schränkt den Typ des animierten Bilds ein, das in Konversationen angezeigt werden kann.</li><li>Aktiviert oder deaktiviert die Möglichkeit für Teammitglieder, anpassbare Bilder (so genannte benutzerdefinierte Memes) aus dem Internet zu Team Unterhaltungen hinzuzufügen (**anpassbare Bilder aus dem Internet**).</li><li>Aktiviert oder deaktiviert die Möglichkeit für Teammitglieder, bearbeitbare Bilder (so genannte Aufkleber) zu Team Unterhaltungen hinzuzufügen (**bearbeitbare Bilder**).</li><li>Aktiviert oder deaktiviert die Möglichkeit für Teammitglieder, Bots in Microsoft Teams-Chats und-Kanälen zu verwenden (**organisationsweite Bots)**.</li><li>Aktiviert bestimmte Bots für Microsoft Teams. Dazu gehört nicht der t-bot, der für Teams Hilfe bot verfügbar ist, wenn Bots für die Organisation aktiviert sind (**einzelne Bots**).</li><li>Aktiviert oder deaktiviert die Möglichkeit für Teammitglieder, Erweiterungen oder Registerkarten (**Erweiterungen oder Registerkarten**) hinzuzufügen.</li><li>Aktiviert oder deaktiviert das Seiten Laden von proprietären Bots für Microsoft Teams (**Seiten Laden von Bots**).</li><li>Aktiviert oder deaktiviert die Möglichkeit für Benutzer, e-Mail-Nachrichten an einen Microsoft Teams-Kanal zu senden (**Kanal-e-Mail**).</li></ul>|
|Rolle von Mitgliedern im Team geändert    |MemberRoleChanged         |Ein Teambesitzer ändert die Rolle von Mitgliedern in einem Team. Die folgenden Werte geben den dem Benutzer zugewiesenen Rollentyp an. <br><br>**1** – gibt die Rolle des Besitzers an.<br>**2** – gibt die Mitglieder Rolle an.<br>**3** – gibt die Gastrolle an.<br><br>Die Members-Eigenschaft enthält auch den Namen Ihrer Organisation und die e-Mail-Adresse des Mitglieds.        |
|Einstellung des Teams geändert    |TeamSettingChanged        |Der TeamSettingChanged-Vorgang wird protokolliert, wenn die folgenden Aktivitäten von einem Teambesitzer ausgeführt werden. Für jede dieser Aktivitäten wird in den Suchergebnissen des Überwachungsprotokolls in der Spalte **Element** eine Beschreibung der geänderten Einstellung (in Klammern angezeigt) angezeigt.<ul><li>Ändert den Zugriffstyp für ein Team. Teams können als "Privat" oder "öffentlich" (**Team Zugriffstyp**) eingerichtet werden. Wenn ein Team privat ist (die Standardeinstellung), können Benutzer nur durch Einladung auf das Team zugreifen. Wenn ein Team öffentlich ist, kann es von jedem erkannt werden.</li><li>Ändert die Informationsklassifizierung eines Teams (**Team Klassifizierung**). Beispielsweise können Team Daten als Auswirkungen auf den Geschäftserfolg, mittelständische Unternehmen oder geringe geschäftliche Auswirkungen klassifiziert werden.</li><li>Ändert den Namen eines Teams (**Teamname**).</li><li>Ändert die Team Beschreibung (**Team Beschreibung**).</li><li>Änderungen, die an den Team Einstellungen vorgenommen wurden. Um auf diese Einstellungen zuzugreifen, kann ein Teambesitzer mit der rechten Maustaste auf ein Team klicken, **Team verwalten**auswählen und dann auf die Registerkarte **Einstellungen** klicken. Bei diesen Aktivitäten wird der Name der geänderten Einstellung in der Spalte **Element** in den Suchergebnissen des Überwachungsprotokolls angezeigt.</li></ul>         |
|Team erstellt    |TeamCreated         |Ein Benutzer erstellt ein Team.         |
|Alle Organisations-apps gelöscht|DeletedAllOrganizationApps           |Alle Organisations-Apps aus dem Katalog gelöscht.     |
|Gelöschte App |AppDeletedFromCatalog           |Eine App wurde aus dem Katalog gelöscht.     |
|Gelöschter Kanal     |ChannelDeleted         |Ein Benutzer löscht einen Kanal aus einem Team.         |
|Team gelöscht  |TeamDeleted            |Ein Teambesitzer löscht ein Team.      |
|Installierte App |AppInstalled         |Eine App wurde installiert.   |
|Aktion auf Karte durchgeführt|PerformedCardAction|Ein Benutzer hat in einem Chat auf einer adaptiven Karte gehandelt. Adaptive Karten werden in der Regel von Bots verwendet, um die reichhaltige Anzeige von Informationen und Interaktion in Chats zu ermöglichen. <br/><br/>**Hinweis:** Im Überwachungsprotokoll stehen nur Inline Eingabeaktionen auf einer adaptiven Karte in einem Chat zur Verfügung. Wenn ein Benutzer beispielsweise eine Umfrageantwort in einer Kanal Unterhaltung über eine Adaptive Karte sendet, die von einem Umfrage-bot generiert wurde. Benutzeraktionen wie "Ergebnis anzeigen", mit denen ein Dialogfeld geöffnet wird, oder Benutzeraktionen innerhalb von Dialogfeldern stehen im Überwachungsprotokoll nicht zur Verfügung.|
|Veröffentlichte App |AppPublishedToCatalog           |Dem Katalog wurde eine app hinzugefügt.     |
|Bot aus dem Team entfernt   |BotRemovedFromTeam         |Ein Benutzer entfernt einen bot aus einem Team.       |
|Connector entfernt     |ConnectorRemoved         |Ein Benutzer entfernt einen Connector aus einem Kanal.         |
|Mitglieder entfernt    |MemberRemoved        |Ein Teambesitzer entfernt Mitglieder aus einem Team-, Kanal-oder Gruppen-Chat.         |
|Registerkarte entfernt    |TabRemoved         |Ein Benutzer entfernt eine Registerkarte aus einem Kanal.         |
|Deinstallierte App |AppUninstalled           |Eine App wurde deinstalliert.     |
|Aktualisierte APP |AppUpdatedInCatalog           |Eine App wurde im Katalog aktualisiert.     |
|Connector aktualisiert    |ConnectorUpdated         |Ein Benutzer hat einen Verbinder in einem Kanal geändert.         |
|Registerkarte "aktualisiert"   |TabUpdated         |Ein Benutzer hat eine Registerkarte in einem Kanal geändert.         |
|Aktualisierte APP |AppUpgraded           |Eine App wurde im Katalog auf die neueste Version aktualisiert.     |
|Benutzer, der bei Teams angemeldet ist     |TeamsSessionStarted         |Ein Benutzer meldet sich bei einem Microsoft Teams-Client an. Dieses Ereignis erfasst keine Token-Aktualisierungsaktivitäten.         |

## <a name="shifts-in-teams-activities"></a>Schichten in den Teamaktivitäten

**(in der Vorschau)**

Wenn Ihre Organisation die app "Schichten" in Teams verwendet, können Sie das Überwachungsprotokoll nach Aktivitäten durchsuchen, die sich auf die Schicht-App beziehen. Im folgenden finden Sie eine Liste aller Ereignisse, die für schichtaktivitäten in Teams im Microsoft 365-Überwachungsprotokoll protokolliert werden.

|Anzeigename  |Vorgang  |Beschreibung  |
|---------|---------|---------|
|Gruppe ' Terminplanung hinzugefügt '      |SchedulingGroupAdded          |Ein Benutzer fügt dem Terminplan erfolgreich eine neue Planungsgruppe hinzu.          |
|Gruppe ' bearbeitete Planung '     |SchedulingGroupEdited         |Ein Benutzer bearbeitet eine Planungsgruppe erfolgreich.          |
|Gruppe "gelöschte Planung"         |SchedulingGroupDeleted              |Ein Benutzer löscht eine Planungsgruppe erfolgreich aus dem Terminplan.|
|Schicht hinzugefügt      |ShiftAdded          |Ein Benutzer fügt erfolgreich eine Schicht hinzu.           |
|Bearbeitete Schicht       |ShiftEdited       |Ein Benutzer bearbeitet eine Schicht erfolgreich.        |
|Gelöschte Schicht          |ShiftDeleted          | Ein Benutzer löscht eine Schicht erfolgreich.               |
|Hinzugefügte Arbeitszeit      |TimeOffAdded          |Ein Benutzer fügt dem Terminplan erfolgreich Zeit aus.          |
|Bearbeitete arbeitsfreie Zeit         |TimeOffEdited           |Ein Benutzer bearbeitet die freie Zeit erfolgreich.          |
|Gelöschte Zeit aus     |TimeOffDeleted              |Ein Benutzer löscht die Arbeitszeit erfolgreich.           |
|Geöffnete Schicht hinzugefügt     |OpenShiftAdded          |Ein Benutzer fügt erfolgreich eine offene Schicht zu einer Planungsgruppe hinzu.          |
|Geöffnete Umschalttaste bearbeitet    |OpenShiftEdited          |Ein Benutzer bearbeitet eine geöffnete Schicht in einer Planungsgruppe erfolgreich.          |
|Geöffnete UMSCHALTTASTE gelöscht      |OpenShiftDeleted          |Ein Benutzer löscht eine geöffnete Schicht aus einer Planungsgruppe erfolgreich.         |
|Freigegebener Zeitplan     |ScheduleShared                  |Ein Benutzer hat erfolgreich einen Team Zeitplan für einen Datumsbereich freigegeben.          |
|Uhr mit Zeitstempel         |ClockedIn          |Ein Benutzer hat mit der Uhrzeit Uhr erfolgreich Uhren.          |
|Getaktet mit Zeitstempel      |ClockedOut          |Ein Benutzer hat mit der Zeitschaltuhr erfolgreich ausgetaktt.          |
|Unterbrechungs Beginn mit Zeitstempel      |BreakStarted          |Ein Benutzer startet während einer aktiven Zeit Takt Sitzung erfolgreich eine Unterbrechung.          |
|Pause mit Zeitstempel beendet    |BreakEnded          |Ein Benutzer beendet während einer aktiven Zeit Takt Sitzung erfolgreich eine Unterbrechung.          |
|Zeitstempel Eintrag hinzugefügt     |TimeClockEntryAdded          |Ein Benutzer fügt erfolgreich einen neuen manuellen Zeitstempel Eintrag auf der Arbeitszeittabelle hinzu.          |
|Zeit Takt Eintrag bearbeitet     | TimeClockEntryEdited             |Ein Benutzer bearbeitet erfolgreich eine Zeit Takt Eingabe auf dem Arbeitszeittabellen.          |
|Uhrzeit Eintrag für gelöschte Zeit    |TimeClockEntryDeleted              |Ein Benutzer löscht einen Uhrzeit Eintrag erfolgreich auf der Arbeitszeittabelle.          |
|Schicht Anforderung hinzugefügt         |RequestAdded              |Ein Benutzer hat eine Schicht Anforderung hinzugefügt.          |
|Reaktion auf Schicht Anforderung     |RequestRespondedTo                  |Ein Benutzer hat auf eine Schicht Anforderung geantwortet.          |
|Abgebrochene Schicht Anforderung         |RequestCanceled               |Ein Benutzer hat eine Schicht Anforderung abgebrochen.          |
|Einstellung ' Zeitplan geändert '      |ScheduleSettingChanged          |Ein Benutzer ändert eine Einstellung in den Schichten Einstellungen.         |
|Integration von Arbeitskräften hinzugefügt      |WorkforceIntegrationAdded                  | Die Schicht-APP ist in ein Drittanbietersystem integriert.         |
|Off-Shift-Nachricht angenommen         |OffShiftDialogAccepted          |Ein Benutzer bestätigt die Off-Shift-Nachricht für den Zugriff auf Teams nach Schicht Stunden.           |

## <a name="office-365-management-activity-api"></a>Office 365-Verwaltungs Aktivitäts-API

Sie können die Office 365-Verwaltungs Aktivitäts-API verwenden, um Informationen zu Teams-Ereignissen abzurufen. Weitere Informationen zum API-Schema für Verwaltungsaktivitäten für Teams finden Sie unter [Teams-Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).


## <a name="attribution-in-teams-audit-logs"></a>Zuordnung in Teams-Überwachungsprotokollen

Zurzeit gibt es ein bekanntes Problem mit der Zuordnung von Überwachungsprotokollen und Kontroll Meldungen in Teams: ein Besitzer kann fälschlicherweise mit dem Entfernen oder Hinzufügen von Benutzern attributiert sein. Dies geschieht, wenn die Änderung außerhalb von Teams stattfindet. In diesen Fällen empfiehlt es sich, die [Office 365-Überwachungsprotokolle](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)zu verwenden.

## <a name="related-topics"></a>Verwandte Themen

- [Durchsuchen des Überwachungsprotokolls im Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 

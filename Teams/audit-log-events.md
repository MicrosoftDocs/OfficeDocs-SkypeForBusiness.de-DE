---
title: Suchen nach Überwachungsprotokoll für Ereignisse in Microsoft Teams
author: robmazz
ms.author: robmazz
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
description: Erfahren Sie, wie Sie Microsoft Teams-Daten aus dem Überwachungsprotokoll in der Microsoft Purview-Complianceportal abrufen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7d94411132b575aa4754aae993f070a36718a2d
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808446"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Durchsuchen des Überwachungsprotokolls nach Ereignissen in Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Mithilfe des Überwachungsprotokolls können Sie bestimmte Aktivitäten in allen Microsoft 365-Diensten untersuchen. Für Microsoft Teams werden unter anderem die folgenden Aktivitäten überwacht:

- Teamerstellung
- Löschung von Teams
- Hinzufügen von Kanälen
- Kanal gelöscht
- Kanaleinstellung geändert

Eine vollständige Liste der überwachten Teams-Aktivitäten finden Sie unter [Teams-Aktivitäten](#teams-activities) und [Schichten in Teams-Aktivitäten](#shifts-in-teams-activities).

> [!NOTE]
> Überwachungsereignisse aus privaten Kanälen werden ebenfalls protokolliert, wenn sie Teams und Standardkanäle betreffen.

## <a name="turn-on-auditing-in-teams"></a>Aktivieren der Überwachung in Microsoft Teams

Bevor Sie sich Überwachungsdaten ansehen können, müssen Sie zuerst die Überwachung im Microsoft Purview-Complianceportal aktivieren. Weitere Informationen finden [Sie unter Aktivieren oder Deaktivieren der Überwachung](/microsoft-365/compliance/turn-audit-log-search-on-or-off).

> [!IMPORTANT]
> Überwachungsdaten sind erst ab dem Zeitpunkt verfügbar, an dem Sie die Überwachung aktiviert haben.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Abrufen von Microsoft Teams-Daten aus dem Überwachungsprotokoll

1. Um Überwachungsprotokolle für Teams-Aktivitäten abzurufen, wechseln Sie zu <https://compliance.microsoft.com> **"Überwachen**", und wählen Sie "Überwachen" aus.

2. Filtern Sie auf der Seite **"Suchen** " die Aktivitäten, Datumsangaben und Benutzer, die Sie überwachen möchten.

3. Exportieren Sie die Ergebnisse zur weiteren Analyse nach Excel.

Schrittweise Anleitungen finden [Sie unter Durchsuchen des Überwachungsprotokolls im Compliance Center](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

> [!IMPORTANT]
> Überwachungsdaten sind nur dann im Überwachungsprotokoll sichtbar, wenn die Überwachung aktiviert ist.

Wie lange ein Überwachungsdatensatz aufbewahrt wird (und nach ihm im Überwachungsprotokoll gesucht werden kann), hängt von Ihrem Microsoft 365- oder Office 365-Abonnement und insbesondere vom Lizenztyp ab, der Benutzern zugewiesen ist. Weitere Informationen finden Sie unter [Security & Compliance Center – Dienstbeschreibung](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="tips-for-searching-the-audit-log"></a>Tipps für die Suche im Überwachungsprotokoll

Nachstehend finden Sie Tipps für die Suche nach Microsoft Teams-Aktivitäten im Überwachungsprotokoll.

:::image type="content" alt-text="Screenshot der Seite &quot;Überwachungsprotokollsuche&quot; im Compliance Center" source="media/audit-log-search-page.png" lightbox="media/audit-log-search-page.png":::

- Sie können bestimmte Aktivitäten auswählen, nach denen gesucht werden soll, indem Sie auf das Kontrollkästchen neben einer oder mehreren Aktivitäten klicken. Wenn eine Aktivität ausgewählt ist, können Sie darauf klicken, um die Auswahl aufzuheben. Sie können auch das Suchfeld verwenden, um die Aktivitäten anzuzeigen, die das von Ihnen eingegebene Schlüsselwort enthalten.

  ![Screenshot der Dropdownliste "Aktivitäten" auf der Seite "Überwachungsprotokollsuche"](media/audit-log-search.png)

- Zum Anzeigen von Ereignissen für Aktivitäten, die mit Cmdlets ausgeführt werden, wählen Sie in der Liste **Aktivitäten** die Option **Ergebnisse für alle Aktivitäten anzeigen** aus. Wenn Sie den Namen des Vorgangs für diese Aktivitäten kennen, geben Sie ihn in das Suchfeld ein, um die Aktivität anzuzeigen, und wählen Sie sie dann aus.

- Klicken Sie auf **"Alle löschen**", um die aktuellen Suchkriterien zu löschen. Der Datumsbereich wird auf die Standardeinstellung für die letzten sieben Tage zurückgesetzt.

- Wenn 5.000 Ergebnisse gefunden werden, ist es wahrscheinlich, dass mehr als 5.000 Ereignisse die Suchkriterien erfüllen. Sie können die Suchkriterien verfeinern und die Suche erneut ausführen, um weniger Ergebnisse zurückzugeben, oder Sie können alle Suchergebnisse exportieren, indem Sie " **Alle** > **Ergebnisse exportieren"** auswählen. Schrittweise Anleitungen zum Exportieren von Überwachungsprotokollen finden Sie unter [Exportieren der Suchergebnisse in eine Datei](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#step-3-export-the-search-results-to-a-file).

Sehen Sie sich [dieses Video](https://www.youtube.com/embed/UBxaRySAxyE) zur Verwendung der Überwachungsprotokollsuche an. Ansuman Acharya, Programm-Manager für Microsoft Teams, veranschaulicht, wie eine Überwachungsprotokollsuche für Microsoft Teams durchgeführt wird.

## <a name="teams-activities"></a>Microsoft Teams-Aktivitäten

Nachstehend finden Sie eine Liste aller Ereignisse, die im Hinblick auf Benutzer- und Administratoraktivitäten in Microsoft Teams im Microsoft 365-Überwachungsprotokoll erfasst werden. Die Tabelle enthält den Anzeigenamen, der in der Spalte **Aktivitäten** angezeigt wird, sowie den Namen des zugehörigen Vorgangs, der in den Detailinformationen eines Überwachungsdatensatzes und in der CSV-Datei aufscheint, wenn Sie Ihre Suchergebnisse exportieren.

|Anzeigename|Vorgang|Beschreibung|
|---|---|---|
|Bot zum Team hinzugefügt|BotAddedToTeam|Ein Benutzer fügt einem Team einen Bot hinzu.|
|Kanal hinzugefügt|ChannelAdded|Ein Benutzer fügt einem Team einen Kanal hinzu.|
|Connector hinzugefügt|ConnectorAdded|Ein Benutzer fügt einen Connector zu einem Kanal hinzu.|
|Details zu <sup>Teams-Besprechung 2</sup> hinzugefügt|MeetingDetail|Teams hat Informationen zu einer Besprechung hinzugefügt, einschließlich der Startzeit, der Endzeit und der URL für die Teilnahme an der Besprechung.|
|Informationen zu Besprechungsteilnehmern <sup>hinzugefügt 2</sup>|MeetingParticipantDetail|Teams hat Informationen zu den Teilnehmern einer Besprechung hinzugefügt, einschließlich der Benutzer-ID jedes Teilnehmers, der Zeit, zu der ein Teilnehmer der Besprechung beigetreten ist, und der Zeit, zu der ein Teilnehmer die Besprechung verlassen hat.|
|Hinzugefügte Mitglieder|MemberAdded|Ein Teambesitzer fügt Mitglieder zu einem Team-, Kanal- oder Gruppenchat hinzu.|
|Registerkarte hinzugefügt|TabAdded|Ein Benutzer fügt einem Kanal eine Registerkarte hinzu.|
|Kanaleinstellung geändert|ChannelSettingChanged|Der Vorgang "ChannelSettingChanged" wird protokolliert, wenn die folgenden Aktivitäten von einem Teammitglied ausgeführt werden. Für jede dieser Aktivitäten wird in den Suchergebnissen für das Überwachungsprotokoll in der Spalte **Element** eine Beschreibung der geänderten Einstellung (in Klammern gesetzt) angezeigt. <ul><li>Ändert den Namen eines Teamkanals (**Kanalname**).</li><li>Ändert die Beschreibung eines Teamkanals (**Kanalbeschreibung**).</li> </ul>|
|Organisationseinstellung geändert|TeamsTenantSettingChanged|Der Vorgang "TeamsTenantSettingChanged" wird protokolliert, wenn die folgenden Aktivitäten von einem globalen Administrator im Microsoft 365 Admin Center ausgeführt werden. Diese Aktivitäten wirken sich organisationsweit auf Microsoft Teams-Einstellungen aus. Weitere Informationen finden Sie unter [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md). <br>Für jede dieser Aktivitäten wird in den Suchergebnissen für das Überwachungsprotokoll in der Spalte **Element** eine Beschreibung der geänderten Einstellung (in Klammern gesetzt) angezeigt.<ul><li>Aktiviert bzw. deaktiviert Microsoft Teams für die Organisation (**Microsoft Teams**).</li><li>Aktiviert bzw. deaktiviert die Interoperabilität zwischen Microsoft Teams und Skype for Business für die Organisation (**Skype for Business-Interoperabilität**).</li><li>Aktiviert oder deaktiviert die Organigrammansicht in Microsoft Teams-Clients (**Organigrammansicht**).</li><li>Aktiviert oder deaktiviert die Möglichkeit für Teammitglieder, private Besprechungen zu planen (**Private Besprechung planen**).</li><li>Aktiviert oder deaktiviert die Möglichkeit für Teammitglieder, Kanalbesprechungen zu planen (**Kanalbesprechung planen**).</li><li>Aktiviert oder deaktiviert Videoanrufe in Microsoft Teams-Besprechungen (**Video für Skype-Besprechungen**).</li><li>Aktiviert oder deaktiviert die Bildschirmfreigabe in Microsoft Teams-Meetups für die Organisation (**Bildschirmfreigabe für Skype-Besprechungen**).</li><li>Aktiviert oder deaktiviert die Möglichkeit, animierte Bilder (so genannte Giphys) zu Microsoft Teams-Unterhaltungen hinzuzufügen (**Animierte Bilder**).</li><li>Ändert die Inhaltsbewertungseinstellung für die Organisation (**Inhaltsbewertung**). Die Inhaltsbewertung beschränkt, welche Arten animierter Bilder in Unterhaltungen angezeigt werden können.</li><li>Aktiviert oder deaktiviert die Möglichkeit für Teammitglieder, anpassbare Bilder (so genannte benutzerdefinierte Memes) aus dem Internet in Teamunterhaltungen hinzuzufügen (**Anpassbare Bilder aus dem Internet**).</li><li>Aktiviert oder deaktiviert die Möglichkeit für Teammitglieder, bearbeitbare Bilder (so genannte Aufkleber) zu Teamunterhaltungen hinzuzufügen (**Bearbeitbare Bilder**).</li><li>Aktiviert oder deaktiviert die Möglichkeit für Teammitglieder, Bots in Microsoft Teams-Chats und -Kanälen zu verwenden (**Organisationsweite Bots**).</li><li>Aktiviert bestimmte Bots für Microsoft Teams. Davon ausgenommen ist der Microsoft Teams-Hilfebot „T-Bot“, der verfügbar ist, wenn Bots für die Organisation aktiviert sind (**Einzelne Bots**).</li><li>Aktiviert oder deaktiviert die Möglichkeit für Teammitglieder, Erweiterungen oder Registerkarten hinzuzufügen (**Erweiterungen oder Registerkarten**).</li><li>Aktiviert oder deaktiviert das Querladen proprietärer Bots für Microsoft Teams (**Querladen von Bots**).</li><li>Aktiviert oder deaktiviert die Möglichkeit für Benutzer, E-Mail-Nachrichten an einen Microsoft Teams-Kanal zu senden (**Kanal-E-Mail**).</li></ul>|
|Hat die Rolle von Mitgliedern im Team geändert|MemberRoleChanged|Ein Teambesitzer ändert die Rolle von Mitgliedern in einem Team. Die folgenden Werte geben den Rollentyp an, der dem Benutzer zugewiesen wurde. <br><br>**1**: Gibt die Mitgliedsrolle an.<br>**2**: Gibt die Besitzerrolle an.<br>**3**: Gibt die Gastrolle an.<br><br>Die Eigenschaft „Mitglied“ umfasst auch den Namen Ihrer Organisation und die E-Mail-Adresse des Mitglieds.|
|Teameinstellung geändert|TeamSettingChanged|Der Vorgang "TeamSettingChanged" wird protokolliert, wenn die folgenden Aktivitäten von einem Teambesitzer ausgeführt werden. Für jede dieser Aktivitäten wird in den Suchergebnissen für das Überwachungsprotokoll in der Spalte **Element** eine Beschreibung der geänderten Einstellung (in Klammern gesetzt) angezeigt.<ul><li>Ändert die Art des Zugriffs für ein Team. Teams können als „Privat“ oder „Öffentlich" festgelegt werden (**Art des Teamzugriffs**). Wenn ein Team privat ist (Standardeinstellung), können Benutzer nur nach Einladung darauf zugreifen. Wenn ein Team öffentlich ist, kann es von allen Benutzern gefunden werden.</li><li>Ändert die Informationsklassifizierung eines Teams (**Teamklassifizierung**). Teamdaten können beispielsweise als mit hohen, mittleren oder niedrigen geschäftlichen Auswirkungen klassifiziert werden.</li><li>Ändert den Namen eines Teams (**Teamname**).</li><li>Ändert die Beschreibung eines Teams (**Teambeschreibung**).</li><li>Es wurden Änderungen an den Teameinstellungen vorgenommen. Ein Teambesitzer kann auf diese Einstellungen zugreifen, indem er mit der rechten Maustaste auf ein Team klickt, anschließend auf **Team verwalten** klickt und dann die Registerkarte **Einstellungen** auswählt. Für solche Aktivitäten wird in den Suchergebnissen für das Überwachungsprotokoll in der Spalte **Element** der Name der geänderten Einstellung angezeigt.</li></ul>|
|Erstellt einen Chat <sup>1, </sup> <sup>2</sup>|ChatCreated|Ein Teams-Chat wurde erstellt.|
|Team erstellt|TeamCreated|Ein Benutzer erstellt ein Team.|
|Eine Nachricht gelöscht|MessageDeleted|Eine Nachricht in einem Chat oder Kanal wurde gelöscht.|
|Alle Organisations-Apps gelöscht|DeletedAllOrganizationApps|Alle Organisations-Apps wurden aus dem Katalog gelöscht.|
|App gelöscht|AppDeletedFromCatalog|Eine App wurde aus dem Katalog gelöscht.|
|Kanal gelöscht|ChannelDeleted|Ein Benutzer löscht einen Kanal aus einem Team.|
|Team gelöscht|TeamDeleted|Ein Teambesitzer löscht ein Team.|
|Eine Nachricht mit einem URL-Link in Teams bearbeitet|MessageEditedHasLink|Ein Benutzer bearbeitet eine Nachricht und fügt in Teams einen URL-Link hinzu.|
|Exportierte Nachrichten <sup>1, </sup> <sup>2</sup>|MessagesExported|Chat- oder Kanalnachrichten wurden exportiert.|
|Fehler beim Überprüfen der Einladung zum freigegebenen Kanal<sup>3</sup>|FailedValidation|Ein Benutzer antwortet auf eine Einladung an einen freigegebenen Kanal, die Überprüfung der Einladung ist jedoch fehlgeschlagen.|
|Abgerufener Chat <sup>1, </sup> <sup>2</sup>|ChatRetrieved|Ein Microsoft Teams-Chat wurde abgerufen.|
|Alle gehosteten Inhalte einer Nachricht<sup>abgerufen 1, </sup> <sup>2</sup>|MessageHostedContentsListed|Alle gehosteten Inhalte in einer Nachricht, z. B. Bilder oder Codeausschnitte, wurden abgerufen.|
|App installiert|AppInstalled|Eine App wurde installiert.|
|Aktion auf Karte ausgeführt|PerformedCardAction|Ein Benutzer hat in einem Chat eine Aktion auf einer adaptiven Karte ausgeführt. Adaptive Karten werden in der Regel von Bots verwendet, um die Anzeige umfassender Informationen und die Interaktion in Chats zu ermöglichen. <br/><br/>**Hinweis:** Nur Inline-Eingabeaktionen auf einer adaptiven Karte innerhalb eines Chats sind im Überwachungsprotokoll verfügbar. Beispielsweise wenn ein Benutzer eine Antwort zu einer Umfrage in einer Kanalunterhaltung über eine adaptive Karte übermittelt, die von einem Umfrage-Bot generiert wurde. Benutzeraktionen wie "Ergebnis anzeigen", wodurch ein Dialogfeld geöffnet wird, oder Benutzeraktionen in Dialogfeldern sind im Überwachungsprotokoll nicht verfügbar.|
|Eine neue Nachricht <sup>gepostet 1, </sup> <sup>2</sup>|MessageSent|Eine neue Nachricht wurde in einem Chat oder Kanal gepostet.|
|App veröffentlicht|AppPublishedToCatalog|Dem Katalog wurde eine App hinzugefügt.|
|Lesen einer Nachricht <sup>1, </sup> <sup>2</sup>|MessageRead|Eine Nachricht eines Chats oder Kanals wurde abgerufen.|
|Lesen des gehosteten Inhalts einer Nachricht <sup>1, </sup> <sup>2</sup>|MessageHostedContentRead|Gehosteter Inhalt in einer Nachricht, z. B. ein Bild oder ein Codeausschnitt, wurde abgerufen.|
|Bot aus Team entfernt|BotRemovedFromTeam|Ein Benutzer entfernt einen Bot aus einem Team.|
|Connector entfernt|ConnectorRemoved|Ein Benutzer entfernt einen Connector aus einem Kanal.|
|Mitglieder entfernt|MemberRemoved|Ein Teambesitzer entfernt Mitglieder aus einem Team-, Kanal- oder Gruppenchat.|
|Freigabe von Teamkanal<sup>3</sup> entfernt|TerminatedSharing|Ein Team- oder Kanalbesitzer hat die Freigabe für einen freigegebenen Kanal deaktiviert.|
|Freigabe von Teamkanal<sup>3</sup> wiederhergestellt|SharingRestored|Ein Team- oder Kanalbesitzer aktivierte die Freigabe für einen freigegebenen Kanal erneut.|
|Registerkarte entfernt|TabRemoved|Ein Benutzer entfernt eine Registerkarte aus einem Kanal.|
|Auf Einladung für freigegebenen Kanal<sup>geantwortet 3</sup>|InviteeResponded|Ein Benutzer hat auf eine Einladung für einen freigegebenen Kanal geantwortet.|
|Auf eingeladene Antwort auf freigegebenen Kanal<sup>geantwortet 3</sup>|ChannelOwnerResponded|Ein Kanalbesitzer hat auf eine Antwort eines Benutzers geantwortet, der auf eine Einladung zu einem freigegebenen Kanal geantwortet hat.|
|Abgerufene Nachrichten <sup>1, </sup> <sup>2</sup>|MessagesListed|Nachrichten aus einem Chat oder Kanal wurden abgerufen.|
|Eine Nachricht mit einem URL-Link in Teams gesendet|MessageCreatedHasLink|Ein Benutzer sendet eine Nachricht mit einem URL-Link in Teams.|
|Änderungsbenachrichtigung für die Nachrichtenerstellung <sup>gesendet 1, </sup> <sup>2</sup>|MessageCreatedNotification|Eine Änderungsbenachrichtigung wurde gesendet, um eine abonnierte Listeneranwendung über eine neue Nachricht zu benachrichtigen.|
|Änderungsbenachrichtigung zum Löschen von Nachrichten <sup>gesendet 1, </sup> <sup>2</sup>|MessageDeletedNotification|Eine Änderungsbenachrichtigung wurde gesendet, um eine abonnierte Listeneranwendung über eine gelöschte Nachricht zu benachrichtigen.|
|Änderungsbenachrichtigung für Nachrichtenupdate <sup>1, </sup> <sup>2</sup> gesendet|MessageUpdatedNotification|Eine Änderungsbenachrichtigung wurde gesendet, um eine abonnierte Listeneranwendung über eine aktualisierte Nachricht zu benachrichtigen.|
|Einladung für freigegebenen Kanal<sup>gesendet 3</sup>|InviteSent|Ein Kanalbesitzer oder -mitglied sendet eine Einladung an einen freigegebenen Kanal. Einladungen zu freigegebenen Kanälen können an Personen außerhalb Ihrer Organisation gesendet werden, wenn die Kanalrichtlinie so konfiguriert ist, dass der Kanal für externe Benutzer freigegeben wird.|
|Abonnierte <sup>Nachrichtenänderungsbenachrichtigungen 1, </sup> <sup>2</sup>|SubscribedToMessages|Ein Abonnement wurde von einer Listeneranwendung erstellt, um Änderungsbenachrichtigungen für Nachrichten zu erhalten.|
|App deinstalliert|AppUninstalled|Eine App wurde deinstalliert.|
|App aktualisiert|AppUpdatedInCatalog|Eine App wurde im Katalog aktualisiert.|
|Chat <sup>1, </sup> <sup>2 aktualisiert</sup>|ChatUpdated|Ein Teams-Chat wurde aktualisiert.|
|Nachricht <sup>1, </sup> <sup>2 aktualisiert</sup>|MessageUpdated|Eine Nachricht eines Chats oder Kanals wurde aktualisiert.|
|Connector aktualisiert|ConnectorUpdated|Ein Benutzer hat in einem Kanal einen Connector geändert.|
|Registerkarte aktualisiert|TabUpdated|Ein Benutzer hat in einem Kanal eine Registerkarte geändert.|
|App-Upgrade|AppUpgraded|Für eine App wurde ein Upgrade auf die neueste Version im Katalog durchgeführt.|
|Benutzer bei Teams angemeldet|TeamsSessionStarted|Ein Benutzer meldet sich bei einem Microsoft Teams-Client an. Dieses Ereignis erfasst keine Tokenaktualisierungsaktivitäten.|

> [!NOTE]
> <sup>1</sup> Ein Überwachungsdatensatz für dieses Ereignis wird nur protokolliert, wenn der Vorgang durch Aufrufen einer Microsoft Graph-API ausgeführt wird. Wenn der Vorgang im Teams-Client ausgeführt wird, wird kein Überwachungsdatensatz protokolliert.<br/><sup>2</sup> Dieses Ereignis ist nur in Audit (Premium) verfügbar. Dies bedeutet, dass Benutzern die entsprechende Lizenz zugewiesen werden muss, bevor diese Ereignisse im Überwachungsprotokoll protokolliert werden. Weitere Informationen zu Aktivitäten, die nur in Audit (Premium) verfügbar sind, finden Sie [unter Audit (Premium) in Microsoft Purview](/microsoft-365/compliance/advanced-audit#advanced-audit-events). Informationen zu Den Lizenzanforderungen für Die Überwachung (Premium) finden Sie [unter Überwachungslösungen in Microsoft 365](/microsoft-365/compliance/auditing-solutions-overview#licensing-requirements). <br/> <sup>3</sup> Dieses Ereignis befindet sich in der öffentlichen Vorschau.

## <a name="shifts-in-teams-activities"></a>"Schichten"-Aktivitäten in Microsoft Teams

**(in der Vorschau)**

Wenn Ihre Organisation die App "Schichten" in Microsoft Teams verwendet, können Sie das Überwachungsprotokoll nach Aktivitäten im Zusammenhang mit der "Schichten"-App durchsuchen. Nachstehend finden Sie eine Liste aller Ereignisse, die im Zusammenhang mit "Schichten"-Aktivitäten in Microsoft Teams im Microsoft 365-Überwachungsprotokoll erfasst werden.

|Anzeigename|Vorgang|Beschreibung|
|---|---|---|
|Terminplanungsgruppe hinzugefügt|ScheduleGroupAdded|Ein Benutzer fügt dem Terminplan eine neue Terminplanungsgruppe hinzu.|
|Terminplanungsgruppe bearbeitet|ScheduleGroupEdited|Ein Benutzer hat eine Terminplanungsgruppe bearbeitet.|
|Terminplanungsgruppe gelöscht|ScheduleGroupDeleted|Ein Benutzer hat eine Terminplanungsgruppe aus dem Terminplan gelöscht.|
|Zeitplan zurückgezogen|ScheduleWithdrawn|Ein Benutzer hat einen veröffentlichten Zeitplan zurückgezogen.|
|Schicht hinzugefügt|ShiftAdded|Ein Benutzer hat eine Schicht hinzugefügt.|
|Schicht bearbeitet|ShiftEdited|Ein Benutzer hat eine Schicht bearbeitet.|
|Schicht gelöscht|ShiftDeleted|Ein Benutzer hat eine Schicht gelöscht.|
|Arbeitsfreie Zeit hinzugefügt|TimeOffAdded|Ein Benutzer hat im Terminplan arbeitsfreie Zeit hinzugefügt.|
|Arbeitsfreie Zeit bearbeitet|TimeOffEdited|Ein Benutzer hat arbeitsfreie Zeit bearbeitet.|
|Arbeitsfreie Zeit gelöscht|TimeOffDeleted|Ein Benutzer hat arbeitsfreie Zeit gelöscht.|
|Offene Schicht hinzugefügt|OpenShiftAdded|Ein Benutzer hat einer Terminplanungsgruppe eine offene Schicht hinzugefügt.|
|Offene Schicht bearbeitet|OpenShiftEdited|Ein Benutzer hat eine offene Schicht in einer Terminplanungsgruppe bearbeitet.|
|Offene Schicht gelöscht|OpenShiftDeleted|Ein Benutzer hat eine offene Schicht aus einer Terminplanungsgruppe gelöscht.|
|Zeitplan freigegeben|ScheduleShared|Ein Benutzer hat einen Teamzeitplan für einen Datumsbereich freigegeben.|
|Mit Stechuhr eingestempelt|ClockedIn|Ein Benutzer stempelt über die Stechuhr ein.|
|Mit Stechuhr ausgestempelt|ClockedOut|Ein Benutzer stempelt über die Stechuhr aus.|
|Mit Stechuhr Pause begonnen|BreakStarted|Ein Benutzer beginnt während einer aktiven Stechuhrsitzung eine Pause.|
|Mit Stechuhr Pause beendet|BreakEnded|Ein Benutzer beendet eine Pause während einer aktiven Zeituhrsitzung.|
|Stechuhreintrag hinzugefügt|TimeClockEntryAdded|Ein Benutzer fügt in der Arbeitszeittabelle manuell einen neuen Stechuhreintrag hinzu.|
|Stechuhreintrag bearbeitet|TimeClockEntryEdited|Ein Benutzer hat einen Stechuhreintrag in der Arbeitszeittabelle bearbeitet.|
|Stechuhreintrag gelöscht|TimeClockEntryDeleted|Ein Benutzer hat einen Stechuhreintrag in der Arbeitszeittabelle gelöscht.|
|Schichtanfrage hinzugefügt|RequestAdded|Ein Benutzer hat eine Schichtanfrage hinzugefügt.|
|Auf Schichtanfrage geantwortet|RequestRespondedTo|Ein Benutzer hat auf eine Schichtanfrage geantwortet.|
|Schichtanfrage storniert|RequestCancelled|Ein Benutzer hat eine Schichtanfrage storniert.|
|Zeitplaneinstellung geändert|ScheduleSettingChanged|Ein Benutzer hat eine Einstellung in den "Schichten"-Einstellungen geändert.|
|Mitarbeiterintegration hinzugefügt|WorkforceIntegrationAdded|Die "Schichten"-App wird in ein Drittanbietersystem eingebunden.|
|"Außerhalb der Schicht"-Nachricht angenommen|OffShiftDialogAccepted|Ein Benutzer nimmt die "Außerhalb der Schicht"-Nachricht an, um außerhalb von Schichtzeiten auf Microsoft Teams zuzugreifen.|

## <a name="office-365-management-activity-api"></a>Office 365-Verwaltungsaktivitäten-API

Sie können die Office 365-Verwaltungsaktivitäten-API verwenden, um Informationen zu Microsoft Teams-Ereignissen abzurufen. Weitere Informationen zum Verwaltungsaktivitäten-API-Schema für Microsoft Teams finden Sie unter [Microsoft Teams-Schema-](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).

## <a name="attribution-in-teams-audit-logs"></a>Zuordnungen in Microsoft Teams-Überwachungsprotokollen

Mitgliedschaftsänderungen in Microsoft Teams (z. B. hinzugefügte oder gelöschte Benutzer), im Microsoft 365-Administratorportal oder der Microsoft 365 Groups Graph-API werden in Microsoft Teams-Überwachungsnachrichten und im Kanal "Allgemein" einem bestehenden Besitzer des Teams und nicht dem eigentlichen Ausführenden der Aktion zugeordnet. Informationen zu diesen Szenarien finden Sie in Azure AD oder [Microsoft 365-Gruppenüberwachungsprotokollen](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="use-defender-for-cloud-apps-to-set-activity-policies"></a>Verwenden von Defender für Cloud-Apps zum Festlegen von Aktivitätsrichtlinien

[Mithilfe Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security) Integration können Sie [Aktivitätsrichtlinien](/cloud-app-security/user-activity-policies) festlegen, um eine Vielzahl automatisierter Prozesse mithilfe der APIs des App-Anbieters zu erzwingen. Mit diesen Richtlinien können Sie bestimmte Aktivitäten überwachen, die von verschiedenen Benutzern ausgeführt werden, oder das unerwartet häufige Auftreten einer bestimmten Aktivitätsart untersuchen.

Nachdem Sie eine Aktivitätserkennungsrichtlinie festgelegt haben, beginnt diese mit dem Generieren von Warnungen. Warnungen werden nur zu Aktivitäten generiert, die nach dem Erstellen der Richtlinie auftreten. Hier sind einige Beispielszenarien für die Verwendung von Aktivitätsrichtlinien in Defender für Cloud-Apps zum Überwachen von Teams-Aktivitäten.

### <a name="external-user-scenario"></a>Szenario "Externer Benutzer"

Ein Szenario, das Sie aus geschäftlicher Sicht vielleicht im Auge behalten möchten, ist das Hinzufügen externer Benutzer zu Ihrer Microsoft Teams-Umgebung. Wenn externe Benutzer aktiviert sind, empfiehlt es sich, ihre Anwesenheit zu überwachen.  Sie können [Defender für Cloud-Apps](/cloud-app-security/what-is-cloud-app-security) verwenden, um potenzielle Bedrohungen zu identifizieren.

:::image type="content" alt-text="Richtlinie zum Überwachen des Hinzufügens externer Benutzer." source="media/TeamsExternalUserAddPolicy.png" lightbox="media/TeamsExternalUserAddPolicy.png":::

Wie im Screenshot dieser Richtlinie zum Überwachen des Hinzufügens externer Benutzer zu sehen ist, haben Sie die Möglichkeit, die Richtlinie zu benennen, den Schweregrad entsprechend den Anforderungen Ihres Unternehmens festzulegen, es (in diesem Fall) als eine einzelne Aktivität festzulegen und dann die Parameter anzugeben, die speziell das Hinzufügen von nicht internen Benutzern überwachen und diese Aktivität auf Microsoft Teams beschränken werden.

Die Ergebnisse dieser Richtlinie können im Aktivitätsprotokoll angezeigt werden:

:::image type="content" alt-text="Ereignisse, die von der Richtlinie für externe Benutzer ausgelöst werden." source="media/TeamsExternalUserList.png" lightbox="media/TeamsExternalUserList.png":::

Hier können Sie Übereinstimmungen mit der von Ihnen festgelegten Richtlinie überprüfen und bei Bedarf Anpassungen vornehmen oder die Ergebnisse exportieren, um sie an anderer Stelle zu verwenden.

### <a name="mass-delete-scenario"></a>Szenario "Massenlöschung"

Wie weiter oben erwähnt, können Sie Löschszenarien überwachen. Es ist möglich, eine Richtlinie zu erstellen, die das Massenlöschen von Microsoft Teams-Sites überwacht. In diesem Beispiel ist eine warnungsbasierte Richtlinie so eingerichtet, dass Massenlöschungen von Teams in einem Zeitraum von 30 Minuten erkannt werden.

:::image type="content" alt-text="Richtlinie, die das Einrichten einer Richtlinie für die Erkennung von Massenlöschungen von Teams zeigt." source="media/TeamsMassDeletePolicy.png" lightbox="media/TeamsMassDeletePolicy.png":::

Wie im Screenshot zu sehen ist, können Sie viele verschiedene Parameter für diese Richtlinie festlegen, um Löschungen in Microsoft Teams zu überwachen, einschließlich Schweregrad, einzelner oder wiederholter Aktion sowie Parameter, die dies auf Microsoft Teams und Sitelöschungen beschränken. Dies kann unabhängig von einer Vorlage erfolgen, Sie können aber auch eine Vorlage verwenden, auf der diese Richtlinie basieren soll, je nach den Anforderungen Ihres Unternehmens.

Nach der Einrichtung einer für Ihr Unternehmen passenden Richtlinie können Sie die Ergebnisse zu ausgelösten Ereignissen im Aktivitätsprotokoll überprüfen:

:::image type="content" alt-text="Screenshotereignisse, die durch Massenlöschungen ausgelöst werden." source="media/TeamsMassDeleteList.png" lightbox="media/TeamsMassDeleteList.png":::

Sie können anhand der von Ihnen festgelegten Richtlinie filtern, um die Ergebnisse der Richtlinie zu sehen. Wenn Sie mit den Ergebnissen im Aktivitätsprotokoll nicht zufrieden sind (vielleicht sehen Sie eine Menge Ergebnisse, oder gar nichts), kann dies Ihnen dabei helfen, die Abfrage zu verfeinern, damit sie für Ihre Zwecke relevanter wird.

### <a name="alert-and-governance-scenario"></a>Szenario "Warnungen und Governance"

Sie können Warnungen und das Senden von E-Mails an Administratoren und andere Benutzer einrichten, wenn eine Aktivitätsrichtlinie ausgelöst wird. Sie können automatisierte Governanceaktionen festlegen, z. B. das vorübergehende Sperren eines Benutzers oder das automatisierte Auffordern zur erneuten Anmeldung für einen Benutzer. Dieses Beispiel zeigt, wie ein Benutzerkonto vorübergehend gesperrt werden kann, wenn eine Aktivitätsrichtlinie ausgelöst und ermittelt wird, dass ein Benutzer zwei oder mehr Teams in 30 Minuten gelöscht hat.

![Screenshot von Warnungen und Governanceaktionen für eine Aktivitätsrichtlinie.](media/audit-log-governance.png)

## <a name="use-defender-for-cloud-apps-to-set-anomaly-detection-policies"></a>Verwenden von Defender für Cloud-Apps zum Festlegen von Anomalieerkennungsrichtlinien

[Anomalieerkennungsrichtlinien](/cloud-app-security/anomaly-detection-policy) in Defender für Cloud-Apps bieten sofort vordefinierte Benutzer- und Entitätsverhaltensanalysen (UEBA) und Machine Learning (ML), sodass Sie sofort eine erweiterte Bedrohungserkennung in Ihrer Cloudumgebung ausführen können. Da sie automatisch aktiviert werden, bieten die neuen Anomalieerkennungsrichtlinien sofortige Ergebnisse durch sofortige Erkennung, indem sie zahlreiche Verhaltensanomalien bei allen Benutzer sowie den mit Ihrem Netzwerk verbundenen Computern und Geräten berücksichtigen. Darüber hinaus machen die neuen Richtlinien mehr Daten aus dem Erkennungsmodul von Defender für Cloud-Apps verfügbar, damit Sie den Untersuchungsprozess beschleunigen und fortlaufende Bedrohungen eindämmen können.

Wir arbeiten an der Einbindung von Microsoft Teams-Ereignissen in Anomalieerkennungsrichtlinien. Derzeit können Sie Anomalieerkennungsrichtlinien für andere Office-Produkte einrichten und Maßnahmen für Benutzer festlegen, die diesen Richtlinien übereinstimmen.

## <a name="related-topics"></a>Verwandte Themen

- [Durchsuchen des Überwachungsprotokolls im Microsoft Purview-Complianceportal](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

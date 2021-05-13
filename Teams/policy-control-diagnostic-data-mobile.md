---
title: Erforderliche mobile Diagnosedaten für Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Eine Liste von mobilen Eigenschaften und Ereignissen für die Richtliniensteuerelemente für Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c54a38a547708b78f652096cdad577088283c5b
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469647"
---
# <a name="required-mobile-diagnostic-data-for-microsoft-teams"></a>Erforderliche mobile Diagnosedaten für Microsoft Teams

Der folgende Artikel enthält eine Liste von Microsoft Teams-Ereignissen auf mobilen Geräten sowie Listen von Eigenschaften, die vom jeweiligen Ereignis erfasst werden.

## <a name="events"></a>Ereignisse

> [!NOTE]
> Es gibt einige Eigenschaften, die von allen nachstehend aufgeführten Ereignissen übermittelt werden. Informationen hierzu finden Sie unter [Eigenschaften, die mit allen Ereignissen gesendet werden](#properties-sent-with-all-events).

### <a name="panelaction"></a>PanelAction

> [!NOTE]
> Informationen zu den Eigenschaften von PanelAction-Ereignissen finden Sie unter [Eigenschaften, die mit Panelaction-Ereignissen gesendet werden](#properties-sent-with-panelaction-events).

- **accessibilityUserConfiguration**: Wenn ein Benutzer den Umschalter für ein Barrierefreiheitsfeature betätigt.
- **acknowledgeSettingChange**: Bestätigen Sie ein Update im Dialogfeld „Wir haben eine Benachrichtigungseinstellung aktualisiert“. Hierbei handelt es sich um eine Feature-Erfolgsmetrik, die zum Bestätigen von Aktualisierungsbenachrichtigungen und zur Ermittlung der Zuverlässigkeit von Benachrichtigungen verwendet wird.
- **actionComposeMenu**
  - Verwendung der Nachrichtenerweiterung anlegen.
  - Verwendung der Aktionsnachrichtenerweiterung.
- **active_session_banner_dismissed**: Das aktive Erinnerungsbanner für die Standortfreigabe wurde geschlossen.
- **activityChatClicked**: Wird ausgelöst, wenn in der Registerkarte **Aktivität** die Option Nicht-Live-Chat ausgewählt oder eine geteilte Ansicht angezeigt wird.
- **activityContextMenu**: Überlaufaktionen im Aktivitätsfeed.
- **activityFeedClick**: Es wird auf ein Element des Aktivitätsfeeds getippt und zu einem Botchat navigiert.
- **activityFeedLongPress**: Erfasst lange Druckgesten auf Feedartikel.
- **activityFeedSwipe**: Erfasst Wischgesten in Feed-Elementen.
- **activityFilterClick**: Erfasst Nutzung des Aktivitätsfilters.
- **activityFilterOptionsClick**: Erfasst Nutzung des Aktivitätsfilters.
- **activityFilterOptionsClicked**: Erfasst Nutzung des Aktivitätsfilters.
- **activityLiveChatClicked**: Wird ausgelöst, wenn in einer Live-Besprechung auf der Registerkarte **Aktivität** der Chat ausgewählt wird.
- **activityLiveDetailsClicked**: Wird ausgelöst, wenn in einer Live-Besprechung auf der Registerkarte **Aktivität** der **Details** ausgewählt wird.
- **activityTabClicked**: Hilft zu ermitteln, ob:
  - Die Registerkarte **Aktivität** wird angezeigt.
  - Teams erfasst ein Registerkartenereignis **Aktivität**.
- **activityTypeDropdown**: Erfasst die Verwendung von Aktivitätsfiltern, um zwischen **Meine Aktivitäten** und **Feeds** zu wechseln.
- **addChannel** – Hinzufügen eines Kanals. Dieses Element liefert Erfolgsdaten rund um die erfolgreiche Erstellung eines Kanals.
- **addMember**: Die Schaltfläche **Personen einladen** wurde im Menü **Mehr** aktiviert.
- **addMembers**: Fügen Sie Mitglieder zu einem Team oder einem privaten Kanal hinzu.
- **addToCalendar**: Wählen Sie die Schaltfläche **Zu Kalender hinzufügen** für Kalenderereignisse aus, die im privaten Kalender fehlen.
- **addToList**: Ein Kontakt wird einer Kontaktliste hinzugefügt.
- **addToMeeting**: Wählen Sie die Schaltfläche **Zu Besprechung hinzufügen** in der Teilnehmerliste für eine Besprechung aus (für Teilnehmer, die Teil des Chats sind).
- **addUserAsContact**: Ein Kontakt kann hinzugefügt werden, indem das Symbol **Kontakt hinzufügen** aus der Profilkarte des Kontakts ausgewählt wird.
- **admitAll**: Die Häufigkeit, mit der die Schaltfläche **Alle zulassen** im Wartebereich-Abschnitt ausgewählt wird.
- **admitParticipant**: Die Häufigkeit, in der jemand aus der Besprechungsliste in eine Besprechung aufgenommen wird.
- **alertsNavAlert**: Tippen auf ein Feed-Element.
- **android: null**: Einen Bot-Chat stummschalten oder die Stummschaltung aufheben. Dadurch wird die bestehende Telemetrie um Chats herum verbessert, indem lediglich Anwendungsinformationen hinzugefügt werden.
- **anonymousMeetingJoin** - **An Besprechung teilnehmen** wird auf der Seite „Anonym beitreten und Namen angeben“ ausgewählt, oder im Namensdialog wird **OK** angetippt.
- **anonymousMeetingJoinWelcome** - **Als Gast teilnehmen** wird auf der Startseite „Anonym an der Besprechung teilnehmen“ ausgewählt.
- **anonymousMeetingPostMeetingChat**: Die Anzahl der Benutzeransichten des Chats vom Anrufbeendigungsbildschirm aus.
- **anonymousMeetingPostMeetingRejoin**: Die Anzahl der Versuche eines anonymen Benutzers, einer Besprechung erneut beizutreten.
- **anonymousMeetingSignIn**: Die Anzahl der Male, die ein Benutzer von der Namenseingabemaske zur Anmeldung navigiert hat.
- **anonymousMeetingSignInWelcome****Anmelden und beitreten** ist auf der Startseite „Anonym an der Besprechung teilnehmen“ ausgewählt.
- **anonymousMeetingToggleMuted**: Die Anzahl, wie oft die Stummschalttaste ausgewählt wurde.
- **anonymousMeetingToggleVideo**: Die Anzahl, wie oft die Videotaste ausgewählt wurde.
- **appKilled**: Die Anwendung wird beendet.
- **approveTimeOffRequest**: Wenn ein Manager von Mitarbeitern in Service und Produktion (Frontline Worker, FLW) einen Antrag eines FLW auf arbeitsfreie Zeit genehmigt.
- **assigneeChange**: Wird ausgelöst, wenn eine neue zugewiesene Person einem Aufgabenelement hinzugefügt wird.
- **assignmentPickerClicked**: Die Schaltfläche **Zuweisen zu** ist ausgewählt und es wird eine Auswahlseite für die zugewiesene Person geöffnet.
- **assignmentRemoved**: Wird ausgelöst, wenn eine zugewiesene Person aus einem Aufgabenelement entfernt wird, indem **x** ausgewählt wird (dies ist die einzige Möglichkeit zum Entfernen einer zugewiesenen Person).
- **attachmentAdded**: Bestätigt, dass eine Anlage in einer Aufgabe erfolgreich hinzugefügt wurde.
- **attachmentDeleted**: Bestätigt, dass eine Anlage in einer Aufgabe erfolgreich gelöscht wurde.
- **attachmentUpdated**: Bestätigt, dass eine Anlage in einer Aufgabe erfolgreich aktualisiert wurde.
- **audioOnlyLowBatteryBanner**: Aufgrund eines Banners, das geringem Akkustand anzeigt, ist die Option **nur Audio** ausgewählt.
- **audioOnlyPoorNetworkBanner**: Aufgrund eines Banners, das eine schlechte Verbindung anzeigt, ist die Option **Video aus** ausgewählt.
- **audioUserDoubleTap**: Doppeltippen auf einen Audioteilnehmer.
- **autoReconnectCallmebackCallDrop**: Die Häufigkeit, mit der die Schaltfläche **Callmeback** auf einem Anrufende-Bildschirm ausgewählt wurde.
- **autoReconnectDialIn**
  - Die Schaltfläche **Einwählen** ist auf dem USB-Laufwerk „Verbindungswiederherstellung“ ausgewählt.
  - Die Häufigkeit, mit der die Schaltfläche **Einwählen** ausgewählt wurde, während eine Wiederherstellung der Verbindung stattfindet.
- **autoReconnectDialInonCallDrop**: Die Schaltfläche **Einwähle** ist auf dem USB-Laufwerk „Anruf getrennt“ ausgewählt.
- **autoReconnectDialOut**: Die Schaltfläche **Rückruf** ist auf dem USB-Laufwerk „Verbindungswiederherstellung“ ausgewählt.
- **autoReconnectRejoinonCallDrop**: Die Häufigkeit, mit der die Schaltfläche **Erneut teilnehmen** oder **Wahlwiederholung** auf einem Anrufende-Bildschirm ausgewählt wurde.
- **backFromCallMePSTN**: Rückruf-PSTN-Nummernfluss ist nicht abgeschlossen.
- **backToPhotoShare**: Zurückkehren zu einer Kamera.
- **backToStageFromWhiteboard**: Zurückkehren von einem Whiteboard zu einem Anrufbildschirm.
- **backToWhiteboardFromStage**: Wechseln von einem Anrufbildschirm zu einem Whiteboard.
- **blockAnonymous**: In folgenden Fällen:
  - Aktiviert die Anrufeinstellung, um Anrufe ohne Anrufer-ID aus den Einstellungen zu blockieren.
  - Deaktiviert die Anrufeinstellung, um Anrufe ohne Anrufer-ID aus den Einstellungen zu blockieren.
  - Aktiviert die Anrufeinstellung, um Anrufe ohne Anrufer-ID aus der Aktionstabelle zu blockieren.
  - Deaktiviert die Anrufeinstellung, um Anrufe ohne Anrufer-ID aus der Aktionstabelle zu blockieren.
- **blockCaller**: Blockiert:
  - Eine Nummer und einen Kontakt aus der neuen IOS-Aktionstabelle.
  - Einen Kontakt und eine Nummer von der Visitenkarte.
  - Nummern aus Einstellungen.
- **blockChat**: Blockieren eines Bot-Chats. Dadurch wird die bestehende Telemetrie um Chats herum verbessert und es werden lediglich Anwendungsinformationen hinzugefügt.
- **botClickCardAction**: Verwendung von Connectorkarten.
- **brbFeedback**: Bezogen auf die Leistung des „Bin gleich zurück“-Antwortformulars.
- **brbFormCancelled**: Ein Ereignis, das gesendet wird, wenn das „Bin gleich zurück“-Antwortformular abgebrochen wird und der Benutzer zur App zurückkehrt.
- **brbFormOpened**: Ein Ereignis, das gesendet wird, wenn das „Bin gleich zurück“-Formular geöffnet wird.
- **brbFormSubmit**: Ein Ereignis, das gesendet wird, wenn der Benutzer **Senden** im Antwortformular auswählt.
- **breakStartEndClicked**: Auf dem Bildschirm zum Einstempeln ist die Schaltfläche **Pause beginnen** oder **Pause beenden** ausgewählt.
- **breakStartEndTriggered**: Registrieren Sie, wenn ein Benutzer die Verwendung von „Pause beginnen“ oder „Pause beenden“ auswählt.
- **bucketSelected**: Bestätigt, dass ein Bucket erfolgreich ausgewählt wurde.
- **bucketUnselected**: Bestätigt, dass die Auswahl eines Buckets erfolgreich aufgehoben wurde.
- **bucketPickerClicked**: Bestätigt, dass die Bucket-Auswahl erfolgreich gestartet wurde.
- **BYOELiveEventJoin**: Ein Benutzer tritt einem BYOE (Broadcast Your Own Event)-Liveereignis bei.
- **calendarLiveChatClicked**: Chat aus einer Livebesprechung auf der Registerkarte **Zeitplan**.
- **calendarMeetingJoin** - Schaltfläche **Besprechungsteilnahme**, die aus einem Kalender ausgewählt wird.
- **calendarTab** – Wählen Sie den Tab **Besprechungen** in der unteren Leiste. Nützlich, um die Nutzung des Kalenders zu verstehen und mit anderen Apps in der unteren Leiste zu vergleichen, oder um festzustellen, ob es einen Fehler beim Rendern des Kalenderposts nach der Auswahl in der unteren Leiste gab.
- **calendarTabClicked**: Unter den nachstehend aufgeführten Umständen zeigt dies die Kalenderverwendung an und ermöglicht Ihnen den Vergleich mit anderen Navbar-Apps auf der unteren Leiste. Dies kann verwendet werden, um zu ermitteln, ob ein Fehler aufgetreten ist, wenn:
  - Die Registerkarte **Zeitplan** wird angezeigt.
  - Die Registerkarte **Besprechungen** ist in der unteren Leiste ausgewählt.
- **calendarUpcomingChatClicked**: Chat aus einer bevorstehenden Besprechung auf der Registerkarte **Zeitplan**.
- **callAccepted**: Anruf wird angenommen.
- **callAcceptedSFB**: Anruf wird angenommen.
- **callAppPreference**: Eine bevorzugte Anruf-App ist ausgewählt.
- **callControlsManualDismiss**: Anruf-Steuerelemente werden manuell geschlossen.
- **callControlsManualInvoke**: Anruf-Steuerelemente werden manuell aufgerufen.
- **callHistoryItemExpand**: Anrufverlaufselement erweitert.
- **callHistoryTab** - Registerkarte **CallHistory** ist in Anrufe ausgewählt.
- **callInProgressShown**: Ein **_Aktiver Anruf_*-Banner wird angezeigt.
- **callMePSTNConnected** - **Rückruf** ist erfolgreich.
- **callOrMeetUpAddParticipants**: Ausgelöst in folgenden Fällen:
  - Schaltfläche „Teilnehmer hinzufügen“ wird auf einem 1:1-Anrufbildschirm angetippt.
  - Person auswählen (VoIP) in „Teilnehmer hinzufügen“.
  - PSTN auswählen in „Teilnehmer hinzufügen“.
  - Hinzufügen von Personen in einer privaten Live-Besprechung.
  - PSTN auswählen in einer privaten Live-Besprechung.
  - Unternehmenskontakt auswählen in einer privaten Live-Besprechung.
  - Gerätekontakt auswählen in einer privaten Live-Besprechung.
  - „Teilnehmer hinzufügen erledigt“ in einer privaten Live-Besprechung.
  - Hinzufügen von Personen in einer Live-Kanal-Besprechung.
  - PSTN auswählen in einer Live-Kanal-Besprechung.
  - Teammitglied auswählen in einer Live-Kanal-Besprechung.
  - Gerätekontakt auswählen in einer Live-Kanal-Besprechung.
  - „Teilnehmer hinzufügen erledigt“ in einer Live-Kanal-Besprechung.
- **callOrMeetUpAddParticipantsDone**: Ein Benutzer schließt das Hinzufügen von Teilnehmern ab.
- **callOrMeetUpAddRoom**: Ausgelöst in folgenden Fällen:
  - **Raum hinzufügen** ist in der Liste ausgewählt.
  - In „Raum hinzufügen“ ist ein Suchergebnis ausgewählt.
  - **Schließen** ist für „In der Nähe“ ausgewählt.
  - **BT aktivieren** oder **Standort** ist für „In der Nähe“ ausgewählt.
  - In „Raum hinzufügen“ ist ein Suchergebnis für einen Raum in der Nähe ausgewählt.
  - In „Raum hinzufügen“ ist ein Suchergebnis für einen vorgeschlagenen Raum ausgewählt.
  - **Fertig** ist in Raum hinzufügen ausgewählt.
- **callOrMeetUpAudioOffSwitch**: Umklappen der Schaltfläche **Audio aus** im Begleiter-Join-Modus in einem Liveanruf oder einem Meetup.
- **callOrMeetUpAutoReconnect**: Schlechte Netzwerkleistung bewirkt, dass das Gerät eines Benutzers in den Autoreconnect-Modus wechselt.
- **callOrMeetUpCallAccepted**: Ausgelöst in folgenden Fällen:
  - Ein Anruf wird angenommen.
  - Ein PSTN-Anruf wird angenommen.
- **callOrMeetUpCallEnded**: Ausgelöst in folgenden Fällen:
  - Eine Schaltfläche **Anruf beenden** wird angetippt.
  - In callOrMeetupLive wird auf eine Schaltfläche **Anruf beendet** getippt.
  - In lockScreen wird auf eine Schaltfläche **Anruf beendet** getippt.
  - In notification wird auf eine Schaltfläche **Anruf beendet** getippt.
  - In inApp wird auf die Schaltfläche **Anruf beendet** getippt.
  - In callKit wird auf eine Schaltfläche **Anruf beendet** getippt.
  - Es wird auf eine Schaltfläche **Anruf beendet** für PSTN getippt.
- **callOrMeetUpChatWithParticipants**: Chatumschaltfläche während einer Live-Besprechung oder eines Anrufs.
- **callOrMeetUpDeviceAudioSwitch**: Ausgelöst in folgenden Fällen:
  - Audioquelle zu Lautsprecher wechseln.
  - Audioquelle zu Gerät wechseln.
  - Audioquelle zu Bluetooth wechseln.
  - Audioquelle zu „Audio aus“ wechseln.
  - Lautsprecher während einer Live-Besprechung oder eines Anrufs wechseln.
  - Lautsprecher während einer Live-Besprechung oder eines Anrufs zu „Audio aus“ wechseln.
  - Umklappen der Schaltfläche **Audio aus** im Begleiter-Join-Modus in einem Liveanruf oder einem Meetup.
  - Geräte-Audioschalter im PSTN.
- **callOrMeetUpEnterDriveMode**: Manueller Wechsel in den Laufwerksmodus aus dem Menü **...**.
- **callOrMeetupExitDriveMode** - Schaltfläche **Fahrmodus beenden** wird angetippt.
- **callOrMeetUpHold**: Ausgelöst in folgenden Fällen:
  - Die Schaltfläche **Halten** wird während einer Live-Besprechung oder eines Anrufs angetippt.
  - „Anruf wird gehalten“ in PSTN.
- **callOrMeetUpIncomingVideoSwitch**: Deaktivieren Sie IncomingVideo während einer Live-Besprechung oder eines Anrufs.
- **callOrMeetUpInvitedParticipants**: Ausgelöst in folgenden Fällen:
  - **Alle anzeigen** wird am Ende einer **Weitere Eingeladene**-Teilnehmergruppe während einer privaten Live-Besprechung angeklickt.
  - **Alle anzeigen** wird am Ende einer **Weitere Eingeladene**-Teilnehmergruppe während einer Live-Kanal-Besprechung angeklickt.
- **callOrMeetUpJoinedParticipants**: Ausgelöst in folgenden Fällen:
  - **Alle anzeigen** wird am Ende einer **In der Besprechung**-Teilnehmergruppe während einer privaten Live-Besprechung angeklickt.
  - **Alle anzeigen** wird am Ende einer **In der Besprechung**-Teilnehmergruppe während einer Live-Kanal-Besprechung angeklickt.
- **callOrMeetUpLobbyParticipants**: Ausgelöst in folgenden Fällen:
  - **Alle anzeigen** wird am Ende einer **Wartebereich**-Teilnehmergruppe während einer privaten Live-Besprechung angeklickt.
  - **Alle anzeigen** wird am Ende einer **Wartebereich**-Teilnehmergruppe während einer Live-Kanal-Besprechung angeklickt.
- **callOrMeetUpMicrophoneSwitch**: Ausgelöst in folgenden Fällen:
  - Einschalten des Mikrofons.
  - Ausschalten des Mikrofons.
  - Die Schaltfläche **Mikrofon** wird während einer Live-Besprechung oder eines Anrufs ausgewählt.
  - Mikrofon-Schalter im PSTN.
- **callOrMeetUpMuteParticipant**: Ein Remote-Teilnehmer ist stummgeschaltet.
- **callOrMeetUpMuteParticipants**: Schalten Sie alle Teilnehmer während einer Live-Besprechung oder eines Anrufs stumm.
- **callOrMeetUpParticipants**: Teilnehmer-Umschaltfläche während einer Live-Besprechung oder eines Anrufs.
- **callOrMeetUpRemoteMuteUFD**: Sie wurden stummgeschaltet UFD.
- **callOrMeetUpResume**: Ausgelöst in folgenden Fällen:
  - Die Schaltfläche **Fortsetzen** wird während einer Live-Besprechung oder eines Anrufs ausgewählt.
  - „Anruf fortsetzen“ in PSTN.
- **callOrMeetUpSearchParticipants**: Ausgelöst in folgenden Fällen:
  - Während einer privaten Live-Besprechung wird auf **Suche** in den Besprechungsteilnehmern geklickt.
  - Während einer privaten Besprechung wird auf **Suche** geklickt, nachdem die **Wartebereich**-Teilnehmergruppe angezeigt wurde.
  - Während einer privaten Besprechung wird auf **Suche** geklickt, nachdem die **In der Besprechung**-Teilnehmergruppe angezeigt wurde.
  - Während einer privaten Besprechung wird auf **Suche** geklickt, nachdem die **Weitere Eingeladene**-Teilnehmergruppe angezeigt wurde.
  - Während einer Live-Kanal-Besprechung wird auf **Suche** in den Besprechungsteilnehmern geklickt.
  - Während einer Live-Kanal-Besprechung wird auf **Suche** geklickt, nachdem die **Wartebereich**-Teilnehmergruppe angezeigt wurde.
  - Während einer Live-Kanal-Besprechung wird auf **Suche** geklickt, nachdem die **In der Besprechung**-Teilnehmergruppe angezeigt wurde.
  - Während einer Live-Kanal-Besprechung wird auf **Suche** geklickt, nachdem die **Weitere Eingeladene**-Teilnehmergruppe angezeigt wurde.
- **callOrMeetUpVideoSwitch**: Ausgelöst in folgenden Fällen:
  - Einschalten des Videos.
  - Ausschalten des Videos.
  - Video-Schaltfläche wird während einer Besprechung oder eines Anrufs ausgewählt.
- **callPark**: Ausgelöst in folgenden Fällen:
  - **Anruf parken** wird im Menü **…** ausgewählt.
  - Schaltfläche **Abrufen** ist ausgewählt.
  - **Pickup** ist im Abrufen-Dialogfeld ausgewählt.
  - **Abbrechen** ist im Abrufen-Dialogfeld ausgewählt.
- **callPreferenceSetting**: App-Einstellung „Anrufpräferenz“.
- **callsTabNewCall** - **Neuer Anruf** ist auf der Registerkarte **Anrufe** ausgewählt.
- **callTransfer**: Eine Anrufübertragung wird gestartet.
- **callVoicemailTab** - Registerkarte **Voicemail** wird unter „Anrufe“ ausgewählt.
- **cameraPermissionCancel** - Im Dialogfeld „Kameraberechtigung“ ist **Abbrechen** ausgewählt.
- **cameraPermissionGoToSettings** - Aus dem Dialogfeld „Kameraberechtigung“ wird zu **Einstellungen** navigiert.
- **cancelEditMeeting**: Wählen Sie die Schaltfläche **Schließen** auf der Besprechungsplaner-Seite aus, nachdem **Besprechung bearbeiten** ausgewählt wurde. Dies protokolliert, wenn ein Benutzer die Auswahl „Besprechung bearbeiten“ abbricht.
- **cancelFileShare** - **Abbrechen** ist im Bestätigungsdialogfeld ausgewählt.
- **cancelFileUpload** - **x** ist im Uploaddialogfeld ausgewählt.
- **cancelMeeting**: Wählen Sie **Ereignis abbrechen** auf der Besprechungsdetailsseite aus. Wird verwendet, um aggregierte Daten zur Anzahl der abgebrochenen Besprechungen zu erhalten.
- **cancelNavigationToLink**: Navigation abbrechen wurde ausgewählt.
- **cancelRequestToJoinTeam**: Abbrechen der Anforderung, einem Team beizutreten.
- **cancelRequestToJoinTeamError**: Fehler beim Abbrechen einer Anforderung, einem Team beizutreten.
- **cancelNewMeeting**: Zum Protokollieren von abgebrochenen Auswahlen „Besprechung erstellen“ und zum Überprüfen, was diese verursacht hat, wenn:
  - Auf der Seite „Besprechungsplaner“ ist die Schaltfläche **Schließen** ausgewählt.
  - Auf der Seite „Besprechungsplaner“ ist die Schaltfläche **Schließen** ausgewählt, nachdem **Besprechung bearbeiten** ausgewählt wurde.
- **cardView - No AS assigned**: Kartenansicht und Kartenrendering. Karten sind wichtige Plattformkonstrukte, und die Messung ihrer Nutzung und ihres Musters ist notwendig, um die Plattformnutzung zu verstehen und auf mögliche Probleme auf der Kundenseite zu achten. Dieses Element ist erforderlich, um jeden Fehler beim Beitreten zu einem Team zu messen.
- **castPpt**: Ereignis wird ausgelöst in folgenden Fällen:
  - Eine PowerPoint-Option ist ausgewählt.
  - Ein bestimmtes PowerPoint ist ausgewählt.
  - Der Ordner „Teams und Kanäle“ ist auf der Dateiauswahlseite ausgewählt.
  - Auswahl eines OneDrive-Ordners auf der Dateiauswahlseite.
  - Beenden der Casting-Sitzung.
  - Tippen auf Multitasking PiP.
  - Auswählen einer Anzeigeoption aus der Dateiansicht.
- **castScreen**: Bezieht sich auf:
  - Tippen auf die Option „Bildschirm freigeben“.
  - Beenden der Bildschirmfreigabesitzung.
  - Auswählen einer Anzeigeoption aus der Dateiansicht.
- **center_on_team_clicked**: Ein Benutzer zentriert die Zuordnung zu Gruppen erfolgreich.
- **channelFollow**: Aktivieren von Benachrichtigungen für einen Kanal.
- **channelUnfollow**: Deaktivieren von Benachrichtigungen für einen Kanal.
- **channelsActiveSetting**: Die **Benachrichtigung, wenn ich aktiv am Desktop bin**-Benachrichtigungseinstellung wird geändert.
- **chatCreation**: Erfolgreiche Chaterstellung.
- **changeIsActiveSetting**: Ändern der Desktopaktivitätsbasierten Benachrichtigung.
- **channel**: Neue Nachrichten-Schaltfläche oder Textfeld im Chat.
- **channelDetails**: Kanalnavigationsinformationen für die folgenden Fälle:
  - Eine Kanalüberschrift ist ausgewählt.
  - Es wird zu der Seite Kanaldetails navigiert.
- **channelFollow/channelUnfollow**: Folgen oder entfolgen Sie einem Kanals.
- **channelNav**: Von überall aus zu einem Kanal navigieren.
- **channelNavTab**: Bietet Erfolgs- und Auffindbarkeitdaten für Dateien in Teams in folgenden Fällen:
  - Die Registerkarte **Dateien** ist im Kanal ausgewählt.
  - Es gibt eine Antwort der Connectorkarte.
- **channelNotificationSettings**: Ausgelöst in folgenden Fällen:
  - Das Dialogfeld **Neue Benachrichtigungseinstellungen** ist ausgewählt.
  - Die Schaltfläche „Kanalbenachrichtigungseinstellungen" ist in der Kanalanzeige ausgewählt.
  - Eine Kanalbenachrichtigungseinstellung ist ausgewählt.
- **channelSelected**: Bestätigt, dass ein Kanal für einen neuen Plan erfolgreich ausgewählt wurde.
- **channelSendMessage**: Ausgelöst in folgenden Fällen:
  - Eine Kanalnachricht wird gesendet.
  - Ein Bot wird in einem Feld „Verfassen“ @erwähnt.
- **channelTabOverflow**: Wählt die Registerkarte **Mehr** in einem Kanal aus.
- **chat**: Verweist auf:
  - Eine neue Nachrichten-Schaltfläche oder Textfeld im Chat.
  - 1:1-Chat, der auf einem callHistory-Element ausgewählt wird.
  - Eine 1:1-Chat-Auswahl aus der Anrufliste.
- **chat - No AS Assigned**: Anzeigen des ungelesenen Chats oder Bearbeiten der Chatliste, insbesondere:
  - Auswahl der Schaltfläche **Fertig**, wenn ein Benutzer zu einem Chat hinzugefügt wird.
  - Ein Chatlistenfilter wird ausgewählt, um nach ungelesen zu filtern.
- **chatAddChat**: Fügen Sie ein Mitglieds zum Chat hinzu, Schaltfläche angetippt (dies gilt auch für den 1:1-Chat und den Gruppenchat).
- **chatAllowJoinViaLink**: Aktiviert oder deaktiviert die Teilnahmelinkfunktionen auf der Chatdetails-Seite.
- **chatAvatarEdit**: Verfolgt, wie viele Gruppen ihre Avatare von der Chatdetails-Seite ändern.
- **chatAvatarEditCamera**: Wird ausgelöst, wenn ein Benutzer den Avatar von einem Live-Kamera-Feed aus bearbeitet.
- **chatAvatarEditGallery**: Wird ausgelöst, wenn ein Benutzer den Avatar von der Smartphone-Gallerie aus bearbeitet.
- **chatAvatarEditView**: Wird ausgelöst, wenn ein Benutzer das Bild des bestehenden Avatars anzeigt.
- **chatListNavConversations**: Wenn ein Benutzer auf ein Chatlistenelement tippt.
- **chatCancelAudioCall**: Einen Gruppen-Audioanruf abbrechen – Bestätigungsdialogfeld.
- **chatCancelVideoCall**: Einen Gruppen-Videoanruf abbrechen – Bestätigungsdialogfeld.
- **chatCM_CopyText**: Tippen Sie auf **Text kopieren** in einem Chat-Kontextmenü.
- **chatCM_DeleteMessage**: Tippen Sie auf **Nachricht löschen** in einem Chat-Kontextmenü.
- **chatCM_edit**: Tippen Sie auf **Bearbeiten** in einem Chat-Kontextmenü.
- **chatCM_Forward**: Tippen Sie auf **Weiterleiten** in einem Chat-Kontextmenü.
- **chatCM_markUnread**: Tippen Sie auf **Als ungelesen markieren** in einem Chat-Kontextmenü.
- **chatCM_save**: Tippen Sie auf **Speichern** in einem Chat-Kontextmenü.
- **chatCM_SeenBy**: Tippen Sie auf **Gesehen** in einer Kontextmenü-Option. Lesebestätigungen, z. B. gelesen von (readby)
- **chatContactsEnter**: Die Registerkarte **Chatkontakte** wird eingegeben.
- **chatDetails**: Bietet Erfolgs- und Auffindbarkeitsdaten für eine Chatdetailseite, wenn:
  - Eine Chatüberschrift wird ausgewählt.
  - Es wird zu einer Chatdetailseite navigiert.
- **chatRecentEnter**: Die Registerkarte **Zuletzt verwendeter Chat** wird eingegeben.
- **chatSendMessage**: Senden Sie eine Chatnachricht.
- **chatShareLink**: Verfolgt, wie viele Benutzer einen Gruppeneinladungslink senden.
- **chatStartAudioCall**: Ausgelöst in folgenden Fällen:
  - Antippen der Schaltfläche „1:1-Audioanruf“.
  - Antippen der Schaltfläche **Audio** in einem Suchergebnis.
  - Antippen der Schaltfläche **Anruf starten** auf der rechten Seite.
  - Antippen von 1:1-Audioanruf von einem callHistory-Element aus.
  - Antippen von 1:1-Audioanruf von einem voicemail-Element aus.
  - Führen Sie eine Gruppen-Audioanruf durch – Bestätigungsdialogfeld.
- **chatStartAudioCallOnBehalfOf**: Delegieren startet einen Anruf aus der Aktionstabelle als „Chef“.
- **chatStartAudioCallOnBehalfOfMyself**: Delegieren startet einen Anruf aus der Aktionstabelle als „Ich selbst“.
- **chatStartAudioCallSFB**: Antippen der 1:1-Audioanruf-Schaltfläche.
- **chatStartVideoCall**: Ausgelöst in folgenden Fällen:
  - Tippen der Schaltfläche „1:1-Videoanruf“.
  - Tippen der Videoschaltfläche in einem Suchergebnis.
  - Antippen von 1:1-Videoanruf von einem callHistory-Element aus.
  - Durchführen eines Gruppen-Videoanrufs – Bestätigungsdialogfeld.
- **chatStartVideoCallSFB**: 1:1-Videoanruf-Schaltfläche angetippt.
- **chatWithMeetingParticipants**: Auswählen der Registerkarte **Chat** von der Besprechungsdetailsseite aus.
- **checkListAddClicked** - **Element hinzufügen** ist in der Aufgabendetail-Anzeige für den Checklistenabschnitt ausgewählt.
- **checkListItemAdded**: Für eine Aufgabe wird ein Checklistenelement erstellt.
- **checkListItemDeleted**: Ein Checklistenelement wird aus einer Aufgabe gelöscht.
- **checkListItemAdded**: Für eine Aufgabe wird ein Checklistenelement aktualisiert.
- **channelPickerClicked**: Bestätigt, dass die Kanalauswahl erfolgreich gestartet wurde.
- **checklistSeeAllClicked**: Wenn innerhalb der Aufgabendetails die Schaltfläche **Alle anzeigen** ausgewählt ist, um alle Checklistenelemente anzuzeigen.
- **chicletExpand**: Verstehen Sie, wie Karten auf mobilen Geräten in der Vorschau angezeigt werden und wie die Vorschau geschlossen wird.
- **clearFilter**: Wenn alle Filter beim Anzeigen einer Aufgabenliste gelöscht werden.
- **clickPhotoOfficeLens**: Wählen Sie **Foto aufnehmen** aus – Kamera starten (nur Android).
- **clockInEntryTeamSelectionShown**: Ein Benutzer wählt ein Team für die Zeituhr aus, während er nicht eingestempelt ist.
- **clockInOutClicked**: Auf der Bildschirmanzeige „einstempeln“ sind die Schaltflächen **Einstempeln** oder **Ausstempeln** ausgewählt.
- **clockInOutTriggered**: Registrieren Sie das Ein- oder Ausstempelns eines Benutzers. Dies wird erst ausgelöst, wenn Sie den Speicherort überprüft haben und vorausgesetzt, dass der Standort erforderlich ist.
- **closedBannerMessage**: Wird ausgelöst, wenn die Bannernachricht einer Benachrichtigung geschlossen wird.
- **closeLobbyBanner**: Häufigkeit, mit der die Wartebereichtoastmeldung über dessen Schaltfläche **Schließen** geschlossen wird.
- **commentAdded**: Bestätigt, dass einer Aufgabe ein Kommentar hinzugefügt wurde.
- **commentsClicked**: Bestätigt, dass die Kommentar-Ansicht erfolgreich gestartet wurden.
- **commentUpdated**: Bestätigt, dass ein Kommentar zu einer Aufgabe erfolgreich aktualisiert wurde.
- **companionBannerJoin**: Wählen Sie im Banner der obersten Ebene **Beitreten** aus.
- **companionDismiss**: Schließen Sie das Begleitbanner.
- **companionDismissProximity**: Schließen Sie das Begleitbanner.
- **companionJoin**: Die Option „Als Begleiter beitreten“ wird auf dem Arbeitsblatt ausgewählt.
- **companionJoinProximity**: Durch das Begleitbanner beigetreten.
- **completionStateChange**: Wird ausgelöst, wenn in der Filteransicht in der Aufgabenliste ein abgeschlossener oder nicht abgeschlossener Filterumschalter ausgewählt wird.
- **composeExpandComposer** - Die Schaltfläche **Format** wird angetippt.
- **composeFilePick**: Native Dateiauswahl gestartet.
- **composeImagePicker** -  Die Schaltfläche **Bild** wird angetippt.
- **composeLocation** - Die Schaltfläche **Standort** wird in Verfassen angetippt.
- **composeMention**: @erwähnen.
- **composeOpenEmoticonPicker**: Die Emoticon-Auswahl wird angetippt.
- **composeOpenFunPicker**: Die Spaß-Auswahl wird angetippt.
- **composeParticipantAdded**: Wenn ein Teilnehmer zur Schichten-App hinzugefügt wird.
- **composeSearchResult**: Auswahl des Ergebnisses der Nachrichtenerweiterung, die zum Verständnis der Relevanz des Suchergebnisses der App hilfreich ist. Verbessert auch die Nachrichtensende-Telemetrie mit Appdaten.
- **composeSelectExtension**: Tippen Sie auf eine ME-App.
- **composeSendSmartReply**: Ein Smart Reply-Element wird angeklickt.
- **composeSendMessage**: Verbessert die Nachrichtensende-Telemetrie mit Appdaten.
- **confirmAudioOn**: Ein Benutzer bestätigt, dass er Audio angeschaltet haben möchte.
- **confirmFileShare** - **Freigeben** wird im Bestätigungsdialogfeld ausgewählt.
- **consultTransfer**: Ausgelöst in folgenden Fällen:
  - Wählt **Übertragung** > **Zuerst konsultieren**
  - Übertragungsziel ist auf Person festgelegt
  - Übertragungsziel ist auf Telefonnummer festgelegt.
- **consultTransferCall**: Ausgelöst in folgenden Fällen:
  - Ein Konsultierungsanruf wird initiiert.
  - Bestätigen ist in einem Dialogfeld „Übertragung wird bestätigt“ aktiviert.
  - Abbrechen ist in einem Dialogfeld „Übertragung wird bestätigt“ aktiviert.
  - Die Schaltfläche **Bannerübertragung** ist ausgewählt.
  - Die Schaltfläche **Banner wiederaufnehmen** ist ausgewählt.
- **consultTransferChat**: Ausgelöst in folgenden Fällen:
  - Ein Konsultierungschat wird initiiert.
  - Bestätigen ist in einem Dialogfeld „Übertragung wird bestätigt“ aktiviert.
  - Bestätigt ist in einem Dialogfeld „Übertragung wird bestätigt“ aktiviert.
  - Eine Schaltfläche **Bannerübertragung** oder **Banner wiederaufnehmen** ist ausgewählt.
- **consumeVoiceMessage**: Sprachausgabe wird abgespielt.
- **ContactCard_SeeMoreOOF**: Mehr anzeigen von einer langen Abwesenheitsnachricht.
- **contactOrganizer**: **Kontaktorganisator** ausgewählt.
- **conversation, tabs**: Registerkarte ausgewählt.
- **copyLink**: Kopieren Sie einen Link in einen Kanalbeitrag.
- **contactActivity**: Wenn die Schaltfläche zum Anzeigen der Aktivität eines Benutzers auf der Visitenkarte aktiviert ist.
- **conversation**: Wenn ein Benutzer zur Registerkarte **Chat** oder **Beiträge** navigiert.
- **CreateChannel**: Bietet Erfolgsdaten rund um die erfolgreiche Erstellungs- oder Verwerfen-Aktion für die neue Kanalerstellung, wenn:
  - Die Schaltfläche **Fertig** wird auf der Seite **Kanal erstellen** ausgewählt.
  - Die Schaltfläche **Abbrechen** wird auf der Seite **Kanal erstellen** ausgewählt.
- **createComposeExtension**: Erstellen Sie die Verwendung der Nachrichtenerweiterung oder die Aktion ME-Verwendung.
- **createConversationClicked**: Wenn eine Unterhaltung mit anderen Mitarbeitern erstellt wird.
- **createDefaultPlannerPlan**: Eine freigegebene Liste wird automatisch erstellt, wenn die Aufgaben-App zum ersten Mal von jedem beliebigen in dieser Gruppe geöffnet wird, überprüft die automatische Liste, die mit dem Planer-Dienst erstellt wurde. Bestätigt, dass die standardmäßige freigegebene Aufgabenliste erfolgreich in Planner erstellt wird, wenn ein Benutzer das erste Mal eine freigegebene Aufgabenliste erstellt.
- **createOrJoinTeam**: Die Schaltfläche **+** wird ausgewählt, um ein Team zu erstellen oder ihm beizutreten.
- **createPersonalPlan**: Eine persönliche Liste wird erstellt, Prüfliste mit ToDo-Dienst erstellt. Bestätigt, dass in ToDo eine neue persönliche Aufgabenliste erstellt wird.
- **createPersonalSubtask**: Bestätigt, dass eine persönliche Teilaufgabe erfolgreich erstellt wurde.
- **createPersonalTask**: Bestätigt, dass eine persönliche Aufgabe erfolgreich erstellt wurde.
- **createplan**: Bestätigt, dass eine freigegebene Aufgabenliste erfolgreich erstellt wurde. Bestätigt, dass ein freigegebener Plan erfolgreich über die mittlere Ebene erstellt wurde.
- **createPlannerPlan**: Eine freigegebene Liste wird erstellt, überprüft Liste die mit Planner-Dienst erstellt wurde. Bestätigt, dass in Planner eine neue freigegebene Aufgabenliste erstellt wird.
- **createPlannerTask**: Überprüft einen Aufruf des Planner-Diensts. Bestätigt, dass eine Aufgabe erfolgreich in einer Liste mit freigegebenen Aufgaben erstellt wurde.
- **createShiftClicked**: Wenn ein Manager **Schicht erstellen** auswählt.
- **createShiftOrTimeOffClicked**: Wird ausgelöst, wenn Sie **Schicht erstellen** oder **Abwesenheit** auswählen.
- **CreateTask**: Wird verwendet, wenn der Erstellungsvorgang fehlschlägt, überprüft den Call zum Planner-Dienst. Bestätigt, dass der Vorgang zum Erstellen einer Aufgabe fehlgeschlagen ist.
- **createtasklist**: Wenn ein Benutzer zur „Plan erstellen“-Ansicht aus der Startansicht navigiert.
- **createTeam**: Bietet Erfolgsdaten rund um die erfolgreiche Erstellungs- oder Verwerfen-Aktion für die neue Teamerstellung, wenn:
  - Die Schaltfläche **Fertig** wird auf der Seite **Team erstellen** ausgewählt.
  - Die Schaltfläche **Abbrechen** wird auf der Seite **Team erstellen** ausgewählt.
- **createTeam, createChannel**: Bietet Erfolgsdaten über das erfolgreiche Hinzufügen von Mitgliedern in ein Team und die erfolgreiche Erstellung eines neuen Teams, wenn:
  - Die Schaltfläche **Überspringen** wird auf der Seite **Mitglieder hinzufügen** ausgewählt (zuerst bereits vorhandene überprüfen).
  - Die Schaltfläche **Fertig** wird auf der Seite **Mitglieder hinzufügen** ausgewählt (zuerst bereits vorhandene überprüfen).
  - Zeigt die Bestätigung der Team- oder Kanalerstellung an.
- **crossCloudDialogCancel** - **Abbrechen** wird für einen cloudübergreifenden Dialog ausgewählt.
- **crossCloudDialogJoin** - **Als Gast beitreten** wird für einen cloudübergreifenden Dialog ausgewählt.
- **dashboardNav**: Ein Benutzer navigiert zu einer Kachel im Chat-Dashboard.
- **dateChanged**: Ein Benutzer hat ein Schichtdatum geändert.
- **datePickerLaunch**: Bestätigt, dass die Datumsauswahl erfolgreich gestartet wurde.
- **dayClicked**: Auswählen der Tagesanzeige, wenn der Benutzer seine Schichten sieht.
- **daySaved**: Ein Benutzer speichert die Tagesverfügbarkeit, speichert einen Schichttag.
- **declineTimeOffRequest**: Wenn ein Benutzer die Anforderung für arbeitsfreie Zeit ablehnt. Es handelt sich um eine Schlüsselfunktion für arbeitsfreie Zeit, mit der Manager Anforderungen für arbeitsfreie Zeit ablehnen können.
- **deleteClicked**: Wenn **Löschen** innerhalb der Aufgabendetails ausgewählt wird, wodurch das Bestätigungsdialogfeld angezeigt wird.
- **deleteContact**: Ein Benutzer löscht einen vorhandenen privaten Kontakt.
- **deleteMeeting**: Wählen Sie auf der Besprechungsdetailseite die Schaltfläche **Löschen** aus.
- **deletePersonalTask**: Bestätigt, dass eine persönliche Aufgabe erfolgreich gelöscht wurde.
- **deletePersonalSubtask**: Bestätigt, dass eine persönliche Teilaufgabe erfolgreich gelöscht wurde.
- **deletePlannerTask**: Bestätigt, dass ein Löschvorgang für eine freigegebene Aufgabe erfolgreich abgeschlossen wurde.
- **deleteShift**: Löschen einer Schicht.
- **duration_picker_dismissed**: Wenn die Dauer-Auswahl geschlossen wird.
- **deleteTask**: Überprüft beim Planner-Dienst, ob eine Löschaktion erfolgreich oder nicht erfolgreich war. Bestätigt, dass das Löschen einer Aufgabe fehlgeschlagen ist, das heißt, die Löschung einer Aufgabe war nicht erfolgreich.
- **deleteVoicemail**: „Voicemail-Element löschen“ angetippt.
- **demotedToAttendee**: Ein Benutzer degradiert einen Referenten – Schaltfläche **Ändern** im Dialogfeld.
- **denyParticipant**: Häufigkeit, mit der ein Benutzer einer Person einen Eintrag aus der Liste verweigert.
- **descriptionChanged**: Bestätigt, dass die Beschreibung einer freigegebenen Aufgabe erfolgreich geändert wurde.
- **descriptionClicked**: Wenn ein Benutzer **Beschreibung anzeigen** aus den Aufgabendetails auswählt.
- **detailsTabClicked**: Die Registerkarte **Details** ist in der Besprechung ausgewählt.
- **deviceAddressBookSync**: Wird ausgelöst, wenn die Adressbuchsynchronisierung über die Einstellungsseite aktiviert ist.
- **deviceAddressBookUnsync**: Wird ausgelöst, wenn die Adressbuchsynchronisierung über die Einstellungsseite deaktiviert ist.
- **dialIn**: Ein Benutzer wählt die Einwahl in eine Besprechung (verschiedene Standorte).
- **dialInBadNetworkBanner** - **Einwählen** wird für ein Banner „schlechte Verbindung“ ausgewählt.
- **dialInBadNetworkBannerCancel**: Das **Einwählen** wird im systemeigenen Dialogfeld abgebrochen.
- **dialInBadNetworkBannerConfirm**: Das **Einwählen** wird im systemeigenen Dialogfeld bestätigt.
- **dialInCall** - **Anrufen** wird auf dem Popup **Einwählen** ausgewählt.
- **dialInCancel** - **Abbrechen** wird auf dem Popup **Einwählen** ausgewählt.
- **dialOutCall**: Wird ausgelöst, wenn ein Benutzer:
  - Im Laufwerkmodus beitritt.
  - **Anrufen** auf dem Popup **Rückruf** auswählt.
- **dialOutCallAAD**: Wenn eine Nummer aus **Meine Nummern** in der Aktionstabelle ausgewählt wird.
- **dialOutCallRecent**: Wenn eine Nummer von vorherigen zuletzt verwendeten Nummern in der Aktionstabelle ausgewählt wird.
- **dialOutCancel** - **Abbrechen** wird auf dem Popup **Rückruf** ausgewählt.
- **dialOutDialog** - **Neue Nummer** wird in der Aktionstabelle ausgewählt.
- **dialOutFailRetry** - **Wiederholen** wird aus einem Fehler-Banner ausgewählt.
- **Dialpad**: Die Schaltfläche **Wähltastatur** wird aus der Anrufliste ausgewählt.
- **disableCategory**: Deaktivieren Sie eine Art von Benachrichtigung, oder deaktivieren Sie eingehende Anrufbenachrichtigungen.
- **disabled** - **Benachrichtigungen überspringen** wird in der FRE (First-run experience) ausgewählt. Dies liefert wichtige Erfolgsdaten für das Überspringen der Benachrichtigung im FRE-Fluss.
- **disableQuietDays**: Ruhige Tage deaktiviert. Feature-Erfolgstelemetrie für ruhige Tage.
- **disableQuietHours**: Ruhige Stunden deaktiviert.
- **discoverTeams**: Navigieren Sie zu „Teams durchsuchen und beitreten“.
- **Dismiss_earlycancelledCQF**: Das CQF-Formular „vorzeitig abgebrochener Anruf“ wird zurückgewiesen.
- **Dismiss_ratemycallCQF**: Das CQF-Formular „Anruf bewerten“ wird zurückgewiesen.
- **Dismiss_ratemyliveeventCQF**: Das CQF-Formular „Mein Liveereignis bewerten“ wird zurückgewiesen.
- **dismissBadNetworkBanner** - **Schließen** wird für ein Banner „schlechte Verbindung“ ausgewählt.
- **dismissFlyout** - Schaltfläche **Schließen** wird ausgewählt.
- **dismissModality**: Die Modalitätsauswahl wird ohne Freigabe beendet.
- **dismissModalityPicker**: Die Schaltfläche **Modalitätsauswahl** wird ausgewählt.
- **dismissReadReceiptsNotice** - **Verstanden** wird aus einer Feature-Benachrichtigung ausgewählt.
- **dismissStartRecording**: Fehler beim Starten der Aufzeichnung zurückweisen.
- **dismissStopRecording**: Fehler beim Beenden der Aufzeichnung zurückweisen.
- **dismissUseWifiForVideoBanner**: Wird ausgelöst, wenn ein Benutzer ein Banner zurückweist:
  - Das den Benutzer informiert, dass das Video des entfernten Teilnehmers blockiert ist und Benutzer zu WLAN wechseln müssen, um es zu sehen.
  - Das den Benutzer informiert, dass die Benutzer zum Freigeben von Videos zu WLAN wechseln müssen.
- **DLPDelete**: Ein Benutzer hat eine blockierte Nachricht gelöscht.
- **DLPEdit**: Ein Benutzer hat eine blockierte Nachricht bearbeitet.
- **DLPOverride**: Ein Benutzer hat eine blockierte Nachricht überschrieben.
- **DLPOverrideReport**: Ein Benutzer hat ein falsch positives Ergebnis gemeldet und die Nachricht überschrieben.
- **DLPReport**: Ein Benutzer hat ein falsch positives Ergebnis gemeldet.
- **DLPResolve**: Ein Benutzer hat versucht, eine DLP-Nachricht aufzulösen.
- **DLPSeeOriginal**: Ein Benutzer hat getippt, um eine Originalnachricht zu sehen.
- **downloadFile**: Hilft, um zu:
  - Ermitteln, ob ein Downloadvorgang eingeleitet wurde.
  - Ermitteln, ob eine Datei erfolgreich heruntergeladen wurde.
- **dragDatePickerHandle**
- **dtmfPSTNCall**: Die MFV-Schaltfläche wird auf der Wähltastatur angetippt.
- **dueDateChanged**: Wird ausgelöst, wenn ein Benutzer einem Vorgang ein Fälligkeitsdatum zuweist.
- **dueDatePickerClicked**: Wird ausgelöst, wenn in Aufgabendetails die Schaltfläche **Fälligkeitsdatum** ausgewählt wird, wodurch die Seite Fälligkeitsdatum-Auswahl geöffnet wird.
- **dueDateSelected**: Wird ausgelöst, wenn ein Benutzer einen Filter nach Fälligkeitsdatum beim Anzeigen einer Taskliste anwendet.
- **dueDateUnselected**: Wird ausgelöst, wenn ein Benutzer einen Filter nach Fälligkeitsdatum beim Anzeigen einer Taskliste entfernt.
- **edit** - Schaltfläche **Bearbeiten** in einer Chatnachricht.
- **editChannel**: Ein Benutzer wählt eine Schaltfläche aus, um einen Kanal zu bearbeiten, den Sie besitzen oder verwalten.
- **editContact**: Ein Benutzer bearbeitet einen vorhandenen privaten Kontakt, indem er beispielsweise zur Visitenkarte navigiert.
- **editMeetingResponse**: Besprechungsantwort von der Besprechungsdetailseite bearbeiten.
- **editNavigation** - **Neu anordnen** wird im Menü **Mehr** ausgewählt, um die Reihenfolge der Apps auf der unteren Leiste zu bearbeiten.
- **editRsvpMeetingOptions**: Wählen Sie **RSVP** aus, um die vorherige Auswahl zu ändern.
- **editShiftClicked**: Eine Schicht bearbeiten.
- **editSmartReply**: Ein Smart Reply-Element wird angeklickt.
- **editTeam**: Ein Benutzer tippt auf eine Schaltfläche, um ein Team zu bearbeiten, das er besitzt oder verwaltet.
- **editTeam, editChannel**: Bezieht sich auf die erfolgreiche Hinzufügung von Mitgliedern in einem Team und die erfolgreiche Erstellung eines bestehenden Teams in folgenden Fällen:
  - Die Schaltfläche **Abbrechen** wird auf der Seite **Mitglieder hinzufügen** ausgewählt (bereits vorhandenes Team oder Kanal).
  - Die Schaltfläche **Fertig** wird auf der Seite **Mitglieder hinzufügen** ausgewählt (bereits vorhandenes Team oder Kanal).
- **emergencyCall**: Notruf führte Anrufplan durch.
- **emergencyCallDirectRouting**: Notruf führte direktes Routing durch.
- **emergencyCallLocationPolicyBased**: DialEmergency durch Wähltastatur verwendet.
- **emergencycallSecurityDeskNotify** – Notruf abgesetzt, Sicherheitsdesk informiert.
- **enableCategory**: Bezieht sich auf Benachrichtigungseinstellungen beim Aktivieren von:
  - Einem Benachrichtigungstyp.
  - Eingehenden Anrufbenachrichtigungen.
- **enabled**: Bezieht sich auf das Aktivieren der Benachrichtigung im FRE (First-run experience)-Fluss:
  - **Enable notifications** wird in der FRE (First-run experience) ausgewählt.
  - „Aktivieren“ wird in einer Erinnerung ausgewählt.
- **enabled/disabled**: Anrufberechtigungen oder Kontaktberechtigungen (nur Android).
- **enabled, notNow**: Schaltfläche **Annehmen** für die Aufforderung zur Benachrichtigungsberechtigung, FRE (First-run experience)-Benachrichtigungsberechtigung (iOS). Damit wird erfasst, wie viele Personen das Benachrichtigungsfeature aktiviert haben, und es werden Informationen bereitgestellt.
- **enablediOSPrompt**: Ein Benutzer aktiviert tatsächlich Benachrichtigungen in der Eingabeaufforderung für iOS-Benachrichtigungen. Dies gibt Informationen über Benutzer, die tatsächlich Benachrichtigungen in iOS von der Eingabeaufforderung für Benachrichtigungsberechtigungen aus aktivieren.
- **enabledQuietDays**: Ruhige Tage aktiviert.
- **enableLocationPermission**: Wenn ein Benutzer die Standortberechtigungen für die Standortfreigabefunktion aktiviert.
- **enableQuietDays**: Ein Benutzer aktiviert ruhige Tage.
- **enableQuietHours**: Ruhige Stunden aktiviert.
- **endEditing** - Schaltfläche **Speichern** gedrückt.
- **endFileShare** - **Zurück** ist im Dialogfeld „Dateifreigabe“ ausgewählt.
- **endMyShift**: Anzahl der Geräte im Freigabemodus oder Anzahl der Abmeldungen.
- **endPhotoShare** - **x** aus der Fotofreigabe.
- **entryPointClicked**: **Anforderungen** auf der Registerkarte **Zeitplan** auswählen. Anforderungen gelten für den Zeitpunkt, zu dem ein Mitarbeiter in Service und Produktion Schichtzeit anfordert usw.
- **endPSTNCallSelected**: Ein Benutzer beendet einen PSTN- und Inhaltsanruf.
- **endPSTNCallShown**: Ein Benutzer wird aufgefordert, ein PSTN- oder einen Inhaltsanruf zu beenden.
- **endVideoShare** - **x** aus der Videofreigabe.
- **errorShown**: Es wird ein Fehler angezeigt.
- **expand/collapse**: Abschnitt „Gerätekontakte“ oder „Unternehmenskontakte“.
- **expandCollapseSection**: Tippen Sie auf einen Abschnittskopf, um einen Abschnitt zu erweitern oder zu reduzieren.
- **Expected: atMention - Android: chatSendMessage - iOS: sendMsg**: @erwähnen Sie einen Bot in einem „Verfassen“-Feld.
- **Erwartet: botClickCardAction – Android: showCard – iOS: fehlt**: Tippen Sie auf Kartenschaltflächen. Karten sind wichtige Plattformkonstrukte und die Messung ihrer Verwendung und ihrer Muster ist notwendig, um die Plattformnutzung zu verstehen und nach potenziellen Problemen auf der Client-Seite Ausschau zu halten.
- **Expected: chatSendMessage - iOS: composeSendMessage**: Tippen Sie auf **Antworten** und antworten Sie auf einen Bot-Chat in einem Kanal.
- **Expected: composeSendMessage - Android: replyChannel - iOS: missing**: Tippen Sie auf **Antworten** und antworten Sie auf einen Bot-Chat in einem Kanal.
- **Expected: messageLike - Android: reactLike_CM**: Drücken Sie bei einer Bot-Nachricht auf „Gefällt mir“.
- **Expected: messageUnread - Android: markAsLastUnread**: Nachrichtenkontext-Menüoptionen für eine Bot-Nachricht.
- **federatedUpgradeNewChat**: Der ältere Chat wird auf „nativ“ aktualisiert.
- **files**: Verfolgt, ob die Dateiauflistung im Chat- und Kanal-Dateien-Register erfolgreich durchgeführt wurde.
- **fileSelected**: Eine PowerPoint-Präsentation wird ausgewählt.
- **fileThumbnailPreviewDownloaded**: Hilft bei der Identifizierung, ob eine Miniaturansicht für eine Datei erfolgreich gerendert wurde.
- **fileThumbnailPreviewFromCache**: Erfasst, ob die Miniaturansicht aus dem Cache erfolgreich angezeigt wird, und hilft bei der Identifizierung, ob die Miniaturansicht für eine Datei erfolgreich gerendert wurde.
- **fileThumbnailPreviewNotAvailable**: Hilft bei der Identifizierung, ob die Miniaturansicht für eine Datei erfolgreich gerendert wurde.
- **fillFrameVideo**: Rahmen aus Aktionstabelle ausfüllen.
- **firstTimeSignedIn** Anmelden oder Für Ereignis anmelden, ausgelöst durch:
  - Erfolgreicher Anmeldevorgang.
  - Erste Anmeldung erfolgreich.
  - Anmeldefehler werden einem Benutzer angezeigt.
  - Erfassen der Telemetrie über MAM/MDM-Richtlinien, die beim erstmaligen Anmelden implementiert wurden.
  - Aufzeichnen der Referrer-Parameter der Anwendungsinstallation nach der ersten erfolgreichen Anmeldung.
- **fitToFrameVideo**: An Rahmen aus Aktionstabelle anpassen.
- **flipCamera**: Kamera kippen.
- **forcedUpdateAccept**: Ein Benutzer akzeptiert, dass die App-Version im Dialogfeld „Aktualisierung erzwingen“ aktualisiert wird.
- **forcedUpdateExit**: Ein Benutzer schließt die App, anstatt die App-Version im Dialogfeld „Aktualisierung erzwingen“ zu aktualisieren.
- **forcedUpdatePrompt**: Wird in Situationen verwendet, in denen Benutzer mit älteren Versionen, die möglicherweise nicht die neuesten Sicherheits- und Datenschutzfixes aufweisen, erreicht werden müssen.
- **formattingBold**: Ein Benutzer wählt die Fettformatierung aus.
- **formattingHighlight**: Ein Benutzer wählt die Hervorhebungsformatierung aus.
- **formattingImportant**: Ein Benutzer wählt Wichtigkeit aus.
- **formattingItatlics**: Ein Benutzer wählt kursiv aus.
- **formattingTextColor**: Ein Benutzer wählt die Textfarbenformatierung aus.
- **formattingUnderline**: Ein Benutzer wählt Unterstreichen aus.
- **FRE - No AS Assigned**: Erfassen der Telemetrie über MAM/MDM-Richtlinien beim App-Start. Telemetrie für die Intune-Integration für MAM und MDM. Liefert Erfolgsdaten zu Fehlern während der FRE (First-run experience).
- **freActionClicked** - **Erste Schritte**, **Später versuchen** oder **Schließen** (GPS) wird in der FRE (First-run experience) ausgewählt.
- **freDone**: Die FRE (First-run experience) wurde abgeschlossen.
- **freTriggered**: Ein Benutzer zeigt die Stechuhr bei der FRE (First-run experience) an.
- **funSearchQueryEntered**: Giphy-Abfrage eingegeben. Erfolgsdaten für das Giphy-Anlagen-Feature in Teams.
- **funSelectItem**: Giphy-Bild ausgewählt. Erfolgsdaten für das Giphy-Anlagen-Feature in Teams.
- **galleryImage**: Bild hochgeladen – Gallerie.
- **get_directions_clicked**: Die Schaltfläche **Wegbeschreibung abrufen** wird ausgewählt.
- **goToNotificationSettings**: Wechseln Sie zur Seite „Benachrichtigungseinstellungen“ von dem Dialogfeld **Nachrichteneinstellungen wurden aktualisiert**.
- **GPSPromptClicked**: In einer Aufforderung des Betriebssystems wird **Zulassen** oder **Nicht zulassen** ausgewählt. Entweder GPS erlauben oder nicht.
- **group_map_closed**: Ein Benutzer öffnet die Kartenansicht aus dem Chat.
- **group_map_open**: Ein Benutzer schließt die Kartenansicht.
- **groupCallJoin**: Ein Benutzer tritt einem Gruppenanruf bei.
- **groupClicked**: Verfolgt, wenn ein Benutzer die Schichtgruppe auswählt.
- **guideMe**: Benutzer wählen ein Banner aus, das Sie über eine Blockierungsbenachrichtigung einer 3P-App informiert und Anleitungen zur Problembehandlung bietet.
- **hamburgerMenu**: Navigieren Sie zum Hamburger-Menü. Das Hamburger-Menü enthält wichtige Aktionen, wie z. B. Kontowechsel, Benachrichtigungseinstellungen, Dateneinstellung und Profileinstellungen.
- **handoffComplete**: Auf diesem Gerät wurde eine Besprechung oder ein Anruf abgegeben.
- **handoffJoin**: Auf der Aktionstabelle wird eine Besprechungsübergabe-Option ausgewählt.
- **hardwareAudioOff**: Deaktivieren Sie Audio durch die Hardware-Schaltflächen.
- **hardwareAudioOn**: Aktivieren Sie Audio durch die Hardware-Schaltflächen.
- **hide**: Chat ausblenden.
- **hideChannel**: Einen Kanal aus der Teams- und Kanalliste ausblenden.
- **image**: Bild.
- **immediateCallForward**: Ziel für die sofortige Anrufweiterleitung ist festgelegt, oder es wird die sofortige Anrufweiterleitung aktiviert („Anrufe bei mir klingeln lassen“ ist deaktiviert).
- **importanceToggleClicked**: Wird ausgelöst, wenn das Feld **!** in den Aufgabenelement-Details umgeschaltet wird.
- **importantMessage_select**: Ein Benutzer wählt eine wichtige Nachricht aus dem Prioritäten-Kontextmenü aus.
- **importantMessageSend**: Ein Benutzer sendet eine wichtige Nachricht.
- **inCallDialOut**: Ein Benutzer wählt die Schaltfläche **Rückruf** aus den weiteren Optionen im Anruf aus.
- **initiatePhotoShare**: Fotofreigabe initiieren.
- **initiateVideoShare**: Videofreigabe initiieren.
- **install**: Installieren oder Ereignis installieren.
- **installReferrer**: Aufzeichnen der Referrer-Parameter der Anwendungsinstallation nach der ersten Installation.
- **invisionWhiteboardClicked**: InVision-Whiteboard wird ausgewählt:
  - Die Registerkarte **Kanaldateien**.
  - Die Besprechungsregisterkarte **Chatdateien**.
- **inviteFreemium**: Tippen auf die Schaltfläche **+** im Einladen-Bildschirm.
- **inviteGuest**: Tippen auf die Schaltfläche **+** im Einladen-Bildschirm.
- **joinFromDeeplinkInTeams**: Ein Benutzer ist über einen Deeplink in der Teams-App beigetreten.
- **joinFromDeeplinkOutsideTeams**: Ein Benutzer ist über einen Deeplink von außerhalb der Teams-App beigetreten.
- **joinFromJoinLauncher**: Ein Benutzer ist von einem Beitritts-Launcher aus beigetreten.
- **joinFromNudge**: Ein Benutzer ist vom Anstupser aus beigetreten.
- **joinFromStore**: Ein Benutzer ist nach dem Herunterladen der App aus dem App Store beigetreten.
- **joinMeeting**: Erkennt den Erfolg oder Misserfolg des Beitritts von Besprechungen aus dem Kalender in den folgenden Situationen:
  - An der Besprechung durch Einwählen teilnehmen.
  - An der Besprechung durch Rückruf teilnehmen.
  - Nur an Besprechungsinhalten teilnehmen.
  - Die Schaltfläche **Besprechungsteilnahme** aus der Agendaansicht auswählen.
- **joinOptionsEdu**: Ein EDU-Benutzer wählt Optionen aus, um an einer geplanten Besprechung teilzunehmen, und es werden die richtigen Optionen angezeigt.
- **joinTeam**: Die Schaltfläche **Beitreten** wird gedrückt.
- **joinViaCode**: Ein Benutzer tritt einer Besprechung über einen Code bei.
- **labelPickerClicked**: Bestätigt, dass die Bezeichnungsauswahl erfolgreich gestartet wurde.
- **labelSelected**: Bestätigt, dass eine Bezeichnung erfolgreich ausgewählt wurde.
- **labelUnselected**: Bestätigt, dass die Auswahl einer Bezeichnung erfolgreich aufgehoben wurde.
- **launchLinksGallery**: Wenn ein Benutzer über das Dashboard den Linkkatalog betritt.
- **Launch source such as direct, link, appShortcut**: Startet direkt oder per Link (Aufzeichnung von Mobiler Anwendungsverwaltung (MAM) oder Mobiler Geräteverwaltung (MDM) Telemetrie beim Start der Anwendung, um Daten für aktive Benutzer zu sammeln).
- **leaveChat**: Bestätigung des Verlassens des Chats.
- **legacyChatLink**: Ein Link wird für einen älteren Chat ausgewählt.
- **likeAppDismiss**: Wenn die Eingabeaufforderung, die fragt, ob ein Benutzer die App mag oder nicht, ohne Antwort zurückgewiesen wird.
- **likeAppNo**: Wenn die Eingabeaufforderung, die fragt, ob Benutzer die App mag, die Antwort „Nein“ erhält.
- **likeAppYes**: Wenn die Eingabeaufforderung, die fragt, ob Benutzer die App mag, die Antwort „Ja“ erhält.
- **likeMsg**: Wählen Sie **Gefällt mir** aus.
- **linkPreviewCancel**: Grundlegendes zum Verhalten beim Schließen der Vorschau.
- **listUserClicked**: Wenn ein Benutzer einen Benutzer in „Arbeitet jetzt“ auswählt.
- **liveCaptions**: Live-Untertitel werden aktiviert bzw. deaktiviert.
- **liveEventAdditonalLink**: Es wird ein zusätzlicher Link ausgewählt.
- **liveEventInfo**: Die Schaltfläche **Informationen** ist ausgewählt.
- **liveEventJoin**: Ein Benutzer tritt einem Lve-Ereignis bei.
- **liveEventLeave**: Die Schaltfläche **Verlassen** wird gedrückt.
- **liveEventPresenterJoin**: Ein Referent tritt einem Liveereignis bei.
- **liveEventPresenterJoinAsAttendee**: Ein Live-Event-Referent ist als Teilnehmer beigetreten.
- **liveEventQnA**: Das Symbol **Q&A** ist ausgewählt.
- **liveEventYammer**: Das Symbol **Yammer** ist ausgewählt.
- **liveMeetingPushNotificationClicked**: Pushbenachrichtigung ist ausgewählt.
- **liveMeetingToastClicked**: Toast in einer App ist ausgewählt.
- **live_location_in_chats_from_profile_clicked** - **Live-Standorte** ist in der Profildarstellung ausgewählt.
- **lobbyPickAudio**: Anzahl der Male, die ein Benutzer die Audioausgabe vom Wartebereich aus umschaltet.
- **lobbyToggleMuted**: Anzahl der Male, die ein Benutzer aus dem Wartebereich das Mikrofon ein- oder ausgeschaltet hat.
- **lobbyToggleVideo**: Anzahl der Male, die ein Benutzer aus dem Wartebereich das Video ein- oder ausgeschaltet hat.
- **logOutClicked**: Wenn sich ein Benutzer abmeldet.
- **location_active_tracking**: Das Gerät eines Benutzers wird in „aktive Nachverfolgung“ umgeschaltet.
- **locationCard**: Wählen Sie eine Standortkarte aus.
- **location_family_sync**: Anzeigen von Mitgliedern einer Familiengruppe, die in der MSA-Familien-App erstellt wurden. Bestätigt, dass alle Familienmitglieder angezeigt werden, denen die Zustimmung erteilt werden kann.
- **location_group_map_sync**: Kartenansicht wird geöffnet.
- **location_map_load**: Laden der Kartenansicht.
- **location_map_markers_load**: Kartenansicht laden. Bestätigt, dass die Standortmarkierungen für alle aktiv teilenden Benutzer in der Kartenansicht richtig angezeigt werden.
- **location_message_send**: Ein Benutzer initiiert eine Sitzung zur Standortübermittlung.
- **location_data_use_privacy_denied**: In einem Popup, das die Verwendung von Standortdaten durch TFL erklärt, weist ein Benutzer die Option **Nicht jetzt** ab oder wählt sie aus.
- **location_data_use_privacy_granted**: In dem Popup, das die Verwendung von Standortdaten durch TFL erklärt, wählt ein Benutzer **Zulassen** aus.
- **location_settings_open**: Ein Benutzer öffnet die Standorteinstellungen.
- **location_sharing_start**: Ein Benutzer gibt seinen Live-Standort in einem Chat frei.
- **location_sharing_stop**: Ein Benutzer beended die Freigabe seines Live-Standorts in einem Chat.
- **LoginFailed**: Benutzer konnte sich nicht anmelden.
- **loginSuccess**: Benutzer konnte sich anmelden.
- **manageBlockedNumbers**: Zugriff zu blockierten Nummer über Einstellungen.
- **manualSendMessage**: Eine Nachricht wird manuell versendet.
- **mapAppPicker**: Wenn ein Benutzer die zu verwendende Mapping-App auswählt, indem er auf eine Standortkarte tippt.
- **markAsRead**: Als gelesen markieren.
- **markAsUnread**: Als ungelesen markieren.
- **markChannelRead**: Ein Benutzer markiert einen Kanal als gelesenen.
- **messageBookmarkMessage**: Speichern der Connectorkarte. Verwenden vorhandene Telemetrie mit App-spezifischen Daten. Oder Speichern einer Bot-Nachricht.
- **markAsLastUnread**: Kontextmenü der Connectorkarte.
- **maskCallerId**: Ein Benutzer aktiviert bzw. deaktiviert die Anrufeinstellung zur Maskierung der Anrufer-ID.
- **meetingDetailCalendarList**: Besprechungsdetailsseite, die von calenderList ausgewählt ist, oder Auswählen der Registerkarte **Details** auf der Besprechungsdetailsseite.
- **meetingDetailChatWithParticipants**: Chatten Sie mit Teilnehmern über die Besprechungsdetailsseite.
- **meetingDetailDeleteMeetingforSelf**: Löschen Sie eine Besprechung von der Besprechungsdetailseite für sich selbst.
- **meetingDetailJoin**: Die Schaltfläche **Besprechungsteilnahme** wird auf der Besprechungsdetailseite ausgewählt.
- **meetingDetailParticipants**: Zeigen Sie alle Teilnehmern über die Besprechungsdetails-Seite an.
- **meetingDetailScheduledMeeting**: Besprechungsdetailseite, ausgewählt vom Objekt „Geplantes Meeting“ (**...**), oder wählen Sie die Registerkarte **Details** einer geplanten Besprechung aus.
- **meetingDetailSearchParticipants**: **Suchen** in Besprechungsteilnehmern auf dem Besprechungszeitplan ausgewählt.
- **meetingJoinLeave**: Verlassen angetippt -> **x** wird angetippt, nachdem die Schaltfläche **Beitreten** angetippt wird.
- **meetingJoinNow** - **Für VoIP beitreten** ausgewählt.
- **meetingJoinNowWithCallMe**: Ein Benutzer tritt einer Besprechung mit **Rückruf** bei.
- **meetingJoinNowWithPSTN**: Ein Benutzer tritt einer Besprechung mit Einwählen bei.
- **meetingLeaveChat**: Chat verlassen.
- **meetingMuteChat**: Chat stumm schalten.
- **meetingNotesCreatedInChatLink**: Das Chicklet **Besprechungsnotizen erstellt** wird im privaten Besprechungschat oder im Kanal-Besprechungschat ausgewählt.
- **meetingNotesMentionCharLink**: Der Link @erwähnen ist im privaten Besprechungschat ausgewählt.
- **meetingNotesMentionChatLink**: Der Link @erwähnen ist im Kanal-Besprechungschat ausgewählt.
- **meetingNotesTabEntryPoint**: Die Registerkarte **Besprechungsnotizen** ist in einer privaten Besprechung oder in einem Kanal ausgewählt.
- **meetingNotificationSettingsAccepted**: Die Option Benachrichtigungseinstellungen wurde zu „nur akzeptierte“ geändert.
- **meetingNotificationSettingsAll**: Die Option Benachrichtigungseinstellungen wurde zu „Alle“ geändert.
- **meetingNotificationSettingsNone**: Die Option Benachrichtigungseinstellungen wurde zu „Keine“ geändert.
- **messagePriority_select**: Ein Einstiegspunkt für die Nachrichtenpriorität ist ausgewählt.
- **messageSeeOriginal**: Ein Benutzer kehrt die übersetzte Nachricht wieder zum Original zurück.
- **meetingSeeParticipantsChatDetails**: Alle Teilnehmer anzeigen.
- **memberListLoadMore**: Scrollen Sie nach unten, um mehr zu laden.
- **messagedEditMessage**: Ein Benutzer bearbeitet eine Nachricht.
- **messageShareMessage**: Eine Nachricht teilen.
- **messageTranslate**: Ein Benutzer übersetzt eine Nachricht.
- **messageUnabletoEdit**: Ein Benutzer kann eine Nachricht nicht bearbeiten.
- **meetingUserAnonB2B**: Anonymer B2B ist der Besprechung beigetreten.
- **meetingUserAnonB2C**: Anonymer B2C ist der Besprechung beigetreten.
- **meetingUserDialIn**: PSTN (Einwahl)-Benutzer ist der Besprechung beigetreten.
- **meetingUserDialOut**: PSTN-Rückruf-Benutzer ist der Besprechung beigetreten.
- **meetingUserFederated**: Ein Verbundbenutzer ist der Besprechung beigetreten.
- **meetingUserFreemium**: Ein Freemium-Benutzer ist der Besprechung beigetreten.
- **meetingUserGuest**: Ein Gastbenutzer ist der Besprechung beigetreten.
- **meetingUserTenant**: Ein In-Mandanten-Benutzer ist der Besprechung beigetreten.
- **messageCopyMessage**: Nachricht kopieren.
- **messageDelete**: Nachricht löschen.
- **messageEditMessage**: Nachricht bearbeiten.
- **messageForwardMessage**: Ein Benutzer wählt einen Weiterleitungseinstiegspunkt aus dem Nachrichtenkontextmenü aus.
- **messageLike/messageUnlike**: Nachricht liken oder Like entfernen.
- **messageMuteSender**: Absender stumm schalten oder Stummschaltung aufheben.
- **messageLike**: Liken der Connectorkarte. Verwenden vorhandene Telemetrie mit App-spezifischen Daten.
- **messageScheduledMeeting**: Besprechungsobjekt im Kanal ausgewählt (nicht nur geplante).
- **messageTriggered**: Dies ist der Zeitpunkt, zu dem eine Benachrichtigung für eine Nachricht ausgelöst wird.
- **micPermissionCancel** - Im Dialogfeld „Mikrofonberechtigung“ ist **Abbrechen** ausgewählt.
- **micPermissionGoToSettings**: Ein Benutzer navigiert zu „Einstellungen“ im Dialogfeld Mikrofonberechtigungen.
- **MicrosoftWhiteboardClicked**: Microsoft Whiteboard ist auf der Registerkarte **Kanaldateien** oder auf der Registerkarte **Besprechungschat-Dateien** ausgewählt.
- **moreOptionsClicked**: Wird ausgelöst, wenn das Menü **...** oben rechts auf dem Aufgabenelement-Editorbildschirm ausgewählt ist.
- **moveTaskClicked**: Option innerhalb des Aufgabenelements Weitere Optionen-Liste.
- **multiCallEndFromUFD**: Häufigkeit, mit der ein Benutzer den Anruf in einer Situation mit mehreren Anrufen beendet.
- **multiCallResumeFromUFD**: Anzahl der Male, in denen ein Benutzer wählt, einen Anruf aus der Warteschleife wieder aufzunehmen.
- **multiCallSwitch**: Anzahl der Male, in denen ein Benutzer eine Option zum Umschalten des Anrufs auswählt, und eine Liste der gehaltenen Anrufe wird angezeigt.
- **multipleAccounts**: Anzahl der Konten für einen Benutzer.
- **multipleTenants**: Anzahl der Mandanten pro Konto.
- **mute**: Chat stumm schalten.
- **muteOnWhiteboard**: Ein Benutzer schaltet die Stummschaltung auf dem Whiteboard-Bildschirm ein oder aus.
- **muteParticipant**: Teilnehmer stumm schalten (zur Aktionstabelle verschieben).
- **my_location_button_clicked**: Benutzer zentriert die Karte an deren Position, indem er die Schaltfläche **Mein Standort** auswählt.
- **my_location_clicked**: Ein Benutzer zentriert die Karte an deren Position, indem er den **blauen Punkt** auf der Karte auswählt.
- **myShiftPickerClicked**: Wird nur protokolliert, wenn die gesendete Anforderung ein Tausch oder ein Angebot ist. **Meine Schicht** ist ausgewählt.
- **nameGroupChat**: Name Gruppenchat.
- **nativeTimeClockBreak**: Eine Pause auf der Stechuhr.
- **nativeChatLink**: Ein Link zum systemeigenen Chat ist ausgewählt.
- **navActivity**: Navigieren Sie zur Seite „Aktivitätsfeeds“.

- **navBookmark**: Ein Benutzer navigiert zur Registerkarte **Gespeichert** oder zur App auf der unteren Leiste oder zur App-Leiste.
- **navCalendar**: Misst, ob ein Benutzer zu einem Kalender navigiert.
- **navCallingSettings**: Ein Benutzer navigiert zu den Anrufeinstellungen.
- **navCalls** - Registerkarte **Anrufe** angetippt.
- **navCamera**: Ein Benutzer navigiert zur Registerkarte **Kamera** oder zur App auf der unteren Leiste oder zur App-Leiste.
- **navChat**: Ein Benutzer navigiert zur Registerkarte **Chat** oder zur App auf der unteren Leiste oder zur App-Leiste.
- **navContacts**: Ein Benutzer navigiert zur Registerkarte **Kontakte** oder **Personen** oder zur App auf der unteren Leiste oder zur App-Leiste.
- **navDashboardTab**: Ein Benutzer navigiert innerhalb einer Unterhaltung zur Registerkarte **Dashboard**.
- **navDynamics365**: Wird ausgelöst, wenn die Dynamics365-App geöffnet wird.
- **navFiles**: Dateien-App ist ausgewählt, verfolgt, ob ein Benutzer die Dateien-App in der App-Leiste (iOS) starten kann.
- **navFilesTab**: Dateien-App ist ausgewählt, verfolgt, ob ein Benutzer die Dateien-App in der unteren Navigationsleiste (iOS) starten kann.
- **navMeetings** - Registerkarte **Kalender** angetippt.
- **navNotes**: Wird ausgelöst, wenn die Notizen-App geöffnet wird.
- **navOrganization**: Wird ausgelöst, wenn die Organisations-App geöffnet wird.
- **navOrgChart**: Wird ausgelöst, wenn die Organigramm-App geöffnet wird.
- **navPeople**: Ereignis wird ausgelöst, wenn die Personen-App geöffnet wird.
- **navPeopleSettings** Wird ausgelöst, wenn Sie im Einstellungsmenü zur Kategorie **Personen** navigieren.
- **navPersonalFiles**: Dateien-App ist ausgewählt, verfolgt, ob ein Benutzer die Dateien-App in der unteren Navigationsleiste (Android) starten kann.
- **navPhotoTab** - Registerkarte **Foto**.
- **navSaved**: Ein Benutzer navigiert zur Registerkarte **Gespeichert** oder zur App auf der unteren Leiste oder zur App-Leiste.
- **navSelectPlan**: Wenn ein Benutzer einen freigegebenen Plan zur Navigation von der Startseite aus auswählt.
- **navSelectPersonalList**: Wenn ein Benutzer einen persönlichen Plan zur Navigation von der Startseite aus auswählt.
- **navSelectSmartList**: Wenn ein Benutzer einen intelligenten Plan zur Navigation von der Startseite aus auswählt.
- **navTasks**: Wird ausgelöst, wenn die Aufgaben-App geöffnet wird.
- **navTeams**: Tippen Sie auf **Alle anzeigen**.
- **navVideocamera**: Ein Benutzer navigiert zur Registerkarte **Kamera** oder zur App auf der unteren Leiste oder zur App-Leiste.
- **navVideoTab** - Registerkarte **Video**.
- **navVoicemail**: Ein Benutzer navigiert zur Voicemailseite.
- **navWalkieTalkie**: Ein Benutzer hat die Walkie Talkie-App geöffnet.
- **navWiki**: Wird ausgelöst, wenn die Wiki-App geöffnet wird.
- **newChat**: Ein Benutzer erstellt einen Chat.
- **newCall**: Tippen auf Schaltfläche **Neuer Anruf**.
- **newCallDialPad**: Tippen auf die Schaltfläche **Wähltastatur** auf der Registerkarte.
- **newCallPeople**: Tippen auf die Schaltfläche **Personen** auf der Registerkarte.
- **noBGActivityDetected**: Überschreitet den Schwellenwert für Fehler bei Hintergrundaktivitäten.
- **notBlockedDevice**: Ein Benutzer erreicht nicht den Schwellenwert für Fehler bei Hintergrundaktivitäten innerhalb von 30 Tagen.
- **notNow** - **Nicht jetzt** wird bei der Erinnerung ausgewählt.
- **notNowUpdate**: UpdateDefer.
- **notificationNavChannelConversation**: Starten Sie die App mit einer Benachrichtigung für eine Kanalunterhaltung.
- **notificationNavChannelThreadConversation**: Starten Sie die App mit einer Benachrichtigung für eine spezifische Nachricht in einer Kanalunterhaltung.
- **notificationSettingTurnedOff**: Pushbenachrichtigungen für die Teams-Android-App deaktivieren.
- **notificationNavPreCall**: Ein Benutzer erhält eine Benachrichtigung über den Beginn einer Besprechung, die ihn bei der Auswahl zum Vorabrufbildschirm navigiert.
- **ocvFeedback**: Bezogen auf die Leistung des OCV-Antwortformulars.
- **ocvFormCancelled**: Ein Ereignis, das gesendet wird, wenn das OCV-Antwortformular abgebrochen wird und der Benutzer zur App zurückkehrt.
- **ocvFormOpened**: Ein Ereignis, das gesendet wird, wenn das OCV-Formular geöffnet wird.
- **ocvFormSubmit**: Ein Ereignis, das gesendet wird, wenn der Benutzer auf dem OCV-Antwortformular auf Senden klickt.
- **offerRecipientClicked**: Wird nur protokolliert, wenn die gesendete Anforderung ein Angebot ist. Der Benutzer gibt die Teammitglied-Auswahl ein, um eine Schicht anzubieten. Anbieten bedeutet, eine Schichtzeit freizugeben.
- **offerSwapShiftFromL1**: Die Art der Schicht, die ein Benutzer aus einer Schichtliste anzubieten oder zu tauschen versucht. iOS-Aktion ist ein **SwipedRight** und Android-Aktion ein **LongPressed**.
- **offerSwapShiftFromL1Triggered**: Ein Benutzer bietet an, eine Schicht mit einem anderen Benutzer zu tauschen.
- **officeLens**: Wird ausgelöst, wenn die App das officeLens-Kamerafeature in folgenden Fällen startet:
  - Ein Benutzer versucht, ein Foto an seine Nachricht anzuhängen.
  - Ein Benutzer versucht, ein Foto aufzunehmen und direkt in den Katalog hochzuladen.
- **officeLens or cameraImage**: Kamerabild ausgewählt – Standardkamera oder Office Lens.
- **onBackClicked**: Immer, wenn der Zurück-Pfeil ausgewählt ist, um eine Seite zurückzugehen.
- **OneNote**: Wenn ein Benutzer die OneNote-App öffnet.
- **open**: Tippen auf Benachrichtigungseinstellungen.
- **open edit**: Telemetrie der Wiki-Nutzung – Benutzer wählt aus, das Wiki zu bearbeiten.
- **openApp**: Öffnen einer persönlichen App.
- **openAppDrawer** - **Mehr** ist auf der unteren Leiste ausgewählt, um den Domänenadministrator zu öffnen.
- **openEditMeetingForm**: Die Schaltfläche **Bearbeiten** wird auf der Besprechungsdetailseite ausgewählt.
- **OpenFile**: Hilft in folgenden Fällen:
  - Um zu identifizieren, dass eine Datei im Chat erfolgreich geöffnet werden konnte.
  - Um zu identifizieren, dass eine Datei aus einer Dateiliste erfolgreich geöffnet werden konnte.
  - Um zu überprüfen, ob Dateien aus einer OneDrive-Liste geöffnet werden können.
  - Um zu identifizieren, dass geöffnete Dateien aus einer Kanalliste geöffnet werden können.
  - Um zu ermitteln, ob Dateien aus Gruppenchats geöffnet werden können.
  - Um zu ermitteln, ob eine Datei aus der Datei-App erfolgreich geöffnet werden kann.
  - Um zu ermitteln, ob eine Nachrichtendatei aus dem Chicklet erfolgreich geöffnet werden kann.
  - Um zu ermitteln, ob Dateien aus der Liste „Zuletzt verwendet“ erfolgreich geöffnet werden können.
  - Um zu ermitteln, ob eine Datei aus der Dateiliste erfolgreich geöffnet werden kann.
  - Um zu ermitteln, ob eine Datei aus einem Nachrichtendatei-Chicklet geöffnet werden kann.
  - Um zu ermitteln, ob Dateien erfolgreich aus einer Dateiliste geöffnet werden können.
- **openInAppClicked**: Option innerhalb des Aufgaben-Elements „Weitere Optionen“-Liste, nur für persönliche Aufgaben verfügbar.
- **opensCalendarView**: Tippen auf **Schichten öffnen** auf der Registerkarte **Zeitplan**.
- **openContactCard** – ein Benutzer tippt auf ein **Kontakt**-Symbol oder einen Kontakt in der Personen-App, um die Profilkarte dieses Kontakts zu starten.
- **openContactCard_ReactionSummary**: Navigieren Sie auf der Seite „Reaktionszusammenfassung“ zur Visitenkarte.
- **openFileInApp**: Hilft bei der Identifizierung, ob sich der Benutzer für das Öffnen von Dateien außerhalb von Teams gegenüber innerhalb von Teams entschieden hat.
- **openHamburgerMenu**: Das **Hamburger**-Symbol (oben links) wird ausgewählt, um das Seitenmenü für den Zugriff auf Einstellungen, Anwesenheitsstatus und Mandantenwechsler zu öffnen.
- **openInStream**: Öffnen Sie ein Video in Stream.
- **openMeetingDetails**: Öffnen Sie die Besprechungsdetails oder die Seite „Besprechungsdetails öffnen“ einer bestimmten Besprechung.
- **openModalityPicker**: X = ChatsAndChannels für Chats und Kanäle.
- **openNewMeetingForm**: Bestätigt, dass eine persönliche Teilaufgabe erfolgreich aktualisiert wurde.
- **openNewMeetingForm**: Öffnen Sie den Planer, während Sie eine neue Besprechung einrichten.
- **openPhotoLibrary**: Wählen Sie eine Fotobibliothek aus.
- **openQuietDays**: Navigieren Sie zu der Seite „Ruhige Tage“.
- **openQuietHours**: Naavigieren Sie zu der Seite „Ruhige Stunden“.
- **openReactionHoverBubble**: Drücken Sie auf der Seite Reaktionszusammenfassung die Schaltfläche **Reaktion hinzufügen**.
- **openReactionSummary**: Schublade „Reaktionszusammenfassung“ aufrufen.
- **openSettingsSetUpInstructions**: Öffnen Sie die **Einstellungen** von den Anweisungen aus.
- **openSharedLink**: Wenn ein Benutzer einen Link über die Kachel Dashboard-Links oder den Links-Katalog öffnet.
- **openShiftsClicked**: Wie viele Personen das Symbol **Kalender** antippen.
- **Organigramm-Nein als zugeordnet**: Grundlegende Nutzung der Telemetrie für das Organigramm.
- **pageEntered**: Ein Benutzer hat eine Seite eingegeben.
- **parental_consent_grant**: Ein Benutzer gewährt einem Minderjährigen in seiner MS-Familie die Berechtigung zum Verwenden der Funktion „Live-Standort“ in TFL.
- **parental_consent_grant**: Ein Benutzer gewährt einem Minderjährigen in seiner MS-Familie die Berechtigung zum Verwenden der Funktion „Live-Standort“ in TVL.
- **pauseVoicemail** - **Anhalten** wird auf einem Voicemail-Element angetippt.
- **peoplePickerInvoked**: Personenauswahl wird an sieben Stellen in Teams Mobile verwendet, einschließlich (aber nicht beschränkt auf):
  - Neue Chatauswahl.
  - Weiterleiten einer Nachricht.
  - Hinzufügen eines Teilnehmers zu einer Besprechung.
- **personalAppNavBotChat**: Navigieren Sie mit der persönlichen App zum Bot.
- **personalAppNavTab**: Navigieren Sie mit der persönlichen App zu Registerkarten.
- **photoLibraryPicker** - **Fotobibliothek öffnen** wird in der Bildauswahl angetippt.
- **pickGalleryPhoto**: Wählen Sie ein Foto aus dem Katalog aus.
- **pickParticipantChatDetails**: Wählen Sie einen Benutzer aus der Liste aus.
- **pickRecentPhoto**: Wählt ein zuletzt verwendetes Bild für die Freigabe aus.
- **pinChannel**: Heften Sie einen Kanal an, um ihn oberhalb der Liste „Teams und Kanäle“ anzuzeigen.
- **pinSelf**: Mich selbst aus der Aktionstabelle anheften.
- **pinuser**: Einen Benutzer aus der Aktionstabelle anheften.
- **play**: Die Aufzeichnung abspielen.
- **playVoicemail** - **Wiedergabe** wird auf dem Voicemail-Element angetippt.
- **plusButtonClicked**: Auswählen der **Plus-Schaltfläche** (**+**).
- **pptNextSlide**: Nächste Folie als Referent oder in der privaten Anzeige.
- **pptPreviousSlide**: Vorherige Folie als Referent oder in der privaten Anzeige.
- **pptReturnToPresenter**: Wechseln Sie zur Folie **Live** (die Folie, auf der sich der Referent und alle anderen Personen befinden).
- **pptStopPresenting**: Präsentation beenden.
- **pptTakeControl**: Kontrolle übernehmen.
- **preJoinAddRoom**: Die Schaltfläche **Raum hinzufügen** ist im Dropdownmenü vor der Teilnahme ausgewählt, **Beitreten** ist im Szenario **Raum hinzufügen** ausgewählt.
- **preJoinAudioOff**: Die Schaltfläche **Audio aus** ist im Dropdownmenü vor der Teilnahme ausgewählt.
- **preJoinAutoAddRoom** - **Jetzt beitreten** wird ausgewählt, wenn sich ein Raum in der Nähe befindet.
- **preJoinBack** - Die Schaltfläche **Zurück** oder **Schließen** ist ausgewählt.
- **preJoinDenied**: Ein Benutzer kann an einer Besprechung nicht teilnehmen.
- **preJoinDeviceAudio** - **Mit Geräteaudio teilnehmen** wird aus der Dropdownliste ausgewählt.
- **preJoinDialIn**: Die Schaltfläche **Einwählen** ist im Dropdownmenü vor der Teilnahme ausgewählt.
- **preJoinDialInCall**: Ein Benutzer bestätigt die Anforderung **Einwählen** vor der Teilnahme.
- **preJoinDialInCancel**: Ein Benutzer bricht die Anforderung **Einwählen** vor der Teilnahme ab.
- **preJoinDialOut**: Die Schaltfläche **Rückruf** ist im Dropdownmenü vor der Teilnahme ausgewählt.
- **preJoinDialOutCall**: Ein Benutzer bestätigt die Anforderung **Rückruf** vor der Teilnahme.
- **preJoinDialOutCancel**: Ein Benutzer bricht die Anforderung **Rückruf** vor der Teilnahme ab.
- **preJoinPSTNOptions**: Ein Benutzer wählt ein Dropdown für andere Beitrittsoptionen aus.
- **priorityChange**: Wird ausgelöst, wenn der Prioritätsfilter beim Anzeigen einer Taskliste angewendet wird.
- **priorityPickerClicked**: Wird ausgelöst, wenn ein Benutzer vom Filterbildschirm der Aufgabenliste zu einer Prioritätsfilter-Auswahl navigiert.
- **privateMeetingJoin** - Die Schaltfläche **Besprechungsbeitritt** wird aus dem privaten Besprechungschat angetippt.
- **processInBG**: Verarbeitung einer eingehenden Benachrichtigung im Hintergrund (Android).
- **processInFG**: Verarbeitung einer eingehenden Benachrichtigung im Vordergrund (Android).
- **progressItemClicked**: Bestätigt, dass ein Benutzer die Statusauswahl für eine Aufgabe erfolgreich geöffnet hat.
- **promotedToPresenter**: Der Benutzer stuft einer Teilnehmer höher – Schaltfläche **Ändern** im Dialogfeld.
- **provideFeedbackDismiss**: Schließen der Eingabeaufforderung, in der gefragt wird, ob der Benutzer Feedback dazu senden möchte, warum ihm die App nicht gefallen hat.
- **provideFeedbackNo**: Eingabeaufforderung, in der gefragt wird, ob der Benutzer Feedback dazu senden möchte, warum ihm die App nicht gefallen hat, wird mit „Nein“ beantwortet.
- **provideFeedbackYes**: Eingabeaufforderung, in der gefragt wird, ob der Benutzer Feedback dazu senden möchte, warum ihm die App nicht gefallen hat, wird mit „Ja“ beantwortet.
- **provideRatingDismiss**: Schließen der Eingabeaufforderung, in der der Benutzer gefragt wird, ob er uns im App Store bewerten möchte, nachdem er gesagt hat, dass ihm die App gefällt.
- **provideRatingNo**: Antworten mit „Nein“ auf die Eingabeaufforderung, in der der Benutzer gefragt wird, ob er uns im App Store bewerten möchte, nachdem er gesagt hat, dass ihm die App gefällt.
- **provideRatingYes**: Antworten mit „Ja“ auf die Eingabeaufforderung, in der der Benutzer gefragt wird, ob er uns im App Store bewerten möchte, nachdem er gesagt hat, dass ihm die App gefällt.
- **proximityPermissionDismissed**: Berechtigungsbanner wird geschlossen.
- **proximityPermissionGranted**: Berechtigung im Popup wird gegeben.
- **proximityPermissionViewed**: Berechtigungsbanner wird angetippt.
- **pushNotification**: Auslösende Ereignisse sind:
  - Starten über die Benachrichtigung.
  - Pushbenachrichtigung ausgewählt.
  - Die erneute Verbindung mit der Pushbenachrichtigung wird angetippt.
  - **Reconnect failed**: Pushbenachrichtigung wird angetippt.
- **quickNotificationAction**: Wenn ein Benutzer mit einer der schnellen Aktionen mit einer Benachrichtigung interagiert (z. B. die Möglichkeit, eine Nachricht direkt von der Pushbenachrichtigung aus mit „Gefällt mir“ zu markieren).
- **quickSelectImagePicker**: Schnellauswahl.
- **quickStartLiveEventJoin**: Ein Benutzer tritt einem Schnellstart-Liveereignis bei.
- **quietHoursValues**: Erfassen des Status „Ruhige Stunden“ bei der Navigation mit der Zurück-Schaltfläche.
- **quotedReplySent**: Ein Benutzer hat eine Antwortnachricht mit dem Kontexttyp gesendet.
- **reactAngry_CM**: Mit „wütend“ aus dem Kontextmenü antworten.
- **reactAngry_HB**: Mit „wütend“ aus der Schwebeblase antworten.
- **reactHeart_CM**: Mit „Herz“ aus dem Kontextmenü antworten.
- **reactHeart_HB**: Mit „Herz“ aus der Schwebeblase antworten.
- **reactLaugh_CM**: Mit „Breites Grinsen“ aus dem Kontextmenü antworten.
- **reactLaugh_HB**: Mit „Breites Grinsen“ aus der Schwebeblase antworten.
- **reactLike_CM**: Mit „Gefällt mir“ aus dem Kontextmenü antworten oder eine Botnachricht liken.
- **reactLike_doubleTap**: Mit „Gefällt mir“ aus dem Doppeltippen antworten.
- **reactLike_HB**: Mit „Gefällt mir“ aus der Schwebeblase antworten.
- **reactSad_CM**: Mit „Traurig“ aus dem Kontextmenü antworten.
- **reactSad_HB**: Mit „Traurig“ aus der Schwebeblase antworten.
- **reactSurprised_CM**: Mit „Überrascht“ aus dem Kontextmenü antworten.
- **reactSurprised_HB**: Mit „Überrascht“ aus der Schwebeblase antworten.
- **reactRemoved_HB**: Wenn ein Benutzer eine Reaktion über die Seite Reaktionszusammenfassung entfernt.
- **readReceipts**: Benutzer hat Feature aktiviert.
- **redeemInvite**: Rückzahlung in der App.
- **refreshCalendarList**: Nach unten ziehen, um die Ansicht der Agenda zu aktualisieren.
- **refreshLinksGallery**: Wenn ein Benutzer nach unten wischt, um den Linkkatalog zu aktualisieren.
- **removeAssignee**: Bestätigt, dass eine zugewiesene Person aus der Ansicht der Zuordnungsauswahl entfernt wird (im Gegensatz zu *assignmentRemoved*, was ausgelöst wird, wenn **x** außerhalb der Ansicht der Zuordnungsauswahl ausgewählt wird).
- **removeMeeting**: Wählen Sie auf der Besprechungsdetailseite einer abgebrochenen Besprechung **Aus Kalender entfernen** aus.
- **removeParticipantFromEditMeeting**: Entfernen Sie einen Teilnehmer nachdem Sie **Besprechung bearbeiten** auf der Besprechungsdetailseite ausgewählt haben.
- **removeParticipantFromNewMeeting**: Entfernen Sie einen Teilnehmer aus der Planerseite, während Sie eine neue Besprechung einrichten.
- **removeReplyObject**: Ein Benutzer hat ein Antwortobjekt aus Verfassen gelöscht.
- **removeUser**: Bestätigt, dass eine zugewiesene Person von der Ansicht der Zuordnungsauswahl aus entfernt wird (im Gegensatz zu *assignmentRemoved*, was ausgelöst wird, wenn **x** außerhalb der Ansicht der Zuordnungsauswahl ausgewählt wird).
- **removeUser_CM**: Wenn ein Benutzer eine Person über die Chat-Teilnehmerliste entfernt.
- **removeUserConfirm**: Ein Benutzer hat das Dialogfeld „Benutzer entfernen“ bestätigt.
- **removeUserContextMenu**: Ein Benutzer hat einen Teilnehmer über das Kontextmenü entfernt.
- **removeUserSwipe**: Ein Benutzer hat einen Teilnehmer durch Wischen entfernt.
- **reorderChannelItem**: Ein Benutzer hat die angehefteten Kanäle neu angeordnet.
- **reportAbuseConfirmation**: Wenn ein Benutzer die Schaltfläche **Fertig** auf dem Bestätigungsbildschirm auswählt.
- **reportAbuseOpen**: Die Anzahl der Male, in denen im Kontextmenü die Schaltfläche **Bedenken melden** aktiviert wird.
- **reportAbuseSend**: Wenn ein Benutzer die Schaltfläche **Bericht** auswählt; die Telemetrie sollte den ausgewählten Berichtstyp aufbewahren.
- **replyChain**: Ausgewählte Schaltfläche **Neue Nachricht** oder Textfeld in der Antwortkette (Thread).
- **replyChannel**: Ausgewählte Schaltfläche **Antworten** in Kanälen.
- **replyNavigation**: Antwortobjekt wurde ausgewählt, um zum Referenzbeitrag zu navigieren.
- **replySendMessage**: Kanalantwort senden.
- **replyViaMsgOptions**: Benutzer beginnt Antwort über das Kontextmenü.
- **replyViaSwipe**: Benutzer beginnt Antwort durch Wischen.
- **requestActedOn**: Wird ausgelöst, wenn ein Manager auf eine offene Schichtanfrage reagiert.
- **requestActionClicked**: Wenn ein Benutzer eine Aktion anfordert, z. B. wenn die Anforderung für eine Schicht ausgewählt wird (entweder durch den Manager eines Mitarbeiters in Service und Produktion oder durch den Mitarbeiter selbst).
- **requestDetailsClicked**: Wenn die Anforderung für eine Schicht ausgewählt wird (entweder durch den Manager eines Mitarbeiters in Service und Produktion oder durch den Mitarbeiter selbst).
- **requestJoinTeam** - Schaltfläche **Anforderung** gedrückt.
- **requestSent**: Protokolliert, ob eine Anforderung gesendet wurde.
- **requestToJoinTeam**: Anforderung, einem Team beizutreten (öffentlich oder privat).
- **requestToJoinTeamError**: Fehler bei einer Beitrittsanforderung.
- **requestTypeClicked**: Ermitteln des Anforderungstyps, den Personen aus der Anforderungsauswahl gewählt haben.
- **resolveIssue** - **Auflösen** wird im Benachrichtigungs-Flyout zur Fehlerbehebung ausgewählt, um zur Blocker-App zu navigieren.
- **responseClicked**: Ein Benutzer wählt eine Antwortseite aus.
- **retryButtonClicked**: Die Schaltfläche **Wiederholen** ist ausgewählt.
- **returnToMessage**: Die Schaltfläche **Zurück** ist aktiviert, um zur Nachricht zurückzukehren.
- **runningLate**: Der Benutzer verspätet sich.
- **safeLink**: Link als sicher bestätigt.
- **saveEditMeeting**: Wählen Sie die Schaltfläche **Speichern** auf der Besprechungsplaner-Seite aus, nachdem eine Besprechung aktualisiert wurde.
- **saveNewMeeting**: Wählen Sie die Schaltfläche **Speichern** auf der Besprechungsplaner-Seite aus. Dies protokolliert erfolgreich gespeicherte Besprechungen und den Prozentsatz der Besprechungen, die aufgrund eines clientseitigen oder Dienstfehlers nicht erstellt werden konnten.
- **savePlanClicked**: Löst aus, dass **Erstellen** im neuen Planersteller von der Standardinitialisierung der App aus ausgewählt wird.
- **scheduledMeetingJoin**: Die Schaltfläche **Besprechungsbeitritt** wird aus dem geplanten Besprechungsobjekt ausgewählt.
- **scrollCalendarList**: Misst Scrolls im Kalender.
- **scrollDatePicker**: Scrollen Sie durch das Kalendersteuerelement für die Datumsauswahl.
- **searchAbandoned**: Ermittelt, ob die Suche abgebrochen wurde.
- **searchCancelled**: Ermitteln, pb:
  - Die Suche erfolgreich war, oder ob der Benutzer die Suche abgebrochen hat.
  - Eine Suchabfrage erfolgreich war.
- **searchContacts**: Aus der Anrufliste suchen.
- **searchIcon**: Ermitteln:
  - Ob die Suche ausgelöst werden kann.
  - Die Quelle eines Suchtriggers.
  - Ob relevante Ergebnisse erfolgreich gefunden wurden.
- **searchInitiated**: Ermmittelt, ob die Suche ausgelöst werden kann, sowie die Quelle des Suchtriggers.
- **searchMeetingParticipants**: Suchen Sie nach Teilnehmern, die im Zeitplan-Formular hinzugefügt werden sollen. Zur Unterscheidung zwischen der Anzahl der erstellten Termine und der Anzahl der erstellten Besprechungen.
- **searchResultsClicked**: Ermittelt:
  - Ob relevante Ergebnisse erfolgreich gefunden werden können.
  - Ob die Suchergebnisse von der Registerkarte „alle“ stammen im Vergleich zu einer einzelnen Domäne.
- **searchTab**: Ermittelt:
  - Domäneninformationen des Suchergebnisses – für Personen, Chats, Nachrichten und Dateien.
  - Ob die Suchergebnisse auf der Registerkarte „alle“ liegen, im Vergleich zu einer einzelnen Domäne.
- **searchTabClicked**: Ermittelt:
  - Domäneninformationen des Suchergebnisses – für Personen, Chats, Nachrichten und Dateien.
  - Ob die relevanten Ergebnisse erfolgreich gefunden wurden.
- **seeAllMeetingParticipants**: Wählen Sie auf der Seite mit den Besprechungsdetails **Alle anzeigen** aus, oder zeigen Sie alle Teilnehmer an. Protokolliert Benutzerdaten über den Kalendertrichter, wobei Details zu Kalendertreffen eine wichtige Rolle spielen. Dies hilft bei der Validierung von Auswahlen für Einwahlen, Teambesprechungen, RSVPs usw.
- **seeMeetingDescription**: Öffnen der Besprechungsdetailseite oder Auswählen von **Weitere Informationen** in der Besprechungsbeschreibung auf der Besprechungsdetailsseite. Daten werden über den Kalendertrichter protokolliert, wobei Details zu Kalendertreffen eine wichtige Rolle spielen. Dies hilft bei der Validierung von Auswahlen für Einwahlen, Teambesprechungen, RSVPs usw.
- **seeRsvpMeetingOptions**: Wählen Sie auf der Besprechungsdetailseite **Organisator benachrichtigen** aus dem RSVP-Popupmenü aus, oder wählen Sie **RSVP** aus.
- **selectActivityType**: Zeichnet Auswahlgesten auf Feedelement auf.
- **selectCalendarDate**: Wählen Sie ein bestimmtes Datum im Kalendersteuerelement für die Datumsauswahl aus.
- **selectDevice**: Auswählen eines bestimmten Geräts in der Anzeige-App.
- **selectGeneralSetting**: Wechseln Sie zu Allgemeine Einstellungen.
- **selection**: Gerätekontakt ausgewählt oder Unternehmenskontakt ausgewählt.
- **selectMeetingChicklet** | Besprechung.
- **selectMeetingRsvpOption**: Wählen Sie die Schaltfläche **RSVP**, um eine Option auszuwählen.
- **selectMeetingRsvpOptions**: Wählen Sie die Schaltfläche **RSVP**, um eine Option auszuwählen.
- **selectPersonalList**: Bestätigt, dass der Benutzer erfolgreich zu einer persönlichen Aufgabenliste navigiert ist, indem er sie antippt.
- **selectPlannerList**: Bestätigt, dass der Benutzer erfolgreich zu einer freigegebenen Aufgabenliste navigiert ist, indem er sie antippt.
- **selectSettingOption**: Wechseln Sie zur Registerkarte **Einstellungen** aus dem Hamburger-Menü.
- **selectTheme**: Dunkles Design aktivieren.
- **selectUser**: Bestätigt, dass eine zugewiesene Person für eine Aufgabe erfolgreich ausgewählt wurde.
- **selfLongPress**: Langes Drücken auf „ich selbst“.
- **Send_earlycancelledCQF**: Ein Benutzer sendet Feedback über das CQF-Anrufformular.
- **send_map_pin_clicked**: Ein Benutzer sendet einen statischen Standort.
- **Send_ratemycallCQF**: Ein Benutzer sendet Feedback über das CQF-Formular „Anruf bewerten“.
- **Send_ratemyliveeventCQF**: Ein Benutzer sendet Feedback über das CQF-Formular „Liveereignis bewerten“.
- **sendForward**: Ein Benutzer bestätigt, dass er eine Weiterleitungsnachricht aus der Weiterleitungsauswahl sendet.
- **sendImage**: Bild senden.
- **sendLocation**: Standort senden.
- **sendMsg**: Wählen Sie **senden** in der Antwort aus.
- **sendRequestBulkClicked**: Dies wird für jede gesendete Massenanforderung einmal protokolliert.
- **sendRequestClicked** - **Schichtanforderung gesendet** ist ausgewählt.
- **sendVoiceMessage** - Schaltfläche **Aufnehmen** wird freigegeben.
- **Setting/Dismiss**: Gerätekontakteinstellung.
- **settingsNavReadReceiptNotice**: Benutzer ist vom Feature-Hinweis zu den Einstellungen gewechselt.
- **settingsOpened**: Dies wird ausgelöst, wenn die Gerätezeitzone des Benutzers nicht der Teamzeitzone entspricht, und der Benutzer zu Einstellungen wechselt.
- **shareFile**: Wird ausgelöst, wenn **Datei freigeben** ausgewählt ist. Hilft außerdem beim Überprüfen, ob:
  - Der Benutzer die Dateifreigabeoperation initiieren konnte.
  - Der Benutzer eine Datei erfolgreich freigeben kann.
- **shareHistory**: „Verlaufsauswahl freigeben“ ausgewählt.
- **shareInto**: Ein Benutzer gibt etwas aus einer anderen App in Teams frei.
- **sharePlanToChat**: Eine freigegebene Liste wird manuell aus der Aufgaben-App an den Gruppenchat als Chicklet freigegeben, Chicklet überprüfen, das über den Backend-Messaging-Dienst gesendet wird.
- **sharePPTFromChannels** - **Teams und Kanäle** ist ausgewählt.
- **sharePPTFromOneDrive** - **OneDrive** ist ausgewählt.
- **shareRecording**: Eine Aufzeichnung freigeben.
- **shareScreen**: Eine Bildschirmfreigabe starten oder beenden.
- **shareShift**: Die Informationen, die angegeben werden, wenn eine Schicht freigegeben wird.
- **shareShiftsClicked**: Die Details einer offenen Schicht.
- **shareTray** - **Freigeben...** ist in der Aktionstabelle ausgewählt.
- **shiftAssigneeClicked**: Die Schichtkalender-Ansicht, in der die einzelnen Schichtdetails angezeigt werden.
- **shiftDetails**: Hiermit können Sie die Details einer Schicht anzeigen.
- **shiftDetailsCalendar**: Benutzer wechselt zu Schichtdetails.
- **shiftDetailsMyShifts**: Tippen auf **Kalender** auf der Registerkarte **Zeitpläne**.
- **shiftDetailsTodaysCoworkers**: Auf dem Bildschirm zum Einstempeln ist die Schaltfläche **Pause beginnen** oder **Pause beenden** ausgewählt.
- **shortCircuitContactCount**: Die Anzahl der mit dem Adressbuch übereinstimmenden kurzgeschlossenen Kontakte, die von einem Kontaktabruf erhalten wurden.
- **showBanner**: Anzahl der Erscheinen des Banners **WLAN verbunden, kein Internet**.
- **showCard**: Tippen Sie auf Kartenschaltflächen. Karten sind wichtige Konstrukte der Plattform, und die Messung ihrer Nutzung und ihrer Muster ist notwendig, um die Nutzung der Plattform zu verstehen und nach möglichen Problemen auf der Client-Seite Ausschau zu halten.
- **shownReadReceiptNotice**: Der Featurehinweis mit Einstellungsoptionen, der dem Benutzer angezeigt wird.
- **signIn** - **Anmelden** wird auf der Homepage ausgewählt, oder die Schaltfläche **Anmelden** wird angetippt.
- **signUp** - **Kostenloses Konto erstellen** oder **Kostenlos registrieren** ist ausgewählt.
- **simultaneousCallForward**: Wird ausgelöst in den folgenden Fällen:
  - Das Ziel für die gleichzeitige Rufumleitung ist festgelegt.
  - Die gleichzeitige Rufumleitung ist aktiviert („Anrufe bei mir klingeln lassen“ ist aktiviert und „Auch anrufen“ ist festgelegt).
- **skipVerificationForLink**: Der Benutzer hat ausgewählt, die Überprüfung zu überspringen.
- **smartReply**: Die Umschaltfläche für intelligente Antworten wird angeklickt.
- **SMSSendMessage**: Der Benutzer sendet eine SMS-Nachricht.
- **sortChanged**: Wird ausgelöst, wenn der Benutzer die Sortierreihenfolge beim Anzeigen einer Aufgabenliste ändert.
- **startEditing** - Schaltfläche **Bearbeiten** ausgewählt.
- **startPresentPhoto**: Foto-Präsentation beginnen.
- **startPresentVideo**: Video-Präsentation beginnen.
- **startPSTNCall**: Wird ausgelöst durch:
  - PSTN-Ergebnis in globaler Suche (Personen).
  - PSTN-Anruf von contactCard des Geräts abgesetzt.
  - PSTN-Anruf von callList abgesetzt.
  - DialPSTN-Nummer verwendet Wähltastatur.
- **startRecording**: Aufzeichnung starten.
- **startVoicemailCall** - **Voicemail-Begrüßung ändern** ausgewählt.
- **static_place_selected**: Ein Benutzer zieht die Karte, um einen statischen Ort auszuwählen.
- **statusCheckBoxClicked**: Wird ausgelöst, wenn ein Aufgabenelement entweder abgeschlossen oder nicht abgeschlossen ist.
- **statusMsgCancel**: Ein Benutzer bricht die Änderung der Statusmeldung ab.
- **statusMsgExpiry**: Ein Benutzer bestimmt die Ablaufzeit.
- **statusMsgSet**: Ein Benutzer legt eine neue Statusnachricht fest.
- **statusPageViaContactCard**: Ein Benutzer gibt den Status „Erfahrung erstellen“ über eine Visitenkarte ein.
- **statusPageViaHamburger**: Ein Benutzer gibt den Status „Erfahrung erstellen“ über den Hamburger ein.
- **stop_location_sharing_logout**: Ein Benutzer meldet sich aus der App ab.
- **stopMeetingButton**: Die Anzahl der Male, wenn ein Benutzer den Wartebereich verlässt, ohne in die Besprechung aufgenommen zu werden.
- **stopPresentPhoto**: Foto-Präsentation beenden.
- **stopPresentVideo**: Video-Präsentation beenden.
- **stopRecording**: Aufzeichnung beenden.
- **structuredMeetingsBannerDismiss**: Ein Benutzer schließt das Banner, das ihn über seine Besprechungsrolle informiert.
- **stuckOnConnectingDialInSelected** - **Einwählen** wird in der Schublade ausgewählt.
- **stuckOnConnectingRetrySelected** - **Erneut versuchen** wird in der Schublade ausgewählt.
- **stuckOnConnectingShownDismissed**: Ein Benutzer hat die Schublade geschlossen.
- **suggested_place_selected**: Ein Benutzer teilt einen statischen Standort, indem er einen vorgeschlagenen Ort auswählt.
- **switchTeamAction**: Ein Benutzer wechselt Teams innerhalb der Stechuhr. Dies sollte ausgelöst werden, nachdem der Benutzer auswählt, zu welchem Team er wechseln möchte.
- **switchTeamsDialogTriggered**: Ein Benutzer zeigt die Registerkarte **Schichten** an.
- **tabActionCopyLink**: Wie Benutzer die Registerkarte „Link kopieren“ auf mobilen Geräten entdecken und verwenden.
- **tabActionMoreOptions**: Verstehen der Verwendung von Auslassungszeichen (**...**) aus einer Registerkarte heraus.
- **tabActionOpenInBrowser**: Verwendung von „In Browser öffnen“. Dies ist notwendig, um zu verstehen, ob Benutzer das Öffnen eines Tabs außerhalb von Teams bevorzugen.
- **tabActionOpenInBrowserFromTab**: Verstehen der Nutzung von „in Browser öffnen“ aus einer Registerkarte heraus, für weitere Optionen – Auffindbarkeit und Nutzung.
- **tabActionOpenInTeams**: In der Verwendung öffnen. Dies ist wichtig, um zu verstehen, ob der Tab standardmäßig zum Öffnen in Teams eingestellt werden kann.
- **tabActionRemove**: Verstehen, wie auffindbar die Löschoption ist, sowie die Verwendung des Features.
- **tabActionRename**: Verstehen, wie auffindbar Umbennen ist, sowie die Verwendung des Features.
- **tabActionSetting, Android - fix**: Wie Benutzer die Registerkartenkonfiguration auf mobilen Geräten entdecken und verwenden.
- **table**: Wählen Sie eine Tabelle aus.
- **tabListMoreOptions**: Verstehen, wie die weiteren Optionen für eine Registerkarte verwendet werden.
- **tabOpen**: Notiert den Erfolg beim Öffnen von Registerkarten oder wenn es Probleme beim Öffnen von Registerkarten gibt.
- **tabViewed**: Wird nur protokolliert, wenn die zu sendende Anforderung ein Tausch ist, für Einträge in der **Team-Schicht**-Auswahl.
- **takePhoto**: Nehmen Sie ein Foto auf.
- **takePhotoPicker** - **Bild aufnehmen** ist innerhalb der Bildauswahl ausgewählt.
- **tapChicletExpand**: Wie Benutzer eine Vorschau von Karten auf Mobiltelefonen anzeigen.
- **tapDatePickerHandle**: Erweitern Sie das Steuerelement für die Auswahl des Kalenderdatums.
- **tapSettings**: Die Anzahl der Benutzer, die Apps auf mobilen Geräten neu konfigurieren.
- **tasksAppLaunchAdaptiveCard**: Die Aufgaben-App wird aus einer adaptivecard in einem Gruppenchat geöffnet. Überprüfen des App-Starts über die URL des IC3-Diensts.
- **tasksAppLaunchComposeExtension**: Die Aufgaben-App wird aus der Erweiterung „Verfassen“ eines Gruppen-Chats geöffnet. Überprüfen des App-Starts über den MT-Dienst.
- **tasksAppLaunchDashboard**: Die Aufgaben-App wird über die Kachel des Dashboards oder einen bestimmten Plan geöffnet. Überprüfen des App-Starts über den MT-Dienst.
- **tasksAppLaunchDashboardSeeAll**: Die Aufgaben-App wird über die Dashboard-Schaltfläche **Alle anzeigen** auf dem Dashboard geöffnet. Überprüfen des App-Starts über den MT-Dienst.
- **tasksAppLaunchDefault**: Die Aufgaben-App wird über die untere Schublade geöffnet. Überprüfen des App-Starts über den MT-Dienst.
- **tabCalendarClicked**: Ein Benutzer hat ein Team aus der Team-Auswahl ausgewählt.
- **teamChannelChanged**: Wird ausgelöst, wenn ein Benutzer einen Plan aus der Planliste auswählt und dahin navigiert. Nur an appInsights gesendet, nicht an Aria.
- **teamCreate**: Ein Benutzer wählt die Option zum Erstellen eines neuen Teams aus.
- **teamEdit**: Ein Benutzer bearbeitet einige Aspekte eines Teams, das er besitzt oder verwaltet.
- **teamNav**: Menüoptionen für ein Team anzeigen.
- **teamsDeviceCallResumed**: Ein Benutzer mit einer durch Bluetooth verbundenen Peripherie (mobile Docking-Station) reaktiviert einen gehaltenen Anruf.
- **teamSelectedClicked**: Wenn ein Benutzer **ausgewähltes Team** für eine Arbeitszeittabelle auswählt.
- **teamShiftPickerClicked**: Wenn ein Benutzer einen neuen Pauseneintrag hinzufügt. Das Ereignis wird protokolliert, sobald der Benutzer die Änderungen speichert.
- **tenantSwitch**: Beim Wechsel des Mandanten. Feature-Erfolgsmetriken für das MTMA-Feature (Multiple Tenant and Multiple Account). Damit werden Probleme proaktiv erkannt und behoben und eine reibungslose Benutzererfahrung beim Umschalten gewährleistet.
- **TenantSwitchUnsupportedError**: Tenant Unsupported Error (wenn ein Benutzer den Fehler sieht). Feature-Erfolgsmetriken für MTMA (mehrere Mandanten und mehrere Konten), bietet Telemetrie rund um Konto- oder Mandantenwechsel-Fehler, damit wir Probleme proaktiv erkennen und beheben können und eine reibungslose Benutzererfahrung beim Wechsel bieten können.
- **timeClockClicked**: Ein Benutzer wählt die Schaltfläche **Stechuhr** auf der Registerkarte „Meine Schichten“ aus.
- **timeOffReasonClicked**: Ermittlung, ob ein Grund für arbeitsfreie Zeit angegeben wird.
- **timesheetAddClicked**: Wenn ein Benutzer seiner Pausenbearbeitung eine Notiz hinzufügt. Das Ereignis wird protokolliert, sobald der Benutzer die Änderungen speichert.
 **timesheetBreakAdded**: Hinzufügen eines neuen Uhr-Eintrags. Das Ereignis wird protokolliert, sobald Änderungen gespeichert werden.
- **timesheetBreakEdited**: Wenn ein Benutzer seine Arbeitszeittabelle bestätigt. Das Ereignis wird protokolliert, wenn der Benutzer im Modal bestätigt.
- **timesheetBreakNoteAdded**: Wenn ein Benutzer seine Arbeitszeittabelle löscht. Das Ereignis wird protokolliert, wenn der Benutzer die Löschung Modal bestätigt.
- **timesheetClockAdded**: Wenn ein Benutzer die Option „Bearbeiten“ für eine Arbeitszeittabelle auswählt.
- **timesheetClockEdited**: Wenn ein Benutzer in einer bearbeiteten Arbeitszeittabelle „Speichern“ auswählt.
- **timesheetConfirmed**: Wenn ein Benutzer seiner Arbeitszeittabellen-Bearbeitung eine Notiz hinzufügt. Das Ereignis wird protokolliert, sobald der Benutzer die Änderungen speichert.
- **timesheetDeleted**: Wenn ein Benutzer eine Schichterinnerung festgelegt oder nicht festgelegt hat, sowie die Anzahl der Minuten vor einer Schicht, die ein Benutzer benachrichtigt werden möchte.
- **timesheetEditClicked**: Telemetrie zur Benutzerkonfiguration.
- **timesheetEditSaved**: Ein Benutzer tippt auf eine Arbeitszeittabelle aus dem Profil eines Benutzers, um die Arbeitszeittabelle dieses Benutzers zu öffnen.
- **timesheetNoteAdded**: Zum Anzeigen einer genehmigten Anforderung für arbeitsfreie Zeit.
- **Titleist**: Wird ausgelöst, wenn der Titel eines Aufgabenelements geändert wird, wird bei jeder Zeichenänderung ausgelöst.
- **toast**: Toast in der App ist ausgewählt.
- **toggleChannelsInChat**: Feature an- oder ausschalten. Feature-Erfolgsmetriken für einheitliche Chat- und Kanalerfahrungen.
- **toggleClicked**: Es wird eine Umschaltfläche ausgewählt.
- **transferNow**: Wird in folgenden Fällen ausgelöst:
  - Ein Benutzer wählt **Übertragen** > **Jetzt übertragen** aus.
  - Übertragungsziel ist auf eine Person festgelegt.
  - Übertragungsziel ist auf eine Telefonnummer festgelegt.
- **translateFailed**: Übersetzung ist fehlgeschlagen (offline ausgeschlossen). Feature-Erfolgsmetriken für das Nachrichtenübersetzungs-Feature.
- **unansweredCallForward**: Es wird ein Weiterleitungsziel für unbeantwortete Anrufe festgelegt. Ermöglicht auch die offene Rufumleitung für unbeantwortete Anrufe („Anrufe bei mir klingeln lassen“ ist aktiviert und „Wenn unbeantwortet“ ist aktiviert).
- **unblockCaller**: Aufheben der Blockierung:
  - Kontakt oder Nummer aus der Aktionstabelle.
  - Kontakt oder Nummer aus einer Visitenkarte.
  - Nummer aus Einstellungen.
- **unblockChat**: Aufheben der Blockierung eines Bot-Chats.
- **unpinChannel**: Kanal lösen.
- **unpinSelf**: Mich selbst aus der Aktionstabelle lösen.
- **unpinUser**: Einen Benutzer aus der Aktionstabelle lösen.
- **unsafeLink**: Ein Link wurde als unsicher eingestuft.
- **updatePersonalTask**: Bestätigt, dass eine persönliche Aufgabe erfolgreich aktualisiert wurde.
- **updatePlaybackSpeedVoicemail**: Der Wert für die Wiedergabegeschwindigkeit der Voicemail wird geändert.
- **updateTask**: Bestätigt, dass die Aktion zum Aktualisieren von Aufgaben fehlgeschlagen ist.
- **updateTaskState**: Bestätigt, dass der Aufgabenstatus aktualisiert wurde. Aktion.
- **upgrade**: Auswählen der Schaltfläche **Upgraden** im Menü **Mehr**.
- **uploadFile**: Ein Benutzer wählt **Upload vom Gerät** aus.
- **uploadSelectedFile**: Wird in folgenden Situationen ausgelöst:
  - Hochladen von Dateien im Kanal erfolgreich.
  - Hochladen von Dateien im Chat erfolgreich.
  - Dateien im Antwortfenster hochladen.
  - Erfolgreiches Hochladen von Dateien erfolgreich im Gruppenchat.
  - Verwendung des Core-Szenarios.
  - Der Anfang des Upload-Szenarios im Kanal.
  - Der Anfang des Upload-Szenarios im Chat.
  - Der Anfang oder das Ende des Upload-Szenarios im Kanal.
  - Erfolgreiches Hochladen einer Datei in die Registerkarte **Dateien**.
  - Wenn während des Dateiuploads auf eine Eingabeaufforderung reagiert wird.
  - Wenn eine ausgewählte Datei erfolgreich hochgeladen wird.
- **uploadSelectFile**: Wählen Sie eine Datei erfolgreich aus; Wählen Sie die Schaltfläche **Datei hochladen** erfolgreich aus.
- **urgentMessageSelect**: Wählt eine dringende Nachricht aus dem Prioritäts-Kontextmenü aus.
- **urgentMessageSend**: Sendet eine dringende Nachricht.
- **url**: URL.
- **urlPreview**: URL-Vorschau.
- **urlPreviewAdd**: URL-Vorschau hinzufügen.
- **urlPreviewOpen**: URL-Vorschau geöffnet.
- **urlPreviewRemove**: URL-Vorschau entfernt.
- **userConfiguration**: Zum Anzeigen einer Anforderung für ausstehende Abwesenheitszeiten.
- **userJoinedViaShareLink**: Ein Benutzer ist über einen Link einer Besprechung beigetreten.
- **userLongPress**: Langes Drücken auf einen Teilnehmer.
- **userProfileOpened**: Ein Benutzer wählt ein **Benutzer**-Symbol aus, um ein Benutzerprofil zu öffnen.
- userTimesheetOpened**: Ein Benutzer wählt eine Arbeitszeittabelle aus dem Profil eines Benutzers aus, um die Arbeitszeittabelle dieser Person zu öffnen.
- **useWifiForAudioDialog**: Ein Benutzer wählt **OK** aus, obwohl ein Administrator die Audio- und Videoanrufe auf dem Mobiltelefon blockiert hat.
- **useWifiForVideoDialog**: Wird in folgenden Fällen ausgelöst:
  - **OK** wird während der Eingabeaufforderung des Systems ausgewählt, obwohl ein Administrator Videoanrufe auf dem Mobiltelefon blockiert hat.
  - Der Versuch, Video in einer Besprechung zu aktivieren, obwohl ein Administrator dies auf dem Mobiltelefon blockiert hat.
  - **OK** wird während der Eingabeaufforderung des Systems ausgewählt, obwohl ein Administrator Videos in Besprechungen auf dem Mobiltelefon blockiert hat.
- **videoUserDoubleTap**: Doppeltippen auf einen Videoteilnehmer.
- **viewChannelMembers**: Anzeigen einer Liste von Kanalmitgliedern.
- **viewContactCard**: ContactCard ausgewählt aus:
  - Einem callHistory-Element.
  - Einem Voicemail-Element.
  - Einer Anrufliste.
- **viewed**: Ein Benutzer hat eine Seite angezeigt.
- **viewFullAllDayMeetingList**: Agenda-Ansicht auf mobilen Geräten.
- **viewLobbyFromBanner**: Die Anzahl der Male, in denen ein Benutzer **Wartebereich anzeigen** aus einem Benachrichtigungsbanner auswählt.
- **viewMeetingDetails**: Auswählen des Menüs **...** auf der Besprechungsdetailseite. In Bezug auf die Verwendung des Menüs **Mmehr** für mobile Kalender.
- **viewMeetingOccurrence**: Öffnen Sie die Besprechungsdetails einer Instanz einer Besprechungsserie. Telemetrie zum Protokollieren der Benutzerdaten über den Kalendertrichter, wobei Details zu Kalendertreffen eine wichtige Rolle spielen. Das hilft bei der Validierung von Wählt Einwahl, Teambesprechungen, RSVPs und so weiter.
- **viewMeetingSeries**: Zum Protokollieren des erfolgreichen Renderings einer Besprechungsserie in den folgenden Situationen:
  - Beim Umstieg von einer Instanz zur Besprechungsdetailseite der Serie.
  - Bei der Auswahl von **Serie anzeigen** aus der Besprechungsdetailseite.
- **viewOrgChart**: Grundlegende Nutzung der Telemetrie für ein Organigramm.
- **viewRequests**: Die Schaltfläche **Anforderungen anzeigen** wird gedrückt.
- **voiceDataCollectionOptOut**: Ein Benutzer deaktiviert die Aufzeichnung vom mobilen Gerät aus durch Klicken auf das Banner.
- **voicemail - No AS Assigned**: Ein Sprecher tippt auf einen Voicemail-Eintrag.
- **whiteboardUsed**: Ein Benutzer macht Anmerkungen auf einem Whiteboard (eine Aktion in der Webansicht).
- **wiki - No AS assigned**: Telemetrie der Wiki-Nutzung.

### <a name="scenario"></a>Szenario

> [!NOTE]
> Informationen zu den Eigenschaften von PanelAction-Ereignissen finden Sie unter [Eigenschaften, die mit Szenario-Ereignissen gesendet werden](#properties-sent-with-scenario-events).

- **create_default_plan_and_nav_to_view**: Bestätigt die erfolgreiche Erstellung einer standardmäßigen, freigegebenen Aufgabenliste und die Zeit, die ein Benutzer benötigte, um nach der Aktion auf der Ergebnisansicht zu landen.
- **create_personal_plan_and_nav_to_view**: Bestätigt die erfolgreiche Erstellung einer persönlichen Aufgabenliste und die Zeit, die ein Benutzer benötigte, um nach der Aktion auf der Ergebnisansicht zu landen.
- **create_personal_task**: Bestätigt die erfolgreiche Erstellung eines persönlichen Aufgabenelements.
- **create_planner_plan_and_nav_to_view**: Bestätigt die erfolgreiche Erstellung einer freigegebenen Aufgabenliste und die Zeit, die ein Benutzer benötigte, um nach der Aktion auf der Ergebnisansicht zu landen.
- **create_planner_task**: Bestätigt die erfolgreiche Erstellung eines freigegebenen Aufgabenelements.
- **delete_personal_plan**: Bestätigt das erfolgreiche Löschen einer persönlichen Aufgabenliste.
- **delete_personal_plan**: Bestätigt das erfolgreiche Löschen eines persönlichen Aufgabenelements.
- **delete_planner_plan**: Bestätigt das erfolgreiche Löschen einer freigegebenen Aufgabenliste.
- **delete_planner_task**: Bestätigt das erfolgreiche Löschen eines freigegebenen Aufgabenelements.
- **get_sender_sub_scenario**: Sender-Subszenario in Aktivität abrufen.
- **load_chat_plans_list**: Bestätigt das erfolgreiche Abrufen von Planner-Plänen für die Planansicht eines Chats.
- **load_home_page**: Bestätigt das erfolgreiche Abrufen von persönlichen und freigegebenen Aufgabenlisten für die Startseite.
- **load_personal_task_list**: Bestätigt das erfolgreiche Abrufen der Aufgaben einer persönlichen Aufgabenliste für die Aufgabenliste.
- **load_shared_task_list**: Bestätigt das erfolgreiche Abrufen der Aufgaben einer freigegebenen Aufgabenliste für die Aufgabenliste.
- **load_smart_task_list**: Bestätigt das erfolgreiche Abrufen der Aufgaben einer intelligenten Aufgabenliste für die Aufgabenliste.
- **rename_personal_plan**: Bestätigt die erfolgreiche Umbenennung einer persönlichen Aufgabenliste.
- **rename_planner_plan**: Bestätigt die erfolgreiche Umbennenung einer freigegebenen Aufgabenliste.
- **smart_reply_enabled**: Bestätigt, dass Smart Reply für den aktuellen Benutzer aktiviert ist.
- **smart_reply_received**: Bestätigt, dass ein Smart Reply-Vorschlag empfangen wurde.
- **smart_reply_banned**: Bestätigt, dass Smart Reply für den aktuellen Benutzer nicht angezeigt werden kann.
- **update_planner_task_and_nav_to_view**: Bestätigt das erfolgreiche Aktualisieren eines freigegebenen Aufgabenelements und die Zeit, die ein Benutzer benötigte, um nach der Aktion auf der Ergebnisansicht zu landen.
- **update_personal_task_and_nav_to_view**: Bestätigt die erfolgreiche Aktualisierung eines persönlichen Aufgabenelements, und wie lange es dauert, bis ein Benutzer danach auf der Ergebnisansicht landet – **updatePlannerTask** –Bbestätigt, dass ein Benutzer eine Aufgabe in einer freigegebenen Aufgabenliste erfolgreich aktualisiert hat.

## <a name="property-lists"></a>Eigenschaftenlisten

### <a name="properties-sent-with-all-events"></a>Eigenschaften, die mit allen Ereignissen gesendet werden

| Eigenschaftenname                    | Beschreibung                                                          |
|----------------------------------|----------------------------------------------------------------------|
| EventInfo_Time                   | Ereignisgenerierungszeit                                                |
| EventInfo_Name                   | Name des Ereignisses; wird verwendet, um zwischen Ereignistypen zu unterscheiden.               |
| EventInfo_BaseType/name          | Ereignistyp; wird verwendet, um zwischen Ereignistypen in einem Ereignis zu unterscheiden.   |
| EventInfo_Source                 | Quelle der Ereignisgenerierung                                       |
| AppInfo_Language                 | App-Sprache                                                         |
| AppInfo_ETag                     | Dem Benutzer zugeordnete Experiment-ID                                     |
| DeviceInfo_OsBuild               | Buildversion des Betriebssystems                                              |
| UserInfo_Mri                     | Eine Benutzer-ID eingeben                                                       |
| Session_RunId                    | Typ einer Sitzungs-ID                                                 |
| DeviceInfo_DetailModel           | Modell des Geräts                                                  |
| UserInfo_TimeZone                | Zeitzone des Benutzers                                                |
| DeviceInfo_OsName                | Betriebssystemname des Geräts                                                       |
| DeviceInfo_NetworkProvider       | Gerätenetzwerk-Anbieter                                              |
| DeviceInfo_Model                 | Gerätemodell                                                         |
| DeviceInfo_NetworkType           | Gerätenetzwerktyp                                                  |
| UserInfo_Language                | Benutzersprache – ähnlich wie die App-Sprache                              |
| client_ring/UserInfo_Ring        | Benutzerring, der die Veröffentlichung von Features für Early Adopter unterstützt           |
| UserInfo_Id                      | Benutzer-ID                                                              |
| UserInfo_TenantId                | Mandanten-ID                                                            |
| EventInfo_SdkVersion             | SDK-Version, mit der das Ereignis generiert wird                               |
| DeviceInfo_Id                    | Geräte-ID, die vom Gerätebetriebssystem bereitgestellt wird                                      |
| eventpriority                    | Priorität eines Ereignisses                                                 |
| DeviceInfo_Make                  | Gerätehersteller                                                  |
| AppInfo_Version                  | Version der App                                                   |
| DeviceInfo_OsVersion             | Geräte-Betriebssystemversion                                                    |
| Session_Id/SessionId             | Sitzungs-ID der Anforderung                                            |
| Session_Environment              | Sitzungsumgebung                                                  |
| isNetworkIssue                   | Zeichnet Informationen auf, ob bei der Bearbeitung der Anfrage ein Netzwerkproblem aufgetreten ist |
| UserRole                         | Benutzerrolle in einem Mandanten                                                |
| Tenant_Model                     | Erfasst, ob es sich bei dem Konto um ein Freemium- oder ein Unternehmenskonto handelt          |
| licenseType/UserInfo_LicenseType | Dem Benutzer zugewiesener Lizenztyp                                    |
| UserLocale                       | Gebietsschema, in dem auf die App zugegriffen wird.                                |
| Intune_sdkVersion                | Version des InTune-SDKs                                            |
| Intune_sdkBundleVersion          | Detaillierte Version des InTune-SDKs                                   |
| AppInfo_Environment              | Umgebung, in der auf die App zugegriffen wird                         |

### <a name="properties-sent-with-panelaction-events"></a>Eigenschaften, die mit Panelaction-Ereignissen gesendet werden

| Eigenschaftenname         | Beschreibung                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | Der URI der Ressource, auf die die Benutzeraktion zugreift                  |
| Panel_Uri             | Der URI des für den Benutzer bereitgestellten Bereichs                             |
| Action_Gesture        | Die Art der vom Benutzer in der App ausgeführten Geste                       |
| Action_ScenarioType   | Featuregruppierung, die Geschäftsmetriken für das Feature entspricht.       |
| Panel_Type            | Der Bereichstyp, auf den der Benutzer zugegriffen hat                                    |
| Action_Outcome        | Ergebnis der Aktion, die vom Benutzer ausgeführt wurde                            |
| Team_Id               | Die ID des Teams, in dem die Aktion vom Benutzer ausgeführt wurde.           |
| Module_Type           | Der Typ des Moduls, das die Benutzeraktion gehostet hat                        |
| Module_Name           | Der Name des Moduls, das die Benutzeraktion gehostet hat                        |
| Module_Summary        | Zusammenfassung des Moduls, das die Benutzeraktion gehostet hat                      |
| Thread_Id             | Die ID des Threads, auf den der Benutzer zugegriffen hat.                         |
| Panel_PreviousUri     | URI des vorhergehenden Bereichs                                          |
| Panel_Region          | Region, in der der Bereich in der App gehostet wurde                       |
| Panel_LaunchMethod    | Methode, durch die der Bereich gestartet wurde                        |
| Panel_PreviousType    | Typ des vorhergehenden Bereichs                                         |
| Thread_Type           | Der Typ des Threads, auf den der Benutzer zugegriffen hat                                    |
| Module_State          | Status des Moduls, auf das der Benutzer zugegriffen hat                               |
| Action_Scenario       | Funktion in einer Gruppe von Funktionen, die Geschäftsmetriken entspricht |
| Panel_LaunchSource    | Quellinformationen des gestarteten Bereichs                  |
| Tab_Type              | Der Typ der Registerkarte, auf die der Benutzer zugegriffen hat                                   |
| Team_Type             | Der Typ des Teams, auf das der Benutzer zugegriffen hat                                      |

### <a name="properties-sent-with-panelview-events"></a>Eigenschaften, die mit Panelview-Ereignissen gesendet werden

| Panel_Uri          | Der URI des für den Benutzer bereitgestellten Bereichs                   |
|--------------------|----------------------------------------------------------|
| Panel_Type         | Der Bereichstyp, auf den der Benutzer zugegriffen hat                          |
| Team_Id            | Die ID des Teams, in dem die Aktion vom Benutzer ausgeführt wurde. |
| Thread_Id          | Die ID des Threads, auf den der Benutzer zugegriffen hat.               |
| Panel_PreviousUri  | URI des vorhergehenden Bereichs                                |
| Panel_Region       | Region, in der der Bereich in der App gehostet wurde             |
| Panel_LaunchMethod | Methode, durch die der Bereich gestartet wurde              |
| Panel_PreviousType | Typ des vorhergehenden Bereichs                               |
| Thread_Type        | Der Typ des Threads, auf den der Benutzer zugegriffen hat                          |
| Panel_LaunchSource | Quellinformationen des gestarteten Bereichs        |
| Tab_Type           | Der Typ der Registerkarte, auf die der Benutzer zugegriffen hat                         |
| Team_Type          | Der Typ des Teams, auf das der Benutzer zugegriffen hat                            |

### <a name="properties-sent-with-scenario-events"></a>Eigenschaften, die mit Szenario-Ereignissen gesendet werden

| Eigenschaftenname        | Beschreibung |
|----------------------|-------------|
| Scenario_Status      | Status eines Szenarios – Abbrechen/OK/FEHLER |
| Scenario_Step        | Wenn ein Szenario mehrere Schritte mit unterschiedlichen Ausfallpunkten enthält, erfasst diese Eigenschaft Details zu dem Schritt |
| Scenario_StatusCode  | Eigenschaft zeichnet den Statuscode des Szenarios auf, basierend auf Erfolg oder Misserfolg des Szenarios |

### <a name="properties-sent-with-trace-events"></a>Eigenschaften, die mit Spurereignissen gesendet werden

| Eigenschaftenname | Beschreibung                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| Trace_message | Enthält die Fehlerzeichenfolge und Details zu den Gründen, aufgrund derer ein Fehler möglicherweise aufgetreten ist |

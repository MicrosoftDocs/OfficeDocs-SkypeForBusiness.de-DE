---
title: Verwalten von Besprechungsrichtlinien
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie die Einstellungen für Besprechungsrichtlinien in Teams verwalten und verwenden, um die für Besprechungsteilnehmer verfügbaren Features für Besprechungen zu steuern, die von Benutzern geplant werden.
ms.openlocfilehash: 689b22a98c986ca73ae3926785f75dcb6c6a9e74
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918704"
---
# <a name="manage-meeting-policies-in-teams"></a>Verwalten von Besprechungsrichtlinien in Teams

::: zone target="docs"
Besprechungsrichtlinien werden verwendet, um die Features zu steuern, die Besprechungsteilnehmern für Besprechungen, die von Benutzern in Ihrer Organisation geplant werden, zur Verfügung stehen. Nachdem Sie eine Richtlinie erstellt und die gewünschten Änderungen vorgenommen haben, können Sie der Richtlinie Nutzer zuweisen. Sie können Besprechungsrichtlinien im Microsoft Teams Admin Center oder mithilfe von [PowerShell](teams-powershell-overview.md)verwalten.

Sie können Richtlinien wie folgt implementieren, die sich auf die Besprechungs Erfahrung für Benutzer auswirken, bevor eine Besprechung beginnt, während einer Besprechung oder nach einer Besprechung.

|Implementierungs  |Beschreibung  |
|---------|---------|
|Pro Organisator    |Wenn Sie eine Richtlinie pro Organisation implementieren, erben alle Besprechungsteilnehmer die Richtlinie des Organisators. So ist beispielsweise " **Personen automatisch zulassen** " eine Richtlinie pro Organisator und steuert, ob Benutzer direkt an der Besprechung teilnehmen oder in der Lobby auf Besprechungen warten, die der Benutzer, dem die Richtlinie zugewiesen ist, geplant hat.          |
|Pro Benutzer    |Wenn Sie eine Richtlinie pro Benutzer implementieren, gilt nur die Richtlinie pro Benutzer, um bestimmte Features für den Organisator und/oder die Besprechungsteilnehmer zu beschränken. So ist beispielsweise die Option "jetzt besprechen" **in Kanälen** eine Richtlinie pro Benutzer.     |
|Pro Organisator und pro Benutzer     |Wenn Sie eine Kombination aus einer pro-Organizer-und pro-Benutzer-Richtlinie implementieren, sind bestimmte Features für Besprechungsteilnehmer basierend auf Ihrer Richtlinie und der Richtlinie des Organisators eingeschränkt. So können Sie beispielsweise für die **Cloud-Aufzeichnung** eine pro-Organizer-und pro-Benutzer-Richtlinie verwenden. Aktivieren Sie diese Einstellung, damit der Besprechungsorganisator und die Teilnehmer eine Aufzeichnung starten und beenden können.

Standardmäßig wird eine Richtlinie mit dem Namen Global (org-Wide Standard) erstellt. Allen Benutzern in Ihrer Organisation wird standardmäßig die globale Besprechungsrichtlinie zugewiesen. Sie können entweder Änderungen daran vornehmen oder eine oder mehrere benutzerdefinierte Richtlinien erstellen und Ihnen Benutzer zuweisen. Benutzer erhalten die globale Richtlinie, es sei denn, Sie erstellen eine benutzerdefinierte Richtlinie und weisen diese zu. Wenn Sie eine benutzerdefinierte Richtlinie erstellen, können Sie zulassen oder verhindern, dass bestimmte Features für Ihre Benutzer verfügbar sind, und Sie dann einem oder mehreren Benutzern zuweisen, auf die die Einstellungen angewendet werden.
-Hinweis – die Schaltfläche "Besprechungsdetails" wird availiable, wenn ein Benutzer die audioconference-Lizenzen aktiviert hat oder wenn der Benutzer audioconferencing zulässt, wenn dies nicht der Fall ist, werden die Besprechungsdetails nicht availiable
## <a name="change-or-create-a-meeting-policy"></a>Ändern oder Erstellen einer Besprechungsrichtlinie

Wenn Sie eine Besprechungsrichtlinie ändern oder erstellen möchten, wechseln Sie zum Microsoft Teams Admin Center > **Besprechungen** > ** Besprechungsrichtlinien**. Wählen Sie eine Richtlinie aus der Liste aus oder wählen Sie **Hinzufügen**. Wenn Sie eine neue Richtlinie erstellen, fügen Sie einen Namen und eine Beschreibung hinzu. Der Name darf keine Sonderzeichen enthalten und nicht mehr als 64 Zeichen lang sein. Wählen Sie Ihre Einstellungen aus, und wählen Sie dann **Speichern**aus.

Nehmen wir beispielsweise an, Sie haben eine Gruppe von Nutzern, und Sie möchten die Bandbreite begrenzen, die für Ihre Besprechung erforderlich ist. Sie erstellen dann eine neue benutzerdefinierte Richtlinie namens „begrenzte Bandbreite“ und deaktivieren die folgenden Einstellungen:

Unter **Audio & Video**:
- Deaktivieren Sie Cloud-Aufzeichnung zulassen.
- Deaktivieren Sie IP-Video zulassen.

Unter **Inhaltsfreigabe**:
- Deaktivieren Sie den Bildschirmfreigabemodus.
- Deaktivieren Sie Whiteboard zulassen.
- Deaktivieren Sie Freigegebene Notizen zulassen.

Weisen Sie dann die Richtlinie den Nutzern zu.

> [!NOTE]
> Einem Benutzer kann immer nur eine Besprechungsrichtlinie zugewiesen werden.

## <a name="assign-a-meeting-policy-to-users"></a>Nutzern eine Besprechungsrichtlinie zuweisen

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.
2. Wählen Sie den Nutzer aus, indem Sie links neben den Nutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.
3. Wählen Sie unter **Besprechungsrichtlinie** die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Übernehmen**.

Informationen dazu, wie Sie eine Richtlinie mehreren Nutzern gleichzeitig zuweisen können, finden Sie unter [Batchbearbeitung von Nutzereinstellungen eines Teams](edit-user-settings-in-bulk.md).

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu**Besprechungsrichtlinien**für **Besprechungen** > .
2. Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
5. Nachdem Sie das Hinzufügen von Benutzern abgeschlossen haben, wählen Sie **Speichern**aus.

> [!NOTE]
> Sie können eine Richtlinie nicht löschen, solange Sie Benutzern zugewiesen ist. Sie müssen allen betroffenen Benutzern erst eine andere Richtlinie zuweisen, bevor Sie die ursprüngliche Richtlinie löschen können.

## <a name="meeting-policy-settings"></a>Einstellungen für Besprechungsrichtlinien

Wenn Sie auf der Seite **Besprechungsrichtlinien** eine vorhandene Richtlinie auswählen oder auf **Hinzufügen** klicken, um eine neue Richtlinie hinzuzufügen, können Sie die Einstellungen für Folgendes konfigurieren.

- [Allgemein](#meeting-policy-settings---general)
- [Audio & Video](#meeting-policy-settings---audio--video)
- [Inhaltsfreigabe](#meeting-policy-settings---content-sharing)
- [Teilnehmer & Gäste](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>Einstellungen für Besprechungsrichtlinien – allgemein

- [Sofortbesprechung in Kanälen zulassen](#allow-meet-now-in-channels)
- [Zulassen des Outlook-Add-ins](#allow-the-outlook-add-in)
- [Planen der Kanal Besprechung zulassen](#allow-channel-meeting-scheduling)
- [Planen privater Besprechungen zulassen](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a>Sofortbesprechung in Kanälen zulassen

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die vor dem Beginn einer Besprechung gilt. Diese Einstellung steuert, ob ein Benutzer eine Ad-hoc-Besprechung in einem Teams-Kanal starten kann. Wenn Sie diese Option aktivieren und ein Benutzer eine Nachricht in einem Teams-Kanal sendet, kann der Benutzer unter dem Feld zum Verfassen auf **jetzt** besprechen klicken, um eine Ad-hoc-Besprechung im Kanal zu starten.

![Screenshot mit dem Symbol "jetzt besprechen" unter einer Nachricht](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a>Zulassen des Outlook-Add-ins

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die vor dem Beginn einer Besprechung gilt. Mit dieser Einstellung wird gesteuert, ob Teams-Besprechungen in Outlook (Windows, Mac, Web und Mobile) geplant werden können.

![Screenshot, der zeigt, wie Sie eine neue Besprechung planen können](media/meeting-policies-outlook-add-in.png)

Wenn Sie diese Option deaktivieren, können die Benutzer keine Teams-Besprechungen planen, wenn Sie in Outlook eine neue Besprechung erstellen. In Outlook unter Windows wird beispielsweise die Option **neue Teams-Besprechung** nicht im Menüband angezeigt.

### <a name="allow-channel-meeting-scheduling"></a>Planen der Kanal Besprechung zulassen

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die vor dem Beginn einer Besprechung gilt. Diese Einstellung steuert, ob Benutzer eine Besprechung in einem Teams-Kanal planen können.  Wenn Sie **diese Option deaktivieren, steht der Benutzer** beim Starten einer Besprechung in einem Teams-Kanal und der Option **Kanal hinzufügen** für Benutzer in Teams deaktiviert zur Verfügung.

![Screenshot der Option "Besprechung planen" in Teams](media/meeting-policies-schedule-a-meeting.png)

![Screenshot mit der Option "Kanal zur Besprechung auswählen"](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>Planen privater Besprechungen zulassen

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die vor dem Beginn einer Besprechung gilt. Diese Einstellung steuert, ob Benutzer private Besprechungen in Teams planen können. Eine Besprechung ist privat, wenn Sie nicht in einem Kanal in einem Team veröffentlicht wurde.

Beachten Sie Folgendes: Wenn Sie die Option " **Planen privater Besprechungen zulassen** " deaktivieren und die **Kanal Besprechungsplanung zulassen**, sind die Optionen " **erforderliche Teilnehmer hinzufügen** " und " **Kanal hinzufügen** " für Benutzer in Teams deaktiviert.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Einstellungen für Besprechungsrichtlinien – Audio & Video

- [Transkription zulassen](#allow-transcription)
- [Cloud-Aufzeichnung zulassen](#allow-cloud-recording)
- [IP-Video zulassen](#allow-ip-video)
- [Media-Bitrate (KPS)](#media-bit-rate-kps)

### <a name="allow-transcription"></a>Transkription zulassen

Hierbei handelt es sich um eine Kombination aus einer pro-Organizer-und pro-User-Richtlinie. Mit dieser Einstellung wird gesteuert, ob Beschriftungen und Transkriptions Features bei der Wiedergabe von Besprechungsaufzeichnungen zur Verfügung stehen. Wenn Sie diese Option deaktivieren, stehen die Optionen " **Suchen** " und " **CC** " während der Wiedergabe einer Besprechungsaufzeichnung nicht zur Verfügung. Die Person, die die Aufzeichnung gestartet hat, muss diese Einstellung aktiviert haben, damit die Aufzeichnung auch Transkription umfasst. 

Beachten Sie, dass die Transkription für aufgezeichnete Besprechungen derzeit nur für Benutzer unterstützt wird, für die die Sprache in Teams auf Englisch festgesetzt ist und wenn Englisch in der Besprechung gesprochen wird.

![Screenshot mit Transkriptions Optionen in einer Besprechung](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>Cloud-Aufzeichnung zulassen

Hierbei handelt es sich um eine Kombination aus einer pro-Organizer-und pro-User-Richtlinie. Diese Einstellung steuert, ob die Besprechungen dieses Benutzers aufgezeichnet werden können. Die Aufzeichnung kann vom Besprechungsorganisator oder von einem anderen Besprechungsteilnehmer gestartet werden, wenn die Richtlinieneinstellung für den Teilnehmer aktiviert ist und es sich um einen authentifizierten Benutzer aus derselben Organisation handelt.

Personen außerhalb Ihrer Organisation, wie etwa Föderations-und anonyme Benutzer, können die Aufzeichnung nicht starten. Gastbenutzer können die Aufzeichnung nicht starten oder beenden. 

![Screenshot mit den Aufzeichnungsoptionen](media/meeting-policies-recording.png)

Sehen wir uns das folgende Beispiel an:

|Benutzer |Besprechungsrichtlinie  |Cloud-Aufzeichnung zulassen |
|---------|---------|---------|
|Daniela | Global   | Falsch |
|Amanda | Location1MeetingPolicy | Wahr|
|John (externer Benutzer) | Nicht zutreffend | Nicht zutreffend|

Von Daniela organisierte Besprechungen können nicht aufgezeichnet werden, und Amanda, deren Richtlinieneinstellung aktiviert ist, kann keine von Daniela organisierten Besprechungen aufzeichnen. Von Amanda organisierte Besprechungen können aufgezeichnet werden, doch Daniela, die die Richtlinieneinstellung deaktiviert hat, und John, der ein externer Benutzer ist, kann keine von Amanda organisierten Besprechungen aufzeichnen.

Weitere Informationen zur Aufzeichnung von Cloud-Besprechungen finden Sie unter [Cloud-Besprechungsaufzeichnung in Teams](cloud-recording.md).

### <a name="allow-ip-video"></a>IP-Video zulassen

Hierbei handelt es sich um eine Kombination aus einer pro-Organizer-und pro-User-Richtlinie. Video ist eine wichtige Komponente für Besprechungen. In einigen Organisationen möchten Administratoren möglicherweise mehr Kontrolle darüber haben, welche Benutzer Besprechungen Video haben. Diese Einstellung steuert, ob Video in Besprechungen, die von einem Benutzer gehostet werden, und in 1:1-anrufen und Gruppen anrufen, die von einem Benutzer gestartet werden, aktiviert werden kann. Besprechungen, die von einem Benutzer organisiert werden, für den diese Richtlinie aktiviert ist, ermöglichen die Videofreigabe in der Besprechung durch die Besprechungsteilnehmer, wenn die Richtlinie für die Besprechungsteilnehmer ebenfalls aktiviert ist. Besprechungsteilnehmern, denen keine Richtlinien zugewiesen sind (beispielsweise anonyme und verbundene Teilnehmer) erben die Richtlinie des Besprechungsorganisators.

![Screenshot einer Besprechung mit Audio-und Videoeinstellungen](media/meeting-policies-audio-video-settings.png)

Sehen wir uns das folgende Beispiel an:

|Benutzer |Besprechungsrichtlinie  |IP-Video zulassen |
|---------|---------|---------|
|Daniela   | Global   | Wahr        |
|Amanda    | Location1MeetingPolicy        | Falsch      |

Von Daniela moderierte Besprechungen ermöglichen das Aktivieren von Videos. Daniela kann an der Besprechung teilnehmen und Video aktivieren. Amanda kann in Danielas Besprechung kein Video einschalten, weil Amandas Richtlinie so eingestellt ist, dass Video nicht zulässig ist. Amanda kann Videos sehen, die von anderen Teilnehmern an der Besprechung freigegeben wurden.

In Besprechungen, die von Amanda gehostet werden, kann niemand Video unabhängig von der Ihnen zugewiesenen Video Richtlinie aktivieren. Das bedeutet, dass Daniela in Amandas Besprechungen kein Video einschalten kann.  

Wenn Daniela Amanda mit Video anruft, kann Amanda den Anruf nur mit Audio annehmen.  Wenn der Anruf verbunden ist, kann Amanda Danielas Video sehen, kann aber kein Video aktivieren. Wenn Amanda Daniela anruft, kann Daniela den Anruf mit Video und Audio annehmen. Wenn der Anruf verbunden ist, kann Daniela sein Video nach Bedarf aktivieren oder deaktivieren.

### <a name="media-bit-rate-kps"></a>Media-Bitrate (KPS)

Hierbei handelt es sich um eine Richtlinie pro Benutzer. Diese Einstellung bestimmt die Medien Bitrate für Audio-, Video-und videobasierte App-Freigabe Übertragungen in anrufen und Besprechungen für den Benutzer. Sie wird sowohl auf den aufwärts-als auch den Downlink-Medien Durchlauf für Benutzer im Anruf oder in der Besprechung angewendet. Mit dieser Einstellung erhalten Sie eine granulare Kontrolle über die Verwaltung der Bandbreite in Ihrer Organisation. Je nach den von Benutzern benötigten Besprechungs Szenarien empfehlen wir, genügend Bandbreite zur Verfügung zu haben, um eine gute Qualität zu erzielen. Der Mindestwert beträgt 30 KPS, und der Höchstwert hängt vom Besprechungs Szenario ab. Wenn Sie mehr über die empfohlene Mindestbandbreite für Besprechungen, Anrufe und Live-Events in Teams mit guter Qualität erfahren möchten, lesen Sie [Bandbreitenanforderungen](prepare-network.md#bandwidth-requirements).

Wenn für eine Besprechung nicht genügend Bandbreite zur Verfügung steht, sehen die Teilnehmer eine Meldung, die auf schlechte Netzwerkqualität hinweist.

Für Besprechungen, die die höchste Videoqualität benötigen, wie CEO-Board-Meetings und Teams-Live-Events, empfehlen wir, die Bandbreite auf 10 Mbit/s festzulegen. Auch wenn die maximale Benutzererfahrung festgelegt ist, passt sich der Medien Stapel von Teams an niedrige Bandbreitenbedingungen an, wenn bestimmte Netzwerkbedingungen je nach Szenario erkannt werden. 

## <a name="meeting-policy-settings---content-sharing"></a>Besprechungsrichtlinien Einstellungen – Inhaltsfreigabe

- [Bildschirmübertragungsmodus](#screen-sharing-mode)
- [Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert](#allow-a-participant-to-give-or-request-control)
- [Zulassen, dass ein externer Teilnehmer die Steuerung erteilt oder anfordert](#allow-an-external-participant-to-give-or-request-control)
- [PowerPoint-Freigabe zulassen](#allow-powerpoint-sharing)
- [Whiteboard zulassen](#allow-whiteboard)
- [Zulassen von freigegebenen Notizen](#allow-shared-notes)

### <a name="screen-sharing-mode"></a>Bildschirmübertragungsmodus

Hierbei handelt es sich um eine Kombination aus einer pro-Organizer-und pro-User-Richtlinie. Mit dieser Einstellung wird gesteuert, ob die Desktop-und/oder Fenster Freigabe in der Besprechung des Benutzers zulässig ist. Besprechungsteilnehmern, denen keine Richtlinien zugewiesen sind (beispielsweise anonyme, Gast-, B2B-und Verbund Teilnehmer) erben die Richtlinie des Besprechungsorganisators.

|Einstellungswert |Verhalten  |
|---------|---------|
|**Ganzer Bildschirm**    | Die vollständige Desktopfreigabe und Anwendungsfreigabe ist in der Besprechung zulässig. |
|**Einzelne Anwendung**   | Die Anwendungsfreigabe ist in der Besprechung zulässig.        |
|**Deaktiviert**     |Bildschirmübertragung und Anwendungsfreigabe in der Besprechung deaktiviert.       |

Sehen wir uns das folgende Beispiel an:

|Benutzer |Besprechungsrichtlinie |Bildschirmübertragungsmodus |
|---------|---------|---------|
|Daniela  | Global   | Ganzer Bildschirm |
|Amanda   | Location1MeetingPolicy  | Deaktiviert |

Von Daniela moderierte Besprechungen ermöglichen Besprechungsteilnehmern, ihren gesamten Bildschirm oder eine bestimmte Anwendung freizugeben. Wenn Amanda an Danielas Besprechung teilnimmt, kann Amanda Ihren Bildschirm oder eine bestimmte Anwendung nicht freigeben, da ihre Richtlinieneinstellung deaktiviert ist. In Besprechungen, die von Amanda gehostet werden, darf niemand Ihren Bildschirm oder eine einzelne Anwendung freigeben, unabhängig von der Ihnen zugewiesenen Richtlinie für den Bildschirmfreigabe Modus. Das bedeutet, dass Daniela Ihren Bildschirm oder eine einzige Anwendung nicht in Amandas Besprechungen freigeben kann.  

Zurzeit können Benutzer keine Videos abspielen oder Ihren Bildschirm in einer Teams-Besprechung freigeben, wenn Sie Google Chrome verwenden.

### <a name="allow-a-participant-to-give-or-request-control"></a>Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert

Hierbei handelt es sich um eine Richtlinie pro Benutzer. Diese Einstellung steuert, ob der Benutzer die Steuerung des freigegebenen Desktops oder Fensters an andere Besprechungsteilnehmer weitergeben kann. Um die Steuerung zu übernehmen, zeigen Sie auf den oberen Rand des Bildschirms. 

Wenn diese Einstellung für den Benutzer aktiviert ist, wird die Option **Steuerung übergeben** in der oberen Leiste einer Freigabesitzung angezeigt. 

![Screenshot mit der Option "Steuerung übergeben"](media/meeting-policies-give-control.png)

Wenn die Einstellungen für den Benutzer deaktiviert sind, steht die Option " **Steuerelement angeben** " nicht zur Verfügung.

![Screenshot, der zeigt, dass die Option "Steuerelement angeben" nicht verfügbar ist](media/meeting-policies-give-control-not-available.png)

Sehen wir uns das folgende Beispiel an:

|Benutzer |Besprechungsrichtlinie  |Zulassen, dass Teilnehmer die Steuerung erteilen oder anfordern |
|---------|---------|---------|
|Daniela   | Global   | Wahr       |
|Babək    | Location1MeetingPolicy        | Falsch   |

Daniela kann die Steuerung des freigegebenen Desktops oder Fensters an andere Teilnehmer an einer von Babək organisierten Besprechung übergeben, während Babək anderen Teilnehmern keine Kontrolle geben kann.

Verwenden Sie das AllowParticipantGiveRequestControl-Cmdlet, um mithilfe von PowerShell Steuern zu können, wer Steuerelemente steuern oder akzeptieren kann.

> [!NOTE]
> Um freigegebene Inhalte während der Freigabe zu übernehmen und zu steuern, müssen beide Parteien den Desktop Client von Teams verwenden. Die Steuerung wird nicht unterstützt, wenn eine der beiden Parteien Teams in einem Browser ausführt. Dies ist auf eine technische Einschränkung zurückzuführen, die wir planen zu beheben. 

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Zulassen, dass ein externer Teilnehmer die Steuerung erteilt oder anfordert

Hierbei handelt es sich um eine Richtlinie pro Benutzer. Diese Einstellung steuert, ob externe Teilnehmer an einer Besprechung anderen Teilnehmern an der Besprechung die Steuerung Ihres freigegebenen Desktops oder Fensters gewähren können. Externe Teilnehmer an Teams-Besprechungen können wie folgt kategorisiert werden:  

- Anonymer Benutzer
- Gastbenutzer  
- B2B-Nutzer
- Federated-Benutzer  

Ob Verbundbenutzer externen Benutzern die Kontrolle überlassen können, während die Freigabe von **einem externen Teilnehmer** gesteuert wird, der die Steuerungseinstellung in Ihrer Organisation erteilt oder anfordert.

Verwenden Sie das AllowExternalParticipantGiveRequestControl-Cmdlet, um mithilfe von PowerShell Steuern zu können, ob externe Teilnehmer Steuerelemente steuern oder akzeptieren können.

### <a name="allow-powerpoint-sharing"></a>PowerPoint-Freigabe zulassen

Hierbei handelt es sich um eine Richtlinie pro Benutzer. Mit dieser Einstellung wird gesteuert, ob der Benutzer PowerPoint-Folienstapel in einer Besprechung freigeben kann. Externe Benutzer, einschließlich Anonymous-, Guest-und Federated-Benutzer, erben die Richtlinie des Besprechungsorganisators.

Sehen wir uns das folgende Beispiel an:

|Benutzer |Besprechungsrichtlinie  |PowerPoint-Freigabe zulassen |
|---------|---------|---------|
|Daniela   | Global   | Wahr       |
|Amanda   | Location1MeetingPolicy        | Falsch   |

Amanda kann PowerPoint-Folienstapel in Besprechungen auch dann nicht freigeben, wenn Sie der Organisator der Besprechung ist. Daniela kann PowerPoint-Folienstapel auch dann freigeben, wenn die Besprechung von Amanda organisiert ist. Amanda kann die von anderen Personen in der Besprechung freigegebenen PowerPoint-Folienstapel anzeigen, auch wenn Sie PowerPoint-Folienstapel nicht freigeben kann.

### <a name="allow-whiteboard"></a>Whiteboard zulassen

Hierbei handelt es sich um eine Richtlinie pro Benutzer. Mit dieser Einstellung wird gesteuert, ob ein Benutzer das Whiteboard in einer Besprechung freigeben kann. Externe Benutzer, einschließlich anonymen, B2B-und Verbundbenutzern, erben die Richtlinie des Besprechungsorganisators. 

Sehen wir uns das folgende Beispiel an:

|Benutzer |Besprechungsrichtlinie  |Whiteboard zulassen|
|---------|---------|---------|
|Daniela   | Global   | Wahr       |
|Amanda   | Location1MeetingPolicy        | Falsch   |

Amanda kann das Whiteboard nicht in einer Besprechung freigeben, auch wenn Sie der Organisator der Besprechung ist. Daniela kann das Whiteboard auch dann freigeben, wenn eine Besprechung von Amanda organisiert ist.  

### <a name="allow-shared-notes"></a>Zulassen von freigegebenen Notizen

Hierbei handelt es sich um eine Richtlinie pro Benutzer. Mit dieser Einstellung wird gesteuert, ob ein Benutzer Notizen in einer Besprechung erstellen und freigeben kann. Externe Benutzer, einschließlich anonymen, B2B-und Verbundbenutzern, erben die Richtlinie des Besprechungsorganisators. Die Registerkarte " **Besprechungsnotizen** " wird derzeit nur in Besprechungen mit weniger als 20 Teilnehmern unterstützt.

Sehen wir uns das folgende Beispiel an:

|Benutzer |Besprechungsrichtlinie  |Zulassen von freigegebenen Notizen |
|---------|---------|---------|
|Daniela   | Global   | Wahr       |
|Amanda   | Location1MeetingPolicy | Falsch |

Daniela kann in Amandas Besprechungen Notizen machen, und Amanda kann in keiner Besprechung Notizen machen.

## <a name="meeting-policy-settings---participants--guests"></a>Besprechungsrichtlinien Einstellungen – Teilnehmer & Gäste

Diese Einstellungen steuern, welche Besprechungsteilnehmer in der Lobby warten, bevor Sie an der Besprechung teilnehmen, sowie die Teilnahmestufe, die Sie in einer Besprechung zugelassen sind.

- [Zulassen, dass anonyme Personen eine Besprechung starten](#let-anonymous-people-start-a-meeting)
- [Automatisches zulassen von Personen](#automatically-admit-people)
- [Zulassen, dass Einwahlbenutzer die Lobby umgehen können](#allow-dial-in-users-to-bypass-the-lobby)
- ["Besprechung jetzt in privaten Besprechungen zulassen"](#allow-meet-now-in-private-meetings)
- [Aktivieren von Live Beschriftungen](#enable-live-captions)
- [Chat in Besprechungen zulassen](#allow-chat-in-meetings)

> [!NOTE]
>Die Optionen für die Teilnahme an einer Besprechung unterscheiden sich je nach den Einstellungen für die einzelnen Teams und der Verbindungsmethode. Wenn Ihre Gruppe über Audiokonferenzen verfügt und diese zum Herstellen einer Verbindung verwendet, lesen Sie [Audio-Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365). Wenn Ihre Gruppe "Teams" keine Audiokonferenzen hat, finden Sie unter [teilnehmen an einer Besprechung in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

### <a name="let-anonymous-people-start-a-meeting"></a>Zulassen, dass anonyme Personen eine Besprechung starten

Hierbei handelt es sich um eine Richtlinie pro Organisator. Mit dieser Einstellung wird gesteuert, ob anonyme Personen, einschließlich B2B-und Verbundbenutzern, an der Besprechung des Benutzers teilnehmen können, ohne dass ein authentifizierter Benutzer von der Organisation anwesend ist. 

![Screenshot mit einer Nachricht an einen wartenden Benutzer](media/meeting-policies-anonymous-user-lobby.png)

Hier sehen Sie das Join-Verhalten anonymer Personen, wenn authentifizierte Benutzer in der Besprechung anwesend sind.

|Zulassen, dass anonyme Personen eine Besprechung starten  |Automatisches zulassen von Personen |Join-Verhalten anonymer Personen |
|---------|---------|---------|
|Wahr    | Jeder      | Direkt teilnehmen         |
|   | Jeder in Ihrer Organisation       | In der Lobby warten        |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen       | In der Lobby warten         |
|Falsch    | Jeder        | Direkt teilnehmen        |
|   | Jeder in Ihrer Organisation     | In der Lobby warten        |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen      | In der Lobby warten         |

Hier sehen Sie das Join-Verhalten anonymer Personen, wenn keine authentifizierten Benutzer in der Besprechung anwesend sind.

|Zulassen, dass anonyme Personen eine Besprechung starten |Automatisches zulassen von Personen  |Join-Verhalten anonymer Personen |
|---------|---------|---------|
|Wahr    | Jeder      | Direkt teilnehmen         |
|   | Jeder in Ihrer Organisation       | In der Lobby warten        |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen       | In der Lobby warten         |
|Falsch    | Jeder        | Warten Sie in der Lobby. Benutzer werden automatisch zugelassen, wenn der erste authentifizierte Benutzer der Besprechung Beitritt.        |
|   | Jeder in Ihrer Organisation     |In der Lobby warten         |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen      | In der Lobby warten         |

### <a name="automatically-admit-people"></a>Automatisches zulassen von Personen

Hierbei handelt es sich um eine Richtlinie pro Organisator. Mit dieser Einstellung wird gesteuert, ob Personen direkt an einer Besprechung teilnehmen oder in der Lobby warten, bis Sie von einem authentifizierten Benutzer zugelassen werden.

![Screenshot einer Besprechung mit einem Benutzer in der Lobby](media/meeting-policies-lobby.png)

 Besprechungsorganisatoren können in der Besprechungseinladung auf **Besprechungsoptionen** klicken, um diese Einstellung für jede von Ihnen geplante Besprechung zu ändern.
  
|Einstellungswert  |Join-Verhalten |
|---------|---------|
|**Jeder**   |Alle Besprechungsteilnehmer werden direkt an der Besprechung teilnehmen, ohne in der Lobby zu warten. Dazu gehören authentifizierte Benutzer, Verbundbenutzer, Gäste, anonyme Benutzer und Personen, die sich per Telefon einwählen.       |
|**Jeder in Ihrer Organisation und in Verbundorganisationen**     |Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gastbenutzer und die Benutzer aus Föderations Organisationen, nehmen direkt an der Besprechung Teil, ohne in der Lobby zu warten.  Anonyme Benutzer und Benutzer, die sich per Telefon einwählen, warten in der Lobby.   |
|**Jeder in Ihrer Organisation**    |Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gastbenutzer, nehmen an der Besprechung direkt Teil, ohne in der Lobby zu warten.  Föderationsbenutzer, anonyme Benutzer und Benutzer, die sich per Telefon einwählen, warten in der Lobby.           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Zulassen, dass Einwahlbenutzer die Lobby umgehen können

Hierbei handelt es sich um eine Richtlinie pro Organisator. Diese Einstellung steuert, ob Personen, die sich per Telefon einwählen, direkt an der Besprechung teilnehmen oder in der Lobby warten, unabhängig von der Einstellung " **Personen automatisch zulassen** ".

Hier sehen Sie das Join-Verhalten von Personen, die sich per Telefon einwählen.

|Zulassen, dass Einwahlbenutzer die Lobby umgehen können  |Automatisches zulassen von Personen  |Join-Verhalten von Personen, die sich einwählen |
|---------|---------|---------|
|Wahr    | Jeder      | Direkt teilnehmen         |
|   | Jeder in Ihrer Organisation       | Direkt teilnehmen        |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen       | Direkt teilnehmen         |
|Falsch    | Jeder        | Direkt teilnehmen        |
|   | Jeder in Ihrer Organisation     |In der Lobby warten         |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen      | In der Lobby warten         |

### <a name="allow-meet-now-in-private-meetings"></a>"Besprechung jetzt in privaten Besprechungen zulassen"

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die vor dem Beginn einer Besprechung gilt. Mit dieser Einstellung wird gesteuert, ob ein Benutzer eine private Ad-hoc-Besprechung starten kann. 

### <a name="enable-live-captions"></a>Aktivieren von Live Beschriftungen

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die während einer Besprechung gilt. Mit dieser Einstellung wird gesteuert, ob die Option " **Live Beschriftungen aktivieren** " für den Benutzer verfügbar ist, um in Besprechungen, an denen der Benutzer teilnimmt, Live Beschriftungen zu aktivieren und zu deaktivieren.  

![Screenshot mit der Option "Live-Beschriftungen aktivieren"](media/meeting-policies-live-captions.png)

|Einstellungswert |Verhalten  |
|---------|---------|
|**Deaktiviert, aber der Organisator kann außer Kraft gesetzt werden**     | Live Beschriftungen werden für den Benutzer während einer Besprechung nicht automatisch aktiviert. Der Benutzer sieht im Überlaufmenü (**.**..) die Option **Live Beschriftungen aktivieren** , um Sie zu aktivieren. Dies ist die Standardeinstellung. |
|**Deaktiviert**     | Live Beschriftungen sind für den Benutzer während einer Besprechung deaktiviert. Der Benutzer kann nicht aktiviert werden.          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>Chat in Besprechungen zulassen

Hierbei handelt es sich um eine Richtlinie pro Organisator. Mit dieser Einstellung wird gesteuert, ob der Besprechungs Chat in der Besprechung des Benutzers zulässig ist.

<a name="bkparticipantsandguests"> </a>

## <a name="related-topics"></a>Verwandte Themen

[Nachrichtenrichtlinien in Teams](messaging-policies-in-teams.md)

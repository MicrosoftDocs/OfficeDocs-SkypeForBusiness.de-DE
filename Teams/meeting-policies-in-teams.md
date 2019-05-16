---
title: Verwalten von Besprechungsrichtlinien
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 05/14/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: Informationen zum Verwalten von Richtlinieneinstellungen in Teams meeting.
ms.openlocfilehash: 99458e71ae02eb6307b3f363dbf7e060e1b4ed5b
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036629"
---
# <a name="manage-meeting-policies-in-teams"></a>Verwalten von Besprechungsrichtlinien in Teams

::: zone target="docs"
Besprechungsrichtlinien werden verwendet, um die Steuerung der Features, die an die Teilnehmer bei Besprechungen, die von Benutzern in Ihrer Organisation geplant sind verfügbar sind. Nachdem Sie eine Richtlinie erstellen und Ihre Änderungen vornehmen, können Sie die Richtlinie Benutzer zuweisen. Sie können in der Microsoft-Teams-Verwaltungskonsole oder mithilfe [von PowerShell](teams-powershell-overview.md)Besprechungsrichtlinien verwalten.

Implementieren Sie Richtlinien auf folgende Weise, die Einfluss auf die besprechungsumgebung für Benutzer vor einer Besprechung gestartet wird, während einer Besprechung oder nach einer Besprechung. 

|Implementierungstyp  |Beschreibung  |
|---------|---------|
|Pro organizer    |Wenn Sie eine Richtlinie pro Organisator implementieren, erben alle Teilnehmer die Richtlinie des Dialogfelds Organisieren. Beispielsweise wird **automatisch zulassen von Personen** eine pro Organisator und-Steuerung für, ob Benutzer an der Besprechung teilnehmen direkt oder warten in der Lobby geplant, die von dem Benutzer, der die Richtlinie zugewiesen wird.          |
|Pro Benutzer    |Wenn Sie eine benutzerbasierte Richtlinie implementieren, gilt nur für die benutzerbasierte Richtlinie, um bestimmte Features für die Inhaltsorganisation und/oder Besprechung Teilnehmer zu beschränken. Beispielsweise ist **Jetzt besprechen ermöglichen** eine benutzerbasierte Richtlinie.     |
|Pro Organisator und pro Benutzer     |Wenn Sie eine Kombination aus einer Richtlinie pro Organisator und pro Benutzer implementieren, sind bestimmte Features für die Besprechungsteilnehmer basierend auf ihren und dem Organisator Richtlinie beschränkt. **Aufzeichnen von zulassen Cloud** ist beispielsweise eine Richtlinie pro Organisator und pro Benutzer. Aktivieren Sie diese Einstellung für das Zulassen der Organisator der Besprechung und die Teilnehmer zum Starten und Beenden einer aufzeichnungs. 

Standardmäßig wird eine Richtlinie mit dem Namen Global (Org geltende Standard) erstellt. Alle Benutzer in Ihrer Organisation werden standardmäßig diese besprechungsrichtlinie zugewiesen werden. Sie können entweder Änderungen an dieser Richtlinie vornehmen oder einen oder mehrere benutzerdefinierte Richtlinien erstellen und Benutzer zuweisen. Wenn Sie eine benutzerdefinierte Richtlinie erstellen, können Sie zulassen oder verhindern, dass bestimmte Features für die Benutzer verfügbar wird, und weisen Sie es an einen oder mehrere Benutzer die Einstellungen angewendet werden. 

## <a name="change-or-create-a-meeting-policy"></a>Ändern Sie oder erstellen Sie eine besprechungsrichtlinie

Zum Ändern oder erstellen eine besprechungsrichtlinie, wechseln Sie auf der Microsoft-Teams, Admin Center > **Besprechungen** > **Besprechungsrichtlinien**. Wählen Sie eine Richtlinie aus der Liste aus, oder wählen Sie **neue Richtlinie**. Wenn Sie eine neue Richtlinie erstellen, fügen Sie einen Namen und eine Beschreibung ein. Der Name kann keine Sonderzeichen enthalten oder länger als 64 Zeichen sein. Wählen Sie Ihre Einstellungen, und wählen Sie dann auf **Speichern**.

Angenommen Sie, Sie haben eine Reihe von Benutzern und Sie möchten beschränken Bandbreite, die ihrer Besprechung benötigen. Sie erstellen eine neue benutzerdefinierte Richtlinie mit dem Namen "Eingeschränkten Bandbreite" und deaktivieren die folgenden Einstellungen:

Klicken Sie unter **Audio & video**:
- Deaktivieren der Cloud aufzeichnen
- Zulassen von IP-video deaktivieren

Klicken Sie unter **gemeinsame Nutzung von Inhalten**:
- Deaktivieren Sie Bildschirmfreigabe Modus
- Whiteboard deaktivieren
- Freigegebene Notizen deaktivieren

Klicken Sie dann den Benutzern zuweisen der Richtlinie.

> [!NOTE] 
> Ein Benutzer kann jeweils nur eine besprechungsrichtlinie zugewiesen werden. 

## <a name="assign-a-meeting-policy-to-users"></a>Weisen Sie eine besprechungsrichtlinie für Benutzer

Wenn Sie die Richtlinie auf einen Benutzer anwenden möchten, wählen Sie im linken Navigationsbereich auf **Benutzer** aus, und klicken Sie dann auf den Namen des Benutzers anzeigen. Wählen Sie auf der Benutzer-Seite neben **zugewiesene Richtlinien** **Bearbeiten**. Klicken Sie dann im Bereich **Richtlinien für Benutzer bearbeiten** unter **besprechungsrichtlinie**, wählen Sie die besprechungsrichtlinie aus der Dropdownliste aus, und wählen Sie dann auf **Speichern**. Sie können auch Richtlinien aus der Liste der Benutzer zuweisen. Wählen Sie den Benutzer dazu, indem Sie auf der linken Seite des Anzeigenamen des Benutzers auf. Wählen Sie **Einstellungen bearbeiten**. Klicken Sie dann im Bereich **Einstellungen bearbeiten** unter **besprechungsrichtlinie**, wählen Sie die Richtlinie aus der Dropdown-Liste aus, und wählen Sie dann auf **Speichern**. 
 
Wenn Sie eine Richtlinie auf mehrere Benutzer anwenden möchten, wählen Sie **Benutzer** im linken Navigationsbereich und wählen Sie dann jeden Benutzer durch Klicken auf links neben den Benutzernamen ein, und klicken Sie dann auf **Bearbeiten**. Klicken Sie im Bereich **Einstellungen bearbeiten** unter **besprechungsrichtlinie**wählen Sie die Richtlinie aus der Dropdown-Liste aus, und wählen Sie dann auf **Speichern**.
 
Sie können einen oder mehrere Benutzer auch wie folgt eine besprechungsrichtlinie zuweisen:

1. Navigieren Sie zum **Microsoft-Teams, Administrationscenter** > **Besprechungen** > **Besprechungsrichtlinien**.
2. Wählen Sie die Richtlinie, indem Sie auf links neben den Namen der Richtlinie.
3. Wählen Sie **Benutzer verwalten**.
4. Klicken Sie im Bereich **Benutzer verwalten** Suche für den Benutzer nach Anzeigename oder nach Benutzernamen, wählen Sie den Namen, und wählen Sie dann auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, die Sie hinzufügen möchten.
5. Wenn Sie die Benutzer hinzugefügt haben, wählen Sie **Speichern**aus.
 
> [!NOTE] 
> Eine Richtlinie kann nicht gelöscht werden, wenn Benutzer zugewiesen sind. Sie müssen zuerst eine andere Richtlinie für alle betroffenen Benutzer zuweisen, und klicken Sie dann können Sie die ursprüngliche Richtlinie löschen.
 
## <a name="meeting-policy-settings"></a>Richtlinieneinstellungen für die Besprechung

Wenn Sie eine vorhandene Richtlinie auf der Seite **Besprechungsrichtlinien** auswählen oder **neue Richtlinie** für eine neue Richtlinie hinzuzufügen, können Sie Einstellungen für Folgendes konfigurieren.

- [Allgemein](#meeting-policy-settings---general)
- [Audio & video](#meeting-policy-settings---audio--video)
- [Gemeinsame Nutzung von Inhalten](#meeting-policy-settings---content-sharing)
- [Teilnehmer & Gäste](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>Richtlinie besprechungseinstellungen - Allgemein

- [Sofortbesprechungen in Kanäle zulassen](#allow-meet-now-in-channels)
- [Zulassen von privaten Sofortbesprechungen (bald verfügbar)](#allow-private-meet-now-coming-soon)
- [Zulassen des Outlook-add-Ins](#allow-the-outlook-add-in)
- [Zulassen der Kanal Besprechung planen.](#allow-channel-meeting-scheduling)
- [Zulassen Sie planen von privaten Besprechungen](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a>Sofortbesprechungen in Kanäle zulassen

Dies ist eine benutzerbasierte Richtlinie und wendet vor einer Besprechung beginnt. Diese Einstellung steuert, ob ein Benutzer in einem Kanal Teams eine Ad-hoc-Besprechung starten kann. Wenn Sie aktivieren auf, wenn ein Benutzer eine Nachricht in einem Kanal Teams bereitstellt, kann der Benutzer **Jetzt besprechen** unter dem Feld Verfassen im Kanal eine Ad-hoc-Besprechung starten klicken.

![Meeting-Richtlinien-Meet-now.png](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now-coming-soon"></a>Zulassen von privaten Sofortbesprechungen (bald verfügbar)

Dies ist eine benutzerbasierte Richtlinie und wendet vor einer Besprechung beginnt. Diese Einstellung steuert, ob ein Benutzer eine private ad-hoc-Besprechung starten kann.  

### <a name="allow-the-outlook-add-in"></a>Zulassen des Outlook-add-Ins

Dies ist eine benutzerbasierte Richtlinie und wendet vor einer Besprechung beginnt. Diese Einstellung steuert, ob Teams Besprechungen in Outlook (Windows, Mac, Web und Mobile) von geplant werden können.

![Meeting-Richtlinien-Outlook-add-in.png](media/meeting-policies-outlook-add-in.png)

Wenn Sie diese Option aktivieren, können Benutzer keine Teams Besprechungen planen, wenn sie eine neue Besprechung in Outlook zu erstellen. Beispielsweise werden in Outlook unter Windows die Option **Neue Teams Besprechung** in der Multifunktionsleiste nicht angezeigt.

### <a name="allow-channel-meeting-scheduling"></a>Zulassen der Kanal Besprechung planen.

Dies ist eine benutzerbasierte Richtlinie und wendet vor einer Besprechung beginnt. Diese Einstellung steuert, ob Benutzer eine Besprechung in einem Kanal Teams planen können.  Wenn diese Option deaktiviert die Option **Zeitplan einer Besprechung** nicht verfügbar für den Benutzer, wenn sie eine Besprechung in einem Kanal Teams beginnen und die Option **Wählen Sie einen Kanal erfüllen** ist nicht verfügbar, die dem Benutzer, wenn sie von Besprechungen in Teams eine Besprechung planen.

![Meeting-Richtlinien-Zeitplan-a-meeting.png](media/meeting-policies-schedule-a-meeting.png)

![Meeting-Policies-Select-a-Channel-to-Meet-in.PNG](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>Zulassen Sie planen von privaten Besprechungen

Dies ist eine benutzerbasierte Richtlinie und wendet vor einer Besprechung beginnt. Diese Einstellung steuert, ob Benutzer in Teams private Konferenzen planen können. Eine Besprechung ist privat, wenn sie nicht in einem Kanal ein Team veröffentlicht wird.

Beachten Sie, dass, wenn Sie **Planen von privaten Besprechungen zulassen** und **Zulassen Channel Besprechung planen**deaktivieren, die **Besprechung planen** Option nicht verfügbar und Benutzer keine Besprechungstermine in Teams können.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Richtlinieneinstellungen für die Meeting - Audio & video

- [Lautschrift zulassen](#allow-transcription)
- [Zulassen von Cloud aufzeichnen](#allow-cloud-recording)
- [IP video zulassen](#allow-ip-video)
- [Media-Bitrate (Kbit/s)](#media-bit-rate-kbs)
- [Aktivieren Sie live Beschriftungen (bald verfügbar)](#enable-live-captions-coming-soon)

### <a name="allow-transcription"></a>Lautschrift zulassen

Dies ist eine Kombination aus einer Richtlinie pro Organisator und pro Benutzer. Diese Einstellung steuert, ob bei der Wiedergabe des meeting-Aufzeichnungen Beschriftungen und Lautschrift-Features zur Verfügung stehen. Wenn Sie diese Option deaktiviert wird, wird nicht die **Suche** und **CC** -Optionen während der Wiedergabe einer Aufzeichnung der Besprechung zur Verfügung. Die Person, die die Aufzeichnung gestartet benötigt diese Einstellung aktiviert, sodass die Aufzeichnung auch Lautschrift enthält. 

Beachten Sie, dass Lautschrift von aufgezeichneten Besprechungen derzeit unterstützt nur für Benutzer, die die Sprache in Teams auf Englisch festgelegt haben und wenn Englisch in der Besprechung gesprochen wird.

![Meeting-Richtlinien-transcription.png](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>Zulassen von Cloud aufzeichnen

Dies ist eine Kombination aus einer Richtlinie pro Organisator und pro Benutzer. Diese Einstellung steuert, ob dieses Benutzers Besprechungen aufgezeichnet werden können. Die Aufzeichnung kann vom Organisator Besprechung oder durch einen anderen Teilnehmer gestartet werden, wenn die Einstellung für den Teilnehmer eingeschaltet ist und sie als authentifizierter Benutzer aus derselben Organisation sind.

Personen außerhalb Ihrer Organisation, beispielsweise Verbund- und anonyme Benutzer, können nicht die Aufzeichnung gestartet werden. Gast-Benutzer können nicht starten oder beenden die Aufzeichnung. 

![Meeting-Richtlinien-recording.png](media/meeting-policies-recording.png)

Betrachten Sie das folgende Beispiel aus.

|User |Besprechungsrichtlinie  |Zulassen von Cloud aufzeichnen |
|---------|---------|---------|
|Daniela | Global   | Falsch |
|Amanda | Location1MeetingPolicy | True|
|John (externe Benutzer) | Nicht zutreffend | Nicht zutreffend|

Von Daniela organisierte Besprechungen können nicht aufgezeichnet werden und Amanda, der die richtlinieneinstellung aktiviert hat, kann nicht von Daniela organisierte Besprechungen aufzeichnen. Von Amanda organisierte Besprechungen erfasst werden können, jedoch Daniela, die richtlinieneinstellung deaktiviert hat und John, ein externer Benutzer ist, nicht aufgezeichnet werden von Amanda organisierte Besprechungen.

Weitere Informationen zu Cloud besprechungsaufzeichnung finden, finden Sie unter [Teams cloud besprechungsaufzeichnung](cloud-recording.md).

### <a name="allow-ip-video"></a>IP video zulassen

Dies ist eine Kombination aus einer Richtlinie pro Organisator und pro Benutzer. Video ist eine wichtige Komponente zu Besprechungen. In einigen Organisationen möglicherweise Administratoren mehr Kontrolle über welche Benutzer Besprechungen Video haben möchten. Diese Einstellung steuert können, ob video in Besprechungen, die von einem Benutzer gehostet und in 1:1-Anrufe und Gruppe Anrufe von einem Benutzer gestartet aktiviert werden. Von einem Benutzer, der diese Richtlinie aktiviert ist, hat organisierte Besprechungen zulassen video in der Besprechung durch die Besprechungsteilnehmer freigeben, wenn die Teilnehmer der Besprechung auch die Richtlinie aktiviert ist. Besprechungsteilnehmer, die alle Richtlinien zugewiesen (beispielsweise anonyme und Verbundbenutzer Teilnehmer) werden nicht erben die Richtlinie des Besprechungsorganisators.

![Meeting-Richtlinien-Audio-Video-settings.png](media/meeting-policies-audio-video-settings.png)

Betrachten Sie das folgende Beispiel aus.

|User |Besprechungsrichtlinie  |IP-Video zulassen |
|---------|---------|---------|
|Daniela   | Global   | True        |
|Amanda    | Location1MeetingPolicy        | Falsch      |

Von Daniela gehostet zuzulassen video aktiviert werden. Daniela können Sie an der Besprechung teilnehmen und Video zu aktivieren. Video in Danielas erfüllen, da einer vergleichbaren Richtlinie gesetzt ist, können keine video kann nicht Amanda aktivieren. Amanda sichtbar Videos von andere Teilnehmer an der Besprechung gemeinsam genutzt werden.

In Besprechungen von Amanda gehostet werden können niemand Video, unabhängig von der ihnen zugewiesenen videorichtlinie zu aktivieren. Dies bedeutet, dass Daniela auf Video in einer vergleichbaren Besprechungen nicht aktiviert werden kann.  

Falls Daniela Amanda mit Video auf Anrufen, kann Amanda den Anruf mit nur Audio beantworten.  Die Verbindung hergestellt wurde, Amanda Danielas Video sehen, aber kann nicht auf Video aktivieren. Wenn Amanda Daniela aufruft, kann Daniela den Anruf mit Video und Audio beantworten. Wenn die Verbindung hergestellt wurde, kann Daniela aktivieren oder deaktivieren ihr Video, je nach Bedarf.

### <a name="media-bit-rate-kbs"></a>Media-Bitrate (Kbit/s)

Dies ist eine Richtlinie pro organisieren. Diese Einstellung bestimmt die Medien Bitrate für audio, video und Video-basierte Anwendungsfreigabe Übertragungen in Anrufe und Besprechungen des Benutzers. Es wird auf die Uplink und die Downlink Medien für Benutzer in der Anruf oder Besprechung angewendet. Diese Einstellung gibt Ihnen detaillierte Kontrolle über das Verwalten der Bandbreite in Ihrer Organisation. Je nach den Besprechungen Szenarien von Benutzern erforderlich sollten genügend Bandbreite direkten guter Qualität-Erfahrung mit. Der Mindestwert ist 30 Kbit/s und der maximale Wert hängt von des Besprechung-Szenarios. Weitere Informationen zu mindestens empfohlene Bandbreite für guter Qualität Besprechungen, Anrufe und live Ereignisse in Teams finden Sie unter [erforderliche Bandbreite](prepare-network.md#bandwidth-requirements).

Wenn nicht genügend Bandbreite für eine Besprechung vorhanden ist, wird eine Meldung, die angibt, unzureichende Netzwerkqualität von Teilnehmern angezeigt.

Für Besprechungen, die das höchste Qualität Videoerlebnis benötigen, wie beispielsweise CEO board Besprechungen und Teams live Ereignisse, sollten Sie die Bandbreite auf 10 Mbit/s festgelegt. Auch wenn die maximale Erfahrung festgelegt ist, wird der medienstapel Teams an geringer Bandbreite, wenn bestimmte Netzwerkprobleme, je nach Szenario erkannt werden. 

### <a name="enable-live-captions-coming-soon"></a>Aktivieren Sie live Beschriftungen (bald verfügbar)

Dies ist eine benutzerbasierte Richtlinie und während einer Besprechung gilt. Wenn diese Einstellung aktiviert ist, erhält der Benutzer eine Option, um die Beschriftungen während einer Besprechung anzeigen.

<a name="bkcontentsharing"> </a>

## <a name="meeting-policy-settings---content-sharing"></a>Richtlinie besprechungseinstellungen - Inhalts-Freigabe

- [Bildschirm Freigabemodus](#screen-sharing-mode)
- [Ermöglichen eines Teilnehmers zu gewähren oder Anfordern der Steuerung](#allow-a-participant-to-give-or-request-control)
- [Ermöglichen Sie einen externen Teilnehmer zu gewähren oder Anfordern der Steuerung](#allow-an-external-participant-to-give-or-request-control)
- [PowerPoint-Freigabe zulassen](#allow-powerpoint-sharing)
- [Whiteboard zulassen](#allow-whiteboard)
- [Freigegebene Notizen zulassen](#allow-shared-notes)
- [Ermöglicht es Chat in Besprechungen (bald verfügbar)](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a>Bildschirm Freigabemodus

Dies ist eine Kombination aus einer Richtlinie pro Organisator und pro Benutzer. Diese Einstellung steuert, ob desktop und/oder Fenster Freigeben des Benutzers Besprechung zulässig ist. Besprechungsteilnehmern, die keine Richtlinien zugewiesen haben (z. B., anonyme, Gast B2B, und Verbundpartner Teilnehmer) erben die Richtlinie des Besprechungsorganisators.

|Wert der Einstellung |Verhalten  |
|---------|---------|
|**Gesamten Bildschirm**    | Vollständige Desktop- und Anwendungsfreigabe ist zulässig, in der Besprechung |
|**Einzelne Anwendung**   | Anwendungsfreigabe ist in der Besprechung zulässig ist.        |
|**Deaktiviert**     |Bildschirmfreigabe und Anwendungsfreigabe in der Besprechung deaktiviert wird.       |

Betrachten Sie das folgende Beispiel aus.

|User |Besprechungsrichtlinie |Bildschirm Freigabemodus |
|---------|---------|---------|
|Daniela  | Global   | Gesamten Bildschirm |
|Amanda   | Location1MeetingPolicy  | Deaktiviert |

Von Daniela gehostet zuzulassen Teilnehmer ihrer ganzen Bildschirm oder eine bestimmte Anwendung freigeben. Wenn Amanda Danielas Besprechung beigetreten ist, kann nicht Amanda ihr Bildschirm oder eine bestimmte Anwendung freigeben, wie ihre richtlinieneinstellung deaktiviert ist. In Besprechungen von Amanda gehostet werden darf niemand ihren Bildschirm oder in einer einzigen Anwendung, unabhängig von der Bildschirmfreigabe Modus Richtlinie zugewiesen freigeben. Dies bedeutet, dass nicht Daniela ihr Bildschirm oder in einer einzigen Anwendung in einer vergleichbaren Besprechungen freigeben.  

Benutzer können nicht aktuell, video wiedergeben oder ihren Bildschirm in einer Besprechung Teams freigeben, wenn Sie ihre Google Chrome verwenden.

### <a name="allow-a-participant-to-give-or-request-control"></a>Ermöglichen eines Teilnehmers zu gewähren oder Anfordern der Steuerung

Dies ist eine benutzerbasierte Richtlinie. Diese Einstellung steuert, ob der Benutzer andere Teilnehmer der Besprechung Kontrolle über den freigegebenen Desktop oder Fenster zuweisen kann. Um die Steuerung übergeben möchten, bewegen Sie den Mauszeiger über dem oberen Rand des Bildschirms. 

Wenn diese Einstellung für den Benutzer aktiviert ist, wird die Option **Steuerung übergeben** an einer freigabesitzung in der oberen Leiste angezeigt. 

![Meeting-Richtlinien-vorführen-control.png](media/meeting-policies-give-control.png)

Wenn die Einstellungen ist für den Benutzer deaktiviert, ist die Option **Steuerung** nicht verfügbar.

![Meeting-Policies-GIVE-Control-Not-Available.PNG](media/meeting-policies-give-control-not-available.png)

Betrachten Sie das folgende Beispiel aus.

|User |Besprechungsrichtlinie  |Zulassen der Teilnehmer zu gewähren oder Anfordern der Steuerung |
|---------|---------|---------|
|Daniela   | Global   | True       |
|Babek    | Location1MeetingPolicy        | Falsch   |

Daniela kann übergeben der Steuerung des freigegebenen Desktops oder des Fensters an andere Teilnehmer an einer Besprechung organisiert Babek während Babek Steuerung an andere Teilnehmer übergeben möchten ist nicht möglich.

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Ermöglichen Sie einen externen Teilnehmer zu gewähren oder Anfordern der Steuerung

Dies ist eine benutzerbasierte Richtlinie. Diese Einstellung steuert, ob externe Teilnehmer an einer Besprechung Steuerung des freigegebenen Desktops oder Fenster an andere Teilnehmer der Besprechung übertragen können. Externe Teilnehmer an Besprechungen Teams können sich wie folgt kategorisieren:  

   - Anonyme Benutzer
   - Gast-Benutzer  
   - B2B-Benutzer
   - Verbundbenutzer  

Gibt an, ob Verbundbenutzer an externe Benutzer während der Freigabe steuern können, werden durch die Einstellung **können Sie einen externen Teilnehmer zu gewähren oder Anfordern der Steuerung** in ihrer Organisation gesteuert.

### <a name="allow-powerpoint-sharing"></a>PowerPoint-Freigabe zulassen

Dies ist eine benutzerbasierte Richtlinie. Diese Einstellung steuert, ob Benutzer PowerPoint-Folienstapel in einer Besprechung freigegeben werden kann. Externe Benutzer, einschließlich anonyme, Gast, Benutzer und Partnerbenutzer, erben die Richtlinie des Besprechungsorganisators.

Betrachten Sie das folgende Beispiel aus.

|User |Besprechungsrichtlinie  |PowerPoint-Freigabe zulassen |
|---------|---------|---------|
|Daniela   | Global   | True       |
|Amanda   | Location1MeetingPolicy        | Falsch   |

Amanda kann nicht PowerPoint-Folienstapel an Besprechungen freigeben, auch wenn er der Organisator der Besprechung ist. Daniela kann PowerPoint-Folienstapel freigeben, auch wenn die Besprechung nach Amanda organisiert ist. Amanda kann die PowerPoint-Folienstapel von anderen Personen gemeinsam genutzt werden in der Besprechung anzeigen, obwohl sie PowerPoint-Folienstapel nicht freigeben.

### <a name="allow-whiteboard"></a>Whiteboard zulassen

Dies ist eine benutzerbasierte Richtlinie. Diese Einstellung steuert, ob ein Benutzer das Whiteboard in einer Besprechung freigegeben werden kann. Externe Benutzer, einschließlich anonyme, B2B und Verbundbenutzer, erben die Richtlinie des Besprechungsorganisators. 

Betrachten Sie das folgende Beispiel aus.

|User |Besprechungsrichtlinie  |Whiteboard zulassen|
|---------|---------|---------|
|Daniela   | Global   | True       |
|Amanda   | Location1MeetingPolicy        | Falsch   |

Amanda kann nicht das Whiteboard in einer Besprechung freigeben, selbst wenn er der Organisator der Besprechung wird. Daniela kann das Whiteboard freigeben, selbst wenn durch Amanda eine Besprechung organisiert werden.  

### <a name="allow-shared-notes"></a>Freigegebene Notizen zulassen

Dies ist eine benutzerbasierte Richtlinie. Diese Einstellung steuert, ob ein Benutzer erstellen und Freigeben von Notizen in einer Besprechung kann. Externe Benutzer, einschließlich anonyme, B2B und Verbundbenutzer, erben die Richtlinie des Besprechungsorganisators. Die Registerkarte **Besprechungsnotizen** ist derzeit nur in unterstützten Besprechungen, die weniger als 20 Teilnehmer haben. 

Betrachten Sie das folgende Beispiel aus.

|User |Besprechungsrichtlinie  |Freigegebene Notizen zulassen |
|---------|---------|---------|
|Daniela   | Global   | True       |
|Amanda   | Location1MeetingPolicy | Falsch |

Daniela kann Aufzeichnen von Notizen in einer vergleichbaren Besprechungen und Amanda kann nicht Aufzeichnen von Notizen in eine beliebige Besprechungen.

### <a name="allow-chat-in-meetings-coming-soon"></a>Ermöglicht es Chat in Besprechungen (bald verfügbar)

Dies ist eine Richtlinie pro organisieren. Diese Einstellung steuert, ob der Benutzer Besprechung meeting Chat zulässig ist. 

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---participants--guests"></a>Richtlinie besprechungseinstellungen - Teilnehmer & Gäste

Diese Einstellungen steuern, welche Besprechungsteilnehmer warten im Wartebereich warten, bevor sie an der Besprechung und die Ebene der Teilnahme zugelassen sind, die sie in einer Besprechung zugelassen werden.

- [Automatisch Personen zulassen](#automatically-admit-people)
- [Erlauben Sie anonyme Benutzern, starten Sie eine Besprechung](#allow-anonymous-people-to-start-a-meeting)
- [Zulassen Sie DFÜ-Benutzer umgehen den Wartebereich](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)
- [Zulassen von Organisatoren, Wartebereich Einstellungen außer Kraft setzen](#allow-organizers-to-override-lobby-settings-coming-soon)

### <a name="automatically-admit-people"></a>Automatisch Personen zulassen

Dies ist eine Richtlinie pro organisieren. Diese Einstellung steuert, ob Personen, für die Verknüpfung einer Besprechung direkt oder im Wartebereich warten, bis Sie sie durch einen authentifizierten Benutzer zugelassen werden.

![Meeting-Richtlinien-lobby.png](media/meeting-policies-lobby.png)

 Besprechungsorganisatoren kann Klicken Sie auf **Besprechungsoptionen** in der Einladung zum Ändern dieser Einstellung für jede Besprechung, die sie planen. **(bald verfügbar)**
  
|Wert der Einstellung  |Teilnehmen an Verhalten |
|---------|---------|
|**Jeder**   |Alle Teilnehmer an die Besprechung direkt und ohne im Wartebereich warten teilnehmen. Dazu gehören authentifizierte Benutzer, Verbundbenutzer, Gäste, anonyme Benutzer und Personen, die sich per Telefon einwählen.       |
|**Jede Person in Ihrer Organisation und Partnerorganisationen**     |Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gast und die Benutzer aus verbundorganisationen, teilnehmen an der Besprechung direkt und ohne im Wartebereich warten.  Anonyme Benutzer und Benutzer, die sich per Telefon einwählen im Wartebereich warten.   |
|**Jede Person in Ihrer Organisation**    |Authentifizierte Benutzer von innerhalb der Organisation, einschließlich Gastbenutzer teilnehmen an der Besprechung direkt und ohne im Wartebereich warten.  Benutzer, die sich per Telefon einwählen, Verbundbenutzer und anonyme Benutzer im Wartebereich warten.           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a>Erlauben Sie anonyme Benutzern, starten Sie eine Besprechung

Dies ist eine Richtlinie pro organisieren. Diese Einstellung steuert, ob anonyme Benutzer, einschließlich B2B und Verbundbenutzer, des Benutzers Besprechung ohne als authentifizierter Benutzer aus der Organisation in Anwesenheit beitreten können. 

![Meeting-Richtlinien-anonyme-Benutzer-lobby.png](media/meeting-policies-anonymous-user-lobby.png)

Hier wird das Verhalten Join von anonymen Benutzern bei der authentifizierte Benutzer in der Besprechung vorhanden sind.

|Erlauben Sie anonyme Benutzern, starten Sie eine Besprechung  |Automatisch Personen zulassen |Verhalten von anonymen Benutzern teilnehmen |
|---------|---------|---------|
|True    | Jeder      | Direkte Verknüpfung         |
|   | Jede Person in Ihrer Organisation       | Im Wartebereich warten        |
|   | Jede Person in Ihrer Organisation und Partnerorganisationen       | Im Wartebereich warten         |
|Falsch    | Jeder        | Direkte Verknüpfung        |
|   | Jede Person in Ihrer Organisation     | Im Wartebereich warten        |
|   | Jede Person in Ihrer Organisation und Partnerorganisationen      | Im Wartebereich warten         |

Hier ist das Join Verhalten von anonymen Benutzern, wenn keine authentifizierte Benutzer in der Besprechung vorhanden sind.

|Erlauben Sie anonyme Benutzern, starten Sie eine Besprechung |Automatisch Personen zulassen  |Verhalten von anonymen Benutzern teilnehmen |
|---------|---------|---------|
|True    | Jeder      | Direkte Verknüpfung         |
|   | Jede Person in Ihrer Organisation       | Im Wartebereich warten        |
|   | Jede Person in Ihrer Organisation und Partnerorganisationen       | Im Wartebereich warten         |
|Falsch    | Jeder        | Im Wartebereich warten. Benutzer werden automatisch zugelassen werden, wenn der erste authentifizierte Benutzer die Besprechung Beitritt.        |
|   | Jede Person in Ihrer Organisation     |Im Wartebereich warten         |
|   | Jede Person in Ihrer Organisation und Partnerorganisationen      | Im Wartebereich warten         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a>Zulassen, dass der Benutzer einwählen, umgehen den Wartebereich für eine (bald verfügbar)

Dies ist eine Richtlinie pro organisieren. Diese Einstellung steuert, ob die Personen, die sich per Telefon einwählen an der Besprechung teilnehmen direkt oder warten im Wartebereich ungeachtet der Einstellung der **Personen automatisch zuzulassen** .

Es folgt das Join-Verhalten von Personen, die sich per Telefon einwählen.

|Zulassen Sie DFÜ-Benutzer umgehen den Wartebereich  |Benutzer automatisch zulassen  |Teilnehmen Sie das Verhalten der Personen, die sich einwählen |
|---------|---------|---------|
|True    | Jeder      | Direkte Verknüpfung         |
|   | Jede Person in Ihrer Organisation       | Direkte Verknüpfung        |
|   | Jede Person in Ihrer Organisation und Partnerorganisationen       | Direkte Verknüpfung         |
|Falsch    | Jeder        | Direkte Verknüpfung        |
|   | Jede Person in Ihrer Organisation     |Im Wartebereich warten         |
|   | Jede Person in Ihrer Organisation und Partnerorganisationen      | Im Wartebereich warten         |

### <a name="allow-organizers-to-override-lobby-settings-coming-soon"></a>Zulassen von Organisatoren, Wartebereich-Einstellungen (bald verfügbar) außer Kraft setzen

Dies ist eine Richtlinie pro organisieren. Diese Einstellung steuert, ob der Organisator der Besprechung die Lobby Einstellungen außer Kraft, die ein Administrator in **automatisch zulassen von Personen** und **Benutzern einwählen setzen kann, umgehen den Wartebereich für eine** festgelegt, wenn sie eine neue Besprechung planen. 

Besprechungsorganisatoren kann Klicken Sie auf **Besprechungsoptionen** in der Einladung Wartebereich Einstellungen für jede Besprechung ändern, den sie planen. 

Hier ist, wie Sie diese Einstellung wirkt sich, ob der Organisator der Besprechung die Einstellung **automatisch Personen zulassen** für jede Sitzung der Organisator Zeitpläne ändern kann.

|Zulassen von Organisatoren, Wartebereich Einstellungen außer Kraft setzen  |Automatisch Personen zulassen  |Verhalten |
|---------|---------|---------|
|True    | Jeder      | Organisatoren kann die Einstellung auf einen anderen Wert ändern. |
|   | Jede Person in Ihrer Organisation       | Organisatoren kann die Einstellung auf einen anderen Wert ändern.|
|   | Jede Person in Ihrer Organisation und Partnerorganisationen       | Organisator kann diese auf einen anderen Wert ändern.         |
|Falsch    | Jeder        | Organisatoren kann die Einstellung auf einen anderen Wert ändern.|
|   | Jede Person in Ihrer Organisation     |Organisatoren kann die Einstellung für **alle Benutzer in Ihrer Organisation**ändern. |
|   | Jede Person in Ihrer Organisation und Partnerorganisationen      | Organisator kann nicht die Lobby Einstellung außer Kraft setzen. |

Hier ist wie diese Einstellung wirkt sich auf, ob der Organisator der Besprechung die **Zugriffsnummer für Einwahl Benutzern erlauben, umgehen den Wartebereich für eine** Einstellung für jede Sitzung der Organisator Zeitpläne ändern kann.
    
|Zulassen von Organisatoren, Wartebereich Einstellungen außer Kraft setzen  |Zulassen Sie DFÜ-Benutzer umgehen den Wartebereich  |Verhalten |
|---------|---------|---------|
|True    |  True        | Organizer kann die Einstellung auf "false" ändern.       |
|True      | Falsch         | Organisatoren kann die Einstellung auf "true" ändern.        |
|Falsch     | True        |Organizer kann die Einstellung auf "false" ändern.         |
|Falsch      |Falsch          |Organisator kann nicht die Lobby Einstellung außer Kraft setzen und lässt keine DFÜ-Benutzer umgehen den Wartebereich für eine in der Besprechung.        |

[Vollständigen Artikel](meeting-policies-in-teams.md)

## <a name="related-topics"></a>Verwandte Themen
[Messagingrichtlinien in Teams](messaging-policies-in-teams.md)

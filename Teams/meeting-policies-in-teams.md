---
title: Verwalten von Besprechungsrichtlinien
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 05/14/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
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
description: Erfahren Sie, wie Sie die Einstellungen von Besprechungsrichtlinien in Teams verwalten.
ms.openlocfilehash: eff7eb41b5dccba299f8650c5771b33df04e719b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236621"
---
# <a name="manage-meeting-policies-in-teams"></a>Verwalten von Besprechungsrichtlinien in Teams

::: zone target="docs"
Besprechungsrichtlinien werden verwendet, um die Features zu steuern, die Besprechungsteilnehmern für Besprechungen, die von Benutzern in Ihrer Organisation geplant werden, zur Verfügung stehen. Nachdem Sie eine Richtlinie erstellt und die gewünschten Änderungen vorgenommen haben, können Sie der Richtlinie Benutzer zuweisen. Sie können Besprechungsrichtlinien im Microsoft Teams Admin Center oder [mithilfe von PowerShell](teams-powershell-overview.md) verwalten.

Sie können Richtlinien, die sich auf die Benutzererfahrung vor, während oder nach einer Besprechung auswirkt, auf folgende Weise implementieren. 

|Implementierungstyp  |Beschreibung  |
|---------|---------|
|Organisatorspezifische Richtlinie    |Wenn Sie eine organisatorspezifische Richtlinie implementieren, erben alle Besprechungsteilnehmer die Richtlinie des Organisators. So ist beispielsweise **Personen automatisch zulassen** eine organisatorspezifische Richtlinie, die bei Besprechungen, die vom Nutzer, der die Richtlinie zugewiesen hat, geplant worden sind, steuert, ob Benutzer an der Besprechung direkt teilnehmen oder in der bis zum Beginn Wartebereich bleiben.          |
|Benutzerspezifische Richtlinie    |Wenn Sie eine benutzerspezifische Richtlinie implementieren, gilt nur die Richtlinie pro Benutzer, um bestimmte Features für die Organisator-und/oder Besprechungsteilnehmer einzuschränken. So ist beispielsweise **Sofortbesprechung zulassen** eine benutzerspezifische Richtlinie.     |
|Organisatorspezifische und benutzerspezifische Richtlinie     |Wenn Sie eine Kombination aus einer organisatorspezifischen und einer benutzerspezifischen Richtlinie implementieren, sind bestimmte Features für Besprechungsteilnehmer basierend auf Ihrer Richtlinie und der Richtlinie des Organisators eingeschränkt. So ist beispielsweise **Cloud-Aufnahme zulassen** eine organisatorspezifische und benutzerspezifische Richtlinie. Aktivieren Sie diese Einstellung, um es dem Besprechungsorganisator und den Teilnehmern zu ermöglichen, eine Aufnahme zu starten und zu beenden. 

Standardmäßig wird eine Richtlinie namens „Global“ (organisationsweiter Standard) erstellt. Allen Benutzern in Ihrer Organisation wird diese Besprechungsrichtlinie standardmäßig zugewiesen. Sie können entweder Änderungen an dieser Richtlinie vornehmen oder eine oder mehrere benutzerdefinierte Richtlinien erstellen und sie den Benutzern zuweisen. Wenn Sie eine benutzerdefinierte Richtlinie erstellen, können Sie zulassen oder verhindern, dass bestimmte Features für Ihre Benutzer zur Verfügung stehen. Sie können sie dann einem oder mehreren Benutzern zuweisen, sodass die Einstellungen auf sie angewendet werden. 

## <a name="change-or-create-a-meeting-policy"></a>Ändern oder Erstellen einer Besprechungsrichtlinie

Wenn Sie eine Besprechungsrichtlinie ändern oder erstellen möchten, wechseln Sie zum Microsoft Teams Admin Center > **Besprechungen** > ** Besprechungsrichtlinien**. Wählen Sie eine Richtlinie aus der Liste aus, oder wählen Sie **Neue Richtlinie** aus. Wenn Sie eine neue Richtlinie erstellen, fügen Sie einen Namen und eine Beschreibung hinzu. Der Name darf keine Sonderzeichen enthalten und nicht mehr als 64 Zeichen lang sein. Wählen Sie die gewünschten Einstellungen und dann **Speichern** aus.

Nehmen wir beispielsweise an, Sie haben eine Gruppe von Benutzern, und Sie möchten die Bandbreite begrenzen, die für Ihre Besprechung erforderlich ist. Sie erstellen dann eine neue benutzerdefinierte Richtlinie namens „begrenzte Bandbreite“ und deaktivieren die folgenden Einstellungen:

Unter **Audio & Video**:
- Deaktivieren von „Cloud-Aufnahme“
- Deaktivieren von „IP-Video zulassen“

Unter **Inhaltsfreigabe**:
- Deaktivieren des Bildschirmübertragungsmodus
- Deaktivieren des Whiteboards
- Deaktivieren von freigegebene Notizen

Weisen Sie dann die Richtlinie den Benutzern zu.

> [!NOTE] 
> Einem Benutzer kann jeweils nur eine Besprechungsrichtlinie zugewiesen werden. 

## <a name="assign-a-meeting-policy-to-users"></a>Benutzern eine Besprechungsrichtlinie zuweisen

Wenn Sie die Richtlinie einem Benutzer zuweisen wollen, wählen Sie im linken Navigationsbereich **Benutzer** aus, und klicken dann auf seinen Anzeigenamen. Klicken Sie auf der Seite des Benutzers neben **Zugewiesene Richtlinien** auf **Bearbeiten**. Wählen Sie nun im Bereich **Benutzerrichtlinien bearbeiten** unter **Besprechungsrichtlinie** die Besprechungsrichtlinie aus der Dropdownliste aus und klicken Sie dann auf **Speichern**. Sie können Richtlinien auch aus der Benutzerliste zuweisen. Wählen Sie dazu den Benutzer aus, indem Sie links neben dem Anzeigenamen des Benutzers klicken. Wählen Sie **Einstellungen bearbeiten**. Wählen Sie nun im Bereich **Einstellungen bearbeiten** unter **Besprechungsrichtlinie** die Besprechungsrichtlinie aus der Dropdownliste aus und klicken Sie dann auf **Speichern**. 
 
Wenn Sie eine Richtlinie auf mehrere Benutzer anwenden möchten, wählen Sie im linken Navigationsbereich die Option **Benutzer** und dann die einzelnen Benutzer aus, indem Sie links neben dem Benutzernamen und dann auf **Einstellungen bearbeiten** klicken. Wählen Sie im Bereich **Einstellungen bearbeiten** unter **Besprechungsrichtlinie** die Besprechungsrichtlinie aus der Dropdownliste aus und klicken Sie dann auf **Speichern**.
 
Sie können einem oder mehreren Benutzern eine Besprechungsrichtlinie auch folgendermaßen zuweisen:

1. Wechseln Sie zu **Microsoft Teams Admin Center** > **Besprechungen** > **Besprechungsrichtlinien**.
2. Wählen Sie die Richtlinie aus, indem Sie links neben ihren Namen klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder Benutzernamens nach dem Benutzer, wählen Sie den Namen aus und klicken Sie auf **Hinzufügen**.  Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
5. Wenn Sie fertig sind, klicken Sie auf **Speichern**.
 
> [!NOTE] 
> Sie können eine Richtlinie nicht löschen, solange Sie Benutzern zugewiesen ist. Sie müssen allen betroffenen Benutzern eine andere Richtlinie zuweisen, bevor Sie die ursprüngliche Richtlinie löschen können.
 
## <a name="meeting-policy-settings"></a>Einstellungen für Besprechungsrichtlinien

Wenn Sie auf der Seiten **Besprechungsrichtlinien** eine vorhandene Richtlinie auswählen oder **Neue Richtlinie** auswählen, um eine neue Richtlinie hinzuzufügen, können Sie die folgenden Einstellungen konfigurieren.

- [Allgemein](#meeting-policy-settings---general)
- [Audio & Video](#meeting-policy-settings---audio--video)
- [Inhaltsfreigabe](#meeting-policy-settings---content-sharing)
- [Teilnehmer & Gäste](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>Besprechungsrichtlinien – Allgemeine Einstellungen

- [Sofortbesprechungen in Kanälen zulassen](#allow-meet-now-in-channels)
- [Private Sofortbesprechungen zulassen (in Kürze verfügbar)](#allow-private-meet-now-coming-soon)
- [Outlook-Add-In zulassen](#allow-the-outlook-add-in)
- [Planung von Kanalbesprechungen zulassen](#allow-channel-meeting-scheduling)
- [Planung privater Besprechungen zulassen](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a>Sofortbesprechungen in Kanälen zulassen

Hierbei handelt es sich um eine benutzerspezifisch Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Mit dieser Einstellung wird gesteuert, ob ein Benutzer eine Sofortbesprechung in einem Teams-Kanal starten kann. Wenn Sie diese Option aktivieren, kann ein Benutzer, wenn eine Nachricht in einem Teams-Kanal gesendet wird, unter dem Feld zum Erstellen auf **Sofortbesprechung** klicken, um eine Sofortbesprechung im Kanal zu starten.

![Screenshot mit dem Symbol "Sofortbesprechung" unter einer Nachricht](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now-coming-soon"></a>Private Sofortbesprechungen zulassen (in Kürze verfügbar)

Hierbei handelt es sich um eine benutzerspezifisch Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Mit dieser Einstellung wird gesteuert, ob ein Benutzer eine private Sofortbesprechung in einem Teams-Kanal starten kann.  

### <a name="allow-the-outlook-add-in"></a>Outlook-Add-In zulassen

Hierbei handelt es sich um eine benutzerspezifisch Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Mit dieser Einstellung wird gesteuert, ob Teams-Besprechungen in Outlook (Windows, Mac, Web und Mobile) geplant werden können.

![Screenshot, der zeigt, wie eine neue Besprechung geplant werden kann](media/meeting-policies-outlook-add-in.png)

Wenn Sie diese Option deaktivieren, können die Benutzer keine Teams-Besprechungen planen, wenn Sie eine neue Besprechung in Outlook erstellen. In Outlook unter Windows wird beispielsweise die Option **Neue Teams-Besprechung** nicht im Menüband angezeigt.

### <a name="allow-channel-meeting-scheduling"></a>Planung von Kanalbesprechungen zulassen

Hierbei handelt es sich um eine benutzerspezifisch Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Mit dieser Einstellung wird gesteuert, ob ein Benutzer eine Besprechung in einem Teams-Kanal planen kann.  Wenn Sie diese Option deaktivieren, stehen die Optionen **Besprechung planen** und **Kanal für Besprechung auswählen** (beim Starten einer Besprechung in einem Teams-Kanal) für den jeweiligen Benutzer beim Planen einer Besprechung in Teams nicht zur Verfügung.

![Screenshot, der die Option "Besprechung planen" in Teams zeigt](media/meeting-policies-schedule-a-meeting.png)

![Screenshot, der die Option "Kanal für Besprechung auswählen" zeigt](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>Planung privater Besprechungen zulassen

Hierbei handelt es sich um eine benutzerspezifisch Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Mit dieser Einstellung wird gesteuert, ob ein Benutzer private Besprechungen in einem Teams-Kanal planen kann. Eine Besprechung ist privat, wenn Sie nicht in einem Kanal im Team veröffentlicht wird.

Beachten Sie: Wenn Sie die Option **private Besprechungen planen** und **Planung von Kanalbesprechungen zulassen** deaktivieren, steht die Option **Besprechung planen** nicht zur Verfügung, und die Benutzer können keine Besprechungen in Teams planen.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Einstellungen für Besprechungsrichtlinien – Audio & Video

- [Transkription zulassen](#allow-transcription)
- [Cloud-Aufnahme zulassen](#allow-cloud-recording)
- [IP-Video zulassen](#allow-ip-video)
- [Media-Bitrate (KBs)](#media-bit-rate-kbs)
- [Liveuntertitel aktivieren (in Kürze verfügbar)](#enable-live-captions-coming-soon)

### <a name="allow-transcription"></a>Transkription zulassen

Hierbei handelt es sich um eine Kombination aus einer benutzerspezifischen und einer organisatorspezifischen Richtlinie. Mit dieser Einstellung wird gesteuert, ob Untertitel- und Transkriptionsfeatures während der Wiedergabe von Besprechungsaufzeichnungen verfügbar sind. Wenn Sie diese Option deaktivieren, stehen die Optionen **Suche** und **CC** während der Wiedergabe einer Besprechungsaufzeichnung nicht zur Verfügung. Die Person, die die Aufzeichnung gestartet hat, muss diese Einstellung aktivieren, damit die Aufzeichnung auch eine Transkription enthält. 

Beachten Sie, dass die Transkription für aufgezeichnete Besprechungen derzeit nur für Benutzer unterstützt wird, die die Sprache in Teams auf Englisch festgelegt haben und nur funktioniert, wenn in der Besprechung Englisch gesprochen wird.

![Screenshot der Transkriptionsoptionen in einer Besprechung](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>Cloud-Aufnahme zulassen

Hierbei handelt es sich um eine Kombination aus einer benutzerspezifischen und einer organisatorspezifischen Richtlinie. Mit dieser Einstellung wird gesteuert, ob Besprechungen dieses Benutzers aufgezeichnet werden können. Die Aufzeichnung kann vom Besprechungsorganisator oder von einem anderen Besprechungsteilnehmer gestartet werden, wenn die Richtlinieneinstellung für den Teilnehmer aktiviert ist, und wenn es sich um einen authentifizierten Benutzer aus derselben Organisation handelt.

Personen außerhalb Ihrer Organisation, z. b. Partner- oder anonyme Benutzer, können die Aufzeichnung nicht starten. Gastbenutzer können die Aufzeichnung nicht starten oder beenden. 

![Screenshot, der die Aufzeichnungsoptionen zeigt](media/meeting-policies-recording.png)

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Cloud-Aufnahme zulassen |
|---------|---------|---------|
|Daniela | Global   | Falsch |
|Amala | Location1MeetingPolicy | Wahr|
|Johann (externer Benutzer) | Nicht zutreffend | Nicht zutreffend|

Von Daniela organisierte Besprechungen lassen sich nicht aufzeichnen, und Amanda, deren Richtlinieneinstellung aktiviert ist, kann keine von Daniela organisierten Besprechungen aufzeichnen. Von Amanda organisierte Besprechungen können zwar aufgezeichnet werden, allerdings können Daniela, bei der die Richtlinieneinstellung deaktiviert ist, und John, der ein externer Benutzer ist, von Amanda organisierte Besprechungen nicht aufzeichnen.

Wenn Sie mehr über die Aufzeichnung einer Cloud-Besprechung erfahren möchten, lesen Sie [Aufzeichnung einer Teams-Cloudbesprechung](cloud-recording.md).

### <a name="allow-ip-video"></a>IP-Video zulassen

Hierbei handelt es sich um eine Kombination aus einer benutzerspezifischen und einer organisatorspezifischen Richtlinie. Video ist eine Schlüsselkomponente für Besprechungen. In einigen Organisationen möchten Administratoren möglicherweise mehr Kontrolle darüber haben, welche Besprechungen der Benutzer über Video verfügen. Mit dieser Einstellung wird gesteuert, ob Video in von einem Benutzer gehosteten Besprechungen eingeschaltet werden kann, und ob die Funktion bei Einzel- und Gruppenanrufen, die der Benutzer gestartet hat, zur Verfügung steht. Besprechungen, die von einem Benutzer organisiert wurden, bei dem diese Richtlinie aktiviert ist, können die Videofreigabe von den Besprechungsteilnehmern zulassen, sofern die Richtlinie für sie ebenfalls aktiviert ist. Besprechungsteilnehmer, denen keine Richtlinien zugewiesen sind (z. b. anonyme Teilnehmer und Partner), erben die Richtlinie des Besprechungsorganisators.

![Screenshot einer Besprechung mit Audio- und Videoeinstellungen](media/meeting-policies-audio-video-settings.png)

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |IP-Video zulassen |
|---------|---------|---------|
|Daniela   | Global   | Wahr        |
|Amala    | Location1MeetingPolicy        | Falsch      |

Von Daniela organisierte Besprechungen ermöglichen das Aktivieren von Video. Daniela kann an der Besprechung teilnehmen und Video aktivieren. Amanda kann das Video in Danielas Besprechung nicht einschalten, bei ihr die Richtlinie so festgelegt ist, dass Video nicht zulässig ist. Amanda kann Videos anzeigen, die von anderen Teilnehmern der Besprechung geteilt werden.

In Besprechungen, die von Amanda gehostet werden, kann unabhängig von der zugewiesenen Videorichtlinie niemand Video aktivieren. Das bedeutet, dass Daniela in Amandas Besprechungen Video nicht einschalten kann.  

Wenn Daniela Amanda mit aktiviertem Video anruft, kann Amanda den Anruf nur mit Audio annehmen.  Wenn die beiden verbunden sind, kann Amanda Danielas Video sehen, selbst Video aber nicht aktivieren. Wenn Amanda Daniela anruft, kann Daniela den Anruf mit Video und Audio annehmen. Wenn die beiden verbunden sind, kann Daniela ihr Video nach Wunsch aktivieren oder deaktivieren.

### <a name="media-bit-rate-kbs"></a>Media-Bitrate (KBs)

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Diese Einstellung bestimmt für den Benutzer die Medienbitrate für Audio-, Video- und videobasierte App-Übertragung bei Anrufen und in Besprechungen. Sie wird sowohl auf die Uplink- als auch auf die Downlink-Medienübertragung für die Benutzer die sich in einem Anruf oder einer Besprechung befinden, angewendet. Mit dieser Einstellung können Sie die Bandbreite in Ihrer Organisation präzise kontrollieren und verwalten. Je nach Szenario, das die Benutzer benötigen, empfiehlt es sich, genügend Bandbreite für eine bereitzustellen, um eine gute, qualitativ hochwertige Erfahrung zu gewährleisten. Der Mindestwert beträgt 30 KBit/s. Der Höchstwert ist von der jeweiligen Besprechungssituation abhängig. Weitere Informationen zur minimal empfohlenen Bandbreite für Besprechungen, Anrufe und Live-Ereignisse in Teams finden Sie unter [Bandbreitenanforderungen](prepare-network.md#bandwidth-requirements).

Wenn für eine Besprechung nicht genügend Bandbreite vorhanden ist, wird den Teilnehmern eine Nachricht angezeigt, die auf die geringe Übertragungsleistung hinweist.

Wenn Sie Besprechungen mit höchster Videoqualität, z. b. Vorstandssitzungen oder Teams-Liveereignisse, organisieren wollen, empfehlen wir, dass Sie die Bandbreite auf 10 Mbit/s festlegen. Selbst wenn die Einstellungen für eine möglichst hochwertige Erfahrung festgelegt wurden, passt sich der Teams-Medienstapel an die Bedingungen niedriger Bandbreite an, wenn abhängig vom Szenario bestimmte Netzwerkbedingungen ermittelt werden. 

### <a name="enable-live-captions-coming-soon"></a>Liveuntertitel aktivieren (in Kürze verfügbar)

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die während einer Besprechung angewendet wird. Wenn diese Einstellung aktiviert ist, sieht der Benutzer eine Option zum Anzeigen von Untertiteln während einer Besprechung.

<a name="bkcontentsharing"> </a>

## <a name="meeting-policy-settings---content-sharing"></a>Einstellungen für Besprechungsrichtlinien – Inhaltsfreigabe

- [Bildschirmübertragungsmodus](#screen-sharing-mode)
- [Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert](#allow-a-participant-to-give-or-request-control)
- [Zulassen, dass ein externer Teilnehmer die Steuerung erteilt oder anfordert](#allow-an-external-participant-to-give-or-request-control)
- [Teilen von PowerPoint zulassen](#allow-powerpoint-sharing)
- [Whiteboard zulassen](#allow-whiteboard)
- [Geteilte Notizen zulassen](#allow-shared-notes)
- [Chat in Besprechungen zulassen (in Kürze verfügbar)](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a>Bildschirmübertragungsmodus

Hierbei handelt es sich um eine Kombination aus einer benutzerspezifischen und einer organisatorspezifischen Richtlinie. Mit dieser Einstellung wird gesteuert, ob die Desktop- oder Fensterübertragung in der Besprechung des Benutzers zulässig ist. Besprechungsteilnehmer, denen keine Richtlinien zugewiesen sind (z. b. anonyme Teilnehmer, Gäste, B2B-Teilnehmer und Partner), erben die Richtlinie des Besprechungsorganisators.

|Einstellungswert |Verhalten  |
|---------|---------|
|**Gesamter Bildschirm**    | Die vollständige Desktop- und Anwendungsfreigabe ist in der Besprechung zulässig. |
|**Einzelne Anwendung**   | Die Anwendungsfreigabe ist in der Besprechung zulässig.        |
|**Deaktiviert**     |Die Bildschirm- und Anwendungsfreigabe ist in der Besprechung deaktiviert.       |

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie |Bildschirmübertragungsmodus |
|---------|---------|---------|
|Daniela  | Global   | Gesamter Bildschirm |
|Amala   | Location1MeetingPolicy  | Deaktiviert |

Besprechungen, die von Daniela gehostet werden, ermöglichen Besprechungsteilnehmern, den gesamten Bildschirm oder eine bestimmte Anwendung zu übertragen. Wenn Amanda an Danielas Besprechung teilnimmt, kann Amanda Ihren Bildschirm oder eine bestimmte Anwendung nicht teilen, da ihre Richtlinieneinstellung deaktiviert ist. In Besprechungen, die von Amanda gehostet werden, darf niemand seinen Bildschirm oder eine Anwendung teilen – unabhängig von der Bildschirmübertragungsrichtlinie, die Ihnen zugewiesen wurde. Das bedeutet, dass Daniela Ihren Bildschirm oder eine einzelne Anwendung in Amandas Besprechungen nicht übertragen kann.  

Derzeit können Benutzer in einer Teams-Besprechung keine Videos abspielen oder Ihren Bildschirm übertragen, wenn Sie Google Chrome verwenden.

### <a name="allow-a-participant-to-give-or-request-control"></a>Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob der Benutzer die Steuerung des übertragenen Desktops oder Fensters an andere Besprechungsteilnehmer übergeben kann. Um die Steuerung zu übergeben, zeigen Sie auf den oberen Bereich des Bildschirms. 

Wenn diese Einstellung für den Benutzer aktiviert ist, wird die Option **Steuerung übergeben** in der oberen Leiste einer Freigabesitzung angezeigt. 

![Screenshot mit der Option „Steuerung übergeben“](media/meeting-policies-give-control.png)

Wenn die Einstellungen für den Benutzer deaktiviert sind, ist die Option **Steuerung übergeben** nicht verfügbar.

![Screenshot, der zeigt, dass die Option „Steuerung übergeben“ nicht verfügbar ist](media/meeting-policies-give-control-not-available.png)

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert |
|---------|---------|---------|
|Daniela   | Global   | Wahr       |
|Babek    | Location1MeetingPolicy        | Falsch   |

Daniela kann die Steuerung des übertragenen Desktops oder Fensters in einer von Babək organisierten Besprechung an andere Teilnehmer übergeben. Dagegen kann Babək den anderen Teilnehmern die Steuerung nicht übergeben.

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Zulassen, dass ein externer Teilnehmer die Steuerung erteilt oder anfordert

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob externe Teilnehmer in einer Besprechung die Steuerung des übertragenen Desktops oder Fensters an andere Besprechungsteilnehmer übergeben können. Externe Teilnehmer an Teams-Besprechungen können wie folgt kategorisiert werden:  

   - Anonymer Benutzer
   - Gastbenutzer  
   - B2B-Benutzer
   - Verbundbenutzer  

Mit dieser Einstellung wird gesteuert, ob Verbundbenutzer externen Benutzern die Steuerung übergeben können, während die Steuerung durch die Einstellung**Zulassen, dass ein externer Teilnehmer die Steuerung erteilt oder anfordert** kontrolliert wird.

### <a name="allow-powerpoint-sharing"></a>Teilen von PowerPoint zulassen

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob der Benutzer PowerPoint-Folien in einer Besprechung übertragen kann. Externe Benutzer, einschließlich anonyme, Gast- und Verbundbenutzer, erben die Richtlinie des Besprechungsorganisators.

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Teilen von PowerPoint zulassen |
|---------|---------|---------|
|Daniela   | Global   | Wahr       |
|Amala   | Location1MeetingPolicy        | Falsch   |

Amanda kann keine PowerPoint-Folien in Besprechungen übertragen, auch wenn Sie der Besprechungsorganisator ist. Daniela kann PowerPoint-Folien übertragen, auch wenn die Besprechung von Amanda organisiert wurde. Amanda kann die von anderen Personen in der Besprechung übertragenen PowerPoint-Folien anzeigen, auch wenn Sie selbst keine PowerPoint-Folien übetragen kann.

### <a name="allow-whiteboard"></a>Whiteboard zulassen

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob ein Benutzer in einer Besprechung das Whiteboard übertragen kann. Externe Benutzer, einschließlich anonyme, B2B- und Verbundbenutzer, erben die Richtlinie des Besprechungsorganisators. 

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Whiteboard zulassen|
|---------|---------|---------|
|Daniela   | Global   | Wahr       |
|Amala   | Location1MeetingPolicy        | Falsch   |

Amanda kann das Whiteboard in einer Besprechung nicht übertragen, auch wenn Sie der Besprechungsorganisator ist. Daniela kann das Whiteboard auch dann übertragen, wenn eine Besprechung von Amanda organisiert wird.  

### <a name="allow-shared-notes"></a>Geteilte Notizen zulassen

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob ein Benutzer in einer Besprechung Notizen erstellen und übertragen kann. Externe Benutzer, einschließlich anonyme, B2B- und Verbundbenutzer, erben die Richtlinie des Besprechungsorganisators. Die Registerkarte **Besprechungsnotizen** wird derzeit nur in Besprechungen mit weniger als 20 Teilnehmern unterstützt. 

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Geteilte Notizen zulassen |
|---------|---------|---------|
|Daniela   | Global   | Wahr       |
|Amala   | Location1MeetingPolicy | Falsch |

Daniela kann sich in Amandas Besprechungen Notizen machen, Amanda kann hingegen in keiner Besprechung Notizen machen.

### <a name="allow-chat-in-meetings-coming-soon"></a>Chat in Besprechungen zulassen (in Kürze verfügbar)

Hierbei handelt es sich um eine organisatorspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob in der Besprechung des Benutzers ein Chat zulässig ist. 

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---participants--guests"></a>Einstellungen für Besprechungsrichtlinien – Teilnehmer und Gäste

Mit diesen Einstellungen können Sie steuern, welche Besprechungsteilnehmer im Wartebereich bleiben müssen, bevor Sie zur Besprechung zugelassen werden. Außerdem legen sie ihre Teilnahmemöglichkeiten während einer Besprechung fest.

- [Personen automatisch zulassen](#automatically-admit-people)
- [Zulassen, dass anonyme Personen eine Besprechung starten](#allow-anonymous-people-to-start-a-meeting)
- [Einwählbenutzern das Umgehen des Wartebereichs gestatten](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)
- [Organisatoren das Außerkraftsetzen von Wartebereichseinstellungen gestatten](#allow-organizers-to-override-lobby-settings-coming-soon)

> [!NOTE]
>Die Optionen zur Teilnahme an einer Besprechung variieren je nach den Einstellungen für jede Teams-Gruppe und Verbindungsmethode. Wenn Ihre Gruppe über Audiokonferenzen verfügt und sie für die Verbindung verwendet, sehen Sie sich [Audiokonferenzen in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365) an. Wenn Ihre Teams-Gruppe nicht über Audiokonferenzen verfügt, finden Sie weitere Informationen unter [Teilnehmen an einer Besprechung in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

### <a name="automatically-admit-people"></a>Personen automatisch zulassen

Hierbei handelt es sich um eine organisatorspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob Personen direkt an einer Besprechung teilnehmen können oder in im Wartebereich bleiben müssen, bis Sie von einem authentifizierten Benutzer zugelassen werden.

![Screenshot einer Besprechung mit einem Benutzer im Wartebereich](media/meeting-policies-lobby.png)

 Besprechungsorganisatoren können in der Besprechungseinladung auf **Besprechungsoptionen** klicken, um diese Einstellung für jede von Ihnen geplante Besprechung zu ändern. **(In Kürze verfügbar)**
  
|Einstellungswert  |Verhalten bei Teilnahme |
|---------|---------|
|**Jeder**   |Alle Besprechungsteilnehmer nehmen direkt an der Besprechung teil und müssen nicht im Wartebereich warten. Dazu zählen authentifizierte Benutzer, Verbundbenutzer, Gäste, anonyme Benutzer und Personen, die sich per Telefon einwählen.       |
|**Jeder in Ihrer Organisation und in Verbundorganisationen**     |Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gastbenutzer und Benutzer aus Verbundorganisationen, nehmen an der Besprechung direkt teil, ohne im Wartebereich warten zu müssen.  Anonyme Benutzer und Benutzer, die sich per Telefon einwählen, warten im Wartebereich.   |
|**Jeder in Ihrer Organisation**    |Authentifizierte Benutzer innerhalb der Organisation, einschließlich Gastbenutzer, nehmen an der Besprechung direkt teil, ohne im Wartebereich warten zu müssen.  Verbundbenutzer, anonyme Benutzer und Benutzer, die sich per Telefon einwählen, warten im Wartebereich.           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a>Zulassen, dass anonyme Personen eine Besprechung starten

Hierbei handelt es sich um eine organisatorspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob anonyme Personen, einschließlich B2B- und Verbundbenutzern, an der Besprechung des Benutzers teilnehmen können, ohne dass ein authentifizierter Benutzer aus der Organisation teilnimmt. 

![Screenshot, der eine Nachricht an einen wartenden Benutzer zeigt](media/meeting-policies-anonymous-user-lobby.png)

Hier sehen Sie das Verhalten bei Teilnahme anonymer Personen, wenn authentifizierte Benutzer in der Besprechung anwesend sind.

|Zulassen, dass anonyme Personen eine Besprechung starten  |Personen automatisch zulassen |Verhalten bei Teilnahme anonymer Personen |
|---------|---------|---------|
|Wahr    | Jeder      | Direkt teilnehmen         |
|   | Jeder in Ihrer Organisation       | Im Wartebereich warten        |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen       | Im Wartebereich warten         |
|Falsch    | Jeder        | Direkt teilnehmen        |
|   | Jeder in Ihrer Organisation     | Im Wartebereich warten        |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen      | Im Wartebereich warten         |

Hier sehen Sie das Verhalten bei Teilnahme anonymer Personen, wenn keine authentifizierten Benutzer in der Besprechung anwesend sind.

|Zulassen, dass anonyme Personen eine Besprechung starten |Personen automatisch zulassen  |Verhalten bei Teilnahme anonymer Personen |
|---------|---------|---------|
|Wahr    | Jeder      | Direkt teilnehmen         |
|   | Jeder in Ihrer Organisation       | Im Wartebereich warten        |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen       | Im Wartebereich warten         |
|Falsch    | Jeder        | Im Wartebereich warten. Benutzer werden automatisch zugelassen, wenn der erste authentifizierte Benutzer an der Besprechung teilnimmt.        |
|   | Jeder in Ihrer Organisation     |Im Wartebereich warten         |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen      | Im Wartebereich warten         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a>Einwählbenutzern das Umgehen des Wartebereichs gestatten (in Kürze verfügbar)

Hierbei handelt es sich um eine organisatorspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob Personen, die sich per Telefon in die Besprechung einwählen, direkt an der Besprechung teilnehmen oder im Wartebereich warten – unabhängig von der Einstellung **Personen automatisch zulassen**.

Hier sehen Sie das Verhalten bei der Teilnahme von Personen, die sich per Telefon einwählen.

|Einwählbenutzern das Umgehen des Wartebereichs gestatten  |Benutzer automatisch zulassen  |Verhalten bei der Teilnahme von Personen, die sich per Telefon einwählen. |
|---------|---------|---------|
|Wahr    | Jeder      | Direkt teilnehmen         |
|   | Jeder in Ihrer Organisation       | Direkt teilnehmen        |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen       | Direkt teilnehmen         |
|Falsch    | Jeder        | Direkt teilnehmen        |
|   | Jeder in Ihrer Organisation     |Im Wartebereich warten         |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen      | Im Wartebereich warten         |

### <a name="allow-organizers-to-override-lobby-settings-coming-soon"></a>Organisatoren das Außerkraftsetzen von Wartebereichseinstellungen gestatten (in Kürze verfügbar)

Hierbei handelt es sich um eine organisatorspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob der Besprechungsorganisator beim Planen einer Besprechung die Wartebereichseinstellungen außer Kraft setzen kann, die ein Administrator in den Einstellungen **Personen automatisch zulassen** und **Einwählbenutzern das Umgehen des Wartebereichs gestatten** festgelegt hat. 

Besprechungsorganisatoren können in der Besprechungseinladung auf **Besprechungsoptionen** klicken, um die Wartebereichseinstellungen für jede von Ihnen geplante Besprechung zu ändern. 

Hier erfahren Sie, wie sich diese Einstellung darauf auswirkt, ob der Besprechungsorganisator die Einstellung **Personen automatisch zulassen** für jede Besprechung, die er plant, ändern kann.

|Organisatoren das Außerkraftsetzen von Wartebereichseinstellungen gestatten  |Personen automatisch zulassen  |Verhalten |
|---------|---------|---------|
|Wahr    | Jeder      | Der Organisator kann die Einstellung in einen beliebigen anderen Wert ändern. |
|   | Jeder in Ihrer Organisation       | Der Organisator kann die Einstellung in einen beliebigen anderen Wert ändern.|
|   | Jeder in Ihrer Organisation und in Verbundorganisationen       | Der Organisator kann die Einstellung in einen beliebigen anderen Wert ändern.         |
|Falsch    | Jeder        | Der Organisator kann die Einstellung in einen beliebigen anderen Wert ändern.|
|   | Jeder in Ihrer Organisation     |Der Organisator kann die Einstellung auf **Jeder in Ihrer Organisation** ändern. |
|   | Jeder in Ihrer Organisation und in Verbundorganisationen      | Der Organisator kann die Einstellung für den Wartebereich nicht außer Kraft setzen. |

Hier erfahren Sie, wie sich diese Einstellung darauf auswirkt, ob der Besprechungsorganisator die Einstellung **Einwählbenutzern das Umgehen des Wartebereichs gestatten** für jede Besprechung, die er plant, ändern kann.
    
|Organisatoren das Außerkraftsetzen von Wartebereichseinstellungen gestatten  |Einwählbenutzern das Umgehen des Wartebereichs gestatten  |Verhalten |
|---------|---------|---------|
|Wahr    |  Wahr        | Der Organisator kann die Einstellung auf „Falsch“ ändern.       |
|Wahr      | Falsch         | Der Organisator kann die Einstellung auf „Wahr“ ändern.        |
|Falsch     | Wahr        |Der Organisator kann die Einstellung auf „Falsch“ ändern.         |
|Falsch      |Falsch          |Der Organisator kann die Einstellung für den Wartebereich nicht außer Kraft setzen und kann Einwählbenutzern nicht erlauben, den Wartebereich zu umgehen.        |

[Vollständiger Artikel](meeting-policies-in-teams.md)

## <a name="related-topics"></a>Verwandte Themen
[Messaging-Richtlinien in Teams](messaging-policies-in-teams.md)

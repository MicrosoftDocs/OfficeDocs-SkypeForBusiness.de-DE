---
title: Verwalten von Besprechungsrichtlinien
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 03/22/2019
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
ms.openlocfilehash: a31f663a7714a0a5af09e6fddd9436e710582fa1
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517200"
---
# <a name="manage-meeting-policies-in-teams"></a>Verwalten von Besprechungsrichtlinien in Teams

::: zone target="docs"
Besprechungsrichtlinien werden verwendet, um die Steuerung der Features, die an die Teilnehmer bei Besprechungen, die von Benutzern in Ihrer Organisation geplant sind verfügbar sind. Nachdem Sie eine Richtlinie erstellen und Ihre Änderungen vornehmen, können Sie die Richtlinie Benutzer zuweisen. 

Standardmäßig wird eine Richtlinie mit dem Namen Global (Org geltende Standard) erstellt. Alle Benutzer in Ihrer Organisation werden standardmäßig diese besprechungsrichtlinie zugewiesen werden. Sie können entweder Änderungen an dieser Richtlinie vornehmen oder einen oder mehrere benutzerdefinierte Richtlinien erstellen und Benutzer zuweisen. Wenn Sie eine benutzerdefinierte Richtlinie erstellen, können Sie zulassen oder verhindern, dass bestimmte Features für die Benutzer verfügbar wird, und weisen Sie es an einen oder mehrere Benutzer die Einstellungen angewendet werden. 

## <a name="change-or-create-a-meeting-policy"></a>Ändern Sie oder erstellen Sie eine besprechungsrichtlinie

Zum Ändern oder erstellen eine besprechungsrichtlinie, wechseln Sie zur **Microsoft-Teams-Verwaltungskonsole** > **Besprechungen** > **Besprechungsrichtlinien**. Wählen Sie eine Richtlinie aus der Liste aus, oder wählen Sie **neue Richtlinie**. Wählen Sie Ihre Einstellungen, und wählen Sie dann auf **Speichern**.

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
 
 
## <a name="user-policy-settings"></a>Benutzerrichtlinieneinstellungen

Wenn Sie eine vorhandene Richtlinie auf der Seite **Besprechungsrichtlinien** auswählen oder **neue Richtlinie** für eine neue Richtlinie hinzuzufügen, können Sie die folgenden Einstellungen konfigurieren.

### <a name="new-meeting-policy-name-and-description"></a>Neue Name und Beschreibung der Besprechung
   - **Name** Dies ist der Name der Richtlinie, die auf der Seite **Besprechungsrichtlinien** angezeigt wird. Es kann nicht länger als 64 Zeichen oder Sonderzeichen enthalten. Beachten Sie, dass eine vorhandene Richtlinie Name nicht geändert werden kann.
   - **Beschreibung** Sie können in eine benutzerfreundliche Beschreibung für die Richtlinie hinzufügen, die Sie erstellen. Das ist hilfreich, wenn Sie eine Richtlinie für eine Gruppe von Benutzern zuweisen möchten.
::: zone-end 

<a name="bkgeneral"> </a>
### <a name="general"></a>Allgemein
   - **Sofortbesprechungen zulassen** Aktivieren Sie dies ansetzt, kann die Funktion "Jetzt besprechen" für Benutzer verfügbar sein, die an Besprechungen teilnehmen.
   - **Zulassen des Outlook-add-ins** Aktivieren Sie dies können Benutzer, die die Richtlinie zugewiesen haben Outlook-add-in zur Verfügung, wenn sie Besprechungen planen.
   - **DDE-Kanal zulassen Besprechung planen.** Aktivieren Sie dies können Channel-Besprechung planen.
   - **Planen von privaten Besprechungen zulassen** Aktivieren Sie dies ermöglicht Benutzern, die private Konferenzen planen einer Besprechung teilnehmen.

<a name="bkaudioandvideo"> </a>

### <a name="audio--video"></a>Audio & video
   - **Lautschrift zulassen** Wenn Sie diese aktivieren, werden Umsetzung der Besprechung für Benutzer verfügbar.
   - **Aufzeichnen von Cloud zulassen** Aktivieren Sie dies können Aufzeichnungen in der Cloud gespeichert werden soll.
   - **Zulassen von IP-video** Aktivieren Sie dies kann IP-Videos während einer Besprechung ansetzt.
   - **Media Bitrate (Kbit/s)** Sie können die Bitrate für Besprechungen festlegen. Der Standardwert beträgt 50 MB.

<a name="bkcontentsharing"> </a>

### <a name="content-sharing"></a>Gemeinsame Nutzung von Inhalten
   - **Bildschirmfreigabe Modus** Sie können den Modus für die Bildschirmfreigabe auswählen. Dabei wird die Größe des Bildschirms handeln, die während einer Besprechung verwendet werden, die ein Benutzer mit der Richtlinie zugewiesen verwenden können.
   - **Ermöglichen ein Teilnehmers zu gewähren oder Anfordern der Steuerung** Dadurch werden alle Teilnehmer an einer Besprechung und dessen Bildschirmfreigabe Steuerung anfordern.
   - **Ermöglichen Sie einen externen Teilnehmer zu gewähren oder Anfordern der Steuerung** Dies ermöglicht einen extern (kein Bestandteil Ihrer Organziation jemand) Teilnehmer zu übergeben und dessen Steuerung einer Besprechung anfordern, wenn der Bildschirm gemeinsam genutzt wird.
   - **Zulassen von PowerPoint-Freigabe** Wenn Sie diese aktivieren, können Benutzer, die Besprechungstermine PowerPoint-Folienstapel während einer Besprechung freigeben.
   - **Whiteboard zulassen** Wenn Sie diese aktivieren, wird das Whiteboard an die Teilnehmer während einer Besprechung verfügbar sein.
   - **Freigegebene Notizen zulassen** Wenn Sie diese aktivieren, werden die freigegebene Notizen an die Teilnehmer während einer Besprechung verfügbar sein.

<a name="bkparticipantsandguests"> </a>

### <a name="participants--guests"></a>Teilnehmer & Gäste
   - **Zulassen von Personen, die sich einwählen, um eine Besprechung zu starten.** Sie können auf Aktivieren oder deaktivieren, wenn Sie Besucher authentifiziert wurde noch nicht, da sie gewählt haben, in über das Telefon an eine Besprechung starten möchten.
   - **Automatisch Personen zulassen** Bestimmt, welche Arten von Teilnehmern automatisch werden von diesem Benutzer organisierte Besprechungen hinzugefügt werden. Legen Sie den "Jede Person in einer Organisation" Besprechungen platzieren Sie alle externen Benutzer in der Lobby, aber alle Benutzer im Unternehmen Teilnahme an der Besprechung sofort zulassen möchten. Legen Sie dies auf "Jeder", wenn Sie standardmäßig anonyme Benutzer zulassen möchten. Legen Sie den "Jede Person in Ihrer Organisation und Partnerorganisationen" Besprechungen Verbundbenutzer wie Ihres Unternehmens Benutzer teilnehmen, aber setzen Sie alle externen Benutzer in einer Wartebereich zulassen möchten.

[Vollständigen Artikel](meeting-policies-in-teams.md)

### <a name="related-topics"></a>Verwandte Themen
[Messagingrichtlinien in Teams](messaging-policies-in-teams.md)

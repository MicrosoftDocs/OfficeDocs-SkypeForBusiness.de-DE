---
title: Verwalten, wer sofort Besprechungen starten und Besprechungen planen kann
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Erfahren Sie, wie Sie die Richtlinieneinstellungen für Teams-Besprechungen verwenden, um zu steuern, wer sofort Besprechungen starten und Besprechungen planen kann.
ms.openlocfilehash: 6736ecd20ef4b0e9eb082e83bd8212597da5f7ab
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466289"
---
# <a name="manage-who-can-start-instant-meetings-and-schedule-meetings"></a>Verwalten, wer sofort Besprechungen starten und Besprechungen planen kann

Als Administrator können Sie einschränken, welche Benutzer sofort Besprechungen starten und Besprechungen in Teams planen können. Dies kann aus Datenschutz- und Sicherheitsgründen besonders hilfreich sein, wenn Sie möglicherweise nicht möchten, dass bestimmte Benutzer Besprechungen einrichten.

Die Besprechungsrichtlinieneinstellungen sind standardmäßig aktiviert. Diese Einstellungen finden Sie im Teams Admin Center unter den **Richtlinien für Besprechungsbesprechungen** > .

- **Besprechungen jetzt in Kanälen**: Steuert, ob ein Benutzer eine sofort Besprechung in einem Kanal starten kann.
- **Planung von Kanalbesprechungen**: Steuert, ob ein Benutzer eine Besprechung in einem Kanal planen kann.
- **Planung privater Besprechungen**: Steuert, ob ein Benutzer eine private Besprechung in Teams planen kann. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.
- **Outlook-Add-In**: Steuert, ob ein Benutzer eine private Besprechung von Outlook aus planen kann. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.
- **Besprechungen jetzt in privaten Besprechungen**: Steuert, ob ein Benutzer eine sofortige private Besprechung starten kann.

> [!NOTE]
> Wenn die Besprechung von einer Stellvertretung gesendet wurde, der die Berechtigung zum Senden von Besprechungseinladungen im Namen einer anderen Person, z. B. eines Vorgesetzten, erteilt wurde, wird die Besprechungsrichtlinieneinstellung auf die Person angewendet, die die Berechtigung erteilt hat (der Vorgesetzte).

## <a name="channel-meetings"></a>Kanalbesprechungen

Wenn Sie Complianceanforderungen haben, die nur bestimmte Personen dazu verpflichten, Sofortkanalbesprechungen zu starten und Kanalbesprechungen zu planen, können Sie Ihre Besprechungsrichtlinie erstellen oder aktualisieren, um diese Einstellungen einzuschränken. Sie können dann eine separate Richtlinie erstellen, die Benutzern zugeordnet ist, die Sie sofort kanalbesprechungen starten und Kanalbesprechungen planen möchten.

1. Wechseln Sie im Teams Admin Center zu den **Richtlinien für Besprechungsbesprechungen** > , und wählen Sie die Richtlinie aus, die Sie aktualisieren möchten. Klicken Sie auf **"Hinzufügen"**, um eine neue Richtlinie zu erstellen.
1. Schalten **Sie unter "Allgemein**" Folgendes um:
    1. Wenn Sie einschränken möchten, wer sofort Besprechungen in einem Kanal starten kann, schalten **Sie "Jetzt besprechen" in Kanälen** auf **"Aus" um**.
    1. Wenn Sie einschränken möchten, wer Besprechungen in einem Kanal planen kann, schalten Sie die **Kanalbesprechungsplanung** auf **"Aus**" um.
1. Klicken Sie unten auf der Seite auf **"Speichern** ".

## <a name="private-meetings"></a>Private Besprechungen

Wenn Sie Complianceanforderungen haben, die nur bestimmte Personen dazu verpflichten, sofort private Besprechungen zu starten und private Besprechungen zu planen, können Sie Ihre Besprechungsrichtlinien erstellen oder aktualisieren, um diese Einstellungen einzuschränken. Sie können dann eine separate Richtlinie erstellen, die Benutzern zugeordnet ist, die Sofortbesprechungen starten und private Besprechungen planen möchten.

1. Wechseln Sie im Teams Admin Center zu den **Richtlinien für Besprechungsbesprechungen** > , und wählen Sie die Richtlinie aus, die Sie aktualisieren möchten. Klicken Sie auf **"Hinzufügen"**, um eine neue Richtlinie zu erstellen.
1. Schalten **Sie unter "Allgemein**" Folgendes um:
    1. Wenn Sie einschränken möchten, wer sofort private Besprechungen starten kann, schalten **Sie "Jetzt in privaten Besprechungen besprechen** " auf **"Aus" um**.
    1. Wenn Sie einschränken möchten, wer private Besprechungen in einem Kanal planen kann, schalten Sie sowohl die **Planung privater Besprechungen** als auch **das Outlook-Add-In auf** **"Aus" um**.
1. Klicken Sie unten auf der Seite auf **"Speichern** ".

## <a name="turning-off-meeting-policy-settings"></a>Deaktivieren der Besprechungsrichtlinieneinstellungen

Nachdem eine dieser Besprechungsrichtlinieneinstellungen deaktiviert wurde, kann jeder der Richtlinie zugewiesene Benutzer keine Besprechungen dieses Typs starten oder planen. Die Besprechungsbeitrittslinks und Konferenz-IDs aller vorhandenen Besprechungen dieses Typs, die der Benutzer zuvor gestartet oder geplant hatte, funktionieren nicht. (Die Unterhaltungen, Dateien, Whiteboards, Aufzeichnungen, Transkriptionen und andere Inhalte im Zusammenhang mit der Besprechung werden beibehalten, und die Benutzer können weiterhin darauf zugreifen.)

Wenn eine Besprechungsrichtlinieneinstellung deaktiviert und dann erneut für einen Benutzer aktiviert ist, werden alle zuvor geplanten Besprechungen aktiv, die vom Benutzer organisiert wurden, und Personen können über den Besprechungsbeitrittslink oder per Telefon daran teilnehmen.

## <a name="related-topics"></a>Verwandte Themen

[Ändern des Ablaufdatums der Besprechung – Endbenutzersteuerelemente](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-overview.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](policy-assignment-overview.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Limits und Spezifikationen für Microsoft Teams](/microsoftteams/limits-specifications-teams)

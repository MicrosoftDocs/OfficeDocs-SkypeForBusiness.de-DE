---
title: Verwalten von Besprechungsrichtlinien in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie die Einstellungen für Besprechungsrichtlinien in Microsoft Teams verwalten und verwenden können, um die Features zu steuern, die Besprechungsteilnehmern für von Benutzern geplante Besprechungen zur Verfügung stehen.
ms.openlocfilehash: f471d9513995a13eb32eaacd118cd2f3874cda7c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627337"
---
# <a name="manage-meeting-policies-in-microsoft-teams"></a>Verwalten von Besprechungsrichtlinien in Microsoft Teams

<a name="bkautomatically-admit-people"> </a>

<a name="bkallow-a-participant-to-give-or-request-control"> </a>

<a name="bkallow-transcription"> </a>

Besprechungsrichtlinien werden verwendet, um die Features zu steuern, die Besprechungsteilnehmern für Besprechungen, die von Benutzern in Ihrer Organisation geplant werden, zur Verfügung stehen. Sie können die globale (standardmäßig organisationsweit geltende) Richtlinie verwenden, oder benutzerdefinierte Richtlinien erstellen und diese gezielt zuweisen. Besprechungsrichtlinien werden im Microsoft Teams Admin Center oder mithilfe von [PowerShell](teams-powershell-overview.md) verwaltet.

> [!NOTE]
> Informationen zur Verwendung von Rollen zum Verwalten der Berechtigungen von Besprechungsmoderatoren und -teilnehmern finden Sie unter [Rollen in einer Microsoft Teams-Besprechung](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Sie können Richtlinien, die sich auf die Benutzererfahrung vor, während oder nach einer Besprechung auswirken, auf folgende Weise implementieren.

|Implementierungstyp  |Beschreibung  |
|---------|---------|
|Organisatorspezifische Richtlinie    |Wenn Sie eine organisatorspezifische Richtlinie implementieren, erben alle Besprechungsteilnehmer die Richtlinie des Organisators. So ist beispielsweise **Personen automatisch zulassen** eine organisatorspezifische Richtlinie, die bei Besprechungen, die vom Nutzer, der die Richtlinie zugewiesen hat, geplant worden sind, steuert, ob Benutzer an der Besprechung direkt teilnehmen oder in der bis zum Beginn Wartebereich bleiben.          |
|Benutzerspezifische Richtlinie    |Wenn Sie eine benutzerspezifische Richtlinie implementieren, gilt nur diese Richtlinie, um bestimmte Features für den Organisator und/oder die Besprechungsteilnehmer einzuschränken. So ist beispielsweise **Sofortbesprechung in Kanälen zulassen** eine benutzerspezifische Richtlinie.     |
|Organisator- und benutzerspezifisch     |Wenn Sie eine Kombination aus einer organisatorspezifischen und einer benutzerspezifischen Richtlinie implementieren, sind bestimmte Features für Besprechungsteilnehmer basierend auf Ihrer Richtlinie und der Richtlinie des Organisators eingeschränkt. So ist beispielsweise **Cloud-Aufnahme zulassen** eine organisatorspezifische und benutzerspezifische Richtlinie. Aktivieren Sie diese Einstellung, um es dem Besprechungsorganisator und den Teilnehmern zu ermöglichen, eine Aufnahme zu starten und zu beenden.

Sie können die Einstellungen in der globalen Richtlinie bearbeiten oder eine oder mehrere benutzerdefinierte Richtlinien erstellen und zuweisen. Für Benutzern in Ihrer Organisation gilt die globale Richtlinie, es sei denn, Sie erstellen eine benutzerdefinierte Richtlinie und weisen ihnen diese zu.

> [!NOTE]
> Die Schaltfläche "Besprechungsdetails" ist verfügbar, wenn für einen Benutzer die Audiokonferenz-Lizenzen aktiviert sind oder er zu Audiokonferenzen zugelassen ist. Andernfalls sind die Besprechungsdetails nicht verfügbar.

## <a name="create-a-custom-meeting-policy"></a>Erstellen einer benutzerdefinierten Besprechungsrichtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Besprechungen** > **Besprechungsrichtlinien**.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein. Der Name darf keine Sonderzeichen enthalten und maximal 64 Zeichen lang sein.
4. Wählen Sie die gewünschten Einstellungen aus.
5. Klicken Sie auf **Speichern**.

Nehmen wir beispielsweise an, Sie haben eine Gruppe von Nutzern, und Sie möchten die Bandbreite begrenzen, die für Ihre Besprechung erforderlich ist. Sie erstellen dann eine neue benutzerdefinierte Richtlinie namens „begrenzte Bandbreite“ und deaktivieren die folgenden Einstellungen:

Unter **Audio & Video**:

- Deaktivieren Sie Cloud-Aufzeichnung zulassen.
- Deaktivieren Sie IP-Video zulassen.

Unter **Inhaltsfreigabe**:

- Deaktivieren Sie den Bildschirmfreigabemodus.
- Deaktivieren Sie Whiteboard zulassen.
- Deaktivieren Sie Freigegebene Notizen zulassen.

Weisen Sie dann die Richtlinie den Nutzern zu.

## <a name="edit-a-meeting-policy"></a>Bearbeiten einer Besprechungsrichtlinie

Sie können die globale Standardrichtlinie oder eine von Ihnen erstellte benutzerdefinierte Richtlinie jederzeit bearbeiten.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Besprechungen** > **Besprechungsrichtlinien**.
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie nun die gewünschten Änderungen vor.
4. Klicken Sie auf **Speichern**.

> [!NOTE]
> Einem Benutzer kann jeweils nur eine Besprechungsrichtlinie zugewiesen werden.

## <a name="assign-a-meeting-policy-to-users"></a>Benutzern eine Besprechungsrichtlinie zuweisen

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> Sie können eine Richtlinie nicht löschen, solange Sie Benutzern zugewiesen ist. Sie müssen allen betroffenen Benutzern erst eine andere Richtlinie zuweisen, bevor Sie die ursprüngliche Richtlinie löschen können.

## <a name="meeting-policy-settings"></a>Einstellungen für Besprechungsrichtlinien

Wenn Sie auf der Seite **Besprechungsrichtlinien** eine vorhandene Richtlinie oder **Hinzufügen** auswählen, um eine neue Richtlinie hinzuzufügen, können Sie die folgenden Einstellungen konfigurieren.

- [Allgemein](meeting-policies-in-teams-general.md)
- [Audio & Video](meeting-policies-audio-and-video.md)
- [Inhaltsfreigabe](meeting-policies-content-sharing.md)
- [Teilnehmer & Gäste](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)
- [Entfernen der Microsoft Teams-Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern](meeting-policies-restricted-anonymous-access.md)
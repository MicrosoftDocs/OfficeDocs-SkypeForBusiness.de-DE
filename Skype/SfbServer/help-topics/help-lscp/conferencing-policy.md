---
title: Konferenzrichtlinie
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: Eine Konferenzrichtlinie definiert die Funktionen, die Benutzern während einer Konferenz (auch als Besprechung bezeichnet) zur Verfügung stehen.
ms.openlocfilehash: 6d69c463a9aa8a1e151b0787dfbfebf4e24fb693
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115365"
---
# <a name="conferencing-policy"></a>Konferenzrichtlinie

Eine Konferenzrichtlinie definiert die Funktionen, die Benutzern während einer Konferenz (auch als Besprechung bezeichnet) zur Verfügung stehen.

Zu den Konferenzrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Standort- und Benutzerrichtlinien:

- **Globale Richtlinie:** Die globale Richtlinie wird standardmäßig erstellt. Sie können die globale Richtlinie bearbeiten, jedoch nicht löschen. Wenn Sie versuchen, die globale Richtlinie zu entfernen, werden alle Einstellungen auf die Standardwerte zurückgesetzt.

- **Websiterichtlinien (optional):** Sie können eine oder mehrere Websitekonferenzrichtlinien erstellen, die jeweils für einen bestimmten Standort gelten. Standortrichtlinien setzen die globale Richtlinie außer Kraft.

- **Benutzerrichtlinien (optional):** Sie können eine oder mehrere Benutzerkonferenzrichtlinien erstellen, die jeweils für einen bestimmten Benutzer oder eine bestimmte Gruppe von Benutzern gelten. Benutzerrichtlinien setzen die globale Richtlinie und Standortrichtlinien außer Kraft.

Auf der Seite **Konferenzrichtlinie** wird eine Liste mit allen Konferenzrichtlinien angezeigt, die für Ihre Organisation definiert sind.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Konferenzrichtlinie** können Sie die folgenden Aufgaben ausführen:

- Erstellen einer neuen Konferenzrichtlinie für Standorte oder Benutzer

- Ändern der globalen Richtlinie oder einer vorhandenen Standort- oder Benutzerrichtlinie

- Löschen einer Standort- oder Benutzerrichtlinie

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Befehle der Seite beschrieben.

- **Neu** Startet eine neue Websitekonferenzrichtlinie oder Benutzerkonferenzrichtlinie.

- **Bearbeiten** Öffnet die ausgewählte Konferenzrichtlinie, um sie zu bearbeiten, wählt alle Konferenzrichtlinien in der Liste aus oder löscht die ausgewählte Websiterichtlinie oder Benutzerrichtlinie.

    > [!NOTE]
    > Für die globale Richtlinie werden die Einstellungen mit **Löschen** auf die Standardwerte zurückgesetzt.

- **Aktualisieren** Aktualisiert die Liste der Konferenzrichtlinien.

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Identifiziert die Konferenzrichtlinie.

- **Bereich** Gibt den Bereich der Konferenzrichtlinie an: global, standort- oder benutzer.

- **Datenzusammenarbeit** Überprüft, ob die Konferenzrichtlinie angibt, dass die Datenzusammenarbeit in Konferenzen zulässig ist.

- **Anwendungsfreigabe** Überprüft, ob die Konferenzrichtlinie angibt, dass die Anwendungsfreigabe in Konferenzen zulässig ist.

- **Audio** Überprüft, ob die Konferenzrichtlinie angibt, dass Audio in Konferenzen zulässig ist.

- **Video** Überprüft, ob die Konferenzrichtlinie angibt, dass Video in Konferenzen zulässig ist.

- **PSTN** Überprüft, ob die Konferenzrichtlinie angibt, dass PSTN-Einwahlkonferenzen zulässig sind.

- **Aufzeichnung** Überprüft, ob die Konferenzrichtlinie angibt, dass die Aufzeichnung in Konferenzen zulässig ist.

Ausführliche Informationen zu den Konferenzfunktionen finden Sie unter [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Konferenzrichtlinien finden Sie unter [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) in der Betriebsdokumentation.
---
title: Standortrichtlinie
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: Anhand von Standortrichtlinien wird bestimmt, ob E9-1-1 aktiviert ist, wie es verwendet wird und wie Standortinformationen für Benutzer und Kontakte verwendet werden.
ms.openlocfilehash: 9d22f76f65c84c12d16a2f8668882b2db16b7923
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220326"
---
# <a name="location-policy"></a>Standortrichtlinie

Anhand von Standortrichtlinien wird bestimmt, ob E9-1-1 aktiviert ist, wie es verwendet wird und wie Standortinformationen für Benutzer und Kontakte verwendet werden.

Zu den Standortrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Standort- und Benutzerrichtlinien:

- **Globale Richtlinie:** Die globale Richtlinie wird standardmäßig erstellt. Sie können die globale Richtlinie bearbeiten, jedoch nicht löschen. Wenn Sie versuchen, die globale Richtlinie zu entfernen, werden alle Einstellungen auf die Standardwerte zurückgesetzt.

- **Websiterichtlinien (optional):** Sie können eine oder mehrere Website Speicherort Richtlinien erstellen, von die jeder auf eine bestimmte Website angewendet wird. Standortrichtlinien setzen die globale Richtlinie außer Kraft.

- **Richtlinien für Benutzer (optional):** Sie können eine oder mehrere Benutzer Standortrichtlinien erstellen, von die jedes auf einen bestimmten Benutzer oder eine Gruppe von Benutzern angewendet wird. Benutzerrichtlinien setzen die globale Richtlinie und Standortrichtlinien außer Kraft.

> [!NOTE]
> Außerdem können Sie Standortrichtlinien Netzwerkstandorten hinzufügen, wobei es sich um Gruppen von Subnetzen handelt. Netzwerkstandorten zugewiesene Standortrichtlinien haben Vorrang vor allen anderen Benutzerrichtlinien. Weitere Informationen zum Zuweisen von Standortrichtlinien zu Netzwerkstandorten mithilfe von Cmdlets finden Sie unter [Hinzufügen einer ortungsrichtlinie zu einem Netzwerkstandort in Skype für Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Weitere Informationen zur Verwendung von Skype Business Server-Systemsteuerung einem Netzwerkstandort eine Standortrichtlinie zugewiesen finden Sie unter [Konfigurieren von Netzwerkstandorten](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).

Auf der Seite **Standortrichtlinie** wird eine Liste mit allen Standortrichtlinien angezeigt, die für Ihre Organisation definiert sind.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Standortrichtlinie** können Sie die folgenden Aufgaben ausführen:

- Erstellen einer neuen Standortrichtlinie für Standorte oder Benutzer

- Ändern der globalen Richtlinie oder einer vorhandenen Standort- oder Benutzerrichtlinie

- Löschen einer Standort- oder Benutzerrichtlinie

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Befehle der Seite beschrieben.

- **Neue** Ermöglicht die Erstellung einer neuen Standortrichtlinie oder Standortrichtlinie.

- **Bearbeiten** Öffnet die ausgewählte Standortrichtlinie zur Bearbeitung, wählt alle Standortrichtlinien in der Liste aus oder löscht die ausgewählte Standort- oder Benutzerrichtlinie.

    > [!NOTE]
    > Für die globale Richtlinie werden die Einstellungen mit **Löschen** auf die Standardwerte zurückgesetzt.

- **Aktualisieren** Aktualisiert die Liste mit den Standortrichtlinien.

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Name** Identifiziert die Standortrichtlinie an.

- **Bereich** Gibt den Bereich der Standortrichtlinie: global, Standort oder Benutzer.

- **E9-1-1** Überprüft, wenn der Benutzer, denen diese Standortrichtlinie zugewiesen für E9-1-1 aktiviert sind.

- **Speicherort** Gibt an, ob Benutzer Standortinformationen eingeben, wenn deren Clients bei Skype für Business Server an einem neuen Standort registriert wird, und ob sie einen Haftungsausschluss angezeigt, wenn sie die Meldung schließen, ohne Eingabe von Standortinformationen aufgefordert werden.

- **PSTN-Verwendung** Gibt das Telefonfestnetz (PSTN) Netzwerkauslastung, das verwendet wird, zum Bestimmen der VoIP-Route zur Weiterleitung von Notrufen von Clients, die mit diesem Profil verwendet.

- **Anzahl der E9-1-1** Gibt die Nummer, die zum Erreichen der notrufdienste gewählt wird.

- **Maske E9-1-1** Gibt eine Zahl, die ein Benutzer wählt, die dann in die Notrufnummer Nummer übersetzt wird.

Weitere Informationen zu Enterprise-VoIP notrufunterstützung Features und Funktionen finden Sie unter [Übersicht über E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Standortrichtlinien finden Sie in der Betriebsdokumentation unter [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx).



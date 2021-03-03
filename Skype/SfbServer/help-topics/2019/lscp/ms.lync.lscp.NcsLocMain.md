---
title: Ortungsrichtlinie
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: Anhand von Standortrichtlinien wird bestimmt, ob die erweiterten Notfalldienste aktiviert sind und wie sie verwendet werden und wie Standortinformationen für Benutzer und Kontakte verwendet werden.
ms.openlocfilehash: bb7a63e63864b3d342d37fd62b26f806434644b7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824785"
---
# <a name="location-policy"></a>Ortungsrichtlinie

Anhand von Standortrichtlinien wird bestimmt, ob die erweiterten Notfalldienste aktiviert sind und wie sie verwendet werden und wie Standortinformationen für Benutzer und Kontakte verwendet werden.

Zu den Standortrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Standort- und Benutzerrichtlinien:

- **Globale Richtlinie:** Die globale Richtlinie wird standardmäßig erstellt. Sie können die globale Richtlinie bearbeiten, jedoch nicht löschen. Wenn Sie versuchen, die globale Richtlinie zu entfernen, werden alle Einstellungen auf die Standardwerte zurückgesetzt.

- **Websiterichtlinien (optional):** Sie können eine oder mehrere Standortrichtlinien für Standorte erstellen, die jeweils für einen bestimmten Standort gelten. Standortrichtlinien setzen die globale Richtlinie außer Kraft.

- **Benutzerrichtlinien (optional):** Sie können eine oder mehrere Standortrichtlinien für Benutzer erstellen, die jeweils für einen bestimmten Benutzer oder eine Bestimmte Benutzergruppe gelten. Benutzerrichtlinien setzen die globale Richtlinie und Standortrichtlinien außer Kraft.

> [!NOTE]
> Außerdem können Sie Standortrichtlinien Netzwerkstandorten hinzufügen, wobei es sich um Gruppen von Subnetzen handelt. Netzwerkstandorten zugewiesene Standortrichtlinien haben Vorrang vor allen anderen Benutzerrichtlinien. Weitere Informationen zum Zuweisen von Standortrichtlinien zu Netzwerkstandorten mithilfe von Cmdlets finden Sie unter Hinzufügen einer Standortrichtlinie zu einem Netzwerkstandort [in Skype for Business Server.](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md) Weitere Informationen zur Verwendung der Skype for Business Server-Systemsteuerung zum Zuweisen einer Standortrichtlinie zu einem Netzwerkstandort finden Sie unter ["Konfigurieren von Netzwerkstandorten".](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)

Auf der Seite **Standortrichtlinie** wird eine Liste mit allen Standortrichtlinien angezeigt, die für Ihre Organisation definiert sind.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Standortrichtlinie** können Sie die folgenden Aufgaben ausführen:

- Erstellen einer neuen Standortrichtlinie für Standorte oder Benutzer

- Ändern der globalen Richtlinie oder einer vorhandenen Standort- oder Benutzerrichtlinie

- Löschen einer Standort- oder Benutzerrichtlinie

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Befehle der Seite beschrieben.

- **Neu** Startet eine neue Standortrichtlinie für Standorte oder Benutzer.

- **Bearbeiten** Öffnet die ausgewählte Standortrichtlinie, um sie zu bearbeiten, wählt alle Standortrichtlinien in der Liste aus oder löscht die ausgewählte Standort- oder Benutzerrichtlinie.

    > [!NOTE]
    > Für die globale Richtlinie werden die Einstellungen mit **Löschen** auf die Standardwerte zurückgesetzt.

- **Aktualisieren** Aktualisiert die Liste der Standortrichtlinien.

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Identifies the location policy.

- **Bereich** Gibt den Bereich der Standortrichtlinie an: global, Standort oder Benutzer.

- **E9-1-1** Aktiviert, wenn Benutzer, denen diese Standortrichtlinie zugewiesen ist, für E9-1-1 aktiviert sind.

- **Position** Gibt an, ob Benutzer zur Eingabe von Standortinformationen aufgefordert werden, wenn sich ihr Client bei Skype for Business Server an einem neuen Standort registriert, und ob ein Haftungsausschluss angezeigt wird, wenn sie die Eingabeaufforderung ohne Eingabe von Standortinformationen schließen.

- **PstN-Verwendung** Gibt die Verwendung des Telefonnetzes (Public Switched Telephone Network, PSTN) an, die verwendet wird, um die Sprachroute zu bestimmen, die zum Routen von Notrufen von Clients verwendet wird, die dieses Profil verwenden.

- **E9-1-1-Nummer** Gibt die Nummer an, die zum Erreichen der Notrufdienste gewählt wird.

- **E9-1-1-Maske** Gibt eine Nummer an, die ein Benutzer wählt, die dann in die Notrufnummer übersetzt wird.

Ausführliche Informationen zu Enterprise-VoIP und -funktionen finden Sie in der Übersicht über [E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Standortrichtlinien finden Sie unter [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in der Betriebsdokumentation.



---
title: Ortungsrichtlinie
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: Anhand von Standortrichtlinien wird bestimmt, ob die erweiterten Notfalldienste aktiviert sind und wie sie verwendet werden und wie Standortinformationen für Benutzer und Kontakte verwendet werden.
ms.openlocfilehash: a7173a4b7598d3645aeb9ddd02f7dcbaad88f585
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393997"
---
# <a name="location-policy"></a>Ortungsrichtlinie

Anhand von Standortrichtlinien wird bestimmt, ob die erweiterten Notfalldienste aktiviert sind und wie sie verwendet werden und wie Standortinformationen für Benutzer und Kontakte verwendet werden.

Zu den Standortrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Standort- und Benutzerrichtlinien:

- **Globale Richtlinie:** Die globale Richtlinie wird standardmäßig erstellt. Sie können die globale Richtlinie bearbeiten, jedoch nicht löschen. Wenn Sie versuchen, die globale Richtlinie zu entfernen, werden alle Einstellungen auf die Standardwerte zurückgesetzt.

- **Websiterichtlinien (optional):** Sie können eine oder mehrere Standortrichtlinien für Websites erstellen, die jeweils für einen bestimmten Standort gelten. Standortrichtlinien setzen die globale Richtlinie außer Kraft.

- **Benutzerrichtlinien (optional):** Sie können eine oder mehrere Standortrichtlinien für Benutzer erstellen, die jeweils für einen bestimmten Benutzer oder eine Benutzergruppe gelten. Benutzerrichtlinien setzen die globale Richtlinie und Standortrichtlinien außer Kraft.

> [!NOTE]
> Außerdem können Sie Standortrichtlinien Netzwerkstandorten hinzufügen, wobei es sich um Gruppen von Subnetzen handelt. Netzwerkstandorten zugewiesene Standortrichtlinien haben Vorrang vor allen anderen Benutzerrichtlinien. Ausführliche Informationen zum Zuweisen von Standortrichtlinien zu Netzwerkstandorten mithilfe von Cmdlets finden [Sie unter Hinzufügen einer Standortrichtlinie zu einem Netzwerkstandort in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Ausführliche Informationen zur Verwendung Skype for Business Server Systemsteuerung zum Zuweisen einer Standortrichtlinie zu einem Netzwerkstandort finden Sie unter ["Konfigurieren von Netzwerkstandorten"](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites).

Auf der Seite **Standortrichtlinie** wird eine Liste mit allen Standortrichtlinien angezeigt, die für Ihre Organisation definiert sind.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Standortrichtlinie** können Sie die folgenden Aufgaben ausführen:

- Erstellen einer neuen Standortrichtlinie für Standorte oder Benutzer

- Ändern der globalen Richtlinie oder einer vorhandenen Standort- oder Benutzerrichtlinie

- Löschen einer Standort- oder Benutzerrichtlinie

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Befehle der Seite beschrieben.

- **Neu** Startet eine neue Standortrichtlinie oder Standortrichtlinie für Benutzer.

- **Bearbeiten** Öffnet die ausgewählte Standortrichtlinie, um sie zu bearbeiten, wählt alle Standortrichtlinien in der Liste aus oder löscht die ausgewählte Standortrichtlinie oder Benutzerrichtlinie.

    > [!NOTE]
    > Für die globale Richtlinie werden die Einstellungen mit **Löschen** auf die Standardwerte zurückgesetzt.

- **Aktualisieren** Aktualisiert die Liste der Standortrichtlinien.

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Namen** Identifiziert die Standortrichtlinie.

- **Umfang** Gibt den Bereich der Standortrichtlinie an: global, Standort oder Benutzer.

- **E9-1-1** Überprüft, ob Benutzer, denen diese Standortrichtlinie zugewiesen ist, für E9-1-1 aktiviert sind.

- **Lage** Gibt an, ob Benutzer aufgefordert werden, Standortinformationen einzugeben, wenn sich ihr Client bei Skype for Business Server an einem neuen Standort registriert, und ob ein Haftungsausschluss angezeigt wird, wenn die Eingabeaufforderung ohne Eingabe von Standortinformationen geschlossen wird.

- **PSTN-Verwendung** Gibt die PSTN-Verwendung (Public Switched Telephone Network) an, die verwendet wird, um die VoIP-Route zu bestimmen, die zum Weiterleiten von Notrufen von Clients mit diesem Profil verwendet wird.

- **E9-1-1-Nummer** Gibt die Nummer an, die zum Erreichen der Notrufdienste gewählt wird.

- **E9-1-1-Maske** Gibt eine Nummer an, die ein Benutzer wählt, die dann in die Notrufnummer übersetzt wird.

Ausführliche Informationen zu Enterprise-VoIP Funktionen und Funktionen des Notfalldienstes finden Sie in der Planungsdokumentation [unter "Übersicht über E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1)". Ausführliche Informationen zur Verwendung von Standortrichtlinien finden Sie unter [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) in der Betriebsdokumentation.
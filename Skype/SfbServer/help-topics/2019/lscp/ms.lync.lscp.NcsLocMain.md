---
title: Standortrichtlinie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: Anhand von Standortrichtlinien wird bestimmt, ob E9-1-1 aktiviert ist, wie es verwendet wird und wie Standortinformationen für Benutzer und Kontakte verwendet werden.
ms.openlocfilehash: 82126acf09ed4e0cd1b98b20f22760f23038226c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41704610"
---
# <a name="location-policy"></a>Standortrichtlinie

Anhand von Standortrichtlinien wird bestimmt, ob E9-1-1 aktiviert ist, wie es verwendet wird und wie Standortinformationen für Benutzer und Kontakte verwendet werden.

Zu den Standortrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Standort- und Benutzerrichtlinien:

- **Globale Richtlinie:** Standardmäßig wird die globale Richtlinie erstellt. Sie können die globale Richtlinie bearbeiten, jedoch nicht löschen. Wenn Sie versuchen, die globale Richtlinie zu entfernen, werden alle Einstellungen auf die Standardwerte zurückgesetzt.

- **Website Richtlinien (optional):** Sie können eine oder mehrere Website Standortrichtlinien erstellen, die jeweils für eine bestimmte Website gelten. Standortrichtlinien setzen die globale Richtlinie außer Kraft.

- **Benutzerrichtlinien (optional):** Sie können eine oder mehrere Benutzerstandort Richtlinien erstellen, die jeweils für einen bestimmten Benutzer oder eine Gruppe von Benutzern gelten. Benutzerrichtlinien setzen die globale Richtlinie und Standortrichtlinien außer Kraft.

> [!NOTE]
> Außerdem können Sie Standortrichtlinien Netzwerkstandorten hinzufügen, wobei es sich um Gruppen von Subnetzen handelt. Netzwerkstandorten zugewiesene Standortrichtlinien haben Vorrang vor allen anderen Benutzerrichtlinien. Details zum Zuweisen von Standortrichtlinien zu Netzwerk Websites mithilfe von Cmdlets finden Sie unter [Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Details zur Verwendung der Skype for Business Server-Systemsteuerung zum Zuweisen einer Standortrichtlinie zu einer Netzwerk Website finden Sie unter [Konfigurieren von Netzwerkstandorten](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).

Auf der Seite **Standortrichtlinie** wird eine Liste mit allen Standortrichtlinien angezeigt, die für Ihre Organisation definiert sind.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Standortrichtlinie** können Sie die folgenden Aufgaben ausführen:

- Erstellen einer neuen Standortrichtlinie für Standorte oder Benutzer

- Ändern der globalen Richtlinie oder einer vorhandenen Standort- oder Benutzerrichtlinie

- Löschen einer Standort- oder Benutzerrichtlinie

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Befehle der Seite beschrieben.

- **Neu** Startet eine neue Website Standortrichtlinien-oder Benutzerstandort Richtlinie.

- **Bearbeiten** von Öffnet die ausgewählte Standortrichtlinie, um Sie zu bearbeiten, wählt alle Standortrichtlinien in der Liste aus oder löscht die ausgewählte Website Richtlinie oder Benutzerrichtlinie.

    > [!NOTE]
    > Für die globale Richtlinie werden die Einstellungen mit **Löschen** auf die Standardwerte zurückgesetzt.

- **Aktualisieren** Aktualisiert die Liste der Standortrichtlinien.

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Name** Identifiziert die Standortrichtlinie.

- **Bereich** Identifiziert den Bereich der Standortrichtlinie: Global, Site oder User.

- **E9-1-1** Überprüft, ob Benutzer, denen diese Standortrichtlinie zugewiesen ist, für E9-1-1 aktiviert sind.

- **Ort** Gibt an, ob Benutzer zur Eingabe von Standortinformationen aufgefordert werden, wenn sich der Client mit Skype for Business Server an einem neuen Speicherort registriert und ob er eine Verzichtserklärung erhält, wenn er die Eingabeaufforderung ohne Angabe von Standortinformationen versieht.

- **PSTN-Verwendung** Gibt die PSTN-Nutzung (Public Switched Telephone Network) an, die verwendet wird, um die VoIP-Route zu ermitteln, die für die Weiterleitung von Notrufen von Clients mit diesem Profil verwendet wird.

- **E9-1-1 Nummer** Gibt die Nummer an, die zum Erreichen von Notfalldiensten gewählt wurde.

- **E9-1-1-Maske** Gibt eine Zahl an, die ein Benutzer anwählt, die dann in die Notrufnummer übersetzt wird.

Ausführliche Informationen zu den Features und Funktionen des Enterprise-VoIP-Notfall Diensts finden Sie unter [Übersicht über E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Standortrichtlinien finden Sie in der Betriebsdokumentation unter [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx).



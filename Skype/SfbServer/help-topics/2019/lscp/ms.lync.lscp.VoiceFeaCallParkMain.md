---
title: Funktion zum Parken von Anrufen
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Wenn ein Anruf geparkt wird, wird er an eine temporäre Nummer weitergeleitet, bei der der Anruf gehalten wird, bis jemand ihn entgegennimmt oder ein Zeitüberschreitung auftritt. Sie müssen eine Tabelle mit den Bereichen von Durchwahlnummern konfigurieren, die Sie für geparkte Anrufe reservieren. Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist). Jeder Pool, in dem die Anwendung zum Parken von Anrufen ausgeführt wird, kann über einen oder mehrere Erweiterungsbereiche verfügen. Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.
ms.openlocfilehash: f37913066bb2bf0a0eb6eec767501a3b16534ec6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845698"
---
# <a name="call-park"></a>Parken von Anrufen

Wenn ein Anruf geparkt wird, wird er an eine temporäre Nummer weitergeleitet, bei der der Anruf gehalten wird, bis jemand ihn entgegennimmt oder ein Zeitüberschreitung auftritt. Sie müssen eine Tabelle mit den Bereichen von Durchwahlnummern konfigurieren, die Sie für geparkte Anrufe reservieren. Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist). Jeder Pool, in dem die Anwendung zum Parken von Anrufen ausgeführt wird, kann über einen oder mehrere Erweiterungsbereiche verfügen. Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.

Auf der Seite **zum Parken** von Anrufen wird eine Liste aller Nummernbereiche für das Parken von Anrufen angezeigt, die für Ihre Organisation definiert sind.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Anruf parken** können Sie die folgenden Aufgaben ausführen:

- Erstellen eines neuen Nummernbereichs

- Ändern eines vorhandenen Nummernbereichs

- Löschen eines Nummernbereichs

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Befehle der Seite beschrieben.

- **Neu** Startet einen neuen Nummernbereich für das Parken von Anrufen.

- **Bearbeiten** Öffnet den ausgewählten Nummernbereich zur Bearbeitung, wählt alle Nummernbereiche in der Liste aus oder löscht den ausgewählten Nummernbereich.

- **Aktualisieren** Aktualisiert die Liste der Nummernbereiche.

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Der eindeutige Name, der den Nummernbereich identifiziert.

- **Startbereich** Die Anfangsnummer des Bereichs.

- **Endbereich** Die Endnummer des Bereichs.

- **Ziel** Der vollqualifizierte Domänenname (FQDN) oder die Dienst-ID des Anwendungsdiensts, der die Anwendung zum Parken von Anrufen für den Nummernbereich hostet.

Ausführliche Informationen zu den Funktionen und Funktionen zum Parken von Anrufen finden Sie unter [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Ausführliche Informationen zum Arbeiten mit Nummernbereichen für das Parken von Anrufen finden Sie unter [Konfigurieren Telefon Nummernerweiterungen für das Parken von Anrufen.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)
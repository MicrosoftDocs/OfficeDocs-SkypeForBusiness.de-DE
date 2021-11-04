---
title: Funktion zum Parken von Anrufen
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Wenn ein Anruf geparkt wird, wird er an eine temporäre Nummer weitergeleitet, bei der der Anruf gehalten wird, bis jemand ihn entgegennimmt oder ein Zeitüberschreitung auftritt. Sie müssen eine Tabelle mit den Bereichen von Durchwahlnummern konfigurieren, die Sie für geparkte Anrufe reservieren. Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist). Jeder Pool, in dem die Anwendung zum Parken von Anrufen ausgeführt wird, kann über einen oder mehrere Erweiterungsbereiche verfügen. Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.
ms.openlocfilehash: cfbe98e0f432fc5be2b27979ab76d0436ae8343f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742302"
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

Ausführliche Informationen zu den Funktionen und Funktionen zum Parken von Anrufen finden Sie unter [Plan for Call Park in Skype for Business 2015.](../../plan-your-deployment/enterprise-voice-solution/call-park.md) Ausführliche Informationen zum Arbeiten mit Nummernbereichen für das Parken von Anrufen finden Sie unter [Konfigurieren Telefon Nummernerweiterungen für das Parken von Anrufen.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)
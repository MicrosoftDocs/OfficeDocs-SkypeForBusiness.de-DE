---
title: Funktion zum Parken von Anrufen
ms.reviewer: ''
ms.author: v-cichur
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
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Wenn ein Anruf geparkt wird, wird er an eine temporäre Nummer umgestellt, unter der der Anruf gehalten wird, bis er von einem Benutzer abgerufen wird oder ein Zeitfing vor sich geht. Sie müssen eine Tabelle mit den Durchwahlnummernbereichen konfigurieren, die Sie für geparkte Anrufe reservieren. Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist). Jeder Pool, in dem die Anwendung zum Parken von Anrufen ausgeführt wird, kann einen oder mehrere Durchlaufbereiche haben. Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.
ms.openlocfilehash: 7723b3bb3145725834059c73c0acc273fc67ca61
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800305"
---
# <a name="call-park"></a>Parken von Anrufen

Wenn ein Anruf geparkt wird, wird er an eine temporäre Nummer umgestellt, unter der der Anruf gehalten wird, bis er von einem Benutzer abgerufen wird oder ein Zeitfing vor sich geht. Sie müssen eine Tabelle mit den Durchwahlnummernbereichen konfigurieren, die Sie für geparkte Anrufe reservieren. Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist). Jeder Pool, in dem die Anwendung zum Parken von Anrufen ausgeführt wird, kann einen oder mehrere Durchlaufbereiche haben. Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.

Auf **der Seite zum Parken** von Anrufen wird eine Liste aller Nummernbereiche für das Parken von Anrufen angezeigt, die für Ihre Organisation definiert sind.

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

Weitere Informationen zu funktionen und Features zum Parken von Anrufen finden Sie unter [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Weitere Informationen zum Arbeiten mit Nummernbereichen zum Parken von Anrufen finden Sie unter "Konfigurieren von [Telefonnummernerweiterungen für das Parken von Anrufen".](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)



---
title: Parken von Anrufen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Wenn ein Anruf abgestellt wird, wird er an eine temporäre Rufnummer übertragen, in der der Anruf abgehalten wird, bis er von jemandem abgebucht wird, oder wenn der Anruf abläuft. Sie müssen eine Tabelle mit den Bereichen der Durchwahlnummern konfigurieren, die für geparkte Anrufe reserviert werden. Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist). Jeder Pool, auf dem die Anwendung "Parken" ausgeführt wird, kann einen oder mehrere Bereichs Erweiterungen aufweisen. Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.
ms.openlocfilehash: 1a7417ab525f8471b730dc177a993c3458750a3f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700300"
---
# <a name="call-park"></a>Parken von Anrufen

Wenn ein Anruf abgestellt wird, wird er an eine temporäre Rufnummer übertragen, in der der Anruf abgehalten wird, bis er von jemandem abgebucht wird, oder wenn der Anruf abläuft. Sie müssen eine Tabelle mit den Bereichen der Durchwahlnummern konfigurieren, die für geparkte Anrufe reserviert werden. Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist). Jeder Pool, auf dem die Anwendung "Parken" ausgeführt wird, kann einen oder mehrere Bereichs Erweiterungen aufweisen. Diese Bereiche müssen innerhalb der Bereitstellung eindeutig sein.

Auf der Seite " **Parken des Anrufs** " wird eine Liste aller für Ihre Organisation definierten Park Nummernbereiche angezeigt.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Anruf parken** können Sie die folgenden Aufgaben ausführen:

- Erstellen eines neuen Nummernbereichs

- Ändern eines vorhandenen Nummernbereichs

- Löschen eines Nummernbereichs

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Befehle der Seite beschrieben.

- **Neu** Startet einen neuen Anruf Park Nummernbereich.

- **Bearbeiten** von Öffnet den markierten Zahlenbereich für die Bearbeitung, wählt alle Nummernbereiche in der Liste aus oder löscht den markierten Zahlenbereich.

- **Aktualisieren** Aktualisiert die Liste der Nummernbereiche.

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Name** Der eindeutige Name, der den Zahlenbereich identifiziert.

- **Start Bereich** Die Anfangszahl des Bereichs.

- **Endbereich** Die letzte Zahl des Bereichs.

- **Ziel** Den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die Dienst-ID des Anwendungsdiensts, der die Anruf Park Anwendung für den Nummernbereich hostet.

Details zu den Funktionen und Funktionen des Anruf Parks finden Sie unter [Planen des Anruf Parks in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Details zum Arbeiten mit den Rufnummernbereichen des Anruf Parks finden Sie unter [Konfigurieren von Telefonnummern Erweiterungen für Park Anrufe](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).



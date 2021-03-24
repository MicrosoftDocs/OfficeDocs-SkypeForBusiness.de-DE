---
title: Parken von Anrufen Erstellen neuer oder Bearbeiten vorhandener Anrufe
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Nummernbereiche zum Parken von Anrufen definieren die temporären Nummern, in denen geparkte Anrufe gehalten werden, bis jemand sie abruft oder ein Zeit-Out hat.
ms.openlocfilehash: af2762f94800ef0db0d4e04fac6949be49104250
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097061"
---
# <a name="call-park-create-new-or-edit-existing"></a>Funktion zum Parken von Anrufen: Erstellen einer neuen oder Bearbeiten einer vorhandenen Funktion zum Parken von Anrufen

Nummernbereiche zum Parken von Anrufen definieren die temporären Nummern, in denen geparkte Anrufe gehalten werden, bis jemand sie abruft oder ein Zeit-Out hat.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Geben Sie einen beschreibenden Namen ein, der den Nummernbereich identifiziert. Nachdem Sie den Nummernbereich gespeichert haben, kann dieser Name nicht mehr geändert werden.

- **Nummernbereich** Geben Sie im ersten Feld die Anfangsnummer des Nummernbereichs ein. Geben Sie im zweiten Feld die Endnummer des Nummernbereichs ein.

  - Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.

  - Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie die letzte Nummer des Bereichs.

  - Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

  - Wenn der Nummernbereich mit dem Zeichen oder \* #beginnt, muss der Bereich größer als 100 sein.

  - Gültige Werte: Muss mit der zeichenfolge für reguläre Ausdrücke übereinstimmen ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die mit dem Zeichen oder # oder einer Zahl 1 bis 9 beginnt (das erste Zeichen darf keine \* Null sein). Wenn das erste Zeichen oder #ist, muss das folgende Zeichen die Zahl 1 bis 9 sein (es darf keine \* Null sein). Nachfolgende Zeichen können eine Beliebige Zahl von 0 bis 9 bis sieben zusätzliche Zeichen sein (z. B. "#6000", \* "92000", \* "95551212" und "915551212"). Wenn das erste Zeichen nicht oder #ist, muss das erste Zeichen die Zahl 1 bis 9 sein (es darf nicht null sein), gefolgt von bis zu acht Zeichen, jeweils eine Zahl von 0 bis \* 9 (z. B.: 915551212;41212;300).

  - Sie sollten nicht mehr als 50.000 Nummern pro Pool haben. Jeder Nummernbereich umfasst in der Regel 100 oder weniger Zahlen, kann jedoch viel größer sein, solange er weniger als 10.000 Nummern umfasst. Geben Sie anstelle eines Bereichs mit der Startnummer "7000000" und der Endnummer "8000000" als Startnummer beispielsweise "7000000" und als Endnummer "7000100" an.

- **FQDN des Zielservers** Wählen Sie den vollqualifizierten Domänennamen (FQDN) oder die Dienst-ID des Anwendungsdiensts aus, der die Anwendung zum Parken von Anrufen hostet. Alle Anrufe, die in Nummern innerhalb des durch die Start- und Endnummer im Nummernbereich angegebenen Bereichs geparkt werden, werden an diesen Server oder Pool geroutet.

Weitere Informationen zu den Funktionen und Funktionen des Parkens von Anrufen finden Sie unter [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Weitere Informationen zum Arbeiten mit Nummernbereichen zum Parken von Anrufen finden Sie unter [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).
---
title: Parken von Anrufen – Erstellen einer neuen oder Bearbeiten einer vorhandenen Funktion
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
description: Nummernbereiche für das Parken von Anrufen definieren die temporären Nummern, bei denen geparkte Anrufe gehalten werden, bis jemand sie abruft oder ein Timeout aufweist.
ms.openlocfilehash: 7c4050ebf09d2b0f533aee9fecb4eda3c4f383b9a914886a125f150740cea07f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294732"
---
# <a name="call-park-create-new-or-edit-existing"></a>Funktion zum Parken von Anrufen: Erstellen einer neuen oder Bearbeiten einer vorhandenen Funktion zum Parken von Anrufen

Nummernbereiche für das Parken von Anrufen definieren die temporären Nummern, bei denen geparkte Anrufe gehalten werden, bis jemand sie abruft oder ein Timeout aufweist.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Geben Sie einen beschreibenden Namen ein, der den Nummernbereich identifiziert. Nachdem Sie den Nummernbereich gespeichert haben, kann dieser Name nicht mehr geändert werden.

- **Nummernbereich** Geben Sie im ersten Feld die Anfangsnummer des Nummernbereichs ein. Geben Sie im zweiten Feld die Endnummer des Nummernbereichs ein.

  - Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.

  - Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie die letzte Nummer des Bereichs.

  - Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

  - Wenn der Zahlenbereich mit dem Zeichen \* oder #beginnt, muss der Bereich größer als 100 sein.

  - Gültige Werte: Muss mit der Zeichenfolge des regulären Ausdrucks übereinstimmen ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die entweder mit dem Zeichen \* oder der Zahl 1 bis 9 beginnt (das erste Zeichen darf keine Null sein). Wenn das erste Zeichen \* oder #ist, muss das folgende Zeichen eine Zahl 1 bis 9 sein (es darf keine Null sein). Nachfolgende Zeichen können eine beliebige Zahl zwischen 0 und 9 bis zu sieben zusätzlichen Zeichen sein (z. B. "#6000", " \* 92000", " \* 95551212" und "915551212"). Wenn das erste Zeichen nicht \* oder #ist, muss das erste Zeichen eine Zahl zwischen 1 und 9 sein (es kann nicht null sein), gefolgt von bis zu acht Zeichen, jeweils eine Zahl 0 bis 9 (z. B.: 915551212;41212;300).

  - Sie sollten nicht mehr als 50.000 Nummern pro Pool haben. Jeder Nummernbereich umfasst in der Regel 100 oder weniger Nummern, kann jedoch viel größer sein, solange er weniger als 10.000 Nummern enthält. Geben Sie anstelle eines Bereichs mit der Startnummer "7000000" und der Endnummer "8000000" als Startnummer beispielsweise "7000000" und als Endnummer "7000100" an.

- **FQDN des Zielservers** Wählen Sie den vollqualifizierten Domänennamen (FQDN) oder die Dienst-ID des Anwendungsdiensts aus, der die Anwendung zum Parken von Anrufen hostet. Alle Anrufe, die an Nummern innerhalb des durch die Start- und Endnummer im Nummernbereich angegebenen Bereichs geparkt werden, werden an diesen Server oder Pool weitergeleitet.

Ausführliche Informationen zu den Funktionen und Funktionen zum Parken von Anrufen finden Sie unter [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Ausführliche Informationen zum Arbeiten mit Nummernbereichen für das Parken von Anrufen finden Sie unter [Konfigurieren Telefon Nummernerweiterungen für das Parken von Anrufen.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)
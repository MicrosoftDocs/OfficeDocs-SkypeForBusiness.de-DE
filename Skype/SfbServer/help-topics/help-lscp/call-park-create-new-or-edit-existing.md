---
title: Erstellen eines neuen oder Bearbeiten eines vorhandenen Anrufparks
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
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Nummernbereiche für das Parken von Anrufen definieren die temporären Nummern, in denen geparkte Anrufe gehalten werden, bis sie von einem Benutzer abgerufen werden oder ein Zeit zeitweise abgestellt wird.
ms.openlocfilehash: 5ee0891ebaabc97b965aadc5f1ab1c4390669427
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819385"
---
# <a name="call-park-create-new-or-edit-existing"></a>Funktion zum Parken von Anrufen: Erstellen einer neuen oder Bearbeiten einer vorhandenen Funktion zum Parken von Anrufen

Nummernbereiche für das Parken von Anrufen definieren die temporären Nummern, in denen geparkte Anrufe gehalten werden, bis sie von einem Benutzer abgerufen werden oder ein Zeit zeitweise abgestellt wird.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Geben Sie einen beschreibenden Namen ein, der den Nummernbereich identifiziert. Nachdem Sie den Nummernbereich gespeichert haben, kann dieser Name nicht mehr geändert werden.

- **Nummernbereich** Geben Sie im ersten Feld die Anfangsnummer des Nummernbereichs ein. Geben Sie im zweiten Feld die Endnummer des Nummernbereichs ein.

  - Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.

  - Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie die letzte Nummer des Bereichs.

  - Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

  - Wenn der Zahlenbereich mit dem Zeichen oder #beginnt, muss der Bereich \* größer als 100 sein.

  - Gültige Werte: Muss mit der Zeichenfolge für reguläre Ausdrücke übereinstimmen ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die entweder mit dem Zeichen oder # oder einer Zahl von 1 bis 9 beginnt (das erste Zeichen darf keine \* Null sein). Wenn das erste Zeichen oder #ist, muss das folgende Zeichen eine Zahl von 1 bis 9 sein (es darf \* keine Null sein). Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis sieben zusätzliche Zeichen sein (z. B. "#6000", " \* 92000", " \* 95551212" und "915551212"). Wenn das erste Zeichen nicht oder #ist, muss das erste Zeichen eine Zahl von 1 bis 9 sein (es darf nicht null sein), gefolgt von bis zu acht Zeichen, jeweils eine Zahl von 0 bis \* 9 (z. B.: 915551212;41212;300).

  - Sie sollten nicht mehr als 50.000 Nummern pro Pool haben. Jeder Nummernbereich umfasst normalerweise 100 oder weniger Zahlen, kann jedoch viel größer sein, solange er weniger als 10.000 Nummern enthält. Geben Sie anstelle eines Bereichs mit der Startnummer "7000000" und der Endnummer "8000000" als Startnummer beispielsweise "7000000" und als Endnummer "7000100" an.

- **FQDN des Zielservers** Wählen Sie den vollqualifizierten Domänennamen (FQDN) oder die Dienst-ID des Anwendungsdiensts aus, der die Anwendung zum Parken von Anrufen hostet. Alle Anrufe, die in Nummern innerhalb des durch die Start- und Endnummer im Nummernbereich angegebenen Bereichs geparkt werden, werden an diesen Server oder Pool geroutet.

Weitere Informationen zu funktionen und Features zum Parken von Anrufen finden Sie unter [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Weitere Informationen zum Arbeiten mit Nummernbereichen zum Parken von Anrufen finden Sie unter "Konfigurieren von [Telefonnummernerweiterungen für das Parken von Anrufen".](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)



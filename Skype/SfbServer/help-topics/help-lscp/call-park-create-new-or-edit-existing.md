---
title: Parken von Anrufen Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Parken Nummernbereiche definieren die temporären Nummern, in dem Geparkte Anrufe gehalten werden, bis eine Person oder Timeout abgerufen.
ms.openlocfilehash: 6948bc42616ee85c77eb7fe250fe922420d6919b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234809"
---
# <a name="call-park-create-new-or-edit-existing"></a>Funktion zum Parken von Anrufen: Erstellen einer neuen oder Bearbeiten einer vorhandenen Funktion zum Parken von Anrufen

Parken Nummernbereiche definieren die temporären Nummern, in dem Geparkte Anrufe gehalten werden, bis eine Person oder Timeout abgerufen.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Name** Geben Sie einen beschreibenden Namen, der den Nummernbereich. Nach dem Speichern des Nummernbereichs kann dieser Name nicht mehr geändert werden.

- **Zahlenbereich** Geben Sie im ersten Feld die Anfangsnummer des Bereichs an. Geben Sie im zweiten Feld die Endnummer des Nummernbereichs ein.

  - Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.

  - Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.

  - Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

  - Wenn der Nummernbereich mit dem Zeichen beginnt \* oder #, der Bereich muss größer als 100 sein.

  - Gültige Werte: Zeichenfolge des regulären Ausdrucks muss übereinstimmen ([\\* | #] ? [1-9] \d{0,7}) | ([1-9] \d{0,8}). Dies bedeutet, dass der Wert muss eine Zeichenfolge beginnend mit entweder die Zeichen \* oder # oder eine Zahl zwischen 1 und 9 (das erste Zeichen darf nicht NULL sein). Wenn das erste Zeichen ist \* oder #, in das folgende Zeichen muss eine Zahl zwischen 1 und 9 (es kann nicht NULL sein). Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzliche Zeichen sein (z. B. "#6000", "\*92000", "\*95551212" und "915551212"). Wenn das erste Zeichen nicht ist \* oder #, in das erste Zeichen muss eine Zahl zwischen 1 und 9 (es kann nicht NULL sein), gefolgt von bis zu acht Zeichen jedes eine Zahl von 0 bis 9 (zum Beispiel: 915551212; 41212; 300).

  - Sie sollten über maximal 50.000 Nummern pro Pool verfügen. Jeder Nummernbereich umfasst normalerweise maximal 100 Nummern, Sie können jedoch einen deutlich höheren Wert festlegen (bis maximal 10.000 Nummern). Geben Sie anstelle eines Bereichs mit der Startnummer "7000000" und der Endnummer "8000000" als Startnummer beispielsweise "7000000" und als Endnummer "7000100" an.

- **FQDN des Zielservers** Wählen Sie den vollqualifizierten Domänennamen (FQDN) oder die Dienst-ID des Anwendungsdiensts, die die Anwendung zum Parken von Anrufen gehostet wird. Alle Anrufe, die im Bereich geparkt werden, der über die Start- und Endnummer des Nummernbereichs angegeben wird, werden an diesen Server oder Pool weitergeleitet.

Weitere Informationen zu parken Features und Funktionen finden Sie unter [Planen des Parkens von Anrufen in Skype für Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Ausführliche Informationen zum Arbeiten mit Parken Nummernbereiche finden Sie unter [Konfigurieren Telefon Anzahl Erweiterungen für das Parken von Anrufen](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).



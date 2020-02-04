---
title: Anruf parken neues erstellen oder vorhandenes bearbeiten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Die Rufnummernbereiche des Anruf Parks definieren die temporären Nummern, in denen geparkte Anrufe abgehalten werden, bis jemand Sie abruft oder Sie auslaufen.
ms.openlocfilehash: 5f32cccf70593ffe480cbcba028974cc1dc91046
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41703930"
---
# <a name="call-park-create-new-or-edit-existing"></a>Funktion zum Parken von Anrufen: Erstellen einer neuen oder Bearbeiten einer vorhandenen Funktion zum Parken von Anrufen

Die Rufnummernbereiche des Anruf Parks definieren die temporären Nummern, in denen geparkte Anrufe abgehalten werden, bis jemand Sie abruft oder Sie auslaufen.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste werden die Felder der Seite beschrieben.

- **Name** Geben Sie einen aussagekräftigen Namen ein, der den Nummernbereich kennzeichnet. Nach dem Speichern des Nummernbereichs kann dieser Name nicht mehr geändert werden.

- **Nummernbereich** Geben Sie im ersten Feld die Anfangszahl des Zahlenbereichs ein. Geben Sie im zweiten Feld die Endnummer des Nummernbereichs ein.

  - Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.

  - Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.

  - Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

  - Wenn der Zahlenbereich mit dem Zeichen \* oder # beginnt, muss der Bereich größer als 100 sein.

  - Gültige Werte: muss mit der Zeichenfolge für den regulären\\Ausdruck übereinstimmen ([* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die \* entweder mit dem Zeichen oder # oder einer Zahl von 1 bis 9 beginnt (das erste Zeichen darf keine NULL sein). Wenn das erste Zeichen oder \* # ist, muss das folgende Zeichen eine Zahl von 1 bis 9 sein (es darf keine NULL sein). Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzlichen Zeichen sein (beispielsweise "#6000"\*, "92000"\*, "95551212" und "915551212"). Wenn das erste Zeichen nicht \* oder # ist, muss das erste Zeichen eine Zahl von 1 bis 9 sein (es darf nicht NULL sein), gefolgt von bis zu acht Zeichen, die jeweils eine Zahl von 0 bis 9 aufweisen (Beispiel: 915551212; 41212; 300).

  - Sie sollten über maximal 50.000 Nummern pro Pool verfügen. Jeder Nummernbereich umfasst normalerweise maximal 100 Nummern, Sie können jedoch einen deutlich höheren Wert festlegen (bis maximal 10.000 Nummern). Geben Sie anstelle eines Bereichs mit der Startnummer "7000000" und der Endnummer "8000000" als Startnummer beispielsweise "7000000" und als Endnummer "7000100" an.

- **FQDN des Zielservers** Wählen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die Dienst-ID des Anwendungsdiensts aus, der die Anwendung für den Anruf Park hostet. Alle Anrufe, die im Bereich geparkt werden, der über die Start- und Endnummer des Nummernbereichs angegeben wird, werden an diesen Server oder Pool weitergeleitet.

Details zu den Funktionen und Funktionen des Anruf Parks finden Sie unter [Planen des Anruf Parks in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Details zum Arbeiten mit den Rufnummernbereichen des Anruf Parks finden Sie unter [Konfigurieren von Telefonnummern Erweiterungen für Park Anrufe](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).



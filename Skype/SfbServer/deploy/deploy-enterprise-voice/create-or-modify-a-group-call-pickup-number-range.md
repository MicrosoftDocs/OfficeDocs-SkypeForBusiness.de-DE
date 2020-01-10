---
title: Erstellen oder Ändern eines Gruppenanruf-Pickup-Nummernbereichs in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: In Skype for Business Server Enterprise-VoIP können Sie einen Gruppenanruf-Abhol Nummernbereich erstellen oder ändern.
ms.openlocfilehash: 546fefd996286678aae77338b4e0867285670a57
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001715"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Erstellen oder Ändern eines Gruppenanruf-Pickup-Nummernbereichs in Skype for Business

In Skype for Business Server Enterprise-VoIP können Sie einen Gruppenanruf-Abhol Nummernbereich erstellen oder ändern.

Die Abholung von Gruppen anrufen basiert auf der Anwendung "Parken". Wenn Sie die Gruppenanruf Abholung bereitstellen, müssen Sie die Umlaufbahn Tabelle des Anruf Parks mit Bereichen von Telefonnummern konfigurieren, die als Gruppennummern für die Anruf Abholung festgelegt sind. Bei diesen Gruppennummern handelt es sich um Nummern, die Benutzer wählen, um Anrufe anzunehmen, die an einen Benutzer eingehen.

Wie bei Orbitnummern zum Parken von Anrufen muss es sich auch bei Nummern für die Gruppenanrufannahme um virtuelle Durchwahlen handeln, denen kein Benutzer oder Telefon zugewiesen ist. Jeder Front-End-Pool, in dem Sie die Gruppenanruf Abholung bereitstellen, kann über einen oder mehrere Bereiche der Gruppennummern für die Anruf Abholung verfügen. Die Gruppennummernbereiche müssen in der in Ihrer Bereitstellung global eindeutig sein und müssen als Typ **GroupPickup** zugewiesen werden.

Verwenden Sie das folgende Verfahren, um einen Nummernbereich für die Anrufannahmegruppe in der Orbittabelle für das Parken von Anrufen zu erstellen oder zu ändern.

> [!NOTE]
> Sie müssen die Skype for Business Server-Verwaltungsshell zum Erstellen, ändern, entfernen und Anzeigen von Gruppenanruf-Pickup-Nummernbereichen in der Orbit-Tabelle des Anruf Parks verwenden. Nummernbereiche für Gruppenanrufe sind in der Skype for Business Server-Systemsteuerung nicht verfügbar.

Die Nummernbereiche für die Anrufannahmegruppe müssen folgenden Regeln entsprechen:

- Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.

- Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.

- Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

- Wenn der Zahlenbereich mit dem Zeichen \* oder # beginnt, muss der Bereich größer als 100 sein.

- Gültige Werte: muss mit der Zeichenfolge für den regulären\\Ausdruck übereinstimmen ([* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die \* entweder mit dem Zeichen oder # oder einer Zahl von 1 bis 9 beginnt (das erste Zeichen darf keine NULL sein). Wenn das erste Zeichen oder \* # ist, muss das folgende Zeichen eine Zahl von 1 bis 9 sein (es darf keine NULL sein). Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzlichen Zeichen sein (beispielsweise "#6000"\*, "92000"\*, "95551212" und "915551212"). Wenn das erste Zeichen nicht \* oder # ist, muss das erste Zeichen eine Zahl von 1 bis 9 sein (es darf nicht NULL sein), gefolgt von bis zu acht Zeichen, die jeweils eine Zahl von 0 bis 9 aufweisen (beispielsweise "915551212"; "41212"; "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>So erstellen oder ändern Sie einen Bereich für die Anrufannahmegruppe

1. Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **Delegieren von Setup Berechtigungen**beschrieben.

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

3. Mit **New-CsCallParkOrbit** erstellen Sie einen neuen Nummernbereich für die Anrufannahmegruppe. Mit **Set-CsCallParkOrbit** ändern Sie einen vorhandenen Nummernbereich für die Anrufannahmegruppe.

    Führen Sie an der Eingabeaufforderung folgenden Befehl aus:

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Beispiel:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    Das folgende Beispiel zeigt, wie ein Nummernbereich von Orbits für das Parken von Anrufen zu Anrufannahmegruppen geändert wird.

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Verwenden Sie dieses Cmdlet zum Ändern der zugewiesenen Nummernbereiche nur dann, wenn Sie ursprünglich einen falschen Typ angegeben haben und der Gruppenbereich noch nicht verwendet wird. Wenn der Nummernbereich bereits verwendet wird und Sie den Typ von „CallPark“ zu „GroupPickup“ oder umgekehrt ändern, funktioniert entweder das Parken von Anrufen oder die Gruppenanrufannahme für diesen Nummernbereich nicht mehr. Wenn Sie beispielsweise einen Zahlenbereich von CallPark in GroupPick ändern, kann die Anwendung für den Anruf Park diesen Bereich von Umlaufbahnen nicht mehr zum Parken von Anrufen verwenden.

## <a name="see-also"></a>Siehe auch

[Neu – CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Satz-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Löschen eines Umlauf Bereichs für einen Anruf Park](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

---
title: Erstellen oder Ändern eines Nummernbereichs für die Gruppenanrufannahme in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Erstellen oder ändern Sie einen Nummernbereich für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: f487c277b8eaa03a5b31ce0dc9696b0efe712340
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822405"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Erstellen oder Ändern eines Nummernbereichs für die Gruppenanrufannahme in Skype for Business

Erstellen oder ändern Sie einen Nummernbereich für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP.

Die Gruppenanrufannahme basiert auf der Anwendung zum Parken von Anrufen. Wenn Sie die Gruppenanrufannahme bereitstellen, müssen Sie die Orbittabelle für das Parken von Anrufen mit Nummernbereichen konfigurieren, die als Gruppennummern für die Anrufannahme festgelegt sind. Bei diesen Gruppennummern handelt es sich um die Nummern, die Benutzer wählen, um Anrufe an einen anderen Benutzer weiter zu nehmen.

Wie Orbitnummern zum Parken von Anrufen müssen Nummern der Anrufannahmegruppe virtuelle Durchstellen sein, denen kein Benutzer oder Telefon zugewiesen ist. Jeder Front-End-Pool, in dem Sie die Gruppenanrufannahme bereitstellen, kann einen oder mehrere Bereiche von Gruppennummern für die Anrufannahme enthalten. Die Gruppennummerbereiche müssen in Ihrer Bereitstellung global eindeutig sein und als **"GroupPickup"-Typ zugewiesen** sein.

Verwenden Sie das folgende Verfahren, um einen Nummernbereich für die Anrufannahmegruppe in der Orbittabelle für das Parken von Anrufen zu erstellen oder zu ändern.

> [!NOTE]
> Sie müssen skype for Business Server Management Shell verwenden, um Nummernbereiche der Gruppenanrufannahme in der Orbittabelle für das Parken von Anrufen zu erstellen, zu ändern, zu entfernen und anzeigen. Nummernbereiche für die Gruppenanrufannahme sind in der Skype for Business Server-Systemsteuerung nicht verfügbar.

Die Nummernbereiche der Anrufannahmegruppe müssen die folgenden Regeln erfüllen:

- Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.

- Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie die letzte Nummer des Bereichs.

- Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

- Wenn der Zahlenbereich mit dem Zeichen oder #beginnt, muss der Bereich größer als \* 100 sein.

- Gültige Werte: Muss mit der Zeichenfolge für reguläre Ausdrücke übereinstimmen ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die entweder mit dem Zeichen oder # oder einer Zahl von 1 bis 9 beginnt (das erste Zeichen darf keine \* Null sein). Wenn das erste Zeichen oder #ist, muss das folgende Zeichen eine Zahl von 1 bis 9 sein (es darf \* keine Null sein). Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis sieben zusätzlichen Zeichen sein (z. B. "#6000", " \* 92000", " \* 95551212" und "915551212"). Wenn das erste Zeichen nicht oder #ist, muss das erste Zeichen eine Zahl von 1 bis 9 sein (es darf nicht null sein), gefolgt von bis zu acht Zeichen, jeweils eine Zahl von 0 bis 9 (z. B. \* "915551212", "41212", "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>So erstellen oder ändern Sie einen Anrufannahmegruppenbereich

1. Melden Sie sich bei dem Computer, auf dem Skype for Business Server Management Shell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie unter "Berechtigungen zum Delegieren des **Setups" beschrieben.**

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**

3. Verwenden **Sie New-CsCallParkOrbit,** um einen neuen Bereich von Nummern für die Anrufannahmegruppe zu erstellen. Verwenden **Sie Set-CsCallParkOrbit,** um einen vorhandenen Bereich von Anrufannahmenummern zu ändern.

    Führen Sie an der Eingabeaufforderung Folgendes aus:

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Beispiel:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    Das folgende Beispiel zeigt, wie Sie einen Nummernbereich von Orbits zum Parken von Anrufen in Anrufannahmegruppen ändern.

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Verwenden Sie dieses Cmdlet, um den typ, der Nummernbereichen zugewiesen ist, nur zu ändern, wenn Sie anfänglich den falschen Typ angegeben haben und der Gruppenbereich noch nicht verwendet wird. Wenn Sie den Nummernbereich von "CallPark" in "GroupPickup" oder umgekehrt ändern und der Nummernbereich bereits verwendet wird, funktioniert entweder das Parken von Anrufen oder die Gruppenanrufannahme für diesen Nummernbereich nicht mehr. Wenn Sie beispielsweise einen Nummernbereich von "CallPark" in "GroupPick" ändern, kann die Anwendung zum Parken von Anrufen diesen Orbitbereich nicht mehr zum Parken von Anrufen verwenden.

## <a name="see-also"></a>Siehe auch

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Löschen eines Orbitbereichs für das Parken von Anrufen](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

---
title: Erstellen oder Ändern eines Gruppenanrufannahmenummerbereichs in Skype for Business
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
description: Erstellen oder Ändern eines Gruppenanrufannahmenummerbereichs in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: e71915519014b1fa4cfffa3172327e9949ed73a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100421"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Erstellen oder Ändern eines Gruppenanrufannahmenummerbereichs in Skype for Business

Erstellen oder Ändern eines Gruppenanrufannahmenummerbereichs in Skype for Business Server Enterprise-VoIP.

Die Gruppenanrufannahme basiert auf der Anwendung zum Parken von Anrufen. Wenn Sie die Gruppenanrufannahme bereitstellen, müssen Sie die Orbittabelle zum Parken von Anrufen mit Telefonnummernbereichen konfigurieren, die als Anrufannahmegruppennummern festgelegt sind. Diese Gruppennummern sind die Nummern, die Benutzer wählen, um Anrufe zu nehmen, die für einen anderen Benutzer klingeln.

Wie Orbitnummern zum Parken von Anrufen müssen Anrufannahmegruppennummern virtuelle Erweiterungen sein, denen kein Benutzer oder Telefon zugewiesen ist. Jeder Front-End-Pool, in dem Sie die Gruppenanrufannahme bereitstellen, kann über einen oder mehrere Bereiche von Anrufannahmegruppennummern verfügen. Die Gruppennummerbereiche müssen global eindeutig in Ihrer Bereitstellung sein und als **GroupPickup-Typ zugewiesen** werden.

Verwenden Sie das folgende Verfahren, um einen Anrufannahmegruppennummerbereich in der Orbittabelle zum Parken von Anrufen zu erstellen oder zu ändern.

> [!NOTE]
> Sie müssen skype for Business Server Management Shell verwenden, um Gruppenanrufannahme-Nummernbereiche in der Orbittabelle zum Parken von Anrufen zu erstellen, zu ändern, zu entfernen und anzeigen. Gruppenanrufannahme-Nummernbereiche sind in der Skype for Business Server-Systemsteuerung nicht verfügbar.

Die Anrufannahmegruppennummerbereiche müssen den folgenden Regeln entsprechen:

- Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.

- Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie die letzte Nummer des Bereichs.

- Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

- Wenn der Nummernbereich mit dem Zeichen oder \* #beginnt, muss der Bereich größer als 100 sein.

- Gültige Werte: Muss mit der zeichenfolge für reguläre Ausdrücke übereinstimmen ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die mit dem Zeichen oder # oder einer Zahl 1 bis 9 beginnt (das erste Zeichen darf keine \* Null sein). Wenn das erste Zeichen oder #ist, muss das folgende Zeichen die Zahl 1 bis 9 sein (es darf keine \* Null sein). Nachfolgende Zeichen können eine Beliebige Zahl von 0 bis 9 bis sieben zusätzliche Zeichen sein (z. B. "#6000", \* "92000", \* "95551212" und "915551212"). Wenn das erste Zeichen nicht oder #ist, muss das erste Zeichen die Zahl 1 bis 9 sein (es darf nicht null sein), gefolgt von bis zu acht Zeichen, jeweils eine Zahl von 0 bis 9 (z. B. \* "915551212", "41212", "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>So erstellen oder ändern Sie einen Anrufannahmegruppenbereich

1. Melden Sie sich an dem Computer an, auf dem Skype for Business Server Management Shell als Mitglied der Gruppe RTCUniversalServerAdmins installiert ist, oder mit den erforderlichen Benutzerrechten, wie unter **Delegate Setup Permissions beschrieben.**

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

3. Verwenden **Sie New-CsCallParkOrbit,** um einen neuen Bereich von Anrufannahmegruppennummern zu erstellen. Verwenden **Sie Set-CsCallParkOrbit,** um einen vorhandenen Bereich von Anrufannahmenummern zu ändern.

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
    > Verwenden Sie dieses Cmdlet, um den Typ zu ändern, der Nummernbereichen zugewiesen ist, nur, wenn Sie den falschen Typ ursprünglich angegeben haben und der Gruppenbereich noch nicht verwendet wird. Wenn Sie den Nummernbereich von CallPark in GroupPickup oder umgekehrt ändern und der Nummernbereich bereits verwendet wird, funktioniert entweder das Parken von Anrufen oder die Gruppenanrufannahme nicht mehr für diesen Nummernbereich. Wenn Sie beispielsweise einen Nummernbereich von CallPark zu GroupPick ändern, kann die Anwendung zum Parken von Anrufen diesen Orbitbereich nicht mehr verwenden, um Anrufe zu parken.

## <a name="see-also"></a>Siehe auch

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Löschen eines Orbitbereichs für das Parken von Anrufen](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)
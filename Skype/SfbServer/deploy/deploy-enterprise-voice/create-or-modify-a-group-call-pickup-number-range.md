---
title: Erstellen oder Ändern eines Nummernbereichs für die Gruppenanrufannahme in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Erstellen oder Ändern eines Nummernbereichs für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP.
---

# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Erstellen oder Ändern eines Nummernbereichs für die Gruppenanrufannahme in Skype for Business

Erstellen oder Ändern eines Nummernbereichs für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP.

Die Gruppenanrufannahme basiert auf der Anwendung zum Parken von Anrufen. Wenn Sie die Gruppenanrufannahme bereitstellen, müssen Sie die Orbittabelle für das Parken von Anrufen mit Bereichen von Telefonnummern konfigurieren, die als Nummern für die Anrufannahmegruppe festgelegt sind. Bei diesen Gruppennummern handelt es sich um die Nummern, die Benutzer wählen, um Anrufe entgegenzunehmen, die für einen anderen Benutzer klingeln.

Wie Orbitnummern für das Parken von Anrufen müssen Nummern für die Anrufannahmegruppe virtuelle Erweiterungen sein, denen kein Benutzer oder Telefon zugewiesen ist. Jeder Front-End-Pool, in dem Sie die Gruppenanrufannahme bereitstellen, kann über einen oder mehrere Bereiche von Anrufannahmegruppennummern verfügen. Die Gruppennummernbereiche müssen in Ihrer Bereitstellung global eindeutig sein und als **GroupPickup-Typ** zugewiesen werden.

Verwenden Sie das folgende Verfahren, um einen Nummernbereich für die Anrufannahmegruppe in der Orbittabelle für das Parken von Anrufen zu erstellen oder zu ändern.

> [!NOTE]
> Sie müssen Skype for Business Server Verwaltungsshell verwenden, um Nummernbereiche für die Gruppenanrufannahme in der Orbittabelle für das Parken von Anrufen zu erstellen, zu ändern, zu entfernen und anzuzeigen. Nummernbereiche für die Gruppenanrufannahme sind in Skype for Business Server Systemsteuerung nicht verfügbar.

Die Nummernbereiche der Anrufannahmegruppe müssen die folgenden Regeln erfüllen:

- Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.

- Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie die letzte Nummer des Bereichs.

- Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

- Wenn der Zahlenbereich mit dem Zeichen \* oder #beginnt, muss der Bereich größer als 100 sein.

- Gültige Werte: Muss mit der Zeichenfolge des regulären Ausdrucks übereinstimmen ([\\*|#]?[ 1-9]\d{0,7})| ([1-9]\d{0,8}). Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die entweder mit dem Zeichen \* oder der Zahl 1 bis 9 beginnt (das erste Zeichen darf keine Null sein). Wenn das erste Zeichen oder #ist \* , muss das folgende Zeichen eine Zahl 1 bis 9 sein (es darf keine Null sein). Nachfolgende Zeichen können eine beliebige Zahl zwischen 0 und 9 bis zu sieben zusätzlichen Zeichen sein (z. B. "#6000", "\*92000", "\*95551212" und "915551212"). Wenn das erste Zeichen nicht \* oder #ist, muss das erste Zeichen eine Zahl 1 bis 9 sein (es kann nicht null sein), gefolgt von bis zu acht Zeichen, jeweils eine Zahl 0 bis 9 (z. B. "915551212", "41212", "300").

### <a name="to-create-or-modify-a-call-pickup-group-range"></a>So erstellen oder ändern Sie einen Gruppenbereich für die Anrufannahme

1. Melden Sie sich bei dem Computer an, auf dem Skype for Business Server Verwaltungsshell als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **"Stellvertretungs-Setupberechtigungen**" beschrieben.

2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start**", auf **"Alle Programme**", auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell**.

3. Verwenden Sie **New-CsCallParkOrbit** , um einen neuen Bereich von Nummern für die Anrufannahmegruppe zu erstellen. Verwenden Sie **"Set-CsCallParkOrbit** ", um einen vorhandenen Bereich von Anrufannahmenummern zu ändern.

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
    > Verwenden Sie dieses Cmdlet, um den Nummernbereich zugewiesenen Typ nur dann zu ändern, wenn Sie den falschen Typ ursprünglich angegeben haben und der Gruppenbereich noch nicht verwendet wird. Wenn Sie den Nummernbereich von CallPark in GroupPickup oder umgekehrt ändern und der Nummernbereich bereits verwendet wird, funktioniert entweder das Parken von Anrufen oder die Gruppenanrufannahme nicht mehr für diesen Nummernbereich. Wenn Sie beispielsweise einen Nummernbereich von CallPark in GroupPick ändern, kann die Anwendung zum Parken von Anrufen diesen Orbitbereich nicht mehr zum Parken von Anrufen verwenden.

## <a name="see-also"></a>Siehe auch

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Löschen eines Orbitbereichs für das Parken von Anrufen](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)
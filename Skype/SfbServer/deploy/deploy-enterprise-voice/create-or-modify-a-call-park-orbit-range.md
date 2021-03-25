---
title: Erstellen oder Ändern eines Orbitbereichs zum Parken von Anrufen in Skype for Business
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Erstellen oder Ändern einer Orbitbereichstabelle zum Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: eab1c3e6e53eaa878546b5fe4a9684147a00c583
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106321"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Erstellen oder Ändern eines Orbitbereichs zum Parken von Anrufen in Skype for Business

Erstellen oder Ändern einer Orbitbereichstabelle zum Parken von Anrufen in Skype for Business Server Enterprise-VoIP.

Das Parken von Anrufen verwendet Orbits für Parkanrufe. Bevor Benutzer Anrufe parken und abrufen können, müssen Sie die Orbittabelle zum Parken von Anrufen konfigurieren. Sie müssen die Bereiche von Durchwahlnummern (Orbits) angeben, die Ihre Organisation für Parkanrufe reserviert, und das Routing für diese Bereiche definieren, indem Sie angeben, welcher Anrufparkpool die einzelnen Bereiche verarbeitet. Wenn Sie Orbitbereiche definieren, besteht das Ziel in ausreichenden Orbits, damit ein Orbit nicht zu schnell wiederverwendet wird, aber nicht so viele Orbits, dass Sie die Anzahl der erweiterungen begrenzen, die für Benutzer oder andere Dienste verfügbar sind. Sie können mehrere Orbitbereiche für das Parken von Anrufen für jeden Skype for Business Server-Pool erstellen, in dem die Anwendung zum Parken von Anrufen bereitgestellt wird. Jeder Orbitbereich zum Parken von Anrufen muss einen global eindeutigen Namen und einen eindeutigen Satz von Erweiterungen haben.

> [!IMPORTANT]
> Ein Orbitbereich umfasst normalerweise 100 oder weniger Orbits. Jeder Bereich kann deutlich größer sein, solange der Höchstwert von 10.000 Orbits pro Bereich nicht überschritten wird und Sie über weniger als 50.000 Orbits pro Pool verfügen. Ist ein Bereich zu klein, werden die Orbits zu schnell wiederverwendet.

Verwenden Sie für Ihre Orbitbereiche Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist).

> [!NOTE]
> Das Zuweisen von Direktwahlnummern (Direct Inward Dialing, DID) als Orbitnummern in der Orbittabelle zum Parken von Anrufen wird nicht unterstützt.

Mit den folgenden Verfahren können Sie Orbitbereichseinstellungen für das Parken von Anrufen erstellen oder bearbeiten.

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>So verwenden Sie die Skype for Business Server-Systemsteuerung zum Erstellen oder Ändern eines Nummernbereichs zum Parken von Anrufen

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" am Computer an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und dann auf **Anruf parken**.

4. Führen Sie auf der Seite **Anruf parken** eine der folgenden Aktionen aus:

   - Um einen neuen Orbitbereich zu erstellen, klicken Sie auf **Neu**. Geben Sie im Feld **Name** einen Namen zur Identifizierung dieses Nummernbereichs ein.

     > [!NOTE]
     > Nachdem Sie den Orbitbereich in die Datenbank geschrieben haben, können Sie den Namen nicht mehr ändern.

   - Um einen bestehenden Orbitbereich zu bearbeiten, geben Sie den Namen des Bereichs teilweise oder vollständig im Suchfeld ein. Klicken Sie anschließend in der Ergebnisliste auf den Orbit, den Sie bearbeiten möchten, und dann auf **Bearbeiten** und auf **Details anzeigen**.

5. Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich von Durchwahlen für diesen Orbit zum Parken von Anrufen ein, und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein. Beachten Sie:

   - Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.

   - Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie die letzte Nummer des Bereichs.

   - Der Orbitbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

   - Wenn der Orbitbereich mit dem Zeichen oder \* #beginnt, muss der Bereich größer als 100 sein.

   - Gültige Werte: Muss mit der zeichenfolge für reguläre Ausdrücke übereinstimmen ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die mit dem Zeichen oder # oder einer Zahl 1 bis 9 beginnt (das erste Zeichen darf keine \* Null sein). Wenn das erste Zeichen oder #ist, muss das folgende Zeichen die Zahl 1 bis 9 sein (es darf keine \* Null sein). Nachfolgende Zeichen können eine Beliebige Zahl von 0 bis 9 bis sieben zusätzliche Zeichen sein (z. B. "#6000", \* "92000", \* "95551212" und "915551212"). Wenn das erste Zeichen nicht oder #ist, muss das erste Zeichen die Zahl 1 bis 9 sein (es darf nicht null sein), gefolgt von bis zu acht Zeichen, jeweils eine Zahl von 0 bis 9 (z. B. \* "915551212", "41212", "300").

   - Sie sollten über maximal 50.000 Orbits pro Pool verfügen. Jeder Orbitbereich umfasst typischerweise maximal 100 Orbits, Sie können jedoch einen deutlich höheren Wert festlegen (bis maximal 10.000 Orbits). Geben Sie anstelle eines Bereichs mit der Startnummer "7000000" und der Endnummer "8000000" als Startnummer beispielsweise "7000000" und als Endnummer "7000100" an.

6. Klicken Sie in **FQDN des Zielservers** auf den vollqualifizierten Domänennamen oder die Dienst-ID des Anwendungsdiensts, der die Anwendung zum Parken von Anrufen hostet. Alle Anrufe, die im Bereich geparkt werden, der über die Start- und Endnummer des Orbitbereichs angegeben wird, werden an diesen Server oder Pool weitergeleitet.

7. Klicken Sie auf **Commit**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>So verwenden Sie die Skype for Business Server-Verwaltungsshell zum Erstellen oder Ändern eines Nummernbereichs für das Parken von Anrufen

1. Melden Sie sich an dem Computer an, auf dem Skype for Business Server Management Shell als Mitglied der Gruppe RTCUniversalServerAdmins installiert ist, oder mit den erforderlichen Benutzerrechten, wie unter **Delegate Setup Permissions beschrieben.**

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

3. Mit **New-CsCallParkOrbit** können Sie einen neuen Orbitnummernbereich erstellen. Mit **Set-CsCallParkOrbit** können Sie einen bestehenden Orbitnummernbereich bearbeiten.

    Führen Sie an der Eingabeaufforderung Folgendes aus:

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    Beispiel:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    Mit dem folgenden Befehl wird das Bearbeiten der Nummern in einem bestehenden Orbitbereich veranschaulicht:

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>Siehe auch

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Löschen eines Orbitbereichs für das Parken von Anrufen](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)
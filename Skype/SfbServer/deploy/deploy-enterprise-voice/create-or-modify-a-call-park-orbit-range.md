---
title: Erstellen oder Ändern eines Umlauf Bereichs für einen Anruf Park in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Erstellen oder ändern Sie in Skype for Business Server Enterprise-VoIP eine Tabelle des Umlauf Bereichs des Anruf Parks.
ms.openlocfilehash: 77be47597e5bbb674719ac2b3192efdf4217a3dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286263"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Erstellen oder Ändern eines Umlauf Bereichs für einen Anruf Park in Skype for Business

Erstellen oder ändern Sie in Skype for Business Server Enterprise-VoIP eine Tabelle des Umlauf Bereichs des Anruf Parks.

Call Park verwendet Umlaufbahnen für Park Anrufe. Bevor Benutzer Anrufe parken und abrufen können, müssen Sie die Umlaufbahn Tabelle des Anruf Parks konfigurieren. Sie müssen die Bereiche der Durchwahlnummern (Orbits) angeben, die Ihre Organisation für Park Anrufe reserviert, und den Arbeitsplan für diese Bereiche definieren, indem Sie angeben, welcher Anruf Park Pool für jeden Bereich zuständig ist. Wenn Sie Umlaufbahn Bereiche definieren, besteht das Ziel darin, genügend Umlaufbahnen zu haben, damit eine Umlaufbahn nicht zu schnell wieder verwendet wird, aber nicht so viele Umlaufbahnen, dass Sie die Anzahl der für Benutzer oder andere Dienste verfügbaren Erweiterungen einschränken. Sie können für jeden Skype for Business Server-Pool, in dem die Park-Anwendung bereitgestellt wird, mehrere orbitbereiche für den Anruf Bereich erstellen. Jeder Orbit-Bereich für das Parken von Anrufen muss einen global eindeutigen Namen und einen eindeutigen Satz von Erweiterungen aufweisen.

> [!IMPORTANT]
> Ein Orbitbereich umfasst normalerweise 100 oder weniger Orbits. Jeder Bereich kann deutlich größer sein, solange der Höchstwert von 10.000 Orbits pro Bereich nicht überschritten wird und Sie über weniger als 50.000 Orbits pro Pool verfügen. Ist ein Bereich zu klein, werden die Orbits zu schnell wiederverwendet.

Verwenden Sie für Ihre Orbitbereiche Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist).

> [!NOTE]
> Das Zuweisen von Direktwahlnummern (DID) als Orbit-Nummern in der Orbit-Tabelle des Anruf Parks wird nicht unterstützt.

Mit den folgenden Verfahren können Sie Orbitbereichseinstellungen für das Parken von Anrufen erstellen oder bearbeiten.

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>So verwenden Sie die Skype for Business Server-Systemsteuerung zum Erstellen oder Ändern eines Nummernbereichs für Park Anrufe

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und dann auf **Anruf parken**.

4. Führen Sie auf der Seite **Anruf parken** eine der folgenden Aktionen aus:

   - Um einen neuen Orbitbereich zu erstellen, klicken Sie auf **Neu**. Geben Sie im Feld **Name** einen Namen zur Identifizierung dieses Nummernbereichs ein.

     > [!NOTE]
     > Nachdem Sie den Orbitbereich in die Datenbank geschrieben haben, können Sie den Namen nicht mehr ändern.

   - Um einen bestehenden Orbitbereich zu bearbeiten, geben Sie den Namen des Bereichs teilweise oder vollständig in das Suchfeld ein. Klicken Sie anschließend in der Ergebnisliste auf den Orbit, den Sie bearbeiten möchten, und dann auf **Bearbeiten** und auf **Details anzeigen**.

5. Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich von Durchwahlen für diesen Orbit zum Parken von Anrufen ein und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein. Beachten Sie Folgendes:

   - Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.

   - Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.

   - Der Orbitbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

   - Wenn der Umlaufbahn Bereich mit dem Zeichen \* oder # beginnt, muss der Bereich größer als 100 sein.

   - Gültige Werte: muss mit der Zeichenfolge des regulären Ausdrucks\\übereinstimmen ([* | #] ? [1{0,7}-9] \d) | ([1-9] \d{0,8}). Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die \* entweder mit dem Zeichen oder # oder einer Zahl von 1 bis 9 beginnt (das erste Zeichen darf keine NULL sein). Wenn das erste Zeichen oder \* # ist, muss das folgende Zeichen eine Zahl von 1 bis 9 sein (es darf keine NULL sein). Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzlichen Zeichen sein (beispielsweise "#6000"\*, "92000"\*, "95551212" und "915551212"). Wenn das erste Zeichen nicht \* oder # ist, muss das erste Zeichen eine Zahl von 1 bis 9 sein (es darf nicht NULL sein), gefolgt von bis zu acht Zeichen, die jeweils eine Zahl von 0 bis 9 aufweisen (beispielsweise "915551212"; "41212"; "300").

   - Sie sollten über maximal 50.000 Orbits pro Pool verfügen. Jeder Orbitbereich umfasst typischerweise maximal 100 Orbits, Sie können jedoch einen deutlich höheren Wert festlegen (bis maximal 10.000 Orbits). Geben Sie anstelle eines Bereichs mit der Startnummer „7000000“ und der Endnummer „8000000“ als Startnummer beispielsweise „7000000“ und als Endnummer „7000100“ an.

6. Klicken Sie in **FQDN des Zielservers**auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die Dienst-ID des Anwendungsdiensts, der die Anwendung für den Anruf Park hostet. Alle Anrufe, die im Bereich geparkt werden, der über die Start- und Endnummer des Orbitbereichs angegeben wird, werden an diesen Server oder Pool weitergeleitet.

7. Klicken Sie auf **Commit ausführen**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>So verwenden Sie die Skype for Business Server-Verwaltungsshell zum Erstellen oder Ändern eines Nummernbereichs für Park Anrufe

1. Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter Delegieren von **Setup Berechtigungen**beschrieben.

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

3. Mit **New-CsCallParkOrbit** können Sie einen neuen Orbitnummernbereich erstellen. Mit **Set-CsCallParkOrbit** können Sie einen bestehenden Orbitnummernbereich bearbeiten.

    Führen Sie an der Eingabeaufforderung folgenden Befehl aus:

   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    Beispiel:

   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    Mit dem folgenden Befehl wird das Bearbeiten der Nummern in einem bestehenden Orbitbereich veranschaulicht:

   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>Siehe auch

[Neu – CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Satz-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[Löschen eines Umlauf Bereichs für einen Anruf Park](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

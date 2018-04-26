---
title: Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Skype for Business 2015
ms.openlocfilehash: 3617fb739d56e395c31359c6cedae74e9fb63756
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business-2015"></a>Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Skype for Business 2015
 
Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Skype for Business 2015
  
Call Park uses orbits for parking calls. Before users can park and retrieve calls, you must configure the Call Park orbit table. You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range. When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services. You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed. Each Call Park orbit range must have a globally unique name and a unique set of extensions.
  
> [!IMPORTANT]
> Ein Orbitbereich umfasst normalerweise 100 oder weniger Orbits. Jeder Bereich kann deutlich größer sein, solange der Höchstwert von 10.000 Orbits pro Bereich nicht überschritten wird und Sie über weniger als 50.000 Orbits pro Pool verfügen. Ist ein Bereich zu klein, werden die Orbits zu schnell wiederverwendet. 
  
Verwenden Sie für Ihre Orbitbereiche Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist). 
  
> [!NOTE]
> Das Zuweisen von DID-Nummern (Direct Inward Dialing) als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt. 
  
Mit den folgenden Verfahren können Sie Orbitbereichseinstellungen für das Parken von Anrufen erstellen oder bearbeiten. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>So erstellen oder bearbeiten Sie mit  einen Nummernbereich für das Parken von Anrufen

1. Melden Sie sich beim Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Rolle Cs-VoiceAdministrator, Cs-ServerAdministrator oder CsAdministrator an. For details, see **Delegate Setup Permissions**.
    
2. Alternativ können Sie ein Browserfenster öffnen und dort die Admin-URL eingeben, um zur Systemsteuerung von Skype for Business Server zu gelangen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und dann auf **Anruf parken**.
    
4. Führen Sie auf der Seite **Anruf parken** eine der folgenden Aktionen aus:
    
  - Um einen neuen Orbitbereich zu erstellen, klicken Sie auf **Neu**. Geben Sie im Feld **Name** einen Namen zur Identifizierung dieses Nummernbereichs ein.
    
    > [!NOTE]
    > Nachdem Sie den Orbitbereich in die Datenbank geschrieben haben, können Sie den Namen nicht mehr ändern. 
  
  - Um einen bestehenden Orbitbereich zu bearbeiten, geben Sie den Namen des Bereichs teilweise oder vollständig in das Suchfeld ein. Klicken Sie anschließend in der Ergebnisliste auf den Orbit, den Sie bearbeiten möchten, und dann auf **Bearbeiten** und auf **Details anzeigen**.
    
5. Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich von Durchwahlen für diesen Orbit zum Parken von Anrufen ein und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein. Be aware:
    
   - Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.
    
   - Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.
    
   - Der Orbitbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.
    
   - Wenn der Orbitbereich mit dem Zeichen * oder # beginnt, muss der Bereich größer als 100 sein.
    
   - Gültige Werte müssen mit dem regulären Ausdruck [\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8} übereinstimmen. Dies bedeutet, dass es sich bei dem Wert um eine Zeichenfolge handeln muss, die entweder mit dem Zeichen * oder # oder einer Zahl zwischen 1 und 9 beginnt (das erste Zeichen darf keine Null sein). Wenn das erste Zeichen ein Sternchen (*) oder ein Rautenzeichen (#) ist, muss das folgende Zeichen eine Zahl zwischen 1 und 9 sein (keine Null). Bei den nachfolgenden Zeichen kann es sich um eine beliebige Zahl zwischen 0 und 9 und zusätzlich sieben Zeichen handeln (Beispiel: „#6000“, „*92000“, „*95551212“ und „915551212“). Wenn es sich bei dem ersten Zeichen nicht um * oder # handelt, muss das erste Zeichen eine Zahl zwischen 1 und 9 sein (keine Null), gefolgt von bis zu acht Zeichen, bei denen es sich jeweils um eine Zahl zwischen 0 und 9 handeln muss (z. B. „915551212“, „41212“ oder „300“).
    
   - Sie sollten über maximal 50.000 Orbits pro Pool verfügen. Jeder Orbitbereich umfasst typischerweise maximal 100 Orbits, Sie können jedoch einen deutlich höheren Wert festlegen (bis maximal 10.000 Orbits). Geben Sie anstelle eines Bereichs mit der Startnummer „7000000“ und der Endnummer „8000000“ als Startnummer beispielsweise „7000000“ und als Endnummer „7000100“ an.
    
6. Klicken Sie in FQDN des Zielservers auf den vollqualifizierten Domänennamen oder die Dienst-ID des Anwendungsdiensts, der die  hostet. Alle Anrufe, die im Bereich geparkt werden, der über die Start- und Endnummer des Orbitbereichs angegeben wird, werden an diesen Server oder Pool weitergeleitet.
    
7. Klicken Sie auf **Commit ausführen**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>So erstellen oder bearbeiten Sie mit  einen Nummernbereich für das Parken von Anrufen

1. Melden Sie sich auf dem Computer, auf dem die  installiert ist, als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter .
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Mit **** können Sie einen neuen Orbitnummernbereich erstellen. Mit **** können Sie einen bestehenden Orbitnummernbereich bearbeiten.
    
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

#### 

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[Delete a Call Park Orbit Range](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)


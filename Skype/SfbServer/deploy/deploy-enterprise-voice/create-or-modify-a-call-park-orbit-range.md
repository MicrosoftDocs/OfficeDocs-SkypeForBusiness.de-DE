---
title: Erstellen Sie oder ändern Sie einen orbitbereich zum Parken von Anrufen in Skype für Unternehmen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Erstellen Sie oder ändern Sie einer Parken Bereich orbittabelle in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: ccbde7291a97e834aade35fb62dc074064f9d58c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009732"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Erstellen Sie oder ändern Sie einen orbitbereich zum Parken von Anrufen in Skype für Unternehmen
 
Erstellen Sie oder ändern Sie einer Parken Bereich orbittabelle in Skype für Business Server Enterprise-VoIP.
  
Parken von Anrufen verwendet Orbits für das Parken von Anrufen. Bevor Benutzer Parken und Abrufen von anrufen können, müssen Sie die orbittabelle für das Parken von Anrufen konfigurieren. Durch angeben, welcher Pool zum Parken von Anrufen verarbeitet den jeweiligen Bereich möchten legen die Bereiche Durchwahlnummern (Orbits), dass Ihre Organisation reserviert für das Parken von Anrufen und das routing für diese Bereiche definieren. Wenn Sie Bereiche für den anrufparkorbit definieren, ist das Ziel genügend Orbits verfügen, damit alle eine Orbit nicht zu schnell ein, jedoch nicht so viele Orbits erneut verwendet wird,, die Anzahl der Erweiterungen für Benutzer verfügbar oder andere Dienste beschränken. Sie können mehrere Bereiche für das Parken von Anrufen für den anrufparkorbit für jede Skype für Business Server-Pool erstellen, in dem die Anwendung zum Parken bereitgestellt wird. Jede orbitbereich zum Parken von Anrufen muss einen global eindeutigen Namen und einen eindeutigen Satz von Erweiterungen verfügen.
  
> [!IMPORTANT]
> Ein Orbitbereich umfasst normalerweise 100 oder weniger Orbits. Jeder Bereich kann deutlich größer sein, solange der Höchstwert von 10.000 Orbits pro Bereich nicht überschritten wird und Sie über weniger als 50.000 Orbits pro Pool verfügen. Ist ein Bereich zu klein, werden die Orbits zu schnell wiederverwendet. 
  
Verwenden Sie für Ihre Orbitbereiche Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist). 
  
> [!NOTE]
> Zuweisen von direkten (Nummern Inward DIALING) als orbitnummern in der Parken wird orbittabelle nicht unterstützt. 
  
Mit den folgenden Verfahren können Sie Orbitbereichseinstellungen für das Parken von Anrufen erstellen oder bearbeiten. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Verwenden Sie zum Erstellen oder ändern einen Nummernbereich für das Parken von Anrufen Skype Business Server-Systemsteuerung

1. Melden Sie sich an dem Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Mitglied der Rolle CsVoiceAdministrator, CsServerAdministrator oder csadministrator an. Weitere Informationen hierzu finden Sie unter **Delegate Setup Permissions**.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und dann auf **Anruf parken**.
    
4. Führen Sie auf der Seite **Anruf parken** eine der folgenden Aktionen aus:
    
  - Um einen neuen Orbitbereich zu erstellen, klicken Sie auf **Neu**. Geben Sie im Feld **Name** einen Namen zur Identifizierung dieses Nummernbereichs ein.
    
    > [!NOTE]
    > Nachdem Sie den Orbitbereich in die Datenbank geschrieben haben, können Sie den Namen nicht mehr ändern. 
  
  - Um einen bestehenden Orbitbereich zu bearbeiten, geben Sie den Namen des Bereichs teilweise oder vollständig in das Suchfeld ein. Klicken Sie anschließend in der Ergebnisliste auf den Orbit, den Sie bearbeiten möchten, und dann auf **Bearbeiten** und auf **Details anzeigen**.
    
5. Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich von Durchwahlen für diesen Orbit zum Parken von Anrufen ein und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein. Beachten Sie:
    
   - Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.
    
   - Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.
    
   - Der Orbitbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.
    
   - Wenn der orbitbereich mit dem Zeichen beginnt \* oder #, der Bereich muss größer als 100 sein.
    
   - Gültige Werte: Zeichenfolge des regulären Ausdrucks muss übereinstimmen ([\\* | #] ? [1-9] \d{0,7}) | ([1-9] \d{0,8}). Dies bedeutet, dass der Wert muss eine Zeichenfolge beginnend mit entweder die Zeichen \* oder # oder eine Zahl zwischen 1 und 9 (das erste Zeichen darf nicht NULL sein). Wenn das erste Zeichen ist \* oder #, in das folgende Zeichen muss eine Zahl zwischen 1 und 9 (es kann nicht NULL sein). Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzliche Zeichen sein (z. B. "#6000", "\*92000", "\*95551212" und "915551212"). Wenn das erste Zeichen nicht ist \* oder #, in das erste Zeichen muss eine Zahl zwischen 1 und 9 (es kann nicht NULL sein), gefolgt von bis zu acht Zeichen jedes eine Zahl von 0 bis 9 (beispielsweise "915551212", "41212", "300").
    
   - Sie sollten über maximal 50.000 Orbits pro Pool verfügen. Jeder Orbitbereich umfasst typischerweise maximal 100 Orbits, Sie können jedoch einen deutlich höheren Wert festlegen (bis maximal 10.000 Orbits). Geben Sie anstelle eines Bereichs mit der Startnummer „7000000“ und der Endnummer „8000000“ als Startnummer beispielsweise „7000000“ und als Endnummer „7000100“ an.
    
6. Klicken Sie in **FQDN des Zielservers**auf den vollqualifizierten Domänennamen (FQDN) oder die Dienst-ID des Anwendungsdiensts, die die Anwendung zum Parken von Anrufen gehostet wird. Alle Anrufe, die im Bereich geparkt werden, der über die Start- und Endnummer des Orbitbereichs angegeben wird, werden an diesen Server oder Pool weitergeleitet.
    
7. Klicken Sie auf **Commit ausführen**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Verwenden von Skype für Business Server-Verwaltungsshell zum Erstellen oder ändern einen Nummernbereich für das Parken von Anrufen

1. Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Verwenden Sie **New-CsCallParkOrbit** , um einen neuen Bereich von orbitnummern erstellen. Verwenden Sie **Set-CsCallParkOrbit** , um einen bestehenden Bereich von orbitnummern ändern.
    
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

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[Löschen eines Orbitbereichs für das Parken von Anrufen](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
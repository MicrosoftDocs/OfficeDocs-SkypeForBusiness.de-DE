---
title: Erstellen oder Ändern eines Gruppe anrufen Pickup-Nummernbereichs in Skype für Unternehmen
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
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Erstellen oder Ändern eines Gruppe anrufen Pickup-Nummernbereichs in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 15906402fe81047f02fc033ba7a051a4169a0f26
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21002453"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a>Erstellen oder Ändern eines Gruppe anrufen Pickup-Nummernbereichs in Skype für Unternehmen
 
Erstellen oder Ändern eines Gruppe anrufen Pickup-Nummernbereichs in Skype für Business Server Enterprise-VoIP.
  
Gruppe aufrufen Pickup-basiert auf die Anwendung zum Parken. Bei der Bereitstellung von Gruppe aufrufen Pickup-müssen Sie die orbittabelle für das Parken von Anrufen mit Bereichen von Telefonnummern konfigurieren, die als Rufnummern pickup Gruppe festgelegt sind. Bei diesen Gruppennummern handelt es sich um Nummern, die Benutzer wählen, um Anrufe anzunehmen, die an einen Benutzer eingehen.
  
Wie bei Orbitnummern zum Parken von Anrufen muss es sich auch bei Nummern für die Gruppenanrufannahme um virtuelle Durchwahlen handeln, denen kein Benutzer oder Telefon zugewiesen ist. Jeder Front-End-Pool, in der Gruppe anrufen Pickup-bereitstellen, kann ein oder mehrere Bereiche des pickup Gruppe Rufnummern haben. Die Gruppennummernbereiche müssen in der in Ihrer Bereitstellung global eindeutig sein und müssen als Typ **GroupPickup** zugewiesen werden.
  
Verwenden Sie das folgende Verfahren, um einen Nummernbereich für die Anrufannahmegruppe in der Orbittabelle für das Parken von Anrufen zu erstellen oder zu ändern. 
  
> [!NOTE]
> Sie müssen die Skype für Business Server-Verwaltungsshell verwenden, erstellen, ändern, entfernen und anzeigen Gruppe aufrufen Pickup-Nummernbereiche in der orbittabelle für das Parken von Anrufen. Gruppe aufrufen Pickup-Nummernbereiche stehen nicht in Skype Business Server-Systemsteuerung. 
  
Die Nummernbereiche für die Anrufannahmegruppe müssen folgenden Regeln entsprechen:
  
- Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.
    
- Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.
    
- Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.
    
- Wenn der Nummernbereich mit dem Zeichen beginnt \* oder #, der Bereich muss größer als 100 sein.
    
- Gültige Werte: Zeichenfolge des regulären Ausdrucks muss übereinstimmen ([\\* | #] ? [1-9] \d{0,7}) | ([1-9] \d{0,8}). Dies bedeutet, dass der Wert muss eine Zeichenfolge beginnend mit entweder die Zeichen \* oder # oder eine Zahl zwischen 1 und 9 (das erste Zeichen darf nicht NULL sein). Wenn das erste Zeichen ist \* oder #, in das folgende Zeichen muss eine Zahl zwischen 1 und 9 (es kann nicht NULL sein). Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzliche Zeichen sein (z. B. "#6000", "\*92000", "\*95551212" und "915551212"). Wenn das erste Zeichen nicht ist \* oder #, in das erste Zeichen muss eine Zahl zwischen 1 und 9 (es kann nicht NULL sein), gefolgt von bis zu acht Zeichen jedes eine Zahl von 0 bis 9 (beispielsweise "915551212", "41212", "300").
    
### <a name="to-create-or-modify-a-call-pickup-group-range"></a>So erstellen oder ändern Sie einen Bereich für die Anrufannahmegruppe

1. Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Verwenden Sie **New-CsCallParkOrbit** , um einen neuen Nummernbereich Anruf pickup Gruppe erstellen. Verwenden Sie **Set-CsCallParkOrbit** , um einen bestehenden Bereich von Rufnummern pickup ändern.
    
    Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    Beispiel:
    
   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    Das folgende Beispiel zeigt, wie ein Nummernbereich von Orbits für das Parken von Anrufen zu Anrufannahmegruppen geändert wird.
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > Verwenden Sie dieses Cmdlet zum Ändern der zugewiesenen Nummernbereiche nur dann, wenn Sie ursprünglich einen falschen Typ angegeben haben und der Gruppenbereich noch nicht verwendet wird. Wenn der Nummernbereich bereits verwendet wird und Sie den Typ von „CallPark“ zu „GroupPickup“ oder umgekehrt ändern, funktioniert entweder das Parken von Anrufen oder die Gruppenanrufannahme für diesen Nummernbereich nicht mehr. Angenommen, wenn Sie einen Nummernbereich von CallPark in GroupPick ändern, können die Anwendung zum Parken nicht mehr diesem Bereich der Orbits für das Parken von Anrufen. 
  
## <a name="see-also"></a>Siehe auch

[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[Löschen eines Orbitbereichs für das Parken von Anrufen](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
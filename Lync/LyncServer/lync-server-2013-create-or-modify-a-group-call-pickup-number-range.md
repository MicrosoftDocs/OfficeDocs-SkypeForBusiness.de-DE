---
title: 'Lync Server 2013: Erstellen oder Ändern eines Gruppenanruf-Abhol Nummernbereichs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a82f9cdc02052bf08dba3e9529871eff2b01211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Create or modify a Group Call Pickup number range in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Verwenden Sie das folgende Verfahren, um einen Nummernbereich für die Anrufannahmegruppe in der Orbittabelle für das Parken von Anrufen zu erstellen oder zu ändern.

<div>


> [!NOTE]  
> Sie müssen die lync Server-Verwaltungsshell zum Erstellen, ändern, entfernen und Anzeigen von Gruppenanruf-Pickup-Nummernbereichen in der Orbit-Tabelle des Anruf Parks verwenden. Gruppenanruf-Abhol Nummernbereiche sind in der lync Server-Systemsteuerung nicht verfügbar.



</div>

<div>


> [!IMPORTANT]  
> Dem Nummernbereich für die Anruf Abholung muss ein GroupPickup-Typ zugewiesen werden. Benutzer sind für die Gruppenanruf Abholung nur aktiviert, wenn die Ihnen zugewiesene Gruppennummer Typ GroupPickup ist.



</div>

Die Nummernbereiche für die Anrufannahmegruppe müssen folgenden Regeln entsprechen:

  - Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.

  - Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.

  - Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

  - Wenn der Zahlenbereich mit dem Zeichen \* beginnt \#, muss der Bereich größer als 100 sein.

  - Gültige Werte: muss mit der Zeichenfolge des regulären\[\\\*|\#\]Ausdrucks\[ übereinstimmen (? 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}). Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die \* entweder \# mit dem Zeichen oder einer Zahl von 1 bis 9 beginnt (das erste Zeichen darf keine NULL sein). Wenn das erste Zeichen oder \* \#ist, muss das folgende Zeichen eine Zahl von 1 bis 9 sein (es darf keine NULL sein). Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzlichen Zeichen sein (Beispiels\#Weise "6000"\*, "92000"\*, "95551212" und "915551212"). Wenn das erste Zeichen nicht \* oder \#ist, muss das erste Zeichen eine Zahl von 1 bis 9 sein (es darf nicht NULL sein), gefolgt von bis zu acht Zeichen, jeweils eine Zahl von 0 bis 9 (beispielsweise "915551212"; "41212"; "300").

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>So erstellen oder ändern Sie einen Bereich für die Anrufannahmegruppe

1.  Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Mit **New-CsCallParkOrbit** erstellen Sie einen neuen Nummernbereich für die Anrufannahmegruppe. Mit **Set-CsCallParkOrbit** ändern Sie einen vorhandenen Nummernbereich für die Anrufannahmegruppe.
    
    Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Beispiel:
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    Das folgende Beispiel zeigt, wie ein Nummernbereich von Orbits für das Parken von Anrufen zu Anrufannahmegruppen geändert wird.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > Verwenden Sie dieses Cmdlet zum Ändern der zugewiesenen Nummernbereiche nur dann, wenn Sie ursprünglich einen falschen Typ angegeben haben und der Gruppenbereich noch nicht verwendet wird. Wenn der Nummernbereich bereits verwendet wird und Sie den Typ von „CallPark“ zu „GroupPickup“ oder umgekehrt ändern, funktioniert entweder das Parken von Anrufen oder die Gruppenanrufannahme für diesen Nummernbereich nicht mehr. Wenn Sie beispielsweise einen Zahlenbereich von CallPark in GroupPick ändern, kann die Anwendung für den Anruf Park diesen Bereich von Umlaufbahnen nicht mehr zum Parken von Anrufen verwenden.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen eines Umlauf Bereichs für einen Anruf Park in lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[Neu – CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Satz-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


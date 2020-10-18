---
title: 'Lync Server 2013: Erstellen oder Ändern eines Nummernbereichs für eine Gruppenanruf Abholung'
description: 'Lync Server 2013: Erstellen oder Ändern eines Nummernbereichs für die Gruppenanruf Abholung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc2072a5d80e9c3b09e0c0d2275233214a21e764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577917"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Erstellen oder Ändern eines Nummernbereichs für die gruppenanrufannahme in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-30_

Verwenden Sie das folgende Verfahren, um einen Nummernbereich für die Anrufannahme Gruppe in der Orbit-Tabelle für das Parken von Anrufen zu erstellen oder zu ändern.

<div>


> [!NOTE]  
> Sie müssen lync Server-Verwaltungsshell zum Erstellen, ändern, entfernen und Anzeigen von Gruppenanruf-Abhol Nummernbereichen in der Orbit-Tabelle für das Parken von Anrufen verwenden. Gruppenanruf-Pickup-Nummernbereiche sind in lync Server-Systemsteuerung nicht verfügbar.



</div>

<div>


> [!IMPORTANT]  
> Dem Nummernbereich für die Anrufannahme Gruppe muss ein GroupPickup-Typ zugewiesen sein. Benutzer sind für die gruppenanrufannahme nur aktiviert, wenn die Gruppennummer, der Sie zugeordnet sind, dem Typ GroupPickup entspricht.



</div>

Die Nummernbereiche der Anrufannahme Gruppe müssen den folgenden Regeln entsprechen:

  - Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.

  - Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie die letzte Nummer des Bereichs.

  - Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

  - Wenn der Nummernbereich mit dem Zeichen \* oder beginnt \# , muss der Bereich größer als 100 sein.

  - Gültige Werte: muss mit der Zeichenfolge für reguläre Ausdrücke übereinstimmen ( \[ \\ \* | \# \] ? \[ 1-9 \] \\ d {0,7} ) | ( \[ 1-9 \] \\ d {0,8} ). Dies bedeutet, dass der Wert eine Zeichenfolge sein muss, die entweder mit dem Zeichen \* oder \# einer Zahl von 1 bis 9 beginnt (das erste Zeichen darf nicht NULL sein). Wenn das erste Zeichen \* oder ist \# , muss das folgende Zeichen eine Zahl von 1 bis 9 sein (es darf keine NULL sein). Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzlichen Zeichen sein (beispielsweise " \# 6000", " \* 92000", " \* 95551212" und "915551212"). Wenn das erste Zeichen nicht \* oder ist \# , muss das erste Zeichen eine Zahl 1 bis 9 (es darf nicht NULL sein), gefolgt von bis zu acht Zeichen, jeweils eine Zahl 0 bis 9 (beispielsweise "915551212", "41212", "300").

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>So erstellen oder ändern Sie einen Gruppenbereich für Anruf Pickups

1.  Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Verwenden Sie **New-CsCallParkOrbit** , um einen neuen Bereich von Nummern für die Anrufannahme Gruppe zu erstellen. Verwenden Sie die **Einstellung CsCallParkOrbit** , um einen vorhandenen Bereich von Anrufannahme Nummern zu ändern.
    
    Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Beispiel:
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    Im folgenden Beispiel wird gezeigt, wie Sie einen Nummernbereich von Orbits für das Parken von Anrufen zum Aufrufen von Abhol Gruppen ändern.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > Verwenden Sie dieses Cmdlet, um den dem Nummernbereich zugewiesenen Typ nur dann zu ändern, wenn Sie anfänglich den falschen Typ angegeben haben und der Gruppenbereich noch nicht verwendet wird. Wenn Sie den Nummernbereich von CallPark zu GroupPickup oder umgekehrt ändern und der Nummernbereich bereits verwendet wird, wird entweder die Anrufannahme oder die gruppenanrufannahme für diesen Nummernbereich beendet. Wenn Sie beispielsweise einen Nummernbereich von CallPark in GroupPick ändern, kann der Anwendung zum Parken von Anrufen diesen Bereich von Umlaufbahnen nicht mehr zum Parken von Anrufen verwenden.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen eines Umlaufbahn Bereichs für das Parken von Anrufen in lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  


[New-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Gruppe-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


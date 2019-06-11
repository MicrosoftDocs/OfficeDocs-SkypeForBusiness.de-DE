---
title: 'Lync Server 2013: Erstellen oder Ändern eines orbitbereichs für einen Anruf Bereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04f759c0bb5c33991c961dbe4a2790c50df1f098
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a>Erstellen oder Ändern eines orbitbereichs für einen Anruf Bereich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Mit den folgenden Verfahren können Sie Orbitbereichseinstellungen für das Parken von Anrufen erstellen oder bearbeiten.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>So verwenden Sie die lync Server-Systemsteuerung zum Erstellen oder Ändern eines Zahlenbereichs für Park Anrufe

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und dann auf **Anruf parken**.

4.  Führen Sie auf der Seite **Anruf parken** eine der folgenden Aktionen aus:
    
      - Um einen neuen Orbitbereich zu erstellen, klicken Sie auf **Neu**. Geben Sie im Feld **Name** einen Namen zur Identifizierung dieses Nummernbereichs ein.
        
        <div>
        

        > [!NOTE]  
        > Nachdem Sie den Orbitbereich in die Datenbank geschrieben haben, können Sie den Namen nicht mehr ändern.

        
        </div>
    
      - Um einen bestehenden Orbitbereich zu bearbeiten, geben Sie den Namen des Bereichs teilweise oder vollständig in das Suchfeld ein. Klicken Sie anschließend in der Ergebnisliste auf den Orbit, den Sie bearbeiten möchten, und dann auf **Bearbeiten** und auf **Details anzeigen**.

5.  Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich von Durchwahlen für diesen Orbit zum Parken von Anrufen ein und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.</P>
    > <LI>
    > <P>Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie der Wert der Endnummer des Bereichs.</P>
    > <LI>
    > <P>Der Orbitbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.</P>
    > <LI>
    > <P>Wenn der Orbitbereich mit dem Zeichen * oder # beginnt, muss der Bereich größer als 100 sein.</P>
    > <LI>
    > <P>Gültige Werte: muss mit der Zeichenfolge des regulären Ausdrucks\*übereinstimmen ([| #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). Dies bedeutet, dass es sich bei dem Wert um eine Zeichenfolge handeln muss, die entweder mit dem Zeichen * oder # oder einer Zahl zwischen 1 und 9 beginnt (das erste Zeichen darf keine Null sein). Wenn das erste Zeichen ein Sternchen (*) oder ein Rautenzeichen (#) ist, muss das folgende Zeichen eine Zahl zwischen 1 und 9 sein (keine Null). Nachfolgende Zeichen können eine beliebige Zahl von 0 bis 9 bis zu sieben zusätzlichen Zeichen sein (beispielsweise "#6000", "*92000", "* 95551212" und "915551212"). Wenn es sich bei dem ersten Zeichen nicht um * oder # handelt, muss das erste Zeichen eine Zahl zwischen 1 und 9 sein (keine Null), gefolgt von bis zu acht Zeichen, bei denen es sich jeweils um eine Zahl zwischen 0 und 9 handeln muss (z. B. „915551212“, „41212“ oder „300“).</P>
    > <LI>
    > <P>Sie sollten über maximal 50.000 Orbits pro Pool verfügen. Jeder Orbitbereich umfasst typischerweise maximal 100 Orbits, Sie können jedoch einen deutlich höheren Wert festlegen (bis maximal 10.000 Orbits). Geben Sie anstelle eines Bereichs mit der Startnummer „7000000“ und der Endnummer „8000000“ als Startnummer beispielsweise „7000000“ und als Endnummer „7000100“ an.</P></LI></UL>

    
    </div>

6.  Klicken Sie in **FQDN des Zielservers**auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die Dienst-ID des Anwendungsdiensts, der die Anwendung für den Anruf Park hostet. Alle Anrufe, die im Bereich geparkt werden, der über die Start- und Endnummer des Orbitbereichs angegeben wird, werden an diesen Server oder Pool weitergeleitet.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>So verwenden Sie Windows PowerShell zum Erstellen oder Ändern eines Zahlenbereichs für Park Anrufe

1.  Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Mit **New-CsCallParkOrbit** können Sie einen neuen Orbitnummernbereich erstellen. Mit **Set-CsCallParkOrbit** können Sie einen bestehenden Orbitnummernbereich bearbeiten.
    
    Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    Beispiel:
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    Mit dem folgenden Befehl wird das Bearbeiten der Nummern in einem bestehenden Orbitbereich veranschaulicht:
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

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


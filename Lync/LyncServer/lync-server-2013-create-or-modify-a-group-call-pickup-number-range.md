---
title: Erstellen oder Ändern eines Nummernbereichs für die Gruppenanrufannahme
TOCTitle: Erstellen oder Ändern eines Nummernbereichs für die Gruppenanrufannahme
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945627(v=OCS.15)
ms:contentKeyID: 52056358
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern eines Nummernbereichs für die Gruppenanrufannahme

 

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Verwenden Sie das folgende Verfahren, um einen Nummernbereich für die Anrufannahmegruppe in der Orbittabelle für das Parken von Anrufen zu erstellen oder zu ändern.


> [!NOTE]
> Sie müssen die Lync Server-Verwaltungsshell zum Erstellen, Ändern, Entfernen und Anzeigen von Nummern für die Gruppenanrufannahme in der Orbittabelle für das Parken von Anrufen verwenden. Nummern für die Gruppenanrufannahme sind in Lync Server-Systemsteuerung nicht verfügbar.




> [!IMPORTANT]
> Der Nummernbereich für die Anrufannahmegruppe muss dem Typ "GroupPickup" zugewiesen sein. Benutzer sind nur für die Gruppenanrufannahme aktiviert, wenn die ihnen zugewiesene Gruppennummer den Typ "GroupPickup" aufweist.



Die Nummernbereiche für die Anrufannahmegruppe müssen folgenden Regeln entsprechen:

  - Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.

  - Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie die letzte Nummer des Bereichs.

  - Der Nummernbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.

  - Wenn der Nummernbereich mit dem Zeichen \* oder \# beginnt, muss der Bereich größer als 100 sein.

  - Gültige Werte müssen mit dem regulären Ausdruck \[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8} übereinstimmen. Dies bedeutet, dass es sich bei dem Wert um eine Zeichenfolge handeln muss, die entweder mit dem Zeichen \* oder \# oder einer Zahl zwischen 1 und 9 beginnt (das erste Zeichen darf keine Null sein). Wenn das erste Zeichen ein Sternchen (\*) oder ein Rautenzeichen (\#) ist, muss das folgende Zeichen eine Zahl zwischen 1 und 9 sein (keine Null). Bei den nachfolgenden Zeichen kann es sich um eine beliebige Zahl zwischen 0 und 9 und zusätzlich sieben Zeichen handeln (Beispiel: "\#6000", "\*92000", "\*95551212" und "915551212"). Wenn es sich bei dem ersten Zeichen nicht um \* oder \# handelt, muss das erste Zeichen eine Nummer zwischen 1 und 9 sein (keine Null), gefolgt von bis zu acht Zeichen, bei denen es sich jeweils um eine Zahl zwischen 0 und 9 handeln muss (z. B. "915551212", "41212" oder "300").

## So erstellen oder ändern Sie einen Bereich für die Anrufannahmegruppe

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Mit **New-CsCallParkOrbit** erstellen Sie einen neuen Nummernbereich für die Anrufannahmegruppe. Mit **Set-CsCallParkOrbit** ändern Sie einen vorhandenen Nummernbereich für die Anrufannahmegruppe.
    
    Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    Beispiel:
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    Das folgende Beispiel zeigt, wie ein Nummernbereich von Orbits für das Parken von Anrufen zu Anrufannahmegruppen geändert wird.
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    

    > [!IMPORTANT]
    > Verwenden Sie dieses Cmdlet zum Ändern der zugewiesenen Nummernbereiche nur dann, wenn Sie ursprünglich einen falschen Typ angegeben haben und der Gruppenbereich noch nicht verwendet wird. Wenn der Nummernbereich bereits verwendet wird und Sie die den Typ von "CallPark" zu "GroupPickup" oder umgekehrt ändern, funktioniert entweder das Parken von Anrufen oder die Gruppenanrufannahme für diesen Nummernbereich nicht mehr. Wenn Sie beispielsweise einen Nummernbereich von "CallPark" zu "GroupPick" ändern, kann die Anwendung zum Parken von Anrufen diesen Orbitbereich nicht mehr zum Parken von Anrufen nutzen.



## Siehe auch

#### Aufgaben

[Löschen eines Orbitbereichs für das Parken von Anrufen in Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  

#### Weitere Ressourcen

[New-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit)


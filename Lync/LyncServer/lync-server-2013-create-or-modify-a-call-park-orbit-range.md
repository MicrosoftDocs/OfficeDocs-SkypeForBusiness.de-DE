---
title: 'Lync Server 2013: Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen'
TOCTitle: Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398361(v=OCS.15)
ms:contentKeyID: 49294028
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Mit den folgenden Verfahren können Sie Orbitbereichseinstellungen für das Parken von Anrufen erstellen oder bearbeiten.

## So erstellen oder bearbeiten Sie mit Lync Server-Systemsteuerung einen Nummernbereich für das Parken von Anrufen

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und dann auf **Anruf parken** .

4.  Führen Sie auf der Seite **Anruf parken** eine der folgenden Aktionen aus:
    
      - Um einen neuen Orbitbereich zu erstellen, klicken Sie auf **Neu** . Geben Sie im Feld **Name** einen Namen zur Identifizierung dieses Nummernbereichs ein.
        

        > [!NOTE]
        > Nachdem Sie den Orbitbereich in die Datenbank geschrieben haben, können Sie den Namen nicht mehr ändern.

    
      - Um einen bestehenden Orbitbereich zu bearbeiten, geben Sie den Namen des Bereichs teilweise oder vollständig im Suchfeld ein. Klicken Sie anschließend in der Ergebnisliste auf den Orbit, den Sie bearbeiten möchten, und dann auf **Bearbeiten** und auf **Details anzeigen** .

5.  Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich von Durchwahlen für diesen Orbit zum Parken von Anrufen ein, und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein.
    

    > [!NOTE]
    > <UL>
    > <LI>
    > <P>Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.</P>
    > <LI>
    > <P>Der Wert der Startnummer des Bereichs muss dieselbe Länge aufweisen wie die letzte Nummer des Bereichs.</P>
    > <LI>
    > <P>Der Orbitbereich muss eindeutig sein. Für diesen Bereich sind keine Überschneidungen mit einem anderen Bereich zulässig.</P>
    > <LI>
    > <P>Wenn der Orbitbereich mit dem Zeichen * oder # beginnt, muss der Bereich größer als&nbsp;100 sein.</P>
    > <LI>
    > <P>Gültige Werte müssen mit dem regulären Ausdruck [\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8} übereinstimmen. Dies bedeutet, dass es sich bei dem Wert um eine Zeichenfolge handeln muss, die entweder mit dem Zeichen * oder # oder einer Zahl zwischen 1 und 9 beginnt (das erste Zeichen darf keine Null sein). Wenn das erste Zeichen ein Sternchen (*) oder ein Rautenzeichen (#) ist, muss das folgende Zeichen eine Zahl zwischen 1 und 9 sein (keine Null). Bei den nachfolgenden Zeichen kann es sich um eine beliebige Zahl zwischen&nbsp;0 und 9&nbsp;und zusätzlich sieben Zeichen handeln (Beispiel: "#6000", "*92000", "*95551212" und "915551212"). Wenn es sich bei dem ersten Zeichen nicht um * oder # handelt, muss das erste Zeichen eine Nummer zwischen&nbsp;1 und&nbsp;9 sein (keine Null), gefolgt von bis zu acht Zeichen, bei denen es sich jeweils um eine Zahl zwischen&nbsp;0 und&nbsp;9 handeln muss (z.&nbsp;B. "915551212", "41212" oder "300").</P>
    > <LI>
    > <P>Sie sollten über maximal 50.000&nbsp;Orbits pro Pool verfügen. Jeder Orbitbereich umfasst typischerweise maximal 100&nbsp;Orbits, Sie können jedoch einen deutlich höheren Wert festlegen (bis maximal&nbsp;10.000&nbsp;Orbits). Geben Sie anstelle eines Bereichs mit der Startnummer "7000000" und der Endnummer "8000000" als Startnummer beispielsweise "7000000" und als Endnummer "7000100" an.</P></LI></UL>



6.  Klicken Sie in **FQDN des Zielservers** auf den vollqualifizierten Domänennamen oder die Dienst-ID des Anwendungsdiensts, der die Anwendung zum Parken von Anrufen hostet. Alle Anrufe, die im Bereich geparkt werden, der über die Start- und Endnummer des Orbitbereichs angegeben wird, werden an diesen Server oder Pool weitergeleitet.

7.  Klicken Sie auf **Commit** .

## So erstellen oder bearbeiten Sie mit Windows PowerShell einen Nummernbereich für das Parken von Anrufen

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Mit **New-CsCallParkOrbit** können Sie einen neuen Orbitnummernbereich erstellen. Mit **Set-CsCallParkOrbit** können Sie einen bestehenden Orbitnummernbereich bearbeiten.
    
    Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    Beispiel:
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    Mit dem folgenden Befehl wird das Bearbeiten der Nummern in einem bestehenden Orbitbereich veranschaulicht:
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

## Siehe auch

#### Aufgaben

[Löschen eines Orbitbereichs für das Parken von Anrufen in Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)  

#### Weitere Ressourcen

[New-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit)


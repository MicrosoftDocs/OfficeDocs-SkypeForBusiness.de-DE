---
title: Löschen eines Nummernbereichs für die Gruppenanrufannahme
TOCTitle: Löschen eines Nummernbereichs für die Gruppenanrufannahme
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945629(v=OCS.15)
ms:contentKeyID: 52056336
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen eines Nummernbereichs für die Gruppenanrufannahme

 

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Verwenden Sie das folgende Verfahren, um einen Nummernbereich für die Gruppenanrufannahme zu löschen

## So löschen Sie einen Nummernbereich für die Gruppenanrufannahme

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    Beispiel:
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    

    > [!NOTE]
    > Ausführliche Informationen zu weiteren Optionen finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.



## Siehe auch

#### Aufgaben

[Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### Weitere Ressourcen

[Remove-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCallParkOrbit)


---
title: Löschen eines Orbitbereichs für das Parken von Anrufen in Lync Server 2013
TOCTitle: Löschen eines Orbitbereichs für das Parken von Anrufen in Lync Server 2013
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182546(v=OCS.15)
ms:contentKeyID: 49294643
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen eines Orbitbereichs für das Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Verwenden Sie eine der folgenden Prozeduren, um einen Parken von Anrufen-Orbitbereich zu löschen.

## Zum Verwenden von Lync Server-Systemsteuerung löschen Sie einen Parken von Anrufen-Orbitbereich

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und dann auf **Anruf parken**.

4.  Geben Sie auf der Seite **Anruf parken** im Suchfeld "Teile" den vollständigen Namen des Orbitbereichs ein, den Sie löschen möchten.

5.  Klicken Sie in der Ergebnisliste der Orbits auf den Orbit, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.

6.  Klicken Sie auf **OK**.

## Zum Verwenden von Cmdlets löschen Sie einen Parken von Anrufen-Orbitbereich

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    Beispiel:
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    

    > [!NOTE]
    > Ausführliche Informationen zu weiteren Optionen finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.



## Siehe auch

#### Aufgaben

[Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### Weitere Ressourcen

[Remove-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCallParkOrbit)


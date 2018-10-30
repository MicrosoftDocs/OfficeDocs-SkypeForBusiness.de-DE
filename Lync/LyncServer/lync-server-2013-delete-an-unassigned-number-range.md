---
title: Löschen eines Bereichs nicht zugewiesener Nummern
TOCTitle: Löschen eines Bereichs nicht zugewiesener Nummern
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182565(v=OCS.15)
ms:contentKeyID: 49295015
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen eines Bereichs nicht zugewiesener Nummern

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Verwenden Sie eines der folgenden Verfahren zum Löschen nicht zugewiesener Nummernbereiche für Ansagen.

## So löschen Sie mit der Lync Server-Systemsteuerung einen nicht zugewiesenen Nummernbereich

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und dann auf **Nicht zugewiesene Nummer**.

4.  Geben Sie auf der Seite **Nicht zugewiesene Nummer** im Suchfeld Teile oder den vollständigen Namen des Bereichs nicht zugewiesener Nummern ein, den Sie löschen möchten.

5.  Klicken Sie in der resultierenden Liste der Nummernbereiche auf den Namen, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

6.  Klicken Sie auf **Commit für alle**.

## So löschen Sie mit Cmdlets einen nicht zugewiesenen Nummernbereich

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    Beispiel:
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    

    > [!NOTE]
    > Ausführliche Informationen zu weiteren Optionen finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.



## Siehe auch

#### Aufgaben

[Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  

#### Weitere Ressourcen

[Remove-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUnassignedNumber)


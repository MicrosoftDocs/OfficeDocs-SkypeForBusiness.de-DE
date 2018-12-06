---
title: Löschen einer Ansage
TOCTitle: Löschen einer Ansage
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49890670
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer Ansage

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Führen Sie die folgenden Schritte aus, um eine Ankündigung zu löschen, die für Anrufe bei nicht zugewiesenen Nummern verwendet werden soll.

## So löschen Sie eine Ankündigung

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Listen Sie alle Ankündigungen in Ihrer Organisation auf. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        Get-CsAnnouncement

4.  Suchen Sie in der Ergebnisliste nach der zu löschenden Ankündigung, und kopieren Sie die GUID. Führen Sie an der Eingabeaufforderung dann Folgendes aus:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    Beispiel:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    

    > [!NOTE]
    > Ausführliche Informationen zu weiteren Optionen finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> und <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.



## Siehe auch

#### Aufgaben

[Erstellen einer Ansage in Lync Server 2013](lync-server-2013-create-an-announcement.md)  

#### Weitere Ressourcen

[Remove-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAnnouncement)  
[Get-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAnnouncement)


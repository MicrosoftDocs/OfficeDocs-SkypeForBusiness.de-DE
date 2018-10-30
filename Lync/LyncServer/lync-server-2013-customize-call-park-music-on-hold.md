---
title: Anpassen der Wartemusik für das Parken von Anrufen in Lync Server 2013
TOCTitle: Anpassen der Wartemusik für das Parken von Anrufen in Lync Server 2013
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49890715
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anpassen der Wartemusik für das Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-10_

Sie können Ihre eigene Musikdatei für die Wartemusik anstelle der Standardmusikdatei von Lync Server 2013 festlegen. Verwenden Sie zum Anpassen der Wartemusik das Cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.


> [!NOTE]
> Wenn Sie die Wartemusik anpassen und die gleiche Musikdatei für mehrere Standorte verwenden möchten, müssen Sie die Musikdatei für jeden Standort konfigurieren, in dem die Anwendung zum Parken von Anrufen ausgeführt wird.



## So passen Sie die Musikdatei an

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    

    > [!TIP]
    > Verwenden Sie das Cmdlet <STRONG>Get-CsService</STRONG>, um den Dienst zu ermitteln. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService">Get-CsService</A>.

    
    Im folgenden Beispiel wird gezeigt, wie die Inhalte der Datei "soothingmusic.wma" als Bytearray abgerufen und einer Variablen zugewiesen werden. Anschließend wird die Audiodatei als Wartemusikdatei für die Funktion zum Parken von Anrufen zugewiesen. Ausführliche Informationen finden Sie unter [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

## Siehe auch

#### Weitere Ressourcen

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)


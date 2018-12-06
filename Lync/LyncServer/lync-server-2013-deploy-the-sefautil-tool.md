---
title: Bereitstellen des SEFAUtil-Tools
TOCTitle: Bereitstellen des SEFAUtil-Tools
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945659(v=OCS.15)
ms:contentKeyID: 52056499
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen des SEFAUtil-Tools

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Zum Bereitstellen und Verwalten der Gruppenanrufannahme müssen Sie das SEFAUtil-Resource Kit-Tool verwenden. Das Tool gehört zu den Tools im Resource Kit von Lync Server 2013. Bevor Sie SEFAUtil installieren können, müssen Sie einen vertrauenswürdigen Anwendungspool in Ihrer Topologie haben, SEFAUtil als vertrauenswürdige Anwendung angeben und die Topologie aktivieren.


> [!IMPORTANT]
> Das Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK muss auf jedem Computer installiert sein, auf dem Sie das SEFAUtil-Tool ausführen möchten.



Sie können das SEFAUtil-Tool in jedem Front-End-Pool in Ihrer Bereitstellung ausführen.


> [!NOTE]
> Weitere Informationen zum Ausführen von SEFAUtil finden Sie im TechNet-Bog-Artikel "How to get SEFAutil running?" unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?linkid=278940</A>.



## So stellen Sie das SEFAUtil-Tool bereit

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem vertrauenswürdigen Anwendungspool gehört. Definieren Sie bei Bedarf einen vertrauenswürdigen Anwendungspool für den Front-End-Pool, in dem Sie SEFAUtil ausführen möchten. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Definieren Sie das SEFAUtil-Tool als eine vertrauenswürdige Anwendung. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    

    > [!NOTE]
    > Sie können ggf. einen anderen Port verwenden.



5.  Aktivieren Sie die Topologie mit Ihren Änderungen. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        Enable-CsTopology

6.  Installieren Sie die Tools im Resource Kit von Lync Server 2013 auf einem Front-End-Server, der zu dem in Schritt 3 erstellten vertrauenswürdigen Anwendungspool gehört.

7.  Gehen Sie wie folgt vor, um sicherzustellen, dass Ihr SEFAUtil-Tool korrekt ausgeführt wird:
    
    1.  Führen Sie das Tool an der Windows-Eingabeaufforderung mit Administratorberechtigungen aus, um die Anrufweiterleistungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.
        

        > [!NOTE]
        > Das Tool befindet sich unter "\Programme\Microsoft Lync Server 2013\Reskit".

    
    2.  Zeigen Sie die Anrufweiterleitungseinstellungen eines Benutzers an. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.


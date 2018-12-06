---
title: Verschieben von Exchange Unified Messaging-Kontaktobjekten
TOCTitle: Verschieben von Exchange Unified Messaging-Kontaktobjekten
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49890704
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben von Exchange Unified Messaging-Kontaktobjekten

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Wenn Sie Kontaktobjekte für eine automatische Telefonzentrale und für den Teilnehmerzugriff zur neuen Lync Server 2013-Bereitstellung migrieren möchten, müssen Sie zuerst mithilfe der Cmdlets **Get-CsExUmContact** und **Move-CsExUmContact** die Objekte aus der Office Communications Server 2007 R2-Vorgängerbereitstellung zur neuen Lync Server 2013-Bereitstellung verschieben. Anschließend führen Sie auf dem Exchange-Server das Windows PowerShell-Skript **ExchUCUtil** aus, damit für den neu bereitgestellten Lync-Pool folgende Schritte durchgeführt werden:

  - Hinzufügen der Kontaktobjekte zu den Unified Messaging-IP-Gateways

  - Hinzufügen der Kontaktobjekte zu den Unified Messaging-Sammelanschlüssen


> [!NOTE]
> Damit Sie die Cmdlets <STRONG>Get-CsExUmContact</STRONG> und <STRONG>Move-CsExUmContact</STRONG> verwenden können, müssen Sie ein Mitglied der Gruppe <STRONG>RTCUniversalUserAdmins</STRONG> sein und Organisationseinheitenberechtigung für die Organisationseinheit innehaben, in der die Kontaktobjekte gespeichert sind. Die Berechtigung für Organisationseinheiten kann mithilfe des <STRONG>Grant-OUPermission</STRONG>-Cmdlets erteilt werden.



## So verschieben Sie Kontaktobjekte mithilfe der Lync Server-Verwaltungsshell

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Geben Sie für jeden Pool, der bei Exchange UM registriert ist, an der Befehlszeile Folgendes ein (wobei **pool1.contoso.net** ein Pool aus der Office Communications Server 2007 R2-Bereitstellung ist und **pool2.contoso.net** der Pool aus der Lync Server 2013-Bereitstellung):
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Stellen Sie sicher, dass die Kontaktobjekte verschoben wurden, indem Sie das **Get-CsExumContact**-Cmdlet ausführen und sich vergewissern, dass **RegistrarPool** jetzt auf den neuen Pool zeigt.

## So führen Sie das Windows PowerShell-Skript "ExchUCUtil" aus

1.  Melden Sie sich als Benutzer mit der Berechtigung **Exchange-Organisationsadministrator** am Exchange UM-Server an.

2.  Navigieren Sie zum Windows PowerShell-Skript **ExchUCUtil** .
    
    In Exchange 2007 befindet sich das Skript **ExchUCUtil.ps1** in folgendem Verzeichnis: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**
    
    In Exchange 2010 befindet sich **ExchUCUtil.ps1** in folgendem Verzeichnis: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**

3.  Wenn Exchange in einer einzigen Gesamtstruktur bereitgestellt wird, geben Sie Folgendes ein:
    
        exchucutil.ps1
    
    Oder geben Sie Folgendes ein, falls Exchange in mehreren Gesamtstrukturen bereitgestellt wird:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    Hierbei gibt *forest FQDN* die Gesamtstruktur an, in der Lync Server 2013 bereitgestellt wird.
    

    > [!IMPORTANT]
    > Starten Sie den Dienst <STRONG>Lync Server Front-End</STRONG> (rtcsrv.exe) neu, <EM>nachdem</EM> Sie <STRONG>exchucutil.ps1</STRONG> ausgeführt haben. Andernfalls erkennt Lync Server 2013 Unified Messaging nicht in der Topologie.



---
title: Migrieren von Telefonen in öffentlichen Bereichen
TOCTitle: Migrieren von Telefonen in öffentlichen Bereichen
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49890691
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von Telefonen in öffentlichen Bereichen

 

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Telefone für gemeinsame Bereiche sind IP-Telefone, die sich am häufigsten an einem gemeinsamen Arbeitsplatz oder in einem öffentlichen Bereich befinden, z. B. in einer Lobby, Küche oder Fabriketage. Telefone für gemeinsame Bereiche müssen nicht an einen Computer angeschlossen sein, um Lync Server-UC-Funktionen bereitzustellen. Nach der Migration einer Lync Server 2010-Bereitstellung zu Lync Server 2013, müssen Sie auch die Kontaktobjekte migrieren, die mit dem Legacy-Telefon für gemeinsame Bereiche verknüpft sind. Mit Lync Server-Verwaltungsshell rufen Sie zuerst alle Kontaktobjekte ab, die mit den Lync Server 2010-Telefonen für gemeinsame Bereiche verknüpft sind. Dann verschieben Sie diese Objekte in den Lync Server 2013-Pool.

**Migireren von Telefonen für gemeinsame Bereiche**

1.  Öffnen Sie die Lync Server-Verwaltungsshell auf dem Lync Server 2013-Front-End-Server.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Geben Sie in der Lync Server-Verwaltungsshell Folgendes ein, um zu überprüfen, ob alle Kontaktobjekte in den Lync Server 2013-Pool verschoben wurden:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Überprüfen Sie, ob alle Kontaktobjekte jetzt mit dem Lync Server 2013-Pool verknüpft sind.


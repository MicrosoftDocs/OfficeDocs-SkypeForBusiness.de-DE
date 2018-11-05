---
title: Konfigurieren von Clients für die Migration
TOCTitle: Konfigurieren von Clients für die Migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49890838
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Clients für die Migration

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Dieses Thema enthält die für die Clientbereitstellung empfohlenen Schritte, die vor der Migration nach Lync Server 2013 durchgeführt werden sollten. Diese Konfigurationsänderungen müssen in Office Communications Server 2007 R2 durchgeführt werden. Es ist sehr wichtig, dass diese Schritte vor der Migration durchgeführt werden. Ausführliche Informationen finden Sie unter [Planen von Clients und Geräten in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

## So konfigurieren Sie die Clients im Vorfeld der Migration

1.  Stellen Sie die neusten Server-, Client- und Geräteaktualisierungen (Hotfixes) für Office Communications Server 2007 R2 bereit:
    
      - [Anwenden von Office Communications Server 2007 R2-Updates](apply-office-communications-server-2007-r2-updates.md)
    
      - [Beschreibung des kumulativen Updatepakets für Communicator 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Abrufen von Softwareupdates für Geräte](http://go.microsoft.com/fwlink/?linkid=335809)

2.  In Office Communications Server 2007 R2 muss die Clientversionsfilterung eingesetzt werden, damit sich nur Office Communications Server 2007 R2-Clients anmelden können, auf denen die aktuellsten Updates installiert sind.

3.  Setzen Sie in Office Communications Server 2007 R2 die Clientversionsfilterung ein, um die Anmeldung von Lync Server 2013-Clients zu blockieren. Führen Sie die in **Configuring Client Version Filtering** unter [http://go.microsoft.com/fwlink/?linkid=202488\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=202488%26clcid=0x407) beschriebenen Schritte durch, um die in der folgenden Tabelle aufgeführten Versionsfilter hinzuzufügen. Weisen Sie allen Versionsfiltern die Aktion **Blockieren** zu.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Client</th>
    <th>Benutzer-Agent-Header</th>
    <th>Version</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*.*.*</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*.*.*</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*.*.*</p></td>
    </tr>
    </tbody>
    </table>


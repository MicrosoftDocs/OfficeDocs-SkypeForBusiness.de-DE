---
title: Hinzufügen oder Entfernen eines Front-End-Servers in Lync Server 2013
TOCTitle: Hinzufügen oder Entfernen eines Front-End-Servers in Lync Server 2013
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205153(v=OCS.15)
ms:contentKeyID: 49295056
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hinzufügen oder Entfernen eines Front-End-Servers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-01-21_

Wenn Sie einem Pool einen Front-End-Server hinzufügen oder einen Front-End-Server aus einem Pool entfernen, müssen Sie den Pool anschließend neu starten. Wenden Sie beim Hinzufügen oder Entfernen eines Front-End-Servers das folgende Verfahren an, um Dienstunterbrechungen für die Benutzer zu verhindern.

## So fügen Sie Front-End-Server hinzu oder entfernen sie

1.  Wenn Sie Front-End-Server entfernen, beenden Sie zunächst neue Verbindungen mit diesen Servern. Dazu können Sie das folgende Cmdlet verwenden:
    
        Stop -CsWindowsServices -Graceful

2.  Wenn auf den zu entfernenden Servern keine aktuellen Sitzungen vorhanden sind, halten Sie die Lync Server-Dienste auf diesen Servern an.

3.  Öffnen Sie den Topologie-Generator, und fügen Sie die benötigten Server hinzu, oder entfernen Sie sie.

4.  Veröffentlichen Sie die Topologie.

5.  Wenn der Pool zuvor zwei Front-End-Server umfasste und nun mehr als zwei Server beinhaltet oder wenn der Pool zuvor mehr als zwei Server enthielt und nun genau zwei Server darin existieren, müssen Sie das folgende Cmdlet eingeben:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Wenn der Pool drei oder mehr Server aufweist, müssen beim Eingeben dieses Cmdlets mindestens drei dieser Server ausgeführt werden.

6.  Starten Sie alle Front-End-Server im Pool jeweils einzeln neu.


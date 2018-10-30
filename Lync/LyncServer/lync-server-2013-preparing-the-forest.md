---
title: 'Lync Server 2013: Vorbereiten der Gesamtstruktur'
TOCTitle: Vorbereiten der Gesamtstruktur
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425898(v=OCS.15)
ms:contentKeyID: 49293754
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vorbereiten der Gesamtstruktur für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Bei der Gesamtstrukturvorbereitung werden globale Active Directory-Einstellungen und -Objekte und universelle Active Directory-Gruppen zur Verwendung durch Lync Server 2013 erstellt, und den Active Directory-Objekten werden geeignete Zugriffsberechtigungen gewährt. Eine Beschreibung der universellen Gruppen und der globalen Einstellungen und Objekte, die bei der Gesamtstrukturvorbereitung erstellt werden, finden Sie unter [Änderungen bei der Gesamtstrukturvorbereitung in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).

Außerdem werden bei der Gesamtstrukturvorbereitung Objekte erstellt, die von Lync Server 2013 verwendete Eigenschaftensätze und Anzeigespezifizierer enthalten. Die Objekte werden im Konfigurationscontainer gespeichert.


> [!IMPORTANT]
> Stellen Sie sicher, dass die während der Schemavorbereitung durchgeführten Änderungen auf alle Domänencontroller repliziert wurden, bevor Sie mit der Gesamtstrukturvorbereitung beginnen. Wenn die Replikation noch nicht abgeschlossen wurde, tritt ein Fehler auf.



Wenn Sie eine neue Lync Server-Bereitstellung durchführen, müssen Sie globale Einstellungen auf der Konfigurationspartition speichern. Wenn Sie ein Upgrade von einer früheren Version durchführen und globale Einstellungen noch im Systemcontainer speichern, können Sie den Systemcontainer weiterhin verwenden.

Zum Durchführen dieses Verfahrens müssen Sie ein Mitglied der Gruppe "Organisations-Admins" oder "Domänen-Admins" für die Stammdomäne der Gesamtstruktur sein.

## In diesem Abschnitt

  - [Ausführen der Gesamtstrukturvorbereitung für Lync Server 2013](lync-server-2013-running-forest-preparation.md)

  - [Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)


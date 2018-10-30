---
title: 'Lync Server 2013: Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung'
TOCTitle: Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204866(v=OCS.15)
ms:contentKeyID: 49293883
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-25_

Lync Server 2013 bietet eine hohe Verfügbarkeit durch Serverredundanz aufgrund von Poolbildung. Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen. Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors. Nähere Informationen zu Serverrollen finden Sie unter [Serverrollen in Lync Server 2013](lync-server-2013-server-roles.md).

Lync Server 2013 bietet darüber hinaus Maßnahmen für die Notfallwiederherstellung durch die Kopplung von Pools. Bei der Bereitstellung dieser Topologie legen Sie Paare mit Front-End-Pools fest. Jeder Pool in einem Paar befindet sich dabei in einem separaten Rechenzentrum und in einem separaten geografischen Bereich. Wenn ein Pool oder Standort ausfällt, können die Benutzer dieses Pools an den anderen Pool im Paar weitergeleitet werden, ohne dass es zu nennenswerten Unterbrechungen des Diensts käme.

Lync Server 2013 unterstützt darüber hinaus die Hochverfügbarkeit für Back-End-Server. In dieser optionalen Topologie werden zwei Back-End-Server für einen Front-End-Pool bereitgestellt, und synchrone SQL Server-Spiegelungen für alle Lync-Datenbanken mit den Back-End-Servern werden eingerichtet.

Nähere Informationen zur Kopplung von Pools und zur Spiegelung von Back-End-Servern finden Sie unter [Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

## Siehe auch

#### Konzepte

[Serverrollen in Lync Server 2013](lync-server-2013-server-roles.md)  
[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)


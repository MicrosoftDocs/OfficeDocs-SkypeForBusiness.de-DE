---
title: 'Lync Server 2013: Unterstützte Optionen und bewährte Methoden für das Einrichten von Poolpaaren'
TOCTitle: Unterstützte Optionen und bewährte Methoden für das Einrichten von Poolpaaren
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204697(v=OCS.15)
ms:contentKeyID: 49293260
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützte Optionen und bewährte Methoden für das Einrichten von Poolpaaren in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2017-03-09_

Die Entfernung zwischen zwei Rechenzentren, die als Paar bereitgestellte Front-End-Pools enthalten sollen, ist nicht begrenzt. Wir empfehlen die Verwendung zweier Rechenzentren in derselben Weltregion mit Hochgeschwindigkeitsverbindung. Die Rechenzentren sollen weit genug voneinander entfernt sein, damit sie nicht gleichzeitig von einem Notfall betroffen sein können.

Die Verwendung zweier Rechenzentren in verschiedenen Weltregionen ist zwar möglich, führt jedoch u. U. zu größeren Datenverlusten aufgrund von Wartezeiten bei der Datenreplikation.

Beachten Sie bei der Planung, welche Pools als Paar bereitgestellt werden, dass nur die folgenden Paarungen unterstützt werden:

  - Enterprise Edition-Pools können nur mit anderen Enterprise Edition-Pools gepaart werden. Entsprechend können Standard Edition-Pools nur mit anderen Standard Edition-Pools gepaart werden.

  - Physische Pool können nur mit andere physischen Pools gepaart werden. Entsprechend können virtuelle Pools nur mit anderen virtuellen Pools gepaart werden.

Das Paaren zweier Pools, das nicht diesen Empfehlungen entspricht, wird weder durch den Topologie-Generator noch durch die Topologieüberprüfung verhindert. Der Topologie-Generator lässt z. B. die Paarung eines Enterprise Edition-Pools mit einem Standard Edition-Pool zu. Diese Art von Paarung wird jedoch nicht unterstützt.

Jeder Pool in einem Paar sollte über ausreichend Kapazität verfügen, um bei einem Notfall alle Benutzer zu bedienen.

Wenn Sie Enterprise Edition-Pools paaren, können Sie auch auf den Back-End-Servern hohe Verfügbarkeit bereitstellen; bei Paaren aus Standard Edition-Pools stehen jedoch nur die Notfallwiederherstellungsmaßnahmen zur Verfügung.


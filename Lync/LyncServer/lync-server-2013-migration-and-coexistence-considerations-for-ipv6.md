---
title: 'Lync Server 2013: Überlegungen zu Migration und Koexistenz für IPv6'
TOCTitle: Überlegungen zu Migration und Koexistenz für IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205068(v=OCS.15)
ms:contentKeyID: 49294692
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überlegungen zu Migration und Koexistenz für IPv6 in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-06-14_

IPv6 (IP Version 6) wird unter Lync Server 2010 oder Office Communications Server nicht unterstützt. Bei einer Pilotinstallation können Sie die Koexistenz dualer Stapel von Lync Server 2010 und Lync Server 2013 testen. Es wird empfohlen, dass alle Pools für einen bestimmten zentralen Standort auf Lync Server 2013 aktualisiert werden, bevor IPv6 (Netzwerk dualer Stapel) für einen beliebigen Pool aktiviert wird. Wenn Sie einen Pool nur für IPv6 konfigurieren müssen, wird empfohlen, dass Sie einen Pool nur mit IPv6 in Ihrer Testumgebung zum Testen einrichten.

Die folgenden Szenarien werden bei der Migration und Koexistenz unterstützt:

  - Lync Server 2013-, Lync Server 2010- und Office Communications Server 2007 R2-Pools im IPv4-Modus, die mit Lync Server 2013 im dualen Stapelmodus koexistieren.

  - Lync Server 2013-Pool im Nur-IPv6-Modus, wenn der Nur-IPv6-Pool in Silos zusammengefasst wird.


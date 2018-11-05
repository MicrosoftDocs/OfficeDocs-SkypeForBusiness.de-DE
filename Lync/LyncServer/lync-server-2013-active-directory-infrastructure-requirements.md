---
title: 'Lync Server 2013: Active Directory-Infrastrukturanforderungen'
TOCTitle: Active Directory-Infrastrukturanforderungen
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412955(v=OCS.15)
ms:contentKeyID: 49295311
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Active Directory-Infrastrukturanforderungen für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Bevor Sie mit der Vorbereitung von Active Directory-Domänendienste für Lync Server 2013 beginnen, stellen Sie sicher, dass Ihre Active Directory-Infrastruktur die folgenden Anforderungen erfüllt:

  - Auf allen Domänencontrollern (die sämtliche globalen Katalogserver umfassen) in der Gesamtstruktur, in der Lync Server bereitgestellt wird, wird eines der folgenden Betriebssysteme ausgeführt:
    
      - Windows Server 2012 R2-Betriebssystem
    
      - Windows Server 2012-Betriebssystem
    
      - Windows Server 2008 R2-Betriebssystem
    
      - Windows Server 2008-Betriebssystem
    
      - Windows Server 2008 Enterprise 32-Bit
    
      - 32-Bit- oder 64-Bit-Version des Windows Server 2003 R2-Betriebssystems
    
      - 32-Bit- oder 64-Bit-Version des Windows Server 2003-Betriebssystems

  - Alle Domänen, in denen Sie Lync Server bereitstellen, werden auf eine Domänenfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 heraufgestuft.

  - Die Gesamtstruktur, in der Sie Lync Server bereitstellen, wird auf eine Gesamtstrukturfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 heraufgestuft.
    

    > [!NOTE]
    > Informationen zum Ändern der Funktionsebene von Domänen oder Gesamtstrukturen finden Sie in der TechNet-Bibliothek unter "Heraufstufen von Domänen- und Gesamtstrukturfunktionsebenen" unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=263775">http://go.microsoft.com/fwlink/?linkid=263775</A>.



  - In jeder Domäne, in der Lync Server-Computer oder -Benutzer bereitgestellt werden, wurde ein globaler Katalog bereitgestellt.

Lync Server 2013 unterstützt die universellen Gruppen in den Betriebssystemen Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 und Windows Server 2003 Mitglieder universeller Gruppen können andere Gruppen und Konten aus beliebigen Domänen in der Domänen- oder Gesamtstruktur umfassen und über Berechtigungen für beliebige Domänen in der Domänen- oder Gesamtstruktur verfügen. Durch die Unterstützung universeller Gruppen in Verbindung mit der Delegierung administrativer Aufgaben wird die Verwaltung einer Lync Server-Bereitstellung vereinfacht. Beispielsweise ist es nicht erforderlich, eine Domäne einer anderen hinzuzufügen, um einem Administrator die Verwaltung beider Domänen zu ermöglichen.


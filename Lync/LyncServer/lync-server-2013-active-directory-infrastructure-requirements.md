---
title: 'Lync Server 2013: Active Directory Infrastrukturanforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14980b886ac9a00b9ea23a0d915bc34ac3956c7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Active Directory Infrastrukturanforderungen für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

Bevor Sie mit dem vorbereiten Active Directory-Domänendienste für lync Server 2013 beginnen, müssen Sie sicherstellen, dass Ihre Active Directory Infrastruktur die folgenden Voraussetzungen erfüllt:

  - Alle Domänencontroller (einschließlich aller globalen Katalogserver) in der Gesamtstruktur, in der Sie lync Server bereitstellen, führen eines der folgenden Betriebssysteme aus:
    
      - Windows Server 2012 R2-Betriebssystem
    
      - Windows Server 2012 Betriebssystem
    
      - Windows Server 2008 R2-Betriebssystem
    
      - Windows Server 2008-Betriebssystem
    
      - Windows Server 2008 Enterprise 32-Bit
    
      - 32-Bit- oder 64-Bit-Version von Windows Server 2003 R2
    
      - 32-Bit-oder 64-Bit-Versionen des Windows Server 2003-Betriebssystems

  - Alle Domänen, in denen Sie lync Server bereitstellen, werden auf eine Domänenfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 heraufgesetzt.

  - Die Gesamtstruktur, in der Sie lync Server bereitstellen, wird auf eine Gesamtstrukturfunktionsebene von Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 oder mindestens Windows Server 2003 heraufgesetzt.
    
    <div>
    

    > [!NOTE]  
    > Informationen zum Ändern der Domänen-oder Gesamtstrukturfunktionsebene finden Sie unter "Heraufstufen von Domänen-und Gesamtstruktur <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>Funktionsebenen" in der TechNet-Bibliothek unter.

    
    </div>

  - Ein globaler Katalog wird in jeder Domäne bereitgestellt, in der Sie lync Server Computer oder Benutzer bereitstellen.

Lync Server 2013 unterstützt die universellen Gruppen in den Betriebssystemen Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 und Windows Server 2003. Mitglieder universeller Gruppen können andere Gruppen und Konten aus beliebigen Domänen in der Domänen- oder Gesamtstruktur umfassen und über Berechtigungen für beliebige Domänen in der Domänen- oder Gesamtstruktur verfügen. Die universelle Gruppenunterstützung in Kombination mit der Administrator Delegierung vereinfacht die Verwaltung einer lync Server-Bereitstellung. Beispielsweise ist es nicht erforderlich, eine Domäne einer anderen hinzuzufügen, um einem Administrator die Verwaltung beider Domänen zu ermöglichen.

</div>

<span> </span>

</div>

</div>

</div>


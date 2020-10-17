---
title: 'Lync Server 2013: Anforderungen zum Veröffentlichen einer Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9f4186a351876b874a8b84963f9923369511f65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511822"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Anforderungen zum Veröffentlichen einer Topologie in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

In diesem Thema werden die Infrastruktur-und Softwareanforderungen beschrieben, die für die Veröffentlichung einer Topologie spezifisch sind, sei es mithilfe des Topologie-Generators oder der Befehlszeilenschnittstelle für die lync Server 2013 Verwaltungsshell. Diese Anforderungen gelten zusätzlich zu den allgemeinen Betriebssystem-, Software-und Berechtigungsanforderungen für alle lync Server 2013 Verwaltungstools. Stellen Sie sicher, dass Sie alle Anforderungen an die Verwaltungstools erfüllen, bevor Sie eine Topologie veröffentlichen.

  - Sie müssen den Topologie-Generator auf einem Computer ausführen, der der gleichen Domäne oder Gesamtstruktur der lync Server 2013 Bereitstellung beigetreten ist, die Sie erstellen, damit Active Directory-Domänendienste Vorbereitungsschritte bereits abgeschlossen sind, sodass Sie die Verwaltungstools auf diesem Computer verwenden können, um die Topologie erfolgreich zu veröffentlichen.

  - Die in der Topologie definierten Computer müssen mit der Domäne (mit Ausnahme der Edgeserver) und in AD DS verbunden werden. Die Computer müssen beim Veröffentlichen der Topologie jedoch nicht online sein.

  - Die Dateifreigabe für den Pool muss erstellt worden und für Remotebenutzer verfügbar sein.

  - Zum Veröffentlichen eines Enterprise Edition-Front-End-Pool muss der SQL Server basierte Back-End-Server der Domäne hinzugefügt werden, in der Sie die Server bereitstellen, Online und mit den entsprechenden Firewallregeln konfiguriert, um Sie Remotebenutzern zur Verfügung zu stellen. Ausführliche Informationen zum Angeben von Firewall-Ausnahmen finden Sie unter [Understanding Firewall Requirements for SQL Server with lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Weitere Informationen zum Konfigurieren von SQL Server finden Sie unter [configure SQL Server for lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    
    <div>
    

    > [!NOTE]  
    > Standard Edition-Server verfügt über eine zusammengefasste Datenbank, in der die veröffentlichte Konfiguration akzeptiert wird. Sie müssen zuerst die Setup Aufgabe <STRONG>Prepare First Standard Edition-Server</STRONG> im lync Server-Bereitstellungs-Assistenten ausführen.

    
    </div>

<div>

## <a name="see-also"></a>Siehe auch


[Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  


[Softwareanforderungen für Verwaltungstools in lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Für die Einrichtung und Verwaltung von lync Server 2013 erforderliche Administrator Rechte und-Berechtigungen](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


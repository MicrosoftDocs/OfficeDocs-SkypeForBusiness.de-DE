---
title: 'Lync Server 2013: Anforderungen an das Veröffentlichen einer Topologie'
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
ms.openlocfilehash: 0f1422df35ebbe9f368dc8aa3d121caf740e7033
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Anforderungen an das Veröffentlichen einer Topologie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

In diesem Thema werden die Infrastruktur-und Softwareanforderungen beschrieben, die für das Veröffentlichen einer Topologie spezifisch sind, sei es mithilfe des Topologie-Generators oder der Befehlszeilenschnittstelle der lync Server 2013-Verwaltungsshell. Diese Anforderungen gelten zusätzlich zu den allgemeinen Betriebssystem-, Software-und Berechtigungsanforderungen, die für alle lync Server 2013-Verwaltungstools gelten. Stellen Sie sicher, dass Sie die Anforderungen aller administrativen Tools erfüllen, bevor Sie eine Topologie veröffentlichen.

  - Sie müssen den Topology Builder auf einem Computer ausführen, der mit der gleichen Domäne oder Gesamtstruktur der von Ihnen erstellten lync Server 2013-Bereitstellung verbunden ist, damit die Schritte zur Vorbereitung der Active Directory-Domänendienste bereits abgeschlossen sind, sodass Sie die Verwaltungstools auf verwenden können. dieser Computer, um Ihre Topologie erfolgreich zu veröffentlichen.

  - Die in der Topologie definierten Computer müssen der Domäne, mit Ausnahme von Edgeserver und in AD DS, beigetreten sein. Die Computer müssen jedoch nicht online sein, wenn Sie die Topologie veröffentlichen.

  - Die Dateifreigabe für den Pool muss erstellt und für Remotebenutzer verfügbar sein.

  - Zum Veröffentlichen eines Enterprise Edition-Front-End-Pools muss der auf SQL Server basierende Back-End-Server mit der Domäne verbunden sein, in der Sie die Server online bereitstellen, und mit den entsprechenden Firewallregeln konfiguriert werden, um ihn Remotebenutzern zur Verfügung zu stellen. Details zum Angeben von Firewall-Ausnahmen finden Sie unter [Grundlegendes zu Firewall-Anforderungen für SQL Server mit lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Weitere Informationen zum Konfigurieren von SQL Server finden Sie unter [Konfigurieren von SQL Server für lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    
    <div>
    

    > [!NOTE]  
    > Der Standard Edition-Server verfügt über eine Datenbank, die die veröffentlichte Konfiguration akzeptiert. Sie müssen zuerst im lync Server-Bereitstellungs-Assistenten die Aufgabe " <STRONG>First Standard Edition-Server vorbereiten</STRONG> " ausführen.

    
    </div>

<div>

## <a name="see-also"></a>Siehe auch


[Veröffentlichen der Topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  


[Softwareanforderungen für Verwaltungstools in Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Erforderliche Administratorrechte und Gruppenmitgliedschaften für die Installation und Verwaltung von Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Installieren von Lync Server-Verwaltungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1115d5848806f95d35a158f36b7689967cec5d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>Installieren von Lync Server 2013-Verwaltungstools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

In diesem Thema wird beschrieben, wie Sie die Verwaltungstools installieren, die Sie zum Bereitstellen und Verwalten von lync Server 2013 verwenden müssen. Die Verwaltungstools werden standardmäßig auf jedem Server installiert, auf dem lync Server 2013 ausgeführt wird. Darüber hinaus können Sie die Verwaltungstools auf anderen Computern installieren, beispielsweise in dedizierten Verwaltungskonsolen. Wir empfehlen dringend, dass Sie die Verwaltungstools auf einem Computer installieren, der sich in der gleichen Domäne oder Gesamtstruktur wie die von Ihnen erstellte lync Server 2013-Bereitstellung befindet, weil Sie dadurch sicherstellen, dass die Schritte zur Vorbereitung der Active Directory-Domänendienste bereits ausgeführt werden. Complete, mit dem Sie die Verwaltungstools auf diesem Computer später zum Veröffentlichen Ihrer Topologie verwenden können.

Stellen Sie sicher, dass Sie die Anforderungen für Infrastruktur, Betriebssystem, Software und Administratorrechte überprüfen, bevor Sie die lync Server 2013-Verwaltungstools installieren oder verwenden. Details zu den Infrastrukturanforderungen finden Sie unter [Infrastrukturanforderungen für Verwaltungstools in lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Ausführliche Informationen zu den Anforderungen des Betriebssystems und der Software zum Installieren der lync Server 2013-Verwaltungstools finden Sie unter [Unterstützung des Betriebssystems Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md)und [Zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) Details zu den Benutzerrechten und Berechtigungen, die für die Installation und Verwendung der Tools erforderlich sind, finden Sie unter [Administrator Rechte und Berechtigungen, die für die Einrichtung und Verwaltung von lync Server 2013 erforderlich](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)sind.

<div>


> [!IMPORTANT]  
> Wenn Ihre Organisation erfordert, dass Sie Internet Informationsdienste (IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk finden, können Sie den Pfad für den Installationspfad für die lync Server-Dateien im Dialogfeld einrichten ändern. Wenn Sie die Setup Dateien in diesem Pfad, einschließlich OCSCore. msi, installieren, werden die restlichen lync Server 2013-Dateien ebenfalls auf diesem Laufwerk bereitgestellt.



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>So installieren Sie die lync Server 2013-Verwaltungstools

1.  Melden Sie sich als lokaler Administrator (Mindestanforderung) an dem Computer an, auf dem Sie die Verwaltungstools installieren möchten. Wenn Sie als ein Standardbenutzer unter den Betriebssystemen Windows Vista oder Windows 7 angemeldet sind und die Benutzerkontensteuerung (User Account Control, UAC) aktiviert ist, werden Sie aufgefordert, den lokalen Administrator oder einen Domänen äquivalenten Benutzernamen und das Kennwort einzugeben.

2.  Suchen Sie das Installationsmedium auf dem Computer, und doppelklicken Sie \\dann\\auf\\Setup amd64 Setup. exe.

3.  Wenn Sie aufgefordert werden, die Microsoft Visual C++ 2008-Distribution zu installieren, klicken Sie auf **Ja**.

4.  Klicken Sie auf der Seite **Microsoft lync Server 2013-Installationsspeicherort** auf **OK**. Ändern Sie diesen Pfad zu einem anderen Speicherort oder Laufwerk, wenn die Dateien an einem anderen Speicherort installiert werden müssen.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Ihre Organisation erfordert, dass Sie Internet Informationsdienste (IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk finden, können Sie den Pfad für den Installationspfad für die lync Server 2013-Dateien im Dialogfeld einrichten ändern. Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore. msi, werden auch die restlichen lync Server 2013-Dateien auf diesem Laufwerk bereitgestellt.

    
    </div>

5.  Überprüfen Sie auf der Seite Endbenutzer- **Lizenzvertrag** die Lizenzbedingungen, klicken Sie auf **Ich akzeptiere**, und klicken Sie dann auf **OK**. Dieser Schritt ist erforderlich, bevor Sie fortfahren können.

6.  Klicken Sie auf der Seite **Microsoft lync Server 2013 – Deployment-Assistent** auf **Administrator Tools installieren**.

7.  Wenn die Installation erfolgreich abgeschlossen wurde, klicken Sie auf **Beenden**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Öffnen der lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md)  


[Lync Server 2013-Verwaltungstools](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


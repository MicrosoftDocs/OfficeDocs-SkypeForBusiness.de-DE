---
title: 'Lync Server 2013: Installieren von lync Server Verwaltungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ded1dbdcd81c846db9f23574fa0b39efa0c33dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498722"
---
# <a name="install-lync-server-2013-administrative-tools"></a>Installieren von lync Server 2013 Verwaltungstools

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

In diesem Thema wird beschrieben, wie Sie die Verwaltungstools installieren, die Sie für die Bereitstellung und Verwaltung von lync Server 2013 verwenden müssen. Die Verwaltungstools werden auf jedem Server mit lync Server 2013 standardmäßig installiert. Sie können die Verwaltungstools auch auf anderen Computern wie etwa dedizierten Verwaltungskonsolen installieren. Es wird dringend empfohlen, dass Sie die Verwaltungstools auf einem Computer installieren, der sich in der gleichen Domäne oder Gesamtstruktur wie die lync Server 2013 Bereitstellung befindet, die Sie erstellen, da Sie dadurch sicherstellen, dass Active Directory-Domänendienste Vorbereitungsschritte bereits abgeschlossen sind, sodass Sie später die Verwaltungstools auf diesem Computer zum Veröffentlichen Ihrer Topologie verwenden können.

Stellen Sie sicher, dass Sie die Anforderungen an Infrastruktur, Betriebssystem, Software und Administratorrechte überprüfen, bevor Sie die lync Server 2013 Verwaltungstools installieren oder verwenden. Ausführliche Informationen zu den Infrastrukturanforderungen finden Sie unter [Administrative Tools Infrastructure Requirements in lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Ausführliche Informationen zu den Betriebssystem-und Softwareanforderungen für die Installation der lync Server 2013 Verwaltungstools finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md)sowie [zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Ausführliche Informationen zu den Benutzerrechten und-Berechtigungen, die für die Installation und Verwendung der Tools erforderlich sind, finden Sie unter [Administrator Rechte und-Berechtigungen, die für die Einrichtung und Verwaltung von lync Server 2013 erforderlich](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)sind.

<div>


> [!IMPORTANT]  
> Wenn die Internetinformationsdienste (IIS) und alle Webdienste in Ihrer Organisation auf einem anderen Laufwerk als auf dem Systemlaufwerk platziert werden müssen, können Sie das Installationsverzeichnis für die Lync Server-Dateien im Setupdialogfeld ändern. Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen lync Server 2013 Dateien auf diesem Laufwerk bereitgestellt.



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>So installieren Sie die lync Server 2013 Verwaltungstools

1.  Melden Sie sich mindestens als lokaler Administrator auf dem Computer an, auf dem der fea-cs-topo-tool und die Verwaltungstools installiert werden sollen. Wenn Sie als Standardbenutzer bei einem Windows Vista- oder Windows 7-Betriebssystem angemeldet sind und die Benutzerkontensteuerung aktiviert ist, werden Sie zur Eingabe von Name und Kennwort für den lokalen Administrator oder für ein gleichwertiges Domänenbenutzerkonto aufgefordert.

2.  Suchen Sie das Installationsmedium auf Ihrem Computer, und doppelklicken Sie dann auf \\ Setup \\ amd64 \\Setup.exe.

3.  Klicken Sie auf **Ja**, wenn Sie zur Installation von Microsoft Visual C++ 2008 Distributable aufgefordert werden.

4.  Klicken Sie auf der Seite **Installationsspeicherort für Microsoft lync Server 2013** auf **OK**. Ändern Sie diesen Pfad in einen anderen Speicherort oder ein anderes Laufwerk, wenn Sie die Dateien an einem anderen Speicherort installieren müssen.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn in Ihrer Organisation Internet Information Services (IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk gefunden werden müssen, können Sie den Pfad für den Installationspfad für die lync Server 2013 Dateien im Dialogfeld Setup ändern. Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen lync Server 2013 Dateien auf diesem Laufwerk bereitgestellt.

    
    </div>

5.  Lesen Sie die Lizenzbedingungen auf der Seite **Endbenutzer-Lizenzvertrag**, klicken Sie auf **Ich stimme zu** und anschließend auf **OK**. Dieser Schritt ist erforderlich, um fortfahren zu können.

6.  Klicken Sie auf der Seite **Microsoft lync Server 2013-Bereitstellungs-Assistenten** auf **Administrator Tools installieren**.

7.  Klicken Sie nach dem erfolgreichen Abschluss der Installation auf **Beenden**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Öffnen lync Server 2013 Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md)  


[Lync Server 2013 Verwaltungstools](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


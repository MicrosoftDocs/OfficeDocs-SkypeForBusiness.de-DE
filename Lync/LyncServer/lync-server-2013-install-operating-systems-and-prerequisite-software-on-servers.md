---
title: Installieren von Betriebssystemen und erforderlicher Software auf Servern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 266e8b049bd5de97fbb8f8d5d1e89b7280db3d4f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Installieren von Betriebssystemen und erforderlicher Software auf Servern für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-07-24_

Nachdem Sie die Hardware- und Systeminfrastruktur eingerichtet haben, müssen Sie die geeigneten Windows-Betriebssysteme und Updates sowie alle weiteren erforderlichen Softwarekomponenten auf sämtlichen Servern installieren, die Sie bereitstellen. Dies umfasst jede lync Server 2013-Server Rolle sowie alle weiteren Infrastrukturserver oder Server, auf denen SQL Server für Ihre Bereitstellung erforderlich sind.

<div>


> [!NOTE]
> Im vorliegenden Abschnitt wird die Installation der Betriebssysteme und der erforderlichen Softwarekomponenten für interne Server beschrieben. Wenn Sie Edgeserver bereitstellen, um den Zugriff durch externe Benutzer zu unterstützen, müssen Sie auch Betriebssysteme und die erforderliche Software für diese Server installieren, einschließlich Edgeserver und Reverse-Proxyservern. Ausführliche Informationen zum Vorbereiten von Servern zur Unterstützung des Zugriffs durch externe Benutzer finden Sie unter <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Vorbereiten der Installation von Servern im Umkreisnetzwerk für lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>Installieren von Windows-Betriebssystemen auf Servern

Installieren Sie auf jedem Server, den Sie bereitstellen, das entsprechende Windows-Betriebssystem wie folgt:

  - **Server mit lync Server 2013**   ausführliche Informationen zu den Betriebssystemanforderungen für Server mit lync Server 2013 finden Sie in der Unterstützungsdokumentation unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) .

  - **Datenbankserver**   ausführliche Informationen zu den Betriebssystemanforderungen für Datenbankserver, einschließlich der Back-End-Datenbank, Archivierungsdatenbank und Überwachungsdatenbank finden Sie in der SQL Server Dokumentation. Informationen zu SQL Server 2012 finden Sie in [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)der SQL Server 2012-Online Dokumentation unter.

<div>


> [!NOTE]
> Wenn Sie lync Server 2013 unter Windows Server&nbsp;2008&nbsp;R2 mit SP1 installieren, müssen Sie zuerst das Update installieren, das im Microsoft Knowledge-Artikel 2646886, "Update: Heap corruption" auftritt, wenn ein Modul die InsertEntityBody-Methode in IIS 7,5 aufruft, unter <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.<BR>Sie müssen auch die Registrierung wie im KB-Artikel, Ereignis- <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">IDs 32402, 61045, in lync Server 2013 auf Windows Server 2012 R2 installierten Front-End-Servern angemeldet sind</A>, ändern.



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>Installieren von Windows-Updates auf Servern

Installieren Sie die folgenden Updates von Windows Update auf jedem Server:

  - **Windows Update für Server mit lync Server 2013**   ausführliche Informationen zu den Updates von Windows Update, die für Server mit lync Server 2013 erforderlich sind, finden Sie unter [Additional Software Requirements for lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.

  - **Datenbankserver**   ausführliche Informationen zu den Updates, die für Datenbankserver erforderlich sind, einschließlich der Back-End-Datenbank, Archivierungsdatenbank und Überwachungsdatenbank finden Sie in der Dokumentation zu SQL Server 2012. Informationen zu SQL Server 2012 finden Sie in [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)der SQL Server 2012-Online Dokumentation unter.

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>Installieren zusätzlich erforderlicher Softwarekomponenten auf Servern

Lync Server 2013 erfordert die Installation der folgenden zusätzlichen Software auf Servern:

  - **Die erforderliche Software für Server, auf denen lync Server 2013**   die zusätzlichen Softwarevoraussetzungen für Server mit lync Server 2013 basieren, hängen von der bereitzustellenden Serverrolle ab. Ausführliche Informationen zu den spezifischen Softwareanforderungen für die einzelnen Server finden Sie in der Planungsdokumentation unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) .

  - **WindowsIdentity Foundation**   lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen. Um zu überprüfen, ob Sie bereits auf Ihrem Computer installiert wurde, wechseln Sie zur Systemsteuerung, klicken Sie auf **Programme und Funktionen**, **zeigen Sie installierte Updates**an, und schauen Sie unter **Microsoft Windows**nach. Ausführliche Informationen zum Installieren von Windows Identity Foundation finden [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Sie unter.

  - **Microsoft .NET Framework 4.5**   die 64-Bit-Version von Microsoft .NET Framework 4.5 ist für lync Server 2013 erforderlich.

  - **Erforderliche Software für Datenbankserver**   ausführliche Informationen zu den für Datenbankserver erforderlichen Windows-Updates, einschließlich der Back-End-Datenbank, Archivierungsdatenbank und Überwachungsdatenbank finden Sie in der [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)Dokumentation zu SQL Server 2012 unter.
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 wird Microsoft SQL Server 2012 Express automatisch auf jedem Standard Edition-Server und auf jedem Server mit lync Server 2013 installiert, auf dem sich der lokale Konfigurationsspeicher befindet.

    
    </div>

  - **Windows Media Format Laufzeit**   für alle Front-End-Server und Standard Edition-Server, auf denen Konferenzen bereitgestellt werden, muss die Windows Media Format Runtime installiert sein. Die Windows Media Format-Laufzeitkomponente ist für die WMA-Dateien (Windows Media Audio) erforderlich, die in der Anwendung zum Parken von Anrufen, in der Ansageanwendung und in der Reaktionsgruppenanwendung für die Wiedergabe von Ansagen und Musik verwendet werden.
    
    <div>
    

    > [!NOTE]
    > Für Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media Format Runtime mit Microsoft Media Foundation installiert.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Für Windows Server&nbsp;2008 und Windows Server&nbsp;2008&nbsp;R2 wird die Windows Media Format Runtime als Teil der Windows-Desktop Umgebung installiert. Es wird empfohlen, dass Sie Windows Desktop Experience installieren, bevor Sie lync Server 2013 installieren. Wenn lync Server 2013 diese Software nicht auf dem Server findet, werden Sie aufgefordert, Sie zu installieren, und Sie müssen den Server neu starten, um die Installation abzuschließen.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


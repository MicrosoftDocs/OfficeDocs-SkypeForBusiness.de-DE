---
title: Installieren von Betriebssystemen und erforderlicher Software auf Servern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a4eed86f12386b10b49d4290a4596b40c1fcc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Installieren von Betriebssystemen und erforderlicher Software auf Servern für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-07-24_

Nachdem Sie die Hardware-und Systeminfrastruktur eingerichtet haben, müssen Sie die entsprechenden Windows-Betriebssysteme und-Updates sowie alle anderen erforderlichen Software auf jedem Server installieren, den Sie bereitstellen. Dazu gehören jede lync Server 2013-Serverrolle sowie alle zusätzlichen Infrastrukturserver oder-Server, auf denen SQL Server ausgeführt wird, die für die Bereitstellung erforderlich sind.

<div>


> [!NOTE]
> In diesem Abschnitt werden die Installation von Betriebssystemen und die erforderliche Software für interne Server beschrieben. Wenn Sie Edgeserver zur Unterstützung des Zugriffs externer Benutzer bereitstellen, müssen Sie auch Betriebssysteme und die erforderliche Software für diese Server installieren, einschließlich Edgeserver und Reverse Proxy Server. Details zum Vorbereiten von Servern zur Unterstützung des Zugriffs externer Benutzer finden Sie unter <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Vorbereiten der Installation von Servern im Umkreisnetzwerk für lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>Installieren von Windows-Betriebssystemen auf Servern

Installieren Sie auf jedem Server, den Sie bereitstellen, das entsprechende Windows-Betriebssystem wie folgt:

  - **Server mit lync Server 2013**   Details zu den Betriebssystemanforderungen für Server mit lync Server 2013 finden Sie unter Unterstützung von [Server-und Tools-Betriebssystem in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.

  - **Datenbankserver**   Details zu den Betriebssystemanforderungen für Datenbankserver, einschließlich der Back-End-Datenbank, der Archivierungsdatenbank und der Überwachungsdatenbank, finden Sie in der SQL Server-Dokumentation. Informationen zu SQL Server 2012 finden Sie in [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)der SQL Server 2012-Online Dokumentation unter.

<div>


> [!NOTE]
> Wenn Sie lync Server 2013 unter Windows Server&nbsp;2008&nbsp;R2 mit SP1 installieren, müssen Sie zuerst das Update installieren, das im Microsoft Knowledge-basierten Artikel 2646886 beschrieben wird, "Fix: Heap Beschädigung tritt auf, wenn ein Modul die InsertEntityBody-Methode aufruft. in IIS 7,5 ", at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.<BR>Sie müssen auch die Registrierung ändern, wie im KB-Artikel <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">Ereignis-IDs 32402, 61045 in lync Server 2013-Front-End-Servern protokolliert werden, die in Windows Server 2012 R2 installiert sind</A>.



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>Installieren von Windows Update auf Servern

Installieren Sie die folgenden Updates von Windows Update auf jedem Server:

  - **Windows Update für Server mit lync Server 2013**   Details zu den Updates von Windows Update, die für Server mit lync Server 2013 erforderlich sind, finden Sie unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planung. Dokumentation.

  - **Datenbankserver**   Details zu den Updates von Windows Update, die für Datenbankserver erforderlich sind, einschließlich der Back-End-Datenbank, der Archivierungsdatenbank und der Überwachungsdatenbank, finden Sie in der SQL Server 2012-Dokumentation. Informationen zu SQL Server 2012 finden Sie in [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)der SQL Server 2012-Online Dokumentation unter.

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>Installieren anderer erforderlicher Software auf Servern

Lync Server 2013 erfordert die Installation der folgenden zusätzlichen Software auf Servern:

  - **Erforderliche Software für Server mit lync Server 2013**   die zusätzlichen Softwarevoraussetzungen für Server, auf denen lync Server 2013 ausgeführt wird, hängen davon ab, welche Serverrolle bereitgestellt wird. Details zu den spezifischen Softwareanforderungen für jeden Server finden Sie unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.

  - **WindowsIdentity Foundation**   lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen. Um zu überprüfen, ob Sie bereits auf Ihrem Computer installiert ist, wechseln Sie zur Systemsteuerung, klicken Sie auf **Programme und Funktionen**, **zeigen Sie installierte Updates**an, und schauen Sie unter **Microsoft Windows**nach. Informationen zum Installieren von Windows Identity Foundation finden Sie [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)unter.

  - **Microsoft .NET Framework 4,5**   die 64-Bit-Version von Microsoft .NET Framework 4,5 ist für lync Server 2013 erforderlich.

  - **Erforderliche Software für Datenbankserver**   Details zu den für Datenbankserver erforderlichen Windows-Updates, einschließlich der Back-End-Datenbank, der Archivierungsdatenbank und der Überwachungsdatenbank, finden Sie in [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)der SQL Server 2012-Dokumentation unter.
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 installiert Microsoft SQL Server 2012 Express automatisch auf jedem Standard Edition-Server und auf jedem Server mit lync Server 2013, auf dem sich der lokale Konfigurationsspeicher befindet.

    
    </div>

  - **Windows Media-Format Laufzeit**   alle Front-End-Server und Standard Edition-Server, auf denen Konferenzen bereitgestellt werden, müssen über die Windows Media-Format Laufzeit installiert sein. Die Windows Media-Format Laufzeit ist erforderlich, um die Windows Media-Audio-Dateien (WMA) auszuführen, die von den Anwendungen für die Anruf Park-, Ankündigungs-und Reaktionsgruppen für Ankündigungen und Musik abgespielt werden.
    
    <div>
    

    > [!NOTE]
    > Für Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media-Format Laufzeit mit Microsoft Media Foundation installiert.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Für Windows Server&nbsp;2008 und Windows Server&nbsp;2008&nbsp;R2 wird die Windows Media-Format Laufzeit als Teil der Windows-Desktop Oberfläche installiert. Es wird empfohlen, dass Sie die Windows-Desktop Umgebung installieren, bevor Sie lync Server 2013 installieren. Wenn lync Server 2013 diese Software auf dem Server nicht findet, werden Sie aufgefordert, Sie zu installieren, und dann müssen Sie den Server neu starten, um die Installation abzuschließen.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


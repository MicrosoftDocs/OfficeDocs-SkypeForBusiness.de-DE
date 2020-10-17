---
title: 'Lync Server 2013: Voraussetzungen für das lync VDI-Plug-in'
description: 'Lync Server 2013: Voraussetzungen für das lync VDI-Plug-in.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4389f776747426d07442e29418ab97e9609de7ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566541"
---
# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Voraussetzungen für lync VDI-Plug-ins in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2017-03-07_

In einer VDI-Umgebung (Virtual Desktop Infrastructure) müssen die virtuellen Computer und der lokale Computer des Benutzers die in diesem Abschnitt beschriebenen Anforderungen erfüllen.

<div>


> [!NOTE]  
> Informationen zum Installieren und Bereitstellen der virtualisierten Umgebung erhalten Sie von Ihrem Virtualisierungslösungsanbieter. Informationen zum Bereitstellen einer virtualisierten Umgebung basierend auf Hyper-V und Remotedesktopdiensten finden Sie in den folgenden Artikeln in der TechNet-Bibliothek von Microsoft: 
> <UL>
> <LI>
> <P>Hyper-V unter <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Remote Desktop Dienste in Windows Server &nbsp; 2008 &nbsp; R2 unter <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

Für die virtuellen Maschinen, die auf dem Rechenzentrumscomputer ausgeführt werden, gelten die folgenden Anforderungen:

  - Virtuelle Computer müssen mit Windows 10, Windows 8.1, Windows 8, Windows 7 oder Windows Server 2008 R2 mit den neuesten Service Packs konfiguriert werden.

Die folgenden Anforderungen gelten für den Benutzer und den lokalen Computer des Benutzers:

  - Der Benutzer muss in lync Server 2013 verwaltet werden.

  - Auf dem lokalen Computer muss Windows Embedded Standard 7 mit SP1, Windows 7 mit SP1, Windows 8, Windows 8.1 eingebettet oder Windows 8.1 (nicht eingebettet) installiert sein.

  - Wenn Sie Remote Desktop Dienste verwenden, muss das lync VDI-Plug-in Bitanzahl (das heißt, ob es sich um 32-Bit-oder 64-Bit-Anwendungen handelt) mit dem Betriebssystem Bitanzahl des lokalen Computers übereinstimmen. Die Bitanzahl des Betriebssystems auf dem lokalen Computer und das Betriebssystem auf dem virtuellen Computer müssen nicht übereinstimmen. Wenn Sie eine andere Virtualisierungslösung oder Plattform verwenden, lesen Sie den Leitfaden Ihres Anbieters für die Virtualisierungslösung zu Bitanzahl Anforderungen.

  - Auf dem lokalen Computer muss die neueste Version des Remotedesktopclients installiert sein. Installieren Sie die neuesten Updates des Remotedesktopdienste-Clients von Microsoft oder die neueste Remote Desktop-Client Software von Ihrem Anbieter für die Virtualisierung. Die neuesten Updates für Remote Desktop Dienste finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) .

  - Auf dem lokalen Computer müssen die Einstellungen für den Remotedesktopclient so konfiguriert sein, dass die Audiowiedergabe auf dem lokalen Computer aktiviert und die Remoteaufzeichnung deaktiviert ist. Informationen zum Konfigurieren dieser Einstellungen für die Remotedesktopverbindung in Windows finden Sie im nächsten Abschnitt "so konfigurieren Sie Einstellungen für die Remotedesktopverbindung".

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>So konfigurieren Sie Einstellungen der Remotedesktopverbindung

Führen Sie die folgenden Schritte aus, um die Remote Desktop Verbindung in Windows für das lync VDI-Plug-in vorzubereiten.

1.  Wenn der lokale Computer Windows 8 ausführt, überspringen Sie diesen Schritt. Wenn der lokale Computer Windows 7 mit SP1 ausführt, installieren Sie die neueste Windows 8-Version des Remote Desktop Dienste-Clients, die unter verfügbar ist [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) .

2.  Starten Sie den Remotedesktopdienste-Client, indem Sie auf **Start** und dann auf **Remotedesktopverbindung** klicken.

3.  Klicken Sie auf **Optionen**.

4.  Klicken Sie auf die Registerkarte **Lokale Ressourcen**. Klicken Sie unter **Remoteaudio** auf **Einstellungen**, und führen Sie die folgenden Aktionen aus:
    
      - Wählen Sie unter **Remoteaudiowiedergabe** die Option **Auf diesem Computer wiedergeben** aus.
    
      - Wählen Sie unter **Remoteaudioaufzeichnung** die Option **Nicht aufzeichnen** aus.
    
      - Klicken Sie auf **OK**.

5.  Klicken Sie auf die Registerkarte **Erweitert**. Deaktivieren Sie unter **Leistung** das Kontrollkästchen **Dauerhafte Bitmapzwischenspeicherung**.

6.  Klicken Sie auf die Registerkarte **Allgemein**. Geben Sie im Feld **Computer** den Namen der virtuellen Maschine ein, und klicken Sie dann auf **Verbinden**.

</div>

</div>

<span> </span>

</div>

</div>

</div>


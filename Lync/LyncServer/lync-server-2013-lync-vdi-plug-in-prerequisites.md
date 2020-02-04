---
title: 'Lync Server 2013: Voraussetzungen für das Lync VDI-Plug-In'
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
ms.openlocfilehash: 51fb0081188618b6a5ea2951968effb0d55c4af7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Voraussetzungen für das Lync VDI-Plug-In in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2017-03-07_

In einer VDI-Umgebung (Virtual Desktop Infrastructure) müssen die virtuellen Computer und der lokale Computer des Benutzers die in diesem Abschnitt beschriebenen Anforderungen erfüllen.

<div>


> [!NOTE]  
> Informationen zum Installieren und Bereitstellen der virtualisierten Umgebung finden Sie in Ihrem Anbieter von Virtualisierungslösungen. Informationen zum Bereitstelleneiner virtualisierten Umgebung, die auf Hyper-V und Remote Desktop Diensten basiert, finden Sie in den folgenden Artikeln in der Microsoft TechNet-Bibliothek: 
> <UL>
> <LI>
> <P>Hyper-V at<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Remote Desktop Dienste in Windows Server&nbsp;2008&nbsp;R2 unter<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

Die folgenden Anforderungen gelten für die virtuellen Computer, die auf dem Rechenzentrums Computer ausgeführt werden:

  - Virtuelle Computer müssen mit Windows 10, Windows 8,1, Windows 8, Windows 7 oder Windows Server 2008 R2 mit den neuesten Service Packs konfiguriert sein.

Die folgenden Anforderungen gelten für den Benutzer und den lokalen Computer des Benutzers:

  - Der Benutzer muss sich in lync Server 2013 befinden.

  - Auf dem lokalen Computer muss Windows Embedded Standard 7 mit SP1, Windows 7 mit SP1, Windows 8, Windows 8,1 Embedded oder Windows 8,1 (nicht eingebettet) ausgeführt werden.

  - Wenn Sie Remote Desktop Dienste verwenden, muss das lync VDI-Plug-in Bitanzahl (das heißt, ob es sich um eine 32-Bit-oder 64-Bit-Anwendung handelt) dem Betriebssystem Bitanzahl des lokalen Computers entsprechen. Die Bitanzahl des Betriebssystems auf dem lokalen Computer und das Betriebssystem auf dem virtuellen Computer müssen nicht übereinstimmen. Wenn Sie eine andere Virtualisierungslösung oder Plattform verwenden, finden Sie Informationen zu den Bitanzahl-Anforderungen unter Anleitung Ihres Virtualisierungslösung-Anbieters.

  - Auf dem lokalen Computer muss die neueste Version des Remotedesktopclients ausgeführt werden. Installieren Sie die neuesten Updates des Remotedesktopdienste-Clients von Microsoft oder der neuesten Remote Desktop-Client Software Ihres Virtualisierungslösung-Anbieters. Die neuesten Updates für Remote Desktop Dienste finden Sie [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)unter.

  - Auf dem lokalen Computer müssen die Einstellungen für den Remotedesktopclient so konfiguriert sein, dass die Audiowiedergabe auf dem lokalen Computer aktiviert und die Remoteaufzeichnung deaktiviert ist. Informationen zum Konfigurieren dieser Einstellungen für die Remotedesktopverbindung in Windows finden Sie im nächsten Abschnitt "so konfigurieren Sie die Einstellungen für Remotedesktopverbindung".

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>So konfigurieren Sie die Einstellungen für Remote Desktop Verbindung

Führen Sie die folgenden Schritte aus, um die Remote Desktop Verbindung in Windows für das lync VDI-Plug-in vorzubereiten:

1.  Wenn auf dem lokalen Computer Windows 8 ausgeführt wird, überspringen Sie diesen Schritt. Wenn auf dem lokalen Computer Windows 7 mit SP1 ausgeführt wird, installieren Sie die neueste Version von Windows 8 des Remote Desktop Dienste-Clients [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032), die unter verfügbar ist.

2.  Starten Sie den Remotedesktopdienste-Client, indem Sie auf **Start** und dann auf **Remotedesktopverbindung** klicken.

3.  Klicken Sie auf **Optionen**.

4.  Klicken Sie auf die Registerkarte **Lokale Ressourcen**. Klicken Sie unter **Remoteaudio** auf **Einstellungen**, und gehen Sie wie folgt vor:
    
      - Wählen Sie unter **Remoteaudiowiedergabe** die Option **Auf diesem Computer wiedergeben** aus.
    
      - Wählen Sie unter **Remoteaudioaufzeichnung** die Option **Nicht aufzeichnen** aus.
    
      - Klicken Sie anschließend auf **OK**.

5.  Klicken Sie auf die Registerkarte **Erweitert**. Deaktivieren Sie unter **Leistung** das Kontrollkästchen **Dauerhafte Bitmapzwischenspeicherung**.

6.  Klicken Sie auf die Registerkarte **Allgemein** . Geben Sie in **Computer**den Namen des virtuellen Computers ein, und klicken Sie dann auf **verbinden**.

</div>

</div>

<span> </span>

</div>

</div>

</div>


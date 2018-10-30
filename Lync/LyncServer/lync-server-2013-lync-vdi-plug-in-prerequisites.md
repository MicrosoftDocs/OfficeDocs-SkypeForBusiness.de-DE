---
title: 'Lync Server 2013: Voraussetzungen für das Lync VDI-Plug-In'
TOCTitle: Voraussetzungen für das Lync VDI-Plug-In
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205304(v=OCS.15)
ms:contentKeyID: 49295592
ms.date: 03/08/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Voraussetzungen für das Lync VDI-Plug-In in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2017-03-07_

In einer VDI-Umgebung (virtuelle Desktopinfrastruktur) müssen virtuelle Maschinen und der lokale Computer des Benutzers die in diesem Abschnitt beschriebenen Anforderungen erfüllen.


> [!NOTE]
> Informationen zum Installieren und Bereitstellen der virtualisierten Umgebung erhalten Sie von Ihrem Virtualisierungslösungsanbieter. Informationen zum Bereitstellen einer virtualisierten Umgebung basierend auf Hyper-V und Remotedesktopdiensten finden Sie in den folgenden Artikeln in der TechNet-Bibliothek von Microsoft: 
> <UL>
> <LI>
> <P>Hyper-V unter <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=247514">http://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Remotedesktopdienste in Windows Server&nbsp;2008&nbsp;R2 unter <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=247513">http://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



Für die virtuellen Maschinen, die auf dem Rechenzentrumscomputer ausgeführt werden, gelten die folgenden Anforderungen:

  - Virtuelle Maschinen müssen mit Windows 8, Windows 7 oder Windows Server 2008 R2 mit den neuesten Service Packs konfiguriert sein.

Für den Benutzer und den lokalen Computer des Benutzers gelten die folgenden Anforderungen:

  - Der Benutzer muss in Lync Server 2013 verwaltet werden.

  - Auf dem lokalen Computer muss Windows Embedded Standard 7 mit SP1, Windows 7 mit SP1 oder aber Windows 8 ausgeführt werden.

  - Falls Sie Remotedesktopdienste verwenden, muss die Bitanzahl des Lync-VDI-Plug-Ins (d. h., ob es sich um eine 32-Bit- oder 64-Bit-Anwendung handelt) mit der Bitanzahl des Betriebssystems auf dem lokalen Computer übereinstimmen. Die Bitanzahl des Betriebssystems auf dem lokalen Computer und des Betriebssystems auf der virtuellen Maschine müssen nicht übereinstimmen. Falls Sie eine andere Virtualisierungslösung oder Plattform verwenden, erhalten Sie von Ihrem Virtualisierungslösungsanbieter Informationen zu den Anforderungen bezüglich der Bitanzahl.

  - Auf dem lokalen Computer muss die neueste Version des Remotedesktopclients ausgeführt werden. Installieren Sie die neuesten Updates des Remotedesktopdienste-Clients von Microsoft bzw. die neueste Remotedesktopclient-Software von Ihrem Virtualisierungslösungsanbieter. Die neuesten Updates für den Remotedesktopdienst finden Sie unter [http://go.microsoft.com/fwlink/p/?LinkId=268032](http://go.microsoft.com/fwlink/p/?linkid=268032).

  - Auf dem lokalen Computer müssen die Einstellungen für den Remotedesktopclient so konfiguriert sein, dass die Audiowiedergabe auf dem lokalen Computer aktiviert und die Remoteaufzeichnung deaktiviert ist. Informationen zum Konfigurieren dieser Einstellungen für die Remotedesktopverbindung in Windows finden Sie im nächsten Abschnitt, "So konfigurieren Sie Einstellungen der Remotedesktopverbindung".

## So konfigurieren Sie Einstellungen der Remotedesktopverbindung

Führen Sie zum Vorbereiten der Remotedesktopverbindung in Windows für das Lync-VDI-Plug-In die folgenden Schritte aus.

1.  Wenn auf dem lokalen Computer Windows 8 ausgeführt wird, überspringen Sie diesen Schritt. Wird dort Windows 7 mit SP1 ausgeführt, installieren Sie die aktuelle Windows 8-Version des Remotedesktopdienste-Clients, die unter [http://go.microsoft.com/fwlink/p/?LinkId=268032](http://go.microsoft.com/fwlink/p/?linkid=268032) heruntergeladen werden kann.

2.  Starten Sie den Remotedesktopdienste-Client, indem Sie auf **Start** und dann auf **Remotedesktopverbindung** klicken.

3.  Klicken Sie auf **Optionen** .

4.  Klicken Sie auf die Registerkarte **Lokale Ressourcen** . Klicken Sie unter **Remoteaudio** auf **Einstellungen** , und führen Sie die folgenden Aktionen aus:
    
      - Wählen Sie unter **Remoteaudiowiedergabe** die Option **Auf diesem Computer wiedergeben** aus.
    
      - Wählen Sie unter **Remoteaudioaufzeichnung** die Option **Nicht aufzeichnen** aus.
    
      - Klicken Sie auf **OK** .

5.  Klicken Sie auf die Registerkarte **Erweitert** . Deaktivieren Sie unter **Leistung** das Kontrollkästchen **Dauerhafte Bitmapzwischenspeicherung** .

6.  Klicken Sie auf die Registerkarte **Allgemein** . Geben Sie im Feld **Computer** den Namen der virtuellen Maschine ein, und klicken Sie dann auf **Verbinden** .


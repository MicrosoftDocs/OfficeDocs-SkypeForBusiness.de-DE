---
title: 'Lync Server 2013: Installieren von Betriebssystemen und erforderlicher Software auf Servern'
TOCTitle: Installieren von Betriebssystemen und erforderlicher Software auf Servern
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398103(v=OCS.15)
ms:contentKeyID: 49293041
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren von Betriebssystemen und erforderlicher Software auf Servern für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Nachdem Sie die Hardware- und Systeminfrastruktur eingerichtet haben, müssen Sie die geeigneten Windows-Betriebssysteme und Updates sowie alle weiteren erforderlichen Softwarekomponenten auf sämtlichen Servern installieren, die Sie bereitstellen. Dies schließt die Lync Server 2013-Serverrollen und zusätzliche Infrastrukturserver und SQL Server-basierte Server ein, die für Ihre Bereitstellung erforderlich sind.


> [!NOTE]
> Im vorliegenden Abschnitt wird die Installation der Betriebssysteme und der erforderlichen Softwarekomponenten für interne Server beschrieben. Wenn Sie Edgeserver zur Unterstützung des externen Benutzerzugriffs bereitstellen, müssen Sie außerdem Betriebssysteme und erforderliche Softwarekomponenten für diese Server installieren, Edgeserver und Reverseproxyserver eingeschlossen. Ausführliche Informationen zum Vorbereiten von Servern auf die Unterstützung des externen Benutzerzugriffs finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Vorbereiten der Installation von Servern im Umkreisnetzwerk für Lync Server 2013</A>.



## Installieren von Windows-Betriebssystemen auf Servern

Installieren Sie auf jedem bereitgestellten Server das geeignete Windows-Betriebssystem wie folgt:

  - **Server mit Lync Server 2013**   Ausführliche Informationen zu den Betriebssystemanforderungen für Server mit Lync Server 2013 finden Sie in der Unterstützungsdokumentation unter [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md).

  - **Databankserver**   Ausführliche Informationen zu den Betriebssystemanforderungen für Datenbankserver, einschließlich Back-End-Datenbank, Archivierungsdatenbank und Überwachungsdatenbank, finden Sie in der SQL Server-Dokumentation. Informationen zu SQL Server 2012 finden Sie in der Onlinedokumentation zu SQL Server 2012 unter [http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0x407).


> [!NOTE]
> Wenn Sie Lync Server 2013 unter Windows Server&nbsp;2008&nbsp;R2 mit SP1 installieren, müssen Sie zunächst das im Microsoft Knowledge Base-Artikel 2646886, "Hotfix: Beim Aufrufen der Methode InsertEntityBody in IIS 7.5 durch ein Modul tritt eine Heapbeschädigung auf", unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=3052&amp;clcid=0x407</A> beschriebene Update installieren.<BR>Sie müssen zudem die Registrierung wie im KB-Artikel <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">Ereignis-IDs 32402, 61045 in Lync Server 2013 Front-End-Servern protokolliert, die in Windows Server 2012 R2 installiert sind</A> beschrieben ändern.



## Installieren von Windows Update auf Servern

Installieren Sie die folgenden Updates von Windows Update auf jedem Server:

  - **Windows-Update für Server mit Lync Server 2013**   Ausführliche Informationen zu dem für Server mit Lync Server 2013 erforderlichen Windows Update-Updates finden Sie in der Planungsdokumentation unter [Zusätzliche Softwareanforderungen für Lync Server 2013](lync-server-2013-additional-software-requirements.md).

  - **Databankserver**   Ausführliche Informationen zu den Updates von Windows Update, die für Datenbankserver, einschließlich Back-End-Datenbank, Archivierungsdatenbank und Überwachungsdatenbank, erforderlich sind, finden Sie in der SQL Server 2012-Dokumentation. Informationen zu SQL Server 2012 finden Sie in der Onlinedokumentation zu SQL Server 2012 unter [http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0x407).

## Installieren zusätzlich erforderlicher Softwarekomponenten auf Servern

Für Lync Server 2013 ist die Installation der folgenden zusätzlichen Softwarekomponenten auf Servern erforderlich:

  - **Erforderliche Software für Server mit Lync Server 2013**   Die zusätzlich erforderlichen Softwarekomponenten für Server mit Lync Server 2013 richten sich danach, welche Serverrolle bereitgestellt wird. Ausführliche Informationen zu den spezifischen Softwareanforderungen für die einzelnen Server finden Sie in der Planungsdokumentation unter [Zusätzliche Softwareanforderungen für Lync Server 2013](lync-server-2013-additional-software-requirements.md).

  - **Windows Identity Foundation**    Lync Server 2013 erfordert die Installation von Windows Identity Foundation, damit Szenarios mit Server-zu-Server-Authentifizierung unterstützt werden. Um zu überprüfen, ob diese Komponente bereits auf dem Computer installiert wurde, rufen Sie die Systemsteuerung auf, klicken Sie auf **Programme und Funktionen** und **Installierte Updates anzeigen** und sehen Sie unter **Microsoft Windows** nach. Ausführliche Informationen zur Installation von Windows Identity Foundation finden Sie unter [http://go.microsoft.com/fwlink/?linkid=204657\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=204657%26clcid=0x407).

  - **Microsoft .NET Framework 4.5**   Für Lync Server 2013 ist die 64-Bit-Version von Microsoft .NET Framework 4.5 erforderlich.

  - **Erforderliche Software für Datenbankserver**   Ausführliche Informationen zu den erforderlichen Windows-Updates für Datenbankserver, einschließlich Back-End-Datenbank, Archivierungsdatenbank und Überwachungsdatenbank finden Sie in der Dokumentation zu SQL Server 2012 unter [http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0x407).
    

    > [!NOTE]
    > Lync Server 2013 installiert Microsoft SQL Server 2012 Express automatisch auf jedem Standard Edition-Server und jedem Server mit Lync Server 2013, auf dem sich der lokale Konfigurationsspeicher befindet.



  - **Windows Media Format-Laufzeitkomponente**   Auf allen Front-End-Server und Standard Edition-Server, auf denen Konferenzen bereitgestellt werden, muss die Windows Media Format-Laufzeitkomponente installiert sein. Die Windows Media Format-Laufzeitkomponente ist erforderlich, um die WMA-Dateien (Windows Media Audio) auszuführen, die von der Anrufpark-, Ankündigungs- und Reaktionsgruppenanwendung für Ankündigungen und Musik wiedergegeben werden.
    

    > [!NOTE]
    > Für Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media Format-Laufzeitkomponente mit Microsoft Media Foundation installiert.

    

    > [!NOTE]
    > Für Windows Server&nbsp;2008 und Windows Server&nbsp;2008&nbsp;R2 wird die Windows Media Format-Laufzeitkomponente als Teil der Windows Desktop Experience installiert. Es wird empfohlen, Windows Desktop Experience vor der Installation von Lync Server 2013 zu installieren. Wenn diese Software von Lync Server 2013 nicht auf dem Server gefunden wird, werden Sie zur Installation aufgefordert und müssen den Server dann zum Abschließen neu starten.



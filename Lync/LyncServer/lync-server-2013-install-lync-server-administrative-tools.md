---
title: 'Lync Server 2013: Installieren von Lync Server-Verwaltungstools'
TOCTitle: Installieren von Lync Server-Verwaltungstools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398665(v=OCS.15)
ms:contentKeyID: 49294608
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren von Lync Server 2013-Verwaltungstools

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Im Rahmen dieses Themas wird die Installation der Verwaltungstools beschrieben, die Sie für die Bereitstellung und Verwaltung von Lync Server 2013 benötigen. Die Verwaltungstools werden standardmäßig auf jedem Server installiert, auf dem Lync Server 2013 ausgeführt wird. Darüber hinaus können Sie die Verwaltungstools auf anderen Computern installieren, wie etwa dedizierten Verwaltungskonsolen. Es wird dringend empfohlen, die Verwaltungstools auf einem Computer zu installieren, der sich in derselben Domäne oder Gesamtstruktur wie die Bereitstellung von Lync Server 2013, die Sie erstellen, befindet. So stellen Sie sicher, dass die vorbereitenden Schritte für die Active Directory-Domänendienste bereits abgeschlossen sind, sodass Sie die Verwaltungstools auf diesem Computer später zur Veröffentlichung Ihrer Topologie verwenden können.

Vor der Installation oder Verwendung der Verwaltungstools von Lync Server 2013 müssen Sie die Anforderungen bezüglich Infrastruktur, Betriebssystem, Software und Administratorrechten überprüfen. Ausführliche Informationen zu den Anforderungen der Infrastruktur finden Sie unter [Infrastrukturanforderungen für Verwaltungstools in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Details zu den Anforderungen bezüglich Betriebssystem und Software für die Installation der Verwaltungstools von Lync Server 2013 finden Sie unter [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Zusätzliche Softwareanforderungen für Lync Server 2013](lync-server-2013-additional-software-requirements.md) sowie unter [Zusätzliche Serverunterstützung und Anforderungen in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). Details zu den Benutzerrechten und Berechtigungen, die für die Installation und Verwendung der Tools erforderlich sind, finden Sie unter [Erforderliche Administratorrechte und Gruppenmitgliedschaften für die Installation und Verwaltung von Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).


> [!IMPORTANT]
> Wenn die Internetinformationsdienste (IIS) und alle Webdienste in Ihrer Organisation auf einem anderen Laufwerk als auf dem Systemlaufwerk platziert werden müssen, können Sie das Installationsverzeichnis für die Lync Server-Dateien im Setupdialogfeld ändern. Wenn Sie die Setupdateien, einschließlich "OCSCore.msi", in diesem Verzeichnis installieren, werden die übrigen Lync Server 2013-Dateien ebenfalls auf diesem Laufwerk bereitgestellt.



## So installieren Sie die Lync Server 2013-Verwaltungstools

1.  Melden Sie sich mindestens als lokaler Administrator auf dem Computer an, auf dem der Topologie-Generator und die Verwaltungstools installiert werden sollen. Wenn Sie als Standardbenutzer bei einem Windows Vista- oder Windows 7-Betriebssystem angemeldet sind und die Benutzerkontensteuerung aktiviert ist, werden Sie zur Eingabe von Name und Kennwort für den lokalen Administrator oder für ein gleichwertiges Domänenbenutzerkonto aufgefordert.

2.  Suchen Sie auf Ihrem Computer nach dem Datenträger für die Installation, und doppelklicken Sie auf dem Computer auf **\\Setup\\amd64\\Setup.exe** .

3.  Klicken Sie auf **Ja** , wenn Sie zur Installation von Microsoft Visual C++ 2008 Distributable aufgefordert werden.

4.  Klicken Sie auf der Seite **Microsoft Lync Server 2013Installationsspeicherort** auf **OK** . Ändern Sie diesen Pfad in einen anderen Speicherort oder ein anderes Laufwerk, wenn Sie die Dateien an einem anderen Speicherort installieren müssen.
    

    > [!IMPORTANT]
    > Wenn die Internetinformationsdienste (Internet Information Services, IIS) und alle Webdienste in Ihrer Organisation auf einem anderen Laufwerk als auf dem Systemlaufwerk platziert werden müssen, können Sie das Installationsverzeichnis für die Lync Server 2013-Dateien im Setupdialogfeld ändern. Wenn Sie die Setupdateien, einschließlich "OCSCore.msi", in diesem Verzeichnis installieren, werden die übrigen Lync Server 2013-Dateien ebenfalls auf diesem Laufwerk bereitgestellt.



5.  Lesen Sie die Lizenzbedingungen auf der Seite **Endbenutzer-Lizenzvertrag** , klicken Sie auf **Ich stimme zu** und anschließend auf **OK** . Dieser Schritt ist erforderlich, um fortfahren zu können.

6.  Klicken Sie im Bereitstellungs-Assistenten von **Microsoft Lync Server 2013** auf **Administratortools installieren** .

7.  Klicken Sie nach dem erfolgreichen Abschluss der Installation auf **Beenden** .

## Siehe auch

#### Aufgaben

[Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md)  

#### Konzepte

[Lync Server 2013-Verwaltungstools](lync-server-2013-lync-server-administrative-tools.md)


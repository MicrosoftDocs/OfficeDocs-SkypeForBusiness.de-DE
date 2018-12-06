---
title: 'Lync Server 2013: Systemanforderungen für Server mit Lync Server 2013'
TOCTitle: Systemanforderungen für Server mit Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398588(v=OCS.15)
ms:contentKeyID: 49294468
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Systemanforderungen für Server mit Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_


> [!NOTE]
> Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Serverhardwareplattformen für Lync Server&nbsp;2013</A>.



Für Standard Edition- und Enterprise Edition-Server gelten dieselben Softwareanforderungen.

Server mit Lync Server 2013 Enterprise Edition eignen sich als Hauptbereitstellung für große Organisationen. Enterprise Edition-Server sind auf ca. 80.000 verwaltete Benutzer pro Pool skalierbar. Server mit Lync Server 2013 Standard Edition sind für kleinere Organisationen und für Zweigniederlassungen bestimmt, die sich in geografischer Entfernung zur Hauptbereitstellung einer Organisation befinden. Ein Paar Standard Edition-Server kann bis zu 5.000 Benutzer unterstützen. Ausführliche Informationen zu den Unterschieden zwischen Servern mit Standard Edition und Enterprise Edition finden Sie im Abschnitt [Übersicht über die Bereitstellung für Lync Server 2013](lync-server-2013-deployment-overview.md).

## Betriebssysteminstallation


> [!IMPORTANT]
> Lync Server 2013 ist nur in einer 64-Bit-Version verfügbar, für die 64-Bit-Hardware und eine 64-Bit-Version des Windows Server-Betriebssystems erforderlich sind. In dieser Version ist keine 32-Bit-Version von Lync Server 2013 verfügbar.



Für Standard Edition- und Enterprise Edition-Server können die folgenden Betriebssysteme verwendet werden:

  - Windows Server 2008 R2 SP1 oder neuestes Service Pack

  - Windows Server 2012

  - Windows Server 2012 R2

Installieren Sie die Betriebssystemsoftware auf dem Front-End-Server des Standard Edition- oder Enterprise Edition-Servers. Wenden Sie alle Updates in der vorgesehenen Reihenfolge an, um das Betriebssystem auf den neuesten Stand zu bringen und die Organisationsstandards in Bezug auf Updates zu erfüllen. Ausführliche Informationen zu den Betriebssystemanforderungen finden Sie in der Unterstützungsdokumentation unter [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md).


> [!NOTE]
> Damit Lync Server 2013 unter Windows Server 2012 R2 funktionieren kann, müssen Sie ggf. den Wert eines Registrierungsschlüssels in Windows Server ändern. Diese Änderung ist ggf. notwendig, damit Zertifikate korrekt funktionieren und Clients sich bei Survivable Branch-Anwendungen registrieren können. Weitere Informationen finden Sie unter <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>.



## Zusätzliche Software für Lync Server 2013

Zusätzlich zu den erforderlichen Updates für das Betriebssystem werden für den Betrieb von Lync Server 2013 Betriebssystemrollen, Funktionen und weitere Software benötigt. Ausführliche Informationen zu zusätzlicher Software, die vor Veröffentlichung der Topologie und der Installation von Lync Server 2013 installiert werden muss, finden Sie unter [Zusätzliche Softwareanforderungen für Lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.

## Zusätzliche Softwareanforderungen für alle Serverrollen

Stellen Sie für alle Serverrollen sicher, dass die Windows PowerShell-Befehlszeilenschnittstelle 3.0 und Microsoft .NET Framework 4.5 installiert sind.

Darüber hinaus sind die Windows PowerShell-Befehlszeilenschnittstelle 3.0 und Microsoft .NET Framework 4.5 auf jedem Computer erforderlich, auf dem die Verwaltungstools von Lync Server ausgeführt werden.

## Windows PowerShell 3.0

Für Lync Server 2013 muss auf jedem Computer, der Teil der Lync Server-Topologie ist, Windows PowerShell 3.0 installiert sein. Detaillierte Informationen zur Installation von Windows PowerShell 3.0 finden Sie unter [Installieren von Windows PowerShell 3.0 für Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).


> [!NOTE]
> Unter Windows Server&nbsp;2008&nbsp;R2 mit SP1 kann die Windows PowerShell-Befehlszeilenschnittstelle 3.0 nicht vor der Installation von Microsoft .NET Framework 4.5 installiert werden.



## Microsoft .NET Framework 4.5

Wenn Sie Microsoft .NET Framework 4.5 auf Servern mit Lync Server 2013 unter Windows Server 2012 oder Windows Server 2012 R2 installieren, müssen Sie einen zusätzlichen Schritt ausführen. Nachdem .NET Framework 4.5 installiert ist, verwenden Sie Server-Manager zum Installieren der HTTP-Aktivierung.

**So installieren Sie .NET 4.5 HTTP-Aktivierung unter Windows Server 2012 oder Windows Server 2012 R2**

1.  Klicken Sie im Menü **Start** auf **Programme** , dann auf **Verwaltung** und anschließend auf **Server-Manager**.

2.  Wählen Sie im Server-Manager unter **Featureübersicht** die Option **Features hinzufügen** aus.

3.  Erweitern Sie die Option **.NET Framework 4.5**.

4.  Wählen Sie **WCF Activation** aus, wenn diese Option noch nicht ausgewählt wurde. Wählen Sie dann die Option **HTTP-Aktivierung** aus.

5.  Klicken Sie auf **Weiter** und befolgen Sie die Aufforderungen, um die Installation zu beenden.


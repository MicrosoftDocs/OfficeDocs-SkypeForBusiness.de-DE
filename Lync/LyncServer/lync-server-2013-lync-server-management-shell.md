---
title: Lync Server-Verwaltungsshell
TOCTitle: Lync Server-Verwaltungsshell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398474(v=OCS.15)
ms:contentKeyID: 49294249
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server-Verwaltungsshell

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In Microsoft Lync Server 2010 wurden gegenüber Microsoft Office Communications Server 2007 R2 zahlreiche neue und verbesserte Funktionen eingeführt. Dazu gehören auch die Verwaltungsmöglichkeiten für Ihre Implementation. So gibt es zum Beispiel eine neue Benutzeroberfläche (die Lync Server-Systemsteuerung), die eine erhebliche Verbesserung gegenüber der bisher verwendeten MMC (Microsoft Management Console) darstellt. Eine weitere wichtige Verbesserung im Hinblick auf die Verwaltung ist die Windows PowerShell.

Mit der Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile verwalten. Die Shell verfügt über eine Befehlszeilenumgebung, produktspezifische Befehle und eine komplette Skriptsprache. Die Windows PowerShell wurde 2006 als herunterladbare Version für Windows eingeführt, und in der Befehlszeilenschnittstelle zur Verwaltung von Microsoft Exchange Server 2007 integriert. Von da an ist sie weiter gewachsen und mittlerweile in den meisten Microsoft Server-Produkten (und ab nun auch inMicrosoft Lync Server 2013) enthalten. In Lync Server 2010 wurden fast 550 produktspezifische Cmdlets eingeführt, mit denen Sie jeden Aspekt Ihrer Bereitstellung verwalten können.

Die folgenden Abschnitte enthalten eine Liste der Cmdlets sowie Beschreibungen der Cmdlets. Diese Informationen stehen auch direkt über die Befehlszeile zur Verfügung. Geben Sie einfach den folgenden Befehl an der Eingabeaufforderung von Lync Server-Verwaltungsshell ein:

    Get-Help <cmdlet name> -Full

Wenn Sie beispielsweise Hilfeinformationen zum Cmdlet **New-CsVoicePolicy** von der Befehlszeile aus abrufen möchten, geben Sie folgenden Befehl ein:

    Get-Help New-CsVoicePolicy -Full

Wissenswertes über die Windows PowerShell in Lync Server 2013:

  - Öffnen Sie zum Ausführen der Lync Server-Cmdlets die Lync Server-Verwaltungsshell.
    

    > [!WARNING]
    > Wenn Sie anstelle der Lync Server-Verwaltungsshell ein Windows PowerShell-Fenster öffnen, können Sie in der Standardeinstellung keine Lync Server-Cmdlets ausführen. Geben Sie zum Ausführen der Lync Server-Cmdlets in der Windows PowerShell zunächst den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein:<BR>Import-Module Lync



  - Die Lync Server-Verwaltungsshell wird automatisch auf jedem Lync Server-Front-End-Server der Enterprise Edition und auf jedem Standard Edition-Server installiert.

  - Neue und aktualisierte Informationen, Beispielskripts und Hilfen für erste Schritte sowie weitere Informationen zu Windows PowerShell- und Microsoft Lync Server 2013-Cmdlets finden Sie im Lync Server Windows PowerShell-Blog [http://go.microsoft.com/fwlink/?linkid=203150\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x407).


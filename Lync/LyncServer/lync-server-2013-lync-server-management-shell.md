---
title: 'Lync Server 2013: lync Server-Verwaltungsshell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f367ec9ff3f990c410a95289c159bb021b053cec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 Management-Shell

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2017-09-20_

<div>


> [!NOTE]  
> Die Skype for Business-Cmdlet-Referenz wurde zu docs.Microsoft.com verschoben. Durch Klicken auf die unten aufgeführten Links gelangen Sie zur neuen docs.Microsoft.com-Seite. Der Inhalt ist nun Open sourced und für Community-Beiträge über GitHub verfügbar. Möchten Sie einen Beitrag leisten? Lesen Sie die Readme-Datei im Repo hier:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

In Microsoft lync Server 2010 wurde eine große Menge neuer und verbesserter Features im Vergleich zu den in Microsoft Office Communications Server 2007 R2 verfügbaren Funktionen eingeführt. Eine Verbesserung ist die Methode zur Verwaltung Ihrer Implementierung. Es gibt beispielsweise eine neue Benutzeroberfläche, die als lync Server-Systemsteuerung bezeichnet wird, die eine große Verschiebung von der Verwendung der meisten Personen mit der Microsoft Management Console darstellt. Die andere wesentliche Verbesserung der Verwaltbarkeit ist die Einbeziehung von Windows PowerShell.

Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile verwalten. Windows PowerShell umfasst eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Windows PowerShell wurde erst spät in 2006 als herunterladbare Version für das Windows-Betriebssystem eingeführt und als Befehlszeilenschnittstelle für die Verwaltbarkeit von Microsoft Exchange Server 2007 integriert. Von diesem Moment an wuchs es weiter an und wurde in die meisten Microsoft-Server Produkte integriert, wobei die neueste Microsoft lync Server 2013. Lync Server 2010 haben fast 550 produktspezifische Cmdlets eingeführt, mit denen Sie jeden Aspekt Ihrer Bereitstellung verwalten können.

Die folgenden Abschnitte enthalten eine Liste der Cmdlets sowie Beschreibungen der Cmdlets. Diese Informationen stehen auch direkt über die Befehlszeile zur Verfügung. Geben Sie einfach an der lync Server-Verwaltungsshell Eingabeaufforderung Folgendes ein:

    Get-Help <cmdlet name> -Full

Wenn Sie beispielsweise Hilfeinformationen zum Cmdlet **New-CsVoicePolicy** von der Befehlszeile aus abrufen möchten, geben Sie folgenden Befehl ein:

    Get-Help New-CsVoicePolicy -Full

Wissenswerte über Windows PowerShell in lync Server 2013:

  - Öffnen Sie zum Ausführen der lync Server-Cmdlets das lync Server-Verwaltungsshell.
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie ein Windows PowerShell Fenster anstatt des lync Server-Verwaltungsshells öffnen, können Sie die lync Server-Cmdlets standardmäßig nicht ausführen. Geben Sie an der Windows PowerShell-Eingabeaufforderung Folgendes ein, um die lync Server-Cmdlets in Windows PowerShell auszuführen:<BR>Import-Module Lync

    
    </div>

  - Lync Server-Verwaltungsshell wird automatisch auf allen lync Server Enterprise Edition-Front-End-Server oder-Standard Edition-Server installiert.

  - Auf der lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)finden Sie neue und aktualisierte Informationen, Beispielskripts und Hilfe zum Thema Windows PowerShell und Microsoft lync Server 2013-Cmdlets.

</div>

<span> </span>

</div>

</div>

</div>


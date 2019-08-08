---
title: Kombinieren von Skype for Business Online-Cmdlets mit anderen Windows PowerShell-Cmdlets in
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afcd352521285e619c9ceeb55a0699b4d4ea73e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Kombinieren von Skype for Business Online-Cmdlets mit anderen Windows PowerShell-Cmdlets in

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-05_

Wenn Sie mithilfe von Windows PowerShell eine Verbindung mit Skype for Business Online herstellen, stehen Ihnen ungefähr 40-Cmdlets für Skype for Business Online zur Verfügung. Bei der Verwaltung von Skype for Business Online beschränken Sie sich jedoch nicht auf die Verwendung dieser 40-Cmdlets. Zusätzlich zu den Skype for Business Online-Cmdlets können Sie auch alle anderen Windows PowerShell-Cmdlets verwenden, die auf Ihrem Computer installiert sind. (Wenn Sie Windows PowerShell 3,0 installieren, werden auch Hunderte von zentralen Windows PowerShell-Cmdlets installiert.) Ihre Befehle können die Skype for Business Online-Cmdlets und alle anderen auf dem Computer verfügbaren Cmdlets kombinieren und anpassen.

Obwohl ein vollständiger Kurs in Windows PowerShell 3,0 den Rahmen dieses Artikels sprengt, finden Sie hier einige Beispiele, die zeigen, warum Sie Cmdlets kombinieren und vergleichen können. Zunächst einmal enthält keines der Skype for Business Online-Cmdlets einen Befehl "Drucken", und in der Windows PowerShell-Konsole kann auch kein solcher Befehl gefunden werden. Wie erhalten Sie einen Ausdruck der Informationen, die von einem Cmdlet abgerufen werden? Eine Möglichkeit besteht darin, die Informationen abzurufen und diese Informationen dann an das **Out-Printer-** Cmdlet zu senden:

    Get-CsTenant | Out-Printer

Da keine zusätzlichen Parameter enthalten sind, werden alle vom **Out-Printer-** Cmdlet zurückgegebenen Informationen auf dem Standarddrucker gedruckt.

Ebenso enthalten keine der Skype for Business Online-Cmdlets einen Parameter, mit dem Sie Daten in einer Datei speichern können. Aber das ist OK: Dieser Befehl verwendet das **Out-File-** Cmdlet, um die zurückgegebenen Informationen in der Textdatei\\C\\: Logs Tenants. txt zu speichern:

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

Und dieser Befehl verwendet das Cmdlet **"Select-Object"** , um die Daten zu begrenzen, die zurückgegeben und auf dem Bildschirm angezeigt werden. In diesem Beispiel ruft das Cmdlet " [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) " Informationen zu allen Skype for Business Online-Benutzern ab, und dann wird das Cmdlet **"Select-Object"** verwendet, um die angezeigten Daten auf den Identitätswert und die Archivierungsrichtlinie des Benutzers zu begrenzen:

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

Da es Hunderte von Cmdlets gibt, die auf Ihrem Computer verwendet werden können, haben Sie möglicherweise Schwierigkeiten, zu ermitteln, welche Cmdlets für Skype for Business Online-Cmdlets gelten und welche nicht. Wenn Sie eine Liste der Skype for Business Online-Cmdlets (und nur der Skype for Business Online-Cmdlets) zurückgeben möchten, müssen Sie zuerst den Namen des temporären Windows PowerShell-Moduls ermitteln, das alle Skype for Business Online-Cmdlets enthält. Führen Sie dazu diesen Befehl in der Windows PowerShell-Eingabeaufforderung aus:

    Get-Module

Auf dem Bildschirm werden Informationen ähnlich der folgenden angezeigt:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

Das Modul mit dem modultype-Skript ist das Modul, das die Skype for Business Online-Cmdlets enthält. Wenn Sie eine Liste dieser Cmdlets zurückgeben möchten, führen Sie das Cmdlet " **Get-Command"** aus, indem Sie den Namen des Skriptmoduls als Modulnamen verwenden:

    Get-Command -Module tmp_5astd3uh.m5v

Es ist möglich, dass Sie mehrere Module mit einem modultype gleich Skript haben könnten. In diesem Fall können Sie den folgenden Befehl ausführen, um herauszufinden, welches Modul das Cmdlet " **Get-CsTenant** " enthält:

    Get-Command Get-CsTenant

Das Modul, das für das Cmdlet " **Get-CsTenant** " zurückgegeben wird, ist das Modul, das alle Skype for Business Online-Cmdlets enthält:

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>Siehe auch


[Einführung in Windows PowerShell und Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


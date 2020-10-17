---
title: Kombinieren von Skype for Business Online-Cmdlets mit anderen Windows PowerShell-Cmdlets in
description: Kombinieren von Skype for Business Online-Cmdlets mit anderen Windows PowerShell-Cmdlets in.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd18f60891d48a54eb2f77f189ea8417e0b5e93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548001"
---
# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Kombinieren von Skype for Business Online-Cmdlets mit anderen Windows PowerShell-Cmdlets in

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-05_

Wenn Sie über Windows PowerShell eine Verbindung mit Skype for Business Online herstellen, stehen Ihnen ungefähr 40 Skype for Business Online-Cmdlets zur Verfügung. Sie sind jedoch nicht auf die Verwendung von nur den 40-Cmdlets beim Verwalten von Skype for Business Online beschränkte. Zusätzlich zu den Skype for Business Online-Cmdlets können Sie auch alle anderen Windows PowerShell-Cmdlets verwenden, die auf Ihrem Computer installiert sind. (Bei der Installation von Windows PowerShell 3,0 werden auch Hunderte von Kern Windows PowerShell-Cmdlets installiert.) Ihre Befehle können Skype for Business Online-Cmdlets und anderen auf Ihrem Computer verfügbaren Cmdlets mischen und abgleichen.

Obwohl ein vollständiger Kurs in Windows PowerShell 3,0 über den Rahmen dieses Artikels hinausgeht, finden Sie hier einige Beispiele, die zeigen, warum Sie Cmdlets möglicherweise kombinieren und anpassen möchten. Zunächst enthält keines der Skype for Business Online-Cmdlets einen Print-Befehl, und in der Windows PowerShell Konsole ist auch kein solcher Befehl zu finden. Wie erhalten Sie also einen Ausdruck der von einem Cmdlet abgerufenen Informationen? Eine Möglichkeit besteht darin, die Informationen abzurufen und diese Informationen dann an das **Out-Printer-** Cmdlet zu senden:

    Get-CsTenant | Out-Printer

Da keine zusätzlichen Parameter enthalten sind, werden alle vom **Out-Printer-** Cmdlet zurückgegebenen Informationen auf den Standarddrucker gedruckt.

Ebenso enthält keines der Skype for Business Online-Cmdlets einen Parameter, mit dem Sie Daten in einer Datei speichern können. Aber das ist in Ordnung: Dieser Befehl verwendet das **Out-File-** Cmdlet, um die zurückgegebenen Informationen in der Textdatei C: \\ LogsTenants.txt zu speichern \\ :

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

Und dieser Befehl verwendet das Cmdlet **Select-Object** , um die zurückgegebenen und auf dem Bildschirm angezeigten Daten zu begrenzen. In diesem Beispiel ruft das Cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) Informationen für alle Skype for Business Online Benutzer ab, und dann wird das Cmdlet **Select-Object** verwendet, um die angezeigten Daten auf den Identitätswert des Benutzers und die dazugehörige Archivierungsrichtlinie zu begrenzen:

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

Da Hunderte von Cmdlets für die Verwendung auf Ihrem Computer verfügbar sein werden, haben Sie möglicherweise Schwierigkeiten festzustellen, welche Cmdlets Skype for Business Online-Cmdlets sind und welche nicht. Um eine Liste der Skype for Business Online-Cmdlets (und nur Skype for Business Online-Cmdlets) zurückzugeben, müssen Sie zuerst den Namen des temporären Windows PowerShell-Moduls ermitteln, das alle Skype for Business Online-Cmdlets enthält. Führen Sie dazu in der Windows PowerShell-Eingabeaufforderung folgenden Befehl aus:

    Get-Module

Ähnliche Informationen wie die folgenden werden auf dem Bildschirm angezeigt:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

Das Modul mit dem modultype-Skript ist das Modul, das die Skype for Business Online-Cmdlets enthält. Führen Sie das Cmdlet **Get-Command** aus, um eine Liste dieser Cmdlets zurückzugeben, und verwenden Sie dabei den Namen des Skriptmoduls als Modulnamen:

    Get-Command -Module tmp_5astd3uh.m5v

Möglicherweise verfügen Sie über mehrere Module mit einem ModuleType-Wert, der dem Skript entspricht. In diesem Fall können Sie den folgenden Befehl ausführen, um herauszufinden, welches Modul das **Get-CsTenant-** Cmdlet enthält:

    Get-Command Get-CsTenant

Das Modul, das für das Cmdlet **Get-CsTenant** zurückgegeben wird, ist das Modul, das alle Skype for Business Online-Cmdlets enthält:

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>Siehe auch


[Eine Einführung in Windows PowerShell und Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


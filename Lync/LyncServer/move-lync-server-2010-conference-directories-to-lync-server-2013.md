---
title: Wechseln lync Server 2010 Konferenzverzeichnisse in lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 049472022a26d7a3a6e8e78e20a20ccaa46ff5fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Verschieben von Konferenzverzeichnissen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-28_

Vor der Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis in Ihrem lync Server 2010 Pool ausführen.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>So migrieren Sie ein Konferenzverzeichnis in lync Server 2013

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Um die Identität der Konferenzverzeichnisse in Ihrer Organisation zu erhalten, führen Sie den folgenden Befehl aus:
    
        Get-CsConferenceDirectory
    
    Der obige Befehl gibt alle Konferenzverzeichnisse in Ihrer Organisation zurück. Aus diesem Grund möchten Sie möglicherweise die Ergebnisse auf den Pool beschränken, der außer Betrieb genommen wird. Wenn Sie beispielsweise den Pool mit dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) pool01.contoso.net, verwenden Sie diesen Befehl, um die zurückgegebenen Daten auf Konferenzverzeichnisse aus diesem Pool zu begrenzen:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Dieser Befehl gibt nur die Konferenzverzeichnisse zurück, in denen die Service-Eigenschaft den FQDN pool01.contoso.NET enthält.

3.  Um Konferenzverzeichnisse zu migrieren, führen Sie den folgenden Befehl für jedes Konferenzverzeichnis im Pool aus:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Um beispielsweise das Konferenzverzeichnis 3 zu migrieren, verwenden Sie diesen Befehl, indem Sie einen lync Server 2013 Pool als TargetPool angeben:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    Wenn Sie alle Konferenzverzeichnisse in einem Pool verlagern möchten, verwenden Sie einen Befehl wie den folgenden:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Ausführliche schrittweise Anleitungen zur Außerbetriebnahme von lync 2010-Pools finden Sie im Dokument "Deinstallieren von Microsoft lync Server 2010 und entfernen [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)von Server Rollen" (aus dem heruntergeladen werden kann).

Beim Verschieben von Konferenz Verzeichnissen kann der folgende Fehler auftreten:

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

Dieser Fehler tritt normalerweise auf, wenn der lync Server-Verwaltungsshell eine aktualisierte Gruppe von Active Directory Berechtigungen erfordert, um eine Aufgabe abzuschließen. Um das Problem zu beheben, schließen Sie die aktuelle Instanz der Verwaltungsshell, öffnen Sie dann eine neue Instanz der Shell, und führen Sie den Befehl erneut aus, um das Konferenzverzeichnis zu verlagern.

</div>

</div>

<span> </span>

</div>

</div>

</div>


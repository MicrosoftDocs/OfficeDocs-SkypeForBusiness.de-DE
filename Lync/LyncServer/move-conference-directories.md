---
title: Migrieren von Konferenz Verzeichnissen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2de2b588d880600a4a7d8365f20423d3faf2653e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Migrieren von Konferenz Verzeichnissen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-04_

Vor dem Außerbetriebnahme eines Pools müssen Sie das folgende Verfahren für jedes Konferenzverzeichnis in Ihrem Office Communications Server 2007 R2 Pool ausführen.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>So migrieren Sie ein Konferenzverzeichnis in lync Server 2013

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Führen Sie die folgenden Befehle aus, um die Identität der Konferenzverzeichnisse in Ihrer Organisation zu beziehen:
    
        Get-CsConferenceDirectory
    
    Dieses Cmdlet gibt alle Konferenzverzeichnisse in der Organisation zurück. Deshalb empfiehlt es sich u. U., die Ergebnisse auf den Pool zu beschränken, den Sie außer Betrieb nehmen möchten. Beispiel: Sie möchten einen Pool mit dem vollqualifizierten Domänennamen (FQDN) pool01.contoso.net außer Betrieb nehmen:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Dieses Cmdlet gibt alle Konferenzverzeichnisse zurück, deren Dienst-ID den FQDN pool01.contoso.net enthält.

3.  Führen Sie zum Verschieben von Konferenzverzeichnissen folgenden Befehl für jedes Konferenzverzeichnis in dem Pool aus:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Beispiel:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> Möglicherweise tritt ein unten dargestellter Fehler auf, der durch die lync Server-Verwaltungsshell, die eine aktualisierte Gruppe von Berechtigungen aus Active Directory erfordern, verursacht wird. Schließen Sie zum Beheben des Fehlers das aktuelle Fenster, und öffnen Sie ein neues lync Server-Verwaltungsshell, und führen Sie den Befehl erneut aus.



</div>

![CsConferenceDirectory-Fehlerausgabe](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "CsConferenceDirectory-Fehlerausgabe")

</div>

</div>

<span> </span>

</div>

</div>

</div>


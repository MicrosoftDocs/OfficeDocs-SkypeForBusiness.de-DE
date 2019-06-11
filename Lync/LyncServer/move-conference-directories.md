---
title: Verschieben von Konferenz Verzeichnissen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba7480e3454d338d9d6f2ff521c09e26b4f17c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Verschieben von Konferenz Verzeichnissen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Bevor Sie einen Pool außer Betrieb nehmen, müssen Sie für jedes Konferenzverzeichnis in Ihrem Office Communications Server 2007 R2-Pool die folgenden Schritte ausführen.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>So verschieben Sie ein Konferenzverzeichnis in lync Server 2013

1.  Öffnen Sie die lync Server-Verwaltungsshell.

2.  Führen Sie die folgenden Befehle aus, um die Identität der Konferenzverzeichnisse in Ihrer Organisation zu ermitteln:
    
        Get-CsConferenceDirectory
    
    Da dieses Cmdlet alle Konferenzverzeichnisse in Ihrer Organisation zurückgibt, möchten Sie möglicherweise die Ergebnisse auf den Pool beschränken, den Sie außer Betrieb nehmen möchten. Wenn Sie beispielsweise einen Pool mit dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) pool01.contoso.net:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Dieses Cmdlet gibt alle Konferenzverzeichnisse zurück, in denen die Dienst-ID den FQDN-pool01.contoso.NET enthält.

3.  Führen Sie für jedes Konferenzverzeichnis im Pool die folgenden Schritte aus, um Konferenzverzeichnisse zu verschieben:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Beispiel:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> Möglicherweise tritt ein Fehler auf, der nachfolgend gezeigt wird, der von der lync Server-Verwaltungsshell verursacht wird, die einen aktualisierten Satz von Berechtigungen aus Active Directory erfordert. Wenn Sie den Fehler beheben möchten, schließen Sie das aktuelle Fenster, öffnen Sie eine neue lync Server-Verwaltungsshell, und führen Sie den Befehl erneut aus.



</div>

![Move-CsConferenceDirectory-Fehlerausgabe] (images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory-Fehlerausgabe")

</div>

</div>

<span> </span>

</div>

</div>

</div>


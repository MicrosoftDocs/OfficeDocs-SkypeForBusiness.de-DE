---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Hot deskings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42da4f35c78e182ac988b1185bf797e3cb88ddd5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Aktivieren oder Deaktivieren des Hot deskings in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-20_

Sie können Telefone für gemeinsame Bereiche als Telefon *Apparate*einrichten. Bei Hot-Desk-Telefonen können sich Benutzer bei Ihrem eigenen Benutzerkonto anmelden und nach der Anmeldung lync Server Funktionen und ihre eigenen Benutzerprofileinstellungen verwenden. Das Hot Desking wird mithilfe von Clientrichtlinien verwaltet: zum Aktivieren oder Deaktivieren des Hot deskings müssen Sie die Clientrichtlinien ändern, die von ihren Telefonen in öffentlichen Bereichen verwendet werden. Ausführliche Informationen zum Bestimmen der Konferenzrichtlinien, die ihren Telefonen für gemeinsame Bereiche zugewiesen wurden, finden Sie unter [Anzeigen von Telefon Informationen zu öffentlichen Bereichen in lync Server 2013](lync-server-2013-view-common-area-phone-information.md).

Verwenden Sie den EnableHotdesking-Parameter des **New-CSClientPolicy-** Cmdlets oder das Cmdlet " **setCSClientPolicy** ", um das Hot Desking auf einem Telefon wie folgt zu aktivieren oder zu deaktivieren. Führen Sie diese Cmdlets entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell aus. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>


<div>

## <a name="enabling-hot-desking"></a>Aktivieren von Hot Desking

  - Um das Hot Desking für ein Telefon im öffentlichen Bereich zu aktivieren, müssen Sie die Clientrichtlinie ändern, die diesem Telefon (oder einer Sammlung von Telefonen) zugewiesen wurde.
    
    Nachdem Sie die Richtlinie identifiziert haben, die geändert werden muss, müssen Sie im nächsten Schritt das Cmdlet "CsClientPolicy" verwenden, um den EnableHotdesking **-** Parameter auf "true" festzulegen. Beispiel:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - Alternativ können Sie das Cmdlet **New-CsClientPolicy** verwenden, um eine neue Clientrichtlinie zu erstellen, die das Hot Desking ermöglicht. Beispiel:
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> Nachdem diese Richtlinie erstellt wurde, müssen Sie Sie den entsprechenden Telefonen im öffentlichen Bereich zuweisen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Zuweisen von Richtlinien in lync Server 2013 zu einem Telefon im öffentlichen Bereich</A>.



</div>

<div>

## <a name="disabling-hot-desking"></a>Deaktivieren von Hot Desking

  - Wenn Sie das Hot Desking für ein Telefon in einem öffentlichen Bereich deaktivieren möchten, setzen Sie den Parameter EnableHotdesking des Cmdlets **setCsClientPolicy** auf den Standardwert false zurück. Beispiel:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

Ausführliche Informationen finden Sie in den Hilfethemen für das [New-CsClientPolicy-](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet und das Cmdlet "Set [-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>


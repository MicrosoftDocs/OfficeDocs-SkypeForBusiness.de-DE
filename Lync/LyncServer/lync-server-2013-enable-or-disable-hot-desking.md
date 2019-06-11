---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren von Hot Desking'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5d9f2d168a06b5624375dcd005da58b4d3d5fd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Aktivieren oder Deaktivieren von Hot Desking in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Sie können Telefone im öffentlichen Bereich als *Hot-Desk-Telefone*einrichten. Mit Hot-Desk-Telefonen können sich Benutzer bei Ihrem eigenen Benutzerkonto anmelden und nach der Anmeldung die lync Server-Features und ihre eigenen Benutzerprofileinstellungen verwenden. Hot-Desking wird mithilfe von Clientrichtlinien verwaltet: zum Aktivieren oder Deaktivieren der Hot-Desk-Funktion müssen Sie die Clientrichtlinien ändern, die von ihren Telefonen im öffentlichen Bereich verwendet werden. Details zum Ermitteln der Konferenzrichtlinien, die ihren Telefonen im öffentlichen Bereich zugewiesen wurden, finden Sie unter [Anzeigen von allgemeinen Telefon Informationen in lync Server 2013](lync-server-2013-view-common-area-phone-information.md).

Sie verwenden den EnableHotdesking-Parameter des Cmdlets **New-CSClientPolicy** oder das Cmdlet " **Satz-CSClientPolicy** ", um die Hot-Desk-Funktion auf einem Smartphone wie folgt zu aktivieren oder zu deaktivieren. Führen Sie diese Cmdlets entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell aus. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>


<div>

## <a name="enabling-hot-desking"></a>Aktivieren von Hot-Desking

  - Wenn Sie die Hot-Desk-Funktion für ein Telefon im öffentlichen Bereich aktivieren möchten, müssen Sie die Clientrichtlinie ändern, die diesem Telefon (oder einer Sammlung von Telefonen) zugewiesen wurde.
    
    Nachdem Sie die zu ändernde Richtlinie identifiziert haben, besteht der nächste Schritt darin, das Cmdlet "setCsClientPolicy" zu verwenden, um den EnableHotdesking **-** Parameter auf "true" festzulegen. Beispiel:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - Alternativ können Sie das Cmdlet **New-CsClientPolicy** verwenden, um eine neue Clientrichtlinie zu erstellen, die eine Hot-Desk-Funktion ermöglicht. Beispiel:
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> Nachdem diese Richtlinie erstellt wurde, müssen Sie Sie den entsprechenden Telefonen im öffentlichen Bereich zuweisen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Zuweisen von Richtlinien in lync Server 2013 zu einem gemeinsamen Bereichs Telefon</A>.



</div>

<div>

## <a name="disabling-hot-desking"></a>Deaktivieren des Hot-Desking

  - Um die Hot-Desk-Funktion für ein Telefon im öffentlichen Bereich zu deaktivieren, setzen Sie den EnableHotdesking-Parameter des Cmdlets " **CsClientPolicy** " auf den Standardwert false zurück. Beispiel:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) und dem Cmdlet " [Satz-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>


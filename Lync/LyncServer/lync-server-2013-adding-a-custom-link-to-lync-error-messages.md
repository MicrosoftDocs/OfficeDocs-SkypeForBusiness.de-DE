---
title: 'Lync Server 2013: Hinzufügen eines benutzerdefinierten Links zu Lync-Fehlermeldungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f62dd7841f77a519653a658131423a89f77ed012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Hinzufügen eines benutzerdefinierten Links zu Lync-Fehlermeldungen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Passen Sie lync 2013-Fehlermeldungen an, indem Sie einen Link zu ihren eigenen Problem Behandlungs-oder Helpdesk-Informationen hinzufügen. Verwenden Sie dazu die Cmdlets " **New-CSClientPolicy** " oder " **CSClientPolicy** " der lync Server-Verwaltungsshell mit dem CustomLinkInErrorMessages-Parameter. Der Text des benutzerdefinierten Links lautet "klicken Sie hier, um Supportthemen von Ihrem Administrator zu erhalten" und kann nicht angepasst werden.

Der folgende Befehl bewirkt beispielsweise, dass der benutzerdefinierte Link im Fußnotenbereich jeder lync 2013-Fehlermeldung angezeigt wird, und legt das Verknüpfungsziel aufhttp://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

Verwenden Sie **Grant-CSClientPolicy** , um diese neue Richtlinie Benutzern zuzuweisen. Ausführliche Informationen finden Sie unter **New-CSClientPolicy** und **Grant-CSClientPolicy** in der Dokumentation zur lync Server-Verwaltungsshell.

</div>

<span> </span>

</div>

</div>

</div>


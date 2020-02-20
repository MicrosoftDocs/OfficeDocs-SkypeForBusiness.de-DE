---
title: 'Lync Server 2013: Hinzufügen eines benutzerdefinierten Links zu lync-Fehlermeldungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c02534c76a26313818e9ed4af8c51c31621bbd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Hinzufügen eines benutzerdefinierten Links zu lync-Fehlermeldungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-20_

Passen Sie lync 2013 Fehlermeldungen an, indem Sie einen Link zu ihren eigenen Problem Behandlungs-oder Helpdesk-Informationen hinzufügen. Verwenden Sie dazu die Cmdlets **New-CSClientPolicy** oder **CSClientPolicy** lync Server-Verwaltungsshell mit dem Parameter CustomLinkInErrorMessages. Der Text des benutzerdefinierten Links lautet "klicken Sie hier, um Supportthemen von Ihrem Administrator" zu erhalten, und er kann nicht angepasst werden.

Der folgende Befehl bewirkt beispielsweise, dass der benutzerdefinierte Link im Fußnotenbereich jeder lync 2013 Fehlermeldung angezeigt wird, und legt den Link Ziel aufhttp://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

Verwenden Sie **Grant-CSClientPolicy** , um diese neue Richtlinie Benutzern zuzuweisen. Ausführliche Informationen finden Sie unter **New-CSClientPolicy** und **Grant-CSClientPolicy** in der lync Server-Verwaltungsshell Dokumentation.

</div>

<span> </span>

</div>

</div>

</div>


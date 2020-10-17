---
title: 'Lync Server 2013: Hinzufügen eines benutzerdefinierten Links zu lync-Fehlermeldungen'
description: 'Lync Server 2013: Hinzufügen eines benutzerdefinierten Links zu lync-Fehlermeldungen.'
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
ms.openlocfilehash: a5d333b6f27e10e5092de23fcdf1d37fd75e75a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560031"
---
# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="fdb57-103">Hinzufügen eines benutzerdefinierten Links zu lync-Fehlermeldungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdb57-103">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdb57-104">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="fdb57-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="fdb57-105">Passen Sie lync 2013 Fehlermeldungen an, indem Sie einen Link zu ihren eigenen Problem Behandlungs-oder Helpdesk-Informationen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fdb57-105">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="fdb57-106">Verwenden Sie dazu die Cmdlets **New-CSClientPolicy** oder **CSClientPolicy**   lync Server-Verwaltungsshell mit dem Parameter CustomLinkInErrorMessages.</span><span class="sxs-lookup"><span data-stu-id="fdb57-106">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="fdb57-107">Der Text des benutzerdefinierten Links lautet "klicken Sie hier, um Supportthemen von Ihrem Administrator" zu erhalten, und er kann nicht angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="fdb57-107">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="fdb57-108">Der folgende Befehl bewirkt beispielsweise, dass der benutzerdefinierte Link im Fußnotenbereich jeder lync 2013 Fehlermeldung angezeigt wird, und legt den Link Ziel auf http://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="fdb57-108">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="fdb57-109">Verwenden Sie **Grant-CSClientPolicy** , um diese neue Richtlinie Benutzern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="fdb57-109">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="fdb57-110">Ausführliche Informationen finden Sie unter **New-CSClientPolicy** und **Grant-CSClientPolicy** in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="fdb57-110">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


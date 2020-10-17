---
title: 'Lync Server 2013: Cmdlets für beständigen Chat Server'
description: 'Lync Server 2013: Cmdlets für beständigen Chat Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server cmdlets
ms:assetid: 5aa59edb-db57-406f-9fbd-54bf1a55d31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204920(v=OCS.15)
ms:contentKeyID: 48184226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28016031ffd4efdc568999ec0a400d77bf628ba8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545171"
---
# <a name="persistent-chat-server-cmdlets-in-lync-server-2013"></a>Cmdlets für beständigen Chat Server in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-27_

Mit den Cmdlets für beständigen Chat können Sie den beständiger Chat von Microsoft lync Server 2013 Dienst (früher als Gruppen Chat Dienst bezeichnet) verwalten und konfigurieren. Mit dem beständigen Chat können Benutzer an Online Chatsitzungen teilnehmen. Obwohl diese Sitzungen in Echtzeit erfolgen können, ist der Inhalt jeder Sitzung persistent; Das bedeutet, dass diese Unterhaltungen jederzeit von jedermann fortgesetzt werden können.

<div>

## <a name="persistent-chat-cmdlets"></a>Persistent Chat-Cmdlets

Mit den Cmdlets für beständigen Chat können Sie den lync Server-Dienst für beständigen Chat verwalten und konfigurieren.

**Persistent Chat-Cmdlets**

  - [Get-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))

<!-- end list -->

  - [Gruppe-CsPersistentChatActiveServer](https://technet.microsoft.com/library/JJ205065(v=OCS.15))

<!-- end list -->

  - [Get-cspersistentchataddin "](https://technet.microsoft.com/library/JJ204670(v=OCS.15))

  - [New-cspersistentchataddin "](https://technet.microsoft.com/library/JJ204641(v=OCS.15))

  - [Remove-cspersistentchataddin "](https://technet.microsoft.com/library/JJ205350(v=OCS.15))

  - [Gruppe-cspersistentchataddin "](https://technet.microsoft.com/library/JJ204721(v=OCS.15))

<!-- end list -->

  - [Get-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))

  - [New-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))

  - [Remove-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))

  - [Gruppe-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))

<!-- end list -->

  - [Get-cspersistentchatcomplianceconfiguration "](https://technet.microsoft.com/library/JJ204625(v=OCS.15))

  - [New-cspersistentchatcomplianceconfiguration "](https://technet.microsoft.com/library/JJ205163(v=OCS.15))

  - [Remove-cspersistentchatcomplianceconfiguration "](https://technet.microsoft.com/library/JJ204767(v=OCS.15))

  - [Gruppe-cspersistentchatcomplianceconfiguration "](https://technet.microsoft.com/library/JJ204949(v=OCS.15))

<!-- end list -->

  - [Get-cspersistentchatconfiguration "](https://technet.microsoft.com/library/JJ205140(v=OCS.15))

  - [New-cspersistentchatconfiguration "](https://technet.microsoft.com/library/JJ205330(v=OCS.15))

  - [Remove-cspersistentchatconfiguration "](https://technet.microsoft.com/library/JJ204927(v=OCS.15))

  - [Gruppe-cspersistentchatconfiguration "](https://technet.microsoft.com/library/JJ205122(v=OCS.15))

<!-- end list -->

  - [Export-CsPersistentChatData](https://technet.microsoft.com/library/JJ205378(v=OCS.15))

  - [Import-CsPersistentChatData](https://technet.microsoft.com/library/JJ204709(v=OCS.15))

<!-- end list -->

  - [Get-cspersistentchateligibleprincipal "](https://technet.microsoft.com/library/JJ204891(v=OCS.15))

<!-- end list -->

  - [Get-cspersistentchatendpoint "](https://technet.microsoft.com/library/JJ204764(v=OCS.15))

  - [New-cspersistentchatendpoint "](https://technet.microsoft.com/library/JJ204811(v=OCS.15))

  - [Remove-cspersistentchatendpoint "](https://technet.microsoft.com/library/JJ204626(v=OCS.15))

<!-- end list -->

  - [Remove-cspersistentchatmessage "](https://technet.microsoft.com/library/JJ204668(v=OCS.15))

  - [Test-cspersistentchatmessage "](https://technet.microsoft.com/library/JJ204656(v=OCS.15))

<!-- end list -->

  - [Get-cspersistentchatpolicy "](https://technet.microsoft.com/library/JJ204673(v=OCS.15))

  - [Grant-cspersistentchatpolicy "](https://technet.microsoft.com/library/JJ204907(v=OCS.15))

  - [New-cspersistentchatpolicy "](https://technet.microsoft.com/library/JJ205396(v=OCS.15))

  - [Remove-cspersistentchatpolicy "](https://technet.microsoft.com/library/JJ205301(v=OCS.15))

  - [Gruppe-cspersistentchatpolicy "](https://technet.microsoft.com/library/JJ205192(v=OCS.15))

<!-- end list -->

  - [Clear-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))

  - [Get-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))

  - [New-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))

  - [Remove-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))

  - [Gruppe-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))

<!-- end list -->

  - [Get-cspersistentchatstate "](https://technet.microsoft.com/library/JJ204915(v=OCS.15))

  - [Gruppe-cspersistentchatstate "](https://technet.microsoft.com/library/JJ205109(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Hinzufügen von benutzerdefiniertem Text zu Chatnachrichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0681df9803615fee04c20e52258120bd6616e57d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>Hinzufügen von benutzerdefiniertem Text zu Chatnachrichten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-20_

Hinzufügen eines Haftungsausschlusses oder einer Warnung an den Anfang jeder lync 2013 Sofortnachrichtenunterhaltung (Chat) mithilfe der Cmdlets **New-CSClientPolicy** oder **CSClientPolicy** lync Server-Verwaltungsshell mit dem Parameter imwarning.

Mit dem Befehl im folgenden Beispiel wird eine Sicherheits Erinnerung oben im Unterhaltungsfenster hinzugefügt, wenn eine neue Sofortnachrichtenunterhaltung beginnt:

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

Verwenden Sie **Grant-CSClientPolicy** , um diese neue Richtlinie Benutzern zuzuweisen. Ausführliche Informationen finden Sie unter **New-CSClientPolicy** und **Grant-CSClientPolicy** in der lync Server-Verwaltungsshell Dokumentation.

</div>

<span> </span>

</div>

</div>

</div>


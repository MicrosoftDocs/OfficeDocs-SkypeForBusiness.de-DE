---
title: 'Lync Server 2013: Hinzufügen von benutzerdefiniertem Text zu Chatnachrichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb6746ea5897d779a202bc428b6c7259a1191f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>Hinzufügen von benutzerdefiniertem Text zu Chatnachrichten in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Fügen Sie am Anfang jeder lync 2013-Sofortnachrichtenunterhaltung (im) mithilfe der Cmdlets " **New-CSClientPolicy** " oder " **CSClientPolicy** " der lync Server-Verwaltungsshell mit dem Parameter "unwarning" eine Verzichtserklärung oder eine Warnung hinzu.

Mit dem Befehl im folgenden Beispiel wird eine Sicherheits Erinnerung am Anfang des Unterhaltungsfensters hinzugefügt, wenn eine neue Chat Unterhaltung beginnt:

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

Verwenden Sie **Grant-CSClientPolicy** , um diese neue Richtlinie Benutzern zuzuweisen. Ausführliche Informationen finden Sie unter **New-CSClientPolicy** und **Grant-CSClientPolicy** in der Dokumentation zur lync Server-Verwaltungsshell.

</div>

<span> </span>

</div>

</div>

</div>


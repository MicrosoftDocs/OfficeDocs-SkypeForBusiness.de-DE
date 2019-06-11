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

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="a6976-102">Hinzufügen von benutzerdefiniertem Text zu Chatnachrichten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6976-102">Adding custom text to instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6976-103">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="a6976-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a6976-104">Fügen Sie am Anfang jeder lync 2013-Sofortnachrichtenunterhaltung (im) mithilfe der Cmdlets " **New-CSClientPolicy** " oder " **CSClientPolicy** " der lync Server-Verwaltungsshell mit dem Parameter "unwarning" eine Verzichtserklärung oder eine Warnung hinzu.</span><span class="sxs-lookup"><span data-stu-id="a6976-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="a6976-105">Mit dem Befehl im folgenden Beispiel wird eine Sicherheits Erinnerung am Anfang des Unterhaltungsfensters hinzugefügt, wenn eine neue Chat Unterhaltung beginnt:</span><span class="sxs-lookup"><span data-stu-id="a6976-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="a6976-106">Verwenden Sie **Grant-CSClientPolicy** , um diese neue Richtlinie Benutzern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="a6976-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="a6976-107">Ausführliche Informationen finden Sie unter **New-CSClientPolicy** und **Grant-CSClientPolicy** in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="a6976-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: neues Voicemail-Feature'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New voice mail feature
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49733715
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aaeb0aff851064e1e257194cc4d5a67b8eaabfbe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522262"
---
# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="017ad-102">Neues Voicemail-Feature in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="017ad-102">New voice mail feature in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="017ad-103">_**Letztes Änderungsstand des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="017ad-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="017ad-104">Lync Server 2013 bietet eine Einführung in die Voicemail-escapefunktion, eine Erweiterung für die Verwaltung von Voicemail.</span><span class="sxs-lookup"><span data-stu-id="017ad-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="017ad-105">Mit dieser neuen Funktion kann ermittelt werden, wenn ein Anruf an Voicemail weitergeleitet wurde, und es wird verhindert, dass der Anruf sofort an die Mobiltelefon-Voicemail des Besitzers weitergeleitet wird, ohne dass der Benutzer die Möglichkeit hat, den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="017ad-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="017ad-106">Dieses Szenario tritt ein, wenn der Benutzer das gleichzeitige Klingeln auf dem Mobiltelefon aktiviert und das Mobiltelefon abgeschaltet ist, das Mobiltelefon entladen ist oder keinen Empfang hat.</span><span class="sxs-lookup"><span data-stu-id="017ad-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="017ad-107">Voicemail Escape erkennt, dass der Anruf sofort von der Mobiltelefon-Voicemail des Benutzers beantwortet wurde und unterbricht den Anruf mit der Mobiltelefon-Voicemail.</span><span class="sxs-lookup"><span data-stu-id="017ad-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="017ad-108">Der Anruf klingelt auf anderen Endpunkten vom Benutzer weiter, womit der Benutzer die Möglichkeit hat, den Anruf entgegenzunehmen.</span><span class="sxs-lookup"><span data-stu-id="017ad-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="017ad-109">Sollte der Benutzer den Anruf nicht entgegennehmen, wird der Anruf zur Voicemail des Unternehmens umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="017ad-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="017ad-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="017ad-110">See Also</span></span>


[<span data-ttu-id="017ad-111">Konfigurieren von Voicemail-Escapes in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="017ad-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="017ad-112">Neue Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="017ad-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


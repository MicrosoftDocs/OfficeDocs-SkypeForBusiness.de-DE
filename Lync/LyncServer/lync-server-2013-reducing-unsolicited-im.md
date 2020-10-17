---
title: 'Lync Server 2013: Reduzieren von unerwünschten Sofortnachrichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e6b3b720e5c05051cd556af7d32e8293e95c315
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512012"
---
# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="bb8d6-102">Reduzieren von unerwünschten Sofortnachrichten für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb8d6-102">Reducing unsolicited IM for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb8d6-103">_**Letztes Änderungsstand des Themas:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="bb8d6-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="bb8d6-104">Die intelligente Sofortnachrichten-Filter Anwendung schützt Ihre Microsoft lync Server 2013-Bereitstellung vor den häufigsten Viren mit minimaler Beeinträchtigung der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="bb8d6-105">Der intelligente Sofortnachrichtenfilter bietet folgende Funktionen:</span><span class="sxs-lookup"><span data-stu-id="bb8d6-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="bb8d6-106">Verbesserte URL-Filterung</span><span class="sxs-lookup"><span data-stu-id="bb8d6-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="bb8d6-107">Verbesserte Filterung von Dateiübertragungen</span><span class="sxs-lookup"><span data-stu-id="bb8d6-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="bb8d6-p102">Konfigurieren Sie mit dem intelligenten Sofortnachrichtenfilter Filter zum Blockieren unerwünschter oder potenziell schädlicher Sofortnachrichten von unbekannten Endpunkten außerhalb der Unternehmensfirewall. Zum Konfigurieren von Filtern geben Sie die Kriterien an, anhand derer die zu blockierenden Elemente, z. B. Sofortnachrichten mit Links und Dateien mit bestimmten Erweiterungen, ermittelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-p102">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall. You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="bb8d6-110">Bevor Sie die Filteranwendung für den intelligenten Chat Nachrichtendienst bereitstellen, sollten Sie wissen, wie Filteroptionen angewendet werden, wenn Nachrichten von einem lync Server 2013 Server an einen anderen weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="bb8d6-111">Die Art der Anwendung von Filteroptionen ist konsistent, unabhängig davon, ob die Server sich in einer einzigen Organisation oder in mehreren Organisationen befinden.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="bb8d6-112">Diese Konsistenz betrifft die Art und Weise, wie benutzerdefinierte Hinweise und Warntexte in Nachrichten eingefügt und über Server übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="bb8d6-p104">Es empfiehlt sich, die Filteroptionen so einzustellen, dass Sofortnachrichten mit Hyperlinks zugelassen sind, der intelligente Sofortnachrichtenfilter jedoch einen Unterstrich davor einfügen muss, damit der Link deaktiviert wird. Wenn Sie diese Option auswählen, können Sie zusätzlich einen Hinweis an die Benutzer verfassen, der am Anfang jeder Sofortnachricht angezeigt wird, die einen Hyperlink enthält.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-p104">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it. If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="bb8d6-p105">Eine zweite Filteroption besteht darin, Sofortnachrichten mit nicht veränderten Hyperlinks zuzulassen. Wenn Sie diese Option auswählen, können Sie zusätzlich eine Warnung an die Benutzer verfassen (empfohlen), die in jede Nachricht eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-p105">A second filtering option is to allow instant messages with unmodified hyperlinks. If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="bb8d6-p106">Eine dritte Option besteht darin, alle Sofortnachrichten mit Hyperlinks zu blockieren. Wenn Sie diese Option wählen, sendet der Server eine Warnung an den Benutzer. Diese Warnung müssen Sie selbst verfassen.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-p106">A third option is to block all instant messages that contain hyperlinks. If you choose this option, the server sends a warning to the user. You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


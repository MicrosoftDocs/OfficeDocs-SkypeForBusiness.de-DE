---
title: 'Lync Server 2013: Reduzieren von nicht angeforderten Chatnachrichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5042c4400cdf16be650a3c2c74ed756f01d93114
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="e9bed-102">Reduzieren von nicht angeforderten Chatnachrichten für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9bed-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9bed-103">_**Letztes Änderungsdatum des Themas:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="e9bed-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="e9bed-104">Die intelligente Chat Filter-Anwendung schützt Ihre Microsoft lync Server 2013-Bereitstellung vor den häufigsten Viren mit minimaler Beeinträchtigung der Benutzererfahrung.</span><span class="sxs-lookup"><span data-stu-id="e9bed-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="e9bed-105">Der intelligente Chat-Filter bietet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e9bed-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="e9bed-106">Erweiterte URL-Filterung</span><span class="sxs-lookup"><span data-stu-id="e9bed-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="e9bed-107">Verbesserte Filter für die Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="e9bed-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="e9bed-108">Verwenden Sie den intelligenten Chatfilter, um Filter so zu konfigurieren, dass unerwünschte oder potenziell schädliche Sofortnachrichten von unbekannten Endpunkten außerhalb der Unternehmensfirewall blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="e9bed-108">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="e9bed-109">Sie konfigurieren Filter, indem Sie die Kriterien angeben, die verwendet werden sollen, um zu bestimmen, was blockiert werden soll, beispielsweise Sofortnachrichten mit Links und Dateien mit bestimmten Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="e9bed-109">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="e9bed-110">Bevor Sie die intelligente Chat-Nachrichten Filter Anwendung bereitstellen, sollten Sie wissen, wie Filteroptionen angewendet werden, wenn Nachrichten von einem lync Server 2013-Server an einen anderen weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e9bed-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="e9bed-111">Die Art und Weise, wie diese Filteroptionen angewendet werden, ist konsistent, unabhängig davon, ob sich die Server in einer einzelnen Organisation oder unternehmensübergreifend befinden.</span><span class="sxs-lookup"><span data-stu-id="e9bed-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="e9bed-112">Diese Konsistenz bezieht sich auf die Art und Weise, in der benutzerdefinierte Hinweise und Warnungstexte in Nachrichten eingefügt und serverübergreifend gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9bed-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="e9bed-113">Die empfohlene Filteroption besteht darin, Sofortnachrichten mit Hyperlinks zuzulassen, aber den intelligenten Chat-Filter zum Deaktivieren der Verknüpfung zu erzwingen, indem Sie einen Unterstrich davor einfügen.</span><span class="sxs-lookup"><span data-stu-id="e9bed-113">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="e9bed-114">Wenn Sie diese Option auswählen, haben Sie die zusätzliche Möglichkeit, eine Benachrichtigung an Benutzer zu verfassen, die am Anfang jeder Chatnachricht angezeigt wird, die einen Link enthält.</span><span class="sxs-lookup"><span data-stu-id="e9bed-114">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="e9bed-115">Eine zweite Filteroption besteht darin, Sofortnachrichten mit nicht geänderten Hyperlinks zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e9bed-115">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="e9bed-116">Wenn Sie diese Option auswählen, haben Sie die zusätzliche Option (empfohlen) zum Verfassen einer Warnung für Benutzer, die in jede Nachricht eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e9bed-116">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="e9bed-117">Eine dritte Möglichkeit besteht darin, alle Sofortnachrichten, die Links enthalten, zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="e9bed-117">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="e9bed-118">Wenn Sie diese Option auswählen, sendet der Server eine Warnung an den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e9bed-118">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="e9bed-119">Sie müssen diese Warnung schreiben.</span><span class="sxs-lookup"><span data-stu-id="e9bed-119">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


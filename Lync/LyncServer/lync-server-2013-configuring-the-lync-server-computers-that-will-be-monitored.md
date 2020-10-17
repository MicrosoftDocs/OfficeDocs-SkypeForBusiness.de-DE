---
title: 'Lync Server 2013: Konfigurieren der lync Server Computer, die überwacht werden sollen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39819a546d59d47b60f0c6dfca76cc6939a1cdf2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532352"
---
# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="ae096-102">Konfigurieren der lync Server Computer, die in lync Server 2013 überwacht werden</span><span class="sxs-lookup"><span data-stu-id="ae096-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae096-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="ae096-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="ae096-104">Da lync Server 2013 den in Microsoft lync Server 2010 verwendeten zentralen Ermittlungsprozess nicht verwendet, muss jeder lync Server 2013 Computer, den Sie überwachen möchten, seine Existenz dem Verwaltungs Server selbst melden können.</span><span class="sxs-lookup"><span data-stu-id="ae096-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="ae096-105">Um dies zu ermöglichen, müssen Sie die Operations Manager-Agent-Dateien auf allen zu überwachenden Computern installieren.</span><span class="sxs-lookup"><span data-stu-id="ae096-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="ae096-106">Nach dem Installieren der Agent-Dateien müssen Sie die Computer für die Funktion als System Center-Proxy konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ae096-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="ae096-107">Beachten Sie, dass diese Verfahren ausgeführt werden sollten, nachdem Sie lync Server auf diesen Computern installiert und konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="ae096-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


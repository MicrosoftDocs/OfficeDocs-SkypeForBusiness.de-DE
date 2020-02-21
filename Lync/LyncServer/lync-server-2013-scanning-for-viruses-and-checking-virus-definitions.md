---
title: 'Lync Server 2013: Überprüfen auf Viren und Virendefinitionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aba7d5f1b279ba83a5a6053d2197c90253dd84ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="6d9ca-102">Überprüfen auf Viren und Virendefinitionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d9ca-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d9ca-103">_**Letztes Änderungsstand des Themas:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="6d9ca-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="6d9ca-104">Es wird dringend empfohlen, ein Antivirenprogramm für eine Sofortnachrichten Ebene zu installieren.</span><span class="sxs-lookup"><span data-stu-id="6d9ca-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="6d9ca-105">Im ist eine bekannte Quelle für die schnelle Verbreitung von Viren und bösartiger Software in einer Organisation.</span><span class="sxs-lookup"><span data-stu-id="6d9ca-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="6d9ca-106">Microsoft Forefront® Sicherheit für lync Server bietet Multi-Engine-Scans mit Viren, bösartiger Software, Datei-und Keyword-Filterschutz und nahtloser Integration in Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="6d9ca-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="6d9ca-107">Neben Forefront Security für lync Server empfehlen wir auch, eine Antivirus-Lösung auf Dateiebene zu installieren, um das Dateisystem des Servers zu schützen.</span><span class="sxs-lookup"><span data-stu-id="6d9ca-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="6d9ca-108">Das Aktualisieren von Scanner-Engines und Virendefinitionen ist sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="6d9ca-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="6d9ca-109">Durch das Konfigurieren und Überwachen der Integrität der Updates wird sichergestellt, dass die aktuellsten Überprüfungsinformationen verwendet werden, um sowohl Office Communications Server als auch das Dateisystem zu schützen.</span><span class="sxs-lookup"><span data-stu-id="6d9ca-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6d9ca-110">Wenn Sie eine Antivirensoftware eines Drittanbieters auf Dateiebene auf einem Server verwenden, auf dem lync Server 2013 und Forefront Security für lync Server ausgeführt wird, stellen Sie sicher, dass die Ordner, in denen Forefront Security für lync Server und die lync Server installiert sind, nicht überprüft werden, um zu verhindern Korruption.</span><span class="sxs-lookup"><span data-stu-id="6d9ca-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="6d9ca-111">Die vollständige Liste der Ausschlüsse finden Sie <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>unter.</span><span class="sxs-lookup"><span data-stu-id="6d9ca-111">For the full list of exclusions, see <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


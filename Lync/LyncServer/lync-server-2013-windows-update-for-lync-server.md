---
title: 'Lync Server 2013: Windows Update für Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows Update for Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518337(v=OCS.15)
ms:contentKeyID: 62625495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8df575ac6c42bd62db57ed4e6595ced0af32014a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="12e33-102">Windows Update für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e33-102">Windows Update for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12e33-103">_**Letztes Änderungsdatum des Themas:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="12e33-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="12e33-104">Regelmäßiges Überprüfen und Anwenden von Updates und Sicherheitsupdates mithilfe von Windows Update Services.</span><span class="sxs-lookup"><span data-stu-id="12e33-104">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="12e33-105">Dadurch werden Sicherheitsrisiken in anderen Systemkomponenten verhindert, die dazu führen können, dass Angreifer Zugriff auf Server mit Microsoft lync Server 2013 mit Administratorrechten erhalten und dadurch lync Server 2013 gefährden.</span><span class="sxs-lookup"><span data-stu-id="12e33-105">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="12e33-106">Updates für Microsoft SQL Server 2008 Express (64-Bit Edition) werden auf jedem lync Server 2013 Standard Edition-Server (für die Back-End-Datenbank) und auf allen anderen lync Server 2013-Serverrollen (für den lokalen Konfigurationsspeicher) ausgeführt, es sei denn, Sie haben diese aktualisiert Datenbanken zu SQL Server 2008 R2 Express.</span><span class="sxs-lookup"><span data-stu-id="12e33-106">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="12e33-107">Sie sollten diese Datenbanken im Rahmen der routinemäßigen Aktualisierung des Sicherheitsupdates berücksichtigen, ebenso wie SQL Server in der Back-End-Datenbank eines Front-End-Pools, der Überwachungsdatenbank und der Archivierungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="12e33-107">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="12e33-108">Bewährte Methode</span><span class="sxs-lookup"><span data-stu-id="12e33-108">Best Practice</span></span>

  - <span data-ttu-id="12e33-109">Mit Windows Update auf dem Laufenden bleiben.</span><span class="sxs-lookup"><span data-stu-id="12e33-109">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Vorbereiten von Active Directory für Lync Server
description: Vorbereiten Active Directory auf lync Server.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prepare Active Directory for Lync Server
ms:assetid: 54cd597d-0c2d-479c-8c52-1babc53f71dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688059(v=OCS.15)
ms:contentKeyID: 49733653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff9ff2de825d68f2c7ca9d90cbecdf71e5d00d55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563701"
---
# <a name="prepare-active-directory-for-lync-server"></a><span data-ttu-id="0f988-103">Vorbereiten von Active Directory für Lync Server</span><span class="sxs-lookup"><span data-stu-id="0f988-103">Prepare Active Directory for Lync Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f988-104">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="0f988-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="0f988-105">Vor dem Bereitstellen von lync Server 2013 im koexistenzstatus mit lync Server 2010 müssen Sie einige zusätzliche Active Directory Aufgaben ausführen, um das Schema, die Gesamtstruktur und die Domäne für lync Server 2013 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0f988-105">Prior to deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="0f988-106">Die Schemaerweiterungen fügen die Active Directory Klassen und Attribute hinzu, die für lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0f988-106">The schema extensions add the Active Directory classes and attributes that are required by Lync Server 2013.</span></span> <span data-ttu-id="0f988-107">Weitere Informationen finden Sie im Thema [vorbereiten Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="0f988-107">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="0f988-108">**So bereiten Sie Active Directory für lync Server 2013 vor**</span><span class="sxs-lookup"><span data-stu-id="0f988-108">**To prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="0f988-109">Führen Sie im lync Server 2013 Front-End-Server lync Server 2013 Setup aus.</span><span class="sxs-lookup"><span data-stu-id="0f988-109">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="0f988-110">Wählen Sie **Active Directory vorbereiten** aus.</span><span class="sxs-lookup"><span data-stu-id="0f988-110">Select **Prepare Active Directory**.</span></span>
    
    <span data-ttu-id="0f988-111">![Lync Server 2013-Bereitstellungs-Assistent, Willkommensseite](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013-Bereitstellungs-Assistent, Willkommensseite")</span><span class="sxs-lookup"><span data-stu-id="0f988-111">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="0f988-112">Führen Sie die Schritte 1 bis 5 aus.</span><span class="sxs-lookup"><span data-stu-id="0f988-112">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="0f988-113">![Bereitstellungs-Assistent, Active Directory prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Bereitstellungs-Assistent, Active Directory prearation")</span><span class="sxs-lookup"><span data-stu-id="0f988-113">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


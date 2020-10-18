---
title: 'Lync Server 2013: Voraussetzungen für die Aktivierung der Kerberos-Authentifizierung'
description: 'Lync Server 2013: Voraussetzungen für die Aktivierung der Kerberos-Authentifizierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65a45bad0eb249fdbc717fe05f080ce737c87c6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579921"
---
# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="72521-103">Voraussetzungen für die Aktivierung der Kerberos-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72521-103">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72521-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="72521-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="72521-105">Stellen Sie vor dem Aktivieren der Kerberos-Authentifizierung sicher, dass Sie alle erforderlichen Konfigurations-und Infrastruktur Vorbereitungen ausführen:</span><span class="sxs-lookup"><span data-stu-id="72521-105">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="72521-106">Active Directory Schema wird für lync Server 2013 erweitert.</span><span class="sxs-lookup"><span data-stu-id="72521-106">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="72521-107">Active Directory Gesamtstrukturvorbereitung ist für lync Server 2013 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="72521-107">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="72521-108">Active Directory Domänenvorbereitung ist für lync Server 2013 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="72521-108">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="72521-109">Der zentrale Verwaltungsspeicher wurde erfolgreich installiert und ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="72521-109">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="72521-110">Die Topologie wurde mithilfe des Topologie-Generators erstellt und veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="72521-110">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="72521-111">Server und Rollen, die Webdienste erfordern, wurden definiert und bereitgestellt, einschließlich Front-End-Server, Standard Edition-Server und Directors.</span><span class="sxs-lookup"><span data-stu-id="72521-111">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="72521-112">Internet Information Services (IIS) wird mit den empfohlenen Rollendiensten konfiguriert und bereitgestellt, um Webdienste in lync Server 2013 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="72521-112">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="72521-113">Nachdem die Voraussetzungen erfüllt sind, sollten Sie bereit sein, ein oder mehrere Konten für Webdienste zu erstellen, die für die Kerberos-Authentifizierung für Ihre Bereitstellung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="72521-113">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="72521-114">Sie müssen pro Bereitstellung mindestens ein Kerberos-Authentifizierungskonto erstellen.</span><span class="sxs-lookup"><span data-stu-id="72521-114">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="72521-115">Sie können jedoch ein Konto für jeden Standort erstellen, um eine lokale Kerberos-Authentifizierung am Standort zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="72521-115">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="72521-116">Pro Standort kann nur ein Kerberos-Authentifizierungskonto angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="72521-116">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


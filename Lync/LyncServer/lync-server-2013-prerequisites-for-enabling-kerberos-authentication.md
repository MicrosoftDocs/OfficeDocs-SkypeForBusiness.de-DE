---
title: 'Lync Server 2013: Voraussetzungen für die Aktivierung der Kerberos-Authentifizierung'
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
ms.openlocfilehash: ecbba3403024663e529cef7653b310148faa2e2c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="8cfdc-102">Voraussetzungen für die Aktivierung der Kerberos-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cfdc-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cfdc-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8cfdc-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8cfdc-104">Stellen Sie vor dem Aktivieren der Kerberos-Authentifizierung sicher, dass Sie alle erforderlichen Konfigurations-und Infrastruktur Vorbereitungen ausführen:</span><span class="sxs-lookup"><span data-stu-id="8cfdc-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="8cfdc-105">Active Directory Schema wird für lync Server 2013 erweitert.</span><span class="sxs-lookup"><span data-stu-id="8cfdc-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="8cfdc-106">Active Directory Gesamtstrukturvorbereitung ist für lync Server 2013 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8cfdc-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="8cfdc-107">Active Directory Domänenvorbereitung ist für lync Server 2013 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8cfdc-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="8cfdc-108">Der zentrale Verwaltungsspeicher wurde erfolgreich installiert und ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8cfdc-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="8cfdc-109">Die Topologie wurde mithilfe des Topologie-Generators erstellt und veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="8cfdc-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="8cfdc-110">Server und Rollen, die Webdienste erfordern, wurden definiert und bereitgestellt, einschließlich Front-End-Server, Standard Edition-Server und Directors.</span><span class="sxs-lookup"><span data-stu-id="8cfdc-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="8cfdc-111">Internet Information Services (IIS) wird mit den empfohlenen Rollendiensten konfiguriert und bereitgestellt, um Webdienste in lync Server 2013 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8cfdc-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="8cfdc-112">Nachdem die Voraussetzungen erfüllt sind, sollten Sie bereit sein, ein oder mehrere Konten für Webdienste zu erstellen, die für die Kerberos-Authentifizierung für Ihre Bereitstellung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8cfdc-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="8cfdc-113">Sie müssen pro Bereitstellung mindestens ein Kerberos-Authentifizierungskonto erstellen.</span><span class="sxs-lookup"><span data-stu-id="8cfdc-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="8cfdc-114">Sie können jedoch ein Konto für jeden Standort erstellen, um eine lokale Kerberos-Authentifizierung am Standort zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8cfdc-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="8cfdc-115">Pro Standort kann nur ein Kerberos-Authentifizierungskonto angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8cfdc-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Voraussetzungen zur Aktivierung der Kerberos-Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f405daa37007bffba1e02bd10d20d4de907e820e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="e245e-102">Voraussetzungen zur Aktivierung der Kerberos-Authentifizierung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e245e-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e245e-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e245e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e245e-104">Bevor Sie die Kerberos-Authentifizierung aktivieren, stellen Sie sicher, dass Sie alle erforderlichen Konfigurations-und Infrastruktur Vorbereitungen durchführen:</span><span class="sxs-lookup"><span data-stu-id="e245e-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="e245e-105">Das Active Directory-Schema wird für lync Server 2013 erweitert.</span><span class="sxs-lookup"><span data-stu-id="e245e-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="e245e-106">Die Active Directory-Gesamtstrukturvorbereitung ist für lync Server 2013 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e245e-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="e245e-107">Die Active Directory-Domänenvorbereitung ist für lync Server 2013 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e245e-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="e245e-108">Der zentrale Verwaltungsspeicher wurde erfolgreich installiert und verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e245e-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="e245e-109">Die Topologie wurde mithilfe des Topologie-Generators erstellt und veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="e245e-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="e245e-110">Server und Rollen, die Webdienste erfordern, wurden definiert und bereitgestellt, einschließlich der Front-End-Server, der Standard Edition-Server und der Directors.</span><span class="sxs-lookup"><span data-stu-id="e245e-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="e245e-111">Internet Informationsdienste (IIS) wird mit den empfohlenen Rollendiensten für die Unterstützung von Webdiensten in lync Server 2013 konfiguriert und bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e245e-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="e245e-112">Nachdem die Voraussetzungen erfüllt wurden, sollten Sie bereit sein, mindestens ein Konto für Webdienste zu erstellen, das für die Kerberos-Authentifizierung für Ihre Bereitstellung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e245e-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="e245e-113">Sie müssen mindestens ein Kerberos-Authentifizierungs Konto für jede Bereitstellung erstellen.</span><span class="sxs-lookup"><span data-stu-id="e245e-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="e245e-114">Sie können jedoch für jede Website ein Konto erstellen, um die lokale Kerberos-Authentifizierung auf der Website bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e245e-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="e245e-115">Sie können nur ein Kerberos-Authentifizierungs Konto pro Website angeben.</span><span class="sxs-lookup"><span data-stu-id="e245e-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


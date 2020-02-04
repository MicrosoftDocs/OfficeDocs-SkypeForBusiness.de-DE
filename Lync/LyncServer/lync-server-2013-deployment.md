---
title: 'Lync Server 2013: Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment
ms:assetid: 83bd43ee-c1fe-4b38-bfa7-3eb382817bf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398664(v=OCS.15)
ms:contentKeyID: 48184687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40f77a307b516874449a86f42f84a3053e5f5914
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="af4e0-102">Bereitstellung von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-102">Deployment of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af4e0-103">_**Letztes Änderungsdatum des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="af4e0-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="af4e0-104">Die Bereitstellung der lync Server 2013-Kommunikationssoftware umfasst das Vorbereiten von Active Directory-Domänendiensten, die Bereitstellung der Front-End-Server und anderer interner Komponenten von lync Server 2013 sowie die Bereitstellung zusätzlicher Server Rollen und Features, die möglicherweise erfordert Ihre Organisation beispielsweise den Zugriff durch externe Benutzer und Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="af4e0-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="af4e0-105">In dieser Dokumentation werden drei Szenarien für die Bereitstellung von lync Server 2013 beschrieben:</span><span class="sxs-lookup"><span data-stu-id="af4e0-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="af4e0-106">Neue Bereitstellung von lync Server 2013, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="af4e0-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="af4e0-107">Neue Bereitstellung von lync Server 2013, Standard Edition</span><span class="sxs-lookup"><span data-stu-id="af4e0-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="af4e0-108">Neue Bereitstellung von lync Server 2013 Standard Edition oder Enterprise Edition in einer vorhandenen lync Server 2010 Standard Edition oder Enterprise Edition-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="af4e0-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="af4e0-109">Informationen zum Bereitstellen von lync Server 2013 in einer vorhandenen Microsoft Office Communications Server 2007-oder Microsoft Office Communications Server 2007 R2-Umgebung finden Sie in der [Migrations](migration.md) Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="af4e0-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="af4e0-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="af4e0-110">In This Section</span></span>

  - [<span data-ttu-id="af4e0-111">Bereitstellen von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="af4e0-112">Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="af4e0-113">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="af4e0-114">Bereitstellen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="af4e0-115">Bereitstellen der Archivierung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="af4e0-116">Konfigurieren von Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="af4e0-117">Planen und Bereitstellen von Video in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="af4e0-118">Bereitstellen von Zweigstellen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="af4e0-119">Bereitstellen des Servers für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="af4e0-120">Bereitstellen von Clients und Geräten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="af4e0-121">Planen und Bereitstellen von Unified Contact Store in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="af4e0-122">Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="af4e0-123">Aktualisieren von der Evaluierungsversion von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="af4e0-124">Bereitstellen der Remoteanrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="af4e0-125">Bereitstellen von Mobilität in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="af4e0-126">Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="af4e0-127">Integritäts Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af4e0-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


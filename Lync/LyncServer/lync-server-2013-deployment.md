---
title: 'Lync Server 2013: Bereitstellung'
description: 'Lync Server 2013: Bereitstellung.'
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
ms.openlocfilehash: 750dabf9659327b19e80006d1bca05090f22fd43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555361"
---
# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="a2d94-103">Bereitstellung von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-103">Deployment of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2d94-104">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="a2d94-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="a2d94-105">Die Bereitstellung von lync Server 2013 Kommunikationssoftware umfasst die Vorbereitung Active Directory-Domänendienste, die Bereitstellung der Front-End-Server und anderer Kern lync Server 2013 interner Komponenten sowie die anschließende Bereitstellung zusätzlicher Server Rollen und Features, die Ihre Organisation möglicherweise benötigt, beispielsweise externer Benutzer Zugriff und Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="a2d94-105">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="a2d94-106">In dieser Dokumentation werden drei Szenarien für die Bereitstellung von lync Server 2013 beschrieben:</span><span class="sxs-lookup"><span data-stu-id="a2d94-106">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="a2d94-107">Neue Bereitstellung von lync Server 2013, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="a2d94-107">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="a2d94-108">Neue Bereitstellung von lync Server 2013, Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a2d94-108">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="a2d94-109">Neue Bereitstellung von lync Server 2013 Standard Edition oder Enterprise Edition in einer vorhandenen lync Server 2010 Standard Edition-oder Enterprise Edition-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="a2d94-109">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="a2d94-110">Informationen zum Bereitstellen von lync Server 2013 in einer vorhandenen Microsoft Office Communications Server 2007-oder Microsoft Office Communications Server 2007 R2-Umgebung finden Sie in der [Migrations](migration.md) Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a2d94-110">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a2d94-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2d94-111">In This Section</span></span>

  - [<span data-ttu-id="a2d94-112">Bereitstellen von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-112">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="a2d94-113">Bereitstellen von externem Benutzer Zugriff in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-113">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="a2d94-114">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-114">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="a2d94-115">Bereitstellen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-115">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="a2d94-116">Bereitstellen der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-116">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="a2d94-117">Konfigurieren von Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-117">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="a2d94-118">Planen und Bereitstellen von Videos in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-118">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="a2d94-119">Bereitstellen von Zweigstellenstandorten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-119">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="a2d94-120">Bereitstellen des Servers für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-120">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="a2d94-121">Bereitstellen von Clients und Geräten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-121">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="a2d94-122">Planen und Bereitstellen des einheitlichen Kontaktspeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-122">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="a2d94-123">Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-123">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="a2d94-124">Aktualisieren von der Evaluierungsversion von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-124">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="a2d94-125">Bereitstellen der Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-125">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="a2d94-126">Bereitstellen von Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-126">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="a2d94-127">Konfigurieren der Integration mit Office-webapps Server und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-127">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="a2d94-128">Integritäts Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d94-128">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


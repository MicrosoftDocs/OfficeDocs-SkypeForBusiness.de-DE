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
ms.openlocfilehash: b5fcba91b3017faff29ad8d1bcce20d51a32bd1d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498982"
---
# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="d1c0b-102">Bereitstellung von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-102">Deployment of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1c0b-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d1c0b-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d1c0b-104">Die Bereitstellung von lync Server 2013 Kommunikationssoftware umfasst die Vorbereitung Active Directory-Domänendienste, die Bereitstellung der Front-End-Server und anderer Kern lync Server 2013 interner Komponenten sowie die anschließende Bereitstellung zusätzlicher Server Rollen und Features, die Ihre Organisation möglicherweise benötigt, beispielsweise externer Benutzer Zugriff und Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="d1c0b-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="d1c0b-105">In dieser Dokumentation werden drei Szenarien für die Bereitstellung von lync Server 2013 beschrieben:</span><span class="sxs-lookup"><span data-stu-id="d1c0b-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="d1c0b-106">Neue Bereitstellung von lync Server 2013, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="d1c0b-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="d1c0b-107">Neue Bereitstellung von lync Server 2013, Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d1c0b-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="d1c0b-108">Neue Bereitstellung von lync Server 2013 Standard Edition oder Enterprise Edition in einer vorhandenen lync Server 2010 Standard Edition-oder Enterprise Edition-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="d1c0b-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="d1c0b-109">Informationen zum Bereitstellen von lync Server 2013 in einer vorhandenen Microsoft Office Communications Server 2007-oder Microsoft Office Communications Server 2007 R2-Umgebung finden Sie in der [Migrations](migration.md) Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="d1c0b-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d1c0b-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d1c0b-110">In This Section</span></span>

  - [<span data-ttu-id="d1c0b-111">Bereitstellen von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="d1c0b-112">Bereitstellen von externem Benutzer Zugriff in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="d1c0b-113">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="d1c0b-114">Bereitstellen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="d1c0b-115">Bereitstellen der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="d1c0b-116">Konfigurieren von Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="d1c0b-117">Planen und Bereitstellen von Videos in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="d1c0b-118">Bereitstellen von Zweigstellenstandorten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="d1c0b-119">Bereitstellen des Servers für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="d1c0b-120">Bereitstellen von Clients und Geräten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="d1c0b-121">Planen und Bereitstellen des einheitlichen Kontaktspeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="d1c0b-122">Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="d1c0b-123">Aktualisieren von der Evaluierungsversion von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="d1c0b-124">Bereitstellen der Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="d1c0b-125">Bereitstellen von Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="d1c0b-126">Konfigurieren der Integration mit Office-webapps Server und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="d1c0b-127">Integritäts Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1c0b-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


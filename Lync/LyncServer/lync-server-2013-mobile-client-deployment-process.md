---
title: 'Lync Server 2013: Bereitstellungsprozess für mobile Clients'
description: 'Lync Server 2013: Bereitstellungsprozess für mobile Clients.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa4e9e1d272915e06009df5c06480309ce104e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563481"
---
# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="9cdf6-103">Bereitstellungsprozess für mobile Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cdf6-103">Mobile client deployment process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cdf6-104">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="9cdf6-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="9cdf6-105">Nachdem eine Bereitstellung von Microsoft lync Server 2013 abgeschlossen wurde, können Benutzer die lync 2013-App aus dem mobilen Marktplatz installieren, den Sie für Ihr spezielles Gerät gewohnt sind.</span><span class="sxs-lookup"><span data-stu-id="9cdf6-105">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="9cdf6-106">Lync Mobile-Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="9cdf6-106">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9cdf6-107">Phase</span><span class="sxs-lookup"><span data-stu-id="9cdf6-107">Phase</span></span></th>
<th><span data-ttu-id="9cdf6-108">Schritte</span><span class="sxs-lookup"><span data-stu-id="9cdf6-108">Steps</span></span></th>
<th><span data-ttu-id="9cdf6-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9cdf6-109">Permissions</span></span></th>
<th><span data-ttu-id="9cdf6-110">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="9cdf6-110">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cdf6-111">Ausführen der Aufgaben, die vor der Einrichtung anstehen</span><span class="sxs-lookup"><span data-stu-id="9cdf6-111">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="9cdf6-112">Überprüfen Sie lync Server 2013 Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="9cdf6-112">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="9cdf6-113">Überprüfen der Zertifikatanforderungen</span><span class="sxs-lookup"><span data-stu-id="9cdf6-113">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="9cdf6-114">Administrator</span><span class="sxs-lookup"><span data-stu-id="9cdf6-114">Administrator</span></span></p></td>
<td><p><span data-ttu-id="9cdf6-115"><a href="lync-server-2013-planning-for-mobility.md">Planen der Mobilität in lync Server 2013</a> in der Dokumentation zur Server Planung.</span><span class="sxs-lookup"><span data-stu-id="9cdf6-115"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="9cdf6-116"><a href="lync-server-2013-deploying-mobility.md">Bereitstellen von Mobilität in lync Server 2013</a> in der Dokumentation zur Server Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="9cdf6-116"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="9cdf6-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Zertifikatinfrastruktur Anforderungen für lync Server 2013</a> in der Dokumentation zur Server Planung.</span><span class="sxs-lookup"><span data-stu-id="9cdf6-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cdf6-118">Installieren der Lync-Anwendung auf einem Testgerät</span><span class="sxs-lookup"><span data-stu-id="9cdf6-118">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="9cdf6-119">Installieren der erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="9cdf6-119">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="9cdf6-120">Installieren der Anwendung aus dem für das mobile Gerät spezifischen Marketplace</span><span class="sxs-lookup"><span data-stu-id="9cdf6-120">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="9cdf6-121">Administrator</span><span class="sxs-lookup"><span data-stu-id="9cdf6-121">Administrator</span></span></p></td>
<td><p><span data-ttu-id="9cdf6-122">Installationsanweisungen speziell für das Mobile Gerät bei der <a href="lync-server-2013-deploying-mobile-clients.md">Bereitstellung von mobilen Clients in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9cdf6-122">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cdf6-123">Konfigurieren des Clients</span><span class="sxs-lookup"><span data-stu-id="9cdf6-123">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9cdf6-124">Konfigurieren der Anmeldeinstellungen und Serverinformationen</span><span class="sxs-lookup"><span data-stu-id="9cdf6-124">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9cdf6-125">Administrator</span><span class="sxs-lookup"><span data-stu-id="9cdf6-125">Administrator</span></span></p></td>
<td><p><span data-ttu-id="9cdf6-126"><a href="lync-server-2013-deploying-mobile-clients.md">Bereitstellen von mobilen Clients in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9cdf6-126"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cdf6-127">Testen der mobilen Szenarien</span><span class="sxs-lookup"><span data-stu-id="9cdf6-127">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="9cdf6-128">Testen von Chatnachrichten und Anwesenheitsinformationen</span><span class="sxs-lookup"><span data-stu-id="9cdf6-128">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="9cdf6-129">Testen der Dial-Out-Konferenz</span><span class="sxs-lookup"><span data-stu-id="9cdf6-129">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="9cdf6-130">Suchen nach einem Kontakt im Unternehmensverzeichnis</span><span class="sxs-lookup"><span data-stu-id="9cdf6-130">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="9cdf6-131">Testen von Pushbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="9cdf6-131">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="9cdf6-132">Administrator</span><span class="sxs-lookup"><span data-stu-id="9cdf6-132">Administrator</span></span></p></td>
<td><p><span data-ttu-id="9cdf6-133">Spezifische Überprüfungsanweisungen für das Mobile Gerät bei der <a href="lync-server-2013-deploying-mobile-clients.md">Bereitstellung von mobilen Clients in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9cdf6-133">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cdf6-134">Installieren der Lync-Anwendung auf Mobiltelefonen</span><span class="sxs-lookup"><span data-stu-id="9cdf6-134">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="9cdf6-135">Installieren der erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="9cdf6-135">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="9cdf6-136">Installieren der Anwendung aus dem für das mobile Gerät spezifischen Marketplace</span><span class="sxs-lookup"><span data-stu-id="9cdf6-136">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="9cdf6-137">Benutzer</span><span class="sxs-lookup"><span data-stu-id="9cdf6-137">User</span></span></p></td>
<td><p><span data-ttu-id="9cdf6-138">Installationsanweisungen speziell für das Mobile Gerät bei der <a href="lync-server-2013-deploying-mobile-clients.md">Bereitstellung von mobilen Clients in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9cdf6-138">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


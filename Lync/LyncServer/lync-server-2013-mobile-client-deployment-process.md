---
title: 'Lync Server 2013: Bereitstellungsprozess für mobile Clients'
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
ms.openlocfilehash: 14acbf4a8be4d453fc1a0c5dc4da303136433e0c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="e6f9a-102">Bereitstellungsprozess für mobile Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f9a-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6f9a-103">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e6f9a-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e6f9a-104">Nachdem eine Bereitstellung von Microsoft lync Server 2013 abgeschlossen wurde, können Benutzer die lync 2013-App aus dem mobilen Marktplatz installieren, den Sie für Ihr spezielles Gerät gewohnt sind.</span><span class="sxs-lookup"><span data-stu-id="e6f9a-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="e6f9a-105">Lync Mobile-Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="e6f9a-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6f9a-106">Phase</span><span class="sxs-lookup"><span data-stu-id="e6f9a-106">Phase</span></span></th>
<th><span data-ttu-id="e6f9a-107">Schritte</span><span class="sxs-lookup"><span data-stu-id="e6f9a-107">Steps</span></span></th>
<th><span data-ttu-id="e6f9a-108">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e6f9a-108">Permissions</span></span></th>
<th><span data-ttu-id="e6f9a-109">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="e6f9a-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6f9a-110">Ausführen der Aufgaben, die vor der Einrichtung anstehen</span><span class="sxs-lookup"><span data-stu-id="e6f9a-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e6f9a-111">Überprüfen Sie lync Server 2013 Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="e6f9a-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="e6f9a-112">Überprüfen der Zertifikatanforderungen</span><span class="sxs-lookup"><span data-stu-id="e6f9a-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e6f9a-113">Administrator</span><span class="sxs-lookup"><span data-stu-id="e6f9a-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e6f9a-114"><a href="lync-server-2013-planning-for-mobility.md">Planen der Mobilität in lync Server 2013</a> in der Dokumentation zur Server Planung.</span><span class="sxs-lookup"><span data-stu-id="e6f9a-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="e6f9a-115"><a href="lync-server-2013-deploying-mobility.md">Bereitstellen von Mobilität in lync Server 2013</a> in der Dokumentation zur Server Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="e6f9a-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="e6f9a-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Zertifikatinfrastruktur Anforderungen für lync Server 2013</a> in der Dokumentation zur Server Planung.</span><span class="sxs-lookup"><span data-stu-id="e6f9a-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6f9a-117">Installieren der Lync-Anwendung auf einem Testgerät</span><span class="sxs-lookup"><span data-stu-id="e6f9a-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e6f9a-118">Installieren der erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="e6f9a-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="e6f9a-119">Installieren der Anwendung aus dem für das mobile Gerät spezifischen Marketplace</span><span class="sxs-lookup"><span data-stu-id="e6f9a-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e6f9a-120">Administrator</span><span class="sxs-lookup"><span data-stu-id="e6f9a-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e6f9a-121">Installationsanweisungen speziell für das Mobile Gerät bei der <a href="lync-server-2013-deploying-mobile-clients.md">Bereitstellung von mobilen Clients in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e6f9a-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6f9a-122">Konfigurieren des Clients</span><span class="sxs-lookup"><span data-stu-id="e6f9a-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e6f9a-123">Konfigurieren der Anmeldeinstellungen und Serverinformationen</span><span class="sxs-lookup"><span data-stu-id="e6f9a-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e6f9a-124">Administrator</span><span class="sxs-lookup"><span data-stu-id="e6f9a-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e6f9a-125"><a href="lync-server-2013-deploying-mobile-clients.md">Bereitstellen von mobilen Clients in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e6f9a-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6f9a-126">Testen der mobilen Szenarien</span><span class="sxs-lookup"><span data-stu-id="e6f9a-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e6f9a-127">Testen von Chatnachrichten und Anwesenheitsinformationen</span><span class="sxs-lookup"><span data-stu-id="e6f9a-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="e6f9a-128">Testen der Dial-Out-Konferenz</span><span class="sxs-lookup"><span data-stu-id="e6f9a-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="e6f9a-129">Suchen nach einem Kontakt im Unternehmensverzeichnis</span><span class="sxs-lookup"><span data-stu-id="e6f9a-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="e6f9a-130">Testen von Pushbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="e6f9a-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e6f9a-131">Administrator</span><span class="sxs-lookup"><span data-stu-id="e6f9a-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e6f9a-132">Spezifische Überprüfungsanweisungen für das Mobile Gerät bei der <a href="lync-server-2013-deploying-mobile-clients.md">Bereitstellung von mobilen Clients in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e6f9a-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6f9a-133">Installieren der Lync-Anwendung auf Mobiltelefonen</span><span class="sxs-lookup"><span data-stu-id="e6f9a-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e6f9a-134">Installieren der erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="e6f9a-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="e6f9a-135">Installieren der Anwendung aus dem für das mobile Gerät spezifischen Marketplace</span><span class="sxs-lookup"><span data-stu-id="e6f9a-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e6f9a-136">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e6f9a-136">User</span></span></p></td>
<td><p><span data-ttu-id="e6f9a-137">Installationsanweisungen speziell für das Mobile Gerät bei der <a href="lync-server-2013-deploying-mobile-clients.md">Bereitstellung von mobilen Clients in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e6f9a-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


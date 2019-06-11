---
title: 'Lync Server 2013: Bereitstellungsprozess für mobile Clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0d0bf17fe4906d49fefd8bd319d25d1268191e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="6757e-102">Bereitstellungsprozess für mobile Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6757e-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6757e-103">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="6757e-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="6757e-104">Nachdem eine Bereitstellung von Microsoft lync Server 2013 abgeschlossen wurde, können Benutzer die lync 2013-App aus dem mobilen Marktplatz installieren, den Sie für Ihr spezifisches Gerät gewohnt sind.</span><span class="sxs-lookup"><span data-stu-id="6757e-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="6757e-105">Bereitstellungsprozess für lync Mobile</span><span class="sxs-lookup"><span data-stu-id="6757e-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6757e-106">Phase</span><span class="sxs-lookup"><span data-stu-id="6757e-106">Phase</span></span></th>
<th><span data-ttu-id="6757e-107">Schritte</span><span class="sxs-lookup"><span data-stu-id="6757e-107">Steps</span></span></th>
<th><span data-ttu-id="6757e-108">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6757e-108">Permissions</span></span></th>
<th><span data-ttu-id="6757e-109">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="6757e-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6757e-110">Ausführen von Aufgaben vor der Installation</span><span class="sxs-lookup"><span data-stu-id="6757e-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6757e-111">Überprüfen Sie die lync Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="6757e-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="6757e-112">Überprüfen Sie die Zertifikatanforderungen.</span><span class="sxs-lookup"><span data-stu-id="6757e-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6757e-113">Administrator</span><span class="sxs-lookup"><span data-stu-id="6757e-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="6757e-114"><a href="lync-server-2013-planning-for-mobility.md">Planen der Mobilität in lync Server 2013</a> in der Dokumentation zur Server Planung</span><span class="sxs-lookup"><span data-stu-id="6757e-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="6757e-115"><a href="lync-server-2013-deploying-mobility.md">Bereitstellen von Mobilität in lync Server 2013</a> in der Server Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6757e-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="6757e-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Anforderungen für die Zertifikatinfrastruktur für lync Server 2013</a> in der Server Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6757e-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6757e-117">Installieren Sie die lync-Anwendung auf einem Testgerät.</span><span class="sxs-lookup"><span data-stu-id="6757e-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6757e-118">Installieren Sie die Voraussetzungen.</span><span class="sxs-lookup"><span data-stu-id="6757e-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="6757e-119">Installieren Sie von dem für das Mobile Gerät spezifischen Marktplatz.</span><span class="sxs-lookup"><span data-stu-id="6757e-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6757e-120">Administrator</span><span class="sxs-lookup"><span data-stu-id="6757e-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="6757e-121">Spezifische Installationsanweisungen für das Mobile Gerät bei der <a href="lync-server-2013-deploying-mobile-clients.md">Bereitstellung von mobilen Clients in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6757e-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6757e-122">Konfigurieren Sie den Client.</span><span class="sxs-lookup"><span data-stu-id="6757e-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6757e-123">Konfigurieren Sie Anmeldeeinstellungen und Server Informationen.</span><span class="sxs-lookup"><span data-stu-id="6757e-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6757e-124">Administrator</span><span class="sxs-lookup"><span data-stu-id="6757e-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="6757e-125"><a href="lync-server-2013-deploying-mobile-clients.md">Bereitstellen von mobilen Clients in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6757e-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6757e-126">Testen Sie mobile Szenarien.</span><span class="sxs-lookup"><span data-stu-id="6757e-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6757e-127">Testen von Instant Messaging (im) und Anwesenheitsinformationen</span><span class="sxs-lookup"><span data-stu-id="6757e-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="6757e-128">Testen Sie Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="6757e-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="6757e-129">Suchen Sie im Unternehmensverzeichnis nach einem Kontakt.</span><span class="sxs-lookup"><span data-stu-id="6757e-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="6757e-130">Testen von Push-Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="6757e-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6757e-131">Administrator</span><span class="sxs-lookup"><span data-stu-id="6757e-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="6757e-132">Für das Mobile Gerät spezifische Verifizierungs Anweisungen beim <a href="lync-server-2013-deploying-mobile-clients.md">Bereitstellen von mobilen Clients in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6757e-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6757e-133">Installieren Sie die lync-Anwendung auf Mobiltelefonen.</span><span class="sxs-lookup"><span data-stu-id="6757e-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6757e-134">Installieren Sie die Voraussetzungen.</span><span class="sxs-lookup"><span data-stu-id="6757e-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="6757e-135">Installieren Sie von dem für das Mobile Gerät spezifischen Marktplatz.</span><span class="sxs-lookup"><span data-stu-id="6757e-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6757e-136">User</span><span class="sxs-lookup"><span data-stu-id="6757e-136">User</span></span></p></td>
<td><p><span data-ttu-id="6757e-137">Spezifische Installationsanweisungen für das Mobile Gerät bei der <a href="lync-server-2013-deploying-mobile-clients.md">Bereitstellung von mobilen Clients in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6757e-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


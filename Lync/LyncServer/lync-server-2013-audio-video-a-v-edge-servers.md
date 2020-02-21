---
title: 'Lync Server 2013: Audio/Video-Edgeserver (a/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fce9f00d84465928d942220b1ca2275e59a3817
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="54259-102">Audio/Video-Edgeserver (A/V) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54259-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54259-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="54259-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="54259-p101">Der A/V-Edgeserverdienst bietet eine Möglichkeit für Ihre internen Benutzer (in Ihrem Organisationsnetzwerk angemeldete Benutzer), Audio- und Videodateien für externe Benutzer (nicht in Ihrem Organisationsnetzwerk angemeldete Benutzer) freizugeben. Zusätzlich zu Audio und Video bietet der A/V-Edgedienst beispielsweise Unterstützung für die Desktopfreigabe und die Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="54259-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="54259-p102">Der A/V-Edgeserverdienst wird primär durch die Verwendung der A/V-Edge-Konfiguration verwaltet. Mit diesen Einstellungen können Sie die maximale zuzuweisende Bandbreite pro Port und Benutzer verwalten und den Zeitraum definieren, in dem das Authentifizierungstoken verwendet werden kann, bevor es erneuert werden muss. A/V-Edge-Konfigurationseinstellungen können auf Standorte oder einzelne A/V-Edgeserver angewendet werden. Verwenden Sie beim Bestimmen der zu bevorzugenden Einstellungsauflistung die folgende Anleitung:</span><span class="sxs-lookup"><span data-stu-id="54259-p102">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed. A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers. When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="54259-109">Auf Dienstebene konfigurierte Einstellungen (d. h. auf einem einzelnen Server) haben die höchste Priorität.</span><span class="sxs-lookup"><span data-stu-id="54259-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="54259-p103">Auf Standortebene zugewiesene Einstellungen haben Vorrang vor den global zugewiesenen Einstellungen. Auf Dienstebene vorgenommene Einstellungen ersetzen jedoch ebenfalls auf Standortebene vorgenommene Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="54259-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="54259-112">Einstellungen auf globaler Ebene werden nur verwendet, wenn auf dem einzelnen Server keine auf Dienstebene vorgenommenen Einstellungen konfiguriert wurden und wenn keine auf Standortebene vorgenommenen Einstellungen für den Standort, wo sich der Server befindet, vorliegen.</span><span class="sxs-lookup"><span data-stu-id="54259-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="54259-113">Die A/V-Edgedienst kann nur mit lync Server PowerShell und den CsAVEdgeConfiguration-Cmdlets verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="54259-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="54259-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="54259-114">In This Section</span></span>

  - [<span data-ttu-id="54259-115">Zurückgeben von A/V-Edgeserver Konfigurationsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54259-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="54259-116">Erstellen oder Ändern einer Sammlung von a/V-Edgeserver Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54259-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="54259-117">Löschen einer vorhandenen Auflistung von A/V-Edgeserver Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54259-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


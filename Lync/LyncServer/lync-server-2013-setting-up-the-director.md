---
title: 'Lync Server 2013: Einrichten des Directors'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18de0fe7b06bbeed714aca444e75086fba9579e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="5c592-102">Einrichten des Directors in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c592-102">Setting up the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c592-103">_**Letztes Änderungsdatum des Themas:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="5c592-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="5c592-104">Wenn Sie den Zugriff für externe Benutzer durch die Bereitstellung von Edge-Servern aktivieren, besteht eine Möglichkeit darin, einen Director bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5c592-104">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="5c592-105">Bei einem Director handelt es sich um einen Server mit Microsoft lync Server 2013, der Benutzeranforderungen authentifiziert, jedoch keine Benutzerkonten zu Hause verwendet.</span><span class="sxs-lookup"><span data-stu-id="5c592-105">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="5c592-106">Nun ist dies keine Voraussetzung, aber es ist sehr hilfreich, wenn Sie sich um die Leistung sorgen und die Optimierung von Authentifizierungsanforderungen unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="5c592-106">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="5c592-107">Wenn Sie entscheiden, dass dies eine gute Idee für Ihre Organisation ist, sind die Schritte zum Einrichten eines Director-oder Director-Pools mit dem Einrichten eines Enterprise Edition-Front-End-Pools oder eines Standard Edition-Servers vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="5c592-107">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="5c592-108">Nachdem Sie die Directors in Topology Builder definiert haben, müssen Sie die Schritte in diesem Abschnitt ausführen.</span><span class="sxs-lookup"><span data-stu-id="5c592-108">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5c592-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5c592-109">In This Section</span></span>

  - [<span data-ttu-id="5c592-110">Installieren des lokalen Konfigurationsspeichers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c592-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="5c592-111">Installieren von Lync Server 2013 auf dem Director</span><span class="sxs-lookup"><span data-stu-id="5c592-111">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="5c592-112">Konfigurieren von Zertifikaten für den Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c592-112">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="5c592-113">Starten von Diensten auf dem Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c592-113">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="5c592-114">Testen des Directors in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c592-114">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="5c592-115">Konfigurieren der automatischen Clientanmeldung zur Verwendung des Directors in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c592-115">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


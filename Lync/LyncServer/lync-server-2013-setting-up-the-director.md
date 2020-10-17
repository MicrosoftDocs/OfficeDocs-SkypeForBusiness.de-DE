---
title: 'Lync Server 2013: Einrichten des Directors'
description: 'Lync Server 2013: Einrichten des Directors.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b917000dec6d30fdec2963ff1e464fbb9a70805
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554111"
---
# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="6a405-103">Einrichten des Directors in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a405-103">Setting up the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a405-104">_**Letztes Änderungsstand des Themas:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="6a405-104">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="6a405-105">Wenn Sie den Zugriff für externe Benutzer durch die Bereitstellung von Edge-Servern aktivieren, besteht die Möglichkeit, einen Director bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6a405-105">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="6a405-106">Bei einem Director handelt es sich um einen Server mit Microsoft lync Server 2013, der Benutzeranforderungen authentifiziert, jedoch keine Benutzerkonten zu Hause ausführt.</span><span class="sxs-lookup"><span data-stu-id="6a405-106">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="6a405-107">Nun ist dies keine Voraussetzung, aber es ist sehr hilfreich, wenn Sie sich Sorgen um die Leistung machen und die Optimierung von Authentifizierungsanforderungen erleichtern möchten.</span><span class="sxs-lookup"><span data-stu-id="6a405-107">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="6a405-108">Wenn Sie entscheiden, dass dies eine gute Idee für Ihre Organisation ist, ähneln die Schritte zum Einrichten eines Directors oder Directorpool dem Einrichten einer Enterprise Edition-Front-End-Pool oder eines Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="6a405-108">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="6a405-109">Nachdem Sie Ihre (n) Directors im Topologie-Generator definiert haben, müssen Sie die Schritte in diesem Abschnitt durchführen.</span><span class="sxs-lookup"><span data-stu-id="6a405-109">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6a405-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6a405-110">In This Section</span></span>

  - [<span data-ttu-id="6a405-111">Installieren des lokalen Konfigurationsspeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a405-111">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="6a405-112">Installieren von Lync Server 2013 auf dem Director</span><span class="sxs-lookup"><span data-stu-id="6a405-112">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="6a405-113">Konfigurieren von Zertifikaten für den Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a405-113">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="6a405-114">Starten von Diensten auf dem Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a405-114">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="6a405-115">Testen des Directors in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a405-115">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="6a405-116">Konfigurieren der automatischen Client Sign-In für die Verwendung des Directors in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a405-116">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Bereitstellen der Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Archiving
ms:assetid: a89edd16-12d5-4602-ad2f-194b47d1188e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205147(v=OCS.15)
ms:contentKeyID: 48185031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86b1394df9bb52502e1e0c605bedb05a0579042e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="25405-102">Bereitstellen der Archivierung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25405-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25405-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="25405-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="25405-104">Lync Server 2013 bietet eine Lösung zum Archivieren von Instant Messaging (im)-Inhalten und Konferenz Kommunikationen in lync Server.</span><span class="sxs-lookup"><span data-stu-id="25405-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="25405-105">Sie können Archivierungsunterstützung implementieren, indem Sie den Archivierungsspeicher mit Exchange 2013-Speicher, mithilfe von SQL Server-Datenbanken für die Speicherung von lync Server 2013-Archivierungsdaten oder mithilfe von lync Server 2013 und Exchange 2013-Speicher integrieren.</span><span class="sxs-lookup"><span data-stu-id="25405-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="25405-106">Sie steuern, wie Daten mithilfe von Richtlinien und Archivierungs Konfigurationen archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="25405-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="25405-107">Ausführliche Informationen finden Sie unter [Planen der Archivierung in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation und [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="25405-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="25405-108">Mit den Informationen in diesem Abschnitt können Sie die Archivierung zunächst einrichten und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="25405-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="25405-109">Nach der Bereitstellung können Sie die Archivierungseinstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="25405-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="25405-110">Ausführliche Informationen dazu, wie Sie die Archivierungsunterstützung für die tägliche Verwaltung implementieren oder neue Anforderungen in Ihrer Organisation erfüllen, finden Sie unter [Verwalten der lync Server 2013-Archivierung](lync-server-2013-managing-archiving.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="25405-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="25405-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="25405-111">In This Section</span></span>

  - [<span data-ttu-id="25405-112">Funktionsweise der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25405-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="25405-113">Prüfliste zur Bereitstellung für die Archivierung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25405-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="25405-114">Einrichten von Systemen und Infrastruktur für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25405-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="25405-115">Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen lync Server 2013-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="25405-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="25405-116">Konfigurieren der Unterstützung für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25405-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


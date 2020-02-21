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
ms.openlocfilehash: 1d31a4bdf75b649dec1d18a834335b0d47a69a3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="8ef0a-102">Bereitstellen der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ef0a-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ef0a-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8ef0a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8ef0a-104">Lync Server 2013 bietet eine Lösung zum Archivieren von Chatnachrichten (Instant Messaging) und Konferenzkommunikation in lync Server.</span><span class="sxs-lookup"><span data-stu-id="8ef0a-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="8ef0a-105">Sie können die Archivierungsunterstützung implementieren, indem Sie den Archivierungsspeicher in Exchange 2013 Speicher integrieren, indem Sie SQL Server Datenbanken zum Speichern von lync Server 2013 Archivierungsdaten verwenden oder sowohl lync Server 2013 als auch Exchange 2013 Speicher verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ef0a-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="8ef0a-106">Sie steuern, wie Daten mithilfe von Richtlinien und Archivierungs Konfigurationen archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="8ef0a-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="8ef0a-107">Ausführliche Informationen finden Sie unter [Planning for Archiving in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation und der Funktions [Weise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8ef0a-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="8ef0a-108">Sie können die Informationen in diesem Abschnitt verwenden, um die Archivierung zunächst einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8ef0a-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="8ef0a-109">Nach der Bereitstellung können Sie die Archivierungseinstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="8ef0a-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="8ef0a-110">Ausführliche Informationen zur Implementierung der Archivierungsunterstützung für die tägliche Verwaltung oder zur Erfüllung neuer Anforderungen in Ihrer Organisation finden Sie unter [Managing lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8ef0a-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8ef0a-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8ef0a-111">In This Section</span></span>

  - [<span data-ttu-id="8ef0a-112">Funktionsweise der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ef0a-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="8ef0a-113">Prüfliste zur Bereitstellung für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ef0a-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="8ef0a-114">Einrichten von Systemen und Infrastruktur für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ef0a-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="8ef0a-115">Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen lync Server 2013-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="8ef0a-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="8ef0a-116">Konfigurieren der Unterstützung für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ef0a-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Phase 4: Zusammenführen von Topologien'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 4: Merge topologies'
ms:assetid: 81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205044(v=OCS.15)
ms:contentKeyID: 48184668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b66ce3c7fa5560bc241ddfa6b0a2f56832aafec
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523452"
---
# <a name="phase-4-merge-topologies"></a><span data-ttu-id="b8fdc-102">Phase 4: Zusammenführen von Topologien</span><span class="sxs-lookup"><span data-stu-id="b8fdc-102">Phase 4: Merge topologies</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8fdc-103">_**Letztes Änderungsstand des Themas:** 2012-03-29_</span><span class="sxs-lookup"><span data-stu-id="b8fdc-103">_**Topic Last Modified:** 2012-03-29_</span></span>

<span data-ttu-id="b8fdc-104">In den folgenden Themen werden die Schritte beschrieben, die zum Zusammenführen Ihrer Microsoft Office Communications Server 2007 R2 Pools mit Microsoft lync Server 2013 Pools erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b8fdc-104">The following topics outline the steps needed to merge your Microsoft Office Communications Server 2007 R2 pools to Microsoft Lync Server 2013 pools.</span></span> <span data-ttu-id="b8fdc-105">Verwenden Sie zunächst den Zusammenführungs-Assistenten des Topologie-Generators, um Topologieinformationen zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="b8fdc-105">First, you use the Topology Builder Merge wizard to merge topology information.</span></span> <span data-ttu-id="b8fdc-106">Dieses Tool sammelt Informationen zu Ihrer Office Communications Server 2007 R2 Umgebung, einschließlich Edgeserver Informationen, und veröffentlicht diese Informationen in einer Datenbank, die für lync Server 2013 freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b8fdc-106">This tool collects information about your Office Communications Server 2007 R2 environment, including Edge Server information, and publishes that information to a database shared with Lync Server 2013.</span></span> <span data-ttu-id="b8fdc-107">Nachdem Sie die zusammengeführte Topologie veröffentlicht haben, wird der Topologie-Generator verwendet, um die Office Communications Server 2007 R2 Topologieinformationen sowie Informationen zur neu bereitgestellten lync Server 2013 Topologie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b8fdc-107">After you publish the merged topology, Topology Builder is used to view the Office Communications Server 2007 R2 topology information and information about the newly deployed Lync Server 2013 topology.</span></span> <span data-ttu-id="b8fdc-108">Importieren Sie die Richtlinien und Konfigurationseinstellungen abschließend mithilfe der Lync Server Management Shell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b8fdc-108">Finally, you use Lync Server Management Shell cmdlets to import policies and configuration settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b8fdc-109">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="b8fdc-109">In This Section</span></span>

  - [<span data-ttu-id="b8fdc-110">Installieren des WMI-abwärts Kompatibilitätspakets</span><span class="sxs-lookup"><span data-stu-id="b8fdc-110">Install WMI Backward Compatibility package</span></span>](install-wmi-backward-compatibility-package.md)

  - [<span data-ttu-id="b8fdc-111">Zusammenführen mithilfe des Zusammenführungs-Assistenten für Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="b8fdc-111">Merge using Topology Builder Merge wizard</span></span>](merge-using-topology-builder-merge-wizard.md)

  - [<span data-ttu-id="b8fdc-112">Importieren von Richtlinien und Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b8fdc-112">Import policies and settings</span></span>](import-policies-and-settings.md)

  - [<span data-ttu-id="b8fdc-113">Überprüfen der Topologieinformationen</span><span class="sxs-lookup"><span data-stu-id="b8fdc-113">Verify topology information</span></span>](verify-topology-information.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Exportieren und Importieren der VoIP-Routingkonfiguration'
description: 'Lync Server 2013: Exportieren und Importieren der VoIP-Routingkonfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a94a9c02672debae9f5b30e3a1a96856050d6ab1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564771"
---
# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="80612-103">Exportieren und Importieren der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80612-103">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80612-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="80612-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="80612-105">Wenn Sie Ihre VoIP-Routingkonfiguration ohne Veröffentlichung speichern möchten, führen Sie die folgenden Schritte aus, um die lync Server-Systemsteuerung Konfigurations Export-und Importbefehle zu verwenden, um eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="80612-105">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="80612-106">Wenn Sie eine VoIP-Routing Konfigurationsdatei (. vcfg) importieren, Änderungen an der VoIP-Routingkonfiguration auf dem Server in der Zwischenzeit vorgenommen wurden, geben die Seiten in der Gruppe **VoIP-Routing** in lync Server-Systemsteuerung an, dass keine Commits für Änderungen an der VoIP-Weiterleitung vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="80612-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="80612-107">Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.</span><span class="sxs-lookup"><span data-stu-id="80612-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="80612-108">Wenn Sie Änderungen an den Einstellungen auf einer beliebigen Seite innerhalb der <STRONG>VoIP-Routing</STRONG> Gruppe vorgenommen haben, werden die Änderungen in der exportierten VoIP-Konfigurationsdatei (. vcfg) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="80612-108">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="80612-109">Auf diese Weise können Sie Konfigurationsänderungen für das VoIP-Routing in mehreren lync Server-Systemsteuerung Sitzungen vornehmen, bevor Sie die Änderungen veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="80612-109">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="80612-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="80612-110">In This Section</span></span>

  - [<span data-ttu-id="80612-111">Exportieren einer VoIP-Route-Konfigurationsdatei in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80612-111">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="80612-112">Importieren einer VoIP-Route-Konfigurationsdatei in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80612-112">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="80612-113">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="80612-113">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


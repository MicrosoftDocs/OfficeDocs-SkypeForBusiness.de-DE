---
title: 'Lync Server 2013: Exportieren einer Konfigurationsdatei für die VoIP-Route'
description: 'Lync Server 2013: Exportieren einer Konfigurationsdatei für die VoIP-Route.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bf342e11be41015df3cfd76f6a875381cb8b64
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564791"
---
# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="8f4d8-103">Exportieren einer VoIP-Route-Konfigurationsdatei in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f4d8-103">Export a voice route configuration file in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f4d8-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8f4d8-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8f4d8-105">Wenn Sie Ihre VoIP-Routingkonfiguration ohne Veröffentlichung speichern möchten, führen Sie die folgenden Schritte aus, um die lync Server-Systemsteuerung Konfigurations Export-und Importbefehle zu verwenden, um eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8f4d8-105">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="8f4d8-106">Wenn Sie eine VoIP-Routing Konfigurationsdatei (. vcfg) importieren, Änderungen an der VoIP-Routingkonfiguration auf dem Server in der Zwischenzeit vorgenommen wurden, geben die Seiten in der Gruppe **VoIP-Routing** in lync Server-Systemsteuerung an, dass keine Commits für Änderungen an der VoIP-Weiterleitung vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="8f4d8-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="8f4d8-107">Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.</span><span class="sxs-lookup"><span data-stu-id="8f4d8-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="8f4d8-108">Wenn Sie Änderungen an den Einstellungen auf einer beliebigen Seite innerhalb der Gruppe vorgenommen haben, werden die Änderungen in der exportierten VoIP-Konfigurationsdatei (. vcfg) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8f4d8-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="8f4d8-109">Auf diese Weise können Sie Konfigurationsänderungen für das VoIP-Routing in mehreren Sitzungen vornehmen, bevor Sie die Änderungen veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="8f4d8-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="8f4d8-110">So exportieren Sie eine VoIP-Routingkonfiguration</span><span class="sxs-lookup"><span data-stu-id="8f4d8-110">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="8f4d8-111">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="8f4d8-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8f4d8-112">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8f4d8-112">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8f4d8-113">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8f4d8-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8f4d8-114">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8f4d8-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8f4d8-115">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="8f4d8-115">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="8f4d8-116">Klicken Sie im Menü **Aktionen** auf **Konfiguration exportieren**.</span><span class="sxs-lookup"><span data-stu-id="8f4d8-116">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="8f4d8-117">Geben Sie einen Speicherort und Dateinamen an, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8f4d8-117">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8f4d8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f4d8-118">See Also</span></span>


[<span data-ttu-id="8f4d8-119">Importieren einer VoIP-Route-Konfigurationsdatei in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f4d8-119">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


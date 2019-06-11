---
title: 'Lync Server 2013: Exportieren einer sprach Routen-Konfigurationsdatei'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d61bb4dfda9aa91191515f60b0a26b2665f31421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="dd19f-102">Exportieren einer sprach Routen-Konfigurationsdatei in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd19f-102">Export a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd19f-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dd19f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dd19f-104">Wenn Sie Ihre sprach Routingkonfiguration speichern möchten, ohne Sie zu veröffentlichen, führen Sie die folgenden Schritte aus, um die Konfigurations Export-und-Importbefehle in lync Server Control Panel zu verwenden, um eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="dd19f-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="dd19f-105">Wenn Sie eine sprach Routing-Konfigurationsdatei (. vcfg) importieren, aber Änderungen an der sprach Routingkonfiguration auf dem Server in der Zwischenzeit vorgenommen wurden, zeigen die Seiten in der Gruppe **VoIP-Routing** in der lync Server-Systemsteuerung an, dass es nicht festgeschriebene Änderungen an der sprach Weiterleitung.</span><span class="sxs-lookup"><span data-stu-id="dd19f-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="dd19f-106">Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.</span><span class="sxs-lookup"><span data-stu-id="dd19f-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="dd19f-107">Wenn Sie Änderungen an den Einstellungen auf einer beliebigen Seite innerhalb der Gruppe vorgenommen haben, werden die Änderungen in der exportierten sprach Konfigurationsdatei (vcfg) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dd19f-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="dd19f-108">So können Sie während mehrerer Sitzungen Änderungen an der sprach Routingkonfiguration vornehmen, bevor Sie die Änderungen veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="dd19f-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="dd19f-109">So exportieren Sie eine VoIP-Routingkonfiguration</span><span class="sxs-lookup"><span data-stu-id="dd19f-109">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="dd19f-110">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="dd19f-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="dd19f-111">Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="dd19f-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dd19f-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dd19f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dd19f-113">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dd19f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dd19f-114">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="dd19f-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="dd19f-115">Klicken Sie im Menü **Aktionen** auf **Konfiguration exportieren**.</span><span class="sxs-lookup"><span data-stu-id="dd19f-115">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="dd19f-116">Geben Sie einen Speicherort und Dateinamen an und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dd19f-116">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dd19f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd19f-117">See Also</span></span>


[<span data-ttu-id="dd19f-118">Importieren einer VoIP-Routenkonfigurationsdatei in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd19f-118">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


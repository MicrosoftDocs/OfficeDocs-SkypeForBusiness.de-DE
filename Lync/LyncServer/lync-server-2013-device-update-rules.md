---
title: 'Lync Server 2013: Regeln für Geräte Updates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cce4b0be575665d23b2b09126905fc35791f61ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="c449b-102">Geräteaktualisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c449b-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c449b-103">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="c449b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="c449b-104">In regelmäßigen Abständen veröffentlicht Microsoft eine neue Gruppe von Gerätefirmware-Updates für lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="c449b-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="c449b-105">*Geräteaktualisierungsregeln* verknüpfen Firmware-Updates mit Hardwaregeräten – Telefonen und anderen Geräten, auf denen lync Phone Edition ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c449b-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="c449b-106">Wenn Sie die neuesten Regeln für Geräte Updates abrufen möchten, wechseln Sie zur Seite Hilfe und Support auf der Microsoft-Website, und suchen Sie nach "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="c449b-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="c449b-107">Laden Sie das Updatepaket herunter, und extrahieren Sie die Dateien in einen Ordner auf dem Computer, auf dem die Updates hochgeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c449b-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="c449b-108">Nachdem die Dateien extrahiert wurden, importieren Sie die geräteaktualisierungsregeln, die in der extrahierten Datei gefunden wurden. CAB-Datei (mit dem Namen ucupdates. cab).</span><span class="sxs-lookup"><span data-stu-id="c449b-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="c449b-109">Verwenden Sie dann die lync Server-Systemsteuerung oder Windows PowerShell-Cmdlets, um diese Regeln für die Geräte Ihrer Organisation anzuzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c449b-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="c449b-110">In den folgenden Themen erfahren Sie, wie Sie geräteaktualisierungsregeln importieren, anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="c449b-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c449b-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c449b-111">In This Section</span></span>

  - [<span data-ttu-id="c449b-112">Anzeigen von Informationen zu Geräte Update Regeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c449b-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="c449b-113">Importieren von geräteaktualisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c449b-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="c449b-114">Genehmigen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c449b-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="c449b-115">Entfernen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c449b-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="c449b-116">Zurücksetzen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c449b-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="c449b-117">Wiederherstellen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c449b-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Geräte Update Regeln'
description: 'Lync Server 2013: geräteaktualisierungsregeln.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd6d34c290f4a08f67143294fcc5dd18e1acf9d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565961"
---
# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="51e01-103">Geräteaktualisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51e01-103">Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51e01-104">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="51e01-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="51e01-105">In regelmäßigen Abständen veröffentlicht Microsoft eine Reihe neuer Gerätefirmware-Updates für lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="51e01-105">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="51e01-106">Durch *geräteaktualisierungsregeln* werden Firmware-Updates mit Hardwaregeräten (Telefone und andere Geräte mit lync Phone Edition zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="51e01-106">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="51e01-107">Um die neuesten Regeln für Geräte Updates abzurufen, navigieren Sie auf der Microsoft-Website zur Hilfe-und Support Seite, und suchen Sie nach "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="51e01-107">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="51e01-108">Laden Sie das Updatepaket herunter, und extrahieren Sie die Dateien in einen Ordner auf dem Computer, auf dem die Updates hochgeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="51e01-108">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="51e01-109">Nachdem die Dateien extrahiert wurden, importieren Sie die geräteaktualisierungsregeln, die in der extrahierten gefunden wurden. CAB-Datei (mit dem Namen UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="51e01-109">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="51e01-110">Verwenden Sie dann die lync Server-Systemsteuerung-oder Windows PowerShell-Cmdlets, um diese Regeln für die Geräte Ihrer Organisation anzuzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="51e01-110">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="51e01-111">In den folgenden Themen erfahren Sie, wie Sie geräteaktualisierungsregeln importieren, anzeigen und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="51e01-111">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="51e01-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="51e01-112">In This Section</span></span>

  - [<span data-ttu-id="51e01-113">Anzeigen von Informationen zu geräteaktualisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51e01-113">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="51e01-114">Importieren von geräteaktualisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51e01-114">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="51e01-115">Genehmigen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51e01-115">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="51e01-116">Entfernen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51e01-116">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="51e01-117">Zurücksetzen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51e01-117">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="51e01-118">Wiederherstellen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51e01-118">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


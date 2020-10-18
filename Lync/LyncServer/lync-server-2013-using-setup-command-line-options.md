---
title: 'Lync Server 2013: Verwenden von Setup-Befehlszeilenoptionen'
description: 'Lync Server 2013: Verwenden von Setup-Befehlszeilenoptionen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15c3490ead090766462ce83cb13ffe62355032cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580241"
---
# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="a297d-103">Verwenden von Setup-Befehlszeilenoptionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a297d-103">Using Setup command-line options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a297d-104">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a297d-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a297d-p101">Die Befehlszeile von "Setup.exe" wird nur für wenige Vorgänge des Office-Setups verwendet. Anstelle der Setup-Befehlszeilenoptionen benutzen Sie in der Regel das Office-Anpassungstool und die Datei "Config.xml", um Produkte einzurichten und Funktionen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="a297d-p101">The Setup.exe command line is used for very few operations in Office setup. Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="a297d-107">Die Befehlszeile der Office "Setup.exe" erkennt die in der folgenden Tabelle beschriebenen Befehlzeilenoptionen.</span><span class="sxs-lookup"><span data-stu-id="a297d-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="a297d-108">Optionen der Office Setup-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="a297d-108">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a297d-109">Option der Office Setup-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="a297d-109">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="a297d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a297d-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a297d-111">/admin</span><span class="sxs-lookup"><span data-stu-id="a297d-111">/admin</span></span></p></td>
<td><p><span data-ttu-id="a297d-112">Führt das Office-Anpassungstool aus, um eine Setupanpassungsdatei (.msp-Datei) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a297d-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297d-113">/adminfile [Pfad]</span><span class="sxs-lookup"><span data-stu-id="a297d-113">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="a297d-p102">Wendet die angegebene Setupanpassungsdatei auf die Installation an. Sie können einen Pfad zu einer bestimmten Anpassungsdatei (.msp-Datei) oder zu dem Ordner angeben, in dem Sie Anpassungsdateien speichern.</span><span class="sxs-lookup"><span data-stu-id="a297d-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297d-116">/config [Pfad]</span><span class="sxs-lookup"><span data-stu-id="a297d-116">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="a297d-117">Gibt die Config.xml Datei an, die von Setup während der Installation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a297d-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="a297d-118">Verwenden Sie die Option/config, um die Config.xml Datei anzugeben, die Sie für lync 2013 Installationen angepasst haben, beispielsweise: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="a297d-118">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297d-119">/modify Lync</span><span class="sxs-lookup"><span data-stu-id="a297d-119">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="a297d-p104">Wird mit einer geänderten Config.xml-Datei verwendet, um das Setup im Wartungsmodus auszuführen und Änderungen an einer vorhandenen Office-Installation durchzuführen. Sie können die Option "/modify" z. B. nutzen, um Lync-Funktionen hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a297d-p104">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation. For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297d-122">/repair Lync</span><span class="sxs-lookup"><span data-stu-id="a297d-122">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="a297d-123">Führt Setup auf dem Computer des Benutzers aus, um Lync zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="a297d-123">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297d-124">/uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="a297d-124">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="a297d-125">Führt Setup aus, um Lync vom Computer des Benutzers zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a297d-125">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a297d-126">Ausführliche Informationen zur Verwendung der Setup-Befehlszeilenoptionen finden Sie unter <https://go.microsoft.com/fwlink/p/?linkid=267515> .</span><span class="sxs-lookup"><span data-stu-id="a297d-126">For details about using the setup command-line options, see <https://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


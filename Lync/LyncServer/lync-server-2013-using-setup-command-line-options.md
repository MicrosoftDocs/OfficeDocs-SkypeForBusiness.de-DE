---
title: 'Lync Server 2013: Verwenden von Setup-Befehlszeilenoptionen'
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
ms.openlocfilehash: 0fcf3637ac0d334c2d22ef714891ea0544ee1a6d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="638c0-102">Verwenden von Setup-Befehlszeilenoptionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="638c0-102">Using Setup command-line options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="638c0-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="638c0-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="638c0-p101">Die Befehlszeile von "Setup.exe" wird nur für wenige Vorgänge des Office-Setups verwendet. Anstelle der Setup-Befehlszeilenoptionen benutzen Sie in der Regel das Office-Anpassungstool und die Datei "Config.xml", um Produkte einzurichten und Funktionen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="638c0-p101">The Setup.exe command line is used for very few operations in Office setup. Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="638c0-106">Die Befehlszeile der Office "Setup.exe" erkennt die in der folgenden Tabelle beschriebenen Befehlzeilenoptionen.</span><span class="sxs-lookup"><span data-stu-id="638c0-106">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="638c0-107">Optionen der Office Setup-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="638c0-107">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="638c0-108">Option der Office Setup-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="638c0-108">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="638c0-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="638c0-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="638c0-110">/admin</span><span class="sxs-lookup"><span data-stu-id="638c0-110">/admin</span></span></p></td>
<td><p><span data-ttu-id="638c0-111">Führt das Office-Anpassungstool aus, um eine Setupanpassungsdatei (.msp-Datei) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="638c0-111">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="638c0-112">/adminfile [Pfad]</span><span class="sxs-lookup"><span data-stu-id="638c0-112">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="638c0-p102">Wendet die angegebene Setupanpassungsdatei auf die Installation an. Sie können einen Pfad zu einer bestimmten Anpassungsdatei (.msp-Datei) oder zu dem Ordner angeben, in dem Sie Anpassungsdateien speichern.</span><span class="sxs-lookup"><span data-stu-id="638c0-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="638c0-115">/config [Pfad]</span><span class="sxs-lookup"><span data-stu-id="638c0-115">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="638c0-116">Gibt die Datei config. XML an, die von Setup während der Installation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="638c0-116">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="638c0-117">Verwenden Sie die/config-Option, um die Datei config. XML anzugeben, die Sie für lync 2013-Installationen angepasst haben, beispielsweise:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="638c0-117">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="638c0-118">/Modify lync</span><span class="sxs-lookup"><span data-stu-id="638c0-118">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="638c0-119">Wird mit einer geänderten config.xml-Datei verwendet, um Setup im Wartungsmodus auszuführen und Änderungen an einer vorhandenen Office-Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="638c0-119">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="638c0-120">So können Sie beispielsweise die Option/MODIFY verwenden, um lync-Features hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="638c0-120">For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="638c0-121">/Repair lync</span><span class="sxs-lookup"><span data-stu-id="638c0-121">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="638c0-122">Führt das Setup auf dem Computer des Benutzers aus, um lync zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="638c0-122">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="638c0-123">/Uninstall lync</span><span class="sxs-lookup"><span data-stu-id="638c0-123">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="638c0-124">Führt das Setup aus, um lync vom Computer des Benutzers zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="638c0-124">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="638c0-125">Ausführliche Informationen zur Verwendung der Befehlszeilenoptionen für Setup finden Sie <http://go.microsoft.com/fwlink/p/?linkid=267515>unter.</span><span class="sxs-lookup"><span data-stu-id="638c0-125">For details about using the setup command-line options, see <http://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


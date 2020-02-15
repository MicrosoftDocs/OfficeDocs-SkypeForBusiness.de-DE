---
title: 'Lync Server 2013: lync Server-Cmdlets nach Kategorie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5db33e3d41bca0a3d14361b6d7bda254d43d19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="1eaa6-102">Lync Server 2013-Cmdlets nach Kategorie</span><span class="sxs-lookup"><span data-stu-id="1eaa6-102">Lync Server 2013 cmdlets by category</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eaa6-103">_**Letztes Änderungsstand des Themas:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="1eaa6-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="1eaa6-104">Microsoft lync Server 2013 ist mit fast 550 Cmdlets ausgestattet, die Administratoren das Verwalten von lync Server über die Befehlszeile ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1eaa6-104">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="1eaa6-105">Sie greifen auf die Cmdlets aus dem lync Server-Verwaltungsshell zu.</span><span class="sxs-lookup"><span data-stu-id="1eaa6-105">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="1eaa6-106">Sie können Hilfeinformationen zu einem Cmdlet direkt über die Befehlszeile abrufen, indem Sie einen dem folgenden ähnlichen Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="1eaa6-106">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="1eaa6-107">Mit dem oben genannten Befehl rufen Sie alle verfügbaren Hilfeinformationen zum Cmdlet **New-CsVoicePolicy** ab.</span><span class="sxs-lookup"><span data-stu-id="1eaa6-107">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="1eaa6-108">Ersetzen Sie den Verweis auf **New-CsVoicePolicy** durch den Namen des Cmdlets, zu dem Sie Hilfeinformationen abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="1eaa6-108">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="1eaa6-109">Geben Sie an der lync Server-Verwaltungsshell-Eingabeaufforderung Folgendes ein, um eine vollständige Liste der für die Verwaltung von Microsoft lync Server 2013 verfügbaren Cmdlets abzurufen:</span><span class="sxs-lookup"><span data-stu-id="1eaa6-109">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="1eaa6-p103">Wenn Sie unsicher sind, welche Cmdlets Sie benötigen, finden Sie nachstehend eine nach Kategorien sortierte Liste der Cmdlets sowie die zugehörigen Hilfethemen. Einige der Cmdlets werden in mehr als einer Kategorie aufgeführt. Dies ist beabsichtigt, da diese Cmdlets in verschiedenen Bereichen des Produkts eingesetzt werden. Nachfolgend finden Sie eine Liste der Kategorien:</span><span class="sxs-lookup"><span data-stu-id="1eaa6-p103">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics. You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product. The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1eaa6-113">Die Skype for Business-Cmdlet-Referenz wurde zu docs.Microsoft.com verschoben.</span><span class="sxs-lookup"><span data-stu-id="1eaa6-113">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="1eaa6-114">Durch Klicken auf die unten aufgeführten Links gelangen Sie zur neuen docs.Microsoft.com-Seite.</span><span class="sxs-lookup"><span data-stu-id="1eaa6-114">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="1eaa6-115">Der Inhalt ist nun Open sourced und für Community-Beiträge über GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1eaa6-115">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="1eaa6-116">Möchten Sie einen Beitrag leisten?</span><span class="sxs-lookup"><span data-stu-id="1eaa6-116">Interested in contributing?</span></span> <span data-ttu-id="1eaa6-117">Lesen Sie die Readme-Datei im Repo hier:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="1eaa6-117">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1eaa6-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1eaa6-118">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eaa6-119"><a href="lync-server-2013-user-management-cmdlets.md">Cmdlets für die Benutzerverwaltung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-119"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1eaa6-120"><a href="lync-server-2013-voice-application-cmdlets.md">Cmdlets für die VoIP-Anwendung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-120"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eaa6-121"><a href="lync-server-2013-client-management-cmdlets.md">Cmdlets für die Client Verwaltung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-121"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1eaa6-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Erweiterte Enterprise-VoIP-Cmdlets in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eaa6-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">Cmdlets für Sofortnachrichten und Anwesenheitsinformationen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1eaa6-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Cmdlets für PSTN-Konnektivität in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eaa6-125"><a href="lync-server-2013-conferencing-cmdlets.md">Konferenz-Cmdlets in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-125"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1eaa6-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Cmdlets für Telefone und Geräte in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eaa6-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Cmdlets für die Infrastruktur und Bereitstellung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1eaa6-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Cmdlets für Migration und Koexistenz in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eaa6-129"><a href="lync-server-2013-security-cmdlets.md">Sicherheits-Cmdlets in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-129"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1eaa6-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server-Verwaltungsshell Konfigurations-Cmdlets in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eaa6-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Cmdlets für Server Rollen und Dienste in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1eaa6-132"><a href="lync-server-2013-mobility-cmdlets.md">Mobilitäts-Cmdlets in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-132"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eaa6-133"><a href="lync-server-2013-application-management-cmdlets.md">Cmdlets für die Anwendungsverwaltung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-133"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1eaa6-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Cmdlets für beständigen Chat Server in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eaa6-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Cmdlets für den Verbund und den externen Zugriff in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1eaa6-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Cmdlets für die zentralisierte Protokollierung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eaa6-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise-VoIP-Cmdlets in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1eaa6-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1eaa6-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eaa6-138">See Also</span></span>


[<span data-ttu-id="1eaa6-139">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="1eaa6-139">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Aktualisieren der Outlook-Aktivierungs Liste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c7ee75e70b52a4edd01230fe10aeb46f6e6e40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="5cefc-102">Aktualisieren der Outlook-Aktivierungs Liste in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5cefc-102">Updating the Outlook enable list in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cefc-103">_**Letztes Änderungsdatum des Themas:** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="5cefc-103">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="5cefc-104">Sie können sicherstellen, dass das Online Besprechungs-Add-in für Microsoft lync 2013 für Benutzer immer aktiviert bleibt, indem Sie eine Richtlinie erstellen, die Sie in die Add-in-Verwaltungsliste für Outlook einfügt.</span><span class="sxs-lookup"><span data-stu-id="5cefc-104">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="5cefc-105">Die Richtlinie für Add-in-Verwaltungs Listen ist in den Office administrative Template-Dateien für die Gruppenrichtlinien-Verwaltungskonsole enthalten.</span><span class="sxs-lookup"><span data-stu-id="5cefc-105">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="5cefc-106">Sie erstellt einen Registrierungsschlüssel unter HKCU\\-\\Software\\Richtlinien\\Microsoft\\Office\\15,0\\Outlook15 Resilienz\\-Add-in.</span><span class="sxs-lookup"><span data-stu-id="5cefc-106">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="5cefc-107">Sie können diesem Schlüssel einen Wert für die Datei "ucaddin. dll" hinzufügen und den Wert für "ucaddin. dll" so konfigurieren, dass er immer aktiviert ist, sodass Benutzer ihn nicht manuell deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="5cefc-107">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="5cefc-108">So fügen Sie der Outlook-Add-in-Liste ucaddin. dll hinzu</span><span class="sxs-lookup"><span data-stu-id="5cefc-108">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="5cefc-109">Fügen Sie dem Registrierungsschlüssel addinlist\\unter HKCU-Software\\Richtlinien\\,\\Microsoft\\Office\\15,0\\Outlook15-\\Flexibilitäts-Add-in, den folgenden Wert hinzu:</span><span class="sxs-lookup"><span data-stu-id="5cefc-109">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="5cefc-110">Registry Type = reg\_SZ</span><span class="sxs-lookup"><span data-stu-id="5cefc-110">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="5cefc-111">Name = ucaddin. dll</span><span class="sxs-lookup"><span data-stu-id="5cefc-111">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="5cefc-112">Wert = 1 (gibt an, dass das Add-in immer aktiviert ist und nicht vom Endbenutzer verwaltet werden kann)</span><span class="sxs-lookup"><span data-stu-id="5cefc-112">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


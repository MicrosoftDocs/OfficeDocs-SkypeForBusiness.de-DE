---
title: 'Lync Server 2013: Geräteaktualisierungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update Web service
ms:assetid: 036f473d-a131-431f-8051-76ccadc5cfba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994015(v=OCS.15)
ms:contentKeyID: 51803921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 509428b4cd0646e0993d6127bcee8a1f2182c11f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="71860-102">Geräteaktualisierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71860-102">Device Update Web service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71860-103">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="71860-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="71860-104">Lync Server enthält den Geräte Update-Webdienst, der automatisch als Teil der Webdienste Rolle installiert wird.</span><span class="sxs-lookup"><span data-stu-id="71860-104">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="71860-105">Mit diesem Dienst können Sie Updates von Microsoft herunterladen, testen und dann die Updates auf IP-Telefonen in Ihrer Organisation bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="71860-105">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="71860-106">Sie können den Dienst auch dazu verwenden, für Geräte ein Rollback auf vorherige Softwareversionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="71860-106">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="71860-107">Dieser Abschnitt enthält Informationen zum Verwalten des Geräteupdate-Webdiensts und zur Bereitstellung von Updates mithilfe von Geräte Aktualisierungs Protokollen, Regeln (lync Phone Edition verwendet *Regeln* zum Zuordnen von Firmware-Versionsupdates zu Hardwaregeräten) und Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="71860-107">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="71860-108">Ausführliche Informationen zum Prozess und zu den Features des Geräte Update-Webdiensts finden Sie unter [Updating Devices](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the lync Server 2010 TechNet Library.</span><span class="sxs-lookup"><span data-stu-id="71860-108">For details about the Device Update Web service process and features, see [Updating Devices](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="71860-109">(Beachten Sie, dass der Geräte Update-Webdienst wie alle lync Phone Edition-Komponenten mit lync Server 2013 genauso funktioniert wie mit lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="71860-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="71860-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="71860-110">In This Section</span></span>

  - [<span data-ttu-id="71860-111">Geräte Aktualisierungsprotokolle und-Dateien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71860-111">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="71860-112">Geräteaktualisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71860-112">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="71860-113">Konfigurationseinstellungen für Geräte Updates in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71860-113">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="71860-114">Anzeigen von Softwareupdates für Geräte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71860-114">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71860-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71860-115">See Also</span></span>


<span data-ttu-id="71860-116">[Tools und Dienste für die Verwaltung und Problembehandlung von Geräten](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="71860-116">[Tools and Services for Managing and Troubleshooting Devices](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


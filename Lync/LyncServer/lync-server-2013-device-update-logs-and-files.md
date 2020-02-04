---
title: 'Lync Server 2013: Geräte Aktualisierungsprotokolle und-Dateien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update logs and files
ms:assetid: f7f822b8-0a62-4ff2-a4cb-1ab1ed7503eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994090(v=OCS.15)
ms:contentKeyID: 51804004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170bafb3d00940995e8355c7775681c2af5fd078
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-logs-and-files-in-lync-server-2013"></a><span data-ttu-id="b14a6-102">Geräte Aktualisierungsprotokolle und-Dateien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b14a6-102">Device Update logs and files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b14a6-103">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="b14a6-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="b14a6-104">Geräte Aktualisierungsprotokolle enthalten wichtige Informationen, die Sie für die Verwaltung und Problembehandlung des Geräteupdate-Webdiensts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b14a6-104">Device update logs contain important information that you can use to manage and troubleshoot the Device Update Web service.</span></span> <span data-ttu-id="b14a6-105">Sie können ändern, was protokolliert wird, und Geräteprotokolle und Updates entfernen, die Sie nicht mehr benötigen oder nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="b14a6-105">You can change what is logged and remove device logs and updates that you don’t want or no longer need.</span></span> <span data-ttu-id="b14a6-106">In diesem Abschnitt wird beschrieben, wie Sie die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell verwenden können, um Protokollierungseinstellungen zu ändern, das Geräte Aktualisierungsprotokoll zu löschen oder Protokolldateien vom Server zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b14a6-106">This section describes how you can use Lync Server Control Panel or Lync Server Management Shell to modify logging settings, clear the device update log, or remove log files from the server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b14a6-107">Details zu Geräte Aktualisierungsprotokolldateien finden Sie unter <A href="http://technet.microsoft.com/en-us/library/gg398250(v=ocs.14).aspx">Protokolldatei Typen und Speicherorte</A> in der lync Server 2010 TechNet-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="b14a6-107">For details about device update log files, see <A href="http://technet.microsoft.com/en-us/library/gg398250(v=ocs.14).aspx">Log File Types and Locations</A> in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="b14a6-108">(Beachten Sie, dass der Geräte Update-Webdienst wie alle lync Phone Edition-Komponenten mit lync Server 2013 wie bei lync Server 2010 auf die gleiche Weise funktioniert.)</span><span class="sxs-lookup"><span data-stu-id="b14a6-108">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b14a6-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b14a6-109">In This Section</span></span>

  - [<span data-ttu-id="b14a6-110">Ändern der Einstellungen für Geräte Aktualisierungsprotokolldateien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b14a6-110">Modify settings for Device Update log files in Lync Server 2013</span></span>](lync-server-2013-modify-settings-for-device-update-log-files.md)

  - [<span data-ttu-id="b14a6-111">Löschen von Geräte Aktualisierungsprotokolldateien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b14a6-111">Delete Device Update log files in Lync Server 2013</span></span>](lync-server-2013-delete-device-update-log-files.md)

  - [<span data-ttu-id="b14a6-112">Entfernen von Geräteaktualisierungsdateien, die keinem Gerät zugeordnet sind, in Entfernen von Geräteaktualisierungsdateien, die nicht mit einem Gerät in lync Server 2013 verknüpft sind</span><span class="sxs-lookup"><span data-stu-id="b14a6-112">Remove Device Update files not associated with a device in Remove Device Update files not associated with a device in Lync Server 2013</span></span>](lync-server-2013-remove-device-update-files-not-associated-with-a-device.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Konfigurieren unterstützter Clientversionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a262cab2145013d83cdae573d98b5db17e0e890
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="50c0b-102">Konfigurieren von unterstützten Clientversionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50c0b-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50c0b-103">_**Letztes Änderungsdatum des Themas:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="50c0b-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="50c0b-104">In lync Server 2013 können Sie clientversionsrichtlinien einrichten, um die Versionen der Clients anzugeben, die in Ihrer Umgebung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="50c0b-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="50c0b-105">Darüber hinaus können Sie die globale Client Versions Konfiguration verwenden, um eine Standardaktion für Clients anzugeben, für die noch keine Versionsrichtlinie definiert ist und daher nicht explizit unterstützt oder eingeschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="50c0b-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="50c0b-106">Sie können auch clientversionsrichtlinien verwenden, um Clientupdates zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="50c0b-106">You can also use client version policies to manage client updates.</span></span> <span data-ttu-id="50c0b-107">Wenn Sie eine clientversionsrichtlinie festlegen und die Optionen **zulassen und aktualisieren** sowie **blockieren und aktualisieren**verwenden, erhalten Clients aktualisierte Software vom Windows Server Update-Dienst (wenn Sie diesen Dienst verwenden) oder von Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="50c0b-107">When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="50c0b-108">Client Versionsrichtlinien Einstellungen</span><span class="sxs-lookup"><span data-stu-id="50c0b-108">Client Version Policy Settings</span></span>

<span data-ttu-id="50c0b-109">Die standardmäßige clientversionsrichtlinie setzt voraus, dass alle Clients lync ausführen.</span><span class="sxs-lookup"><span data-stu-id="50c0b-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="50c0b-110">Wenn Clients in Ihrer Umgebung frühere Versionen von Communicator ausführen, müssen Sie möglicherweise die Client Versionsregeln neu konfigurieren, um zu verhindern, dass Clients und Geräte beim Herstellen einer Verbindung mit lync Server 2013 unerwartet blockiert oder aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="50c0b-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="50c0b-111">Sie können die Standardregel ändern, oder Sie können eine höhere Regel in der Liste der Client Versionsrichtlinien hinzufügen, um die Standardregel zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="50c0b-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="50c0b-112">Darüber hinaus sollten Sie die Client Versionsrichtlinie so konfigurieren, dass die neuesten Updates erforderlich sind, da kumulative Updates (CUS) freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="50c0b-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="50c0b-113">Ausführliche Informationen finden Sie unter [angeben der Clientanwendungen, die für die Anmeldung bei lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in der Betriebsdokumentation verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="50c0b-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


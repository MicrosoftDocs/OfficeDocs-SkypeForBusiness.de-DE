---
title: 'Lync Server 2013: bewährte Methoden für Ihre Kerninfrastruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 087cfed02e3b28df88508446c57e451f42ef067c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513002"
---
# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="150bb-102">Bewährte Methoden für Ihre Kerninfrastruktur in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="150bb-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="150bb-103">_**Letztes Änderungsstand des Themas:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="150bb-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="150bb-104">Wahrscheinlich haben Sie bereits Schritte zum Entwerfen der Fehlertoleranz in Ihrem System unternommen, indem Sie Verfahren wie die Sicherstellung der Hardwareredundanz, das Schützen von Stromverlust, die regelmäßige Installation von Sicherheitsupdates und Antivirenmaßnahmen sowie Monitoring Server Aktivitäten verwenden.</span><span class="sxs-lookup"><span data-stu-id="150bb-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="150bb-105">Diese Vorgehensweisen bieten nicht nur Ihrer Microsoft lync Server 2013 Infrastruktur, sondern auch Ihrem gesamten Netzwerkvorteile.</span><span class="sxs-lookup"><span data-stu-id="150bb-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="150bb-106">Wenn Sie diese Vorgehensweisen nicht implementiert haben, sollten Sie dies vor der Bereitstellung von lync Server 2013 tun.</span><span class="sxs-lookup"><span data-stu-id="150bb-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="150bb-107">Um die Server in ihrer lync Server 2013-Bereitstellung vor versehentlicher oder zielgerichteter Beschädigung zu schützen, die zu Ausfallzeiten führen können, sollten Sie die folgenden Vorkehrungen treffen:</span><span class="sxs-lookup"><span data-stu-id="150bb-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="150bb-108">Halten Sie Ihre Server mit Sicherheitsupdates auf dem neuesten Stand.</span><span class="sxs-lookup"><span data-stu-id="150bb-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="150bb-109">Durch das Abonnieren des Microsoft-Sicherheitsbenachrichtigungsdiensts können Sie sicherstellen, dass Sie Sofortbenachrichtigungen über Sicherheitsbulletins für ein beliebiges Microsoft-Produkt erhalten.</span><span class="sxs-lookup"><span data-stu-id="150bb-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="150bb-110">Um sich anzumelden, wechseln Sie zur Microsoft Technical Security Notifications-Website unter [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202) .</span><span class="sxs-lookup"><span data-stu-id="150bb-110">To subscribe, go to the Microsoft Technical Security Notifications website at [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="150bb-111">Stellen Sie sicher, dass die Zugriffsrechte ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="150bb-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="150bb-112">Halten Sie Ihre Server in einer physischen Umgebung, die unbefugten Zugriff verhindert.</span><span class="sxs-lookup"><span data-stu-id="150bb-112">Keep your servers in a physical environment that prevents unauthorized access.</span></span> <span data-ttu-id="150bb-113">Stellen Sie sicher, dass angemessene Antivirensoftware auf allen Servern installiert ist.</span><span class="sxs-lookup"><span data-stu-id="150bb-113">Ensure that adequate antivirus software is installed on all your servers.</span></span> <span data-ttu-id="150bb-114">Halten Sie die Software stets mit den neuesten Virensignaturdateien auf dem aktuellen Stand.</span><span class="sxs-lookup"><span data-stu-id="150bb-114">Keep the software up-to-date with the latest virus signature files.</span></span> <span data-ttu-id="150bb-115">Verwenden Sie das Feature für automatische Aktualisierungen der Antivirenanwendung, um die Virensignaturen auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="150bb-115">Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="150bb-116">Es wird empfohlen, dass Sie die Windows Server-Betriebssystemdienste deaktivieren, die auf den Computern, auf denen Sie lync Server 2013 installieren, nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="150bb-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="150bb-117">Verschlüsseln von Betriebssystemen und Laufwerken, auf denen Daten mit einem Verschlüsselungssystem mit voller Lautstärke gespeichert werden, es sei denn, Sie können eine ständige und vollständige Kontrolle über die Server, die gesamte physische Isolierung und die ordnungsgemäße und sichere Außerbetriebnahme von ausgetauschten oder ausgefallenen Laufwerken garantieren.</span><span class="sxs-lookup"><span data-stu-id="150bb-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="150bb-118">Deaktivieren Sie alle externen DMA-Ports (Direct Memory Access) des Servers, es sei denn, Sie können eine sehr strenge Kontrolle über den physischen Zugriff auf die Server garantieren.</span><span class="sxs-lookup"><span data-stu-id="150bb-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="150bb-119">DMA-basierte Angriffe, die relativ einfach initiiert werden können, könnten sehr vertrauliche Informationen wie private Verschlüsselungsschlüssel verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="150bb-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


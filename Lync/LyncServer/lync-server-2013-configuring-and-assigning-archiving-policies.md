---
title: 'Lync Server 2013: Konfigurieren und Zuweisen von Archivierungsrichtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8cfb5b446456d99750529d883172ed3cb56e3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="c4bc0-102">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4bc0-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4bc0-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c4bc0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c4bc0-104">In lync Server 2013 verwenden Sie Richtlinien, um die Archivierung für die interne Kommunikation und die externe Kommunikation für Benutzer zu aktivieren und zu deaktivieren, die in lync Server 2013 gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="c4bc0-105">Dies umfasst die folgenden Archivierungsrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="c4bc0-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="c4bc0-106">Eine globale Richtlinie, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="c4bc0-107">Optionale Richtlinien auf Websiteebene und auf Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Websites oder Benutzer implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="c4bc0-108">Sie haben zunächst Archivierungsrichtlinien eingerichtet, wenn Sie die Archivierung bereitstellen, Sie können aber nach der Bereitstellung Richtlinien ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="c4bc0-109">In der lync Server 2013-Systemsteuerung können Sie die Seite **Archivierungsrichtlinie** der Gruppe **Archivierung und Überwachung** verwenden, um Richtlinien auf globaler Ebene, auf Websiteebene und auf Benutzerebene zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c4bc0-110">Um die Implementierung der Archivierung zu steuern, müssen Sie Optionen in Archivierungs Konfigurationen angeben, beispielsweise ob Sie Chatnachrichten oder Konferenzen archivieren, die Verwendung des kritischen Modus und Bereinigungsoptionen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="c4bc0-111">Standardmäßig sind keine Optionen in der globalen Archivierungskonfiguration oder einer Standort-oder Pool Archivierungskonfiguration aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="c4bc0-112">Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung für die interne oder externe Kommunikation in den Archivierungsrichtlinien aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="c4bc0-113">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Websites und Pools</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="c4bc0-114">Wenn Sie Ihren lync-Server Speicher in Exchange 2013-Speicher integrieren, haben die Exchange-Benutzerrichtlinien Vorrang vor den Archivierungsrichtlinien für lync Server 2013, aber nur für die Benutzer, die sich in Exchange 2013 befinden und deren Postfächer in der Warteschleife platziert wurden.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="c4bc0-115">Einzelheiten zur Implementierung von Richtlinien, einschließlich der Hierarchie der Richtlinien, finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="c4bc0-116">Ausführliche Informationen zum Verwalten von Richtlinien nach der Bereitstellung finden Sie unter [Verwalten der Archivierung interner und externer Kommunikation in lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c4bc0-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c4bc0-117">In This Section</span></span>

  - [<span data-ttu-id="c4bc0-118">Konfigurieren der globalen Richtlinie für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4bc0-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="c4bc0-119">Einrichten von Website Richtlinien für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4bc0-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="c4bc0-120">Einrichten von Archivierungsrichtlinien für Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4bc0-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


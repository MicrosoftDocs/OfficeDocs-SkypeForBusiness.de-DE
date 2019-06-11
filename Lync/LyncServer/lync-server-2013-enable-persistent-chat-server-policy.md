---
title: 'Lync Server 2013: Aktivieren der Richtlinie für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58e71cd92182fc9f68d272ba23079677983b399
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="8f0cf-102">Aktivieren der Richtlinie für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0cf-102">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f0cf-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="8f0cf-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="8f0cf-104">In der lync Server 2013-Systemsteuerung können Sie die Seite "beständiger **Chat** " der Gruppe "beständiger **Chat** " verwenden, um Richtlinien auf globaler, Pool-, Website-oder Benutzerebene zu verwalten, einschließlich der Konfiguration der globalen Standardrichtlinie und dem Erstellen einer oder mehrerer zusätzliche Benutzer-und Website Richtlinien für Ihre Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-104">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="8f0cf-105">Wenn ein Benutzer nach Richtlinie für beständigen Chat Server aktiviert ist, wird die Server Umgebung für beständigen Chat in seinem lync 2013-Client angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-105">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f0cf-106">In der Topologie gelten Website Richtlinien für beständigen Chat Server global, pro Benutzerpool oder pro Benutzer Website oder pro Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-106">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="8f0cf-107">Die globale Richtlinie wird automatisch erstellt, wenn Sie den beständigen Chat Server bereitstellen, und Sie kann konfiguriert, aber nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="8f0cf-108">Da die globale Richtlinie auf alle Benutzern angewendet wird, muss sie nicht für jeden Benutzer einzeln festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-108">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="8f0cf-109">Sie können mehrere Website-und Benutzerrichtlinien erstellen und konfigurieren, die zusammen mit der globalen Richtlinie Benutzern für beständigen Chat Server ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="8f0cf-110">Pool-und Website-Server Richtlinien für persistente Chats setzen die globale Richtlinie für beständigen Chats außer Kraft, allerdings nur für Benutzer dieser Website.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="8f0cf-111">Benutzerrichtlinien setzen sowohl die globale als auch die Pool- und Standortrichtlinien für diejenigen Benutzer außer Kraft, denen die Benutzerrichtlinie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f0cf-112">Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um der Topologie Unterstützung für beständigen Chat Server hinzuzufügen und dann die Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="8f0cf-113">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigem Chat Server zu Ihrer Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-113">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8f0cf-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8f0cf-114">In This Section</span></span>

  - [<span data-ttu-id="8f0cf-115">Konfigurieren der globalen Richtlinie für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0cf-115">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="8f0cf-116">Erstellen einer Standortrichtlinie für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0cf-116">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="8f0cf-117">Erstellen einer Benutzerrichtlinie für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0cf-117">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="8f0cf-118">Anwenden einer Richtlinie für beständigen Chat auf einen Benutzer oder eine Benutzergruppe in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f0cf-118">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


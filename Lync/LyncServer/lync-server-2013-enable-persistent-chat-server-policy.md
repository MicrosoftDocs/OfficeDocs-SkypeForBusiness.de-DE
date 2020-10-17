---
title: 'Lync Server 2013: Server Richtlinie für beständigen Chat aktivieren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794fe378f9e7d8024f4bc06000d6d7d1cd89481e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528572"
---
# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="d5591-102">Aktivieren der Server Richtlinie für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5591-102">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5591-103">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="d5591-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="d5591-104">In der lync Server 2013-Systemsteuerung können Sie die Seite **Richtlinie** für beständigen Chat der Gruppe **beständiger Chat** verwenden, um Richtlinien auf globaler Ebene, auf Pool-, Standort-oder Benutzerebene zu verwalten, einschließlich der Konfiguration der globalen Standardrichtlinie und dem Erstellen einer oder mehrerer zusätzlicher Benutzer-und Standortrichtlinien für Ihre Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="d5591-104">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="d5591-105">Wenn ein Benutzer für den Server für beständigen Chat nach Richtlinien aktiviert ist, wird die Server Umgebung für beständigen Chat in Ihrem lync 2013-Client angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d5591-105">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5591-106">In der Topologie gelten die Standortrichtlinien für beständigen Chat Server global, pro Pool des Benutzers oder pro Standort des Benutzers oder pro Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d5591-106">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="d5591-107">Die globale Richtlinie wird automatisch erstellt, wenn Sie den Server für beständigen Chat bereitstellen, und Sie kann konfiguriert, jedoch nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="d5591-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="d5591-108">Da die globale Richtlinie für alle Benutzer gilt, muss sie nicht pro Benutzer festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d5591-108">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="d5591-109">Sie können mehrere Standort-und Benutzerrichtlinien erstellen und konfigurieren, die zusammen mit der globalen Richtlinie Benutzer für den Server für beständigen Chat aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d5591-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="d5591-110">Server Richtlinien für Pool-und Website-beständigen Chat setzen die globale Richtlinie für beständigen Chat außer Kraft, jedoch nur für Benutzer dieser Website.</span><span class="sxs-lookup"><span data-stu-id="d5591-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="d5591-111">Benutzerrichtlinien setzen globale Richtlinien, Poolrichtlinien und Standortrichtlinien für diejenigen Benutzer außer Kraft, denen die Benutzerrichtlinie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d5591-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5591-112">Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um die Unterstützung für beständigen Chat Server zur Topologie hinzuzufügen und die Topologie dann zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="d5591-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="d5591-113">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigen Chat Servern zur Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d5591-113">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d5591-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d5591-114">In This Section</span></span>

  - [<span data-ttu-id="d5591-115">Konfigurieren der globalen Richtlinie für den beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5591-115">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="d5591-116">Erstellen einer Standortrichtlinie für den beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5591-116">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="d5591-117">Erstellen einer Benutzerrichtlinie für den beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5591-117">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="d5591-118">Anwenden einer Richtlinie für beständigen Chat auf einen Benutzer oder eine Benutzergruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5591-118">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


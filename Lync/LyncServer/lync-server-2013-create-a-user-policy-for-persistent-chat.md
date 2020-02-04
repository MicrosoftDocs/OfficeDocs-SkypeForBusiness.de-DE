---
title: 'Lync Server 2013: Erstellen einer Benutzerrichtlinie für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a9bd88dd84b8b5056adf19ebc098daac54cb005
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="63d24-102">Erstellen einer Benutzerrichtlinie für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63d24-102">Create a user policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63d24-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="63d24-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="63d24-104">In der lync Server-Systemsteuerung definieren Sie Benutzerrichtlinien, die Benutzern in **Benutzern**zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="63d24-104">In the Lync Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>

<span data-ttu-id="63d24-105">Die Benutzerrichtlinie setzt die Richtlinien auf globaler und Standortebene außer Kraft. Dies gilt jedoch nur für die Benutzer, denen die Benutzerrichtlinie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="63d24-105">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63d24-106">Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um der Topologie Unterstützung für beständigen Chat Server hinzuzufügen und dann die Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="63d24-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="63d24-107">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigem Chat Server zu Ihrer Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="63d24-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="63d24-108">Informationen zum Konfigurieren von Einstellungen für den beständigen Chat Server finden Sie unter <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Konfigurieren von beständigen Chat Serveroptionen Global oder für den Serverpool für beständigen Chat in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="63d24-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="63d24-109">So erstellen Sie eine Benutzerrichtlinie für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="63d24-109">To create a user policy for Persistent Chat</span></span>

1.  <span data-ttu-id="63d24-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="63d24-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="63d24-111">Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="63d24-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="63d24-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="63d24-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="63d24-113">Sie können auch Windows PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="63d24-113">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="63d24-114">Weitere Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des beständigen Chat Servers mithilfe von Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="63d24-114">See <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="63d24-115">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="63d24-115">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="63d24-116">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="63d24-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="63d24-117">Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="63d24-117">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="63d24-118">Geben Sie unter **Name** einen Namen für die neue Benutzerrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="63d24-118">In **Name**, specify a name for the new user policy.</span></span>
    
      - <span data-ttu-id="63d24-119">Geben Sie in **Beschreibung**Details zu den Benutzerrichtlinien an (beispielsweise Richtlinien für beständigen Chat für bestimmten Benutzer).</span><span class="sxs-lookup"><span data-stu-id="63d24-119">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
      - <span data-ttu-id="63d24-120">Zum Steuern des beständigen Chats für alle Benutzer, die nicht ausdrücklich über eine Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **beständigen Chat aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="63d24-120">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="63d24-121">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="63d24-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


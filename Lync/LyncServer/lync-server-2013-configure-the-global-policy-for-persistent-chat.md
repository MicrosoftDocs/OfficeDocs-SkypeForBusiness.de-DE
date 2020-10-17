---
title: 'Lync Server 2013: Konfigurieren der globalen Richtlinie für den beständigen Chat'
description: 'Lync Server 2013: Konfigurieren Sie die globale Richtlinie für den beständigen Chat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 830074c31791ee8ff489d9a67af189be609c7f4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544941"
---
# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="3c82a-103">Konfigurieren der globalen Richtlinie für den beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c82a-103">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c82a-104">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="3c82a-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="3c82a-105">Sie können die standardmäßige globale Richtlinie allein verwenden, um Einstellungen für beständigen Chat für alle Benutzer in Ihrer Bereitstellung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3c82a-105">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="3c82a-106">Sie können auch zusätzliche Richtlinien für Websites und Benutzer festlegen, um zu steuern, ob persistenter Chat für bestimmte Benutzer und Websites aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3c82a-106">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="3c82a-107">Die globale Richtlinie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3c82a-107">You cannot delete the global policy.</span></span> <span data-ttu-id="3c82a-108">Beim Versuch, die globale Richtlinie zu löschen, wird die Konfiguration auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="3c82a-108">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c82a-109">Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um die Unterstützung für beständigen Chat Server zur Topologie hinzuzufügen und die Topologie dann zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="3c82a-109">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="3c82a-110">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigen Chat Servern zur Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3c82a-110">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="3c82a-111">Informationen zum Konfigurieren von Konfigurationseinstellungen für den Server für beständigen Chat finden Sie unter <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configure persistent Chat Server Options Globally or for persistent Chat Serverpool in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3c82a-111">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="3c82a-112">So konfigurieren Sie die globale Richtlinie für den beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="3c82a-112">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="3c82a-113">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator", "CsAdministrator" oder "CsUserAdministrator" zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3c82a-113">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3c82a-114">Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein.</span><span class="sxs-lookup"><span data-stu-id="3c82a-114">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="3c82a-115">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3c82a-115">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3c82a-116">Sie können auch Windows PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c82a-116">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="3c82a-117">Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mit Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3c82a-117">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="3c82a-118">Klicken Sie in lync Server-Systemsteuerung auf **beständiger Chat**und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="3c82a-118">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="3c82a-119">Klicken Sie in der Liste der Richtlinien auf **Global**, und klicken Sie dann auf **Bearbeiten** und **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3c82a-119">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3c82a-120">Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="3c82a-120">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="3c82a-121">Geben Sie in **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardnamen "Global" nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="3c82a-121">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="3c82a-122">Geben Sie in **Beschreibung**Details zu den Anforderungen der Benutzerrichtlinie an (beispielsweise globale Richtlinie für centralSiteName).</span><span class="sxs-lookup"><span data-stu-id="3c82a-122">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="3c82a-123">Zum Steuern des beständigen Chats für alle Websites und Benutzer, die nicht speziell über eine Standort-oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **beständigen Chat aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="3c82a-123">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="3c82a-124">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3c82a-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


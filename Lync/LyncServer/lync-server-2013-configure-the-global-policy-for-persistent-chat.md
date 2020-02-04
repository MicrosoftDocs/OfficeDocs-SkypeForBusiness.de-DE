---
title: 'Lync Server 2013: Konfigurieren der globalen Richtlinie für beständigen Chat'
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
ms.openlocfilehash: 49fb5f329851436e503a9e3e42e144353b70017f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="6934b-102">Konfigurieren der globalen Richtlinie für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6934b-102">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6934b-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="6934b-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="6934b-104">Sie können die standardmäßige globale Richtlinie selbst verwenden, um beständige Chat Einstellungen für alle Benutzer in Ihrer Bereitstellung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6934b-104">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="6934b-105">Sie können auch zusätzliche Richtlinien für Websites und Benutzer angeben, um zu steuern, ob der beständige Chat für bestimmte Benutzer und Websites aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6934b-105">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="6934b-106">Sie können die globale Richtlinie nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="6934b-106">You cannot delete the global policy.</span></span> <span data-ttu-id="6934b-107">Wenn Sie versuchen, Sie zu löschen, wird die Konfiguration auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="6934b-107">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6934b-108">Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um der Topologie Unterstützung für beständigen Chat Server hinzuzufügen und dann die Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6934b-108">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="6934b-109">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von beständigem Chat Server zu Ihrer Bereitstellung in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6934b-109">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="6934b-110">Informationen zum Konfigurieren von Einstellungen für den beständigen Chat Server finden Sie unter <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Konfigurieren von beständigen Chat Serveroptionen Global oder für den Serverpool für beständigen Chat in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6934b-110">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="6934b-111">So konfigurieren Sie die globale Richtlinie für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="6934b-111">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="6934b-112">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="6934b-112">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6934b-113">Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="6934b-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="6934b-114">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6934b-114">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6934b-115">Sie können auch Windows PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="6934b-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="6934b-116">Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des beständigen Chat Servers mithilfe von Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6934b-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="6934b-117">Klicken Sie in der lync Server-Systemsteuerung auf **beständigen Chat**und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="6934b-117">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="6934b-118">Klicken Sie in der Liste der Richtlinien auf **Global**, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6934b-118">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="6934b-119">Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6934b-119">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="6934b-120">Geben Sie unter **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardwert „Global“ nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="6934b-120">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="6934b-121">Geben Sie in **Beschreibung**Details zu den Richtlinien für Benutzer an (beispielsweise globale Richtlinie für centralSiteName).</span><span class="sxs-lookup"><span data-stu-id="6934b-121">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="6934b-122">Zum Steuern des beständigen Chats für alle Websites und Benutzer, die nicht explizit über eine Website Richtlinie oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **beständigen Chat aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="6934b-122">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="6934b-123">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6934b-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


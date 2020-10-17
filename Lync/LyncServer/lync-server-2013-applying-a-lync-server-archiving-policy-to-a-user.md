---
title: 'Lync Server 2013: Anwenden einer lync Server-Archivierungsrichtlinie auf einen Benutzer'
description: 'Lync Server 2013: Anwenden einer lync Server Archivierungsrichtlinie auf einen Benutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69dcca5601185d65735b963673322a0630af6ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544991"
---
# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a><span data-ttu-id="044da-103">Anwenden einer lync Server Archivierungsrichtlinie auf einen Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="044da-103">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="044da-104">_**Letztes Änderungsstand des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="044da-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="044da-105">Nachdem Sie eine lync Server Benutzerrichtlinie erstellt haben, müssen Sie Sie auf bestimmte Benutzer oder Benutzergruppen anwenden, die in lync Server 2013 verwaltet werden, bevor Sie wirksam werden kann.</span><span class="sxs-lookup"><span data-stu-id="044da-105">After creating a Lync Server user policy, you must apply it to specific the users or user groups that are homed on Lync Server 2013 before it can take effect.</span></span> <span data-ttu-id="044da-106">Ausführliche Informationen zum Erstellen von Benutzerrichtlinien für bestimmte Benutzer finden Sie unter [Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="044da-106">For details about creating user policies for specific users, see [Creating and configuring user policies for Archiving in Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="044da-107">Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort-und Benutzerrichtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="044da-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="044da-108">Um die Archivierung konfigurieren und verwenden zu können, müssen Sie zunächst die Archivierung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="044da-108">In order to configure and use archiving, you must first deploy archiving.</span></span> <span data-ttu-id="044da-109">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deploying-archiving.md">Deploying Archiving in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="044da-109">For details, see <A href="lync-server-2013-deploying-archiving.md">Deploying Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="044da-110">Wenn Sie Microsoft Exchange Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-In-Place-Aufbewahrungsrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden, und dass ihre Postfächer In-Place Aufbewahrungsspeicher abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="044da-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="044da-111">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung Exchange Server Integration</A> in die Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="044da-111">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="044da-112">Sie sollten alle entsprechenden Optionen in den Archivierungskonfigurationen angeben, bevor Sie die Archivierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="044da-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="044da-113">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="044da-113">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a><span data-ttu-id="044da-114">So wenden Sie eine lync Server Archivierungsrichtlinie auf einen Benutzer an</span><span class="sxs-lookup"><span data-stu-id="044da-114">To apply a Lync Server archiving policy to a user</span></span>

1.  <span data-ttu-id="044da-115">Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="044da-115">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="044da-116">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="044da-116">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="044da-117">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server 2013 Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="044da-117">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="044da-118">Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie dann nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="044da-118">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="044da-119">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="044da-119">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="044da-120">Wählen Sie im Abschnitt **lync Server Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="044da-120">In **Edit Lync Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="044da-121">Durch die <STRONG> &lt; automatischen &gt; </STRONG> Einstellungen werden die Standardeinstellungen für die Server Installation übernommen.</span><span class="sxs-lookup"><span data-stu-id="044da-121">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="044da-122">Diese Einstellungen werden automatisch vom Server angewendet.</span><span class="sxs-lookup"><span data-stu-id="044da-122">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="044da-123">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="044da-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


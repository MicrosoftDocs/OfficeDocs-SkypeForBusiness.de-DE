---
title: Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8c3c83f06f7bc01d81acc18cb0c9cedb4b0ef7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="7a212-102">Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a212-102">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a212-103">_**Letztes Änderungsstand des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="7a212-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="7a212-104">Zum Aktivieren oder Deaktivieren der Archivierung für bestimmte Benutzer, die in lync Server verwaltet werden, müssen Sie zuerst eine Benutzerrichtlinie erstellen und dann die Richtlinie auf einen oder mehrere Benutzer oder Benutzergruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="7a212-104">To enable or disable Archiving for specific users homed on Lync Server, you must first create a user policy and then apply the policy to one or more users or user groups.</span></span> <span data-ttu-id="7a212-105">Ausführliche Informationen zum Anwenden von Benutzerrichtlinien auf bestimmte Benutzer und Benutzergruppen finden Sie unter [Anwenden einer lync Server Archivierungsrichtlinie auf einen Benutzer in lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7a212-105">For details about applying user policies to specific users and user groups, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

<span data-ttu-id="7a212-106">Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort-und Benutzerrichtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7a212-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, in the Deployment documentation, or in the Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7a212-107">Wenn Sie Microsoft Exchange Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange in-situ-Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden, und dass ihre Postfächer im Compliance-Archiv platziert werden.</span><span class="sxs-lookup"><span data-stu-id="7a212-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="7a212-108">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung Exchange Server Integration</A> in die Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7a212-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="7a212-109">Sie sollten alle entsprechenden Optionen in den Archivierungskonfigurationen angeben, bevor Sie die Archivierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7a212-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="7a212-110">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7a212-110">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a><span data-ttu-id="7a212-111">So konfigurieren Sie eine Archivierungsrichtlinie für Benutzer, die in lync Server verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="7a212-111">To configure an archiving policy for users homed on Lync Server</span></span>

1.  <span data-ttu-id="7a212-112">Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7a212-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7a212-113">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7a212-113">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="7a212-114">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server 2013 Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7a212-114">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7a212-115">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="7a212-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="7a212-116">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="7a212-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="7a212-117">Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7a212-117">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="7a212-118">Geben Sie im Feld **Name** den Namen der Benutzerrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="7a212-118">In **Name**, specify the name for the user policy.</span></span>
    
      - <span data-ttu-id="7a212-119">Machen Sie im Feld **Beschreibung** nähere Angaben zur Art der Benutzerrichtlinie (z. B. Benutzerrichtlinie für die Rechtsabteilung).</span><span class="sxs-lookup"><span data-stu-id="7a212-119">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
      - <span data-ttu-id="7a212-120">Um die Archivierung der internen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.</span><span class="sxs-lookup"><span data-stu-id="7a212-120">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="7a212-121">Um die Archivierung der externen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.</span><span class="sxs-lookup"><span data-stu-id="7a212-121">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="7a212-122">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7a212-122">Click **Commit**.</span></span>

<span data-ttu-id="7a212-123">Benutzerrichtlinien wirken sich nur auf Benutzer aus, denen eine solche Richtlinie zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="7a212-123">A user policy applies only to users to whom you assign the policy.</span></span> <span data-ttu-id="7a212-124">Ausführliche Informationen zum Anwenden einer Benutzerrichtlinie auf bestimmte Benutzer finden Sie unter [Anwenden einer lync Server Archivierungsrichtlinie auf einen Benutzer in lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7a212-124">For details about applying a user policy to specific users, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


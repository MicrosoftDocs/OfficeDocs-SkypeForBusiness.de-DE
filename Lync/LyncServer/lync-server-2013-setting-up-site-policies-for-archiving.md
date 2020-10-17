---
title: 'Lync Server 2013: Einrichten von Standortrichtlinien für die Archivierung'
description: 'Lync Server 2013: Einrichten von Standortrichtlinien für die Archivierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e5b80b7f62ddc18d418415307457c7f2c4010d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558391"
---
# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="78620-103">Einrichten von Standortrichtlinien für die Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78620-103">Setting up site policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78620-104">_**Letztes Änderungsstand des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="78620-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="78620-105">Sie können die Archivierung für bestimmte Websites aktivieren oder deaktivieren, indem Sie für jede dieser Websites eine Archivierungsrichtlinie erstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="78620-105">You can enable or disable Archiving for specific sites by creating and configuring an Archiving policy for each of those sites.</span></span> <span data-ttu-id="78620-106">Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, aber Benutzerrichtlinien überschreiben Standortrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="78620-106">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="78620-107">Archivierungsrichtlinien gelten nur, wenn Sie nicht Microsoft Exchange Integration verwenden oder, wenn Sie Microsoft Exchange-Integration verwenden, aber einige Benutzer haben, die nicht in Exchange 2013 verwaltet werden und deren Postfächer In-Place Aufbewahrungsstelle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="78620-107">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="78620-108">Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort-und Benutzerrichtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="78620-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78620-109">Wenn Sie Microsoft Exchange Integration für Ihre Bereitstellung aktivieren, Steuern Exchange-In-Place-Aufbewahrungsrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden, und dass ihre Postfächer In-Place Aufbewahrungsspeicher abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="78620-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="78620-110">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung Exchange Server Integration</A> in die Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="78620-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="78620-111">Geben Sie in den Archivierungskonfigurationen erst alle erforderlichen Optionen, bevor Sie in den Archivierungsrichtlinien die Archivierung der internen oder externen Kommunikation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="78620-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="78620-112">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="78620-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a><span data-ttu-id="78620-113">So erstellen Sie eine Archivierungsrichtlinie für einen Standort</span><span class="sxs-lookup"><span data-stu-id="78620-113">To create an archiving policy for a site</span></span>

1.  <span data-ttu-id="78620-114">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="78620-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="78620-115">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="78620-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span>

3.  <span data-ttu-id="78620-116">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="78620-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="78620-117">Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort-und Benutzerrichtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="78620-117">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

4.  <span data-ttu-id="78620-118">Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="78620-118">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="78620-119">Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="78620-119">In **Select a site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="78620-120">Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="78620-120">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="78620-121">Geben Sie im Feld **Name** den Namen für die Standortrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="78620-121">In **Name**, specify the name for the site policy.</span></span>
    
      - <span data-ttu-id="78620-122">Geben Sie im Feld **Beschreibung** Informationen zum Verwendungszweck der Standortrichtlinie an (z. B. Standortrichtlinie für Redmond).</span><span class="sxs-lookup"><span data-stu-id="78620-122">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
      - <span data-ttu-id="78620-123">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der internen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="78620-123">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="78620-124">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="78620-124">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>

7.  <span data-ttu-id="78620-125">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="78620-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


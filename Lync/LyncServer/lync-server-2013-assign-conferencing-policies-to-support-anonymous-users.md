---
title: 'Lync Server 2013: Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de154fca02470003fdedd0ff29cc8c879d1865aa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523192"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="84630-102">Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84630-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84630-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="84630-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="84630-104">Standardmäßig werden alle Benutzer daran gehindert, anonyme Benutzer zur Teilnahme an einer Besprechung einzuladen.</span><span class="sxs-lookup"><span data-stu-id="84630-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="84630-105">Sie steuern, wer anonyme Benutzer einladen kann, indem Sie eine Konferenzrichtlinie für die Unterstützung anonymer Benutzer konfigurieren und diese Konferenzrichtlinie auf bestimmte Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="84630-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="84630-106">Ausführliche Informationen zum Konfigurieren von Konferenzrichtlinien zur Unterstützung anonymer Benutzer finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) und [Verwalten des Verbunds und des externen Zugriffs auf lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="84630-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="84630-107">Verwenden Sie das Verfahren in diesem Abschnitt, um eine bereits erstellte Konferenzrichtlinie auf einen oder mehrere Benutzer oder Benutzergruppen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="84630-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84630-108">Neben der Konfiguration und Anwendung einer Richtlinie müssen Sie außerdem die Unterstützung für anonyme Benutzer für Ihre Organisation aktivieren, um Benutzern das Einladen anonymer Benutzer zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="84630-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="84630-109">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">configure Policies to Control Public User Access in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="84630-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="84630-110">So konfigurieren Sie eine Benutzerrichtlinie für die anonyme Teilnahme an Besprechungen</span><span class="sxs-lookup"><span data-stu-id="84630-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="84630-111">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="84630-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="84630-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="84630-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="84630-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="84630-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="84630-114">Klicken Sie in der linken Navigationsleiste auf **Konferenzen**, und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="84630-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="84630-p104">Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie**. Erstellen Sie einen eindeutigen Namen im Feld **Name**, der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnableAnonymous** für eine Benutzerrichtlinie, welche die Kommunikation mit anonymen Benutzern aktiviert).</span><span class="sxs-lookup"><span data-stu-id="84630-p104">To create a new user policy, click **New**, and then click **User policy**. Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="84630-117">Klicken Sie zum Konfigurieren einer vorhandenen Benutzerrichtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="84630-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="84630-118">Aktivieren Sie im Dialogfeld **Konferenzrichtlinien** das Kontrollkästchen **Teilnehmern das Einladen anonymer Benutzer gestatten**.</span><span class="sxs-lookup"><span data-stu-id="84630-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="84630-119">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="84630-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="84630-120">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="84630-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="84630-121">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="84630-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="84630-122">Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **Konferenzrichtlinie** die Benutzerrichtlinie mit der Konfiguration für den anonymen Benutzerzugriff aus, die Sie auf diesen Benutzer anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="84630-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="84630-123">Durch die <STRONG> &lt; automatischen &gt; </STRONG> Einstellungen werden die Standardeinstellungen für die Server Installation übernommen und vom Server automatisch angewendet.</span><span class="sxs-lookup"><span data-stu-id="84630-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="84630-124">Damit Benutzer anonyme Benutzer zu Konferenzen einladen können, müssen Sie auch die Unterstützung für anonyme Benutzer in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="84630-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="84630-125">Ausführliche Informationen finden Sie unter [configure Policies to Control Public User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="84630-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


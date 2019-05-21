---
title: Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie steuern, wer anonyme Benutzer einladen kann, indem Sie eine konferenzrichtlinie für die Unterstützung anonymer Benutzer konfigurieren und diese konferenzrichtlinie auf bestimmte Benutzer anwenden.
ms.openlocfilehash: d7956e68db3330f0804e6161e0eeaf52958bc588
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280285"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="c8298-103">Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8298-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="c8298-104">Standardmäßig werden alle Benutzer daran gehindert, anonyme Benutzer zur Teilnahme an einer Besprechung einzuladen.</span><span class="sxs-lookup"><span data-stu-id="c8298-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="c8298-105">Sie steuern, wer anonyme Benutzer einladen kann, indem Sie eine konferenzrichtlinie für die Unterstützung anonymer Benutzer konfigurieren und diese konferenzrichtlinie auf bestimmte Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="c8298-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="c8298-106">Details zum Konfigurieren von Konferenzrichtlinien zur Unterstützung anonymer Benutzer finden Sie unter [Erstellen von Konferenzrichtlinien in Skype for Business Server](../../conferencing/create-policies.md) und [Verwalten des Föderations-und externen Zugriffs auf Skype for Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="c8298-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="c8298-107">Verwenden Sie das Verfahren in diesem Abschnitt, um eine konferenzrichtlinie anzuwenden, die Sie bereits für einen oder mehrere Benutzer oder Benutzergruppen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="c8298-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="c8298-108">Neben der Konfiguration und Anwendung einer Richtlinie, mit der Benutzer anonyme Benutzer einladen können, müssen Sie auch die Unterstützung für anonyme Benutzer für Ihre Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8298-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="c8298-109">Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von öffentlichen Benutzern in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="c8298-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="c8298-110">So konfigurieren Sie eine Benutzerrichtlinie für die anonyme Teilnahme an Besprechungen</span><span class="sxs-lookup"><span data-stu-id="c8298-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="c8298-111">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c8298-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8298-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c8298-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c8298-113">Klicken Sie in der linken Navigationsleiste auf **Konferenzen**, und führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c8298-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="c8298-114">Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="c8298-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="c8298-115">Erstellen Sie im Feld **Name** einen eindeutigen Namen, der angibt, was die Benutzerrichtlinie umfasst (beispielsweise **EnableAnonymous** für eine Benutzerrichtlinie, die die Kommunikation mit anonymen Benutzern ermöglicht).</span><span class="sxs-lookup"><span data-stu-id="c8298-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="c8298-116">Wenn Sie eine vorhandene Benutzerrichtlinie konfigurieren möchten, klicken Sie auf die entsprechende Richtlinie, die in der Tabelle aufgeführt ist, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c8298-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="c8298-117">Aktivieren Sie im Dialogfeld **Konferenzrichtlinien** das Kontrollkästchen Teilnehmern die Möglichkeit geben, **anonyme Benutzer einzuladen** .</span><span class="sxs-lookup"><span data-stu-id="c8298-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="c8298-118">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c8298-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="c8298-119">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, suchen Sie nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c8298-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="c8298-120">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c8298-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="c8298-121">Wählen Sie in **Skype for Business Server-Benutzer bearbeiten** unter **konferenzrichtlinie**die Benutzerrichtlinie mit der Konfiguration für den anonymen Benutzer Zugriff aus, die Sie auf diesen Benutzer anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c8298-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="c8298-122">Die <STRONG> &lt;automatischen&gt; </STRONG> Einstellungen wenden die Standardeinstellungen für Server Installationen an und werden automatisch vom Server angewendet.</span><span class="sxs-lookup"><span data-stu-id="c8298-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="c8298-123">Damit Benutzer anonyme Benutzer zu Konferenzen einladen können, müssen Sie auch die Unterstützung für anonyme Benutzer in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8298-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="c8298-124">Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von öffentlichen Benutzern in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="c8298-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


---
title: Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie steuern, wer anonyme Benutzer einladen kann durch Konfigurieren einer konferenzrichtlinie so, dass anonyme Benutzer unterstützen und diese konferenzrichtlinie auf bestimmte Benutzer anwenden.
ms.openlocfilehash: 5d3ade88a9d4ca0f639d7119da53f8180af6c30d
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222730"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="1ab7e-103">Zuweisen von konferenzrichtlinien zur Unterstützung anonymer Benutzer in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="1ab7e-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="1ab7e-104">Standardmäßig werden alle Benutzer daran gehindert anonyme Benutzer zur Teilnahme an einer Besprechung einladen.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="1ab7e-105">Sie steuern, wer anonyme Benutzer einladen kann durch Konfigurieren einer konferenzrichtlinie so, dass anonyme Benutzer unterstützen und diese konferenzrichtlinie auf bestimmte Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="1ab7e-106">Ausführliche Informationen zum Konfigurieren einer konferenzrichtlinien zur Unterstützung der anonyme Benutzer finden Sie unter [konferenzrichtlinien in Skype für Business Server erstellen](../../conferencing/create-policies.md) und [Verwalten von Verbund und externen Zugriff auf Skype für Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="1ab7e-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="1ab7e-107">Verwenden Sie das Verfahren in diesem Abschnitt, um einen oder mehrere Benutzer oder Benutzergruppen zuweisen eine konferenzrichtlinie, die Sie bereits erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="1ab7e-108">Zusätzlich zu konfigurieren und Anwenden einer Richtlinie, um Benutzer können anonyme Benutzer einladen zu aktivieren, müssen Sie auch die Unterstützung für anonyme Benutzer für Ihre Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="1ab7e-109">Weitere Informationen hierzu finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Skype für Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1ab7e-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="1ab7e-110">So konfigurieren Sie eine Benutzerrichtlinie für die anonyme Teilnahme an Besprechungen</span><span class="sxs-lookup"><span data-stu-id="1ab7e-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="1ab7e-111">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1ab7e-112">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1ab7e-113">In der linken Navigationsleiste auf **Konferenzen**und führen Sie dann eine der folgenden:</span><span class="sxs-lookup"><span data-stu-id="1ab7e-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="1ab7e-114">Um eine neue Richtlinie zu erstellen, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="1ab7e-115">Erstellen Sie einen eindeutigen Namen im Feld **Name** , das angibt, welche die Benutzerrichtlinie (beispielsweise **EnableAnonymous** für eine Benutzerrichtlinie, die die Kommunikation mit anonymen Benutzern ermöglicht) behandelt.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="1ab7e-116">Um eine vorhandene Benutzerrichtlinie zu konfigurieren, klicken Sie auf die entsprechende Richtlinie in der Tabelle, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="1ab7e-117">Aktivieren Sie im Dialogfeld **Konferenzrichtlinien** das Kontrollkästchen **anonyme Benutzer einladen von Teilnehmern gestatten** .</span><span class="sxs-lookup"><span data-stu-id="1ab7e-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="1ab7e-118">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="1ab7e-119">In der linken Navigationsleiste auf **Benutzer**, und suchen Sie auf das Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="1ab7e-120">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="1ab7e-121">**Skype für Business Server-Benutzer bearbeiten** unter **konferenzrichtlinie**wählen Sie die Benutzerrichtlinie mit der Konfiguration des Zugriffs anonymer Benutzer, die Sie für diesen Benutzer anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="1ab7e-122">Die <STRONG> &lt;automatische&gt; </STRONG> Einstellungen gelten die Standardeinstellungen für Server-Installation und werden vom Server automatisch angewendet.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="1ab7e-123">Damit Benutzer können anonyme Benutzer auf Konferenzen einladen können, müssen Sie auch die Unterstützung für anonyme Benutzer in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1ab7e-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="1ab7e-124">Weitere Informationen hierzu finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Skype für Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1ab7e-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


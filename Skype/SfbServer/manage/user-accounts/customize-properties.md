---
title: Anpassen der Eigenschaften von Benutzerkonten für Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Die Verfahren können in diesem Abschnitt Sie einzelne Benutzerkontoeigenschaften ändern.
ms.openlocfilehash: 1f2039180a2bfa44b3379f7cf6bf095e2d0a7c14
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911833"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="3c0af-103">Anpassen der Eigenschaften von Benutzerkonten für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="3c0af-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="3c0af-104">Die Verfahren können in diesem Abschnitt Sie einzelne Benutzerkontoeigenschaften ändern.</span><span class="sxs-lookup"><span data-stu-id="3c0af-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="3c0af-105">Es gibt zwei grundlegende Vorgänge, die Ebene der einzelnen Benutzer ausgeführt werden können:</span><span class="sxs-lookup"><span data-stu-id="3c0af-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="3c0af-106">Konfigurieren von Telefonieoptionen für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="3c0af-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="3c0af-107">Verschieben von Benutzern in einen anderen pool</span><span class="sxs-lookup"><span data-stu-id="3c0af-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="3c0af-108">Konfigurieren von Telefonieoptionen für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="3c0af-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="3c0af-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="3c0af-109"></span></span>

<span data-ttu-id="3c0af-110">Sie können die telefonieeinstellungen für einen bestimmten Benutzer (sofern der einzelne Benutzer für Skype für Business Server aktiviert wurde, und das Unternehmen Telefonie unterstützt) anpassen.</span><span class="sxs-lookup"><span data-stu-id="3c0af-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="3c0af-111">Skype für Business Server Benutzer Telefonieoptionen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3c0af-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="3c0af-112">**Audio/Video deaktiviert.** Der Benutzer kann keine Anrufe mit audio und video tätigen.</span><span class="sxs-lookup"><span data-stu-id="3c0af-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="3c0af-113">**PC-zu-PC nur** Der Benutzer kann nur PC-zu-PC-audio oder video Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="3c0af-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="3c0af-114">**Enterprise-VoIP** Der Benutzer kann die Skype für Business Server-Infrastruktur verwenden, alle ein- und ausgehenden Anrufe weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="3c0af-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="3c0af-115">Der Benutzer kann auch Anrufe von PC zu PC tätigen.</span><span class="sxs-lookup"><span data-stu-id="3c0af-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="3c0af-116">**Remoteanrufsteuerung** Der Benutzer kann Skype für Business Server verwenden, um das herkömmliche Telefon steuern und kann auch Anrufe von PC zu PC tätigen.</span><span class="sxs-lookup"><span data-stu-id="3c0af-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="3c0af-117">Ausführliche Informationen zum Konfigurieren der Telefonie für eine Organisation finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in Skype für Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) und [Bereitstellen von Enterprise-VoIP in Skype für Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3c0af-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="3c0af-118">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3c0af-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c0af-119">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3c0af-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3c0af-120">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3c0af-121">Geben Sie im Feld **Suchen Benutzer** alle den ersten Teil der Anzeigename, Vorname, letzte Name, Kontonamen Sicherheitskontenverwaltung (SAM), SIP-Adresse oder Zeile URI Uniform Resource Identifier () für das Benutzerkonto an, dass Sie möchten, und klicken Sie dann auf \*\*Suchen \*\*.</span><span class="sxs-lookup"><span data-stu-id="3c0af-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="3c0af-122">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3c0af-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="3c0af-123">Klicken Sie im Menü **Bearbeiten** auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="3c0af-124">Folgendermaßen Sie in der **Telefonie**vor:</span><span class="sxs-lookup"><span data-stu-id="3c0af-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="3c0af-125">Um audio und video-Anrufe für den Benutzer zu deaktivieren, klicken Sie auf **Audio/Video deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="3c0af-126">Um PC-zu-PC-audio-Kommunikation für den Benutzer, aber nicht die Remoteanrufsteuerung oder Enterprise-VoIP zu ermöglichen, klicken Sie auf **PC-zu-PC nur**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="3c0af-127">Geben Sie einen Wert für den **Anschluss-URI** für das Telefon, das der Benutzer für die PC-zu-PC-audio-Kommunikation verwendet.</span><span class="sxs-lookup"><span data-stu-id="3c0af-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="3c0af-128">Klicken Sie auf **Enterprise-VoIP**, so, dass der Benutzer Anrufe mithilfe der Skype für Business-Infrastruktur gemäß der Klasse des Service-Richtlinien, einschließlich Audiokommunikation PC zu PC weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="3c0af-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="3c0af-129">Geben Sie im **Anschluss-URI**der Telefonnummer für Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="3c0af-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="3c0af-130">Geben Sie in der **Richtlinie für Wähleinstellungen** und **VoIP-Richtlinie**die entsprechenden Richtlinien für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3c0af-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="3c0af-131">Um die Normalisierungsregeln für die Übersetzung von Telefonnummern, die vom Benutzer in das e. 164-Format gewählt anzugeben, wählen Sie das entsprechende Standortprofil in **Standortrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="3c0af-132">Zum Aktivieren der Remoteanrufsteuerung-Steuerelement, das Benutzer ihre Telefonen über Skype für Business Server so tätigen Anrufe von PC zu PC und Anrufe von Computer zu Telefon steuern kann, klicken Sie auf **die Remoteanrufsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="3c0af-133">Geben Sie im **Anschluss-URI**die Telefonnummer für die Remoteanrufsteuerung.</span><span class="sxs-lookup"><span data-stu-id="3c0af-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="3c0af-134">Der Benutzer benötigen ein herkömmliches Telefon und private Branch Exchange, (Nebenstellenanlage PBX) Verbindung zum Weiterleiten von Anrufen.</span><span class="sxs-lookup"><span data-stu-id="3c0af-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="3c0af-135">Verschieben von Benutzern in einen anderen pool</span><span class="sxs-lookup"><span data-stu-id="3c0af-135">Move users to another pool</span></span>
<span data-ttu-id="3c0af-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="3c0af-136"></span></span>

<span data-ttu-id="3c0af-137">Skype für Business Server-Systemsteuerung können Sie Benutzer zu einem bestimmten Server oder Pool zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3c0af-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="3c0af-138">Verschieben alle vorhandenen Benutzer von einer Quellpool, die Lync Server 2010 ausgeführt wird oder früher in einer Skype für Business Server Zielpool in einer komplexen Active Directory-Umgebung möglicherweise langsamer Active Directory-Replikation.</span><span class="sxs-lookup"><span data-stu-id="3c0af-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="3c0af-139">Um dies zu vermeiden, können Sie Suchfilter verwenden, um Benutzer von Pools zu verschieben, auf denen Lync Server 2010 ausgeführt werden oder zuvor getrennt, oder Sie können Skype für Business Server-Verwaltungsshell verwenden, um Benutzer mit Cmdlets zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="3c0af-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="3c0af-140">Darüber hinaus lässt sich die Funktionalität Filter mit Skype für Business Server-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3c0af-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="3c0af-141">So verschieben Sie ausgewählte Benutzer zu einem anderen Server oder pool</span><span class="sxs-lookup"><span data-stu-id="3c0af-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="3c0af-142">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3c0af-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c0af-143">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3c0af-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3c0af-144">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3c0af-145">Geben Sie im Feld **Suchen Benutzer** alle den ersten Teil der Anzeigename, Vorname, letzte Name, Kontonamen Sicherheitskontenverwaltung (SAM), SIP-Adresse oder Zeile URI Uniform Resource Identifier () für das Benutzerkonto an, dass Sie möchten, und klicken Sie dann auf \*\*Suchen \*\*.</span><span class="sxs-lookup"><span data-stu-id="3c0af-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="3c0af-146">Wählen Sie in der Tabelle einen bestimmten Benutzer oder Benutzer in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="3c0af-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="3c0af-147">Klicken Sie im Menü **Aktion** auf **ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="3c0af-148">Wählen Sie den Pool, den Sie die Benutzer in **zielregistrierungsstellenpool**verschieben möchten, im Menü **Benutzer verschieben**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="3c0af-149">(Optional) Wenn der Zielserver oder-Pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **erzwingen** .</span><span class="sxs-lookup"><span data-stu-id="3c0af-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3c0af-150">Wenn Sie **erzwingen**ausgewählt haben, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten (beispielsweise Konferenzen, die der Benutzer geplant wurde) gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3c0af-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="3c0af-151">Wenn Sie nicht ausgewählt, werden das Konto und die zugehörigen Daten verschoben.</span><span class="sxs-lookup"><span data-stu-id="3c0af-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="3c0af-152">So verschieben Sie alle Benutzer von einem Server oder Pool zu einem anderen Server oder pool</span><span class="sxs-lookup"><span data-stu-id="3c0af-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="3c0af-153">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3c0af-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c0af-154">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3c0af-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3c0af-155">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3c0af-156">Klicken Sie im Menü **Aktion** auf **alle Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="3c0af-157">**Benutzer verschieben**unter Wählen Sie den Pool mit den Benutzerkonten, die Sie in der **Quelle Registrar-Pool**verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="3c0af-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="3c0af-158">Wählen Sie im **zielregistrierungspool**den Pool, dem Sie die Benutzer verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="3c0af-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="3c0af-159">(Optional) Wenn der Zielserver oder-Pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **erzwingen** .</span><span class="sxs-lookup"><span data-stu-id="3c0af-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3c0af-160">Wenn Sie **erzwingen**ausgewählt haben, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten (beispielsweise Konferenzen, die der Benutzer geplant wurde) gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3c0af-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="3c0af-161">Wenn Sie nicht ausgewählt, werden das Konto und die zugehörigen Daten verschoben.</span><span class="sxs-lookup"><span data-stu-id="3c0af-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="3c0af-162">So verschieben Sie Benutzer aus einem Pool in einen anderen Pool mithilfe eines Filters</span><span class="sxs-lookup"><span data-stu-id="3c0af-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="3c0af-163">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3c0af-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c0af-164">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3c0af-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3c0af-165">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3c0af-166">Klicken Sie bei der **Suche für Benutzer**auf **Suchen**, und klicken Sie dann auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="3c0af-167">Wählen Sie in den Suchkriterien **Registrar-Pool aus**, wählen Sie **gleich**, **FQDN des aktuellen Pools**aus, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="3c0af-168">Klicken Sie im Menü **Aktion** auf **alle Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3c0af-169">Wenn ein Filter auf einen vorhandenen Satz von Benutzern, die Option angewendet wird, im Zusammenhang mit der gefilterten Teilmenge der Benutzer, die nicht **Alle** möglichen Benutzer **alle Benutzer in Pool verschieben ist** .</span><span class="sxs-lookup"><span data-stu-id="3c0af-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="3c0af-170">**Benutzer verschieben**unter Wählen Sie den Pool mit den Benutzerkonten, die Sie in der **Quelle Registrar-Pool**verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="3c0af-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="3c0af-171">Wählen Sie im **zielregistrierungspool**den Pool, in dem Sie die Benutzer verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="3c0af-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="3c0af-172">(Optional) Wenn der Zielserver oder-Pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **erzwingen** .</span><span class="sxs-lookup"><span data-stu-id="3c0af-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3c0af-173">Wenn Sie **erzwingen**auswählen, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten (z. B., Konferenzen, die der Benutzer geplant wurde und Kontakte) gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3c0af-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="3c0af-174">Wenn Sie nicht ausgewählt, werden das Konto und die zugehörigen Daten verschoben.</span><span class="sxs-lookup"><span data-stu-id="3c0af-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="3c0af-175">So verschieben Sie Benutzer aus einem Pool in einen anderen mithilfe von Windows Powershell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3c0af-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="3c0af-176">Je nachdem, wie Sie Windows PowerShell-Befehle (d. h., lokal oder Remote) ausgeführt haben müssen Sie sich als Mitglied der richtigen Skype für Administratorrollen Business Server wie folgt auf:</span><span class="sxs-lookup"><span data-stu-id="3c0af-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="3c0af-177">a.</span><span class="sxs-lookup"><span data-stu-id="3c0af-177">a.</span></span> <span data-ttu-id="3c0af-178">Wenn Sie die Befehle auf dem lokalen Computer (beispielsweise beim Anmelden direkt auf einem Front-End-Server) ausgeführt werden: Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen installiert ist, Benutzerrechte, wie beschrieben unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="3c0af-179">b.</span><span class="sxs-lookup"><span data-stu-id="3c0af-179">b.</span></span> <span data-ttu-id="3c0af-180">Wenn Sie die Befehle Remote auf einem anderen Computer ausführen (z. B. Sie melden Sie sich an Ihren Computer und die Befehle Remote auf einem Standard Edition-Front-End-Server ausführen): von einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder die "csadministrator" zugewiesen ist, Rolle, melden Sie sich an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3c0af-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c0af-181">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Unternehmen**und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="3c0af-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3c0af-182">Verwenden Sie das Cmdlet Move-CsUser zum Verschieben einzelner Benutzer wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3c0af-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="3c0af-183">In dem der Benutzer zum Verschieben der Benutzer Pilar Ackerman, und der Benutzer ist wird aus ihrer derzeit zugeordneten Homepool in den Pool pool01.contoso.net verschoben werden</span><span class="sxs-lookup"><span data-stu-id="3c0af-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="3c0af-184">Um eine große Anzahl von Benutzern zu verschieben, Filter mit dem **Get-CsUser** -Cmdlet verwenden, und der Benutzer den daraus resultierenden Benutzersatz an **Move-CsUser**übergeben:</span><span class="sxs-lookup"><span data-stu-id="3c0af-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="3c0af-185">Zusammen können die Befehle **Get-CsUser** und **Move-CsUser** ergeben Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3c0af-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```



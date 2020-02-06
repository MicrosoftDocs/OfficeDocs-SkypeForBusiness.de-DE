---
title: Anpassen der Eigenschaften des Benutzerkontos für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Mit den Verfahren in diesem Abschnitt können Sie einzelne Benutzerkontoeigenschaften ändern.
ms.openlocfilehash: 96885a1f24685eccc85469209dd36ad655c80fed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817065"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="7e2a0-103">Anpassen der Eigenschaften des Benutzerkontos für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7e2a0-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="7e2a0-104">Mit den Verfahren in diesem Abschnitt können Sie einzelne Benutzerkontoeigenschaften ändern.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="7e2a0-105">Es gibt zwei grundlegende Vorgänge, die auf der einzelnen Benutzerebene ausgeführt werden können:</span><span class="sxs-lookup"><span data-stu-id="7e2a0-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="7e2a0-106">Konfigurieren von Telefonoptionen für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="7e2a0-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="7e2a0-107">Verschieben von Benutzern in einen anderen Pool</span><span class="sxs-lookup"><span data-stu-id="7e2a0-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="7e2a0-108">Konfigurieren von Telefonoptionen für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="7e2a0-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="7e2a0-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="7e2a0-109"><a name="Tel_Op"> </a></span></span>

<span data-ttu-id="7e2a0-110">Sie können die Telefoneinstellungen für einen bestimmten Benutzer anpassen (sofern der einzelne Benutzer für Skype for Business Server aktiviert wurde und die Organisation die Telefonie unterstützt).</span><span class="sxs-lookup"><span data-stu-id="7e2a0-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="7e2a0-111">Zu den Skype for Business Server-Optionen für Benutzer Telefonie gehören die folgenden:</span><span class="sxs-lookup"><span data-stu-id="7e2a0-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="7e2a0-112">**Audio/Video deaktiviert** Der Benutzer kann mit Audio und Video keine Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="7e2a0-113">**Nur PC-zu-PC** Der Benutzer kann nur PC-zu-PC-Audio-oder Videoanrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="7e2a0-114">**Enterprise-VoIP** Der Benutzer kann mit der Skype for Business Server-Infrastruktur alle ein-und ausgehenden Anrufe weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="7e2a0-115">Der Benutzer kann auch PC-zu-PC-Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="7e2a0-116">**Remote Anrufsteuerung** Der Benutzer kann Skype for Business Server verwenden, um das Desktoptelefon zu steuern, und kann auch PC-zu-PC-Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="7e2a0-117">Details zum Konfigurieren der Telefonie für eine Organisation finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) und [Bereitstellen von Enterprise-VoIP in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="7e2a0-118">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7e2a0-119">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="7e2a0-120">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="7e2a0-121">Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="7e2a0-122">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="7e2a0-123">Klicken Sie im Menü **Bearbeiten** auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="7e2a0-124">Führen Sie in **Telefonie**die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="7e2a0-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="7e2a0-125">Wenn Sie Audio-und Videoanrufe für den Benutzer deaktivieren möchten, klicken Sie auf **Audio/Video deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="7e2a0-126">Wenn Sie die PC-zu-PC-Audiokommunikation für den Benutzer, aber nicht die Remoteanrufsteuerung oder Enterprise-VoIP aktivieren möchten, klicken Sie auf **nur PC-zu-** PC.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="7e2a0-127">Geben Sie einen Wert für den **Leitungs-URI** für das Telefon an, das der Benutzer für die PC-zu-PC-Audiokommunikation verwendet.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="7e2a0-128">Klicken Sie auf **Enterprise-VoIP**, um die Telefonanrufe des Benutzers über die Skype for Business-Infrastruktur in Übereinstimmung mit der Service Richtlinienklasse zu leiten, einschließlich der PC-zu-PC-Audiokommunikation.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="7e2a0-129">Geben Sie in der **Zeile URI**die Telefonnummer für Enterprise-VoIP an.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="7e2a0-130">Geben Sie in der Richtlinie für **Wähl Plan Richtlinien** und **VoIP**die entsprechenden Richtlinien für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="7e2a0-131">Wenn Sie die Normalisierungsregeln für die Übersetzung von Telefonnummern angeben möchten, die vom Benutzer im E. 164-Format gewählt wurden, wählen Sie das entsprechende Standortprofil in der **ortungsrichtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="7e2a0-132">Klicken Sie auf **Remoteanrufsteuerung**, um die Remoteanrufsteuerung zu aktivieren, mit der Benutzer Ihre Desktop-Telefonleitung von Skype for Business Server steuern können, um PC-zu-PC-Anrufe zu tätigen und PC-zu-Telefon-Anrufe zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="7e2a0-133">Geben Sie in der **Zeile URI**die Telefonnummer für die Remoteanrufsteuerung ein.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="7e2a0-134">Der Benutzer muss über ein Desktoptelefon und eine PBX-Verbindung (Private Branch Exchange) für das Anrufrouting verfügen.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="7e2a0-135">Verschieben von Benutzern in einen anderen Pool</span><span class="sxs-lookup"><span data-stu-id="7e2a0-135">Move users to another pool</span></span>
<span data-ttu-id="7e2a0-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="7e2a0-136"><a name="Move_Users"> </a></span></span>

<span data-ttu-id="7e2a0-137">Sie können die Skype for Business Server-Systemsteuerung verwenden, um Benutzer einem bestimmten Server oder Pool zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="7e2a0-138">Das Verschieben aller vorhandenen Benutzer aus einem Quell Pool, auf dem lync Server 2010 oder früher ausgeführt wird, zu einem Skype for Business Server-Ziel Pool in einer komplexen Active Directory-Umgebung kann zu einer langsameren Active Directory-Replikation führen.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="7e2a0-139">Um dies zu vermeiden, können Sie mithilfe von Suchfiltern Benutzer aus Pools verschieben, auf denen lync Server 2010 oder früher separat ausgeführt wird, oder Sie können die Skype for Business Server-Verwaltungsshell verwenden, um Benutzer mit Cmdlets zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="7e2a0-140">Die Filterfunktionalität funktioniert auch mit Skype for Business Server-Benutzern.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="7e2a0-141">So verschieben Sie ausgewählte Benutzer auf einen anderen Server oder Pool</span><span class="sxs-lookup"><span data-stu-id="7e2a0-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="7e2a0-142">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7e2a0-143">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7e2a0-144">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="7e2a0-145">Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="7e2a0-146">Wählen Sie in der Tabelle einen bestimmten Benutzer oder Benutzer in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="7e2a0-147">Klicken Sie im Menü **Aktion** auf **ausgewählte Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="7e2a0-148">Wählen Sie in **Benutzer verschieben**den Pool aus, in den Sie die Benutzer in den **Ziel Registrierungspool**verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="7e2a0-149">Optional Aktivieren Sie das Kontrollkästchen **erzwingen** , wenn der Zielserver oder-Pool nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="7e2a0-150">Wenn Sie **erzwingen**auswählen, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (beispielsweise Konferenzen, die der Benutzer geplant hat).</span><span class="sxs-lookup"><span data-stu-id="7e2a0-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="7e2a0-151">Wenn Sie diese Option nicht auswählen, werden sowohl das Konto als auch die zugehörigen Daten verschoben.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="7e2a0-152">So verschieben Sie alle Benutzer von einem Server oder Pool auf einen anderen Server oder Pool</span><span class="sxs-lookup"><span data-stu-id="7e2a0-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="7e2a0-153">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7e2a0-154">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7e2a0-155">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="7e2a0-156">Klicken Sie im Menü **Aktion** auf **alle Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="7e2a0-157">Wählen Sie in **Benutzer verschieben**den Pool aus, der die Benutzerkonten enthält, die Sie im **Quell Registrierungspool**verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="7e2a0-158">Wählen Sie im **Ziel Registrierungspool**den Pool aus, in den Sie die Benutzer verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="7e2a0-159">Optional Aktivieren Sie das Kontrollkästchen **erzwingen** , wenn der Zielserver oder-Pool nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="7e2a0-160">Wenn Sie **erzwingen**auswählen, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (beispielsweise Konferenzen, die der Benutzer geplant hat).</span><span class="sxs-lookup"><span data-stu-id="7e2a0-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="7e2a0-161">Wenn Sie diese Option nicht auswählen, werden sowohl das Konto als auch die zugehörigen Daten verschoben.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="7e2a0-162">So verschieben Sie Benutzer mithilfe eines Filters aus einem Pool in einen anderen Pool</span><span class="sxs-lookup"><span data-stu-id="7e2a0-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="7e2a0-163">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7e2a0-164">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="7e2a0-165">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="7e2a0-166">Klicken Sie in der **Benutzersuche**auf **Suchen**, und klicken Sie dann auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="7e2a0-167">Wählen Sie in den Suchkriterien den Eintrag **Registrierungspool**aus, wählen Sie **gleich**aus, wählen Sie **Aktueller Pool-FQDN**aus, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="7e2a0-168">Klicken Sie im Menü **Aktion** auf **alle Benutzer in Pool verschieben**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7e2a0-169">Wenn ein Filter auf eine vorhandene Gruppe von Benutzern angewendet wird, befindet sich die Option **alle Benutzer in Pool verschieben** im Kontext der gefilterten Teilmenge von Benutzern, nicht **aller** möglichen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="7e2a0-170">Wählen Sie in **Benutzer verschieben**den Pool aus, der die Benutzerkonten enthält, die Sie im **Quell Registrierungspool**verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="7e2a0-171">Wählen Sie im **Ziel Registrierungspool**den Pool aus, in den Sie die Benutzer verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="7e2a0-172">Optional Aktivieren Sie das Kontrollkästchen **erzwingen** , wenn der Zielserver oder-Pool nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="7e2a0-173">Wenn Sie **erzwingen**auswählen, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (beispielsweise Konferenzen, die der Benutzer geplant hat, und Kontakte).</span><span class="sxs-lookup"><span data-stu-id="7e2a0-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="7e2a0-174">Wenn Sie diese Option nicht auswählen, werden sowohl das Konto als auch die zugehörigen Daten verschoben.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="7e2a0-175">So verschieben Sie Benutzer mithilfe von Windows PowerShell-Cmdlets aus einem Pool in einen anderen</span><span class="sxs-lookup"><span data-stu-id="7e2a0-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="7e2a0-176">Je nachdem, wie Sie Windows PowerShell-Befehle ausführen (lokal oder Remote), müssen Sie sich wie folgt als Mitglied der richtigen Skype for Business Server-Administratorrolle anmelden:</span><span class="sxs-lookup"><span data-stu-id="7e2a0-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="7e2a0-177">a.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-177">a.</span></span> <span data-ttu-id="7e2a0-178">Wenn Sie die Befehle auf dem lokalen Computer ausführen (beispielsweise melden Sie sich direkt bei einem Front-End-Server an): Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe installiert ist, oder mit den erforderlichen Benutzerrechten, wie unter **Delegieren von Setup Berechtigungen**beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="7e2a0-179">b.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-179">b.</span></span> <span data-ttu-id="7e2a0-180">Wenn Sie die Befehle Remote auf einem anderen Computer ausführen (beispielsweise melden Sie sich bei Ihrem Computer an, und führen Sie die Befehle Remote auf einem Standard Edition-Front-End-Server aus): von einem Benutzerkonto, das der CsUserAdministrator-Rolle oder dem CsAdministrator zugewiesen ist. Rolle, melden Sie sich bei einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7e2a0-181">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for**Business, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="7e2a0-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7e2a0-182">Verwenden Sie zum Verschieben einzelner Benutzer das Cmdlet Move-CsUser wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7e2a0-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="7e2a0-183">Der Benutzer, der verschoben werden soll, ist der Benutzer Pilar Ackerman, und der Benutzer wird aus dem aktuell zugewiesenen privaten Pool in den Pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7e2a0-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="7e2a0-184">Wenn Sie eine große Anzahl von Benutzern verschieben möchten, verwenden Sie Filter mit dem Cmdlet **Get-CsUser** , und übergeben Sie die resultierenden Benutzersätze an **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="7e2a0-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="7e2a0-185">Die kombinierten Befehle von **Get-CsUser** und **Move-CsUser** können dazu führen:</span><span class="sxs-lookup"><span data-stu-id="7e2a0-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```



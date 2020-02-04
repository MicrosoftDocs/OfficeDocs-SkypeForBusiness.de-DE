---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc79a915d0735f87c0852dff0ba4228b1e391fd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="948d9-102">Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="948d9-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="948d9-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="948d9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="948d9-104">Diese Dokumentation ist vorläufig und kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="948d9-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="948d9-105">Leere Themen sind als Platzhalter enthalten.</span><span class="sxs-lookup"><span data-stu-id="948d9-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="948d9-106">Wenn Sie Richtlinien für die Unterstützung von Verbundpartnern des Extensible Messaging and Presence Protocol (XMPP) konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Verbunddomänen, nicht aber für Benutzer von SIP-Chat Diensten (im). (beispielsweise Windows Live) oder SIP-Verbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="948d9-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="948d9-107">Sie konfigurieren einen **XMPP-Verbund Partner** für jede XMPP-Verbunddomäne, die es Ihren Benutzern ermöglichen soll, Kontakte hinzuzufügen und mit Ihnen zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="948d9-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="948d9-108">Die XMPP-Partner Richtlinien sind nur in einem einzigen Bereich verfügbar, obwohl Sie nicht als globale Richtlinie definiert sind und als globale Richtlinie fungieren.</span><span class="sxs-lookup"><span data-stu-id="948d9-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="948d9-109">Wenn Sie eine globale, Website-oder Benutzerrichtlinie für XMPP-Verbundpartner definieren möchten, konfigurieren Sie den Richtlinienbereich, indem Sie zunächst die Richtlinie für den externen Zugriff für den erforderlichen Bereich erstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="948d9-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="948d9-110">Details zu den Richtlinientypen, die Sie für den externen Zugriff und den Verbund konfigurieren können, finden Sie unter [Verwalten des Föderations-und des externen Zugriffs auf lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="948d9-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="948d9-111">Alle Richtlinien für den <STRONG>Verbund und den externen Zugriff</STRONG> werden über die in-Band-Bereitstellung angewendet.</span><span class="sxs-lookup"><span data-stu-id="948d9-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="948d9-112">Die Richtlinien, die für den Benutzer gelten, zu einer Website gehören oder im Bereich Global sind, werden dem Client während der Anmeldung mitgeteilt.</span><span class="sxs-lookup"><span data-stu-id="948d9-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="948d9-113">Sie können Richtlinien konfigurieren, um den Zugriff auf XMPP-Verbundpartner zu steuern, auch wenn Sie die XMPP-Föderation für Ihre Organisation nicht aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="948d9-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="948d9-114">Die von Ihnen konfigurierten Richtlinien werden jedoch nur wirksam, wenn Sie die XMPP-Partner Föderation bereitgestellt, für Ihre Organisation aktiviert und konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="948d9-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="948d9-115">Details zum Bereitstellen und Konfigurieren von XMPP-Partnerverbund finden Sie unter <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Konfigurieren von SIP Federation, XMPP Federation und Public Instant Messaging in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="948d9-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="948d9-116">Wenn Sie eine Benutzerrichtlinie in der Richtlinie für den externen Zugriff zum Steuern von XMPP-Verbundpartnern angeben, gilt die Richtlinie nur für Benutzer, die für lync Server 2013 aktiviert und für die Verwendung der Richtlinie konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="948d9-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="948d9-117">So bearbeiten Sie eine globale Richtlinie für XMPP-Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="948d9-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="948d9-118">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="948d9-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="948d9-119">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="948d9-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="948d9-120">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="948d9-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="948d9-121">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="948d9-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="948d9-122">Führen Sie auf der Seite " **Richtlinie für den externen Zugriff** " die folgenden Schritte für die globale Richtlinie aus:</span><span class="sxs-lookup"><span data-stu-id="948d9-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="948d9-123">Klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf Details anzeigen.</span><span class="sxs-lookup"><span data-stu-id="948d9-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="948d9-124">Geben Sie eine Beschreibung für die globale Richtlinie an (optional).</span><span class="sxs-lookup"><span data-stu-id="948d9-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="948d9-125">Wählen Sie **Kommunikation mit Verbundbenutzern aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="948d9-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="948d9-126">Wählen Sie **Kommunikation mit XMPP-Verbundbenutzern aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="948d9-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="948d9-127">Klicken Sie auf **Commit** , um Ihre Änderungen an der globalen Richtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="948d9-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="948d9-128">So erstellen Sie eine Website-oder Benutzerrichtlinie für XMPP-Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="948d9-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="948d9-129">Klicken Sie auf **neu**, und klicken Sie dann auf **Website Richtlinie** oder **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="948d9-129">Click **New**, and then click **Site policy** or **User policy**.</span></span> <span data-ttu-id="948d9-130">Klicken Sie unter **Website auswählen**auf die entsprechende Website in der Liste, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="948d9-130">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="948d9-131">Geben Sie eine Beschreibung für die Website Richtlinie an (optional).</span><span class="sxs-lookup"><span data-stu-id="948d9-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="948d9-132">Wählen Sie in der Website-oder Benutzerrichtlinie die Option **Kommunikation mit Verbundbenutzern aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="948d9-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="948d9-133">Wählen Sie **Kommunikation mit XMPP-Verbundbenutzern aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="948d9-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="948d9-134">Klicken Sie auf **Commit** , um Ihre Änderungen an der Website-oder Benutzerrichtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="948d9-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="948d9-135">So bearbeiten Sie eine vorhandene Richtlinie für XMPP-Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="948d9-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="948d9-136">Wenn Sie eine vorhandene Richtlinie ändern möchten, wählen Sie die entsprechende Richtlinie in der Liste aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="948d9-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="948d9-137">Ändern oder aktualisieren Sie die Beschreibung für die Richtlinie (optional).</span><span class="sxs-lookup"><span data-stu-id="948d9-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="948d9-138">Aktivieren oder deaktivieren Sie die Option **Kommunikation mit Verbundbenutzern aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="948d9-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="948d9-139">Aktivieren oder deaktivieren Sie die Option **Kommunikation mit XMPP-Verbundbenutzern aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="948d9-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="948d9-140">Klicken Sie auf **Commit** , um Ihre Änderungen an der Richtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="948d9-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="948d9-141">So bearbeiten Sie eine vorhandene Richtlinie für XMPP-Verbundpartner mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="948d9-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="948d9-142">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="948d9-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="948d9-143">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="948d9-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="948d9-144">Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="948d9-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="948d9-145">Ein Beispielbefehl, mit dem die globale Richtlinie für den Zugriff durch den Verbundbenutzer auf true (aktiviert) und XMPP-Domänenzugriff auf true festgelegt wird (aktiviert):</span><span class="sxs-lookup"><span data-stu-id="948d9-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="948d9-146">So erstellen Sie eine Website-oder Benutzerrichtlinie für XMPP-Verbundpartner mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="948d9-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="948d9-147">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="948d9-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="948d9-148">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="948d9-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="948d9-149">Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="948d9-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="948d9-150">Ein Beispielbefehl, der eine Website Richtlinie für die Website "Redmond" für den Verbundbenutzer Zugriff auf den aktivierten und XMPP-Domänenzugriff auf "aktiviert" setzt:</span><span class="sxs-lookup"><span data-stu-id="948d9-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="948d9-151">So löschen Sie eine vorhandene Richtlinie für XMPP-Verbundpartner mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="948d9-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="948d9-152">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="948d9-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="948d9-153">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="948d9-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="948d9-154">Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="948d9-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="948d9-155">Ein Beispielbefehl, mit dem eine Benutzerrichtlinie gelöscht wird:</span><span class="sxs-lookup"><span data-stu-id="948d9-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="948d9-156">Ein Beispielbefehl, mit dem die globale Richtlinie auf Standardwerte zurückgesetzt wird:</span><span class="sxs-lookup"><span data-stu-id="948d9-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="948d9-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="948d9-157">See Also</span></span>


[<span data-ttu-id="948d9-158">Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="948d9-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="948d9-159">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="948d9-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="948d9-160">Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="948d9-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="948d9-161">Satz-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="948d9-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="948d9-162">Neu – CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="948d9-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="948d9-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="948d9-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="948d9-164">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="948d9-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="948d9-165">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="948d9-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Verwalten von SIP-Partnerverbundanbietern für eine Organisation
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Informationen Sie zum Konfigurieren der Unterstützung für Benutzer von SIP-partnerverbundanbietern zu aktivieren.
ms.openlocfilehash: 1259ae9d2dfd7d829caaa6dba714f0876b5500c4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899673"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="2086d-103">Verwalten der Anbieter für Ihre Organisation in Skype für Business Server SIP-Verbund</span><span class="sxs-lookup"><span data-stu-id="2086d-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="2086d-104">Zum Konfigurieren der Unterstützung für Benutzer von SIP-partnerverbundanbietern zu aktivieren, müssen Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="2086d-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="2086d-105">Konfigurieren Sie eine oder mehrere externe Benutzer Zugriffsrichtlinien zur Unterstützung bei der Kommunikation mit SIP-partnerverbundanbieter-Kontakten</span><span class="sxs-lookup"><span data-stu-id="2086d-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="2086d-106">Geben Sie an welche gehosteten Anbieter Sie unterstützen möchten</span><span class="sxs-lookup"><span data-stu-id="2086d-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="2086d-107">Geben Sie die öffentlichen IM-Dienstanbieter, die Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="2086d-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="2086d-108">Erstellen oder Bearbeiten von öffentlichen SIP-Verbund-Dienstanbieter in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="2086d-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="2086d-109">Öffentliche instant messaging (IM)-Diensten kann Benutzer in Ihrer Organisation, per Sofortnachricht mit Benutzern von Instant Messaging-Dienste öffentliche Anbieter kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="2086d-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="2086d-110">Skype für Business Server hat Sofortnachrichtendienst Konfigurationen für instant messaging.</span><span class="sxs-lookup"><span data-stu-id="2086d-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="2086d-111">Jeden öffentlichen Anbieter wird mit der Anbieter Edge Server vollqualifizierten Domänennamen und die Überprüfung Standardstufe **durch Benutzer zulassen für die Kommunikation nur mit Personen in ihrer Liste Kontakte, die für die Verwendung dieses Anbieters,** konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2086d-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="2086d-112">Als Standard festlegen werden keine der öffentlichen Anbieter aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2086d-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="2086d-113">Schließen Sie die Lizenzvertrag sowie die Bereitstellung von Arbeit, bevor Sie öffentliche Anbieter aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2086d-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="2086d-114">Sie können den Anbieter aktivieren, vor dem Abschließen der Lizenzierung und Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="2086d-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="2086d-115">Benutzer werden nicht kommunizieren mit Kontakten auf die Anbieter, bis die Untersuchung Arbeit abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2086d-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="2086d-116">Details zu Lizenzierung und Bereitstellung der öffentlichen Anbieter finden Sie unter [Configure Policies öffentliche Benutzer hinsichtlich steuern](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2086d-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="2086d-117">Verwenden Sie das folgende Verfahren zum Erstellen oder bearbeiten Sie öffentliche Anbieter.</span><span class="sxs-lookup"><span data-stu-id="2086d-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="2086d-118">So erstellen oder bearbeiten Sie öffentliche Anbieter</span><span class="sxs-lookup"><span data-stu-id="2086d-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="2086d-119">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="2086d-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2086d-120">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2086d-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2086d-121">Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff**und klicken Sie dann auf **SIP Federated Providers**.</span><span class="sxs-lookup"><span data-stu-id="2086d-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="2086d-122">Wenn Sie einen öffentlichen Anbieter erstellen müssen, klicken Sie auf **neu** , und klicken Sie dann auf **öffentlicher Anbieter**.</span><span class="sxs-lookup"><span data-stu-id="2086d-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="2086d-123">Wenn Sie einen Eintrag aus der Liste der Dienstanbieter bearbeiten müssen, wählen Sie einen öffentlichen Anbieter aus, klicken Sie auf **Bearbeiten**und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2086d-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="2086d-124">Auf der Seite **SIP-Verbund-Dienstanbieter bearbeiten** können Sie eingeben oder bearbeiten die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="2086d-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="2086d-125">**Kommunikation mit diesem Anbieter aktivieren**   Instant Messaging mit diesem Anbieter Benutzern ermöglicht diese Einstellung auswählen.</span><span class="sxs-lookup"><span data-stu-id="2086d-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="2086d-126">**Anbietername:**   eine erforderliche Eigenschaft; geben, die der Namen des Anbieters wie er in der Liste der SIP Federated Providers nachvollzogen werden.</span><span class="sxs-lookup"><span data-stu-id="2086d-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="2086d-127">**Zugriffs-edgedienst (FQDN):**   eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Zugriffs-edgedienst des Anbieters, die Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2086d-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="2086d-128">Diese Informationen als ein Standardelement bereitgestellt wird und sollte nur geändert werden, wenn Sie der öffentliche Anbieter eine Änderung an den FQDN des Zugriffs-edgediensts an den öffentlichen Anbieter vornimmt.</span><span class="sxs-lookup"><span data-stu-id="2086d-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="2086d-129">**Default Überprüfungsstufen:**   die Standardeinstellung beschränken **Benutzern erlauben, kommunizieren mit Personen in ihrer Liste Kontakte, die für die Verwendung dieses Anbieters,** Kommunikation mit Kontakten, die Sie akzeptiert haben und in der Kontaktliste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2086d-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="2086d-130">Auswählen von **Benutzern erlauben, die für alle Benutzer mit diesem Anbieter kommunizieren** entfernt die Einschränkung, dass Sie empfangen und einen Kontakt einladen akzeptiert haben müssen.</span><span class="sxs-lookup"><span data-stu-id="2086d-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="2086d-131">Diese Einstellung schränkt nicht, die Sie aus den öffentlichen Anbieter Netzwerk wenden können.</span><span class="sxs-lookup"><span data-stu-id="2086d-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="2086d-132">Wenn Sie sind Konfigurieren der Einstellungen, klicken Sie auf **Commit** , zu speichern oder klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="2086d-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="2086d-133">Erstellen oder Bearbeiten von gehosteten Anbietern von SIP-Verbund in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="2086d-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="2086d-134">Gehostete Anbieter instant messaging (IM)-Konnektivität können Benutzer in Ihrer Organisation, um Sofortnachrichten zu verwenden, um die Kommunikation mit Benutzern von Instant Messaging-Diensten von gehosteten Anbietern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2086d-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="2086d-135">Jede gehosteten Anbieter wird mit der Anbieter Edge Server vollqualifizierten Domänennamen und die Überprüfung Standardstufe **durch Benutzer zulassen für die Kommunikation nur mit Personen in ihrer Liste Kontakte, die für die Verwendung dieses Anbieters,** konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2086d-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="2086d-136">Verwenden Sie das folgende Verfahren zum Erstellen oder bearbeiten Sie gehostete Anbieter.</span><span class="sxs-lookup"><span data-stu-id="2086d-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="2086d-137">So erstellen oder bearbeiten Sie gehostete Anbieter</span><span class="sxs-lookup"><span data-stu-id="2086d-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="2086d-138">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="2086d-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2086d-139">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2086d-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2086d-140">Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff**und klicken Sie dann auf **SIP Federated Providers**.</span><span class="sxs-lookup"><span data-stu-id="2086d-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="2086d-141">Wenn Sie einen neuen gehosteten Anbieter erstellen müssen, klicken Sie auf **neu** , und klicken Sie dann auf **gehosteter Anbieter**.</span><span class="sxs-lookup"><span data-stu-id="2086d-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="2086d-142">Wenn Sie einen Eintrag aus der Liste der gehosteten Anbieter bearbeiten müssen, wählen Sie einen gehosteten Anbieter aus, klicken Sie auf **Bearbeiten**und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2086d-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="2086d-143">Auf der Seite **SIP-Verbund-Dienstanbieter bearbeiten** können Sie eingeben oder bearbeiten die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="2086d-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="2086d-144">**Kommunikation mit diesem Anbieter aktivieren**   ermöglicht die Kommunikation mit diesem Anbieter Benutzer diese Einstellung auswählen.</span><span class="sxs-lookup"><span data-stu-id="2086d-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="2086d-145">**Anbietername:**   eine erforderliche Eigenschaft; geben, die der Namen des Anbieters wie er in der Liste der SIP Federated Providers nachvollzogen werden.</span><span class="sxs-lookup"><span data-stu-id="2086d-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="2086d-146">**Zugriffs-edgedienst (FQDN):**   eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Zugriffs-edgedienst der gehosteten Anbieter, den Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2086d-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="2086d-147">Diese Informationen vom gehosteten Anbieter bereitgestellt werden soll, und sollte nur geändert werden, wenn der gehostete Anbieter eine Änderung an den FQDN des Zugriffs-edgediensts auf den gehosteten Anbieter vornimmt.</span><span class="sxs-lookup"><span data-stu-id="2086d-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="2086d-148">**Default Überprüfungsstufen:**   die Standardeinstellung beschränken **Benutzern erlauben, kommunizieren mit Personen in ihrer Liste Kontakte, die für die Verwendung dieses Anbieters,** Kommunikation mit Kontakten, die Sie akzeptiert haben und in der Kontaktliste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2086d-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="2086d-149">Auswählen von **Benutzern erlauben, die für alle Benutzer mit diesem Anbieter kommunizieren** entfernt die Einschränkung, dass Sie empfangen und einen Kontakt einladen akzeptiert haben müssen.</span><span class="sxs-lookup"><span data-stu-id="2086d-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="2086d-150">Diese Einstellung schränkt nicht, die Sie aus der gehosteten Anbieter Netzwerk wenden können.</span><span class="sxs-lookup"><span data-stu-id="2086d-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="2086d-151">Wenn Sie sind Konfigurieren der Einstellungen, klicken Sie auf **Commit** , zu speichern oder klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="2086d-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="2086d-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2086d-152">See Also</span></span>


[<span data-ttu-id="2086d-153">Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzer hinsichtlich</span><span class="sxs-lookup"><span data-stu-id="2086d-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="2086d-154">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten</span><span class="sxs-lookup"><span data-stu-id="2086d-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)


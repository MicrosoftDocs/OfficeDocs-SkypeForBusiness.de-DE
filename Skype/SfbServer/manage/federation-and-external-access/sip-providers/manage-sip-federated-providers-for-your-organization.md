---
title: Verwalten von SIP-Partnerverbundanbietern für eine Organisation
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Hier erfahren Sie, wie Sie die Unterstützung für Benutzer von SIP-Verbund Anbietern konfigurieren.
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818366"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="ef446-103">Verwalten von SIP-Verbund Anbietern für Ihre Organisation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ef446-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="ef446-104">Wenn Sie die Unterstützung für Benutzer von SIP-Verbund Anbietern konfigurieren möchten, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ef446-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="ef446-105">Konfigurieren einer oder mehrerer externer Benutzerzugriffs Richtlinien zur Unterstützung der Kommunikation mit SIP-Föderations Dienstanbieter-Kontakten</span><span class="sxs-lookup"><span data-stu-id="ef446-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="ef446-106">Angeben, welche gehosteten Anbieter unterstützt werden sollen</span><span class="sxs-lookup"><span data-stu-id="ef446-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="ef446-107">Angeben, welche öffentlichen Chat Anbieter Sie unterstützen möchten</span><span class="sxs-lookup"><span data-stu-id="ef446-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="ef446-108">Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ef446-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="ef446-109">Mit der öffentlichen Instant Messaging-Konnektivität (im) können Benutzer in Ihrer Organisation Chatnachrichten verwenden, um mit Benutzern der Chat Dienste zu kommunizieren, die von öffentlichen Anbietern bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ef446-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="ef446-110">Skype for Business Server verfügt über öffentliche Anbieter Konfigurationen für Chatnachrichten.</span><span class="sxs-lookup"><span data-stu-id="ef446-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="ef446-111">Jeder öffentliche Anbieter ist mit dem vollqualifizierten Domänennamen für den Edge-Server des Anbieters konfiguriert, und die Standard Überprüfungsstufe **ermöglicht Benutzern, nur mit Personen in der Kontaktliste zu kommunizieren, die diesen Anbieter verwenden**.</span><span class="sxs-lookup"><span data-stu-id="ef446-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="ef446-112">Als Standardeinstellung ist keiner der öffentlichen Anbieter aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ef446-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="ef446-113">Sie sollten den Lizenzvertrag und die Bereitstellungs Arbeit abschließen, bevor Sie die öffentlichen Anbieter aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ef446-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="ef446-114">Sie können den Anbieter aktivieren, bevor Sie die Lizenzierung und Bereitstellungs Arbeit abschließen.</span><span class="sxs-lookup"><span data-stu-id="ef446-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="ef446-115">Die Benutzer können erst dann mit Kontakten an diesen Anbietern kommunizieren, wenn die Voraussetzungen für die Arbeit erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="ef446-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="ef446-116">Einzelheiten zur Lizenzierung und Bereitstellung von öffentlichen Anbietern finden Sie unter [Konfigurieren von Richtlinien für den Zugriff durch öffentliche Benutzer](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ef446-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="ef446-117">Gehen Sie wie folgt vor, um öffentliche Anbieter zu erstellen oder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ef446-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="ef446-118">So erstellen oder bearbeiten Sie öffentliche Anbieter</span><span class="sxs-lookup"><span data-stu-id="ef446-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="ef446-119">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ef446-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ef446-120">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ef446-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ef446-121">Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff**, und klicken Sie dann auf **SIP-Verbund Anbieter**.</span><span class="sxs-lookup"><span data-stu-id="ef446-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="ef446-122">Wenn Sie einen neuen öffentlichen Anbieter erstellen müssen, klicken Sie auf **neu** , und klicken Sie dann auf **öffentlicher Anbieter**.</span><span class="sxs-lookup"><span data-stu-id="ef446-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="ef446-123">Wenn Sie einen Eintrag aus der Liste der öffentlichen Anbieter bearbeiten möchten, wählen Sie einen öffentlichen Anbieter aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ef446-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="ef446-124">Auf der Seite **SIP-Verbund Anbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="ef446-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="ef446-125">**Aktivieren der Kommunikation mit diesem Anbieter**   Wenn Sie diese Einstellung auswählen, wird im mit den Benutzern dieses Anbieters aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ef446-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="ef446-126">**Anbietername:**   eine erforderliche Eigenschaft, geben Sie den Namen des Anbieters ein, wie er in der Liste der SIP-Verbund Anbieter wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ef446-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="ef446-127">**Access Edge Service (FQDN):**   eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Access-Edgedienst des Anbieters ein, den Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ef446-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="ef446-128">Diese Informationen werden als Standardelement bereitgestellt und sollten nur geändert werden, wenn der öffentliche Anbieter eine Änderung an dem FQDN des Access Edge-Diensts beim öffentlichen Anbieter vornimmt.</span><span class="sxs-lookup"><span data-stu-id="ef446-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="ef446-129">**Standard Überprüfungsstufe:**   die Standardeinstellung, die es **Benutzern ermöglicht, mit Personen in Ihrer Kontaktliste zu kommunizieren, die diesen Anbieter verwenden** , beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.</span><span class="sxs-lookup"><span data-stu-id="ef446-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="ef446-130">**Wenn Sie Benutzern erlauben, mit allen Personen zu kommunizieren, die diesen Anbieter verwenden, wird** die Einschränkung entfernt, die Sie erhalten haben und eine Kontakt Einladung akzeptieren müssen.</span><span class="sxs-lookup"><span data-stu-id="ef446-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="ef446-131">Diese Einstellung beschränkt nicht, wer Sie aus dem Netzwerk des öffentlichen Anbieters kontaktieren kann.</span><span class="sxs-lookup"><span data-stu-id="ef446-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="ef446-132">Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, klicken **Sie zum Speichern auf übernehmen** , oder klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="ef446-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="ef446-133">Erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ef446-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="ef446-134">Mit der Instant Messaging-Konnektivität (im) des gehosteten Anbieters können Benutzer in Ihrer Organisation Chatnachrichten verwenden, um mit Benutzern der Chat Dienste zu kommunizieren, die von gehosteten Anbietern bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ef446-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="ef446-135">Jeder gehostete Anbieter ist mit dem vollqualifizierten Domänennamen für den Edge-Server des Anbieters konfiguriert, und die Standard Überprüfungsstufe **ermöglicht Benutzern, nur mit Personen in Ihrer Kontaktliste zu kommunizieren, die diesen Anbieter verwenden**.</span><span class="sxs-lookup"><span data-stu-id="ef446-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="ef446-136">Gehen Sie wie folgt vor, um gehostete Anbieter zu erstellen oder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ef446-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="ef446-137">So erstellen oder bearbeiten Sie gehostete Anbieter</span><span class="sxs-lookup"><span data-stu-id="ef446-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="ef446-138">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ef446-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ef446-139">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ef446-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ef446-140">Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff**, und klicken Sie dann auf **SIP-Verbund Anbieter**.</span><span class="sxs-lookup"><span data-stu-id="ef446-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="ef446-141">Wenn Sie einen neuen gehosteten Anbieter erstellen müssen, klicken Sie auf **neu** , und klicken Sie dann auf **gehosteter Anbieter**.</span><span class="sxs-lookup"><span data-stu-id="ef446-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="ef446-142">Wenn Sie einen Eintrag aus der Liste der gehosteten Anbieter bearbeiten möchten, wählen Sie einen gehosteten Anbieter aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ef446-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="ef446-143">Auf der Seite **SIP-Verbund Anbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="ef446-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="ef446-144">**Aktivieren der Kommunikation mit diesem Anbieter**   durch Auswählen dieser Einstellung wird die Kommunikation mit den Benutzern dieses Anbieters aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ef446-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="ef446-145">**Anbietername:**   eine erforderliche Eigenschaft, geben Sie den Namen des Anbieters ein, wie er in der Liste der SIP-Verbund Anbieter wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ef446-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="ef446-146">**Access Edge Service (FQDN):**   eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Access Edge-Diensts des gehosteten Anbieters ein, den Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ef446-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="ef446-147">Diese Informationen sollten vom gehosteten Anbieter bereitgestellt werden und sollten nur geändert werden, wenn der gehostete Anbieter eine Änderung an dem FQDN des Access Edge-Diensts beim gehosteten Anbieter vornimmt.</span><span class="sxs-lookup"><span data-stu-id="ef446-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="ef446-148">**Standard Überprüfungsstufe:**   die Standardeinstellung, die es **Benutzern ermöglicht, mit Personen in Ihrer Kontaktliste zu kommunizieren, die diesen Anbieter verwenden** , beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.</span><span class="sxs-lookup"><span data-stu-id="ef446-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="ef446-149">**Wenn Sie Benutzern erlauben, mit allen Personen zu kommunizieren, die diesen Anbieter verwenden, wird** die Einschränkung entfernt, die Sie erhalten haben und eine Kontakt Einladung akzeptieren müssen.</span><span class="sxs-lookup"><span data-stu-id="ef446-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="ef446-150">Diese Einstellung beschränkt nicht, wer Sie aus dem Netzwerk des gehosteten Anbieters kontaktieren kann.</span><span class="sxs-lookup"><span data-stu-id="ef446-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="ef446-151">Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, klicken **Sie zum Speichern auf übernehmen** , oder klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="ef446-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="ef446-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef446-152">See Also</span></span>


[<span data-ttu-id="ef446-153">Konfigurieren von Richtlinien für den Zugriff durch öffentliche Benutzer</span><span class="sxs-lookup"><span data-stu-id="ef446-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="ef446-154">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten</span><span class="sxs-lookup"><span data-stu-id="ef446-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)


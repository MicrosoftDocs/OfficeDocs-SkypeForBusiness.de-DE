---
title: Bereitstellen von Telefonen für Skype for Business Online
description: Hier erfahren Sie die Schritte zur Bereitstellung, um die richtige Firmware erhalten möchten, aktualisieren sie bei Bedarf, Zuweisen von Lizenzen und Konfigurieren von Einstellungen für Telefone in öffentlichen Bereichen.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
ms.openlocfilehash: 453f9db6a022e924406594c567ea564b10f58694
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2018
---
## <a name="common-area-phones"></a><span data-ttu-id="d6dad-103">Telefone in öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="d6dad-103">Common Area Phones</span></span>
<span data-ttu-id="d6dad-104">Ein Telefon im öffentlichen Bereich oder Cap hat, wird in der Regel in einem freigegebenen Bereich platziert und nicht mit einem einzelnen Benutzer verknüpft.</span><span class="sxs-lookup"><span data-stu-id="d6dad-104">A common area phone, or CAP, is typically placed in a shared area and not associated with an individual user.</span></span> <span data-ttu-id="d6dad-105">Beispielsweise ein Empfang für Telefone, Tür Telefon- oder Meeting Room Telefon, CAPs Geräte, sondern als Benutzer eingerichtet sind, und automatisch mit dem Netzwerk anmelden.</span><span class="sxs-lookup"><span data-stu-id="d6dad-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically  sign in to the network.</span></span> <span data-ttu-id="d6dad-106">In den folgenden Schritten helfen wir Ihnen richten Sie ein Konto für Microsoft Telefonsystem mit Aufrufen plant und anschließendem Bereitstellen einer Cap hat.</span><span class="sxs-lookup"><span data-stu-id="d6dad-106">In the steps below, we’ll help you set up an account for Microsoft Phone System with Calling Plans and then deploy a CAP.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="d6dad-107">Erforderliche Komponenten für Telefone in öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="d6dad-107">Prerequisites for Common Area Phones</span></span>

<span data-ttu-id="d6dad-108">Vergewissern Sie sich, dass Sie über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="d6dad-108">Confirm that you have the following:</span></span>

    - <span data-ttu-id="d6dad-109">Telefone in öffentlichen Bereichen SKU erworben</span><span class="sxs-lookup"><span data-stu-id="d6dad-109">Purchased Common Area Phone SKU</span></span> 
    - <span data-ttu-id="d6dad-110">Aktualisierte Firmware (finden Sie unter Unterstützte Firmware im Themahttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="d6dad-110">Updated firmware (See Supported Firmware in topichttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span></span>
    - <span data-ttu-id="d6dad-111">Genehmigte (anzeigen die Liste am Telefonehttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span><span class="sxs-lookup"><span data-stu-id="d6dad-111">Approved  phones (view the list at https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span></span> 


## <a name="check-the-firmware-for-your-phone"></a><span data-ttu-id="d6dad-112">Überprüfen Sie die Firmware für Ihr Telefon</span><span class="sxs-lookup"><span data-stu-id="d6dad-112">Check the firmware for your phone</span></span>
- <span data-ttu-id="d6dad-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span><span class="sxs-lookup"><span data-stu-id="d6dad-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
- <span data-ttu-id="d6dad-114">**Yealink-Telefone**: Navigieren Sie auf dem Hauptbildschirm des Telefons zu **Status** (Status).</span><span class="sxs-lookup"><span data-stu-id="d6dad-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
- <span data-ttu-id="d6dad-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="d6dad-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
- <span data-ttu-id="d6dad-116">**Telefone mit Lync Phone Edition (LPE)**: Navigieren Sie vom Startbildschirm aus zu **Menü** > **Systeminformationen**.</span><span class="sxs-lookup"><span data-stu-id="d6dad-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

<span data-ttu-id="d6dad-117">Firmwareupdates werden vom Skype for Business-Dienst verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d6dad-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="d6dad-118">Die Firmware für alle Skype for Business-zertifizierten Telefone wird auf den Skype for Business-Updateserver hochgeladen, und Geräteupdates sind in allen Telefonen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d6dad-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

<span data-ttu-id="d6dad-119">Je nachdem, wann die Telefone inaktiv sind und welche Abrufintervalle festgelegt sind, werden die neuesten zertifizierten Builds automatisch heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="d6dad-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="d6dad-120">Sie können die Einstellungen für Geräteupdates mit dem [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)-Cmdlet deaktivieren und den  _EnableDeviceUpdate_-Parameter auf  `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="d6dad-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>

## <a name="create-cap"></a><span data-ttu-id="d6dad-121">CAP erstellen</span><span class="sxs-lookup"><span data-stu-id="d6dad-121">Create CAP</span></span>
<span data-ttu-id="d6dad-122">Erstellen Sie die CAP durch Konfigurieren der Einstellungen, bevor Sie die Telefonapparat einrichten.</span><span class="sxs-lookup"><span data-stu-id="d6dad-122">You create the CAP by configuring the settings before you set up the physical phone.</span></span>

#### <a name="purchase-the-common-area-phone-sku"></a><span data-ttu-id="d6dad-123">Kaufen Sie das Telefon im öffentlichen Bereich SKU.</span><span class="sxs-lookup"><span data-stu-id="d6dad-123">Purchase the Common Area Phone SKU.</span></span> 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a><span data-ttu-id="d6dad-124">Richten Sie das Telefon im öffentlichen Bereich<!-- this section could use a screen shot--></span><span class="sxs-lookup"><span data-stu-id="d6dad-124">Set up the common area phone  <!-- this section could use a screen shot--></span></span>

<span data-ttu-id="d6dad-125">**Benutzer erstellen**</span><span class="sxs-lookup"><span data-stu-id="d6dad-125">**Create user**</span></span> 
1. <span data-ttu-id="d6dad-126">Zuweisen von Kontaktobjekten für Telefone SKU</span><span class="sxs-lookup"><span data-stu-id="d6dad-126">Assign Common Area Phone SKU</span></span>
2. <span data-ttu-id="d6dad-127">Zuweisen von Aufrufen planen (bei Verwendung von Microsoft Telefonsystem mit Aufrufen plant).</span><span class="sxs-lookup"><span data-stu-id="d6dad-127">Assign Calling Plan (if using Microsoft Phone System with Calling Plans).</span></span> 
3. <span data-ttu-id="d6dad-128">Zuweisen einer verfügbaren Telefonnummer in die Skype für Business Admin Center, oder fordern Sie eine neue Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="d6dad-128">Assign an available telephone number in the Skype for Business Admin Center, or request a new telephone number.</span></span>

<span data-ttu-id="d6dad-129">**Erstellen Sie neuen Benutzer**</span><span class="sxs-lookup"><span data-stu-id="d6dad-129">**Create New User**</span></span>

1. <span data-ttu-id="d6dad-130">Klicken Sie im Bereich Bereitstellung müssen Sie eine Option, um einen ersten und letzten Namen (beispielsweise Empfang Main) eingeben.</span><span class="sxs-lookup"><span data-stu-id="d6dad-130">In the provisioning pane, you have an option to enter a first and last name (for example, Reception Main).</span></span>
2. <span data-ttu-id="d6dad-131">Geben Sie einen Anzeigenamen (erforderlich), z. B. "Main Empfang."</span><span class="sxs-lookup"><span data-stu-id="d6dad-131">Enter a display name (required), for example, "Main Reception."</span></span>
3. <span data-ttu-id="d6dad-132">Geben Sie einen Benutzernamen (erforderlich), zum Beispiel "MainReception" @"Domäne" (Name des Unternehmens oder Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d6dad-132">Enter a username (required), for example “MainReception” @” domain” (company or enterprise name)</span></span>
4. <span data-ttu-id="d6dad-133">Geben Sie Speicherort (Land).</span><span class="sxs-lookup"><span data-stu-id="d6dad-133">Enter Location (country).</span></span>

<span data-ttu-id="d6dad-134">**Zuweisen von Kontaktobjekten für Telefone SKU** Wechseln Sie in das Office 365 Administrationscenter zu **Abrechnung > Dienste erwerben** und Hinzufügen von **Kontaktobjekten für Telefone**</span><span class="sxs-lookup"><span data-stu-id="d6dad-134">**Assign Common Area Phone SKU** In the Office 365 admin center, go to **Billing > Purchase Services** and add **Common Area Phone**</span></span>

<span data-ttu-id="d6dad-135">**Aufrufen von Plan CAP SKU zuweisen**</span><span class="sxs-lookup"><span data-stu-id="d6dad-135">**Assign Calling Plan in CAP SKU**</span></span>

1. <span data-ttu-id="d6dad-136">Wählen Sie eine Aufrufen des Telefons aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d6dad-136">Select a Calling Plan to enable the phone.</span></span> 
2. <span data-ttu-id="d6dad-137">Fügen Sie der Caps um Telefonsystem und Skype für Business Online – Plan 2 in der CAP SKU zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d6dad-137">Add the CAP to enable the Phone System and Skype for Business Online Plan 2 in the CAP SKU.</span></span> <!-- odd order for step -->

<span data-ttu-id="d6dad-138">**Weisen Sie eine Telefonnummer**</span><span class="sxs-lookup"><span data-stu-id="d6dad-138">**Assign a telephone number**</span></span>
1. <span data-ttu-id="d6dad-139">Überprüfen Sie unter Verfügbare Telefonnummern **VoIP > Telefonnummern**.</span><span class="sxs-lookup"><span data-stu-id="d6dad-139">Check for available phone numbers under **Voice > Phone Numbers**.</span></span>
2. <span data-ttu-id="d6dad-140">Wählen Sie eine Rufnummer aus der Liste der verfügbaren Nummern Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="d6dad-140">Select a number from the available list of phone numbers number.</span></span>
3. <span data-ttu-id="d6dad-141">Bestätigen Sie Ihre Auswahl durch Auswählen von **Sprach-** und **Rufnummern**.</span><span class="sxs-lookup"><span data-stu-id="d6dad-141">Confirm your selection by selecting **Voice** and **Phone Numbers**.</span></span>

    ><span data-ttu-id="d6dad-142">[Hinweis] VoIP-Benutzer werden nur anzeigen, wenn sie Telefonsystem Lizenz angewendet, obwohl auch nach dem anwenden, es aktualisieren dauern kann verfügen.</span><span class="sxs-lookup"><span data-stu-id="d6dad-142">[Note] Voice users only show if they have the Phone System licence applied, although even after applying, it can take time to refresh.</span></span> <span data-ttu-id="d6dad-143">Können erneut öffnen irgendwann Skype für Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="d6dad-143">Sometime reopening Skype for Business Admin center helps.</span></span>
    
## <a name="configure-phone"></a><span data-ttu-id="d6dad-144">Konfigurieren des Telefons</span><span class="sxs-lookup"><span data-stu-id="d6dad-144">Configure Phone</span></span>

<span data-ttu-id="d6dad-145">**Vorbereiten der physischen Telefone**</span><span class="sxs-lookup"><span data-stu-id="d6dad-145">**Prepare the physical phones**</span></span> 

<span data-ttu-id="d6dad-146">Das ausgewählte Telefon muss den Modus für Telefone in öffentlichen Bereichen haben.</span><span class="sxs-lookup"><span data-stu-id="d6dad-146">Your selected phone needs to have the Common Area Phone mode.</span></span> 

<span data-ttu-id="d6dad-147">***Beispiel Polycom VVX Telefon***</span><span class="sxs-lookup"><span data-stu-id="d6dad-147">***Example Polycom VVX phone***</span></span>

<span data-ttu-id="d6dad-148">Aktivieren Sie Common Area Phone Mode auf Polycom VVX folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d6dad-148">Enable Common Area Phone Mode on Polycom VVX by following these steps:</span></span>
1. <span data-ttu-id="d6dad-149">Verwenden Sie in Ihrem Browser die Weboberfläche, um auf die VVX CAP-Modus aktivieren</span><span class="sxs-lookup"><span data-stu-id="d6dad-149">In your browser, use the web interface to enable CAP mode on the VVX</span></span>
2. <span data-ttu-id="d6dad-150">Wechseln Sie zur **Einstellung** und in der Skype für Business Festlegen der Option, und wählen Sie **Telefone in öffentlichen Bereichen**.</span><span class="sxs-lookup"><span data-stu-id="d6dad-150">Go to **Setting**  and in the Skype for Business Setting option, select **Common Area Phone**.</span></span>
3. <span data-ttu-id="d6dad-151">Klicken Sie auf **Speichern** , um die Konfigurationseinstellungen speichern.</span><span class="sxs-lookup"><span data-stu-id="d6dad-151">Click **Save** to save your configuration settings.</span></span>

<span data-ttu-id="d6dad-152">Nun, dass der CAP Telefon-Modus aktiviert ist, richten Sie das Telefon mit Display des Telefons.</span><span class="sxs-lookup"><span data-stu-id="d6dad-152">Now that the CAP phone mode is enabled, set up the phone using the phone's display.</span></span>

1. <span data-ttu-id="d6dad-153">Wählen Sie in den Einstellungen für **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="d6dad-153">In the Settings, select **Advanced**.</span></span>
2. <span data-ttu-id="d6dad-154">Geben Sie das Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="d6dad-154">Enter password.</span></span>
3. <span data-ttu-id="d6dad-155">Wählen Sie im administrationseinstellungen **Common Area Phone Settings**.</span><span class="sxs-lookup"><span data-stu-id="d6dad-155">In Administration settings, select **Common Area Phone Settings**.</span></span>
4. <span data-ttu-id="d6dad-156">Aktivieren von Common Area Phone and CAP Admin</span><span class="sxs-lookup"><span data-stu-id="d6dad-156">Enable Common Area Phone and CAP Admin</span></span>
5. <span data-ttu-id="d6dad-157">Wählen Sie **Config speichern**.</span><span class="sxs-lookup"><span data-stu-id="d6dad-157">Select **Save Config**.</span></span>

<span data-ttu-id="d6dad-158">Ihr Telefon kann jetzt bereitgestellt werden, was werden Sie bei der Anmeldung auf dem Startbildschirm.</span><span class="sxs-lookup"><span data-stu-id="d6dad-158">Your phone is ready to be provisioned, which you'll do when you sign in on the home screen.</span></span>

1. <span data-ttu-id="d6dad-159">Melden Sie sich durch Auswählen von **Einstellungen > Funktionen > Skype für Business.**</span><span class="sxs-lookup"><span data-stu-id="d6dad-159">Sign in by selecting **settings > features > Skype for Business.**</span></span>
2. <span data-ttu-id="d6dad-160">Wählen Sie Benutzeranmeldeinformationen und wählen Sie **Web - Anmeldung (CAP)** um einen Code zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d6dad-160">Select User Credentials, and select select **web sign-in (CAP)** to generate a code..</span></span>
3. <span data-ttu-id="d6dad-161">Wechseln Sie zu der Bereitstellung Portal http://aka.ms/skypecap, und melden Sie sich als **Administrator**.</span><span class="sxs-lookup"><span data-stu-id="d6dad-161">Go to the provisioning portal http://aka.ms/skypecap, and sign in as **admin**.</span></span>
4. <span data-ttu-id="d6dad-162">Geben Sie Anzeigenamen ein (beispielsweise Main Empfang), um Ihre CAP anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6dad-162">Enter display name (for example, Main Reception) to view your CAP.</span></span>

><span data-ttu-id="d6dad-163">[Hinweis] Wenn "-Suche für Telefone in öffentlichen Bereichen nur" ist ausgecheckt, deaktivieren Sie das Kontrollkästchen, und wiederholen Sie die Suche.</span><span class="sxs-lookup"><span data-stu-id="d6dad-163">[Note] If “Search for Common Area Phones only” is checked, clear the checkbox and search again.</span></span>

5. <span data-ttu-id="d6dad-164">Klicken Sie im Codefenster paarungs Geben Sie den Code auf dem Telefon angezeigt, und klicken Sie auf **Bereitstellung**.</span><span class="sxs-lookup"><span data-stu-id="d6dad-164">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

<span data-ttu-id="d6dad-165">In diesem letzten Schritt Wht, sollte das Telefon automatisch anmelden.</span><span class="sxs-lookup"><span data-stu-id="d6dad-165">Wht this last step, the phone should sign in automatically.</span></span>

<span data-ttu-id="d6dad-166">Weitere Informationen zu verfügbaren Telefonen [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span><span class="sxs-lookup"><span data-stu-id="d6dad-166">Learn more about available phones at [](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span></span>



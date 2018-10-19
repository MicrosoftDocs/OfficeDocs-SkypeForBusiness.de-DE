---
title: Einrichten von Telefonen für gemeinsame Bereiche
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: Hier erfahren Sie die Schritte zur Bereitstellung, um die richtige Firmware erhalten möchten, aktualisieren sie bei Bedarf, Zuweisen von Lizenzen und Konfigurieren von Einstellungen für Telefone in öffentlichen Bereichen.
ms.openlocfilehash: b92cef4234823c53faf6193d2e9e90fe3e5b60f0
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678166"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="7c674-103">Einrichten von Telefonen für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="7c674-103">Set up common area phones</span></span>
<span data-ttu-id="7c674-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span><span class="sxs-lookup"><span data-stu-id="7c674-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="7c674-107">Voraussetzungen für Telefone für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="7c674-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="7c674-108">Zunächst müssen Sie bestätigen, dass Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="7c674-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="7c674-109">Sie haben eine Lizenz für Telefone für gemeinsame Bereiche und einen Anrufplan gekauft.</span><span class="sxs-lookup"><span data-stu-id="7c674-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="7c674-110">Sie haben nach zugelassenen Telefonen gesucht und sie gekauft (siehe die Liste [hier](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="7c674-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="7c674-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span><span class="sxs-lookup"><span data-stu-id="7c674-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="7c674-113">**Telefone Polycom VVX**: Rufen Sie die **Einstellungsseite** > **Status** > **Plattform** > **Anwendung** > **Main**.</span><span class="sxs-lookup"><span data-stu-id="7c674-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="7c674-114">**Yealink Telefone**: Wechseln Sie auf **Status** auf dem Bildschirm Telefon.</span><span class="sxs-lookup"><span data-stu-id="7c674-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="7c674-115">**AudioCodes Telefone**: Gehen Sie zum **Menü** > **Gerätestatus** > **Firmwareversion** auf der Startseite.</span><span class="sxs-lookup"><span data-stu-id="7c674-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="7c674-116">**Lync Phone Edition (LPE) Telefone**: Gehen Sie zum **Menü** > **Systeminformationen** aus dem Startbildschirm.</span><span class="sxs-lookup"><span data-stu-id="7c674-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="7c674-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span><span class="sxs-lookup"><span data-stu-id="7c674-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="7c674-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="7c674-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="7c674-121">Einrichten eines Telefons für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="7c674-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="7c674-122">Sie müssen diese Schritte befolgen:</span><span class="sxs-lookup"><span data-stu-id="7c674-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="7c674-123">Schritt 1 - Lizenzen kaufen</span><span class="sxs-lookup"><span data-stu-id="7c674-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="7c674-124">Gehen Sie im Office 365 Admin Center zu **Rechnung** > **Kaufdienste** und fügen Sie **Weitere Pläne** hinzu.</span><span class="sxs-lookup"><span data-stu-id="7c674-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="7c674-126">Klicken Sie auf **Telefon für gemeinsame Bereiche** > **Jetzt kaufen** > auf der Seite **Check-Out** klicken Sie auf **Jetzt kaufen**.</span><span class="sxs-lookup"><span data-stu-id="7c674-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="7c674-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span><span class="sxs-lookup"><span data-stu-id="7c674-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="7c674-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span><span class="sxs-lookup"><span data-stu-id="7c674-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="7c674-131">Weitere Informationen zu Lizenzen finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="7c674-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="7c674-132">Schritt 2 - Ein neues Benutzerkonto für das Telefon erstellen und die Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="7c674-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="7c674-133">Gehen Sie im Office 365 Admin Center zu **Benutzer** > **Aktive Benutzer** > **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7c674-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="7c674-134">Geben Sie einen **Benutzernamen** wie "Haupt" für den Vornamen und "Empfang" für den Nachnamen ein.</span><span class="sxs-lookup"><span data-stu-id="7c674-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="7c674-135">Geben Sie einen **Anzeigename** ein, falls nicht automatisch einer wie "Hauptempfang" generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7c674-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="7c674-136">Geben Sie einen **Benutzernamen** wie "Hauptempfang" oder "Hauptlobby" ein.</span><span class="sxs-lookup"><span data-stu-id="7c674-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="7c674-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="7c674-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="7c674-139">Wenn Sie sich noch dort befinden, weisen Sie die Lizenzen diesem Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="7c674-139">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="7c674-140">Klicken Sie auf der gleichen Seite auf **Produktlizenzen** erweitern.</span><span class="sxs-lookup"><span data-stu-id="7c674-140">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="7c674-141">Aktivieren Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7c674-141">Turn on the following:</span></span>
   - <span data-ttu-id="7c674-142">Telefon für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="7c674-142">Common Area Phone</span></span>
   - <span data-ttu-id="7c674-143">Danach müssen Sie entweder einen **Anrufplan für Inland** oder einen Anrufplan für Inland und **Ausland**auswählen.</span><span class="sxs-lookup"><span data-stu-id="7c674-143">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="7c674-144">Die Zuweisung der Lizenzen sieht dann so aus:</span><span class="sxs-lookup"><span data-stu-id="7c674-144">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="7c674-146">Nur zu Ihrer Information Skype for Business Plan 2 ist in der Lizenz **Telefon für gemeinsame Bereiche** enthalten.</span><span class="sxs-lookup"><span data-stu-id="7c674-146">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="7c674-147">Weitere Informationen finden Sie unter [Benutzer hinzufügen](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="7c674-147">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="7c674-148">Schritt 3 - Eine Telefonnummer dem Benutzerkonto Telefon für gemeinsame Bereich zuweisen</span><span class="sxs-lookup"><span data-stu-id="7c674-148">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="7c674-149">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Dem Benutzer mit dem **Skype for Business Admin Center** eine Telefonnummer zuweisen</span><span class="sxs-lookup"><span data-stu-id="7c674-149">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="7c674-150">Im Office 365 Administrationscenter > **Admin zentriert** > **Skype für Unternehmen**.</span><span class="sxs-lookup"><span data-stu-id="7c674-150">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="7c674-151">In dem **Skype for Business Admin Center** >  **Sprache** > **Telefonnummern**.</span><span class="sxs-lookup"><span data-stu-id="7c674-151">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="7c674-152">Wählen Sie eine Nummer aus der Liste der Telefonnummern aus und klicken Sie auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="7c674-152">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="7c674-153">Geben Sie auf der Seite **Zuweisen** im Feld **Sprachbenutzer** den Namen des Benutzers ein, der für das Telefon verwendet wird, und wählen Sie den Benutzer im Feld **Sprachbenutzer auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="7c674-153">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="7c674-154">Hier müssen Sie eine Notfalladresse angeben.</span><span class="sxs-lookup"><span data-stu-id="7c674-154">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="7c674-155">Nach der Suche schauen Sie unter **Notfalladresse auswählen**, um die richtige für Sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="7c674-155">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="7c674-156">Klicken Sie auf **Speichern** und Ihr Benutzer sollte so aussehen:</span><span class="sxs-lookup"><span data-stu-id="7c674-156">Click **Save** and your user should look like this:</span></span>

    ![cap-user-nummer.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="7c674-158">Benutzer werden nur angezeigt, wenn sie eine **Telefonsystem**-Lizenz beantragt haben.</span><span class="sxs-lookup"><span data-stu-id="7c674-158">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="7c674-159">Wenn Sie dies gerade erst getan haben, dann kann es etwas dauern, bis der Benutzer in der Liste erscheint.</span><span class="sxs-lookup"><span data-stu-id="7c674-159">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="7c674-160">Weitere Informationen finden Sie unter [Erhalten von Telefonnummern für Ihre Benutzer](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="7c674-160">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="7c674-161">Sie können auch Ihre Telefonnummer, die Sie bei einem anderen Anbieter haben "*portieren*" oder an Office 365 übertragen.</span><span class="sxs-lookup"><span data-stu-id="7c674-161">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="7c674-162">Angezeigt wird, [Übertragen von Telefonnummern zu Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="7c674-162">See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="7c674-163">Schritt 4 - Einrichten des Telefons</span><span class="sxs-lookup"><span data-stu-id="7c674-163">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="7c674-164">**Einstellen des Telefonmodus**</span><span class="sxs-lookup"><span data-stu-id="7c674-164">**Setting the mode on a phone**</span></span>

<span data-ttu-id="7c674-165">Das oder die Telefone, die Sie besitzen, müssen den Modus **Telefone für gemeinsame Bereiche** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="7c674-165">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="7c674-166">Vielleicht sollten Sie das überprüfen, um sicherzugehen.</span><span class="sxs-lookup"><span data-stu-id="7c674-166">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="7c674-167">**Hier ein Beispiel für die Einrichtung eines Polycom VVX-Telefons**</span><span class="sxs-lookup"><span data-stu-id="7c674-167">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="7c674-168">Aktivieren Sie mit den folgenden Schritten den Modus "Telefon für gemeinsame Bereiche" für Polycom VVX:</span><span class="sxs-lookup"><span data-stu-id="7c674-168">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="7c674-169">Stellen Sie in Ihrem Browser eine Verbindung zur Webschnittstelle her, damit Sie den CAP-Modus aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="7c674-169">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="7c674-170">Danach gehen Sie zu **Einstellung** und wählen in der Option **Skype for Business-Einstellungen** **Telefone für gemeinsame Bereiche**.</span><span class="sxs-lookup"><span data-stu-id="7c674-170">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="7c674-171">Klicken Sie auf **Ja**, um Ihre Einstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7c674-171">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="7c674-172">Nachdem der CAP-Modus aktiviert wurde, richten Sie das Telefon über die Anzeige des Telefons ein.</span><span class="sxs-lookup"><span data-stu-id="7c674-172">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="7c674-173">Die Anzeige sollte **CaAP ist aktiviert** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7c674-173">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="7c674-174">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="7c674-174">Then do the following:</span></span>

    1. <span data-ttu-id="7c674-175">Klicken Sie auf **Einstellungen speichern.**</span><span class="sxs-lookup"><span data-stu-id="7c674-175">Click **Settings**.</span></span>
    2. <span data-ttu-id="7c674-176">Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="7c674-176">Select **Advanced**.</span></span>
    3. <span data-ttu-id="7c674-177">Geben Sie das Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="7c674-177">Enter the password.</span></span>
    4. <span data-ttu-id="7c674-178">Wählen Sie unter **Verwaltungseinstellungen** **Einstellungen für Telefone für gemeinsame Bereiche**.</span><span class="sxs-lookup"><span data-stu-id="7c674-178">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="7c674-179">Aktivieren Sie **CAP** und **CAP Admin-Modus**.</span><span class="sxs-lookup"><span data-stu-id="7c674-179">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="7c674-180">Klicken Sie auf **Konfiguration speichern**.</span><span class="sxs-lookup"><span data-stu-id="7c674-180">Click **Save Config**.</span></span>

- <span data-ttu-id="7c674-181">Ok, jetzt ist Ihr Telefon bereit, damit Sie sich auf dem Startbildschirm anmelden können.</span><span class="sxs-lookup"><span data-stu-id="7c674-181">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="7c674-182">Melden Sie sich an, indem Sie **Einstellungen** > **Funktionen** > **Skype for Business** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7c674-182">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="7c674-183">Wählen Sie **Benutzeranmeldeinformationen**, und wählen Sie **Webanmeldung (CAP)**, um einen Code zu generieren.</span><span class="sxs-lookup"><span data-stu-id="7c674-183">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="7c674-184">Gehen Sie zum [Provisioning-Portal](https://aka.ms/skypecap), und melden Sie sich als **Administrator** an.</span><span class="sxs-lookup"><span data-stu-id="7c674-184">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="7c674-185">Geben Sie den Anzeigenamen ein (z. B. Hauptempfang).</span><span class="sxs-lookup"><span data-stu-id="7c674-185">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="7c674-186">Wenn **Nur nach Telefonen für gemeinsame Bereiche suchen** markiert ist, deaktivieren Sie das Kontrollkästchen und suchen Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="7c674-186">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="7c674-187">Geben Sie im Fenster Kopplungscode den auf dem Telefon angezeigten Code ein und klicken Sie auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="7c674-187">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="7c674-188">Nach diesem letzten Schritt sollte sich das Telefon automatisch anmelden.</span><span class="sxs-lookup"><span data-stu-id="7c674-188">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="7c674-189">Die CAP-Bereitstellungsseite gibt an, dass sie das Passwort des CAP-Kontos auf ein zufälliges Passwort zurücksetzt.</span><span class="sxs-lookup"><span data-stu-id="7c674-189">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="7c674-190">Beachten Sie, dass das Konto, auf das sich die CAP bezieht, das Azure Active Directory (AAD)-Konto ist.</span><span class="sxs-lookup"><span data-stu-id="7c674-190">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="7c674-191">Wenn Sie das Konto nur in AAD angelegt haben, ist der Prozess einfach.</span><span class="sxs-lookup"><span data-stu-id="7c674-191">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="7c674-192">Wenn Sie eine lokale Active Directory AAD synchronisiert wurden, und Sie ein Drittanbieter-IDP oder AD FS verwenden, schlägt fehl, CAP-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="7c674-192">If you have synced an on premises Active Directory to AAD and you use a third-party IDP or ADFS, CAP provisioning will fail.</span></span> <span data-ttu-id="7c674-193">In diesem Fall müssen Sie ein Office 365/Azure nur Active Directory-Konto (beispielsweise ein Konto mit der Domäne **"onmicrosoft.com"** ) verwenden CAP Bereitstellung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7c674-193">In this case, you need to use an Office 365/Azure Active Directory account only (for example, an account with **onmicrosoft.com** domain) for CAP provisioning to work.</span></span>


### <a name="related-topics"></a><span data-ttu-id="7c674-194">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7c674-194">Related topics</span></span>

- <span data-ttu-id="7c674-195">Weitere Informationen über verfügbare Telefone finden Sie unter [Einsatz von Skype for Business Online-Telefonen](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="7c674-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="7c674-196">Erwerben von Telefonen für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7c674-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)



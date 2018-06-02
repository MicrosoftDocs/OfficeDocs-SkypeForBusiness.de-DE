---
title: Einrichten von Telefonen für gemeinsame Bereiche
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
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
description: Lernen Sie die Bereitstellungsschritte kennen, um die richtige Firmware zu erhalten, sie bei Bedarf zu aktualisieren, Lizenzen zuzuweisen und Einstellungen für Telefone für gemeinsame Bereiche zu konfigurieren.
ms.openlocfilehash: 25605e7538792080213eebb898e612be6ce5bfab
ms.sourcegitcommit: bdf9946b7c65ef7985d6b03a1479ea3a5c17a304
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
ms.locfileid: "19426801"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="42ecc-103">Einrichten von Telefonen für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="42ecc-103">Set up common area phones</span></span>
<span data-ttu-id="42ecc-104">Ein Telefon für gemeinsame Bereiche (CAP) wird typischerweise in einem Bereich wie in einer Lobby oder in einem anderen Bereich platziert, der vielen Menschen zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="42ecc-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="42ecc-105">Zum Beispiel ein Telefon im Empfangsbereich, ein Türtelefon oder ein Konferenzraumtelefon, CAPs werden als Geräte und nicht als Benutzer eingerichtet und melden sich automatisch in einem Netzwerk an.</span><span class="sxs-lookup"><span data-stu-id="42ecc-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="42ecc-106">In den folgenden Schritten helfen wir Ihnen, ein Konto für das Telefonsystem mit Anrufplänen einzurichten, damit Sie diese Art von Telefone für Ihr Unternehmen bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="42ecc-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="42ecc-107">Voraussetzungen für Telefone für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="42ecc-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="42ecc-108">Zunächst müssen Sie bestätigen, dass Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="42ecc-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="42ecc-109">Sie haben eine Lizenz für Telefone für gemeinsame Bereiche und einen Anrufplan gekauft.</span><span class="sxs-lookup"><span data-stu-id="42ecc-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="42ecc-110">Sie haben nach zugelassenen Telefonen gesucht und sie gekauft (siehe die Liste [hier](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="42ecc-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>         
 - <span data-ttu-id="42ecc-111">Sie haben die Firmware auf Ihren Telefonen aktualisiert (siehe unterstützte Firmware [in diesem Thema](getting-phones-for-skype-for-business-online.md)).</span><span class="sxs-lookup"><span data-stu-id="42ecc-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).</span></span>  <span data-ttu-id="42ecc-112">Sie können die Firmware auf Ihrem Telefon wie folgt überprüfen:</span><span class="sxs-lookup"><span data-stu-id="42ecc-112">You can check the firmware on you phone by doing this:</span></span>       
    - <span data-ttu-id="42ecc-113">**Polycom VVX-Telefone**: Gehen Sie zu **Einstellungen** > **Status** > **Plattform** > **Anwendung** > **Haupt**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="42ecc-114">**Yealink-Telefone**: Gehen Sie auf dem Hauptbildschirm des Telefons zu **Status**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="42ecc-115">**AudioCodes-Telefone**: Gehen Sie auf dem Hauptbildschirm auf **Menü** > **Gerätestatus** > **Firmwareversion**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
    - <span data-ttu-id="42ecc-116">**Telefone mit Lync Phone Edition (LPE)**: Gehen Sie auf dem Startbildschirm auf **Menü** > **Systeminformationen**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="42ecc-117">Firmwareupdates werden vom Skype for Business-Dienst verwaltet.</span><span class="sxs-lookup"><span data-stu-id="42ecc-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="42ecc-118">Die Firmware für alle Skype for Business-zertifizierten Telefone wird auf den Skype for Business-Updateserver hochgeladen, und Geräteupdates sind in allen Telefonen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="42ecc-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

    <span data-ttu-id="42ecc-119">Je nachdem, wann die Telefone inaktiv sind und welche Abrufintervalle festgelegt sind, werden die neuesten zertifizierten Builds automatisch heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="42ecc-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="42ecc-120">Sie können die Einstellungen für Geräteupdates mit dem [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy)-Cmdlet deaktivieren und den Parameter *Geräteupdate aktivieren* auf `false` einstellen.</span><span class="sxs-lookup"><span data-stu-id="42ecc-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="42ecc-121">Einrichten eines Telefons für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="42ecc-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="42ecc-122">Sie müssen diese Schritte befolgen:</span><span class="sxs-lookup"><span data-stu-id="42ecc-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="42ecc-123">Schritt 1 - Lizenzen kaufen</span><span class="sxs-lookup"><span data-stu-id="42ecc-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="42ecc-124">Gehen Sie im Office 365 Admin Center zu **Rechnung** > **Kaufdienste** und fügen Sie **Weitere Pläne** hinzu.</span><span class="sxs-lookup"><span data-stu-id="42ecc-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="42ecc-126">Klicken Sie auf **Telefon für gemeinsame Bereiche** > **Jetzt kaufen** > auf der Seite **Check-Out** klicken Sie auf **Jetzt kaufen**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="42ecc-127">Klicken Sie darauf, um **Add-on-Abonnements** zu erweitern, und klicken Sie dann darauf, um einen Anrufplan zu kaufen.</span><span class="sxs-lookup"><span data-stu-id="42ecc-127">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="42ecc-128">Wählen Sie entweder den **Anrufplan für Inland** oder **Anrufplan für Inland und Ausland**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-128">Domestic Calling Plan, or Domestic and International Calling Plan</span></span>

> [!Note]
> <span data-ttu-id="42ecc-129">Sie benötigen für das Telefonsystem keine Lizenz.</span><span class="sxs-lookup"><span data-stu-id="42ecc-129">You don't need a Phone System license.</span></span> <span data-ttu-id="42ecc-130">Sie ist in der Lizenz **Telefon für gemeinsame Bereiche** enthalten.</span><span class="sxs-lookup"><span data-stu-id="42ecc-130">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="42ecc-131">Weitere Informationen zu Lizenzen finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="42ecc-131">For more information, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="42ecc-132">Schritt 2 - Ein neues Benutzerkonto für das Telefon erstellen und die Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="42ecc-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="42ecc-133">Gehen Sie im Office 365 Admin Center zu **Benutzer** > **Aktive Benutzer** > **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="42ecc-134">Geben Sie einen **Benutzernamen** wie "Haupt" für den Vornamen und "Empfang" für den Nachnamen ein.</span><span class="sxs-lookup"><span data-stu-id="42ecc-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="42ecc-135">Geben Sie einen **Anzeigename** ein, falls nicht automatisch einer wie "Hauptempfang" generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="42ecc-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="42ecc-136">Geben Sie einen **Benutzernamen** wie "Hauptempfang" oder "Hauptlobby" ein.</span><span class="sxs-lookup"><span data-stu-id="42ecc-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="42ecc-137">Für Telefone für gemeinsame Bereiche können Sie ein Kennwort manuell festlegen oder das gleiche Kennwort für alle Telefone für gemeinsame Bereiche verwenden.</span><span class="sxs-lookup"><span data-stu-id="42ecc-137">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="42ecc-138">Sie können auch darüber nachdenken, die Wahl von **Benutzer veranlassen, sein Passwort bei der Erstanmeldung zu ändern** aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="42ecc-138">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="42ecc-139">WARTEN SIE!</span><span class="sxs-lookup"><span data-stu-id="42ecc-139">WAIT!!</span></span> <span data-ttu-id="42ecc-140">Klicken Sie nicht auf **Hinzufügen**!!</span><span class="sxs-lookup"><span data-stu-id="42ecc-140">Don't click **Add**!!</span></span> <span data-ttu-id="42ecc-141">Oh, wenn Sie auf **Hinzufügen** geklickt haben, gehen Sie wie folgt vor: Office 365 Admin Center > **Benutzer** > **Aktive Benutzer** und suchen Sie dann den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="42ecc-141">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="42ecc-142">Danach klicken Sie auf der Eigenschaftenseite des Benutzers auf **Produktlizenzen** und dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-142">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="42ecc-143">Auf der Seite **Produktlizenzen** aktivieren Sie **Telefone für gemeinsame Bereiche** und wählen entweder einen **Anrufplan für Inland** oder einen Anrufplan für Inland und **Anrufplan für Ausland**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-143">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="42ecc-144">Wenn Sie sich noch dort befinden, weisen Sie die Lizenzen diesem Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="42ecc-144">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="42ecc-145">Klicken Sie auf der gleichen Seite auf **Produktlizenzen** erweitern.</span><span class="sxs-lookup"><span data-stu-id="42ecc-145">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="42ecc-146">Aktivieren Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="42ecc-146">Turn on the following:</span></span>
    - <span data-ttu-id="42ecc-147">Telefon für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="42ecc-147">Common Area Phone</span></span>
    - <span data-ttu-id="42ecc-148">Danach müssen Sie entweder einen **Anrufplan für Inland** oder einen Anrufplan für Inland und **Ausland**auswählen.</span><span class="sxs-lookup"><span data-stu-id="42ecc-148">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>
     
    <span data-ttu-id="42ecc-149">Die Zuweisung der Lizenzen sieht dann so aus:</span><span class="sxs-lookup"><span data-stu-id="42ecc-149">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="42ecc-151">Nur zu Ihrer Information Skype for Business Plan 2 ist in der Lizenz **Telefon für gemeinsame Bereiche** enthalten.</span><span class="sxs-lookup"><span data-stu-id="42ecc-151">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="42ecc-152">Weitere Informationen finden Sie unter [Benutzer hinzufügen](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="42ecc-152">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="42ecc-153">Schritt 3 - Eine Telefonnummer dem Benutzerkonto Telefon für gemeinsame Bereich zuweisen</span><span class="sxs-lookup"><span data-stu-id="42ecc-153">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="42ecc-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Dem Benutzer mit dem **Skype for Business Admin Center** eine Telefonnummer zuweisen</span><span class="sxs-lookup"><span data-stu-id="42ecc-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="42ecc-155">Gehen Sie im Office 365 Admin Center zu **Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-155">In the Office 365 admin center, go to **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="42ecc-156">In dem **Skype for Business Admin Center** >  **Sprache** > **Telefonnummern**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-156">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="42ecc-157">Wählen Sie eine Nummer aus der Liste der Telefonnummern aus und klicken Sie auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-157">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="42ecc-158">Geben Sie auf der Seite **Zuweisen** im Feld **Sprachbenutzer** den Namen des Benutzers ein, der für das Telefon verwendet wird, und wählen Sie den Benutzer im Feld **Sprachbenutzer auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="42ecc-158">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span> 
5. <span data-ttu-id="42ecc-159">Hier müssen Sie eine Notfalladresse angeben.</span><span class="sxs-lookup"><span data-stu-id="42ecc-159">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="42ecc-160">Nach der Suche schauen Sie unter **Notfalladresse auswählen**, um die richtige für Sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="42ecc-160">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="42ecc-161">Klicken Sie auf **Speichern** und Ihr Benutzer sollte so aussehen:</span><span class="sxs-lookup"><span data-stu-id="42ecc-161">Click **Save** and your user should look like this:</span></span>

    ![cap-user-nummer.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="42ecc-163">Benutzer werden nur angezeigt, wenn sie eine **Telefonsystem**-Lizenz beantragt haben.</span><span class="sxs-lookup"><span data-stu-id="42ecc-163">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="42ecc-164">Wenn Sie dies gerade erst getan haben, dann kann es etwas dauern, bis der Benutzer in der Liste erscheint.</span><span class="sxs-lookup"><span data-stu-id="42ecc-164">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="42ecc-165">Weitere Informationen finden Sie unter [Erhalten von Telefonnummern für Ihre Benutzer](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="42ecc-165">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="42ecc-166">Sie können auch Ihre Telefonnummer, die Sie bei einem anderen Anbieter haben "*portieren*" oder an Office 365 übertragen.</span><span class="sxs-lookup"><span data-stu-id="42ecc-166">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="42ecc-167">Siehe [Übertragen von Telefonnummern zu Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="42ecc-167">See [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) for more information.</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="42ecc-168">Schritt 4 - Einrichten des Telefons</span><span class="sxs-lookup"><span data-stu-id="42ecc-168">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="42ecc-169">**Einstellen des Telefonmodus**</span><span class="sxs-lookup"><span data-stu-id="42ecc-169">**Setting the mode on a phone**</span></span>

<span data-ttu-id="42ecc-170">Das oder die Telefone, die Sie besitzen, müssen den Modus **Telefone für gemeinsame Bereiche** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="42ecc-170">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="42ecc-171">Vielleicht sollten Sie das überprüfen, um sicherzugehen.</span><span class="sxs-lookup"><span data-stu-id="42ecc-171">You might want to check on that to make sure they do.</span></span> 

<span data-ttu-id="42ecc-172">**Hier ein Beispiel für die Einrichtung eines Polycom VVX-Telefons**</span><span class="sxs-lookup"><span data-stu-id="42ecc-172">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="42ecc-173">Aktivieren Sie mit den folgenden Schritten den Modus "Telefon für gemeinsame Bereiche" für Polycom VVX:</span><span class="sxs-lookup"><span data-stu-id="42ecc-173">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="42ecc-174">Stellen Sie in Ihrem Browser eine Verbindung zur Webschnittstelle her, damit Sie den CAP-Modus aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="42ecc-174">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="42ecc-175">Danach gehen Sie zu **Einstellung** und wählen in der Option **Skype for Business-Einstellungen** **Telefone für gemeinsame Bereiche**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-175">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="42ecc-176">Klicken Sie auf **Ja**, um Ihre Einstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="42ecc-176">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="42ecc-177">Nachdem der CAP-Modus aktiviert wurde, richten Sie das Telefon über die Anzeige des Telefons ein.</span><span class="sxs-lookup"><span data-stu-id="42ecc-177">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="42ecc-178">Die Anzeige sollte **CaAP ist aktiviert** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="42ecc-178">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="42ecc-179">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="42ecc-179">Then do the following:</span></span>

    1. <span data-ttu-id="42ecc-180">Klicken Sie auf **Einstellungen speichern.**</span><span class="sxs-lookup"><span data-stu-id="42ecc-180">Click **Settings**.</span></span>
    2. <span data-ttu-id="42ecc-181">Markieren Sie **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-181">Select **Advanced Request**.</span></span>
    3. <span data-ttu-id="42ecc-182">Geben Sie das Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="42ecc-182">Enter the password.</span></span>
    4. <span data-ttu-id="42ecc-183">Wählen Sie unter **Verwaltungseinstellungen** **Einstellungen für Telefone für gemeinsame Bereiche**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-183">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="42ecc-184">Aktivieren Sie **CAP** und **CAP Admin-Modus**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-184">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="42ecc-185">Klicken Sie auf **Konfiguration speichern**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-185">Click **Save Config**.</span></span>

- <span data-ttu-id="42ecc-186">Ok, jetzt ist Ihr Telefon bereit, damit Sie sich auf dem Startbildschirm anmelden können.</span><span class="sxs-lookup"><span data-stu-id="42ecc-186">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="42ecc-187">Melden Sie sich an, indem Sie **Einstellungen** > **Funktionen** > **Skype for Business** auswählen.</span><span class="sxs-lookup"><span data-stu-id="42ecc-187">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="42ecc-188">Wählen Sie **Benutzeranmeldeinformationen**, und wählen Sie **Webanmeldung (CAP)**, um einen Code zu generieren.</span><span class="sxs-lookup"><span data-stu-id="42ecc-188">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="42ecc-189">Gehen Sie zum [Provisioning-Portal](http://aka.ms/skypecap), und melden Sie sich als **Administrator** an.</span><span class="sxs-lookup"><span data-stu-id="42ecc-189">Go to the [provisioning portal](http://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="42ecc-190">Geben Sie den Anzeigenamen ein (z. B. Hauptempfang).</span><span class="sxs-lookup"><span data-stu-id="42ecc-190">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="42ecc-191">Wenn **Nur nach Telefonen für gemeinsame Bereiche suchen** markiert ist, deaktivieren Sie das Kontrollkästchen und suchen Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="42ecc-191">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="42ecc-192">Geben Sie im Fenster Kopplungscode den auf dem Telefon angezeigten Code ein und klicken Sie auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="42ecc-192">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="42ecc-193">Nach diesem letzten Schritt sollte sich das Telefon automatisch anmelden.</span><span class="sxs-lookup"><span data-stu-id="42ecc-193">Following this last step, the phone should sign in automatically.</span></span>

### <a name="related-topics"></a><span data-ttu-id="42ecc-194">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="42ecc-194">Related topics</span></span>

- <span data-ttu-id="42ecc-195">Weitere Informationen über verfügbare Telefone finden Sie unter [Einsatz von Skype for Business Online-Telefonen](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="42ecc-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="42ecc-196">Kauf von Telefonen für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="42ecc-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)



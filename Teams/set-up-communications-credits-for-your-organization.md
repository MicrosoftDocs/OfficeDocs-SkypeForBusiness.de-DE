---
title: Einrichten von Guthaben für Kommunikationen für Ihre Organisation
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Hier erfahren Sie, wie Sie Abrechnungs Lizenzen für Kommunikations Kredite (PSTN-Verbrauch) für Ihre Benutzer und Ihre Organisation einrichten. '
ms.openlocfilehash: 8deb0d00365803ff8ae585f8f6d4dfefbf72108f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905587"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="ec560-103">Einrichten von Guthaben für Kommunikationen für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="ec560-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="ec560-p101">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="ec560-p101">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec560-109">Weitere Informationen zu den Kosten finden Sie [unter den Tarifen hier](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span><span class="sxs-lookup"><span data-stu-id="ec560-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="ec560-110">Schritt 1: Zuweisen einer Audiokonferenz-oder Anruf Plan Lizenz für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="ec560-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="ec560-111">Bei der Registrierung erhalten Sie je nach Land/Region eine bestimmte Anzahl Minuten.</span><span class="sxs-lookup"><span data-stu-id="ec560-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="ec560-112">Sie können in der [Liste der verfügbaren Länder oder Regionen nach Ihrem Land oder Ihrer Region für Audiokonferenzen und Anrufpläne](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) suchen, um die Anzahl der Minuten anzuzeigen, die Sie erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="ec560-112">You can search for your country or region in the [Country or region availability list for Audio Conferencing and Calling Plans](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) to see the number of minutes you will get.</span></span> <span data-ttu-id="ec560-113">Anrufe werden getrennt, sobald Sie diese Minuten aufgebraucht haben.</span><span class="sxs-lookup"><span data-stu-id="ec560-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="ec560-114">Um dies zu verhindern, müssen Sie Guthaben für Kommunikationen einrichten.</span><span class="sxs-lookup"><span data-stu-id="ec560-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="ec560-115">Dazu **müssen Sie Ihren Benutzern eine Lizenz für Audiokonferenzen oder für Telefonsysteme zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="ec560-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="ec560-116">Weisen Sie Ihren Benutzern eine Lizenz für **Audiokonferenzen** zu.</span><span class="sxs-lookup"><span data-stu-id="ec560-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="ec560-117">Nähres hierzu erfahren Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="ec560-117">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    <span data-ttu-id="ec560-118">Nachdem Sie diese Lizenz zugewiesen haben, müssen Sie Audiokonferenzen einrichten.</span><span class="sxs-lookup"><span data-stu-id="ec560-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="ec560-119">Schritt-für-Schritt-Anleitungen finden Sie unter [Testen oder kaufen von Audiokonferenzen in Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ec560-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="ec560-120">Weisen Sie Ihren Benutzern eine **Telefonanlage** und eine Lizenz für **Inlands-, Inlands-und Auslands** Gespräche zu.</span><span class="sxs-lookup"><span data-stu-id="ec560-120">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users.</span></span> <span data-ttu-id="ec560-121">Nähres hierzu erfahren Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="ec560-121">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ec560-122">Obwohl es für Kommunikationsguthaben nicht erforderlich ist, müssen Sie auch einen **Plan für Inlandsanrufe** oder eine Lizenz für **Inlands-und Auslandsanrufe** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec560-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="ec560-p106">Nach dem Zuweisen dieser Lizenzen müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen. Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="ec560-p106">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="ec560-125">Weitere Informationen finden Sie unter [Microsoft Teams-Add-on-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) .</span><span class="sxs-lookup"><span data-stu-id="ec560-125">For more information, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="ec560-126">Schritt 2: Einrichten von Guthaben für Kommunikationen für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="ec560-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="ec560-127">Anmelden beim neuen Microsoft 365 Admin Center mit Ihrem Geschäfts-oder Schulkonto.</span><span class="sxs-lookup"><span data-stu-id="ec560-127">Sign in to the new Microsoft 365 admin center with your work or school account.</span></span>
    
2. <span data-ttu-id="ec560-128">Wechseln Sie in der linken Navigationsleiste des Microsoft 365 Admin Center zu **Abrechnungs** > **Kauf-Services**.</span><span class="sxs-lookup"><span data-stu-id="ec560-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Purchase Services**.</span></span> <span data-ttu-id="ec560-129">Scrollen Sie nach unten, und wählen Sie **Add-ons**aus.</span><span class="sxs-lookup"><span data-stu-id="ec560-129">Scroll down and select **Add-Ons**.</span></span>

3. <span data-ttu-id="ec560-130">Wählen Sie **Kommunikationsguthaben**aus.</span><span class="sxs-lookup"><span data-stu-id="ec560-130">Select **Communications Credits**.</span></span>
    
4. <span data-ttu-id="ec560-131">Geben Sie auf der Seite **Communications Credits** -Abonnement Ihre Informationen ein, und klicken Sie dann auf **weiter**:</span><span class="sxs-lookup"><span data-stu-id="ec560-131">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="ec560-p108">**Guthaben hinzufügen**: Geben Sie den Betrag ein, den Sie Ihrem Konto hinzufügen möchten. Wenn Sie das automatische Aufladen nicht aktivieren, werden nach dem Aufbrauchen des Guthabens die Anruffunktionen, die über das Guthaben für Kommunikationen aktiviert werden, unterbrochen (z. B. eingehende gebührenfreie Dienste). Um zu vermeiden, dass Sie den Guthabensaldo für Kommunikationen jedes Mal auffüllen müssen, wenn er 0 (null) erreicht, empfehlen wir, die automatische Aufladefunktion zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ec560-p108">**Add funds** Enter the amount that you want to add to your account. If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service). To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="ec560-135">**Automatisch aufladen**: Wenn Sie das automatische Aufladen aktivieren, erhält Ihr Konto automatisch neues Guthaben, wenn der Saldo unter das von Ihnen festgesetzte Limit sinkt.</span><span class="sxs-lookup"><span data-stu-id="ec560-135">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="ec560-p109">Sie sollten die Option **Automatisches Aufladen** nutzen, um Dienstunterbrechungen zu vermeiden, falls der Guthabensaldo für Kommunikationen 0 (null) erreicht. Sie erhalten eine E-Mail, wenn Transaktionen für eine Aufladung erfolgreich waren oder fehlgeschlagen sind (z. B. im Fall einer abgelaufenen Kreditkarte) und wenn der Guthabensaldo für Kommunikationen 0 (null) erreicht.</span><span class="sxs-lookup"><span data-stu-id="ec560-p109">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero). You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="ec560-138">**Aufladebetrag**: Geben Sie in das Feld **Aufladen mit** den Betrag ein, der Ihrem Konto hinzugefügt werden soll, nachdem es den Kontostand, der das automatische Auffüllen auslöst, erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="ec560-138">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="ec560-p110">**Kontostand, der das automatische Auffüllen auslöst**: Geben Sie in das Feld **bei Guthaben unter** den Betrag ein, bei dem das automatische Aufladen „ *ausgelöst*  " wird. Nachdem Ihr Saldo diesen Betrag unterschritten hat, wird der Aufladebetrag dem Konto automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ec560-p110">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge. Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="ec560-p111">Das Guthaben wird nur zu den von Microsoft veröffentlichten Tarifen auf Guthaben für Kommunikationen angewendet, wenn die Dienste genutzt werden. Wenn ein Guthaben nicht innerhalb von 12 Monaten ab dem Kaufdatum aufgebraucht wird, verfällt es.</span><span class="sxs-lookup"><span data-stu-id="ec560-p111">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used. Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="ec560-143">Die monatliche Abrechnung für Kommunikationsguthaben wird nur angewendet, wenn der zugewiesene Fonds verwendet wurde, um zu erfahren, wie Sie Ihre monatliche Nutzung prüfen, lesen Sie den [Skype for Business-PSTN-Nutzungsbericht](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) .</span><span class="sxs-lookup"><span data-stu-id="ec560-143">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="ec560-144">Geben Sie jetzt Ihre Zahlungsinformationen ein, und wählen Sie **Bestellung aufgeben**aus.</span><span class="sxs-lookup"><span data-stu-id="ec560-144">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="ec560-p112">If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span><span class="sxs-lookup"><span data-stu-id="ec560-p112">If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="ec560-148">Jede Organisation verfügt über eine unterschiedliche Verwendung des Anrufplan-Volumes und-Gebühren, die berücksichtigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ec560-148">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="ec560-149">Diese Nutzungsdaten müssen Sie bei Ihrem aktuellen Dienstanbieter erfragen.</span><span class="sxs-lookup"><span data-stu-id="ec560-149">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="ec560-150">Organisationen, die bereits Skype for Business Online als Ihren Dienstanbieter verwenden, können Nutzungsdaten abrufen, indem Sie im **Skype for Business Admin Center** > **Berichte** > **über PSTN-Nutzungsdetails** melden.</span><span class="sxs-lookup"><span data-stu-id="ec560-150">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="ec560-151">Wenn Sie Kommunikationsguthaben einrichten, müssen Sie die Anruf Nutzung für Ihre Organisation untersuchen, um die benötigten Beträge zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="ec560-151">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="ec560-152">Informationen zur Anrufnutzung finden Sie im Bericht **PSTN-Nutzungsdetails**.</span><span class="sxs-lookup"><span data-stu-id="ec560-152">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="ec560-153">In diesem Bericht können Sie die anrufdatensätze nach Excel exportieren, wenn Sie die Daten speichern oder benutzerdefinierte Berichte erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="ec560-153">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="ec560-154">Wenn Sie wissen möchten, wie die Verwendung angezeigt wird, lesen Sie [Skype for Business-PSTN-Nutzungsbericht](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span><span class="sxs-lookup"><span data-stu-id="ec560-154">To learn how to see usage, read [Skype for Business PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="ec560-155">Schritt 3: Zuweisen einer Lizenz für Guthaben für Kommunikationen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="ec560-155">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="ec560-156">Mit Ihrem Firmen-oder Schulkonto anmelden</span><span class="sxs-lookup"><span data-stu-id="ec560-156">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="ec560-157">Navigieren Sie in der linken Navigationsleiste des Microsoft 365 Admin Center zu **Benutzer** > **Aktive Benutzer**, und wählen Sie die entsprechenden Benutzer aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ec560-157">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>
    
3. <span data-ttu-id="ec560-158">Wählen Sie **Lizenzen und apps**aus.</span><span class="sxs-lookup"><span data-stu-id="ec560-158">Choose **Licenses and Apps**.</span></span>
    
4. <span data-ttu-id="ec560-159">Schalten Sie die **Kommunikationsguthaben** auf **ein** , um diese Lizenz zuzuweisen, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="ec560-159">Toggle **Communications Credits** to **On** to assign this license, and then select **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ec560-160">Auch wenn Sie Benutzer haben, denen eine **Enterprise E5**-Lizenz zugewiesen ist, wird dies weiterhin empfohlen.</span><span class="sxs-lookup"><span data-stu-id="ec560-160">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="ec560-161">Sie suchen Informationen zu Plänen und Preisen?</span><span class="sxs-lookup"><span data-stu-id="ec560-161">Want to know about plans and pricing?</span></span>

<span data-ttu-id="ec560-162">Die Pläne und Preise finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="ec560-162">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="ec560-163">Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="ec560-163">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="ec560-164">Audio-Konferenz Pläne</span><span class="sxs-lookup"><span data-stu-id="ec560-164">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="ec560-165">Telefonsystempläne</span><span class="sxs-lookup"><span data-stu-id="ec560-165">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="ec560-166">Sie können Informationen auch anzeigen, indem Sie sich beim [Microsoft 365 Admin Center anmelden](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) und zu **Abrechnungs** > **Abonnements** > Abonnements**Hinzufügen**wechseln.</span><span class="sxs-lookup"><span data-stu-id="ec560-166">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="ec560-167">Eine Tabelle mit den Lizenzen, die für die einzelnen Features benötigt werden, finden Sie unter [Microsoft Teams-Add-on-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="ec560-167">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ec560-168">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ec560-168">Related topics</span></span>

- [<span data-ttu-id="ec560-169">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ec560-169">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="ec560-170">Einrichten von Cloud-Voicemail – Administratorhilfe</span><span class="sxs-lookup"><span data-stu-id="ec560-170">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="ec560-171">[Einrichten von Anrufplänen](set-up-calling-plans.md) und [Anrufpläne für Office 365](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="ec560-171">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="ec560-172">Hinzufügen und Verwalten von Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="ec560-172">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
 

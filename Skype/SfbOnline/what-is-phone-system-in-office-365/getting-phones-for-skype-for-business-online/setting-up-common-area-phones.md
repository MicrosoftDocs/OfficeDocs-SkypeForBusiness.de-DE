---
title: Einrichten von Telefonen in öffentlichen Bereichen
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
description: Hier erfahren Sie die Schritte zur Bereitstellung, um die richtige Firmware erhalten möchten, aktualisieren sie bei Bedarf, Zuweisen von Lizenzen und Konfigurieren von Einstellungen für Telefone in öffentlichen Bereichen.
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="8ad06-103">Einrichten von Telefonen in öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="8ad06-103">Set up common area phones</span></span>
<span data-ttu-id="8ad06-104">Ein Telefon im öffentlichen Bereich (CAP) platziert wird in der Regel im Bereich der ein Wartebereich oder einem anderen Bereich, der viele Personen zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="8ad06-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="8ad06-105">Angenommen, ein Empfang für Telefone, Tür Telefon- oder Meeting Room Telefon, CAPs Geräte, sondern als Benutzer eingerichtet sind, und melden Sie sich automatisch in einem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="8ad06-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="8ad06-106">In den folgenden Schritten helfen wir Ihnen richten Sie ein Konto für Telefonsystem mit plant aufrufen, damit Sie diese Typen von Telefonen für Ihre Organisation bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="8ad06-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="8ad06-107">Erforderliche Komponenten für Telefone in öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="8ad06-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="8ad06-108">Erstes müssen Sie besteht darin, sicherzustellen, dass Sie über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="8ad06-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="8ad06-109">Kaufen Sie Telefone in öffentlichen Bereichen Lizenz und Aufrufen von planen.</span><span class="sxs-lookup"><span data-stu-id="8ad06-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="8ad06-110">Suchen nach und genehmigte Telefone kaufen (Anzeigen der Liste [hier](deploying-skype-for-business-online-phones.md)).</span><span class="sxs-lookup"><span data-stu-id="8ad06-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>         
 - <span data-ttu-id="8ad06-111">Aktualisieren Sie die Firmware auf Ihrer Telefone (Siehe unterstützt Firmware [in diesem Thema](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="8ad06-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md).</span></span>  <span data-ttu-id="8ad06-112">Sie können die Firmware auf Sie Telefon auf diese Weise überprüfen:</span><span class="sxs-lookup"><span data-stu-id="8ad06-112">You can check the firmware on you phone by doing this:</span></span>       
    - <span data-ttu-id="8ad06-113">**Telefone Polycom VVX**: Rufen Sie die **Einstellungsseite** > **Status** > **Plattform** > **Anwendung** > **Main**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="8ad06-114">**Yealink Telefone**: Wechseln Sie auf **Status** auf dem Bildschirm Telefon.</span><span class="sxs-lookup"><span data-stu-id="8ad06-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="8ad06-115">**AudioCodes Telefone**: Gehen Sie zum **Menü** > **Gerätestatus** > **Firmwareversion** auf der Startseite.</span><span class="sxs-lookup"><span data-stu-id="8ad06-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
    - <span data-ttu-id="8ad06-116">**Lync Phone Edition (LPE) Telefone**: Gehen Sie zum **Menü** > **Systeminformationen** aus dem Startbildschirm.</span><span class="sxs-lookup"><span data-stu-id="8ad06-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="8ad06-117">Firmwareupdates werden vom Skype for Business-Dienst verwaltet.</span><span class="sxs-lookup"><span data-stu-id="8ad06-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="8ad06-118">Die Firmware für alle Skype for Business-zertifizierten Telefone wird auf den Skype for Business-Updateserver hochgeladen, und Geräteupdates sind in allen Telefonen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8ad06-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

    <span data-ttu-id="8ad06-119">Je nachdem, wann die Telefone inaktiv sind und welche Abrufintervalle festgelegt sind, werden die neuesten zertifizierten Builds automatisch heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="8ad06-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="8ad06-120">Sie können die Device Update Einstellungen deaktivieren, indem Sie mithilfe des Cmdlets [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) und Festlegen des Parameters *EnableDeviceUpdate* auf `false`.</span><span class="sxs-lookup"><span data-stu-id="8ad06-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="8ad06-121">Einrichten einer Telefone in öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="8ad06-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="8ad06-122">Sie müssen die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8ad06-122">You will need to follow these steps:</span></span>

### <a name="set-up-your-user-account-for-the-phone"></a><span data-ttu-id="8ad06-123">Richten Sie Ihr Benutzerkonto für das Telefon</span><span class="sxs-lookup"><span data-stu-id="8ad06-123">Set up your user account for the phone</span></span>

#### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="8ad06-124">Schritt 1: Erwerben von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="8ad06-124">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="8ad06-125">Wechseln Sie in das Office 365 Administrationscenter zu **Abrechnung** > **Dienste erwerben**, und fügen Sie **andere Pläne**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-125">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP license.png](../../images/cap-license.png)
2. <span data-ttu-id="8ad06-127">Klicken Sie auf **Telefon im öffentlichen Bereich** > **Jetzt kaufen** > auf der Seite auf **Auschecken** , klicken Sie auf **Jetzt kaufen**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-127">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="8ad06-128">Klicken Sie auf erweitern **Add-on-Abonnements** , und klicken Sie dann auf Kaufen aufrufen planen.</span><span class="sxs-lookup"><span data-stu-id="8ad06-128">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="8ad06-129">Wählen Sie die **nationalen Plan aufrufen** oder **nationalen und internationalen aufrufen planen**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-129">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="8ad06-130">Eine Lizenz Telefonsystem ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8ad06-130">You don't need a Phone System license.</span></span> <span data-ttu-id="8ad06-131">Es wurde mit der Lizenz für **Telefone in öffentlichen Bereichen** enthalten.</span><span class="sxs-lookup"><span data-stu-id="8ad06-131">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="8ad06-132">Weitere Informationen zu Lizenzen finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="8ad06-132">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="8ad06-133">Schritt 2 – Erstellen eines neuen Benutzerkontos für das Telefon und die Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="8ad06-133">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="8ad06-134">Wechseln Sie in das Office 365 Administrationscenter zu **Benutzern** > **Aktive Benutzer** > **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-134">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="8ad06-135">Tragen Sie einen **Benutzernamen ein** , wie "Main" für den ersten Namen und "Empfang" für den zweiten Namen.</span><span class="sxs-lookup"><span data-stu-id="8ad06-135">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="8ad06-136">Wenn dies nicht der Fall einer standardbrowserformulare wie "Main Empfang" einen **Anzeigenamen** zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="8ad06-136">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="8ad06-137">Tragen Sie einen **Benutzernamen ein** , wie "MainReception" oder "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="8ad06-137">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="8ad06-138">Für Telefone in öffentlichen Bereichen möchten Sie möglicherweise ein Kennwort manuell festlegen oder das gleiche Kennwort für alle von Ihnen Telefone in öffentlichen Bereichen haben.</span><span class="sxs-lookup"><span data-stu-id="8ad06-138">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="8ad06-139">Darüber hinaus glauben Sie zum Aufheben der Auswahl **stellen diesen Benutzer ändern ihres Kennworts beim erstmaligen Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-139">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="8ad06-140">Warte!!</span><span class="sxs-lookup"><span data-stu-id="8ad06-140">WAIT!!</span></span> <span data-ttu-id="8ad06-141">Klicken Sie nicht auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-141">Don't click **Add**!!</span></span> <span data-ttu-id="8ad06-142">Ugh, wenn Sie **Hinzufügen** die klicken, dies: Office 365 Administrationscenter > **Benutzer** > **aktive Benutzer** und suchen Sie anschließend den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8ad06-142">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="8ad06-143">Klicken Sie dann auf der Eigenschaftenseite des Benutzers auf **Lizenzen** , und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-143">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="8ad06-144">Klicken Sie auf der Seite **Lizenzen** aktivieren Sie **Telefone in öffentlichen Bereichen** , und wählen Sie entweder einen **Nationalen aufrufen planen** oder eine National und **International aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-144">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="8ad06-145">Wenn Sie noch vorhanden sind, weisen Sie die Lizenzen an diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8ad06-145">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="8ad06-146">Klicken Sie auf der gleichen Seite **um Lizenzen**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="8ad06-146">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="8ad06-147">Aktivieren Sie die folgenden:</span><span class="sxs-lookup"><span data-stu-id="8ad06-147">Turn on the following:</span></span>
    - <span data-ttu-id="8ad06-148">Telefone in öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="8ad06-148">Common Area Phone</span></span>
    - <span data-ttu-id="8ad06-149">Klicken Sie dann müssen Sie entweder einen **Nationalen aufrufen planen** oder eine National und **International aufrufen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="8ad06-149">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>
     
    <span data-ttu-id="8ad06-150">Zuweisen von Lizenzen wird wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="8ad06-150">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="8ad06-152">Nur, damit Sie wissen, ist Skype für Business Plan 2 enthalten, mit der Lizenz für **Telefone in öffentlichen Bereichen** .</span><span class="sxs-lookup"><span data-stu-id="8ad06-152">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="8ad06-153">Weitere Informationen finden Sie unter [Benutzer hinzufügen](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="8ad06-153">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

#### <a name="step-3---assign-a-phone-number-to-the-user"></a><span data-ttu-id="8ad06-154">Schritt 3: dem Benutzer eine Telefonnummer zuweisen</span><span class="sxs-lookup"><span data-stu-id="8ad06-154">Step 3 - Assign a phone number to the user</span></span>
<span data-ttu-id="8ad06-155">![SFB-Logo-30x30.png](../../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="8ad06-155">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
1. <span data-ttu-id="8ad06-156">Im Office 365 Administrationscenter > **Admin zentriert** > **Skype für Unternehmen**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-156">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="8ad06-157">In der **Skype für Business Administrationscenter** >  **VoIP** > **Rufnummern**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-157">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="8ad06-158">Wählen Sie eine Rufnummer aus der Liste der Rufnummern, und klicken Sie auf **zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-158">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="8ad06-159">Geben Sie auf der Seite **zuweisen** im Feld **Voice-Benutzer** den Namen des Benutzers, der für das Telefon und wählen Sie dann der Benutzer in der **ein VoIP-Benutzer auswählen** Dropdown-Liste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8ad06-159">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span> 
5. <span data-ttu-id="8ad06-160">Nutzen Sie dort auch müssen Sie zum Hinzufügen einer Notfall Adresse.</span><span class="sxs-lookup"><span data-stu-id="8ad06-160">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="8ad06-161">Nachdem Sie durchsuchen, suchen Sie unter **Wählen Sie Notfall Adresse** auf die richtige für Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="8ad06-161">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="8ad06-162">Klicken Sie auf **Speichern** , und die Benutzer sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="8ad06-162">Click **Save** and your user should look like this:</span></span>

    ![Cap-Benutzer-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="8ad06-164">Benutzer werden nur angezeigt, wenn sie eine **Telefonsystem** Lizenz angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="8ad06-164">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="8ad06-165">Wenn Sie nur dies, erst dann manchmal etwas für den Benutzer in der Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8ad06-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="8ad06-166">Mehr Inhalte finden Sie unter [Getting Rufnummern für Ihre Benutzer](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="8ad06-166">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="8ad06-167">Wenn Sie wissen möchten, können Sie auch Ihre Telefonnummer nutzen, indem Sie mit einem anderen Netzbetreiber und "*Port*" oder zu Office 365 übertragen.</span><span class="sxs-lookup"><span data-stu-id="8ad06-167">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="8ad06-168">Angezeigt wird, [Übertragen von Telefonnummern zu Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="8ad06-168">See, [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>

## <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="8ad06-169">Schritt 4: Einrichten des Telefons</span><span class="sxs-lookup"><span data-stu-id="8ad06-169">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="8ad06-170">**Festlegen des Modus auf einem Telefon**</span><span class="sxs-lookup"><span data-stu-id="8ad06-170">**Setting the mode on a phone**</span></span>

<span data-ttu-id="8ad06-171">Das Telefon oder Telefone, die Sie benötigen den Telefone in öffentlichen Bereichen-Modus aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8ad06-171">The phone or phones you have must have the Common Area Phone mode turned on.</span></span> <span data-ttu-id="8ad06-172">Möglicherweise möchten Sie überprüfen, um sicherzustellen, dass dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="8ad06-172">You might want to check on that to make sure they do.</span></span> 

<span data-ttu-id="8ad06-173">**Es folgt ein Beispiel dafür, wie Sie ein Telefon Polycom VVX einrichten**</span><span class="sxs-lookup"><span data-stu-id="8ad06-173">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="8ad06-174">Aktivieren Sie Telefone in öffentlichen Bereichen Modus für das Polycom VVX, durch die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8ad06-174">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="8ad06-175">In Ihrem Browser eine Verbindung mit der Webschnittstelle, damit Sie CAP-Modus aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="8ad06-175">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="8ad06-176">Wechseln Sie zur **Einstellung** und die Option **Skype für Business-Einstellung** , und wählen Sie **Telefone in öffentlichen Bereichen**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-176">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="8ad06-177">Klicken Sie auf **Ja,** um die Einstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8ad06-177">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="8ad06-178">Nun, dass der CAP-Modus aktiviert ist, richten Sie das Telefon mit Display des Telefons.</span><span class="sxs-lookup"><span data-stu-id="8ad06-178">Now that the CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="8ad06-179">Die Anzeige sollte anzeigen **CaAP ist aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-179">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="8ad06-180">Klicken Sie dann folgendermaßen Sie vor:</span><span class="sxs-lookup"><span data-stu-id="8ad06-180">Then do the following:</span></span>

    1. <span data-ttu-id="8ad06-181">Klicken Sie auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-181">Click **Settings**.</span></span>
    2. <span data-ttu-id="8ad06-182">Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-182">Select **Advanced**.</span></span>
    3. <span data-ttu-id="8ad06-183">Geben Sie das Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="8ad06-183">Enter the password.</span></span>
    4. <span data-ttu-id="8ad06-184">Wählen Sie unter **Einstellungen für die** **Common Area Phone Settings**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-184">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="8ad06-185">Aktivieren Sie **CAP** und **CAP-Admin-Modus**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-185">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="8ad06-186">Klicken Sie auf **Konfiguration speichern**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-186">Click **Save Config**.</span></span>

- <span data-ttu-id="8ad06-187">OK, kann nun Ihr Telefon, damit Sie auf der Startseite anmelden können.</span><span class="sxs-lookup"><span data-stu-id="8ad06-187">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="8ad06-188">Melden Sie sich, indem Sie **Einstellungen**auswählen > **Features** > **Skype für Business.**</span><span class="sxs-lookup"><span data-stu-id="8ad06-188">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="8ad06-189">Wählen Sie **Anmeldeinformationen des Benutzers**aus, und wählen Sie **Web - Anmeldung (CAP)** um einen Code zu generieren.</span><span class="sxs-lookup"><span data-stu-id="8ad06-189">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="8ad06-190">Besuchen Sie die [Bereitstellung Portal](http://aka.ms/skypecap), und melden Sie sich als **Administrator**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-190">Go to the [provisioning portal](http://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="8ad06-191">Geben Sie den Anzeigenamen (beispielsweise Main Empfang).</span><span class="sxs-lookup"><span data-stu-id="8ad06-191">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="8ad06-192">Wenn **Suchen für Telefone in öffentlichen Bereichen nur** aktiviert ist, deaktivieren Sie das Kontrollkästchen, und suchen Sie erneut. "</span><span class="sxs-lookup"><span data-stu-id="8ad06-192">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.\`</span></span>

    5. <span data-ttu-id="8ad06-193">Klicken Sie im Codefenster paarungs Geben Sie den Code auf dem Telefon angezeigt, und klicken Sie auf **Bereitstellung**.</span><span class="sxs-lookup"><span data-stu-id="8ad06-193">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="8ad06-194">Nach diesem letzten Schritt sollte das Telefon automatisch anmelden.</span><span class="sxs-lookup"><span data-stu-id="8ad06-194">Following this last step, the phone should sign in automatically.</span></span>

### <a name="related-topics"></a><span data-ttu-id="8ad06-195">See Also</span><span class="sxs-lookup"><span data-stu-id="8ad06-195">Related topics</span></span>

- <span data-ttu-id="8ad06-196">Weitere Informationen zu verfügbaren Telefonen unter [Bereitstellen von Skype für Business Online-Telefone](deploying-skype-for-business-online-phones.md).</span><span class="sxs-lookup"><span data-stu-id="8ad06-196">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="8ad06-197">Kauf von Telefonen für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8ad06-197">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)



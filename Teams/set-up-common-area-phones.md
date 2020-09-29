---
title: Einrichten der Telefon Lizenz für den öffentlichen Bereich
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Informationen zum Einrichten von Telefonen im öffentlichen Bereich für Lobbies, Empfangsbereiche und Konferenzräume '
ms.openlocfilehash: dfde8c601c0a52dc56a3d76903b788400a5b299a
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294461"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="8b4c2-103">Einrichten der Lizenz für Telefone für gemeinsame Bereiche für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b4c2-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="8b4c2-104">Telefone im öffentlichen Bereich unterstützen keine Voicemail.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="8b4c2-105">Ein Telefon im öffentlichen Bereich befindet sich normalerweise in einem Bereich wie einer Lobby oder einem anderen Bereich, der für viele Personen zur Verfügung steht, um einen Anruf zu tätigen. beispielsweise einen Empfangsbereich, eine Lobby oder ein Konferenztelefon.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="8b4c2-106">Telefone im öffentlichen Bereich sind mit Konten verbunden, die mit einer Telefon Lizenz für den öffentlichen Bereich verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="8b4c2-107">Die TeamsIPPhone-Richtlinie muss auch entsprechend festgesetzt werden, damit das Telefon über eine Benutzeroberfläche mit gemeinsamem Bereich verfügt.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="8b4c2-108">In den nachstehenden Schritten unterstützen wir Sie beim Einrichten eines Kontos für das Telefon System für die Bereitstellung von Telefonen im allgemeinen Bereich für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="8b4c2-109">Für eine vollständige Besprechungsraum-Erfahrung, einschließlich Audiokonferenzen, sollten Sie erwägen, die dedizierte Besprechungsraum-Lizenz mit einem Besprechungsraum Gerät zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="8b4c2-110">Zunächst müssen Sie eine Lizenz für das Common Area Phone (GAP) erwerben und sicherstellen, dass Sie über ein zertifiziertes Telefon verfügen.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="8b4c2-111">Informationen zu zertifizierten Telefonen finden Sie unter [Microsoft Teams-Geräte](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span><span class="sxs-lookup"><span data-stu-id="8b4c2-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="8b4c2-112">Schritt 1 - Lizenzen kaufen</span><span class="sxs-lookup"><span data-stu-id="8b4c2-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="8b4c2-113">Wechseln Sie im Microsoft 365 Admin Center zu **Abrechnungs**  >  **Kauf Dienste** , und erweitern Sie dann **andere Pläne**.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Screenshot der Telefon Kachel für den öffentlichen Bereich](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="8b4c2-115">Wählen Sie den **Bereich Telefon**  >  **Jetzt kaufen**.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="8b4c2-116">Klicken Sie auf der Seite Checkout auf **Jetzt kaufen**.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="8b4c2-117">Erweitern Sie **Add-on-Abonnements** , und klicken Sie dann, um einen Anrufplan zu kaufen.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="8b4c2-118">Wählen Sie entweder den Plan für **Inlandsanrufe** oder den Tarif für **Inlands-und Auslandsgespräche**.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="8b4c2-119">Wenn Sie das direkte Routing von Microsoft Phone System verwenden, benötigen Sie keine Anruf Plan Lizenz.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="8b4c2-120">Sie müssen keine Telefon System Lizenz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="8b4c2-121">Sie ist in der Lizenz Telefon für gemeinsame Bereiche enthalten.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="8b4c2-122">Weitere Informationen zu Lizenzen finden Sie unter [Microsoft Teams-Add-on-Lizenzierung](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="8b4c2-122">For more information on licenses, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="8b4c2-123">Die Telefon Lizenz für den öffentlichen Bereich unterstützt:</span><span class="sxs-lookup"><span data-stu-id="8b4c2-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="8b4c2-124">Telefon für gemeinsame Bereiche</span><span class="sxs-lookup"><span data-stu-id="8b4c2-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="8b4c2-125">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8b4c2-125">Skype for Business</span></span> |   <span data-ttu-id="8b4c2-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="8b4c2-126">&#x2714;</span></span> |
|<span data-ttu-id="8b4c2-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b4c2-127">Microsoft Teams</span></span> |   <span data-ttu-id="8b4c2-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="8b4c2-128">&#x2714;</span></span> |
|<span data-ttu-id="8b4c2-129">Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="8b4c2-129">Phone System</span></span> |    <span data-ttu-id="8b4c2-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="8b4c2-130">&#x2714;</span></span> |
|<span data-ttu-id="8b4c2-131">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="8b4c2-131">Audio Conferencing</span></span> |       <span data-ttu-id="8b4c2-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="8b4c2-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="8b4c2-133">Microsoft InTune</span><span class="sxs-lookup"><span data-stu-id="8b4c2-133">Microsoft Intune</span></span> |    <span data-ttu-id="8b4c2-134">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="8b4c2-134">&#x2714;</span></span> |
|<span data-ttu-id="8b4c2-135">Weltweite Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="8b4c2-135">Worldwide Availability</span></span> |       <span data-ttu-id="8b4c2-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="8b4c2-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="8b4c2-137">Kanalverfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="8b4c2-137">Channel Availability</span></span> |    <span data-ttu-id="8b4c2-138">EA, EAS, CSP, gcc, EBS, Web Direct</span><span class="sxs-lookup"><span data-stu-id="8b4c2-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="8b4c2-139">&sup1; Telefone im öffentlichen Bereich können mit einer vom Besprechungsorganisator bereitgestellten Einwahlnummer an Audiokonferenzen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="8b4c2-140">&sup2; In souveränen Clouds nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="8b4c2-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="8b4c2-141">Schritt 2 - Ein neues Benutzerkonto für das Telefon erstellen und die Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="8b4c2-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="8b4c2-142">Wechseln Sie im Microsoft 365 Admin Center zu **Benutzer**, denen  >  **aktive**Benutzer  >  **einen Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="8b4c2-143">Geben Sie einen Benutzernamen wie "Main" für den Vornamen und "Empfang" für den zweiten Namen ein.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="8b4c2-144">Geben Sie einen Anzeigenamen ein, wenn er nicht wie "Hauptempfang" automatisch generiert wird.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="8b4c2-145">Geben Sie einen Benutzernamen wie "MainReception" oder "Mainlobby" ein.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="8b4c2-146">Für Telefone im öffentlichen Bereich empfiehlt es sich, ein Kennwort manuell festzulegen oder das gleiche Kennwort für alle Telefone im öffentlichen Bereich zu haben.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="8b4c2-147">Darüber hinaus ist es möglich, dass Sie das Kontrollkästchen **diesen Benutzer zum Ändern des Kennworts bei der ersten Anmeldung** verwenden deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="8b4c2-148">Weisen Sie dem Benutzer die Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-148">Assign the licenses to the user.</span></span> <span data-ttu-id="8b4c2-149">Klicken Sie auf der gleichen Seite auf **Produktlizenzen** erweitern.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="8b4c2-150">Aktivieren Sie das Telefon für den öffentlichen Bereich, und wählen Sie entweder einen **Inlandsanruf Plan** oder einen **Plan für Inlands-und Auslandsanrufe**aus.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Screenshot mit Lizenzzuweisung](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="8b4c2-152">Wenn Sie das direkte Routing von Microsoft Phone System verwenden, müssen Sie keine Anruf Plan Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="8b4c2-153">Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="8b4c2-153">For more information, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="8b4c2-154">Schritt 3 - Eine Telefonnummer dem Benutzerkonto Telefon für gemeinsame Bereich zuweisen</span><span class="sxs-lookup"><span data-stu-id="8b4c2-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="8b4c2-155">Verwenden Sie das Team Admin Center, um dem Benutzer eine Nummer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="8b4c2-156">Wählen Sie im Team Admin Center die Option **Voicemail**-  >  **Nummern**aus.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="8b4c2-157">Wählen Sie eine Nummer aus der Liste der Telefonnummern aus und klicken Sie auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="8b4c2-158">Geben Sie auf der Seite **zuweisen** im Feld VoIP-Benutzer den Namen des Benutzers ein, der das Telefon verwenden soll, und wählen Sie dann den Benutzer in der Dropdownliste **Sprachbenutzer auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="8b4c2-159">Als nächstes müssen Sie eine Notfalladresse hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="8b4c2-160">Wählen Sie in der Dropdownliste **Suchen**nach Ort, nach **Beschreibung suchen**oder nach **Ort suchen** aus, und geben Sie dann den Ort, die Beschreibung oder den Ort in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="8b4c2-161">Wenn Sie nach der Suche suchen, suchen Sie unter **Notfalladresse auswählen** , um das richtige für Sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="8b4c2-162">Klicken Sie auf **Speichern** und Ihr Benutzer sollte so aussehen:</span><span class="sxs-lookup"><span data-stu-id="8b4c2-162">Click **Save** and your user should look like this:</span></span>

   ![Screenshot mit Lizenzzuweisung](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="8b4c2-164">Benutzer werden nur angezeigt, wenn Sie über eine Telefon System Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="8b4c2-165">Wenn Sie dies gerade erst getan haben, dann kann es etwas dauern, bis der Benutzer in der Liste erscheint.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="8b4c2-166">Weitere Informationen finden Sie unter [Abrufen von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="8b4c2-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="8b4c2-167">Sie können auch Ihre Telefonnummer, die Sie mit einem anderen Netzbetreiber haben, übernehmen und "portieren" oder auf Microsoft 365 oder Office 365 übertragen.</span><span class="sxs-lookup"><span data-stu-id="8b4c2-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="8b4c2-168">Weitere Informationen finden Sie unter [übertragen von Telefonnummern in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8b4c2-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

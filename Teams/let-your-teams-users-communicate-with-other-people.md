---
title: Kommunizieren Sie mit Benutzern in einer anderen Organisation Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Strat_MT_TeamsAdmin
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Finden Sie unter Konfigurieren von Teams, damit die Benutzer mit Benutzern in anderen Organisationen kommunizieren können.
ms.openlocfilehash: 3eaffac3571abc70d4964ea4a8955f187d1e988f
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "23844637"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="7f0cb-103">Lassen Sie Ihren Teams Benutzer Chat und kommunizieren mit Benutzern in einer anderen Organisation von Teams</span><span class="sxs-lookup"><span data-stu-id="7f0cb-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="7f0cb-104">Führen Sie die Schritte in diesem Artikel in folgenden Fällen aus:</span><span class="sxs-lookup"><span data-stu-id="7f0cb-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="7f0cb-105">Sie müssen die Benutzer in unterschiedlichen Domänen in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-105">You have users in different domains in your business.</span></span> <span data-ttu-id="7f0cb-106">Beispiel: Rob@ContosoEast.com und Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="7f0cb-107">Sie möchten die Personen in Ihrer Organisation Teams verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="7f0cb-108">Sie möchten Personen in der ganzen Welt, die Teams verwendet wird, in der Lage, zu finden, und wenden Sie sich mithilfe Ihrer e-Mail-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="7f0cb-109">Wenn Sie und ein weiterer Benutzer aktivieren des externen Zugriffs und des jeweils anderen Domänen ermöglichen, diese verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="7f0cb-110">Wenn sie nicht funktioniert, der andere Benutzer sollten sicherstellen, dass seine oder ihre Konfiguration Ihrer Domäne blockieren nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="7f0cb-111">Gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="7f0cb-111">Follow these steps:</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="7f0cb-112">Lassen Sie Ihren Teams Benutzer Chat und kommunizieren mit Benutzern in einer anderen Organisation von Teams</span><span class="sxs-lookup"><span data-stu-id="7f0cb-112">Let your Teams users chat and communicate with users in another Teams organization</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="7f0cb-113">Schritt 1: Stellen Sie sicher, dass Sie richten Sie die Ports und URLs, die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-113">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="7f0cb-114">**Am häufigsten haben Benutzer beim Einrichten der Kommunikation zwischen Unternehmen Probleme damit, die [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) richtig festzulegen.**</span><span class="sxs-lookup"><span data-stu-id="7f0cb-114">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="7f0cb-115">Schritt 2: Aktivieren Ihrer Organisation, um die Kommunikation mit einer anderen Organisation von Teams</span><span class="sxs-lookup"><span data-stu-id="7f0cb-115">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="7f0cb-116">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="7f0cb-116">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

   1. <span data-ttu-id="7f0cb-117">Wechseln Sie im linken Navigationsbereich **Org geltende**Einstellungen > **externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-117">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="7f0cb-118">Klicken Sie am oberen Rand der Seite **externen Zugriff** auf **externen Zugriff** auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-118">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="7f0cb-119">Fügen Sie der anderen Organisation Domäne zur Liste zugelassenen hinzu, indem Sie auf **Domäne hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-119">Add the other organization's domain to the allowed list by clicking **Add domain**.</span></span> <span data-ttu-id="7f0cb-120">Klicken Sie im Bereich **Hinzufügen einer Domäne** zu platzieren Domain Name klicken Sie auf **zulässige** und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-120">In the **Add a domain** pane, put in the domain name click **Allowed** and then **Done**.</span></span>

   4. <span data-ttu-id="7f0cb-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-121">Click **Save**.</span></span> 

   5. <span data-ttu-id="7f0cb-122">Stellen Sie sicher, dass der Administrator in der anderen Teams Organisation dieselben Schritte wird.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-122">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="7f0cb-123">Beispiel: In der Liste der **zugelassenen Domänen** muss der Administrator der anderen Organisation die Domäne für Ihr Unternehmen eingeben.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-123">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

### <a name="step-3---test-it"></a><span data-ttu-id="7f0cb-124">Schritt 3: Testen sie das Formular</span><span class="sxs-lookup"><span data-stu-id="7f0cb-124">Step 3 - Test it</span></span>
<span data-ttu-id="7f0cb-125">Um die Installation zu testen, benötigen Sie ein Teams-Benutzer, die nicht hinter der Firewall befindet.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-125">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="7f0cb-126">Nachdem Sie und der Administrator aus der Organisation die **Zugriff durch externe** Einstellungen geändert haben, sollten Sie gut zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-126">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="7f0cb-127">In der app Teams nach e-Mail-Adresse der Person suchen Sie, und senden Sie eine Anforderung zum chat.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-127">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="7f0cb-128">Bitten Sie Ihren Teams Kontakt senden eine Anforderung an chat.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-128">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="7f0cb-129">Wenn Sie die Anfrage nicht erhalten, stellen die Firewalleinstellungen das Problem dar (dabei wird angenommen, dass der Kontakt bereits die Richtigkeit seiner Firewalleinstellungen überprüft hat).</span><span class="sxs-lookup"><span data-stu-id="7f0cb-129">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="7f0cb-130">Eine andere Möglichkeit zu prüfen, ob das Problem der Firewall ist ist, gehen Sie an einem Speicherort Wifi nicht hinter der Firewall wie einem Café und Teams das Senden einer Anforderung an den Kontakt zu chat verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-130">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="7f0cb-131">Wenn die Nachricht dort gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-131">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="7f0cb-132">Kommunizieren Sie mit Benutzern in einer Skype für Business Online-Organisation</span><span class="sxs-lookup"><span data-stu-id="7f0cb-132">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="7f0cb-133">Wenn Sie es bis zu Let einrichten, die Ihrer Benutzer Teams suchen, und wenden Sie sich an Benutzer, die in einer Skype für Business-Organisation sind, müssen Sie die Admin in der Organisation an die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-133">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization, you will the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="7f0cb-134">![SFB-Logo-30x30.png](media/sfb-logo-30x30.png) **Mithilfe von Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="7f0cb-134">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="7f0cb-135">Haben Sie die Admin, Organisation führen Sie diese Schritte:</span><span class="sxs-lookup"><span data-stu-id="7f0cb-135">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="7f0cb-136">Gehen Sie in Office 365 Admin Center zu **Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-136">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
  
2. <span data-ttu-id="7f0cb-137">Wählen Sie unter **Skype for Business Admin Center**die Option **Organisation** > **Externe Kommunikation**.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-137">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="7f0cb-138">Zum Einrichten der Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne, in der Dropdown-Feld auswählen **auf nur für zulässige Domänen**.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-138">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="7f0cb-p107">ODER wählen Sie, wenn Sie die Kommunikation mit allen anderen Unternehmen aktivieren möchten, die über offene Skype for Business-Richtlinien verfügen, die Option **Aktivieren mit Ausnahme der blockierten Domänen** aus. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-p107">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
4. <span data-ttu-id="7f0cb-141">Wählen Sie unter **blockiert oder zugelassenen Domänen**, **+** , und fügen Sie den Namen der Domäne, die Sie zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-141">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="7f0cb-142">Stellen Sie sicher, dass der Administrator in der anderen Organisation dieselben Schritte wird.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-142">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="7f0cb-143">Beispiel: In der Liste der **zugelassenen Domänen** muss der Administrator der anderen Organisation die Domäne für Ihr Unternehmen eingeben.</span><span class="sxs-lookup"><span data-stu-id="7f0cb-143">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="7f0cb-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7f0cb-144">Related topics</span></span>

<span data-ttu-id="7f0cb-145">[Melden Sie sich Teams](sign-in-teams.md)
[Endbenutzer Schulungen für Teams](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="7f0cb-145">[Sign in teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>


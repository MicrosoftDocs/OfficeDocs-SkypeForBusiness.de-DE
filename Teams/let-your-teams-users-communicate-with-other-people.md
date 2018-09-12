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
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Finden Sie unter Konfigurieren von Teams, damit die Benutzer mit Benutzern in anderen Organisationen kommunizieren können.
ms.openlocfilehash: da76d75ba44215b11b68550fa06d1fab87f19e56
ms.sourcegitcommit: 6732f56535d60a46e6998cde64103e8530dd6452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "23937827"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="7168f-103">Lassen Sie Ihren Teams Benutzer Chat und kommunizieren mit Benutzern in einer anderen Organisation von Teams</span><span class="sxs-lookup"><span data-stu-id="7168f-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="7168f-104">Führen Sie die Schritte in diesem Artikel in folgenden Fällen aus:</span><span class="sxs-lookup"><span data-stu-id="7168f-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="7168f-105">Sie müssen die Benutzer in unterschiedlichen Domänen in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="7168f-105">You have users in different domains in your business.</span></span> <span data-ttu-id="7168f-106">Beispiel: Rob@ContosoEast.com und Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="7168f-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="7168f-107">Sie möchten die Personen in Ihrer Organisation Teams verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="7168f-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="7168f-108">Sie möchten Personen in der ganzen Welt, die Teams verwendet wird, in der Lage, zu finden, und wenden Sie sich mithilfe Ihrer e-Mail-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="7168f-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="7168f-109">Wenn Sie und ein weiterer Benutzer aktivieren des externen Zugriffs und des jeweils anderen Domänen ermöglichen, diese verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7168f-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="7168f-110">Wenn sie nicht funktioniert, der andere Benutzer sollten sicherstellen, dass seine oder ihre Konfiguration Ihrer Domäne blockieren nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7168f-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="7168f-111">Gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="7168f-111">Follow these steps:</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="7168f-112">Lassen Sie Ihren Teams Benutzer Chat und kommunizieren mit Benutzern in einer anderen Organisation von Teams</span><span class="sxs-lookup"><span data-stu-id="7168f-112">Let your Teams users chat and communicate with users in another Teams organization</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="7168f-113">Schritt 1: Stellen Sie sicher, dass Sie richten Sie die Ports und URLs, die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7168f-113">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="7168f-114">**Am häufigsten haben Benutzer beim Einrichten der Kommunikation zwischen Unternehmen Probleme damit, die [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) richtig festzulegen.**</span><span class="sxs-lookup"><span data-stu-id="7168f-114">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="7168f-115">Schritt 2: Aktivieren Ihrer Organisation, um die Kommunikation mit einer anderen Organisation von Teams</span><span class="sxs-lookup"><span data-stu-id="7168f-115">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="7168f-116">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="7168f-116">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

   1. <span data-ttu-id="7168f-117">Wechseln Sie im linken Navigationsbereich **Org geltende**Einstellungen > **externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="7168f-117">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="7168f-118">Klicken Sie am oberen Rand der Seite **externen Zugriff** auf **externen Zugriff** auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="7168f-118">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="7168f-119">Wenn Sie alle Teams Organisationen die Kommunikation mit Benutzern in Ihrer Organisation zulassen möchten, überspringen Sie Schritt 5.</span><span class="sxs-lookup"><span data-stu-id="7168f-119">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="7168f-120">Wenn Sie möchten um festzulegen, welche Organisationen zu kommunizieren, können mit Benutzern in Ihrer Organisation, Hinzufügen der anderen Organisation Domäne zur Liste zugelassenen durch Klicken auf **Domäne hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7168f-120">If you want to limit which organizations can communicate with users in your organization, add the other organization's domain to the allowed list by clicking **Add domain**.</span></span> <span data-ttu-id="7168f-121">Klicken Sie im Bereich **Hinzufügen einer Domäne** zu platzieren Domain Name klicken Sie auf **zulässige** und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="7168f-121">In the **Add a domain** pane, put in the domain name click **Allowed** and then **Done**.</span></span>

   4. <span data-ttu-id="7168f-122">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7168f-122">Click **Save**.</span></span> 

   5. <span data-ttu-id="7168f-123">Stellen Sie sicher, dass der Administrator in der anderen Teams Organisation dieselben Schritte wird.</span><span class="sxs-lookup"><span data-stu-id="7168f-123">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="7168f-124">Beispielsweise muss in ihrer Liste der **zulässigen Domänen** ihren Administrator um die Domäne für Ihr Unternehmen einzugeben, falls sie einschränken, die Organisationen mit ihren Benutzern kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="7168f-124">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="7168f-125">Schritt 3: Testen sie das Formular</span><span class="sxs-lookup"><span data-stu-id="7168f-125">Step 3 - Test it</span></span>
<span data-ttu-id="7168f-126">Um die Installation zu testen, benötigen Sie ein Teams-Benutzer, die nicht hinter der Firewall befindet.</span><span class="sxs-lookup"><span data-stu-id="7168f-126">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="7168f-127">Nachdem Sie und der Administrator aus der Organisation die **Zugriff durch externe** Einstellungen geändert haben, sollten Sie gut zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="7168f-127">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="7168f-128">In der app Teams nach e-Mail-Adresse der Person suchen Sie, und senden Sie eine Anforderung zum chat.</span><span class="sxs-lookup"><span data-stu-id="7168f-128">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="7168f-129">Bitten Sie Ihren Teams Kontakt senden eine Anforderung an chat.</span><span class="sxs-lookup"><span data-stu-id="7168f-129">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="7168f-130">Wenn Sie die Anfrage nicht erhalten, stellen die Firewalleinstellungen das Problem dar (dabei wird angenommen, dass der Kontakt bereits die Richtigkeit seiner Firewalleinstellungen überprüft hat).</span><span class="sxs-lookup"><span data-stu-id="7168f-130">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="7168f-131">Eine andere Möglichkeit zu prüfen, ob das Problem der Firewall ist ist, gehen Sie an einem Speicherort Wifi nicht hinter der Firewall wie einem Café und Teams das Senden einer Anforderung an den Kontakt zu chat verwenden.</span><span class="sxs-lookup"><span data-stu-id="7168f-131">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="7168f-132">Wenn die Nachricht dort gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.</span><span class="sxs-lookup"><span data-stu-id="7168f-132">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="7168f-133">Kommunizieren Sie mit Benutzern in einer Skype für Business Online-Organisation</span><span class="sxs-lookup"><span data-stu-id="7168f-133">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="7168f-134">Wenn Sie es einrichten können Ihre Teams Benutzer suchen und Kontakt Benutzer, die in einer Skype für Business-Organisation beschränkt sind, die die Benutzer eine Verbindung herstellen kann, fragt den Administrator in der Organisation an die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="7168f-134">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="7168f-135">![SFB-Logo-30x30.png](media/sfb-logo-30x30.png) **Mithilfe von Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="7168f-135">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="7168f-136">Haben Sie die Admin, Organisation führen Sie diese Schritte:</span><span class="sxs-lookup"><span data-stu-id="7168f-136">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="7168f-137">Wechseln Sie in das Office 365 Administrationscenter zu **Admin Center** > **Teams & Skype** > **Legacy-Portal**.</span><span class="sxs-lookup"><span data-stu-id="7168f-137">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="7168f-138">Wählen Sie unter **Skype for Business Admin Center**die Option **Organisation** > **Externe Kommunikation**.</span><span class="sxs-lookup"><span data-stu-id="7168f-138">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="7168f-139">Zum Einrichten der Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne, in der Dropdown-Feld auswählen **auf nur für zulässige Domänen**.</span><span class="sxs-lookup"><span data-stu-id="7168f-139">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="7168f-140">ODER, falls sie Kommunikation mit allen anderen Benutzern in der ganzen Welt aktivieren, hat öffnen, möchten Skype für Geschäftsrichtlinien, wählen **auf mit Ausnahme der blockierten Domänen**.</span><span class="sxs-lookup"><span data-stu-id="7168f-140">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="7168f-141">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="7168f-141">This is the default setting.</span></span>
    
4. <span data-ttu-id="7168f-142">Wählen Sie unter **blockiert oder zugelassenen Domänen**, **+** , und fügen Sie den Namen der Domäne, die Sie zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="7168f-142">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="7168f-143">Stellen Sie sicher, dass der Administrator in der anderen Organisation dieselben Schritte wird.</span><span class="sxs-lookup"><span data-stu-id="7168f-143">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="7168f-144">Beispiel: In der Liste der **zugelassenen Domänen** muss der Administrator der anderen Organisation die Domäne für Ihr Unternehmen eingeben.</span><span class="sxs-lookup"><span data-stu-id="7168f-144">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="7168f-145">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7168f-145">Related topics</span></span>

<span data-ttu-id="7168f-146">[Melden Sie sich bei Microsoft-Teams,](sign-in-teams.md)
[Endbenutzer Schulungen für Teams](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="7168f-146">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>


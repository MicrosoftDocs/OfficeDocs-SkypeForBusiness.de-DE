---
title: Kommunizieren mit Microsoft Teams-Benutzern in einer anderen Organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: Hier erfahren Sie, wie Sie Teams so konfigurieren, dass Benutzer mit Benutzern in einer anderen Organisation kommunizieren können.
ms.openlocfilehash: 5da04eec6b8ce643f32639a014237ffe118aeabe
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2019
ms.locfileid: "34343938"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="64b36-103">Zulassen, dass Ihre Teams-Benutzer in einer anderen Teams-Organisation chatten und mit Benutzern kommunizieren</span><span class="sxs-lookup"><span data-stu-id="64b36-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="64b36-104">Führen Sie die Schritte in diesem Artikel in folgenden Fällen aus:</span><span class="sxs-lookup"><span data-stu-id="64b36-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="64b36-105">Sie verfügen über Benutzer in verschiedenen Domänen in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="64b36-105">You have users in different domains in your business.</span></span> <span data-ttu-id="64b36-106">Beispiel: Rob@ContosoEast.com und Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="64b36-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="64b36-107">Sie möchten, dass die Personen in Ihrer Organisation Teams verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="64b36-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="64b36-108">Sie möchten, dass andere Personen in der Welt, die Teams verwenden, Ihre e-Mail-Adresse finden und mit Ihnen Kontakt aufnehmen können.</span><span class="sxs-lookup"><span data-stu-id="64b36-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="64b36-109">Wenn Sie und ein anderer Benutzer den externen Zugriff aktivieren und die Domänen der anderen Personen zulassen, kann dies funktionieren.</span><span class="sxs-lookup"><span data-stu-id="64b36-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="64b36-110">Wenn dies nicht funktioniert, sollte der andere Benutzer sicherstellen, dass seine Konfiguration Ihre Domäne nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="64b36-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="64b36-111">Auf diese Weise können Benutzer Sofortnachrichten finden, anrufen und Ihnen senden sowie Besprechungen mit Ihnen einrichten.</span><span class="sxs-lookup"><span data-stu-id="64b36-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="64b36-112">Wenn Sie möchten, dass externe Benutzer auf Teams und Kanäle zugreifen können, ist der Gastzugriff möglicherweise eine bessere Möglichkeit, um zu gehen.</span><span class="sxs-lookup"><span data-stu-id="64b36-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="64b36-113">Führen Sie die Schritte in diesem Artikel aus, und stellen Sie sicher, dass Sie den [Gastzugriff aktivieren](set-up-guests.md) , damit die Benutzer kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="64b36-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64b36-114">Damit Sie zurzeit innerhalb des Microsoft Teams-Clients an einen externen Benutzer außerhalb Ihrer Organisation, der derzeit kein Gast ihres Aad/Mandanten ist, teilnehmen können, müssen Sie für Hybrid ordnungsgemäß eingerichtet sein und zu Skype for Business Online verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="64b36-114">In order to currently federate within the Microsoft Teams client to an external user outside of your organization who's not currently a Guest of your AAD/Tenant, you must be correctly setup for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="64b36-115">Ab 2/25/2019 unterstützt Teams noch keine native Federation, ohne dass der Benutzer das SIP-Profil in Skype for Business Online verwaltet.</span><span class="sxs-lookup"><span data-stu-id="64b36-115">As of 2/25/2019, Teams doesn't yet support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="64b36-116">Weitere Informationen zum Einrichten Ihres Kontos für Hybrid und anschließendes Verschieben in Teams finden Sie unter [Upgrade von Skype for Business-hybridbereitstellung in Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span><span class="sxs-lookup"><span data-stu-id="64b36-116">For more on setting up your account for Hybrid and then moved to Teams, please see [Upgrade Skype for Business Hybrid Deployment to Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="64b36-117">Zulassen, dass Ihre Teams-Benutzer in einer anderen Teams-Organisation chatten und mit Benutzern kommunizieren</span><span class="sxs-lookup"><span data-stu-id="64b36-117">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="64b36-118">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="64b36-118">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="64b36-119">Schritt 1 – Stellen Sie sicher, dass die erforderlichen Ports und URLs eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="64b36-119">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="64b36-120">**Am häufigsten haben Benutzer beim Einrichten der Kommunikation zwischen Unternehmen Probleme damit, die [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) richtig festzulegen.**</span><span class="sxs-lookup"><span data-stu-id="64b36-120">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="64b36-121">Schritt 2 – Aktivieren Ihrer Organisation für die Kommunikation mit einer anderen Teams-Organisation</span><span class="sxs-lookup"><span data-stu-id="64b36-121">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="64b36-122">![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt</span><span class="sxs-lookup"><span data-stu-id="64b36-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

   1. <span data-ttu-id="64b36-123">Navigieren Sie in der linken Navigationsleiste zu **organisationsweiten Einstellungen** > **externer Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="64b36-123">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="64b36-124">Klicken Sie oben auf der Seite **externer Zugriff** auf **externer** Zugriff auf **ein**.</span><span class="sxs-lookup"><span data-stu-id="64b36-124">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="64b36-125">Wenn Sie zulassen möchten, dass alle Teams-Organisationen mit Benutzern in Ihrer Organisation kommunizieren, fahren Sie mit Schritt 5 fort.</span><span class="sxs-lookup"><span data-stu-id="64b36-125">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="64b36-126">Wenn Sie einschränken möchten, welche Organisationen mit Benutzern in Ihrer Organisation kommunizieren können, können Sie entweder alle außer einigen Domänen zulassen oder nur bestimmte Organisationen zulassen.</span><span class="sxs-lookup"><span data-stu-id="64b36-126">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="64b36-127">Wenn Sie nur einige Domänen zulassen möchten, fügen Sie die zu blockierenden Domänen hinzu, indem Sie auf **Domäne hinzufügen**klicken.</span><span class="sxs-lookup"><span data-stu-id="64b36-127">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="64b36-128">Klicken Sie im Bereich **Domäne hinzufügen** im Domänennamen auf **blockiert** und dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="64b36-128">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="64b36-129">Um die Kommunikation auf bestimmte organizatioins zu begrenzen, fügen Sie diese Domänen der Liste mit dem \*\*\*\* Status "verschuldete" hinzu.</span><span class="sxs-lookup"><span data-stu-id="64b36-129">To limit communications to specific organizatioins, add those domains to the list with a status of **Alowed**.</span></span> <span data-ttu-id="64b36-130">Nachdem Sie der Zulassungsliste eine beliebige Domäne hinzugefügt haben, sind die Kommunikationen mit anderen Organisationen nur auf die Organisationen limitiert, deren Domänen sich in der Zulassungsliste befinden.</span><span class="sxs-lookup"><span data-stu-id="64b36-130">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="64b36-131">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="64b36-131">Click **Save**.</span></span> 

   6. <span data-ttu-id="64b36-132">Stellen Sie dann sicher, dass der Administrator in der anderen Teams-Organisation die gleichen Schritte durchführt.</span><span class="sxs-lookup"><span data-stu-id="64b36-132">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="64b36-133">In der Liste der **zulässigen Domänen** muss der Administrator beispielsweise die Domäne für Ihr Unternehmen eingeben, wenn er die Unternehmen, die mit seinen Benutzern kommunizieren können, einschränken.</span><span class="sxs-lookup"><span data-stu-id="64b36-133">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="64b36-134">Schritt 3 – testen</span><span class="sxs-lookup"><span data-stu-id="64b36-134">Step 3 - Test it</span></span>
<span data-ttu-id="64b36-135">Um Ihr Setup zu testen, benötigen Sie einen Teams-Benutzer, der sich nicht hinter Ihrer Firewall befindet.</span><span class="sxs-lookup"><span data-stu-id="64b36-135">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="64b36-136">Nachdem Sie und der Administrator des Unternehmens die Einstellungen für den **externen Zugriff** geändert haben, sollten Sie gut gehen.</span><span class="sxs-lookup"><span data-stu-id="64b36-136">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="64b36-137">Suchen Sie in der Teams-App nach der e-Mail-Adresse der Person, und senden Sie eine Anfrage an den Chat.</span><span class="sxs-lookup"><span data-stu-id="64b36-137">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="64b36-138">Bitten Sie Ihren Team-Kontakt, Ihnen eine Anfrage zum Chat zu senden.</span><span class="sxs-lookup"><span data-stu-id="64b36-138">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="64b36-139">Wenn Sie die Anfrage nicht erhalten, stellen die Firewalleinstellungen das Problem dar (dabei wird angenommen, dass der Kontakt bereits die Richtigkeit seiner Firewalleinstellungen überprüft hat).</span><span class="sxs-lookup"><span data-stu-id="64b36-139">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="64b36-140">Eine weitere Möglichkeit, zu testen, ob es sich um eine Firewall handelt, besteht darin, zu einem WLAN-Standort zu wechseln, der sich nicht hinter Ihrer Firewall wie einem Café befindet, und Teams zu verwenden, um eine Anfrage an Ihren Kontakt zu senden, um zu chatten.</span><span class="sxs-lookup"><span data-stu-id="64b36-140">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="64b36-141">Wenn die Nachricht dort gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.</span><span class="sxs-lookup"><span data-stu-id="64b36-141">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="64b36-142">Kommunizieren mit Benutzern in einer Skype for Business Online-Organisation</span><span class="sxs-lookup"><span data-stu-id="64b36-142">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="64b36-143">Wenn Sie Ihre Teams so einrichten, dass Benutzer in einer Skype for Business-Organisation Personen finden und kontaktieren können, die die Kontaktaufnahme mit ihren Benutzern einschränken, bitten Sie den Administrator in dieser Organisation, die folgenden Schritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="64b36-143">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="64b36-144">![SFB-Logo-30x30. png](media/sfb-logo-30x30.png) **mit Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="64b36-144">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="64b36-145">Führen Sie den Administrator in dieser Organisation aus, um die folgenden Schritte auszuführen:</span><span class="sxs-lookup"><span data-stu-id="64b36-145">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="64b36-146">Wechseln Sie im Office 365 Admin Center zu **Admin Center** > **Teams & Skype** > **Legacy-Portal**.</span><span class="sxs-lookup"><span data-stu-id="64b36-146">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="64b36-147">Wählen Sie im **Skype for Business Admin Center**die Option **Organisation** > **External Communications**aus.</span><span class="sxs-lookup"><span data-stu-id="64b36-147">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="64b36-148">Um die Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne einzurichten, wählen Sie im Dropdownfeld **nur für zulässige Domänen**aktivieren aus.</span><span class="sxs-lookup"><span data-stu-id="64b36-148">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="64b36-149">Wenn Sie die Kommunikation mit allen anderen Personen in der Welt ermöglichen möchten, die Skype for Business-Richtlinien geöffnet haben, wählen Sie **ein, außer für blockierte Domänen**.</span><span class="sxs-lookup"><span data-stu-id="64b36-149">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="64b36-150">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="64b36-150">This is the default setting.</span></span>
    
4. <span data-ttu-id="64b36-151">Wählen **+** Sie unter **blockierte oder zulässige Domänen**den Namen der Domäne aus, die Sie zulassen möchten, und fügen Sie ihn hinzu.</span><span class="sxs-lookup"><span data-stu-id="64b36-151">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="64b36-152">Stellen Sie sicher, dass der Administrator in der anderen Organisation dieselben Schritte durchführt.</span><span class="sxs-lookup"><span data-stu-id="64b36-152">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="64b36-153">Beispiel: In der Liste der **zugelassenen Domänen** muss der Administrator der anderen Organisation die Domäne für Ihr Unternehmen eingeben.</span><span class="sxs-lookup"><span data-stu-id="64b36-153">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="64b36-154">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="64b36-154">Related topics</span></span>

<span data-ttu-id="64b36-155">[Anmelden bei Microsoft Teams](sign-in-teams.md)
-[Endbenutzerschulungen für Teams](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="64b36-155">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>


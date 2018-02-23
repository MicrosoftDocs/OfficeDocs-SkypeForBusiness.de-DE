---
title: "Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/23/2018
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: "Lesen Sie, wie Sie es Benutzern von Skype for Business ermöglichen, externe Skype for Business-Benutzer zu kontaktieren und sie zu ihren Kontaktlisten hinzuzufügen. "
ms.openlocfilehash: 8f6ca948434d9b5a63788cbb5bc54ad6297843e2
ms.sourcegitcommit: 46ca433590a4c3aefbe2fb777542bb0b332563bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="e44b2-103">Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="e44b2-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="e44b2-104">Mit Skype for Business können Ihre Benutzer nach beliebigen Nutzern von Skype – der kostenlosen App – suchen und mit ihnen chatten.</span><span class="sxs-lookup"><span data-stu-id="e44b2-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="e44b2-105">In diesem Artikel wird erläutert, was Sie tun müssen, damit die Benutzer Skype-Kontakte hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="e44b2-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="e44b2-106">Dafür benötigen Sie [Administratorberechtigungen](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e44b2-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="e44b2-107">Melden Sie sich mit Ihrem Office 365-Administratorkonto bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) an.</span><span class="sxs-lookup"><span data-stu-id="e44b2-107">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="e44b2-108">Navigieren Sie im Office 365 Admin Center zu **Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="e44b2-108">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Wählen Sie das Skype for Business Admin Center aus.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="e44b2-110">Wählen Sie im **Skype for Business Admin Center** die Option **Organisation** > **Externe Kommunikation** aus.</span><span class="sxs-lookup"><span data-stu-id="e44b2-110">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="e44b2-111">Standardmäßig können Ihre Benutzer mit allen anderen Personen weltweit kommunizieren, die Skype for Business verwenden (vorausgesetzt, Ihre Firewall ist so konfiguriert, dass sie dies zulässt).</span><span class="sxs-lookup"><span data-stu-id="e44b2-111">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Wählen Sie „Zulassen, dass Skype for Business zur Kommunikation mit Skype-Benutzern außerhalb Ihres Unternehmens verwendet wird“ aus.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="e44b2-113">Wenn Sie möchten, dass Ihre Benutzer mit Skype-Benutzern chatten, ABER nicht mit anderen Skype for Business-Benutzern, wählen Sie **Nur für zulässige Domänen aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="e44b2-113">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="e44b2-114">Wenn Sie den Kontakt mit Skype-Benutzern ermöglichen, wird „skype.com“ automatisch im Hintergrund als zulässige Domäne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e44b2-114">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="e44b2-115">Wenn Sie den Kontakt über Skype for Business von allen anderen Unternehmen weltweit mit Ausnahme bestimmter Unternehmen zulassen möchten, wählen Sie **Aktivieren mit Ausnahme der blockierten Domänen** aus. Wählen Sie dann **+** aus, um die entsprechenden Domänen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e44b2-115">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="e44b2-116">Alle Personen mit Ausnahme derer in diesen Domänen können Kontakt zu Ihnen aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="e44b2-116">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="e44b2-117">(Ein Unternehmen kann diese Option zum Beispiel wählen, wenn ein Rechtsstreit vorliegt und sichergestellt werden muss, dass kein Kontakt zu dem anderen Unternehmen unterhalten wird.)</span><span class="sxs-lookup"><span data-stu-id="e44b2-117">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="e44b2-118">Wählen Sie **Zulassen, dass Skype for Business zur Kommunikation mit Skype-Benutzern außerhalb Ihres Unternehmens verwendet wird** aus.</span><span class="sxs-lookup"><span data-stu-id="e44b2-118">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="e44b2-119">Wenn Sie die Windows-Firewall verwenden, öffnet Skype for Business die erforderlichen Ports automatisch.</span><span class="sxs-lookup"><span data-stu-id="e44b2-119">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="e44b2-120">Wenn Ihre Organisation eine andere Lösung zum Einschränken von Internetverbindungen durch Computer in Ihrem Netzwerk verwendet, stellen Sie sicher, dass die Clientcomputer auf alle [IP-Adressen und URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) für die Skype-Konnektivität und die Suche im Skype-Verzeichnis zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e44b2-120">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="e44b2-121">Dafür kann es erforderlich sein, sie zur Liste für zugelassene ausgehende Verbindungen in Ihrer Firewall oder Proxy-Infrastrukturkonfiguration hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e44b2-121">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="e44b2-122">**WARTEN SIE MIT DEM TEST BIS ZU 24 STUNDEN**.</span><span class="sxs-lookup"><span data-stu-id="e44b2-122">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="e44b2-123">Bei jeder Änderung der Einstellungen für externe Kommunikation kann es bis zu 24 Stunden dauern, bis die Änderungen in allen Rechenzentren übernommen wurden.</span><span class="sxs-lookup"><span data-stu-id="e44b2-123">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="e44b2-124">Zeigen Sie Ihren Benutzern, wie sie Skype-Kontakte finden und zu ihrer Kontaktliste in Skype for Business hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="e44b2-124">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="e44b2-125">Weisen Sie sie auf den Artikel [Suchen nach Personen in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19) hin.</span><span class="sxs-lookup"><span data-stu-id="e44b2-125">Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="e44b2-126">Tests und Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="e44b2-126">Test and troubleshoot</span></span>

<span data-ttu-id="e44b2-127">Um Ihr Setup zu testen, benötigen Sie einen Kontakt in Skype, der sich nicht hinter der Firewall Ihrer Firma befindet.</span><span class="sxs-lookup"><span data-stu-id="e44b2-127">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="e44b2-128">Der Kontakt kann mit einem Gmail-Konto, Outlook.com-Konto oder einem anderen E-Mail-Kontotyp angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="e44b2-128">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="e44b2-129">Warten Sie nach einer Änderung der Einstellungen für externe Kommunikation **BIS ZU 24 STUNDEN, BEVOR SIE TESTS DURCHFÜHREN**.</span><span class="sxs-lookup"><span data-stu-id="e44b2-129">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="e44b2-130">Melden Sie sich bei Skype for Business ab und dann wieder an, damit Sie die Option zum Durchsuchen des Skype-Verzeichnisses sehen.</span><span class="sxs-lookup"><span data-stu-id="e44b2-130">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Wenn das Skype-Verzeichnis markiert ist, können Sie nach Personen mit Skype-Konten suchen.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="e44b2-132">Suchen Sie in Skype for Business nach Ihrem Kontakt in Skype, und senden Sie eine Chatanfrage.</span><span class="sxs-lookup"><span data-stu-id="e44b2-132">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="e44b2-133">Wenn Sie durch eine Meldung informiert werden, dass die Anfrage aufgrund einer Unternehmensrichtlinie nicht gesendet werden konnte, müssen Sie Ihre [Firewalleinstellungen](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) nochmals überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e44b2-133">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="e44b2-134">Eine weitere Möglichkeit zu testen, ob die Firewall das Problem darstellt: Gehen Sie zu einem Ort mit WLAN, der sich nicht hinter Ihrer Firewall befindet (zum Beispiel in ein Café), und senden Sie mit Skype for Business eine Chatanfrage an Ihren Skype-Kontakt.</span><span class="sxs-lookup"><span data-stu-id="e44b2-134">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
  - <span data-ttu-id="e44b2-135">**Wenn Sie Ihrem Skype-Kontakt eine Anfrage gesendet haben, die dieser nicht erhalten hat**, bitten Sie ihn, Ihnen eine Chatanfrage zu senden.</span><span class="sxs-lookup"><span data-stu-id="e44b2-135">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="e44b2-136">Wenn das Problem darin bestand, eine Verbindung zwischen Skype und Skype for Business herzustellen, ist das Problem damit oft gelöst.</span><span class="sxs-lookup"><span data-stu-id="e44b2-136">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
  - <span data-ttu-id="e44b2-137">Wenn die Nachricht im Café gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.</span><span class="sxs-lookup"><span data-stu-id="e44b2-137">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="e44b2-138">Mögliche und nicht mögliche Aktionen</span><span class="sxs-lookup"><span data-stu-id="e44b2-138">What you can and can't do</span></span>

- <span data-ttu-id="e44b2-139">Es gibt in **Skype for Business auf dem Mac** keine Möglichkeit, nach Skype-Kontakten zu suchen und mit ihnen zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e44b2-139">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="e44b2-140">Wenn die Verzeichnissuche aktiviert ist, können Sie nach Benutzern von Skype und Skype for Business suchen.</span><span class="sxs-lookup"><span data-stu-id="e44b2-140">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="e44b2-141">Wenn Sie die Benutzer aus irgendeinem Grund im Verzeichnis nicht finden, können Sie ihnen eine Kontaktanfrage senden. Die Benutzer müssen sich dann bei Skype anmelden und die Anfrage akzeptieren. Anschließend können Sie mit ihnen chatten.</span><span class="sxs-lookup"><span data-stu-id="e44b2-141">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="e44b2-142">Es ist nicht möglich, Verbindungen mit anderen Chatanbietern wie Google oder Facebook zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="e44b2-142">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="e44b2-143">Sie können Skype for Business nicht verwenden, um SMS an Mobiltelefone zu senden.</span><span class="sxs-lookup"><span data-stu-id="e44b2-143">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="e44b2-144">Es ist nicht möglich, Audio- oder Videoanrufe zwischen Skype-Kontakten und Skype for Business-Kontakten aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="e44b2-144">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="e44b2-145">Welche Funktionen sind beim Hinzufügen von Skype-Kontakten verfügbar?</span><span class="sxs-lookup"><span data-stu-id="e44b2-145">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="e44b2-146">Skype-Kontakten, die sich mit ihrem Microsoft-Konto (ehemals Windows Live ID) angemeldet haben, stehen bei Unterhaltungen mit Skype for Business-Benutzern einige, aber nicht alle Funktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e44b2-146">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="e44b2-147">**In Unterhaltungen mit Skype-Kontakten verfügbar**</span><span class="sxs-lookup"><span data-stu-id="e44b2-147">**Available with Skype contacts**</span></span>|<span data-ttu-id="e44b2-148">**In Unterhaltungen mit Skype-Kontakten nicht verfügbar**</span><span class="sxs-lookup"><span data-stu-id="e44b2-148">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e44b2-149">Videounterhaltungen</span><span class="sxs-lookup"><span data-stu-id="e44b2-149">Video conversations</span></span> <br/>  <span data-ttu-id="e44b2-150">Chats zwischen zwei Personen</span><span class="sxs-lookup"><span data-stu-id="e44b2-150">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="e44b2-151">Anwesenheitsfunktionen</span><span class="sxs-lookup"><span data-stu-id="e44b2-151">Presence</span></span> <br/> | <span data-ttu-id="e44b2-152">Chatunterhaltungen mit mehreren Teilnehmern</span><span class="sxs-lookup"><span data-stu-id="e44b2-152">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="e44b2-153">Audio- und Videounterhaltungen mit drei oder mehr Personen</span><span class="sxs-lookup"><span data-stu-id="e44b2-153">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="e44b2-154">Desktop- und Programmfreigabe</span><span class="sxs-lookup"><span data-stu-id="e44b2-154">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="e44b2-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e44b2-155">Related topics</span></span>

[<span data-ttu-id="e44b2-156">Benutzern gestatten, externe Skype for Business-Benutzer zu kontaktieren</span><span class="sxs-lookup"><span data-stu-id="e44b2-156">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="e44b2-157">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e44b2-157">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

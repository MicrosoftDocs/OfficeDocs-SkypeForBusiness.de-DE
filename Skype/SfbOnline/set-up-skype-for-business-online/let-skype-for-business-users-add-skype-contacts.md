---
title: Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. '
ms.openlocfilehash: afe1cb7f465a2a2e43056d01e7512f6f46c0f587
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494159"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="d5fd9-103">Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="d5fd9-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="d5fd9-p101">Mit Skype for Business können Ihre Benutzer nach beliebigen Benutzern von Skype - der kostenlosen App - suchen und Chatnachrichten mit ihnen austauschen. In diesem Artikel wird erläutert, was Sie tun müssen, damit die Benutzer Skype-Kontakte hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-p101">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app! This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="d5fd9-106">Sie benötigen [Administratorberechtigungen](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365, um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>

<span data-ttu-id="d5fd9-107">![Ein Symbol mit dem Skype for Business-](../images/sfb-logo-30x30.png) Logo **im Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="d5fd9-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="d5fd9-108">Melden Sie sich mit Ihrem Office 365-Administratorkonto bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) an.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-108">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="d5fd9-109">Gehen Sie in Office 365 Admin Center zu **Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-109">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="d5fd9-111">Wählen Sie im **Skype for Business Admin Center**die Option **Organisation** > **External Communications**aus.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="d5fd9-112">Standardmäßig können Ihre Benutzer mit allen anderen Personen weltweit kommunizieren, die Skype for Business verwenden (vorausgesetzt, Ihre Firewall ist so konfiguriert, dass sie dies zulässt).</span><span class="sxs-lookup"><span data-stu-id="d5fd9-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="d5fd9-p102">Wenn Sie möchten, dass Ihre Benutzer mit Skype-Benutzern chatten, ABER nicht mit anderen, die Skype for Business verwenden, wählen Sie **Nur für zulässige Domänen aktivieren** aus. Wenn Sie den Kontakt mit Skype-Benutzern ermöglichen, wird „skype.com" automatisch im Hintergrund als zulässige Domäne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-p102">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**. When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="d5fd9-p103">Wenn Sie den Kontakt über Skype for Business von allen anderen Unternehmen weltweit mit Ausnahme bestimmter Unternehmen zulassen möchten, wählen Sie **Aktivieren mit Ausnahme der blockierten Domänen** aus. Wählen Sie dann **+** aus, um die entsprechenden Domänen hinzuzufügen. Alle Personen mit Ausnahme derer in diesen Domänen können Kontakt zu Ihnen aufnehmen. (Ein Unternehmen kann diese Option z. B. wählen, wenn ein Rechtsstreit vorliegt und sichergestellt werden muss, dass kein Kontakt zu dem anderen Unternehmen unterhalten wird.)</span><span class="sxs-lookup"><span data-stu-id="d5fd9-p103">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains. Everyone will be able to contact you except people on those specific domains. (Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="d5fd9-119">Wählen Sie **Zulassen, dass Skype for Business zur Kommunikation mit Skype-Benutzern außerhalb Ihres Unternehmens verwendet wird**.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="d5fd9-120">Wenn Sie die Windows-Firewall verwenden, öffnet Skype for Business die erforderlichen Ports automatisch.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="d5fd9-121">Wenn Ihre Organisation eine andere Lösung verwendet, um die Internet Verbindung von Computern in Ihrem Netzwerk zu beschränken, stellen Sie sicher, dass Clientcomputer auf alle [IP-Adressen und URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) für Skype-Konnektivität und die Skype-Verzeichnissuche zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="d5fd9-122">Dafür kann es erforderlich sein, sie der Liste für zugelassene ausgehende Verbindungen in Ihrer Firewall oder Proxy-Infrastrukturkonfiguration hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="d5fd9-p105">**WARTEN SIE MIT DEM TEST BIS ZU 24 STUNDEN**. Bei jeder Änderung der Einstellungen für externe Kommunikation kann es bis zu 24 Stunden dauern, bis die Änderungen in allen Rechenzentren übernommen wurden.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-p105">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="d5fd9-p106">Zeigen Sie Ihren Benutzern, wie sie Skype-Kontakte finden und zu ihrer Liste mit Skype for Business-Kontakten hinzufügen können. Verweisen Sie die Benutzer auf [Suchen nach Personen in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="d5fd9-p106">Show your users how to find and add Skype contacts to their list of Skype for Business contacts. Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="d5fd9-127">Tests und Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="d5fd9-127">Test and troubleshoot</span></span>

<span data-ttu-id="d5fd9-p107">Um Ihr Setup zu testen, benötigen Sie einen Kontakt in Skype, der sich nicht hinter der Firewall Ihrer Firma befindet. Der Kontakt kann mit einem Gmail-Konto, Outlook.com-Konto oder einem anderen E-Mail-Kontotyp angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-p107">To test your setup, you need a contact on Skype who's not behind your company firewall. They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="d5fd9-130">Warten Sie nach einer Änderung der Einstellungen für externe Kommunikation **BIS ZU 24 STUNDEN, BEVOR SIE TESTS DURCHFÜHREN**.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="d5fd9-131">Melden Sie sich bei Skype for Business ab und dann wieder an, damit Sie die Option zum Durchsuchen des Skype-Verzeichnisses sehen.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="d5fd9-133">Suchen Sie in Skype for Business nach Ihrem Kontakt in Skype, und senden Sie eine Chatanfrage.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="d5fd9-134">Wenn Sie die Meldung erhalten, dass Sie aufgrund einer Unternehmensrichtlinie nicht gesendet werden konnte, müssen Sie Ihre [Firewalleinstellungen](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="d5fd9-135">Eine weitere Möglichkeit, zu testen, ob die Firewall das Problem darstellt: Gehen Sie zu einem Ort mit WLAN, der sich nicht hinter Ihrer Firewall befindet (zum Beispiel in ein Café), und senden Sie mit Skype for Business eine Chatanfrage an Ihren Skype-Kontakt.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="d5fd9-p108">**Wenn Sie Ihrem Skype-Kontakt eine Anfrage gesendet haben, die dieser nicht erhalten hat**, bitten Sie ihn, Ihnen eine Chatanfrage zu senden. Wenn das Problem darin bestand, eine Verbindung zwischen Skype und Skype for Business herzustellen, ist das Problem damit oft gelöst.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-p108">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat. If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="d5fd9-138">Wenn die Nachricht im Café gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="d5fd9-139">Was möglich und was nicht möglich ist</span><span class="sxs-lookup"><span data-stu-id="d5fd9-139">What you can and can't do</span></span>

- <span data-ttu-id="d5fd9-140">**Skype for Businessfür Mac** ist es nicht möglich, nach Skype-Kontakten zu suchen und mit ihnen zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="d5fd9-141">Wenn die Verzeichnissuche aktiviert ist, können Sie nach Skype-und Skype for Business-Benutzern suchen und diese finden.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="d5fd9-142">Wenn Sie Sie aus irgendeinem Grund nicht finden können, indem Sie das Verzeichnis durchsuchen, können Sie Ihnen eine Kontakt Anfrage senden und diese dann bei Skype anmelden und akzeptieren, damit Sie mit Ihnen chatten können.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="d5fd9-p110">Chat-Nachrichtenverbindungen mit anderen Chat-Dienstanbietern wie Google oder Facebook sind nicht möglich. Sie können Skype for Business nicht zum Senden von Mobiltelefon-Textnachrichten verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-p110">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook. You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="d5fd9-145">Es ist nicht möglich, Audio-oder Videoanrufe zwischen einem Skype-Kontakt und einem Skype for Business-Kontakt aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="d5fd9-146">Welche Funktionen sind beim Hinzufügen von Skype-Kontakten verfügbar?</span><span class="sxs-lookup"><span data-stu-id="d5fd9-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="d5fd9-147">Skype-Kontakte, die sich mit Ihrem Microsoft-Konto (vormals Windows Live ID) angemeldet haben, können einige, aber nicht alle Funktionen erhalten, wenn Sie mit Ihren Skype for Business-Benutzern sprechen.</span><span class="sxs-lookup"><span data-stu-id="d5fd9-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="d5fd9-148">**Für Skype-Kontakte verfügbar**</span><span class="sxs-lookup"><span data-stu-id="d5fd9-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="d5fd9-149">**Für Skype-Kontakte nicht verfügbar**</span><span class="sxs-lookup"><span data-stu-id="d5fd9-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="d5fd9-150">Videounterhaltungen</span><span class="sxs-lookup"><span data-stu-id="d5fd9-150">Video conversations</span></span> <br/>  <span data-ttu-id="d5fd9-151">Chatnachrichten zwischen zwei Personen</span><span class="sxs-lookup"><span data-stu-id="d5fd9-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="d5fd9-152">Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="d5fd9-152">Presence</span></span> <br/> | <span data-ttu-id="d5fd9-153">Chatunterhaltungen mit mehreren Personen</span><span class="sxs-lookup"><span data-stu-id="d5fd9-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="d5fd9-154">Audio- und Videounterhaltungen mit drei oder mehr Personen</span><span class="sxs-lookup"><span data-stu-id="d5fd9-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="d5fd9-155">Desktop- und Programmfreigabe</span><span class="sxs-lookup"><span data-stu-id="d5fd9-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="d5fd9-156">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d5fd9-156">Related topics</span></span>

[<span data-ttu-id="d5fd9-157">Benutzern gestatten, externe Skype for Business-Benutzer zu kontaktieren</span><span class="sxs-lookup"><span data-stu-id="d5fd9-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="d5fd9-158">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d5fd9-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 

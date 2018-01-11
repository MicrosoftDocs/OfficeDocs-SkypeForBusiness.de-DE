---
title: "Zulassen, dass Benutzer wenden Sie sich an externe Skype für Unternehmensbenutzer"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: "Finden Sie unter Konfigurieren von Skype für Unternehmen, damit Benutzer mit Benutzern in anderen Organisationen kommunizieren oder außerhalb der für diese Kontakte können. "
ms.openlocfilehash: e21b89c24618d2296dc44766b8d6ddbd3d527ef7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="a1bfb-103">Zulassen, dass Benutzer wenden Sie sich an externe Skype für Unternehmensbenutzer</span><span class="sxs-lookup"><span data-stu-id="a1bfb-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="a1bfb-104">Skype für den Verbund Business nicht zu Office 365 handelt, das von 21Vianet und Office 365 Deutschland Organisationen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="a1bfb-105">Verwenden Sie die Schritte in diesem, wenn Artikel:</span><span class="sxs-lookup"><span data-stu-id="a1bfb-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="a1bfb-106">Sie müssen die Benutzer in verschiedenen Domänen in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-106">You have users on different domains in your business.</span></span> <span data-ttu-id="a1bfb-107">Rob@ContosoEast.com und Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-107">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="a1bfb-108">Sie möchten die Personen in Ihrer Organisation mit Skype für Unternehmen wenden Sie sich an Personen in bestimmten Unternehmen außerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
<span data-ttu-id="a1bfb-109">-Sie möchten andere Person in der ganzen Welt, die Skype für Unternehmen verwendet, in der Lage, zu finden, und wenden Sie sich mithilfe Ihrer e-Mail-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-109">-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="a1bfb-110">Wenn Sie und sie die Standardeinstellung Skype für Business Einstellungen verwenden, funktioniert dies automatisch.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="a1bfb-111">Wenn dies nicht der Fall, müssen sie sicherstellen, dass die Konfiguration Ihrer Domäne blockieren nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="a1bfb-112">Aktivieren Sie Business-Geschäftskommunikation für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="a1bfb-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="a1bfb-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a1bfb-113"></span></span>

<span data-ttu-id="a1bfb-114">Sie benötigen [Administratorberechtigungen](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 dazu.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="a1bfb-115">Melden Sie sich mit Ihrem Office 365-Admin-Konto.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-115">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="a1bfb-116">Wechseln Sie in das Office 365 Administrationscenter zu **Admin Center** > **Skype für Unternehmen**.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-116">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
    
    ![Wählen Sie die Skype für Business Administrationscenter.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="a1bfb-118">Wählen Sie in der **Skype für Business Administrationscenter**, **Organisation** > **externe Kommunikation**.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-118">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
4. <span data-ttu-id="a1bfb-119">Zum Einrichten der Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne, in der Dropdown-Feld auswählen **auf nur für zulässige Domänen**.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-119">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="a1bfb-120">ODER, um die Kommunikation mit allen anderen in der ganzen Welt ermöglichen, die geöffnet ist Skype für Geschäftsrichtlinien, wählen Sie **auf mit Ausnahme der blockierten Domänen**.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-120">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="a1bfb-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-121">This is the default setting.</span></span>
    
5. <span data-ttu-id="a1bfb-122">Wählen Sie unter **blockiert oder zugelassenen Domänen**, **+** , und fügen Sie den Namen der Domäne, die Sie zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-122">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
6. <span data-ttu-id="a1bfb-123">Stellen Sie sicher, dass der Administrator in der anderen Organisation dieselben Schritte in ihrer **Skype für Business Administrationscenter**ist.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-123">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="a1bfb-124">Beispielsweise muss in ihrer Liste der **zulässigen Domänen** ihre Admin die Domäne für Ihr Unternehmen eingeben.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-124">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
7. <span data-ttu-id="a1bfb-125">Wenn Sie Windows-Firewall verwenden, werden die erforderlichen Ports in Skype für Unternehmen automatisch geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-125">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="a1bfb-126">Wenn Ihre Organisation eine andere Firewall-Lösung um zu verhindern, dass die Computer in Ihrem Netzwerk verbinden mit dem Internet verwendet wird, stellen Sie sicher, dass die Client-Computer die folgenden [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-126">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="a1bfb-127">Es kann erforderlich sein, die FQDNs, die ausgehende Zulassungsliste in die Firewall oder der Proxy Infrastruktur-Konfiguration hinzufügen: ** \*. api.skype.com**, \* **. users.storage.live.com**, und **graph.skype.com**. Überprüfen Sie für Informationen dazu, wie Sie diese Ports in der Firewall zu öffnen die Begleitdokumentation es.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-127">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**. For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="a1bfb-128">Eine Liste aller Ports, die Sie öffnen möchten, finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="a1bfb-128">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
8. <span data-ttu-id="a1bfb-129">**So testen Sie bis zu 24 Stunden zu warten**.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-129">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="a1bfb-130">Jeder Änderung von den Einstellungen für externe Kommunikation dauert es bis zu 24 Stunden, damit die Änderungen in den Rechenzentren aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-130">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="a1bfb-131">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Sie können die Benutzer zum Suchen und Instant Messaging mit jeder, der Skype, die kostenlose Consumer-app verwendet!</span><span class="sxs-lookup"><span data-stu-id="a1bfb-131">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="a1bfb-132">Finden Sie weitere Informationen finden Sie unter [Let Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="a1bfb-132">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="a1bfb-133">Tests und Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="a1bfb-133">Test and troubleshoot</span></span>
<span data-ttu-id="a1bfb-134"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a1bfb-134"></span></span>

 <span data-ttu-id="a1bfb-135">**Das am häufigsten verwendete Problem, Personen, beim Einrichten von Business Geschäftskommunikation auftreten, ist ihre [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) rechten abrufen.**</span><span class="sxs-lookup"><span data-stu-id="a1bfb-135">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="a1bfb-136">Um die Installation zu testen, benötigen Sie einen Kontakt auf Skype für Unternehmen, die nicht hinter der Firewall Ihres Unternehmens ist.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-136">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="a1bfb-137">Nachdem ändern Sie die Einstellungen für externe Kommunikation, **Warten Sie, bis zu 24 Stunden zu testen**.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-137">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="a1bfb-138">Suchen Sie in Skype für Unternehmen nach dem Kontakt in Skype für Unternehmen, und senden Sie eine Anforderung zum chat.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-138">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="a1bfb-139">Wenn Sie eine Meldung, die aufgrund der Unternehmensrichtlinie gesendet werden konnte erhalten, müssen Sie Ihre [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-139">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="a1bfb-140">Bitten Sie Ihre Skype für Business Contact senden eine Anforderung an chat.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-140">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="a1bfb-141">Wenn Sie ihre Anforderung erhalten, wird das Problem Einstelllungen Firewall (vorausgesetzt, sie haben bereits bestätigt, dass ihre Firewalleinstellungen korrekt sind).</span><span class="sxs-lookup"><span data-stu-id="a1bfb-141">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="a1bfb-142">Eine andere Möglichkeit zu prüfen, ob das Problem der Firewall ist ist, gehen Sie an einem Speicherort Wifi nicht hinter der Firewall wie einem Café und Skype für Unternehmen das Senden einer Anforderung an den Kontakt zu chat verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-142">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="a1bfb-143">Wenn die Meldung Es durchläuft, aber nicht, wenn Sie im Büro sind, klicken Sie dann Sie, das Problem wissen ist die Firewall.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-143">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="a1bfb-144">Wie andere Personen finden und gefunden werden, beim Herstellen einer Verbindung mit einem anderen Unternehmen</span><span class="sxs-lookup"><span data-stu-id="a1bfb-144">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="a1bfb-145"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a1bfb-145"></span></span>

<span data-ttu-id="a1bfb-146">Nachdem Sie die externe Kommunikation mit anderen Skype für Unternehmensbenutzer aktivieren, Ihre Benutzer können Verbund Skype für Unternehmensbenutzer anhand suchen für ihren Anmeldenamen ein: beispielsweise Rob@contoso.com. Klicken Sie dann müssen sie die Person zu ihrer Liste Kontakte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-146">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com. Then they will need to add the person to their list of contacts.</span></span>
  
![Wenn einen Benutzer in einer verbundgeschäftspartner suchen möchten, müssen Sie ihre e-Mail-Adresse suchen (Dies ist in der Regel auch ihre-Anmeldename).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="a1bfb-148">Tipps zur Einrichtung der Kommunikation mit federated Unternehmen</span><span class="sxs-lookup"><span data-stu-id="a1bfb-148">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="a1bfb-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a1bfb-149"></span></span>

- <span data-ttu-id="a1bfb-150">Konfigurieren von Verbund zwischen Skype für Business 2015 und Skype für Business Online finden Sie in dieser TechNet-Artikel: [Configure Verbund mit Skype für Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="a1bfb-150">To configure federation between Skype for Business 2015 and Skype for Business Online, see this TechNet article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="a1bfb-151">Um zwischen Lync und Skype-Verbund für Business Online zu konfigurieren, finden Sie unter TechNet-Artikel: [Configuring Federation Support für Lync Online-Kunden](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="a1bfb-151">To configure federation between Lync and Skype for Business Online, see this TechNet article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="a1bfb-152">Wenn zwei Skype für Unternehmensbenutzer in Office 365 sind in unterschiedlichen Domänen miteinander kommunizieren, können sie nur Skype für Business-Features (beispielsweise videounterhaltungen oder Desktopfreigabe) verwenden, die in beiden Organisationen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-152">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="a1bfb-153">Wenn eine Skype für Business-Benutzer in Ihrer Organisation für eine In-Place oder Aufbewahrung für eventuelle Rechtsstreitigkeiten festgelegt wird, werden alle Sofortnachrichtenunterhaltungen zwischen diesem Benutzer und andere Skype für Business oder Skype-Benutzer in **Wiederherstellbare Elemente** in ihrem Postfach gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-153">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="a1bfb-154">Diese Gespräche werden nicht im Verlaufsordner **Unterhaltungen** in ihrem Postfach gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-154">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="a1bfb-155">Deaktivieren der externen Kommunikation für den bestimmten Einzelpersonen</span><span class="sxs-lookup"><span data-stu-id="a1bfb-155">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="a1bfb-156"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a1bfb-156"></span></span>

<span data-ttu-id="a1bfb-157">Nachdem Sie die externe Kommunikation für das gesamte Unternehmen aktivieren, können Sie sie nur bestimmten Personen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-157">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="a1bfb-158">Melden Sie sich mit Ihrem Office 365-Admin-Konto.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-158">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="a1bfb-159">Wechseln Sie in das Office 365 Administrationscenter zu **Benutzern** > **aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-159">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="a1bfb-160">Klicken Sie in der Liste der Benutzer wählen Sie den Benutzer, und klicken Sie unter **Weitere Einstellungen** **Skype für Business Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-160">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Wählen Sie Skype für Unternehmen](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="a1bfb-162">Wählen Sie in der **Skype für Business Administrationscenter** **externe Kommunikation**.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-162">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="a1bfb-163">Auf der Seite **Optionen** werden alle Optionen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-163">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="a1bfb-164">Deaktivieren Sie die Kommunikation, die Sie deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-164">Clear the communications you want to disable.</span></span> <span data-ttu-id="a1bfb-165">Die folgende Abbildung zeigt, dass Jakob mit Personen in anderen vertrauenswürdigen Unternehmen, aber nicht mit anderen Skype-Benutzern kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-165">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Wählen Sie externe Kontakte](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="a1bfb-167">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-167">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a1bfb-168">Möglicherweise müssen Sie warten, bis zu 24 Stunden, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="a1bfb-168">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="a1bfb-169">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a1bfb-169">Related topics</span></span>
<span data-ttu-id="a1bfb-170"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="a1bfb-170"></span></span>

[<span data-ttu-id="a1bfb-171">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a1bfb-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="a1bfb-172">Können Sie Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="a1bfb-172">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  


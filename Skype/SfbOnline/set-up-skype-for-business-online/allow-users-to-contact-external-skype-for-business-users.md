---
title: Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
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
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: 24cedb4a9fd612c3aa0c4886a9a35dd89b52fbe7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887593"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="53da6-103">Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren</span><span class="sxs-lookup"><span data-stu-id="53da6-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="53da6-104">Skype für den Verbund Business nicht zu Office 365 handelt, das von 21Vianet und Office 365 Deutschland Organisationen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="53da6-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="53da6-105">Führen Sie die Schritte in diesem Artikel in folgenden Fällen aus:</span><span class="sxs-lookup"><span data-stu-id="53da6-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="53da6-p101">In Ihrem Unternehmen befinden sich Benutzer in verschiedenen Domänen. Beispiel: Rob@ContosoEast.com und Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="53da6-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="53da6-108">Sie möchten den Personen in Ihrer Organisation die Möglichkeit geben, Skype for Business zu verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="53da6-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="53da6-109">Sie möchten andere Person in der ganzen Welt, die Skype für Unternehmen verwendet, in der Lage, zu finden, und wenden Sie sich mithilfe Ihrer e-Mail-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="53da6-109">You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="53da6-110">Wenn Sie und die anderen Benutzer die Standardeinstellungen für Skype for Business verwenden, funktioniert dies automatisch.</span><span class="sxs-lookup"><span data-stu-id="53da6-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="53da6-111">Anderenfalls müssen sie sicherstellen, dass Ihre Domäne nicht durch ihre Konfiguration blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="53da6-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="53da6-112">Aktivieren der Business-to-Business-Kommunikation für die Benutzer</span><span class="sxs-lookup"><span data-stu-id="53da6-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="53da6-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="53da6-113"></span></span>

<span data-ttu-id="53da6-114">Sie benötigen [Administratorberechtigungen](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in beiden Organisationen möchten.</span><span class="sxs-lookup"><span data-stu-id="53da6-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="53da6-115">![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="53da6-115">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="53da6-116">Melden Sie sich mit Ihrem Office 365-Admin-Konto.</span><span class="sxs-lookup"><span data-stu-id="53da6-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="53da6-117">Gehen Sie in Office 365 Admin Center zu **Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="53da6-117">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="53da6-119">Wählen Sie in der **Skype für Business Administrationscenter**, **Organisation** > **externe Kommunikation**.</span><span class="sxs-lookup"><span data-stu-id="53da6-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
4. <span data-ttu-id="53da6-120">Zum Einrichten der Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne, in der Dropdown-Feld auswählen **auf nur für zulässige Domänen**.</span><span class="sxs-lookup"><span data-stu-id="53da6-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="53da6-p103">ODER wählen Sie, wenn Sie die Kommunikation mit allen anderen Unternehmen aktivieren möchten, die über offene Skype for Business-Richtlinien verfügen, die Option **Aktivieren mit Ausnahme der blockierten Domänen** aus. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="53da6-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
5. <span data-ttu-id="53da6-123">Wählen Sie unter **blockiert oder zugelassenen Domänen**, **+** , und fügen Sie den Namen der Domäne, die Sie zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="53da6-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
6. <span data-ttu-id="53da6-124">Stellen Sie sicher, dass der Administrator in der anderen Organisation dieselben Schritte in ihrer **Skype für Business Administrationscenter**ist.</span><span class="sxs-lookup"><span data-stu-id="53da6-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="53da6-125">Beispiel: In der Liste der **zugelassenen Domänen** muss der Administrator der anderen Organisation die Domäne für Ihr Unternehmen eingeben.</span><span class="sxs-lookup"><span data-stu-id="53da6-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
7. <span data-ttu-id="53da6-126">Wenn Sie die Windows-Firewall verwenden, öffnet Skype for Business die erforderlichen Ports automatisch.</span><span class="sxs-lookup"><span data-stu-id="53da6-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="53da6-127">Wenn Ihre Organisation die Internetverbindung von Computern in Ihrem Netzwerk mit einer anderen Firewall-Lösung einschränkt, vergewissern Sie sich, dass Ihre Clientcomputer auf die folgenden [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="53da6-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="53da6-128">Es kann erforderlich sein, die FQDNs, die ausgehende Zulassungsliste in die Firewall oder der Proxy Infrastruktur-Konfiguration hinzufügen: \*\* \*. api.skype.com\*\*, \* **. users.storage.live.com**, und **graph.skype.com**.</span><span class="sxs-lookup"><span data-stu-id="53da6-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="53da6-129">Überprüfen Sie für Informationen dazu, wie Sie diese Ports in der Firewall zu öffnen die Begleitdokumentation es.</span><span class="sxs-lookup"><span data-stu-id="53da6-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="53da6-130">Eine Liste aller Ports, die Sie öffnen möchten, finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="53da6-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

8. <span data-ttu-id="53da6-131">Stellen Sie sicher, dass der Administrator in der Organisation auch diese Schritte ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="53da6-131">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
9. <span data-ttu-id="53da6-p106">**WARTEN SIE MIT DEM TEST BIS ZU 24 STUNDEN**. Bei jeder Änderung der Einstellungen für externe Kommunikation kann es bis zu 24 Stunden dauern, bis die Änderungen in allen Rechenzentren übernommen wurden.</span><span class="sxs-lookup"><span data-stu-id="53da6-p106">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="53da6-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Sie können Ihren Benutzern jetzt die Möglichkeit geben, nach beliebigen Benutzern von Skype, der kostenlosen Heimanwender-App, zu suchen und Chatnachrichten mit ihnen auszutauschen!</span><span class="sxs-lookup"><span data-stu-id="53da6-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="53da6-135">Finden Sie weitere Informationen finden Sie unter [Let Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="53da6-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="53da6-136">Tests und Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="53da6-136">Test and troubleshoot</span></span>
<span data-ttu-id="53da6-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="53da6-137"></span></span>

 <span data-ttu-id="53da6-138">**Am häufigsten haben Benutzer beim Einrichten der Kommunikation zwischen Unternehmen Probleme damit, die [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) richtig festzulegen.**</span><span class="sxs-lookup"><span data-stu-id="53da6-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="53da6-139">Um Ihr Setup zu testen, benötigen Sie einen Kontakt in Skype for Business, der sich nicht hinter der Firewall Ihrer Firma befindet.</span><span class="sxs-lookup"><span data-stu-id="53da6-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="53da6-140">Warten Sie nach einer Änderung der Einstellungen für externe Kommunikation **BIS ZU 24 STUNDEN, BEVOR SIE TESTS DURCHFÜHREN**.</span><span class="sxs-lookup"><span data-stu-id="53da6-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="53da6-141">Suchen Sie in Skype for Business nach Ihrem Kontakt in Skype for Business, und senden Sie eine Chatanfrage.</span><span class="sxs-lookup"><span data-stu-id="53da6-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="53da6-142">Wenn Sie eine Meldung, die aufgrund der Unternehmensrichtlinie gesendet werden konnte erhalten, müssen Sie Ihre [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)überprüfen.</span><span class="sxs-lookup"><span data-stu-id="53da6-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="53da6-p108">Bitten Sie Ihren Skype for Business-Kontakt, Ihnen eine Chatanfrage zu senden. Wenn Sie die Anfrage nicht erhalten, stellen die Firewalleinstellungen das Problem dar (dabei wird angenommen, dass der Kontakt bereits die Richtigkeit seiner Firewalleinstellungen überprüft hat).</span><span class="sxs-lookup"><span data-stu-id="53da6-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="53da6-p109">Eine weitere Möglichkeit, zu testen, ob die Firewall das Problem darstellt: Gehen Sie zu einem Ort mit WLAN, der sich nicht hinter Ihrer Firewall befindet (zum Beispiel in ein Café), und senden Sie mit Skype for Business eine Chatanfrage an Ihren Kontakt. Wenn die Nachricht dort gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.</span><span class="sxs-lookup"><span data-stu-id="53da6-p109">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat. If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="53da6-147">Beim Herstellen einer Verbindung mit einem anderen Unternehmen andere Personen finden und selbst gefunden werden</span><span class="sxs-lookup"><span data-stu-id="53da6-147">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="53da6-148"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="53da6-148"></span></span>

<span data-ttu-id="53da6-149">Nachdem Sie die externe Kommunikation mit anderen Skype für Unternehmensbenutzer aktivieren, Ihre Benutzer können Verbund Skype für Unternehmensbenutzer anhand suchen für ihren Anmeldenamen ein: beispielsweise Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="53da6-149">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="53da6-150">Anschließend müssen sie die Person zu ihrer Kontaktliste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="53da6-150">Then they will need to add the person to their list of contacts.</span></span>
  
![Wenn einen Benutzer in einer verbundgeschäftspartner suchen möchten, müssen Sie ihre e-Mail-Adresse suchen (Dies ist in der Regel auch ihre-Anmeldename).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="53da6-152">Tipps zum Einrichten der Kommunikation mit Partnerunternehmen</span><span class="sxs-lookup"><span data-stu-id="53da6-152">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="53da6-153"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="53da6-153"></span></span>

- <span data-ttu-id="53da6-154">Konfigurieren von Verbund zwischen Skype für Business 2015 und Skype für Business Online finden Sie in diesem Artikel: [Configure Verbund mit Skype für Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="53da6-154">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="53da6-155">Konfigurieren von Verbund zwischen Lync und Skype für Business Online finden Sie in diesem Artikel: [Configuring Federation Support für Lync Online-Kunden](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="53da6-155">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="53da6-156">Wenn zwei Skype for Business-Benutzer in Office 365 auf verschiedenen Domänen miteinander kommunizieren, können sie nur Skype for Business-Funktionen nutzen, die in beiden Organisationen aktiviert wurden (zum Beispiel Videounterhaltung oder Desktopfreigabe).</span><span class="sxs-lookup"><span data-stu-id="53da6-156">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="53da6-157">Wenn eine Skype für Business-Benutzer in Ihrer Organisation für eine In-Place oder Aufbewahrung für eventuelle Rechtsstreitigkeiten festgelegt wird, werden alle Sofortnachrichtenunterhaltungen zwischen diesem Benutzer und andere Skype für Business oder Skype-Benutzer in **Wiederherstellbare Elemente** in ihrem Postfach gespeichert.</span><span class="sxs-lookup"><span data-stu-id="53da6-157">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="53da6-158">Diese Unterhaltungen werden nicht im Ordner **Aufgezeichnete Unterhaltungen** in ihrem Postfach gespeichert.</span><span class="sxs-lookup"><span data-stu-id="53da6-158">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="53da6-159">Externe Kommunikation für bestimmte Personen deaktivieren</span><span class="sxs-lookup"><span data-stu-id="53da6-159">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="53da6-160"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="53da6-160"></span></span>

<span data-ttu-id="53da6-161">Nachdem Sie die externe Kommunikation für Ihr gesamtes Unternehmen aktiviert haben, können Sie sie für bestimmte Personen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="53da6-161">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="53da6-162">Melden Sie sich mit Ihrem Office 365-Admin-Konto.</span><span class="sxs-lookup"><span data-stu-id="53da6-162">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="53da6-163">Wechseln Sie in das Office 365 Administrationscenter zu **Benutzern** > **aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="53da6-163">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="53da6-164">Klicken Sie in der Liste der Benutzer auf den Benutzer und dann unter **Weitere Einstellungen** auf **Skype for Business-Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="53da6-164">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="53da6-166">Wählen Sie in der **Skype für Business Administrationscenter** **externe Kommunikation**.</span><span class="sxs-lookup"><span data-stu-id="53da6-166">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="53da6-167">Auf der Seite **Optionen** werden alle Optionen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="53da6-167">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="53da6-168">Deaktivieren Sie die Kommunikation, die Sie deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="53da6-168">Clear the communications you want to disable.</span></span> <span data-ttu-id="53da6-169">Die folgende Abbildung zeigt, dass Jakob mit Personen in anderen vertrauenswürdigen Unternehmen kommunizieren kann, darüber hinaus jedoch nicht mit anderen Skype-Nutzern.</span><span class="sxs-lookup"><span data-stu-id="53da6-169">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="53da6-171">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="53da6-171">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="53da6-172">Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="53da6-172">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="53da6-173">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="53da6-173">Related topics</span></span>
<span data-ttu-id="53da6-174"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="53da6-174"></span></span>

[<span data-ttu-id="53da6-175">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="53da6-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="53da6-176">Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="53da6-176">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 

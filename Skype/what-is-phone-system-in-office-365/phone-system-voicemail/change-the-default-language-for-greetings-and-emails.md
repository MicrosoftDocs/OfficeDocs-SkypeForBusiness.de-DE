---
title: "Ändern der Standardsprache für Ansagen und E-Mails"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "Hier erfahren Sie, wie Sie Skype for Business so einrichten, dass für die standardmäßige Voicemail-Ansage Ihrer Organisation eine andere Sprache verwendet wird. "
ms.openlocfilehash: 1c311436ed9010ea20598aac6a55b4806fe18abb
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="02702-103">Ändern der Standardsprache für Ansagen und E-Mails</span><span class="sxs-lookup"><span data-stu-id="02702-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="02702-104">Wenn Sie [globaler Office 365-Administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) sind, können Sie Skype for Business so einrichten, dass die standardmäßige Voicemail-Ansage in einer anderen Sprache wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="02702-104">If you are an [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="02702-105">Die Standardansage des Systems lautet zum Beispiel „Bitte hinterlassen Sie eine Nachricht für John Smith.</span><span class="sxs-lookup"><span data-stu-id="02702-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="02702-106">Nehmen Sie Ihre Nachricht nach dem Ton auf.</span><span class="sxs-lookup"><span data-stu-id="02702-106">After the tone, please record your message.</span></span> <span data-ttu-id="02702-107">Wenn Sie fertig sind, legen Sie auf, oder drücken Sie die Rautetaste, um weitere Optionen zu verwenden.".</span><span class="sxs-lookup"><span data-stu-id="02702-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="02702-108">**Lesen Sie zunächst diese wichtigen Informationen:**</span><span class="sxs-lookup"><span data-stu-id="02702-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="02702-109">**Die Ihnen zur Verfügung stehenden Sprachen hängen vom Standort Ihrer Organisation ab**.</span><span class="sxs-lookup"><span data-stu-id="02702-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="02702-110">Wenn sich Ihre Organisation beispielsweise in den USA befindet, können Sie die Standardsprache auf Englisch oder Spanisch festlegen.</span><span class="sxs-lookup"><span data-stu-id="02702-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="02702-111">Wenn sich Ihre Organisation in Kanada befindet, können Sie zwischen Englisch und Französisch wählen.</span><span class="sxs-lookup"><span data-stu-id="02702-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="02702-112">Eine Liste der unterstützten Sprachen finden Sie unter [Sprachen für Voicemail-Ansagen und -nachrichten von Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="02702-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="02702-p103">**Es ist nicht möglich, die Systemsprache für nur eine Person in der Organisation zu ändern.** Sie können die Systemsprache nur für alle Personen in der Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="02702-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="02702-115">Benutzer können nach der Anmeldung ihre eigene Ansagesprache in ihren Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="02702-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="02702-116">**Möchten Sie Ihre ausgehende Voicemail-Nachricht aufzeichnen?**</span><span class="sxs-lookup"><span data-stu-id="02702-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="02702-117">Lesen Sie [Überprüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="02702-117">See [Check Skype for Business voicemail and options](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="02702-118">Ändern der Systemsprache für alle Benutzer in der Organisation</span><span class="sxs-lookup"><span data-stu-id="02702-118">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="02702-119">Melden Sie sich mit Ihrem Konto [als globaler Office 365-Administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.</span><span class="sxs-lookup"><span data-stu-id="02702-119">Sign in with your [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="02702-120">Wählen Sie im Admin Center die Optionen **Einstellungen** > **Organisationsprofil** aus.</span><span class="sxs-lookup"><span data-stu-id="02702-120">In the admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](../../images/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="02702-122">Wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="02702-122">Choose **Edit**.</span></span>
    
    ![Choose Edit.](../../images/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="02702-124">Wählen Sie in der Liste **Bevorzugte Sprache** eine Sprache für alle in der Organisation aus.</span><span class="sxs-lookup"><span data-stu-id="02702-124">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="02702-125">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="02702-125">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="02702-126">Verwandte Artikel für Administratoren</span><span class="sxs-lookup"><span data-stu-id="02702-126">Related articles for the admin</span></span>

- [<span data-ttu-id="02702-127">Was sind Anrufpläne in Office 365?</span><span class="sxs-lookup"><span data-stu-id="02702-127">What are Calling Plans in Office 365?</span></span>](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="02702-128">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="02702-128">Set up Calling Plans</span></span>](../../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
    
- [<span data-ttu-id="02702-129">Planen des Telefonsystems in Office 365 mit lokaler PSTN-Anbindung in Skype for Business Server 2015 oder Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02702-129">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server 2015 or Lync Server 2013</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="02702-130">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="02702-130">Related topics</span></span>

- [<span data-ttu-id="02702-131">Ändern der Anzeigesprache und Zeitzone in Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="02702-131">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/en-us/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="02702-132">[Hinzufügen einer Sprache oder Festlegen von Spracheinstellungen in Office 2010 und höher](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="02702-132">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="02702-133">Aktivieren oder Ändern einer Sprache für das Tastaturlayout</span><span class="sxs-lookup"><span data-stu-id="02702-133">Enable or change a keyboard layout language</span></span>](https://support.office.com/en-us/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    


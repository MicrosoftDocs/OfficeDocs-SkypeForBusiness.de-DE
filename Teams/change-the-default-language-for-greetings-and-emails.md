---
title: Ändern der Standardsprache für Ansagen und E-Mails
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Hier erfahren Sie, wie Sie Skype for Business so einrichten, dass für die standardmäßige Voicemail-Ansage Ihrer Organisation eine andere Sprache verwendet wird. '
ms.openlocfilehash: 0acfb798e404ea0aef4e49a866f0501b85e33653
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "30541608"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="8dfde-103">Ändern der Standardsprache für Ansagen und E-Mails</span><span class="sxs-lookup"><span data-stu-id="8dfde-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="8dfde-104">Wenn Sie [globaler Office 365-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) sind, können Sie Skype for Business so einrichten, dass die standardmäßige Voicemail-Ansage in einer anderen Sprache wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8dfde-104">If you are an [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="8dfde-105">Die Standardansage des Systems lautet zum Beispiel „Bitte hinterlassen Sie eine Nachricht für John Smith.</span><span class="sxs-lookup"><span data-stu-id="8dfde-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="8dfde-106">Nehmen Sie Ihre Nachricht nach dem Ton auf.</span><span class="sxs-lookup"><span data-stu-id="8dfde-106">After the tone, please record your message.</span></span> <span data-ttu-id="8dfde-107">Wenn Sie fertig sind, legen Sie auf, oder drücken Sie die Rautetaste, um weitere Optionen zu verwenden.“.</span><span class="sxs-lookup"><span data-stu-id="8dfde-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="8dfde-108">**Lesen Sie zunächst diese wichtigen Informationen:**</span><span class="sxs-lookup"><span data-stu-id="8dfde-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="8dfde-109">**Die Ihnen zur Verfügung stehenden Sprachen hängen vom Standort Ihrer Organisation ab**.</span><span class="sxs-lookup"><span data-stu-id="8dfde-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="8dfde-110">Wenn sich Ihre Organisation beispielsweise in den USA befindet, können Sie die Standardsprache auf Englisch oder Spanisch festlegen.</span><span class="sxs-lookup"><span data-stu-id="8dfde-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="8dfde-111">Wenn sich Ihre Organisation in Kanada befindet, können Sie zwischen Englisch und Französisch wählen.</span><span class="sxs-lookup"><span data-stu-id="8dfde-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="8dfde-112">Eine Liste der unterstützten Sprachen finden Sie unter [Sprachen für Voicemail-Ansagen und -nachrichten von Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="8dfde-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="8dfde-p103">**Es ist nicht möglich, die Systemsprache für nur eine Person in der Organisation zu ändern.** Sie können die Systemsprache nur für alle Personen in der Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="8dfde-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8dfde-115">Benutzer können nach der Anmeldung ihre eigene Ansagesprache in ihren Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="8dfde-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="8dfde-116">**Möchten Sie Ihre ausgehende Voicemail-Nachricht aufzeichnen?**</span><span class="sxs-lookup"><span data-stu-id="8dfde-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="8dfde-117">Lesen Sie [Überprüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="8dfde-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>

- <span data-ttu-id="8dfde-118">**Möchten Sie die Voicemail Prompt Sprache ändern?**</span><span class="sxs-lookup"><span data-stu-id="8dfde-118">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="8dfde-119">Wechseln Sie zu [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) , und wählen Sie eine neue Sprache unter **Sprache Prompt**.</span><span class="sxs-lookup"><span data-stu-id="8dfde-119">Go to [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="8dfde-120">Ändern der Systemsprache für alle Benutzer in der Organisation</span><span class="sxs-lookup"><span data-stu-id="8dfde-120">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="8dfde-121">Melden Sie sich mit Ihrer [Office 365 globaler Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) -Konto bei[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="8dfde-121">Sign in with your [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="8dfde-122">Wählen Sie in der Office 365-Verwaltungskonsole **Einstellungen** > **Profil des Unternehmens**.</span><span class="sxs-lookup"><span data-stu-id="8dfde-122">In the Office 365 admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="8dfde-124">Wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="8dfde-124">Choose **Edit**.</span></span>
    
    ![Choose Edit.](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="8dfde-126">Wählen Sie in der Liste **Bevorzugte Sprache** eine Sprache für alle in der Organisation aus.</span><span class="sxs-lookup"><span data-stu-id="8dfde-126">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="8dfde-127">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8dfde-127">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="8dfde-128">Verwandte Artikel für Administratoren</span><span class="sxs-lookup"><span data-stu-id="8dfde-128">Related articles for the admin</span></span>

- [<span data-ttu-id="8dfde-129">Was sind Anrufpläne in Office 365?</span><span class="sxs-lookup"><span data-stu-id="8dfde-129">What are Calling Plans in Office 365?</span></span>](what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="8dfde-130">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="8dfde-130">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="8dfde-131">Planen der Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="8dfde-131">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="8dfde-132">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8dfde-132">Related topics</span></span>

- [<span data-ttu-id="8dfde-133">Ändern der Anzeigesprache und Zeitzone in Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="8dfde-133">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="8dfde-134">[Hinzufügen einer Sprache oder Festlegen von Spracheinstellungen in Office 2010 und höher](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="8dfde-134">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="8dfde-135">Aktivieren oder Ändern einer Sprache für das Tastaturlayout</span><span class="sxs-lookup"><span data-stu-id="8dfde-135">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 

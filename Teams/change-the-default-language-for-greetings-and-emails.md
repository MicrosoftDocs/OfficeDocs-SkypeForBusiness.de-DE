---
title: Ändern der Standardsprache für Ansagen und E-Mails
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Hier erfahren Sie, wie Sie Skype für Unternehmen einrichten, um eine andere Sprache für die standardmäßige Voicemail-Ansage Ihrer Organisation zu verwenden. '
ms.openlocfilehash: 078fd14944d5384d38d870e09575980cc89e8889
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825233"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="a11c3-103">Ändern der Standardsprache für Ansagen und E-Mails</span><span class="sxs-lookup"><span data-stu-id="a11c3-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="a11c3-104">Wenn Sie [globaler Office 365-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) sind, können Sie Skype for Business so einrichten, dass die standardmäßige Voicemail-Ansage in einer anderen Sprache wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a11c3-104">If you are an [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="a11c3-105">Die Standardansage des Systems lautet zum Beispiel „Bitte hinterlassen Sie eine Nachricht für John Smith.</span><span class="sxs-lookup"><span data-stu-id="a11c3-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="a11c3-106">Nehmen Sie Ihre Nachricht nach dem Ton auf.</span><span class="sxs-lookup"><span data-stu-id="a11c3-106">After the tone, please record your message.</span></span> <span data-ttu-id="a11c3-107">Wenn Sie fertig sind, legen Sie auf, oder drücken Sie die Rautetaste, um weitere Optionen zu verwenden.".</span><span class="sxs-lookup"><span data-stu-id="a11c3-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="a11c3-108">**Lesen Sie zunächst diese wichtigen Informationen:**</span><span class="sxs-lookup"><span data-stu-id="a11c3-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="a11c3-109">**Die Ihnen zur Verfügung stehenden Sprachen hängen vom Standort Ihrer Organisation ab**.</span><span class="sxs-lookup"><span data-stu-id="a11c3-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="a11c3-110">Wenn sich Ihre Organisation beispielsweise in den USA befindet, können Sie die Standardsprache auf Englisch oder Spanisch festlegen.</span><span class="sxs-lookup"><span data-stu-id="a11c3-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="a11c3-111">Wenn sich Ihre Organisation in Kanada befindet, können Sie zwischen Englisch und Französisch wählen.</span><span class="sxs-lookup"><span data-stu-id="a11c3-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="a11c3-112">Eine Liste der unterstützten Sprachen finden Sie unter [Sprachen für Voicemail-Ansagen und -nachrichten von Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a11c3-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="a11c3-p103">**Es ist nicht möglich, die Systemsprache für nur eine Person in der Organisation zu ändern.** Sie können die Systemsprache nur für alle Personen in der Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="a11c3-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a11c3-115">Benutzer können nach der Anmeldung ihre eigene Ansagesprache in ihren Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="a11c3-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="a11c3-116">**Möchten Sie Ihre ausgehende Voicemail-Nachricht aufzeichnen?**</span><span class="sxs-lookup"><span data-stu-id="a11c3-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="a11c3-117">Lesen Sie [Überprüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="a11c3-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="a11c3-118">Für Microsoft Teams – Benutzer können Ihre Voicemail-Einstellungen über die [Einstellungen des Teams-Desktop Clients](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) ändern.</span><span class="sxs-lookup"><span data-stu-id="a11c3-118">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="a11c3-119">**Möchten Sie die Sprache für die Voicemail-Ansage ändern?**</span><span class="sxs-lookup"><span data-stu-id="a11c3-119">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="a11c3-120">Für Skype for Business – [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) und wählen Sie unter **Eingabeaufforderung**eine neue Sprache aus.</span><span class="sxs-lookup"><span data-stu-id="a11c3-120">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="a11c3-121">Für Microsoft Teams – Benutzer können Ihre Voicemail-Einstellungen über die [Einstellungen des Teams-Desktop Clients](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) ändern.</span><span class="sxs-lookup"><span data-stu-id="a11c3-121">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="a11c3-122">Ändern der Systemsprache für alle Benutzer in der Organisation</span><span class="sxs-lookup"><span data-stu-id="a11c3-122">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="a11c3-123">Registrieren Sie sich[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)bei Ihrem [globalen Office 365-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Konto.</span><span class="sxs-lookup"><span data-stu-id="a11c3-123">Sign in with your [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="a11c3-124">Wählen Sie im Microsoft 365 Admin Center **Einstellungen** > **Organisationsprofil**aus.</span><span class="sxs-lookup"><span data-stu-id="a11c3-124">In the Microsoft 365 admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Screenshot mit Auswahl von Einstellungen und dann Organisationsprofil](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="a11c3-126">Wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="a11c3-126">Choose **Edit**.</span></span>
    
    ![Screenshot mit der Option "Bearbeiten"](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="a11c3-128">Wählen Sie in der Liste **Bevorzugte Sprache** eine Sprache für alle in der Organisation aus.</span><span class="sxs-lookup"><span data-stu-id="a11c3-128">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="a11c3-129">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a11c3-129">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="a11c3-130">Verwandte Artikel für Administratoren</span><span class="sxs-lookup"><span data-stu-id="a11c3-130">Related articles for the admin</span></span>

- [<span data-ttu-id="a11c3-131">Telefonsystem und Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="a11c3-131">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="a11c3-132">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="a11c3-132">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="a11c3-133">Planen des Telefonsystems in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a11c3-133">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="a11c3-134">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a11c3-134">Related topics</span></span>

- [<span data-ttu-id="a11c3-135">Ändern der Anzeigesprache und Zeitzone in Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="a11c3-135">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="a11c3-136">[Hinzufügen einer Sprache oder Festlegen von Spracheinstellungen in Office 2010 und höher](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="a11c3-136">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="a11c3-137">Aktivieren oder Ändern einer Sprache für das Tastaturlayout</span><span class="sxs-lookup"><span data-stu-id="a11c3-137">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 

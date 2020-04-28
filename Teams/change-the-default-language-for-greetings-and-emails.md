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
- seo-marvel-mar2020
description: Hier erfahren Sie, wie Sie Skype für Unternehmen einrichten, um eine andere Sprache für die standardmäßige Voicemail-Ansage Ihrer Organisation zu verwenden.
ms.openlocfilehash: 9941ba697300d7dd1426e278d8d42900621cf58a
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904330"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="8a47b-103">Ändern der Standardsprache für Ansagen und E-Mails</span><span class="sxs-lookup"><span data-stu-id="8a47b-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="8a47b-104">Wenn Sie ein [globaler Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)sind, können Sie Skype for Business so einrichten, dass seine Standardansage für Voicemail in einer anderen Sprache wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8a47b-104">If you are a [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="8a47b-105">Die standardmäßige Systemansage lautet zum Beispiel „Bitte hinterlassen Sie eine Nachricht für John Smith.</span><span class="sxs-lookup"><span data-stu-id="8a47b-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="8a47b-106">Nehmen Sie Ihre Nachricht nach dem Ton auf.</span><span class="sxs-lookup"><span data-stu-id="8a47b-106">After the tone, please record your message.</span></span> <span data-ttu-id="8a47b-107">Wenn Sie fertig sind, legen Sie auf, oder drücken Sie die Rautetaste, um weitere Optionen zu verwenden.".</span><span class="sxs-lookup"><span data-stu-id="8a47b-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="8a47b-108">**Lesen Sie zunächst diese wichtigen Informationen:**</span><span class="sxs-lookup"><span data-stu-id="8a47b-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="8a47b-109">**Die Ihnen zur Verfügung stehenden Sprachen hängen vom Standort Ihrer Organisation ab**.</span><span class="sxs-lookup"><span data-stu-id="8a47b-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="8a47b-110">Wenn sich Ihre Organisation beispielsweise in den USA befindet, können Sie die Standardsprache auf Englisch oder Spanisch festlegen.</span><span class="sxs-lookup"><span data-stu-id="8a47b-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="8a47b-111">Wenn sich Ihre Organisation in Kanada befindet, können Sie zwischen Englisch und Französisch wählen.</span><span class="sxs-lookup"><span data-stu-id="8a47b-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="8a47b-112">Eine Liste der unterstützten Sprachen finden Sie unter [Sprachen für Voicemail-Ansagen und -nachrichten von Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="8a47b-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="8a47b-113">**Ändern von Sprachen für Voicemail-Gruß-und Voicemail-Nachrichten einzelner Benutzer.**</span><span class="sxs-lookup"><span data-stu-id="8a47b-113">**Changing languages for individual user's voicemail greeting and voicemail messages.**</span></span> <span data-ttu-id="8a47b-114">Sie können die bevorzugte lanaguage für Benutzer ändern, wodurch die Sprache der Voicemail-und Voicemail-Nachrichten, die an Ihr Outlook-Postfach gesendet werden, geändert wird.</span><span class="sxs-lookup"><span data-stu-id="8a47b-114">You can change the preferred lanaguage for users, which will change the language of the their voicemail greeting and voicemail messages sent to their Outlook mailbox.</span></span> <span data-ttu-id="8a47b-115">Anleitungen finden Sie unter [so wird es gemacht: Festlegen von Sprach-und Regionshttps://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)Einstellungen für Office 365] (.</span><span class="sxs-lookup"><span data-stu-id="8a47b-115">For instruction please see [How to set language and region settings for Office 365] (https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8a47b-116">Benutzer können Ihre eigene Ansage Sprache durch Ihre Einstellungen ändern, nachdem Sie sich mit den Anweisungen unter [Ändern ihrer Anzeigesprache und Zeitzone in Microsoft 365 for Business](https://support.office.com/en-us/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US) angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="8a47b-116">Users can change their own greeting language through their settings after they sign in by following instructions found in [Change your display language and time zone in Microsoft 365 for Business](https://support.office.com/en-us/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)</span></span>
  
- <span data-ttu-id="8a47b-117">**Möchten Sie Ihre ausgehende Voicemail-Nachricht aufzeichnen?**</span><span class="sxs-lookup"><span data-stu-id="8a47b-117">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="8a47b-118">Lesen Sie [Überprüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="8a47b-118">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="8a47b-119">Für Microsoft Teams – Benutzer können Ihre Voicemail-Einstellungen über die [Einstellungen des Teams-Desktop Clients](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) ändern.</span><span class="sxs-lookup"><span data-stu-id="8a47b-119">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="8a47b-120">**Möchten Sie die Sprache für die Voicemail-Ansage ändern?**</span><span class="sxs-lookup"><span data-stu-id="8a47b-120">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="8a47b-121">Für Skype for Business – [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) und wählen Sie unter **Eingabeaufforderung**eine neue Sprache aus.</span><span class="sxs-lookup"><span data-stu-id="8a47b-121">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="8a47b-122">Für Microsoft Teams – Benutzer können Ihre Voicemail-Ansage über die [Einstellungen des Teams-Desktop Clients](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) ändern.</span><span class="sxs-lookup"><span data-stu-id="8a47b-122">For Microsoft Teams - Users can change their voicemail greeting from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="8a47b-123">Ändern der Systemsprache für alle Benutzer in der Organisation</span><span class="sxs-lookup"><span data-stu-id="8a47b-123">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="8a47b-124">Registrieren Sie sich [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)bei Ihrem [globalen Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Konto.</span><span class="sxs-lookup"><span data-stu-id="8a47b-124">Sign in with your [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="8a47b-125">Wählen Sie im Microsoft 365 Admin Center **Einstellungen** > **Settings** > Einstellungen**Organisationsprofil**aus.</span><span class="sxs-lookup"><span data-stu-id="8a47b-125">In the Microsoft 365 admin center, choose **Settings** > **Settings** > **Organization profile**.</span></span> 
    
     ![Screenshot mit Auswahl von Einstellungen und dann Organisationsprofil](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="8a47b-127">Wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="8a47b-127">Choose **Edit**.</span></span>
    
    ![Screenshot mit der Option "Bearbeiten"](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="8a47b-129">Wählen Sie in der Liste **Bevorzugte Sprache** eine Sprache für alle in der Organisation aus.</span><span class="sxs-lookup"><span data-stu-id="8a47b-129">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="8a47b-130">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8a47b-130">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="8a47b-131">Verwandte Artikel für Administratoren</span><span class="sxs-lookup"><span data-stu-id="8a47b-131">Related articles for the admin</span></span>

- [<span data-ttu-id="8a47b-132">Telefonsystem und Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="8a47b-132">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="8a47b-133">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="8a47b-133">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="8a47b-134">Planen des Telefonsystems in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8a47b-134">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="8a47b-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8a47b-135">Related topics</span></span>

- [<span data-ttu-id="8a47b-136">Ändern der Anzeigesprache und Zeitzone in Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="8a47b-136">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="8a47b-137">[Hinzufügen einer Sprache oder Festlegen von Spracheinstellungen in Office 2010 und höher](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="8a47b-137">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="8a47b-138">Aktivieren oder Ändern einer Sprache für das Tastaturlayout</span><span class="sxs-lookup"><span data-stu-id="8a47b-138">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 

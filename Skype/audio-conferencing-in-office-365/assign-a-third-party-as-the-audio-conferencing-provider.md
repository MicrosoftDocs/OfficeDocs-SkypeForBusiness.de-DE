---
title: "Zuweisen eines Drittanbieters für Audiokonferenzen"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. '
ms.openlocfilehash: a53a2e63f15aa40eb6a88ab13daba2022b35e3b6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a><span data-ttu-id="62cab-103">Zuweisen eines Drittanbieters für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="62cab-103">Assign a third-party as the audio conferencing provider</span></span>

<span data-ttu-id="62cab-104">Kein Audiokonferenzanbieter stellt die *Konferenzbrücke*.</span><span class="sxs-lookup"><span data-stu-id="62cab-104">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="62cab-105">Die Konferenzbrücke bietet die Zugriffsnummer für Einwahl Telefonnummer, PINs und Konferenz-IDs für Besprechungen, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="62cab-105">The conference bridge provides the dial-in phone number, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="62cab-106">Sie müssen nur Personen zu planen, oder führen Skype für Business oder Microsoft-Teams, Besprechungen, die kein Audiokonferenzanbieter zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="62cab-106">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62cab-107">Für Microsoft Teams können Benutzer keinen Drittanbieter für Audiokonferenzen verwenden, sie müssen Audiokonferenzen in Office 365 verwenden. Dadurch wird Microsoft als Audiokonferenzanbieter festgelegt.</span><span class="sxs-lookup"><span data-stu-id="62cab-107">For Microsoft Teams, a user can't use a third-party audio conferencing provider, they must use Audio Conferencing in Office 365, which sets the audio conferencing provider to Microsoft.</span></span> 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="62cab-108">Schritte VOR dem Zuweisen eines Drittanbieters für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="62cab-108">Steps to do BEFORE you can assign a third-party audio conferencing provider</span></span>

1. <span data-ttu-id="62cab-109">Je nach Ihrer Office 365-Plan müssen Sie möglicherweise **Audiokonferenzen** Add-On-Lizenzen für die Personen in Ihrer Organisation, die beabsichtigen, planen, oder führen Skype für Business oder Microsoft-Teams, Besprechungen, die mithilfe von Audiokonferenzen kaufen.</span><span class="sxs-lookup"><span data-stu-id="62cab-109">Depending on your Office 365 plan, you might need to buy **Audio Conferencing** add-on licenses for the people in your organization who are going to schedule or lead Skype for Business or Microsoft Teams meetings using Audio Conferencing.</span></span> <span data-ttu-id="62cab-110">Finden Sie weitere Informationen finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="62cab-110">To learn more, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="62cab-111">Wenn Sie **Audiokonferenzen** Add-on Lizenzen erworben haben, ordnen sie die Personen in Ihrer Organisation, die planen, oder führen Besprechungen, die Audiokonferenz verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="62cab-111">If you purchased **Audio Conferencing** add-on licenses, assign them to the people in your organization who are going to schedule or lead meetings that use Audio Conferencing.</span></span> <span data-ttu-id="62cab-112">Finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="62cab-112">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62cab-p104">Wenn Sie einem Benutzer eine Lizenz für **Audiokonferenzen** zuweisen, **NACHDEM** Sie ihm einen Drittanbieter für Audiokonferenzen zugewiesen haben, wird für diesen Benutzer automatisch Microsoft als Audiokonferenzanbieter festgelegt. In diesem Fall müssen Sie zuerst Microsoft als Audiokonferenzanbieter entfernen, bevor Sie einen Drittanbieter für Audiokonferenzen zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="62cab-p104">If you assign an **Audio Conferencing** license to someone **AFTER** you assign them a third-party audio conferencing provider, that person will automatically be set to use Microsoft as their audio conferencing provider instead! If this happens, you will need to first remove Microsoft as the audio conferencing provider before you can assign a third-party audio conferencing provider to them.</span></span>
  
3. <span data-ttu-id="62cab-p105">Suchen Sie unter [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530) einen Drittanbieter für Audiokonferenzen. Nehmen Sie Kontakt zu ihm auf, und informieren Sie sich über die Einrichtung.</span><span class="sxs-lookup"><span data-stu-id="62cab-p105">Find a third-party audio conferencing provider at [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530). Contact them and find out how to get things set up with them.</span></span>
    
    <span data-ttu-id="62cab-117">Vom Anbieter erhalten Sie:</span><span class="sxs-lookup"><span data-stu-id="62cab-117">They will give you:</span></span>
    
  - <span data-ttu-id="62cab-118">**Einwahlnummern (gebührenpflichtig)** und gebührenfreie Telefonnummern, falls verfügbar</span><span class="sxs-lookup"><span data-stu-id="62cab-118">**Dial-in numbers (toll)** and toll-free numbers if they are available.</span></span>
    
  - <span data-ttu-id="62cab-p106">**Konferenz-IDs**, die für alle Benutzer verwendet werden, die Besprechungen planen. Manche ACPs bezeichnen diese als Konferenz-Passcodes.</span><span class="sxs-lookup"><span data-stu-id="62cab-p106">**Conference IDs** that are used for each person who schedules meetings. Some ACPs call these conference passcodes.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62cab-121">Wenn Sie das Anfangssetup für einen Drittanbieter-ACP durchgeführt haben und Änderungen vornehmen müssen, klicken Sie unten auf der Seite **Microsoft Bridge** auf **Klicken Sie hier, um einen Drittanbieter für Audiokonferenzen zu konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="62cab-121">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="62cab-122">Wenn Sie einen Benutzer für Audiokonferenzen aktivieren und ihm einen Drittanbieter für Audiokonferenzen zuweisen, werden die Audionummern und Konferenzkennungen (Passcodes) automatisch zu allen **neuen** Skype for Business Online-Besprechungen hinzugefügt, die er erstellt.</span><span class="sxs-lookup"><span data-stu-id="62cab-122">When you enable a person for audio conferencing, and assign them a third-party audio conferencing provider, the audio numbers and conference IDs (passcodes) are automatically added to any **new** Skype for Business Online meetings that they create.</span></span>
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a><span data-ttu-id="62cab-123">Zuweisen eines Drittanbieters für Audiokonferenzen zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="62cab-123">How to assign a third-party audio conferencing provider to a user</span></span>

1. <span data-ttu-id="62cab-p107">Wählen Sie im **Skype for Business Admin Center**die Option **Benutzer** aus. Wählen Sie den Benutzer in der Liste aus, und klicken Sie im Aktionsbereich auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="62cab-p107">In the **Skype for Business admin center**, choose **Users**. Select the user from the list and click **Edit** in the action pane.</span></span>
    
2. <span data-ttu-id="62cab-126">Klicken Sie auf der Seite mit den Eigenschaften des Benutzers auf **Audio conferencing** (Audiokonferenz), und geben Sie die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="62cab-126">On the user's properties page, click **Audio conferencing** and enter this information:</span></span>
    
  - <span data-ttu-id="62cab-127">**Name des Anbieters** Wählen Sie aus der Liste des Anbieters von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="62cab-127">**Provider name** Select the third-party provider from the list.</span></span>
    
  - <span data-ttu-id="62cab-128">**Gebührenpflichtige Standardnummer**: Diese Angabe ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="62cab-128">**Default toll number** This is required.</span></span>
    
  - <span data-ttu-id="62cab-129">**Gebührenfreie Standardnummer**: Diese Angabe ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="62cab-129">**Default toll-free number** This not required.</span></span>
    
  - <span data-ttu-id="62cab-130">**Konferenzkennung**: Diese Kennung erhalten Sie von Ihrem Audiokonferenzanbieter.</span><span class="sxs-lookup"><span data-stu-id="62cab-130">**Conference ID** This is provided by your audio conferencing provider.</span></span>
    
3. <span data-ttu-id="62cab-131">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="62cab-131">Click **Save**.</span></span>
    
4. <span data-ttu-id="62cab-p108">Senden Sie jedem Benutzer die PIN, die Sie vom Audiokonferenzanbieter erhalten haben. Die PIN ist möglicherweise zum Einwählen als Organisator oder Gesprächsleiter der Telefonkonferenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="62cab-p108">Send each person the PIN you received from the audio conferencing provider. The PIN may be required to call in as the conference call organizer or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62cab-134">Wenn Sie einen Drittanbieter für Audiokonferenzen verwenden, können Sie keine PINs für Besprechungsorganisatoren anzeigen oder festlegen.</span><span class="sxs-lookup"><span data-stu-id="62cab-134">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a><span data-ttu-id="62cab-135">Zuweisen eines Drittanbieters für Audiokonferenzen zu zahlreichen Benutzern gleichzeitig</span><span class="sxs-lookup"><span data-stu-id="62cab-135">How to assign a third-party audio conferencing provider to many people at the same time</span></span>

1. <span data-ttu-id="62cab-136">Wählen Sie in der **Skype für Business Administrationscenter**, **Audiokonferenzen** > **Microsoft-Brücke**.</span><span class="sxs-lookup"><span data-stu-id="62cab-136">In the **Skype for Business admin center**, choose **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="62cab-137">Klicken Sie am unteren Rand der Seite auf den Link **, wenn Sie, konfigurieren Sie einen Drittanbieter - Audiokonferenzen stattdessen möchten klicken Sie hier**.</span><span class="sxs-lookup"><span data-stu-id="62cab-137">At the bottom of the page, click the link in **If you would like to configure a third-party audio conferencing provider instead, click here**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62cab-138">Wenn dies ist der ersten Einrichten von Drittanbietern ACPS, aber jetzt müssen Sie den Änderungen am unteren Rand der Seite **Microsoft Bridge** , **Klicken Sie hier, um einen Drittanbieter - Audiokonferenzen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="62cab-138">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page, **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
2. <span data-ttu-id="62cab-p110">Klicken Sie auf der Seite **Konfigurieren eines externen Audiokonferenzanbieters** unter **Benutzer importieren und exportieren** auf **Export-Assistent**. Befolgen Sie dann die Schritte im **Assistenten zum Exportieren von Benutzern**. Wenn Sie fertig sind, haben Sie eine Datei, in der die Benutzer aufgelistet sind, die Sie für Audiokonferenzen einrichten möchten.</span><span class="sxs-lookup"><span data-stu-id="62cab-p110">On the **Configure a third party audio conferencing provider** page, under **Import and export users**, click **Export wizard**, and then follow the steps in the **Export Users wizard**. When you finish, you'll have a file that lists the people you want to set up for audio conferencing.</span></span>
    
3. <span data-ttu-id="62cab-p111">Senden Sie die erstellte Datei an Ihren Drittanbieter für Audiokonferenzen. Er fügt die Audiokonferenzinformationen für die in der Datei aufgelisteten Personen hinzu und sendet die Datei an Sie zurück.</span><span class="sxs-lookup"><span data-stu-id="62cab-p111">Send the file you created to your third-party audio conferencing provider. They will add audio conferencing information for the people listed in the file, and then return the file to you.</span></span>
    
4. <span data-ttu-id="62cab-p112">Prüfen Sie nach, ob die zurückgesandte Datei die richtigen Informationen enthält. Es sind Fälle vorgekommen, in denen nicht für jede in der Datei aufgelistete Person die richtigen Informationen angegeben waren.</span><span class="sxs-lookup"><span data-stu-id="62cab-p112">Double-check that the returned file has the right information in it. We've heard of instances where not everyone listed in the file got the right information.</span></span>
    
5. <span data-ttu-id="62cab-145">Klicken Sie auf der Seite **Konfigurieren eines externen Audiokonferenzanbieters** unter **Benutzer importieren und exportieren** auf **Import-Assistent**, und befolgen Sie dann die Schritte im **Assistenten zum Importieren von Benutzern**.</span><span class="sxs-lookup"><span data-stu-id="62cab-145">On the **Configure a third-party audio conferencing provider page**, under **Import and export users**, click **Import wizard**, and then follow the steps in the **Import Users wizard**</span></span>
    
6. <span data-ttu-id="62cab-p113">Senden Sie jedem Benutzer die PIN, die Sie vom Audiokonferenzanbieter erhalten haben. Die PIN ist möglicherweise zum Einwählen als Organisator oder Gesprächsleiter der Telefonkonferenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="62cab-p113">Send each person the PIN you received from the audio conferencing provider. The PIN may be required to call in as the conference call organizer, or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62cab-148">Wenn Sie einen Drittanbieter für Audiokonferenzen verwenden, können Sie keine PINs für Besprechungsorganisatoren anzeigen oder festlegen.</span><span class="sxs-lookup"><span data-stu-id="62cab-148">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="62cab-149">Verwendung eines Drittanbieters für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="62cab-149">When to use a third-party audio conferencing provider</span></span>

<span data-ttu-id="62cab-p114">Wenn Sie sich in einem Land/einer Region befinden, in dem/der Audiokonferenzen in Office 365 nicht verfügbar sind, die Servicequalität aufgrund des Standorts schlecht ist oder Sie einen Vertrag mit einem Drittanbieter für Audiokonferenzen abgeschlossen haben, sollten Sie einen Drittanbieter für Audiokonferenzen verwenden. Andernfalls empfehlen wir Microsoft als Audiokonferenzanbieter.</span><span class="sxs-lookup"><span data-stu-id="62cab-p114">If you are in a country or region where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract with a third-party audio conferencing provider, we recommend using a third-party audio conferencing provider. Otherwise, we recommend using Microsoft as your audio conferencing provider.</span></span>
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a><span data-ttu-id="62cab-152">Automatisieren der Zuweisung des externen Audiokonferenzanbieters anhand von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="62cab-152">Automate assigning the third-party audio conferencing provider by using Windows PowerShell</span></span>

- <span data-ttu-id="62cab-153">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) nutzen.</span><span class="sxs-lookup"><span data-stu-id="62cab-153">To save time or automate this, you can use the [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62cab-p115">Um den Audioanbieter von Microsoft in einen Drittanbieter für Audiokonferenzen zu ändern, müssen Sie Microsoft als Audiokonferenzanbieter entfernen. Dazu können Sie das Cmdlet [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="62cab-p115">To change the audio provider from Microsoft to a third-party audio conferencing provider, you must remove Microsoft as the audio conferencing provider. To do this, use the [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet.</span></span>
  
- <span data-ttu-id="62cab-156">Weitere Informationen zur Nutzung von Windows PowerShell finden Sie unter [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="62cab-156">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
    
## <a name="what-else-do-i-need-to-know"></a><span data-ttu-id="62cab-157">Was muss ich sonst noch wissen?</span><span class="sxs-lookup"><span data-stu-id="62cab-157">What else do I need to know?</span></span>

<span data-ttu-id="62cab-158">Eine Person in Ihrer Organisation kann nur einem Anbieter von Audiokonferenzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="62cab-158">A person in your organization can only use one audio conferencing provider.</span></span> <span data-ttu-id="62cab-159">Um eine Person für Audiokonferenzen an Microsoft zu ändern, finden Sie unter [Verschieben eines Benutzers für Audiokonferenzen an Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) oder [Microsoft als Anbieter von Audiokonferenzen zuweisen](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="62cab-159">To change a person's audio conferencing provider to Microsoft, see [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="62cab-160">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="62cab-160">Related Topics</span></span>

[<span data-ttu-id="62cab-161">Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="62cab-161">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="62cab-162">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="62cab-162">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  


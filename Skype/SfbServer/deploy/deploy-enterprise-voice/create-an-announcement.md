---
title: Erstellen oder Löschen einer Ankündigung in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Erstellen oder Löschen von Ansagen für ansageanwendung in Skype für Business Server Enterprise-VoIP. Dies wirkt sich auf den Umgang mit Anrufen an nicht zugewiesene Nummern aus.
ms.openlocfilehash: cbdcaed3d5908b76f0932f3461dfc21716f74b32
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372294"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="db34f-104">Erstellen oder Löschen einer Ankündigung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="db34f-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="db34f-105">Erstellen oder Löschen von Ansagen für ansageanwendung in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="db34f-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="db34f-106">Dies wirkt sich auf den Umgang mit Anrufen an nicht zugewiesene Nummern aus.</span><span class="sxs-lookup"><span data-stu-id="db34f-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="db34f-p103">Bei der Konfiguration von Ansagen wird tatsächlich konfiguriert, wie Anrufe an nicht zugewiesene Nummern verarbeitet werden sollen. Sie können eine Ansage wiedergeben, bei der es sich um eine Audiodatei oder eine TTS-Datei (Text-to-Speech, Text-zu-Sprache) handeln kann, oder Sie können den Anruf einfach an ein angegebenes Ziel durchstellen, ohne eine Ansage abzuspielen.</span><span class="sxs-lookup"><span data-stu-id="db34f-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="db34f-p104">Sie müssen Ansagen erstellen, bevor Sie die Tabelle nicht zugewiesener Nummern definieren. Diesen Schritt führen Sie für alle Ansagen aus, die eine Audioansage, eine TTS-Ansage oder keine Ansage enthalten.</span><span class="sxs-lookup"><span data-stu-id="db34f-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="db34f-111">In diesem Abschnitt wird beschrieben, wie Ansagen importiert und erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="db34f-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="db34f-112">Weitere Informationen zu den in der Tabelle für den nicht zugewiesenen Nummern Ansagen zuweisen finden Sie unter [Konfigurieren der Tabelle nicht zugewiesener Anzahl](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span><span class="sxs-lookup"><span data-stu-id="db34f-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="db34f-113">Erstellen einer neuen Ansage für nicht zugewiesene Nummern</span><span class="sxs-lookup"><span data-stu-id="db34f-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="db34f-114">Zum Erstellen einer neuen Ansage müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="db34f-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="db34f-115">Für Audioansagen zeichnen Sie die Audiodatei mithilfe Ihrer bevorzugten Anwendung zur Audioaufzeichnung auf.</span><span class="sxs-lookup"><span data-stu-id="db34f-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="db34f-116">Führen Sie für audioansagen das **Import-CsAnnouncementFile** -Cmdlet, um den Inhalt der Audiodatei in Dateispeicher zu importieren.</span><span class="sxs-lookup"><span data-stu-id="db34f-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="db34f-117">Führen Sie das Cmdlet **New-CsAnnouncement** erstellen, und nennen die Ankündigung aus.</span><span class="sxs-lookup"><span data-stu-id="db34f-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="db34f-118">Diesen Schritt führen Sie aus, um Ansagen zu erstellen, die Audioansagen, eine Text-zu-Sprache-Ansage (Text-to-Speech, TTS) oder keine Ansage enthalten.</span><span class="sxs-lookup"><span data-stu-id="db34f-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="db34f-119">Möglicherweise möchten Sie eine Ansage erstellen (wenn Sie z. B. Anrufe an ein bestimmtes Ziel durchstellen möchten, ohne eine Nachricht wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="db34f-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="db34f-120">Weisen Sie die neue Ansage einem Nummernbereich in der Tabelle nicht zugewiesener Nummern zu.</span><span class="sxs-lookup"><span data-stu-id="db34f-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="db34f-121">So erstellen Sie eine neue Ansage</span><span class="sxs-lookup"><span data-stu-id="db34f-121">To create a new announcement</span></span>

1. <span data-ttu-id="db34f-122">Erstellen Sie die Audiodatei für Audioansagen.</span><span class="sxs-lookup"><span data-stu-id="db34f-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="db34f-123">Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="db34f-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="db34f-124">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="db34f-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="db34f-125">Führen Sie für Audioansagen folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="db34f-125">For audio prompts, run:</span></span>

   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="db34f-126">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="db34f-126">Run:</span></span>

   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="db34f-p107">Zum Durchstellen von Anrufen an die Voicemail geben Sie „SIPAddress“ im Format „sip:Benutzername@Domänenname;opaque=app:voicemail“ ein (Beispiel: sip:bob@contoso.com;opaque=app:voicemail). Zum Durchstellen von Anrufen an eine Telefonnummer geben Sie „SIPAddress“ im Format „sip:Nummer@Domänenname;user=phone“ ein (Beispiel: sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="db34f-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="db34f-129">Beispiel für die Festlegung einer Audioansage:</span><span class="sxs-lookup"><span data-stu-id="db34f-129">For example, to specify an audio prompt:</span></span>

   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="db34f-130">Beispiel für die Festlegung einer TTS-Ansage:</span><span class="sxs-lookup"><span data-stu-id="db34f-130">For example, to specify a TTS prompt:</span></span>

   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="db34f-131">Ausführlichere Informationen zu diesen Cmdlets und zum Anzeigen einer Liste der Sprachcodes zur Verwendung im Parameter **TextToSpeechPrompt** finden Sie unter [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="db34f-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="db34f-132">Löschen einer Ansage für nicht zugewiesene Nummern</span><span class="sxs-lookup"><span data-stu-id="db34f-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="db34f-133">So löschen Sie eine Ansage</span><span class="sxs-lookup"><span data-stu-id="db34f-133">To delete an announcement</span></span>

1. <span data-ttu-id="db34f-134">Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="db34f-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="db34f-135">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="db34f-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="db34f-p108">Listen Sie alle Ansagen in Ihrer Organisation auf. Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="db34f-p108">List all the announcements in your organization. At the command line, run:</span></span>

   ```
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="db34f-p109">Suchen Sie in der Ergebnisliste nach der zu löschenden Ansage und kopieren Sie die GUID. Führen Sie an der Eingabeaufforderung dann Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="db34f-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>

   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="db34f-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="db34f-140">For example:</span></span>

   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="db34f-141">Ausführliche Informationen zu weiteren Optionen finden Sie unter [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) und [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="db34f-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="db34f-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db34f-142">See also</span></span>

[<span data-ttu-id="db34f-143">Erstellen oder Löschen einer Ankündigung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="db34f-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="db34f-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="db34f-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="db34f-145">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="db34f-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="db34f-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="db34f-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="db34f-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="db34f-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)


---
title: 'Lync Server 2013: Erstellen einer Ankündigung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfae1817cb47c769885ca42a7ca3ff6f57f7b669
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="dcbf4-102">Erstellen einer Ankündigung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcbf4-102">Create an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcbf4-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dcbf4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dcbf4-104">Zum Erstellen einer neuen Ansage müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="dcbf4-104">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="dcbf4-105">Für Audioansagen zeichnen Sie die Audiodatei mithilfe Ihrer bevorzugten Anwendung zur Audioaufzeichnung auf.</span><span class="sxs-lookup"><span data-stu-id="dcbf4-105">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="dcbf4-106">Führen Sie für Audioansagen das Cmdlet **Import-CsAnnouncementFile** aus, um den Inhalt der Audiodatei in den Dateispeicher zu importieren.</span><span class="sxs-lookup"><span data-stu-id="dcbf4-106">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="dcbf4-107">Führen Sie das Cmdlet **New-CsAnnouncement** aus, um die Ansage zu erstellen und zu benennen.</span><span class="sxs-lookup"><span data-stu-id="dcbf4-107">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="dcbf4-108">Diesen Schritt führen Sie aus, um Ansagen zu erstellen, die Audioansagen, eine Text-zu-Sprache-Ansage (Text-to-Speech, TTS) oder keine Ansage enthalten.</span><span class="sxs-lookup"><span data-stu-id="dcbf4-108">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="dcbf4-109">Möglicherweise möchten Sie eine Ansage erstellen (wenn Sie z. B. Anrufe an ein bestimmtes Ziel durchstellen möchten, ohne eine Nachricht wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="dcbf4-109">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="dcbf4-110">Weisen Sie die neue Ansage einem Nummernbereich in der Tabelle nicht zugewiesener Nummern zu.</span><span class="sxs-lookup"><span data-stu-id="dcbf4-110">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="dcbf4-111">In diesem Abschnitt wird beschrieben, wie Ansagen importiert und erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="dcbf4-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="dcbf4-112">Details zum Zuweisen von Ankündigungen in der Tabelle "nicht zugewiesene Nummern" finden Sie unter [Konfigurieren der Tabelle "nicht zugewiesene Nummern" in lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span><span class="sxs-lookup"><span data-stu-id="dcbf4-112">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="dcbf4-113">So erstellen Sie eine neue Ansage</span><span class="sxs-lookup"><span data-stu-id="dcbf4-113">To create a new announcement</span></span>

1.  <span data-ttu-id="dcbf4-114">Erstellen Sie die Audiodatei für Audioansagen.</span><span class="sxs-lookup"><span data-stu-id="dcbf4-114">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="dcbf4-115">Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dcbf4-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="dcbf4-116">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="dcbf4-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="dcbf4-117">Führen Sie für Audioansagen folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dcbf4-117">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="dcbf4-118">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dcbf4-118">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="dcbf4-p103">Zum Durchstellen von Anrufen an die Voicemail geben Sie „SIPAddress“ im Format „sip:Benutzername@Domänenname;opaque=app:voicemail“ ein (Beispiel: sip:bob@contoso.com;opaque=app:voicemail). Zum Durchstellen von Anrufen an eine Telefonnummer geben Sie „SIPAddress“ im Format „sip:Nummer@Domänenname;user=phone“ ein (Beispiel: sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="dcbf4-p103">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="dcbf4-121">Beispiel für die Festlegung einer Audioansage:</span><span class="sxs-lookup"><span data-stu-id="dcbf4-121">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="dcbf4-122">Beispiel für die Festlegung einer TTS-Ansage:</span><span class="sxs-lookup"><span data-stu-id="dcbf4-122">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="dcbf4-123">Ausführliche Informationen zu diesen Cmdlets sowie eine Liste der Sprachcodes, die im **TextToSpeechPrompt** -Parameter verwendet werden können, finden Sie unter [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span><span class="sxs-lookup"><span data-stu-id="dcbf4-123">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dcbf4-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcbf4-124">See Also</span></span>


[<span data-ttu-id="dcbf4-125">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="dcbf4-125">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="dcbf4-126">Neu – CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="dcbf4-126">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="dcbf4-127">Konfigurieren der Tabelle nicht zugewiesener Nummern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcbf4-127">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


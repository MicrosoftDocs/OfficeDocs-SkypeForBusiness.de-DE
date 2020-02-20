---
title: 'Lync Server 2013: Erstellen einer Ansage'
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
ms.openlocfilehash: ec4384457ae0121893f0413d674368877e5396f4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="10c6a-102">Erstellen einer Ansage in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10c6a-102">Create an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10c6a-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="10c6a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="10c6a-104">Zum Erstellen einer neuen Ansage müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="10c6a-104">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="10c6a-105">Für Audioansagen zeichnen Sie die Audiodatei mithilfe Ihrer bevorzugten audiorecording-Anwendung auf.</span><span class="sxs-lookup"><span data-stu-id="10c6a-105">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="10c6a-106">Führen Sie für Audioansagen das Cmdlet **Import-CsAnnouncementFile** aus, um den Inhalt der Audiodatei in Dateispeicher zu importieren.</span><span class="sxs-lookup"><span data-stu-id="10c6a-106">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="10c6a-107">Führen Sie das Cmdlet **New-CsAnnouncement** aus, um die Ansage zu erstellen und zu benennen.</span><span class="sxs-lookup"><span data-stu-id="10c6a-107">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="10c6a-108">Führen Sie diesen Schritt aus, um Ankündigungen mit einer Eingabeaufforderung, einer TTS-Ansage (Text-to-Speech) oder keine Eingabeaufforderung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10c6a-108">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="10c6a-109">Möglicherweise möchten Sie eine Ansage ohne Eingabeaufforderung erstellen (beispielsweise, wenn Sie Anrufe an ein bestimmtes Ziel übertragen möchten, ohne eine Nachricht wiedergeben zu müssen).</span><span class="sxs-lookup"><span data-stu-id="10c6a-109">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="10c6a-110">Weisen Sie die neue Ansage einem Nummernbereich in der Tabelle nicht zugewiesener Nummern zu.</span><span class="sxs-lookup"><span data-stu-id="10c6a-110">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="10c6a-111">In diesem Thema wird das Importieren und Erstellen von Ankündigungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="10c6a-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="10c6a-112">Ausführliche Informationen zum Zuweisen von Ankündigungen in der Tabelle nicht zugewiesene Nummern finden Sie unter [Konfigurieren der Tabelle nicht zugewiesene Nummern in lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span><span class="sxs-lookup"><span data-stu-id="10c6a-112">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="10c6a-113">So erstellen Sie eine neue Ansage</span><span class="sxs-lookup"><span data-stu-id="10c6a-113">To create a new announcement</span></span>

1.  <span data-ttu-id="10c6a-114">Erstellen Sie für Audioansagen die Audiodatei.</span><span class="sxs-lookup"><span data-stu-id="10c6a-114">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="10c6a-115">Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="10c6a-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="10c6a-116">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="10c6a-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="10c6a-117">Führen Sie für Audioansagen Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="10c6a-117">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="10c6a-118">Ausführen</span><span class="sxs-lookup"><span data-stu-id="10c6a-118">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="10c6a-119">Geben Sie SIPAddress im Format SIP: username@Domainname; Opaque = App: Voicemail ein (beispielsweise SIP: Bob@contoso. com; Opaque = App: Voicemail), um Anrufe an Voicemail weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="10c6a-119">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail).</span></span> <span data-ttu-id="10c6a-120">Geben Sie zum Übertragen von Anrufen an eine Telefonnummer SIPAddress im Format SIP: Number@Domainname; User = Phone ein (beispielsweise SIP: + 14255550121@contoso. com; User = Phone).</span><span class="sxs-lookup"><span data-stu-id="10c6a-120">For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="10c6a-121">Beispielsweise zum Angeben einer Audioansage:</span><span class="sxs-lookup"><span data-stu-id="10c6a-121">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="10c6a-122">Geben Sie beispielsweise eine TTS-Eingabeaufforderung an:</span><span class="sxs-lookup"><span data-stu-id="10c6a-122">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="10c6a-123">Weitere Details zu diesen Cmdlets und eine Liste der Sprachcodes, die im Parameter **TextToSpeechPrompt** verwendet werden sollen, finden Sie unter [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span><span class="sxs-lookup"><span data-stu-id="10c6a-123">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10c6a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10c6a-124">See Also</span></span>


[<span data-ttu-id="10c6a-125">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="10c6a-125">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="10c6a-126">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="10c6a-126">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="10c6a-127">Konfigurieren der Tabelle nicht zugewiesener Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10c6a-127">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Skype Room System – Lokale Bereitstellungen mit einzelner Gesamtstruktur
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System in einer lokalen Umgebung mit einer einzelnen Gesamtstruktur bereitgestellt wird.
ms.openlocfilehash: 2d73ee2313088c653f4362139cb431e55d92015b
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775263"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="145f2-103">Skype Room System – Lokale Bereitstellungen mit einzelner Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="145f2-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="145f2-104">Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System in einer lokalen Umgebung mit einer einzelnen Gesamtstruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="145f2-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="145f2-105">Dieser Abschnitt enthält eine Übersicht über die Schritte zum Bereitstellen des Skype Room-System Kontos auf Exchange Server und von Skype for Business Server, die in einer lokalen Bereitstellung einer einzelnen Gesamtstruktur gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="145f2-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="145f2-106">Lokale Bereitstellungen mit einzelner Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="145f2-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="145f2-107">Wenn Sie bereits über ein Ressourcen Postfachkonto für den Konferenzraum verfügen, können Sie es verwenden.</span><span class="sxs-lookup"><span data-stu-id="145f2-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="145f2-108">Andernfalls müssen Sie eine neue erstellen.</span><span class="sxs-lookup"><span data-stu-id="145f2-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="145f2-109">Sie können entweder die Exchange-Verwaltungsshell (PowerShell) oder die Exchange-Verwaltungskonsole verwenden, um ein neues Ressourcen Postfachkonto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="145f2-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="145f2-110">Wir empfehlen die Verwendung eines neuen Ressourcenpostfachs (altes Postfach löschen und neu erstellen) für das Skype Room-System.</span><span class="sxs-lookup"><span data-stu-id="145f2-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="145f2-111">Stellen Sie sicher, dass Sie die Postfachdaten sichern, bevor Sie Sie löschen und dann mit dem Outlook-Client wieder in das neu erstellte Postfach exportieren (Weitere Informationen finden Sie unter Exportieren oder Sichern von Nachrichten, Kalendern, Aufgaben und Kontakten).</span><span class="sxs-lookup"><span data-stu-id="145f2-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="145f2-112">Informationen zum Wiederherstellen der verloren gegangenen Besprechungen durch Löschen des Postfachs finden Sie unter [verbinden oder Wiederherstellen eines gelöschten Postfachs](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="145f2-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="145f2-113">Befolgen Sie die unten aufgeführten Schritte, um ein vorhandenes Ressourcenpostfachkonto (z. B. LRS-01) zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="145f2-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="145f2-114">Führen Sie den folgenden PowerShell-Befehl für die Exchange-Verwaltung aus:</span><span class="sxs-lookup"><span data-stu-id="145f2-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="145f2-115">Wenn Sie planen, ein neues Postfach zu erstellen, führen Sie für eine lokale Exchange-Organisation mit einer einzelnen Gesamtstruktur folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="145f2-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="145f2-p102">Im Beispiel oben werden ein aktiviertes Benutzerkonto in Active Directory und ein Raum-Postfach für einen Konferenzraum in einer lokalen Exchange-Organisation erstellt. Der Parameter „RoomMailboxPassword“ gibt das Kennwort für das Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="145f2-p102">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization. The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="145f2-118">Konfigurieren Sie das Konto so, dass Konflikte automatisch aufgelöst werden, indem Sie Besprechungen annehmen/ablehnen.</span><span class="sxs-lookup"><span data-stu-id="145f2-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="145f2-119">Skype Room-System ausgestattete Konferenzraum Konten in Exchange können von Einzelpersonen verwaltet werden, beachten Sie jedoch, dass die Person, die eine Besprechung annimmt, nicht im Skype Room System-Startbildschirm Kalender angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="145f2-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="145f2-120">Eine vollständige Auflistung verfügbarer Befehle finden Sie unter „Set-CalendarProcessing“.</span><span class="sxs-lookup"><span data-stu-id="145f2-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="145f2-121">Führen Sie den folgenden Befehl aus, um die Besprechungsorganisatoren daran zu erinnern, dass Sie eine Online-Skype for Business-Besprechung in Outlook führen, um einen QuickInfo für das neue Konto einzurichten:</span><span class="sxs-lookup"><span data-stu-id="145f2-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="145f2-122">Verwenden Sie die folgenden Befehle, um lokalisierte Meldungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="145f2-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="145f2-123">Sofern es für Ihr Unternehmen erforderlich ist, können Sie angepasste Übersetzungen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="145f2-123">If required by your organization, you can also add custom translations:</span></span> 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="145f2-124">Optional: Konfigurieren von Besprechungs Akzeptanz Text, der Benutzern Informationen zu Skype for Business-Besprechungsräumen bietet und was Sie erwarten können, wenn Sie Besprechungen planen und daran teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="145f2-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="145f2-125">Prüfen des Ressourcenpostfachkontos in Active Directory</span><span class="sxs-lookup"><span data-stu-id="145f2-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="145f2-126">Das von Exchange in Schritt 1 erstellte Konferenzraum-Postfachkonto kann ein deaktiviertes Benutzerobjekt in Active Directory sein.</span><span class="sxs-lookup"><span data-stu-id="145f2-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="145f2-127">Wenn das Konto in Active Directory deaktiviert ist, kann sich das Skype Room-System nicht mit der Kerberos/NTLM-Authentifizierung anmelden oder authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="145f2-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="145f2-128">Der Skype Room-System Client muss sich gegen Exchange-Webdienste authentifizieren können, um Kalendereinstellungen abzurufen, und muss außerdem in der Lage sein, e-Mails mit Whiteboard-Inhalten zu senden.</span><span class="sxs-lookup"><span data-stu-id="145f2-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="145f2-129">Deshalb gilt: Wenn das Konto deaktiviert ist, müssen Sie das Konto in Active Directory aktivieren. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="145f2-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="145f2-130">Führen Sie in Active Directory den folgenden Befehl aus, um die Kontoanmeldung zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="145f2-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="145f2-131">Wenn Sie diesen Befehl ausführen, werden Sie zur Eingabe des aktuellen Kennworts und anschließend zur erneuten zweifachen Eingabe des Kennworts zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="145f2-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="145f2-132">Führen Sie, nachdem das Kennwort festgelegt worden ist, den folgenden Befehl aus, um das Konto zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="145f2-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="145f2-133">Aktivieren von Skype Room-System Konten für Skype for Business</span><span class="sxs-lookup"><span data-stu-id="145f2-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="145f2-134">Dieser Abschnitt enthält eine Übersicht über die Schritte, die erforderlich sind, um Skype for Business für Ihr Konferenzraum Konto zu aktivieren, das auf dem Skype Room-System konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="145f2-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="145f2-135">Nachdem Sie ein Ressourcen Postfachkonto für die Konferenzräume erstellt haben, verwenden Sie die Skype for Business Server-Verwaltungsshell zum Aktivieren von Skype Room-System Konten für Skype for Business-Dienste.</span><span class="sxs-lookup"><span data-stu-id="145f2-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="145f2-136">Im folgenden Verfahren wird davon ausgegangen, dass Sie das Skype Room-System Konto in Active Directory aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="145f2-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="145f2-137">Führen Sie den folgenden Befehl aus, um das Skype Room-System Konto in einem Skype for Business Server-Pool zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="145f2-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="145f2-138">Optional: Erlauben Sie, dass dieses Konto Festnetzanrufe tätigt und empfängt, indem Sie das Konto für Enterprise-VoIP aktivieren.</span><span class="sxs-lookup"><span data-stu-id="145f2-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="145f2-139">Enterprise-VoIP ist für das Skype Room System nicht erforderlich, wenn Sie es aber nicht für Enterprise-VoIP aktivieren, kann der Skype Room-System Client keine PSTN-Wählfunktionen bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="145f2-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="145f2-140">Wenn Sie Enterprise-VoIP für das Skype Room System-Konferenzraum Konto aktivieren, stellen Sie sicher, dass Sie eine für Ihre Organisation geeignete Richtlinie für eingeschränkte VoIP konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="145f2-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="145f2-141">Wenn es sich bei dem Skype for Business-Besprechungsraum um eine öffentlich verfügbare Ressource handelt, kann jeder Teilnehmer an einer Besprechung teilnehmen, entweder geplant oder Ad-hoc.</span><span class="sxs-lookup"><span data-stu-id="145f2-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="145f2-142">Nach dem Beitritt zu einer Besprechung kann die Person beliebige Nummern anwählen.</span><span class="sxs-lookup"><span data-stu-id="145f2-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="145f2-143">In Skype for Business Server verwendet das Feature für die Auswahl von Konferenzen die VoIP-Richtlinie des Benutzers, in diesem Fall das Skype Room-System Konto, das für die Teilnahme an der Besprechung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="145f2-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="145f2-144">In früheren Versionen von Lync Server wird die VoIP-Richtlinie des Organisators verwendet.</span><span class="sxs-lookup"><span data-stu-id="145f2-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="145f2-145">Wenn ein Benutzer einer früheren Version von lync Server einen Besprechungsraum plant und das Skype Room-System Raum Konto einlädt, könnte jeder Nutzer den Skype for Business-Besprechungsraum nutzen, um an der Besprechung teilzunehmen und ein beliebiges nationales/regionales oder internationales Telefon zu wählen. Nummer, solange der Organisator diese Nummern anrufen darf.</span><span class="sxs-lookup"><span data-stu-id="145f2-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  


---
title: Skype Room System – Lokale Bereitstellungen mit einzelner Gesamtstruktur
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System in einer lokalen Umgebung mit einer einzelnen Gesamtstruktur bereitgestellt wird.
ms.openlocfilehash: a0c3f76d94e54c616068303a08e4e4254f5f8347
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375301"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="4046e-103">Skype Room System – Lokale Bereitstellungen mit einzelner Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="4046e-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="4046e-104">Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System in einer lokalen Umgebung mit einer einzelnen Gesamtstruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4046e-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="4046e-105">Dieser Abschnitt enthält eine Übersicht über die Schritte für die Bereitstellung von Skype Raum Systemkonto auf Exchange-Server und Skype für Business Server in einer einzelnen Gesamtstruktur lokale Bereitstellung gehostet.</span><span class="sxs-lookup"><span data-stu-id="4046e-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="4046e-106">Lokale Bereitstellungen mit einzelner Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="4046e-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="4046e-107">Wenn Sie bereits über ein Postfach Ressourcenkonto für den Live Meeting-Raum verfügen, können Sie es.</span><span class="sxs-lookup"><span data-stu-id="4046e-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="4046e-108">Andernfalls müssen Sie einen neuen Anwendungspool erstellen.</span><span class="sxs-lookup"><span data-stu-id="4046e-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="4046e-109">Exchange-Verwaltungsshell (PowerShell) oder Exchange-Verwaltungskonsole können Sie um ein neues Postfach Ressourcenkonto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4046e-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="4046e-110">Es wird empfohlen, einen neuen (alte Postfach löschen und Neuerstellen) Ressourcenpostfach für Skype Raum System.</span><span class="sxs-lookup"><span data-stu-id="4046e-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="4046e-111">Stellen Sie sicher, dass Sie Postfachdaten sichern, vor dem Löschen und anschließend wieder auf das neu erstellte Postfach mithilfe des Outlook-Clients zu exportieren (Siehe Exportieren oder Sichern von Nachrichten, Kalender, Aufgaben und Kontakte Weitere Informationen).</span><span class="sxs-lookup"><span data-stu-id="4046e-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="4046e-112">Informationen zum Wiederherstellen von Besprechungen verloren durch Löschen des Postfachs finden Sie unter [Connect- oder Wiederherstellen eines gelöschten Postfachs](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="4046e-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="4046e-113">Befolgen Sie die unten aufgeführten Schritte, um ein vorhandenes Ressourcenpostfachkonto (z. B. LRS-01) zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="4046e-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="4046e-114">Führen Sie den folgenden PowerShell-Befehl für die Exchange-Verwaltung aus:</span><span class="sxs-lookup"><span data-stu-id="4046e-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="4046e-115">Wenn Sie planen, ein neues Postfach zu erstellen, führen Sie für eine lokale Exchange-Organisation mit einer einzelnen Gesamtstruktur folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="4046e-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="4046e-p102">Im Beispiel oben werden ein aktiviertes Benutzerkonto in Active Directory und ein Raum-Postfach für einen Konferenzraum in einer lokalen Exchange-Organisation erstellt. Der Parameter „RoomMailboxPassword“ gibt das Kennwort für das Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="4046e-p102">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization. The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="4046e-118">Konfigurieren Sie das Konto zum Lösen von Konflikten automatisch von Besprechungen akzeptieren/ablehnen.</span><span class="sxs-lookup"><span data-stu-id="4046e-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="4046e-119">Skype Raum System ausgestattet Konferenzraum-Konten in Exchange Personen verwaltet werden können, aber beachten Sie, bis der betroffenen eine Besprechung akzeptiert er nicht im Kalender des Skype Raum System Startseite angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4046e-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="4046e-120">Eine vollständige Auflistung verfügbarer Befehle finden Sie unter „Set-CalendarProcessing“.</span><span class="sxs-lookup"><span data-stu-id="4046e-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="4046e-121">Führen den folgenden Befehl So richten Sie eine e-Mail-Info für das neue Konto ein, um Besprechungsorganisatoren, stellen Sie die Besprechung erinnern ein online Skype für Business Besprechung in Outlook:</span><span class="sxs-lookup"><span data-stu-id="4046e-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="4046e-p104">Verwenden Sie die folgenden Befehle, um lokalisierte Meldungen zu konfigurieren. Sofern es für Ihr Unternehmen erforderlich ist, können Sie angepasste Übersetzungen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="4046e-p104">Use the following commands to configure localized strings. If required by your organization, you can also add custom translations:</span></span> 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="4046e-124">Optional: Konfigurieren meeting Annahme Text, der ermöglicht es Benutzern Informationen über Skype für Business Besprechungsraum und was Sie erwartet, wenn sie planen und teilnehmen an Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="4046e-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="4046e-125">Prüfen des Ressourcenpostfachkontos in Active Directory</span><span class="sxs-lookup"><span data-stu-id="4046e-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="4046e-126">Die Konferenz Raum Postfach von Exchange oben in Schritt 1 erstellte möglicherweise ein deaktiviertes Benutzerobjekt in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4046e-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="4046e-127">Skype-Chatroom-System nicht anmelden oder authentifizieren mithilfe von Kerberos/NTLM-Authentifizierung, wenn das Konto in Active Directory deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4046e-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="4046e-128">Der Client Skype Raum System muss in der Lage, Exchange-Webdienste zum Abrufen von kalendereinstellungen authentifizieren und muss auch Senden von e-Mails mit Whiteboard-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="4046e-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="4046e-129">Deshalb gilt: Wenn das Konto deaktiviert ist, müssen Sie das Konto in Active Directory aktivieren. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="4046e-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="4046e-130">Führen Sie in Active Directory den folgenden Befehl aus, um die Kontoanmeldung zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="4046e-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="4046e-131">Wenn Sie diesen Befehl ausführen, werden Sie zur Eingabe des aktuellen Kennworts und anschließend zur erneuten zweifachen Eingabe des Kennworts zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4046e-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="4046e-132">Führen Sie, nachdem das Kennwort festgelegt worden ist, den folgenden Befehl aus, um das Konto zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="4046e-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="4046e-133">Aktivieren von Skype Raum System Benutzerkonten für Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="4046e-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="4046e-134">Dieser Abschnitt enthält eine Übersicht über die erforderlichen Schritte zum Skype für Unternehmen für Ihre Konferenz Raum aktivieren auf Skype Raum System konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4046e-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="4046e-135">Nachdem ein Postfach Ressourcenkonto für die Konferenzen Räume erstellt wurde, verwenden Sie Skype für Business Server-Verwaltungsshell, um Skype Raum Systemkonten für Skype für BusinessServices zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4046e-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4046e-136">Das folgende Verfahren wird davon ausgegangen, dass Sie das Systemkonto von Skype Raum in Active Directory aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="4046e-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="4046e-137">Führen Sie den folgenden Befehl aus, um das Systemkonto von Skype Raum auf einen Skype für Business Server-Pool zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="4046e-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="4046e-138">Optional: Erlauben Sie, dass dieses Konto Festnetzanrufe tätigt und empfängt, indem Sie das Konto für Enterprise-VoIP aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4046e-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="4046e-139">Enterprise-VoIP ist nicht erforderlich für Skype Raum System, aber wenn Sie es nicht für Enterprise-VoIP aktivieren, der Skype Raum System Client nicht möglich PSTN-Einwahl-Funktionalität bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="4046e-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="4046e-140">Wenn Sie Enterprise-VoIP für das Skype Raum Konferenz Raum Systemkonto aktivieren, stellen Sie sicher, so konfigurieren Sie eine eingeschränkte VoIP-Richtlinie für Ihre Organisation geeignet.</span><span class="sxs-lookup"><span data-stu-id="4046e-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="4046e-141">Wenn die Skype für Business Besprechungsraum eine öffentlich zugängliche Ressource ist, können damit alle Benutzer teilnehmen an einer Besprechung, entweder geplant oder spontan.</span><span class="sxs-lookup"><span data-stu-id="4046e-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="4046e-142">Nach dem Beitritt zu einer Besprechung kann die Person beliebige Nummern anwählen.</span><span class="sxs-lookup"><span data-stu-id="4046e-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="4046e-143">In Skype für Business Server verwendet die Anwahl von Konferenzen-Funktion die VoIP-Richtlinie des Benutzers, in diesem Fall das Skype Raum Systemkonto verwendet wird, an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="4046e-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="4046e-144">In früheren Versionen von Lync Server wird die VoIP-Richtlinie des Organisators verwendet.</span><span class="sxs-lookup"><span data-stu-id="4046e-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="4046e-145">Aus diesem Grund, wenn ein Benutzer von einer früheren Version von Lync Server einen Besprechungsraum plant und das Systemkonto Skype Raum Raum lädt, jeder konnte die Skype für Business Besprechungsraum verwenden, um an der Besprechung teilzunehmen und wählen Sie ein beliebiges Telefon nationale/regionale und internationale konnte Anzahl, solange der Organisator So wählen Sie diese Nummern zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="4046e-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  


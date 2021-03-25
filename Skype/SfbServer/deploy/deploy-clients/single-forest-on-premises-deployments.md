---
title: Lokale Bereitstellungen für einzelne Gesamtstrukturen im Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: In diesem Thema erfahren Sie, wie Sie Skype Room System in einer lokalen Gesamtstruktur bereitstellen.
ms.openlocfilehash: df213b24ef3400aa5551a090d2dd218d05794988
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120324"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Lokale Bereitstellungen für einzelne Gesamtstrukturen im Skype Room System
 
In diesem Thema erfahren Sie, wie Sie Skype Room System in einer lokalen Gesamtstruktur bereitstellen.
  
Dieser Abschnitt enthält eine Übersicht über die Schritte zum Bereitstellen des Skype Room System-Kontos auf Exchange Server und Skype for Business Server, die in einer lokalen Bereitstellung einer einzelnen Gesamtstruktur gehostet werden.
  
## <a name="single-forest-on-premises-deployments"></a>Lokale Bereitstellungen mit einer einzelnen Gesamtstruktur

Wenn Sie bereits über ein Ressourcenpostfachkonto für den Konferenzraum verfügen, können Sie es verwenden. Andernfalls müssen Sie eine neue erstellen. Sie können entweder die Exchange-Verwaltungsshell (PowerShell) oder Exchange-Verwaltungskonsole, um ein neues Ressourcenpostfachkonto zu erstellen. Es wird empfohlen, ein neues Ressourcenpostfach für Skype Room System zu verwenden (altes Postfach löschen und neu erstellen). Stellen Sie sicher, dass Sie Postfachdaten sichern, bevor Sie sie löschen, und exportieren Sie sie dann mithilfe des Outlook-Clients wieder in das neu erstellte Postfach (weitere Informationen finden Sie unter Exportieren oder Sichern von Nachrichten, Kalendern, Aufgaben und Kontakten). Informationen zum Wiederherstellen der Besprechungen, die durch Löschen des Postfachs verloren gehen, finden Sie unter [Verbinden oder Wiederherstellen eines gelöschten Postfachs.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
Führen Sie die folgenden Schritte aus, um ein vorhandenes Ressourcenpostfachkonto (z. B. LRS-01) zu verwenden:
  
1. Führen Sie den folgenden Exchange-Verwaltungs-PowerShell-Befehl aus:
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Wenn Sie ein neues Postfach erstellen möchten, führen Sie für eine lokale Exchange-Gesamtstruktur den folgenden Befehl aus:
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Im obigen Beispiel werden ein aktiviertes Benutzerkonto in Active Directory und ein Raumpostfach für einen Konferenzraum in einer lokalen Exchange-Organisation erstellt. Der Parameter RoomMailboxPassword gibt das Kennwort für das Benutzerkonto an.
    
3. Konfigurieren Sie das Konto, um Konflikte automatisch zu lösen, indem Sie Besprechungen akzeptieren/ablehnen. Mit dem Skype Room System ausgestattete Konferenzraumkonten in Exchange können von Einzelpersonen verwaltet werden, beachten Sie jedoch, dass sie nicht im Skype Room System-Startbildschirmkalender angezeigt werden, bis die Person eine Besprechung akzeptiert.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Eine vollständige Reihe verfügbarer Befehle finden Sie unter Set-CalendarProcessing.
    
   Führen Sie den folgenden Befehl aus, um Besprechungsorganisatoren daran zu erinnern, die Besprechung zu einer Skype for Business-Online-Besprechung in Outlook zu machen, um eine E-Mail-Tip für das neue Konto zu erstellen: 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Verwenden Sie die folgenden Befehle, um lokalisierte Zeichenfolgen zu konfigurieren. Falls von Ihrer Organisation erforderlich, können Sie auch benutzerdefinierte Übersetzungen hinzufügen: 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Optional: Konfigurieren Sie den Text zur Besprechungsakzeptanz, der Benutzern Informationen zu Skype for Business Meeting Room sowie Informationen zum Planen und Beitreten zu Besprechungen bietet. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Überprüfen des Ressourcenpostfachkontos in Active Directory

Das von Exchange in Schritt 1 oben erstellte Konferenzraumpostfachkonto kann ein deaktiviertes Benutzerobjekt in Active Directory sein. Skype Room System kann sich nicht mithilfe der Kerberos/NTLM-Authentifizierung anmelden oder authentifizieren, wenn das Konto in Active Directory deaktiviert ist. Der Skype Room System-Client muss in der Lage sein, sich bei Exchange-Webdiensten zu authentifizieren, um Kalendereinstellungen abzurufen, und er muss auch in der Lage sein, E-Mails mit Whiteboardinhalten zu senden. 
  
Wenn das Konto deaktiviert ist, müssen Sie dieses Konto in Active Directory aktivieren, indem Sie die folgenden Schritte tun: 
  
1. Führen Sie in Active Directory den folgenden Befehl aus, um die Kontoprotokollierung zu aktivieren: 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   Wenn Sie diesen Befehl ausführen, werden Sie aufgefordert, das aktuelle Kennwort einzugeben und das Kennwort zweimal zur Bestätigung erneut einzugeben.
    
2. Führen Sie nach dem Festlegen des Kennworts den folgenden Befehl aus, um das Konto zu aktivieren: 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Aktivieren von Skype Room System Accounts for Skype for Business

Dieser Abschnitt enthält eine Übersicht über die Schritte, die zum Aktivieren von Skype for Business für Ihr Konferenzraumkonto erforderlich sind, das auf Skype Room System konfiguriert wird. 
  
Nachdem Sie ein Ressourcenpostfachkonto für die Konferenzräume erstellt haben, verwenden Sie die Skype for Business Server-Verwaltungsshell, um Skype Room System-Konten für Skype for Business-Dienste zu aktivieren.
  
> [!NOTE]
> Im folgenden Verfahren wird davon ausgegangen, dass Sie das Skype Room System-Konto in Active Directory aktiviert haben. 
  
1. Führen Sie den folgenden Befehl aus, um das Skype Room System-Konto in einem Skype for Business Server-Pool zu aktivieren:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Optional: Zulassen, dass dieses Konto PSTN-Telefonanrufe macht und erhält, indem das Konto für Enterprise-VoIP. Enterprise-VoIP ist für Skype Room System nicht erforderlich, aber wenn Sie es nicht für Enterprise-VoIP aktivieren, kann der Skype Room System-Client keine PSTN-Wählfunktionen bereitstellen:
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Wenn Sie Enterprise-VoIP für das Skype Room System-Konferenzraumkonto aktivieren, müssen Sie eine eingeschränkte Sprachrichtlinie konfigurieren, die für Ihre Organisation geeignet ist. Wenn der Skype for Business-Besprechungsraum eine öffentlich verfügbare Ressource ist, kann jeder sie verwenden, um an einer Besprechung teil zu nehmen, entweder geplant oder ad hoc. Nach der Teilnahme an einer Besprechung konnte die Person eine beliebige Nummer wählen. In Skype for Business Server verwendet die Funktion zum Einwählen von Konferenzen die Sprachrichtlinie des Benutzers, in diesem Fall das Skype Room System-Konto, das für die Teilnahme an der Besprechung verwendet wurde. In früheren Versionen von Lync Server wird die Voicerichtlinie des Organisators verwendet. Wenn ein Benutzer einer früheren Version von Lync Server einen Besprechungsraum plant und das Skype Room System-Raumkonto einlähmt, könnte daher jeder den Skype for Business-Besprechungsraum verwenden, um an der Besprechung teil zu nehmen, und eine beliebige nationale/regionale oder internationale Telefonnummer wählen, solange der Organisator diese Nummern wählen darf. 

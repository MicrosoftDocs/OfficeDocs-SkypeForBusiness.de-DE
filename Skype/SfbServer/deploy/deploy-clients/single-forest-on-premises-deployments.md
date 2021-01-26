---
title: Lokale Bereitstellungen mit einzelner Gesamtstruktur für Skype Room System
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
description: In diesem Thema erfahren Sie, wie Sie Skype Room System in einer lokalen Umgebung mit einer einzelnen Gesamtstruktur bereitstellen.
ms.openlocfilehash: 0449a5e909fa044df12766aec0a036bf97315386
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820755"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Lokale Bereitstellungen mit einzelner Gesamtstruktur für Skype Room System
 
In diesem Thema erfahren Sie, wie Sie Skype Room System in einer lokalen Umgebung mit einer einzelnen Gesamtstruktur bereitstellen.
  
Dieser Abschnitt enthält eine Übersicht über die Schritte zum Bereitstellen des Skype Room System-Kontos auf Exchange Server und Skype for Business Server, die in einer lokalen Bereitstellung mit einer einzelnen Gesamtstruktur gehostet werden.
  
## <a name="single-forest-on-premises-deployments"></a>Lokale Bereitstellungen mit einer einzelnen Gesamtstruktur

Wenn Sie bereits über ein Ressourcenpostfachkonto für den Konferenzraum verfügen, können Sie es verwenden. Andernfalls müssen Sie ein neues erstellen. Sie können entweder die Exchange-Verwaltungsshell (PowerShell) oder Exchange-Verwaltungskonsole, um ein neues Ressourcenpostfachkonto zu erstellen. Es wird empfohlen, ein neues Ressourcenpostfach für Skype Room System zu verwenden (altes Postfach löschen und neu erstellen). Stellen Sie sicher, dass Sie Postfachdaten sichern, bevor Sie sie löschen, und exportieren Sie sie dann mithilfe des Outlook-Clients zurück in das neu erstellte Postfach (weitere Informationen finden Sie unter "Exportieren oder Sichern von Nachrichten, Kalendern, Aufgaben und Kontakten"). Informationen zum Wiederherstellen der durch das Löschen des Postfachs verlorenen Besprechungen finden Sie unter [Verbinden oder Wiederherstellen eines gelöschten Postfachs.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx) 
  
Führen Sie die folgenden Schritte aus, um ein vorhandenes Ressourcenpostfachkonto (z. B. LRS-01) zu verwenden:
  
1. Führen Sie den folgenden Exchange-Verwaltungs-PowerShell-Befehl aus:
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Wenn Sie ein neues Postfach erstellen möchten, führen Sie für eine lokale Exchange-Organisation mit einer einzelnen Gesamtstruktur den folgenden Befehl aus:
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Im obigen Beispiel werden ein aktiviertes Benutzerkonto in Active Directory und ein Raumpostfach für einen Konferenzraum in einer lokalen Exchange-Organisation erstellt. Der Parameter RoomMailboxPassword gibt das Kennwort für das Benutzerkonto an.
    
3. Konfigurieren Sie das Konto, um Konflikte automatisch zu lösen, indem Sie Besprechungen akzeptieren/ablehnen. Mit Skype Room System ausgestattete Konferenzraumkonten in Exchange können von Einzelpersonen verwaltet werden. Beachten Sie jedoch, dass die Person, bis sie eine Besprechung annimmt, nicht im Startbildschirmkalender von Skype Room System angezeigt wird.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Eine vollständige Reihe verfügbarer Befehle finden Sie unter "Set-CalendarProcessing".
    
   Um Besprechungsorganisatoren daran zu erinnern, die Besprechung zu einer Online-Skype for Business-Besprechung in Outlook zu machen, führen Sie den folgenden Befehl aus, um eine E-Mail-Tip für das neue Konto einrichten: 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Verwenden Sie die folgenden Befehle, um lokalisierte Zeichenfolgen zu konfigurieren. Wenn dies für Ihre Organisation erforderlich ist, können Sie auch benutzerdefinierte Übersetzungen hinzufügen: 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Optional: Konfigurieren Sie den Text zur Besprechungsakzeptanz, der Benutzern Informationen über den Skype for Business-Besprechungsraum bietet und was sie beim Planen und Teilnehmen an Besprechungen erwarten können. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Überprüfen des Ressourcenpostfachkontos in Active Directory

Das postfachkonto des Konferenzraums, das von Exchange in Schritt 1 erstellt wurde, ist möglicherweise ein deaktiviertes Benutzerobjekt in Active Directory. Skype Room System kann sich nicht mithilfe der Kerberos/NTLM-Authentifizierung anmelden oder authentifizieren, wenn das Konto in Active Directory deaktiviert ist. Der Skype Room System-Client muss in der Lage sein, sich bei den Exchange-Webdiensten zu authentifizieren, um Kalendereinstellungen abzurufen, und muss auch in der Lage sein, E-Mails mit Whiteboardinhalten zu senden. 
  
Wenn das Konto deaktiviert ist, müssen Sie dieses Konto daher wie folgt in Active Directory aktivieren: 
  
1. Führen Sie in Active Directory den folgenden Befehl aus, um die Kontoprotokollierung zu aktivieren: 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   Wenn Sie diesen Befehl ausführen, werden Sie aufgefordert, das aktuelle Kennwort einzugeben und das Kennwort zweimal zur Bestätigung erneut einzugeben.
    
2. Führen Sie nach dem Festlegen des Kennworts den folgenden Befehl aus, um das Konto zu aktivieren: 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Aktivieren von Skype Room System Accounts für Skype for Business

Dieser Abschnitt enthält eine Übersicht über die erforderlichen Schritte zum Aktivieren von Skype for Business für Ihr Konferenzraumkonto, das in Skype Room System konfiguriert wird. 
  
Nachdem Sie ein Ressourcenpostfachkonto für die Konferenzräume erstellt haben, verwenden Sie die Skype for Business Server-Verwaltungsshell, um Skype Room System-Konten für Skype for Business-Dienste zu aktivieren.
  
> [!NOTE]
> Bei dem folgenden Verfahren wird davon ausgegangen, dass Sie das Skype Room System-Konto in Active Directory aktiviert haben. 
  
1. Führen Sie den folgenden Befehl aus, um das Skype Room System-Konto in einem Skype for Business Server-Pool zu aktivieren:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Optional: Lassen Sie zu, dass dieses Konto Festnetzanrufe macht und erhält, indem Sie das Konto für Enterprise-VoIP. Enterprise-VoIP für Skype Room System ist nicht erforderlich, aber wenn Sie es nicht für Enterprise-VoIP aktivieren, kann der Skype Room System-Client keine Wählfunktionen für das Festnetz bereitstellen:
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Wenn Sie Enterprise-VoIP Skype Room System-Konferenzraumkonto aktivieren, müssen Sie eine eingeschränkte Sprachrichtlinie konfigurieren, die für Ihre Organisation geeignet ist. Wenn es sich bei dem Skype for Business-Besprechungsraum um eine öffentlich verfügbare Ressource handelt, kann jeder sie für die Teilnahme an einer Besprechung verwenden, entweder geplant oder ad hoc. Nach der Teilnahme an einer Besprechung kann die Person eine beliebige Nummer wählen. In Skype for Business Server verwendet die Funktion zum Auswählen von Konferenzen die Sprachrichtlinie des Benutzers, in diesem Fall das Skype Room System-Konto, das für die Teilnahme an der Besprechung verwendet wurde. In früheren Versionen von Lync Server wird die Sprachrichtlinie des Organisators verwendet. Wenn ein Benutzer einer früheren Version von Lync Server einen Besprechungsraum plant und das Skype Room System -Raumkonto einlähmt, kann daher jeder den Skype for Business-Besprechungsraum verwenden, um an der Besprechung teil zu nehmen, und eine beliebige nationale/regionale oder internationale Telefonnummer wählen, solange der Organisator diese Nummern wählen darf. 
  


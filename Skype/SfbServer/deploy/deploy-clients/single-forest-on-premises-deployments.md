---
title: lokale Bereitstellungen Skype Raumsystem mit einzelner Gesamtstruktur
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: In diesem Thema erfahren Sie, wie Sie Skype Raumsystem in einer lokalen Umgebung mit einer einzigen Gesamtstruktur bereitstellen.
ms.openlocfilehash: 8093304ba538d67f64eb9f824033e9b4560fe976
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404437"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>lokale Bereitstellungen Skype Raumsystem mit einzelner Gesamtstruktur
 
In diesem Thema erfahren Sie, wie Sie Skype Raumsystem in einer lokalen Umgebung mit einer einzigen Gesamtstruktur bereitstellen.
  
Dieser Abschnitt enthält eine Übersicht über die Schritte zum Bereitstellen des Skype Raumsystemkontos auf Exchange Server und Skype for Business Server, die in einer lokalen Bereitstellung mit einer einzigen Gesamtstruktur gehostet werden.
  
## <a name="single-forest-on-premises-deployments"></a>Lokale Bereitstellungen mit einer einzelnen Gesamtstruktur

Wenn Sie bereits über ein Ressourcenpostfachkonto für den Konferenzraum verfügen, können Sie es verwenden. Andernfalls müssen Sie ein neues erstellen. Sie können entweder Exchange Verwaltungsshell (PowerShell) oder Exchange-Verwaltungskonsole verwenden, um ein neues Ressourcenpostfachkonto zu erstellen. Wir empfehlen die Verwendung eines neuen Ressourcenpostfachs (altes Postfach löschen und neu erstellen) für Skype Raumsystem. Stellen Sie sicher, dass Sie Postfachdaten sichern, bevor Sie sie löschen und dann mit dem Outlook-Client in das neu erstellte Postfach exportieren (weitere Informationen finden Sie unter Exportieren oder Sichern von Nachrichten, Kalendern, Aufgaben und Kontakten). Informationen zum Wiederherstellen der verlorenen Besprechungen durch Löschen des Postfachs finden Sie unter [Verbinden oder Wiederherstellen eines gelöschten Postfachs](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help). 
  
Führen Sie die folgenden Schritte aus, um ein vorhandenes Ressourcenpostfachkonto (z. B. LRS-01) zu verwenden:
  
1. Führen Sie den folgenden Exchange PowerShell-Befehl "Verwaltung" aus:
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Wenn Sie ein neues Postfach erstellen möchten, führen Sie für eine lokale Gesamtstruktur Exchange Organisation den folgenden Befehl aus:
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Im obigen Beispiel werden ein aktiviertes Benutzerkonto in Active Directory und ein Raumpostfach für einen Konferenzraum in einer lokalen Exchange Organisation erstellt. Der Parameter RoomMailboxPassword gibt das Kennwort für das Benutzerkonto an.
    
3. Konfigurieren Sie das Konto, um Konflikte automatisch zu lösen, indem Sie Besprechungen akzeptieren/ablehnen. Skype Raumsystem-konferenzraumkonten in Exchange können von Einzelpersonen verwaltet werden, beachten Sie jedoch, dass die Person, bis sie eine Besprechung akzeptiert, nicht im Skype Raumsystem-Startbildschirmkalender angezeigt wird.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Eine vollständige Reihe von verfügbaren Befehlen finden Sie unter "Set-CalendarProcessing".
    
   Um Besprechungsorganisatoren daran zu erinnern, die Besprechung zu einer Online-Skype for Business Besprechung in Outlook zu machen, führen Sie den folgenden Befehl aus, um eine E-Mail-Info für das neue Konto einzurichten: 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Verwenden Sie die folgenden Befehle, um lokalisierte Zeichenfolgen zu konfigurieren. Wenn dies von Ihrer Organisation erforderlich ist, können Sie auch benutzerdefinierte Übersetzungen hinzufügen: 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Optional: Konfigurieren Sie den Text für die Besprechungsakzeptanz, der Benutzern Informationen über Skype for Business Besprechungsraum und was sie beim Planen von und bei der Teilnahme an Besprechungen erwarten können. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Überprüfen des Ressourcenpostfachkontos in Active Directory

Das Postfachkonto des Konferenzraums, das von Exchange in Schritt 1 oben erstellt wurde, kann ein deaktiviertes Benutzerobjekt in Active Directory sein. Skype Room System kann sich nicht mithilfe der Kerberos/NTLM-Authentifizierung anmelden oder authentifizieren, wenn das Konto in Active Directory deaktiviert ist. Der Skype Room System-Client muss sich bei Exchange Webdiensten authentifizieren können, um Kalendereinstellungen abzurufen, und er muss auch in der Lage sein, E-Mails mit Whiteboard-Inhalten zu senden. 
  
Wenn das Konto deaktiviert ist, müssen Sie dieses Konto daher in Active Directory wie folgt aktivieren: 
  
1. Führen Sie in Active Directory den folgenden Befehl aus, um die Kontoanmeldung zu aktivieren: 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   Wenn Sie diesen Befehl ausführen, werden Sie aufgefordert, das aktuelle Kennwort einzugeben und das Kennwort dann zur Bestätigung erneut einzugeben.
    
2. Führen Sie nach dem Festlegen des Kennworts den folgenden Befehl aus, um das Konto zu aktivieren: 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Aktivieren von Skype Raumsystemkonten für Skype for Business

Dieser Abschnitt enthält eine Übersicht über die erforderlichen Schritte, um Skype for Business für Ihr Konferenzraumkonto zu aktivieren, das auf Skype Raumsystem konfiguriert wird. 
  
Nachdem Sie ein Ressourcenpostfachkonto für die Konferenzräume erstellt haben, verwenden Sie Skype for Business Server Verwaltungsshell, um Skype Raumsystemkonten für Skype for Business Dienste zu aktivieren.
  
> [!NOTE]
> Im folgenden Verfahren wird davon ausgegangen, dass Sie das Skype Room System-Konto in Active Directory aktiviert haben. 
  
1. Führen Sie den folgenden Befehl aus, um das Skype Room System-Konto in einem Skype for Business Server Pool zu aktivieren:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Optional: Zulassen, dass dieses Konto PSTN-Telefonanrufe tätigen und empfangen kann, indem Sie das Konto für Enterprise-VoIP aktivieren. Enterprise-VoIP ist für Skype Raumsystem nicht erforderlich. Wenn Sie es jedoch nicht für Enterprise-VoIP aktivieren, kann der Skype Raumsystemclient keine PSTN-Wählfunktionen bereitstellen:
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Wenn Sie Enterprise-VoIP für das Skype Room System-Konferenzraumkonto aktivieren, müssen Sie eine eingeschränkte VoIP-Richtlinie konfigurieren, die für Ihre Organisation geeignet ist. Wenn es sich bei dem Skype for Business Besprechungsraum um eine öffentlich verfügbare Ressource handelt, kann jeder diese verwenden, um an einer geplanten oder Ad-hoc-Besprechung teilzunehmen. Nach der Teilnahme an einer Besprechung konnte sich die Person an eine beliebige Nummer auswählen. In Skype for Business Server verwendet das Feature "Ausgehende Anrufe aus Konferenzen" die VoIP-Richtlinie des Benutzers, in diesem Fall das Skype Room System-Konto, das für die Teilnahme an der Besprechung verwendet wurde. In früheren Versionen von Lync Server wird die VoIP-Richtlinie des Organisators verwendet. Wenn ein Benutzer einer früheren Version von Lync Server einen Besprechungsraum plant und das Skype Raumsystemkonto einlädt, kann jeder die Skype for Business Besprechungsraum verwenden, um an der Besprechung teilzunehmen, und eine beliebige nationale/regionale oder internationale Telefonnummer wählen, solange der Organisator diese Nummern wählen darf. 

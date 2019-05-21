---
title: Skype Room System – Lokale Bereitstellungen mit einzelner Gesamtstruktur
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System in einer lokalen Umgebung mit einer einzelnen Gesamtstruktur bereitgestellt wird.
ms.openlocfilehash: 0eae077662b050ed2accb5869f1423e0a201a0d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287953"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype Room System – Lokale Bereitstellungen mit einzelner Gesamtstruktur
 
Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System in einer lokalen Umgebung mit einer einzelnen Gesamtstruktur bereitgestellt wird.
  
Dieser Abschnitt enthält eine Übersicht über die Schritte zum Bereitstellen des Skype Room-System Kontos auf Exchange Server und von Skype for Business Server, die in einer lokalen Bereitstellung einer einzelnen Gesamtstruktur gehostet werden.
  
## <a name="single-forest-on-premises-deployments"></a>Lokale Bereitstellungen mit einzelner Gesamtstruktur

Wenn Sie bereits über ein Ressourcen Postfachkonto für den Konferenzraum verfügen, können Sie es verwenden. Andernfalls müssen Sie eine neue erstellen. Sie können entweder die Exchange-Verwaltungsshell (PowerShell) oder die Exchange-Verwaltungskonsole verwenden, um ein neues Ressourcen Postfachkonto zu erstellen. Wir empfehlen die Verwendung eines neuen Ressourcenpostfachs (altes Postfach löschen und neu erstellen) für das Skype Room-System. Stellen Sie sicher, dass Sie die Postfachdaten sichern, bevor Sie Sie löschen und dann mit dem Outlook-Client wieder in das neu erstellte Postfach exportieren (Weitere Informationen finden Sie unter Exportieren oder Sichern von Nachrichten, Kalendern, Aufgaben und Kontakten). Informationen zum Wiederherstellen der verloren gegangenen Besprechungen durch Löschen des Postfachs finden Sie unter [verbinden oder Wiederherstellen eines gelöschten Postfachs](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Befolgen Sie die unten aufgeführten Schritte, um ein vorhandenes Ressourcenpostfachkonto (z. B. LRS-01) zu verwenden:
  
1. Führen Sie den folgenden PowerShell-Befehl für die Exchange-Verwaltung aus:
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Wenn Sie planen, ein neues Postfach zu erstellen, führen Sie für eine lokale Exchange-Organisation mit einer einzelnen Gesamtstruktur folgenden Befehl aus:
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Im Beispiel oben werden ein aktiviertes Benutzerkonto in Active Directory und ein Raum-Postfach für einen Konferenzraum in einer lokalen Exchange-Organisation erstellt. Der Parameter „RoomMailboxPassword“ gibt das Kennwort für das Benutzerkonto an.
    
3. Konfigurieren Sie das Konto so, dass Konflikte automatisch aufgelöst werden, indem Sie Besprechungen annehmen/ablehnen. Skype Room-System ausgestattete Konferenzraum Konten in Exchange können von Einzelpersonen verwaltet werden, beachten Sie jedoch, dass die Person, die eine Besprechung annimmt, nicht im Skype Room System-Startbildschirm Kalender angezeigt wird.
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Eine vollständige Auflistung verfügbarer Befehle finden Sie unter „Set-CalendarProcessing“.
    
   Führen Sie den folgenden Befehl aus, um die Besprechungsorganisatoren daran zu erinnern, dass Sie eine Online-Skype for Business-Besprechung in Outlook führen, um einen QuickInfo für das neue Konto einzurichten: 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Verwenden Sie die folgenden Befehle, um lokalisierte Meldungen zu konfigurieren. Sofern es für Ihr Unternehmen erforderlich ist, können Sie angepasste Übersetzungen hinzufügen: 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Optional: Konfigurieren von Besprechungs Akzeptanz Text, der Benutzern Informationen zu Skype for Business-Besprechungsräumen bietet und was Sie erwarten können, wenn Sie Besprechungen planen und daran teilnehmen. 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Prüfen des Ressourcenpostfachkontos in Active Directory

Das von Exchange in Schritt 1 erstellte Konferenzraum-Postfachkonto kann ein deaktiviertes Benutzerobjekt in Active Directory sein. Wenn das Konto in Active Directory deaktiviert ist, kann sich das Skype Room-System nicht mit der Kerberos/NTLM-Authentifizierung anmelden oder authentifizieren. Der Skype Room-System Client muss sich gegen Exchange-Webdienste authentifizieren können, um Kalendereinstellungen abzurufen, und muss außerdem in der Lage sein, e-Mails mit Whiteboard-Inhalten zu senden. 
  
Deshalb gilt: Wenn das Konto deaktiviert ist, müssen Sie das Konto in Active Directory aktivieren. Gehen Sie dazu wie folgt vor: 
  
1. Führen Sie in Active Directory den folgenden Befehl aus, um die Kontoanmeldung zu aktivieren: 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   Wenn Sie diesen Befehl ausführen, werden Sie zur Eingabe des aktuellen Kennworts und anschließend zur erneuten zweifachen Eingabe des Kennworts zur Bestätigung aufgefordert.
    
2. Führen Sie, nachdem das Kennwort festgelegt worden ist, den folgenden Befehl aus, um das Konto zu aktivieren: 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Aktivieren von Skype Room-System Konten für Skype for Business

Dieser Abschnitt enthält eine Übersicht über die Schritte, die erforderlich sind, um Skype for Business für Ihr Konferenzraum Konto zu aktivieren, das auf dem Skype Room-System konfiguriert wird. 
  
Nachdem Sie ein Ressourcen Postfachkonto für die Konferenzräume erstellt haben, verwenden Sie die Skype for Business Server-Verwaltungsshell zum Aktivieren von Skype Room-System Konten für Skype for Business-Dienste.
  
> [!NOTE]
> Im folgenden Verfahren wird davon ausgegangen, dass Sie das Skype Room-System Konto in Active Directory aktiviert haben. 
  
1. Führen Sie den folgenden Befehl aus, um das Skype Room-System Konto in einem Skype for Business Server-Pool zu aktivieren:
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Optional: Erlauben Sie, dass dieses Konto Festnetzanrufe tätigt und empfängt, indem Sie das Konto für Enterprise-VoIP aktivieren. Enterprise-VoIP ist für das Skype Room System nicht erforderlich, wenn Sie es aber nicht für Enterprise-VoIP aktivieren, kann der Skype Room-System Client keine PSTN-Wählfunktionen bereitstellen:
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Wenn Sie Enterprise-VoIP für das Skype Room System-Konferenzraum Konto aktivieren, stellen Sie sicher, dass Sie eine für Ihre Organisation geeignete Richtlinie für eingeschränkte VoIP konfigurieren. Wenn es sich bei dem Skype for Business-Besprechungsraum um eine öffentlich verfügbare Ressource handelt, kann jeder Teilnehmer an einer Besprechung teilnehmen, entweder geplant oder Ad-hoc. Nach dem Beitritt zu einer Besprechung kann die Person beliebige Nummern anwählen. In Skype for Business Server verwendet das Feature für die Auswahl von Konferenzen die VoIP-Richtlinie des Benutzers, in diesem Fall das Skype Room-System Konto, das für die Teilnahme an der Besprechung verwendet wurde. In früheren Versionen von Lync Server wird die VoIP-Richtlinie des Organisators verwendet. Wenn ein Benutzer einer früheren Version von lync Server einen Besprechungsraum plant und das Skype Room-System Raum Konto einlädt, könnte jeder Nutzer den Skype for Business-Besprechungsraum nutzen, um an der Besprechung teilzunehmen und ein beliebiges nationales/regionales oder internationales Telefon zu wählen. Nummer, solange der Organisator diese Nummern anrufen darf. 
  


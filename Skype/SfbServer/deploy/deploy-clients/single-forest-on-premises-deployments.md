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
ms.openlocfilehash: 8c931aca8505aa4d41175dbf5e1a138b668323d0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967905"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype Room System – Lokale Bereitstellungen mit einzelner Gesamtstruktur
 
Lesen Sie dieses Thema und erfahren Sie, wie Skype Room System in einer lokalen Umgebung mit einer einzelnen Gesamtstruktur bereitgestellt wird.
  
Dieser Abschnitt enthält eine Übersicht über die Schritte für die Bereitstellung von Skype Raum Systemkonto auf Exchange-Server und Skype für Business Server in einer einzelnen Gesamtstruktur lokale Bereitstellung gehostet.
  
## <a name="single-forest-on-premises-deployments"></a>Lokale Bereitstellungen mit einzelner Gesamtstruktur

Wenn Sie bereits über ein Postfach Ressourcenkonto für den Live Meeting-Raum verfügen, können Sie es. Andernfalls müssen Sie einen neuen Anwendungspool erstellen. Exchange-Verwaltungsshell (PowerShell) oder Exchange-Verwaltungskonsole können Sie um ein neues Postfach Ressourcenkonto zu erstellen. Es wird empfohlen, einen neuen (alte Postfach löschen und Neuerstellen) Ressourcenpostfach für Skype Raum System. Stellen Sie sicher, dass Sie Postfachdaten sichern, vor dem Löschen und anschließend wieder auf das neu erstellte Postfach mithilfe des Outlook-Clients zu exportieren (Siehe Exportieren oder Sichern von Nachrichten, Kalender, Aufgaben und Kontakte Weitere Informationen). Informationen zum Wiederherstellen von Besprechungen verloren durch Löschen des Postfachs finden Sie unter [Connect- oder Wiederherstellen eines gelöschten Postfachs](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
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
    
3. Konfigurieren Sie das Konto zum Lösen von Konflikten automatisch von Besprechungen akzeptieren/ablehnen. Skype Raum System ausgestattet Konferenzraum-Konten in Exchange Personen verwaltet werden können, aber beachten Sie, bis der betroffenen eine Besprechung akzeptiert er nicht im Kalender des Skype Raum System Startseite angezeigt wird.
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Eine vollständige Auflistung verfügbarer Befehle finden Sie unter „Set-CalendarProcessing“.
    
   Führen den folgenden Befehl So richten Sie eine e-Mail-Info für das neue Konto ein, um Besprechungsorganisatoren, stellen Sie die Besprechung erinnern ein online Skype für Business Besprechung in Outlook: 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Verwenden Sie die folgenden Befehle, um lokalisierte Meldungen zu konfigurieren. Sofern es für Ihr Unternehmen erforderlich ist, können Sie angepasste Übersetzungen hinzufügen: 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Optional: Konfigurieren meeting Annahme Text, der ermöglicht es Benutzern Informationen über Skype für Business Besprechungsraum und was Sie erwartet, wenn sie planen und teilnehmen an Besprechungen. 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Prüfen des Ressourcenpostfachkontos in Active Directory

Die Konferenz Raum Postfach von Exchange oben in Schritt 1 erstellte möglicherweise ein deaktiviertes Benutzerobjekt in Active Directory. Skype-Chatroom-System nicht anmelden oder authentifizieren mithilfe von Kerberos/NTLM-Authentifizierung, wenn das Konto in Active Directory deaktiviert ist. Der Client Skype Raum System muss in der Lage, Exchange-Webdienste zum Abrufen von kalendereinstellungen authentifizieren und muss auch Senden von e-Mails mit Whiteboard-Inhalt. 
  
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

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Aktivieren von Skype Raum System Benutzerkonten für Skype für Unternehmen

Dieser Abschnitt enthält eine Übersicht über die erforderlichen Schritte zum Skype für Unternehmen für Ihre Konferenz Raum aktivieren auf Skype Raum System konfiguriert werden. 
  
Nachdem ein Postfach Ressourcenkonto für die Konferenzen Räume erstellt wurde, verwenden Sie Skype für Business Server-Verwaltungsshell, um Skype Raum Systemkonten für Skype für BusinessServices zu aktivieren.
  
> [!NOTE]
> Das folgende Verfahren wird davon ausgegangen, dass Sie das Systemkonto von Skype Raum in Active Directory aktiviert haben. 
  
1. Führen Sie den folgenden Befehl aus, um das Systemkonto von Skype Raum auf einen Skype für Business Server-Pool zu aktivieren:
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Optional: Erlauben Sie, dass dieses Konto Festnetzanrufe tätigt und empfängt, indem Sie das Konto für Enterprise-VoIP aktivieren. Enterprise-VoIP ist nicht erforderlich für Skype Raum System, aber wenn Sie es nicht für Enterprise-VoIP aktivieren, der Skype Raum System Client nicht möglich PSTN-Einwahl-Funktionalität bereitstellen:
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Wenn Sie Enterprise-VoIP für das Skype Raum Konferenz Raum Systemkonto aktivieren, stellen Sie sicher, so konfigurieren Sie eine eingeschränkte VoIP-Richtlinie für Ihre Organisation geeignet. Wenn die Skype für Business Besprechungsraum eine öffentlich zugängliche Ressource ist, können damit alle Benutzer teilnehmen an einer Besprechung, entweder geplant oder spontan. Nach dem Beitritt zu einer Besprechung kann die Person beliebige Nummern anwählen. In Skype für Business Server verwendet die Anwahl von Konferenzen-Funktion die VoIP-Richtlinie des Benutzers, in diesem Fall das Skype Raum Systemkonto verwendet wird, an der Besprechung teilnehmen. In früheren Versionen von Lync Server wird die VoIP-Richtlinie des Organisators verwendet. Aus diesem Grund, wenn ein Benutzer von einer früheren Version von Lync Server einen Besprechungsraum plant und das Systemkonto Skype Raum Raum lädt, jeder konnte die Skype für Business Besprechungsraum verwenden, um an der Besprechung teilzunehmen und wählen Sie ein beliebiges Telefon nationale/regionale und internationale konnte Anzahl, solange der Organisator So wählen Sie diese Nummern zulässig ist. 
  


---
title: Skype Room System – Hybridbereitstellungen
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lesen Sie in diesem Thema erfahren, wie Skype Raum System in einer hybridumgebung bereitstellen.
ms.openlocfilehash: e4ef63ec39106a2cb35201d43ca012b4ce173911
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype Room System – Hybridbereitstellungen
 
Lesen Sie in diesem Thema erfahren, wie Skype Raum System in einer hybridumgebung bereitstellen.
  
## <a name="hybrid-deployments"></a>Hybridbereitstellungen

Gehen Sie folgendermaßen vor, wenn Ihre Topologie Skype für Business Server und Exchange Online, und Sie das Ressourcenpostfach Skype Raum System auf Exchange Online hosten möchten. Dieser Abschnitt behandelt auch ein Hybridszenario, in dessen Rahmen sowohl Exchange Online als auch Exchange Server bereitgestellt werden.
  
Zur Veranschaulichung verwenden wir für die lokale Domäne und LyncSample.ccstp.net LyncSample.com für die online-Domäne.
  
1. Erstellen Sie ein Ressourcenpostfach im Exchange Administrationscenter (LyncSample.ccsctp.net) durch Verbinden mit der Exchange Online-Verwaltungsshell wie in Exchange Online-Bereitstellung beschrieben.
    
  ```
  New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
  ```

    OWA-Konnektivität mit lrstest5@LyncSample.ccsctp.net anmelden kann überprüft werden.
    
2. Fügen Sie einer e-Mail-Adresse lrstest5@LyncSample.com (auf Prem Domäne hinzu), und legen Sie es als Antwortadresse, in der Office 365-Exchange-Verwaltungskonsole.
    
3. Erstellen einer auf Prem Active Directory-Benutzer lrstest5@LyncSample.com, legen Sie die E-mail-Adresse auf lrstest5@LyncSample.com und die Zieladresse auf lrstest5@LyncSample.com festgelegt.
    
4. Auslösen Directory-Synchronisierung und, nachdem Synchronisierung abgeschlossen ist, stellen Sie sicher, dass Benutzer in AAD zusammenführen und Sie nicht zum Ändern der Eigenschaften des Empfängers Ressourcen im Office365 Exchange Administrationscenter können.
    
5. Überprüfen der OWA-Konnektivität mit lrstest5@LyncSample.com. (Früher überprüft, ob Sie OWA-Verbindung und die Domäne online verwenden.)
    
    Nachdem das Postfach erstellt worden ist, können Sie Set-CalendarProcessing in der Exchange-Online-Verwaltungsshell verwenden, um das Postfach zu konfigurieren. Mehr dazu erfahren Sie in den Schritten 3–6 unter „Lokale Bereitstellungen mit einzelner Gesamtstruktur“.
    
    > [!NOTE]
    > Wenn Sie eine hybridumgebung mit Exchange Server und Exchange Online haben, fahren Sie mit der Exchange-Verwaltungsshell und Enable-RemoteMailbox lrstest5@LyncSample.com - RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Chatroom. Lösen Sie anschließend die Verzeichnissynchronisierung aus. 
  
    Wenn Sie das Postfach Skype Raum im Exchange Online hosten möchten, diese Schritte für die Exchange-Verwaltungsshell sind nicht erforderlich, und können Sie mit Schritt 6 fortfahren.
    
6. Aktivieren Sie das Systemkonto von Skype Raum für Skype für Unternehmen durch Ausführen des folgenden Cmdlets auf Skype für Business-Verwaltungsshell:
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Wenn Sie Skype für Business Online anstelle von Skype für Business Server im obigen Szenario haben, klicken Sie dann nach dem das Ressourcenpostfach Exchange-Bereitstellung Bereitstellen einer Skype für Business Konto wie in Skype für die Bereitstellung von Business Online beschrieben. 
  


---
title: Skype Raumsystemhybridbereitstellungen
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: In diesem Thema erfahren Sie, wie Sie Skype Raumsystem in einer Hybridumgebung bereitstellen.
ms.openlocfilehash: caebf77f0ef5abb2b56c64446ad04a052d8f98f9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841947"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype Raumsystemhybridbereitstellungen

In diesem Thema erfahren Sie, wie Sie Skype Raumsystem in einer Hybridumgebung bereitstellen.
  
## <a name="hybrid-deployments"></a>Hybridbereitstellungen

Führen Sie die folgenden Schritte aus, wenn Ihre Topologie über Skype for Business Server und Exchange Online verfügt und Sie das Skype Raumsystem-Ressourcenpostfach auf Exchange Online hosten möchten. In diesem Abschnitt wird auch ein Hybridszenario behandelt, in dem Sie sowohl Exchange Online als auch Exchange Server bereitgestellt haben.
  
Zur Veranschaulichung verwenden wir LyncSample.com für die lokale Domäne und LyncSample.ccstp.net für die Onlinedomäne.
  
1. Erstellen Sie ein Ressourcenpostfach im Exchange Admin Center (LyncSample.ccsctp.net), indem Sie eine Verbindung mit der Exchange Online Verwaltungsshell herstellen, wie in Exchange Online Bereitstellung beschrieben.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Sie können die OWA-Konnektivität mit lrstest5@LyncSample.ccsctp.net für die Anmeldung überprüfen.
    
2. Fügen Sie im Microsoft 365 oder Office 365 Exchange Admin Center eine E-Mail-Adresse lrstest5@LyncSample.com (lokale Domäne) hinzu, und legen Sie sie als Antwortadresse fest.
    
3. Erstellen Sie einen lokalen Active Directory-Benutzer lrstest5@LyncSample.com, legen Sie die E-Mail-Adresse auf lrstest5@LyncSample.com fest, und legen Sie die Zieladresse auf lrstest5@LyncSample.com fest.
    
4. Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.
    
5. Überprüfen Sie die OWA-Konnektivität mit lrstest5@LyncSample.com. (Zuvor haben Sie die OWA-Konnektivität mithilfe der Onlinedomäne überprüft.)
    
    Nach dem Erstellen des Postfachs können Sie Set-CalendarProcessing in der Exchange Online Verwaltungsshell verwenden, um das Postfach zu konfigurieren. Weitere Informationen finden Sie in den Schritten 3 bis 6 unter Lokale Bereitstellungen mit einzelner Gesamtstruktur.
    
   > [!NOTE]
   > Wenn Sie über eine Hybridumgebung mit Exchange Server und Exchange Online verfügen, wechseln Sie zur Exchange Verwaltungsshell und Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room. Lösen Sie dann die Verzeichnissynchronisierung aus. 
  
    Wenn Sie das Skype Raumsystempostfach in Exchange Online hosten möchten, sind diese Exchange Verwaltungsshell-Schritte nicht erforderlich, und Sie können mit Schritt 6 fortfahren.
    
6. Aktivieren Sie das Skype Room System-Konto für Skype for Business, indem Sie das folgende Cmdlet in Skype for Business Verwaltungsshell ausführen:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Wenn Sie im obigen Szenario Skype for Business Online anstelle von Skype for Business Server haben, stellen Sie nach der Bereitstellung des Exchange Ressourcenpostfachs ein Skype for Business Konto bereit, wie in Skype for Business Onlinebereitstellung. 
  


---
title: Skype Raumsystemhybridbereitstellungen
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
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: In diesem Thema erfahren Sie, wie Sie Skype Raumsystem in einer Hybridumgebung bereitstellen.
ms.openlocfilehash: f25f9c57a64f5a6711283e2d5cdb97331e6e699b5fbceab2728221441c9463f8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54332057"
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
    
4. Lösen Sie die Verzeichnissynchronisierung aus, und stellen Sie nach Abschluss der Synchronisierung sicher, dass Benutzer in AAD zusammengeführt werden und dass Sie die Eigenschaften der Empfängerressourcen im Microsoft 365 oder Office 365 Exchange Admin Center nicht ändern können.
    
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
> Wenn Sie im obigen Szenario Skype for Business Online anstelle von Skype for Business Server haben, stellen Sie nach der Bereitstellung des Exchange Ressourcenpostfachs ein Skype for Business Konto bereit, wie in Skype for Business Onlinebereitstellung beschrieben. 
  


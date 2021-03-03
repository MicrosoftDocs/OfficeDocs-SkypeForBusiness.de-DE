---
title: Hybridbereitstellungen von Skype Room System
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
description: In diesem Thema erfahren Sie, wie Sie Skype Room System in einer Hybridumgebung bereitstellen.
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805895"
---
# <a name="skype-room-system-hybrid-deployments"></a>Hybridbereitstellungen von Skype Room System

In diesem Thema erfahren Sie, wie Sie Skype Room System in einer Hybridumgebung bereitstellen.
  
## <a name="hybrid-deployments"></a>Hybridbereitstellungen

Führen Sie die folgenden Schritte aus, wenn Ihre Topologie über Skype for Business Server und Exchange Online verfügt und Sie das Skype Room System-Ressourcenpostfach auf Exchange Online hosten möchten. In diesem Abschnitt wird auch ein Hybridszenario behandelt, in dem Sowohl Exchange Online als auch Exchange Server bereitgestellt werden.
  
Zur Veranschaulichung verwenden wir LyncSample.com für die lokale Domäne und LyncSample.ccstp.net für die Onlinedomäne.
  
1. Erstellen Sie ein Ressourcenpostfach im Exchange Admin Center (LyncSample.ccsctp.net), indem Sie eine Verbindung mit der Exchange Online-Verwaltungsshell herstellen, wie in der Exchange Onlinebereitstellung beschrieben.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Sie können die OWA-Konnektivität mithilfe lrstest5@LyncSample.ccsctp.net anmelden.
    
2. Fügen Sie im Microsoft 365- oder Office 365 Exchange Admin Center eine E-Mail-Adresse lrstest5@LyncSample.com (Vor-Ort-Domäne) hinzu, und legen Sie sie als Antwortadresse.
    
3. Erstellen Sie eine aktive Active Directory-lrstest5@LyncSample.com, legen Sie die E-Mail-Adresse auf lrstest5@LyncSample.com und die Zieladresse auf lrstest5@LyncSample.com.
    
4. Lösen Sie die Verzeichnissynchronisierung aus, und stellen Sie nach Abschluss der Synchronisierung sicher, dass Benutzer in AAD zusammengeführt werden und dass Sie die Eigenschaften der Empfängerressourcen im Microsoft 365 oder Office 365 Exchange Admin Center nicht ändern können.
    
5. Überprüfen Sie die OWA-Konnektivität mithilfe lrstest5@LyncSample.com. (Zuvor haben Sie die OWA-Konnektivität mithilfe der Onlinedomäne überprüft.)
    
    Nach dem Erstellen des Postfachs können Sie Set-CalendarProcessing in der Exchange Online-Verwaltungsshell verwenden, um das Postfach zu konfigurieren. Weitere Informationen finden Sie in den Schritten 3 bis 6 unter "Bereitstellungen mit einer einzelnen Gesamtstruktur vor Ort".
    
   > [!NOTE]
   > Wenn Sie über eine Hybridumgebung mit Exchange Server und Exchange Online verfügen, wechseln Sie zur Exchange-Verwaltungsshell und Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room. Lösen Sie dann die Verzeichnissynchronisierung aus. 
  
    Wenn Sie das Skype Room System-Postfach in Exchange Online hosten möchten, sind diese Schritte der Exchange-Verwaltungsshell nicht erforderlich, und Sie können mit Schritt 6 fortfahren.
    
6. Aktivieren Sie das Skype Room System-Konto für Skype for Business, indem Sie das folgende Cmdlet in der Skype for Business-Verwaltungsshell ausführen:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Wenn Sie skype for Business Online anstelle von Skype for Business Server im obigen Szenario verwenden, stellen Sie nach der Bereitstellung des Exchange-Ressourcenpostfachs ein Skype for Business-Konto wie in skype for Business Online Provisioning beschrieben zur Verfügung. 
  


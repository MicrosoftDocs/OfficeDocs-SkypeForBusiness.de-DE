---
title: Hybridbereitstellungen für Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lesen Sie dieses Thema, um zu erfahren, wie Skype Room System in einer Hybridumgebung bereitgestellt wird.
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219675"
---
# <a name="skype-room-system-hybrid-deployments"></a>Hybridbereitstellungen für Skype Room System

Lesen Sie dieses Thema, um zu erfahren, wie Skype Room System in einer Hybridumgebung bereitgestellt wird.
  
## <a name="hybrid-deployments"></a>Hybridbereitstellungen

Führen Sie die folgenden Schritte aus, wenn Ihre Topologie über Skype for Business Server und Exchange Online verfügt und Sie das Skype Room System-Ressourcenpostfach auf Exchange Online hosten möchten. In diesem Abschnitt wird außerdem ein Hybrid Szenario behandelt, in dem Sie sowohl Exchange Online als auch Exchange Server bereitgestellt haben.
  
Zur Veranschaulichung wird LyncSample.com für die lokale Domäne und LyncSample.ccstp.net für die Online Domäne verwendet.
  
1. Erstellen Sie ein Ressourcenpostfach in der Exchange-Verwaltungskonsole (LyncSample.ccsctp.net), indem Sie eine Verbindung mit der Exchange Online-Verwaltungsshell herstellen, wie in Exchange Online-vorsehen beschrieben.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Sie können die OWA-Konnektivität mithilfe von lrstest5@LyncSample.ccsctp.NET überprüfen, um sich anzumelden.
    
2. Fügen Sie in der Microsoft 365-oder Office 365 Exchange-Verwaltungskonsole eine e-Mail-Adresse lrstest5@LyncSample.com (on-Prem Domain) hinzu, und legen Sie Sie als Antwortadresse fest.
    
3. Erstellen Sie eine Active Directory Benutzer lrstest5@LyncSample.com, legen Sie die e-Mail-Adresse auf lrstest5@LyncSample.com, und legen Sie die Zieladresse auf lrstest5@LyncSample.com.
    
4. Rufen Sie die Verzeichnissynchronisierung ab, und überprüfen Sie nach Abschluss der Synchronisierung, ob die Benutzer in Aad zusammengeführt werden und ob die Eigenschaften in den Ressourcen des Empfängers in der Microsoft 365-oder Office 365 Exchange-Verwaltungskonsole geändert werden können.
    
5. Überprüfen der OWA-Konnektivität mithilfe von lrstest5@LyncSample.com. (Zuvor haben Sie die OWA-Konnektivität über die Online Domäne überprüft.)
    
    Nachdem Sie das Postfach erstellt haben, können Sie mithilfe von "CalendarProcessing" in der Exchange Online-Verwaltungsshell das Postfach konfigurieren. Weitere Informationen finden Sie in den Schritten 3 bis 6 unter einzelne Gesamtstruktur-Bereitstellungen.
    
   > [!NOTE]
   > Wenn Sie über eine Hybridumgebung mit Exchange Server und Exchange Online verfügen, wechseln Sie zum Exchange-Verwaltungsshell und enable-Remote Mailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.Mail.ccsctp.net-Room. Anschließend wird die Verzeichnissynchronisierung ausgelöst. 
  
    Wenn Sie das Skype Room System-Postfach in Exchange Online hosten möchten, sind diese Exchange-Verwaltungsshell Schritte nicht erforderlich, und Sie können mit Schritt 6 fortfahren.
    
6. Aktivieren Sie das Skype Room System-Konto für Skype for Business, indem Sie das folgende Cmdlet für Skype for Business-Verwaltungsshell ausführen:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Wenn Sie Skype for Business Online anstelle von Skype for Business Server im obigen Szenario haben, stellen Sie nach dem Bereitstellen des Exchange-Ressourcenpostfachs ein Skype for Business-Konto bereit, wie unter Skype for Business Online-Bereitstellung beschrieben. 
  


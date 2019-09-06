---
title: Skype Room System – Hybridbereitstellungen
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: In diesem Thema erfahren Sie, wie Sie das Skype Room-System in einer Hybridumgebung bereitstellen.
ms.openlocfilehash: 80e7efaf5fe3705e052d40606ea5944527d43a61
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774956"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype Room System – Hybridbereitstellungen

In diesem Thema erfahren Sie, wie Sie das Skype Room-System in einer Hybridumgebung bereitstellen.
  
## <a name="hybrid-deployments"></a>Hybridbereitstellungen

Führen Sie die folgenden Schritte aus, wenn Ihre Topologie über Skype for Business Server und Exchange Online verfügt und Sie das Skype Room-System Ressourcenpostfach auf Exchange Online hosten möchten. Dieser Abschnitt behandelt auch ein Hybridszenario, in dessen Rahmen sowohl Exchange Online als auch Exchange Server bereitgestellt werden.
  
Zu illustrativen Zwecken verwenden wir LyncSample.com für die lokale Domäne und LyncSample.ccstp.net für die Online Domäne.
  
1. Erstellen Sie ein Ressourcenpostfach im Exchange Admin Center (LyncSample.ccsctp.net), indem Sie eine Verbindung zur Exchange Online-Verwaltungsshell herstellen, wie in Exchange Online-Bereitstellung beschrieben.
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Sie können die OWA-Konnektivität mithilfe von lrstest5@LyncSample.ccsctp.NET überprüfen, um sich anzumelden.
    
2. Fügen Sie im Office 365 Exchange Admin Center eine e-Mail-Adresse lrstest5@LyncSample.com (auf-Prem-Domäne) hinzu, und stellen Sie Sie als Antwortadresse ein.
    
3. Erstellen Sie eine auf-Prem Active Directory-Benutzer lrstest5@LyncSample.com, legen Sie die e-Mail-Adresse auf lrstest5@LyncSample.com, und legen Sie die Zieladresse auf lrstest5@LyncSample.com.
    
4. Führen Sie die Verzeichnissynchronisierung aus, und vergewissern Sie sich nach Abschluss der Synchronisierung, dass Benutzer in Aad zusammengeführt werden und dass Sie die Eigenschaften in den Ressourcen des Empfängers im Office365 Exchange Admin Center nicht ändern können.
    
5. Überprüfen Sie die OWA-Konnektivität mithilfe von lrstest5@LyncSample.com. (Zu einem früheren Zeitpunkt haben Sie OWA-Konnektivität mithilfe der Onlinedomäne überprüft.)
    
    Nachdem das Postfach erstellt worden ist, können Sie Set-CalendarProcessing in der Exchange-Online-Verwaltungsshell verwenden, um das Postfach zu konfigurieren. Mehr dazu erfahren Sie in den Schritten 3–6 unter „Lokale Bereitstellungen mit einzelner Gesamtstruktur“.
    
   > [!NOTE]
   > Wenn Sie über eine Hybridumgebung mit Exchange Server und Exchange Online verfügen, wechseln Sie zur Exchange-Verwaltungsshell, und aktivieren Sie RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.Mail.ccsctp.net-Room. Lösen Sie anschließend die Verzeichnissynchronisierung aus. 
  
    Wenn Sie das Skype Room-System Postfach in Exchange Online hosten möchten, sind diese Schritte zur Exchange-Verwaltungsshell nicht erforderlich, und Sie können mit Schritt 6 fortfahren.
    
6. Aktivieren Sie das Skype Room-System Konto für Skype for Business, indem Sie auf der Skype for Business-Verwaltungsshell das folgende Cmdlet ausführen:
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Wenn Sie Skype for Business Online anstelle von Skype for Business Server im obigen Szenario haben, stellen Sie nach der Bereitstellung des Exchange-Ressourcenpostfachs ein Skype for Business-Konto bereit, wie es in der Skype for Business Online-Bereitstellung beschrieben ist. 
  


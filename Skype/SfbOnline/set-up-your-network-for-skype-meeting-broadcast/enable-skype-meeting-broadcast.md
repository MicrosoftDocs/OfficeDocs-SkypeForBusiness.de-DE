---
title: Aktivieren von Skype-Livekonferenz
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Bevor die Personen in Ihrer Organisation Skype-Live Konferenz verwenden können, müssen Sie Sie aktivieren. Dazu müssen Sie wissen, wie Sie Windows PowerShell verwenden. Wenn Sie keine Erfahrungen mit Windows PowerShell haben, sollten Sie möglicherweise einen Microsoft-Partner für diese Aufgabe heranziehen.
ms.openlocfilehash: f1a672bc8d3b0ce957a32691270293551e1a1409
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494035"
---
# <a name="enable-skype-meeting-broadcast"></a>Aktivieren von Skype-Livekonferenz

Bevor die Personen in Ihrer Organisation Skype-Live Konferenz verwenden können, müssen Sie Sie aktivieren. Dazu müssen Sie wissen, wie Sie Windows PowerShell verwenden. Wenn Sie keine Erfahrungen mit Windows PowerShell haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Aktivieren von Skype-Livekonferenz im Skype for Business Admin Center

![Ein Symbol mit dem Skype for Business-](../images/sfb-logo-30x30.png) Logo **im Skype for Business Admin Center**

1. Melden Sie sich mit dem Konto Globaler Office 365-Administrator bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.
    
2. Navigieren Sie im „Office 365 Admin Center" zu **Admin Center** > **Skype for Business**.
    
3. Wechseln Sie im **Skype for Business Admin Center**zu Besprechungen für **Online Besprechungen** > ****, und wählen Sie dann Skype-Live **Konferenz aktivieren**aus.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Aktivieren von Skype-Livekonferenz mit PowerShell

1. Überprüfen Sie, ob Sie Version 3.0 oder höher von Windows PowerShell ausführen.
    
2. So überprüfen Sie, ob Sie Version 3.0 oder höher benutzen: **Startmenü** > **Windows PowerShell**.
    
3. Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.
    
4. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
5. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
6. Wählen Sie im **Startmenü**die Option **Windows PowerShell**aus.
    
7. Stellen Sie im **Windows PowerShell**-Fenster eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:
    
   ```
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. Bestätigen Sie Ihre aktuelle Skype-Livekonferenz-Konfiguration, indem Sie Folgendes ausführen:
    
   ```
   Get-CsBroadcastMeetingConfiguration
   ```

    Überprüfen Sie, ob der Parameter  _EnableBroadcastMeeting_ auf `False` festgelegt ist.
    
     ![Cmdlet "Enable Organization" in Skype Meeting Broadcast](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Aktivieren Sie Skype-Livekonferenz für Ihr Unternehmen, indem Sie Folgendes ausführen:
    
   ```
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Sie können überprüfen, ob die Einstellung aktiviert ist `Get-CsBroadcastMeetingConfiguration` , indem Sie erneut ausgeführt wird.
    
     ![Cmdlet "Enable Organization" in Skype Meeting Broadcast](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Nach der Änderung kann es bis zu einer Stunde dauern, bis sie im Skype-Livekonferenz-Portal angezeigt wird. 
  
10. Ihre Benutzer können jetzt Livekonferenzen mit anderen Benutzern in Ihrem Unternehmen durchführen. Um Ihre Benutzer bei der Durchführung zu unterstützen, verweisen Sie sie auf [Was ist eine Skype-Livekonferenz?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Konfigurieren Ihres Netzwerks zur Durchführung von Livekonferenzen mit externen Teilnehmern

Wenn Sie über eine Firewall verfügen und Konferenzen mit Personen außerhalb Ihres Unternehmens (die nicht zum Unternehmensverbund gehören) durchführen möchten, müssen Sie Ihr Netzwerk unter Befolgung dieser Anweisungen konfigurieren: [Einrichten Ihres Netzwerks für Skype-Livekonferenz](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Wenn Sie keine Erfahrungen mit der Konfiguration Ihrer Firewall haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.
  
Um diesen Schritt zu überspringen und stattdessen Ihrem Verbund ein anderes Unternehmen hinzuzufügen, führen Sie die Schritte unter [Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) aus. 
  
## <a name="related-topics"></a>Verwandte Themen

[Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
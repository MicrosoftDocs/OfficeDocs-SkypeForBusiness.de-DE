---
title: "Skype-Besprechung Übertragung aktivieren"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Bevor die Personen in Ihrer Organisation Skype Besprechung übertragen verwenden können, müssen Sie ihn aktivieren. Zu diesem Zweck müssen Sie wissen, wie Sie mithilfe von Windows PowerShell. Wenn Sie Windows PowerShell nicht kennen, können Sie Einstellen von Microsoft-Partner können Sie diesen Schritt übergehen."
ms.openlocfilehash: 975f0304f2053e23375c5eabc62ec224bedc02e7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="enable-skype-meeting-broadcast"></a>Skype-Besprechung Übertragung aktivieren

Bevor die Personen in Ihrer Organisation Skype Besprechung übertragen verwenden können, müssen Sie ihn aktivieren. Zu diesem Zweck müssen Sie wissen, wie Sie mithilfe von Windows PowerShell. Wenn Sie Windows PowerShell nicht kennen, können Sie Einstellen von einem [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) können Sie diesen Schritt übergehen.
  
> [!CAUTION]
> Skype-Besprechung Übertragung ist standardmäßig deaktiviert, da die Verteilung von Media-Inhalten einer broadcast Besprechung des Microsoft Azure Content Delivery Network (CDN) verwendet, um sehr hohe Skalierung auf Tausende von Personen, die einen Broadcast ansehen zu erzielen. Die aufgeteilte Medieninhalte über das CDN übergeben wird verschlüsselt, und der CDN-Cache verfügt über eine begrenzte Lebensdauer. Darüber hinaus kann die Azure CDN-Komponente nicht noch alle Elemente der wortstammerkennung aus der EU-Datenschutzrichtlinie der EU-Modellklauseln entsprechen. Aktivieren Sie dieses Feature, bestätigen Sie diesen Hinweis. 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Aktivieren Sie Skype Besprechung übertragen mithilfe der Skype für Business Administrationscenter

1. Melden Sie sich mit Ihrem globalen Office 365-Administratorkonto bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.
    
2. Wechseln Sie in das Office 365 Admin Center zu **Admin zentriert** > **Skype für Unternehmen**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**zu **onlinebesprechungen** > **Besprechungen übertragen**, und wählen Sie dann **Aktivieren Skype Besprechung übertragen**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Aktivieren von Skype Besprechung übertragen von PowerShell

1. Stellen Sie sicher, dass Sie Version 3.0 oder höher von Windows PowerShell ausgeführt werden.
    
1. Um sicherzustellen, dass Sie Version 3.0 oder höher ausgeführt werden: **Im Menü Start** > **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster **Windows PowerShell** die Zeichenfolge _Get-Host_ eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
2. Wählen Sie im **Menü Start**wählen Sie **Windows PowerShell**.
    
3. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. Bestätigen Sie die aktuelle Konfiguration Skype Besprechung übertragen werden durch ausführen:
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    Stellen Sie sicher, dass der Parameter _EnableBroadcastMeeting_ , um festgelegt ist `False`.
    
     ![Skype Besprechung übertragen aktivieren Organisation-Cmdlet.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. Aktivieren Sie Skype Besprechung übertragen für Ihre Organisation durch ausführen:
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    Sie können überprüfen, ob die Einstellung aktiviert ist, durch Ausführen von `Get-CsBroadcastMeetingConfiguration` erneut.
    
     ![Skype-Besprechung Übertragung aktivieren Organisation-Cmdlet.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Nachdem Sie die Änderung vornehmen, kann es bis zu einer Stunde dauern, bis im Portal Skype Besprechung übertragen wirksam wird. 
  
6. Die Benutzer können jetzt broadcast Besprechungen mit anderen Benutzern in Ihrem Unternehmen halten. Um diese Schritte zu erhalten, zeigen sie auf [Was ist eine Skype Besprechung übertragen?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Konfigurieren des Netzwerks, um Besprechungen mit externen Teilnehmern senden

Wenn eine Firewall, und Sie halten Übertragungen mit Personen außerhalb Ihres Unternehmens (, die keiner verbundgeschäftspartner sind) möchten, müssen Sie Ihr Netzwerk anhand der folgenden Schritte konfigurieren: [Richten Sie Ihr Netzwerk für Skype Besprechung übertragen werden](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Wenn Sie keine Erfahrungen mit der Konfiguration Ihrer Firewall haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.
  
Wenn Sie diesen Schritt überspringen und stattdessen ein anderes Unternehmen, Ihre Verbund hinzufügen, finden Sie unter [wenden Sie sich an externe Skype für Unternehmensbenutzer durch Benutzer zulassen](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Verwandte Themen

[Eine Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)


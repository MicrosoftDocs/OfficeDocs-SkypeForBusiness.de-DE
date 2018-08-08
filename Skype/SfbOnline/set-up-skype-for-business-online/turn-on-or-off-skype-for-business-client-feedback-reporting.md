---
title: Aktivieren oder Deaktivieren von Feedbackberichten im Skype for Business-Client
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Sie können Ihre Skype für Unternehmensbenutzer mithilfe der integrierten Skype für Business app-Feedback-Tool, damit Benutzer Probleme melden, und geben Sie Feedback direkt an Microsoft zu ihren Wünschen aktivieren.
ms.openlocfilehash: 09ddaa9952ab5d536c6a95937ca71c4c056a15e0
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "22135540"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>Aktivieren oder Deaktivieren von Feedbackberichten im Skype for Business-Client

Sie können Ihre Skype für Business Online-Benutzern mithilfe der integrierten Skype für Business app-Feedback-Tool, damit Benutzer Probleme melden, und geben Sie Feedback direkt an Microsoft zu ihren Wünschen aktivieren. 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
Mit diesem Tool kann Benutzer kopieren die Protokolle von der app auf ihrem Gerät Microsoft besser zu untersuchen und Behandeln von Problemen, die sie möglicherweise helfen. 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
Sie können auch die Einstellung  _EnableOnlineFeedbackScreenshot_ verwenden, damit Benutzer zusammen mit dem Feedback einen Screenshot von ihrem Gerät senden können.
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> Die Protokolle von der app Feedbacktool gesammelt werden gespeichert für bis zu maximal 90 Tage in den USA, während das Problem untersucht wird. Aktivieren Sie daher das Feedbacktool nicht, wenn dies einen Verstoß gegen die Datenschutzrichtlinien Ihrer Organisation darstellt. 
  
## <a name="verify-and-start-windows-powershell"></a>Überprüfen und Starten von Windows PowerShell

- **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Starten einer Windows PowerShell-Sitzung**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:
    
    > [!NOTE]
    > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.
 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```
Weitere Informationen zum Starten von Windows PowerShell finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder[Herstellen der Verbindung zu Skype for Business Online mit Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>Aktivieren von Feedbackberichten in der Client-App für alle Benutzer in Ihrer Organisation

Um Feedback reporting für Benutzer in Ihrer Organisation zu aktivieren, und ermöglicht es ihnen, Screenshots Gerät übermitteln, führen Sie Folgendes aus:
 
  ```
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Skype verwalten, für die Business Online verwenden eine zentrale Verwaltung, die Ihrer täglichen Arbeit vereinfachen können, wenn Sie mehrere Aufgaben ausführen müssen. Siehe folgende Themen, um Windows PowerShell zu verwenden:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See Also
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)

  
 

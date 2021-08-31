---
title: Aktivieren oder Deaktivieren von Feedbackberichten im Skype for Business-Client
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Sie können Ihren Skype for Business ermöglichen, das integrierte Feedbacktool für Skype for Business-App zu verwenden, damit Benutzer Probleme melden und Microsoft Feedback zu deren Erfahrung direkt geben können.
ms.openlocfilehash: 9382c19c5abf78dc47dcaa3de33841a64e96f490
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728284"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>Aktivieren oder Deaktivieren von Feedbackberichten im Skype for Business-Client

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Sie können Ihren Skype for Business Online-Benutzern die Verwendung des integrierten Feedbacktools für die Skype for Business-App ermöglichen, damit Benutzer Probleme melden und Microsoft Feedback zu deren Erfahrung geben können. 
  
![Symbol "Feedback bereitstellen"](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
Mit diesem Tool kann ein Benutzer die Protokolle aus der App auf dem Gerät kopieren, um Microsoft dabei zu unterstützen, probleme, die möglicherweise auftreten, besser zu untersuchen und zu behandeln. 
  
![Melden Sie ein Problem mithilfe Einstellungen Symbol .](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
Sie können auch die Einstellung  _EnableOnlineFeedbackScreenshot_ verwenden, damit Benutzer zusammen mit dem Feedback einen Screenshot von ihrem Gerät senden können.
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> Die vom Feedbacktool der App gesammelten Protokolle werden bis zu 90 Tage lang in den USA gespeichert, während das Problem untersucht wird. Aktivieren Sie daher das Feedbacktool nicht, wenn dies einen Verstoß gegen die Datenschutzrichtlinien Ihrer Organisation darstellt. 
  
## <a name="start-windows-powershell"></a>Starten Windows PowerShell

> [!NOTE]
> Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams. Wenn Sie die neueste Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.
1. Installieren Sie [Teams PowerShell-Modul.](/microsoftteams/teams-powershell-install)
    
2. Öffnen Sie eine Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   Weitere Informationen zum Starten von Windows PowerShell finden Sie unter Verbinden für alle [Microsoft 365-](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) oder Office 365-Dienste in einem einzigen Windows PowerShell-Fenster oder Einrichten des Computers [für Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>Aktivieren von Feedbackberichten in der Client-App für alle Benutzer in Ihrer Organisation

Um Feedbackberichte für Benutzer in Ihrer Organisation zu aktivieren und ihnen das Übermitteln von Geräte-Screenshots zu ermöglichen, führen Sie die folgenden Funktionen aus:
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365, Office 365 und Skype for Business Online über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Microsoft 365 oder Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center gegenüber Geschwindigkeit, Einfachheit und Produktivität viele Vorteile, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)

  

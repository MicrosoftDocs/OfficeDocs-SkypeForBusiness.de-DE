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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Bevor die Personen in Ihrer Organisation die Skype-Besprechung verwenden können, müssen Sie sie aktivieren. Dazu müssen Sie wissen, wie Sie ihre Windows PowerShell. Wenn Sie keine Erfahrungen mit Windows PowerShell haben, sollten Sie möglicherweise einen Microsoft-Partner für diese Aufgabe heranziehen.
ms.openlocfilehash: 4f16444a07c81b44e4078a2c294208f59e4d7775
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599670"
---
# <a name="enable-skype-meeting-broadcast"></a>Aktivieren von Skype-Livekonferenz

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 beendet, und der Zugriff auf den Dienst endet. Wir empfehlen Kunden, mit dem Upgrade auf Microsoft Teams, den zentralen Client für Kommunikation und Teamarbeit in Microsoft 365.

Bevor die Personen in Ihrer Organisation die Skype-Besprechung verwenden können, müssen Sie sie aktivieren. Dazu müssen Sie wissen, wie Sie ihre Windows PowerShell. Wenn Sie keine Erfahrungen mit Windows PowerShell haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.



> [!NOTE]
> Das Microsoft Teams Admin Center hat das Skype for Business Admin Center (Legacyportal) ersetzt. Alle Einstellungen zum Verwalten Skype for Business Befinden sich jetzt im Teams Admin Center. Ihnen muss die [Azure AD-Administratorrolle](/azure/active-directory/roles/permissions-reference) eines globalen Admins oder Skype for Business zugewiesen sein, damit Skype for Business Features im Teams Admin Center verwalten können. Weitere Informationen finden Sie unter [Verwalten Skype for Business-Einstellungen im Microsoft Teams Admin Center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Aktivieren von Skype-Livekonferenz im Skype for Business Admin Center

![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

1. Melden Sie sich mit Ihrem globalen Administratorkonto oder Skype for Business bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.
    
2. Wechseln Sie im Admin Center zu **Admin Center**  >  **Teams.**
    
3. Wechseln Sie **Teams Admin Center** zu   >  **Legacyportal** Onlinebesprechungen Livebesprechungen übertragen, und wählen Sie dann Skype-Besprechung  >   **Aus.**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Aktivieren von Skype-Livekonferenz mit PowerShell

1. Installieren Sie [Teams PowerShell-Modul.](/microsoftteams/teams-powershell-install)
    
2. Öffnen Sie Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus: 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. Bestätigen Sie Ihre aktuelle Skype-Livekonferenz-Konfiguration, indem Sie Folgendes ausführen:
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    Überprüfen Sie, ob der Parameter  _EnableBroadcastMeeting_ auf `False` festgelegt ist.
    
     ![Cmdlet "Enable Organization" in Skype Meeting Broadcast](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Aktivieren Sie Skype-Livekonferenz für Ihr Unternehmen, indem Sie Folgendes ausführen:
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Sie können bestätigen, dass die Einstellung aktiviert ist, indem Sie erneut  `Get-CsBroadcastMeetingConfiguration` ausführen.
    
     ![Cmdlet "Enable Organization" in Skype Meeting Broadcast](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Nach der Änderung kann es bis zu einer Stunde dauern, bis sie im Skype-Livekonferenz-Portal angezeigt wird. 
  
10. Ihre Benutzer können jetzt Livekonferenzen mit anderen Benutzern in Ihrem Unternehmen durchführen. Um Ihre Benutzer bei der Durchführung zu unterstützen, verweisen Sie sie auf [Was ist eine Skype-Livekonferenz?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Konfigurieren Ihres Netzwerks zur Durchführung von Livekonferenzen mit externen Teilnehmern

Wenn Sie über eine Firewall verfügen und Konferenzen mit Personen außerhalb Ihres Unternehmens (die nicht zum Unternehmensverbund gehören) durchführen möchten, müssen Sie Ihr Netzwerk unter Befolgung dieser Anweisungen konfigurieren: [Einrichten Ihres Netzwerks für Skype-Livekonferenz](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Wenn Sie keine Erfahrungen mit der Konfiguration Ihrer Firewall haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.
  
Um diesen Schritt zu überspringen und stattdessen Ihrem Verbund ein anderes Unternehmen hinzuzufügen, führen Sie die Schritte unter [Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) aus. 
  
## <a name="related-topics"></a>Verwandte Themen

[Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  

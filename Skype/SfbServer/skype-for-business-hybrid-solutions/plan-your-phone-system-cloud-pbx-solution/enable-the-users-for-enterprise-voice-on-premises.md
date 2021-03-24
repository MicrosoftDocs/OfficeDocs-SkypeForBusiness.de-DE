---
title: Aktivieren der Benutzer für Enterprise-VoIP lokal
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Damit ein Benutzer das Telefonsystem (Cloud PBX) verwenden kann, müssen Sie sie zunächst für Enterprise-VoIP aktivieren und ihm eine Telefonnummer zuweisen. Verwenden Sie dazu Ihre lokale Bereitstellung, während der Benutzer weiterhin in der lokalen Bereitstellung zu Hause ist.
ms.openlocfilehash: b26e51ba316c63e0f992b843a7763586d7e9b575
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098591"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Aktivieren der Benutzer für Enterprise-VoIP lokal
 
Damit ein Benutzer das Telefonsystem (Cloud PBX) verwenden kann, müssen Sie sie zunächst für Enterprise-VoIP aktivieren und ihm eine Telefonnummer zuweisen. Verwenden Sie dazu Ihre lokale Bereitstellung, während der Benutzer weiterhin in der lokalen Bereitstellung zu Hause ist.

> [!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, nachdem der Zugriff auf den Dienst nicht mehr möglich ist.  Darüber hinaus wird die PSTN-Verbindung zwischen Ihrer lokalen Umgebung über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>So aktivieren Sie einen Benutzer für Enterprise-VoIP lokal und weisen eine Telefonnummer zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Verwenden Sie das Startmenü oder die Desktopverknüpfung, um die Skype for Business Server-Systemsteuerung zu öffnen.
    
    Sie können auch ein Browserfenster öffnen und dann die Administrator-URL eingeben, um die Skype for Business Server-Systemsteuerung zu öffnen.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Skype for Business Online-Benutzerkonto, das Sie für die Enterprise-VoIP.
    
6. Klicken Sie **im** Menü Bearbeiten auf **Details anzeigen**.
    
7. Klicken **Sie unter** **Telefonie auf Enterprise-VoIP**.
    
8. Klicken **Sie auf Zeilen-URI,** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (z. B. tel:+14255550200). Klicken Sie dann auf **Commit**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Besondere Überlegungen beim Aktivieren von Benutzern Enterprise-VoIP lokalen Benutzern

In einigen Fällen müssen Sie möglicherweise die Art und Weise ändern, wie Sie Benutzer für Enterprise-VoIP, um sicherzustellen, dass sie Erfolgreich Anrufe machen und empfangen können. Wenn Sie Benutzer in Ihrer Bereitstellung haben, die die folgenden Bedingungen erfüllen, führen Sie die enthaltenen Schritte aus, um den Benutzer für die Enterprise-VoIP.
  
- Wenn ein Benutzer in Ihrer lokalen AD erstellt und dann mit Skype for Business Online synchronisiert wird, ohne für Skype for Business oder für Enterprise-VoIP aktiviert zu sein und keinen LineURI-Satz hat, führen Sie die folgenden Cmdlets für jeden betroffenen Benutzer aus, und ersetzen Sie die Werte durch tatsächliche Werte für Ihre \< \> Umgebung:
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Wenn ein Benutzer bereits lokal für Skype for Business aktiviert ist, aber nicht für Enterprise-VoIP aktiviert oder einem LineURI zugewiesen wurde, bevor er zu Skype for Business Online verschoben wird, führen Sie für jeden Benutzer das folgende Cmdlet aus:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Wenn ein Benutzer bereits lokal in Skype for Business aktiviert, aber nicht für Enterprise-VoIP aktiviert ist, auch wenn ihm bereits ein LineURI zugewiesen ist, führen Sie für jeden betroffenen Benutzer das folgende Cmdlet aus:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```
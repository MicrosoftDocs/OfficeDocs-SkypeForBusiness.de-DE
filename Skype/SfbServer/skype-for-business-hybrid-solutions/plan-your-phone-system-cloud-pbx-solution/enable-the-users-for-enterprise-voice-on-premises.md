---
title: Aktivieren der Benutzer für lokale Enterprise-VoIP
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
description: Damit ein Benutzer Telefonsystem (Cloud PBX) verwenden kann, müssen Sie diese zuerst für Enterprise-VoIP aktivieren und ihm eine Telefonnummer zuweisen. Dazu verwenden Sie Ihre lokale Bereitstellung, während der Benutzer noch in der lokalen Bereitstellung verwaltet wird.
ms.openlocfilehash: aef74877d1a12d136bddc7eedc2a414dfad100830a88bb9a21695004be91d1a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289083"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Aktivieren der Benutzer für lokale Enterprise-VoIP
 
Damit ein Benutzer Telefonsystem (Cloud PBX) verwenden kann, müssen Sie diese zuerst für Enterprise-VoIP aktivieren und ihm eine Telefonnummer zuweisen. Dazu verwenden Sie Ihre lokale Bereitstellung, während der Benutzer noch in der lokalen Bereitstellung verwaltet wird.

> [!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, danach ist der Dienst nicht mehr verfügbar.  Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>So aktivieren Sie einen Benutzer für Enterprise-VoIP lokal und weisen eine Telefonnummer zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Verwenden Sie die Startmenü oder Desktopverknüpfung, um die Skype for Business Server Systemsteuerung zu öffnen.
    
    Sie können auch ein Browserfenster öffnen und dann die Administrator-URL eingeben, um die Skype for Business Server Systemsteuerung zu öffnen.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Skype for Business Online-Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.
    
6. Klicken Sie im Menü **"Bearbeiten"** auf **"Details anzeigen".**
    
7. Klicken Sie unter **Telefonie** auf **Enterprise-VoIP**.
    
8. Klicken Sie auf **den Anschluss-URI,** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (z. B. tel:+14255550200). Klicken Sie dann auf **"Commit ausführen".**
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Besondere Überlegungen beim Aktivieren von Benutzern für lokale Enterprise-VoIP

In einigen Fällen müssen Sie möglicherweise ändern, wie Sie Benutzer für Enterprise-VoIP aktivieren, um sicherzustellen, dass sie erfolgreich Anrufe tätigen und empfangen können. Wenn Sie Benutzer in Ihrer Bereitstellung haben, die die folgenden Bedingungen erfüllen, führen Sie die enthaltenen Schritte aus, um den Benutzer für Enterprise-VoIP zu aktivieren.
  
- Wenn ein Benutzer in Ihrem lokalen AD erstellt und dann mit Skype for Business Online synchronisiert wird, ohne für Skype for Business oder für Enterprise-VoIP aktiviert zu sein und kein LineURI festgelegt ist, führen Sie die folgenden Cmdlets für jeden betroffenen Benutzer aus, und ersetzen Sie die Werte durch \< \> tatsächliche Werte für Ihre Umgebung:
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Wenn ein Benutzer bereits für Skype for Business lokal aktiviert ist, aber nicht für Enterprise-VoIP aktiviert oder vor dem Verschieben zu Skype for Business Online einen LineURI zugewiesen hat, führen Sie das folgende Cmdlet für jeden Benutzer aus:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Wenn ein Benutzer bereits in Skype for Business lokalen Bereitstellung, aber nicht für Enterprise-VoIP aktiviert ist, führen Sie auch dann das folgende Cmdlet für jeden betroffenen Benutzer aus, wenn bereits ein LineURI zugewiesen wurde:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```
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
description: Damit ein Benutzer das Telefon System (Cloud PBX) verwenden kann, müssen Sie ihn zunächst für Enterprise-VoIP aktivieren und ihm eine Telefonnummer zuweisen. Verwenden Sie dazu Ihre lokale Bereitstellung, während der Benutzer noch in der lokalen Bereitstellung verwaltet wird.
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359191"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Aktivieren der Benutzer für Enterprise-VoIP lokal
 
Damit ein Benutzer das Telefon System (Cloud PBX) verwenden kann, müssen Sie ihn zunächst für Enterprise-VoIP aktivieren und ihm eine Telefonnummer zuweisen. Verwenden Sie dazu Ihre lokale Bereitstellung, während der Benutzer noch in der lokalen Bereitstellung verwaltet wird.

> [!Important]
> Skype for Business Online werden am 31. Juli 2021 zurückgezogen, nach dem der Zugriff auf den Dienst nicht mehr möglich ist.  Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung unabhängig davon, ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Hier erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>So aktivieren Sie einen Benutzer für Enterprise-VoIP lokal und weisen eine Telefonnummer zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Verwenden Sie das Startmenü oder die Verknüpfung auf dem Desktop, um die Skype for Business Server-Systemsteuerung zu öffnen.
    
    Sie können auch ein Browserfenster öffnen und die Administrator-URL eingeben, um die Skype for Business Server-Systemsteuerung zu öffnen.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Skype for Business Online Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.
    
6. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.
    
7. Klicken Sie unter **Telefonie**auf **Enterprise-VoIP**.
    
8. Klicken Sie auf **Leitungs-URI**, und geben Sie eine eindeutige, normalisierte Telefonnummer ein (beispielsweise Tel: + 14255550200). Klicken Sie dann auf **Commit**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Besondere Überlegungen beim Aktivieren von Benutzern für Enterprise-VoIP vor Ort

In einigen Fällen müssen Sie möglicherweise die Art und Weise ändern, wie Sie Benutzer für Enterprise-VoIP aktivieren, um sicherzustellen, dass Sie Anrufe erfolgreich tätigen und empfangen können. Wenn Sie über Benutzer in Ihrer Bereitstellung verfügen, die die folgenden Bedingungen erfüllen, führen Sie die Schritte aus, die zum Aktivieren des Benutzers für Enterprise-VoIP erforderlich sind.
  
- Wenn ein Benutzer in Ihrer lokalen AD erstellt und dann mit Skype for Business Online synchronisiert wird, ohne für Skype for Business oder Enterprise-VoIP aktiviert zu sein und kein LineURI festgelegt wurde, führen Sie die folgenden Cmdlets für jeden betroffenen Benutzer aus, und ersetzen Sie die Werte in \< \> durch tatsächliche Werte für Ihre Umgebung:
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Wenn ein Benutzer bereits für Skype for Business lokal aktiviert ist, jedoch nicht für Enterprise-VoIP aktiviert wurde oder ein LineURI zugewiesen wurde, bevor er in Skype for Business Online verschoben wurde, führen Sie für jeden Benutzer das folgende Cmdlet aus:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Wenn ein Benutzer bereits in Skype for Business lokal aktiviert, aber für Enterprise-VoIP nicht aktiviert ist, führen Sie das folgende Cmdlet für jeden betroffenen Benutzer aus, wenn bereits ein LineURI zugewiesen ist:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```



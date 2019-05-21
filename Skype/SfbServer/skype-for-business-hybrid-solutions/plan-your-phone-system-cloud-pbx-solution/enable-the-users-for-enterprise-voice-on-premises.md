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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Damit ein Benutzer das Telefon System in Office 365 (Cloud PBX) verwenden kann, müssen Sie ihn zunächst für Enterprise-VoIP aktivieren und ihm eine Telefonnummer zuweisen. Dies erfolgt mithilfe der lokalen Bereitstellung, während der Benutzer weiterhin in der lokalen Bereitstellung verwaltet wird.
ms.openlocfilehash: fdd405d84cddcfe805063287b8330ccea43397de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287510"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Aktivieren der Benutzer für Enterprise-VoIP lokal
 
Damit ein Benutzer das Telefon System in Office 365 (Cloud PBX) verwenden kann, müssen Sie ihn zunächst für Enterprise-VoIP aktivieren und ihm eine Telefonnummer zuweisen. Dies erfolgt mithilfe der lokalen Bereitstellung, während der Benutzer weiterhin in der lokalen Bereitstellung verwaltet wird.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>So aktivieren Sie einen Benutzer für Enterprise-VoIP lokal und weisen eine Telefonnummer zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Benutzen Sie das Startmenü oder die Verknüpfung auf dem Desktop, um die Systemsteuerung von Skype for Business Server zu öffnen.
    
    Alternativ können Sie ein Browserfenster öffnen und dort die Admin-URL eingeben, um zur Systemsteuerung von Skype for Business Server zu gelangen.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Skype for Business Online-Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.
    
6. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.
    
7. Klicken Sie unter **Telefonie** auf **Enterprise-VoIP**.
    
8. Klicken Sie auf **Anschluss-URI** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (z. B. Tel:+14255550200). Klicken Sie dann auf **Commit ausführen**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Besondere Überlegungen beim Aktivieren von Benutzern für Enterprise-VoIP lokal

In einigen Fällen kann es vorkommen, dass Sie die Vorgehensweise hinsichtlich der Aktivierung von Benutzern für Enterprise-VoIP ändern müssen, damit Benutzer erfolgreich Anrufe tätigen und empfangen können. Wenn Sie über Benutzer in Ihrer Bereitstellung verfügen, die die folgenden Bedingungen erfüllen, führen Sie die Schritte aus, die zum Aktivieren des Benutzers für Enterprise-VoIP enthalten sind.
  
- Wenn ein Benutzer in Ihrer lokalen Anzeige erstellt und dann mit Skype for Business Online synchronisiert wird, ohne für Skype for Business oder für Enterprise-VoIP aktiviert zu sein und über keinen LineURI-Satz verfügen, führen Sie die folgenden Cmdlets für jeden betroffenen Benutzer aus, und ersetzen Sie die Werte in < C0 > <b1></b1> mit tatsächlichen Werten für Ihre Umgebung:
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Wenn ein Benutzer bereits für Skype for Business lokal verfügbar ist, aber nicht für Enterprise-VoIP aktiviert ist oder einen LineURI zugewiesen hat, bevor er in Skype for Business Online verschoben wird, führen Sie für jeden Benutzer das folgende Cmdlet aus:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Wenn ein Benutzer bereits in Skype for Business lokal, aber nicht für Enterprise-VoIP aktiviert ist, führen Sie das folgende Cmdlet für jeden betroffenen Benutzer aus, wenn Sie bereits eine LineURI zugewiesen haben:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```



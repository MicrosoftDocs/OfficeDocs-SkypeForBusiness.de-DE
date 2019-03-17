---
title: Aktivieren Sie die Benutzer für Enterprise Voice lokal
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
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
description: Für einen Benutzer in Office 365 (Cloud, PBX) Telefonsystem verwenden müssen Sie zuerst für Enterprise-VoIP zu aktivieren und weisen Sie ihnen eine Telefonnummer ein. Dieser Schritt wird mithilfe der lokalen bereitstellungs während der Benutzer noch in der lokalen Bereitstellung verwaltet wird.
ms.openlocfilehash: 8d00120b0b0fd74baed1ceb003a46cfc2468d502
ms.sourcegitcommit: 7ca7f5cd38742b6a1967bd792113348dfe689850
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2019
ms.locfileid: "30657447"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Aktivieren Sie die Benutzer für Enterprise Voice lokal
 
Für einen Benutzer in Office 365 (Cloud, PBX) Telefonsystem verwenden müssen Sie zuerst für Enterprise-VoIP zu aktivieren und weisen Sie ihnen eine Telefonnummer ein. Dieser Schritt wird mithilfe der lokalen bereitstellungs während der Benutzer noch in der lokalen Bereitstellung verwaltet wird.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Aktivieren von Benutzern für Enterprise-VoIP lokal und Zuweisen einer Telefonnummer

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Benutzen Sie das Startmenü oder die Verknüpfung auf dem Desktop, um die Systemsteuerung von Skype for Business Server zu öffnen.
    
    Alternativ können Sie ein Browserfenster öffnen und dort die Admin-URL eingeben, um zur Systemsteuerung von Skype for Business Server zu gelangen.
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf die Skype für Business Online Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.
    
6. Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.
    
7. Klicken Sie unter **Telefonie** auf **Enterprise-VoIP**.
    
8. Klicken Sie auf **Anschluss-URI** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (z. B. Tel:+14255550200). Klicken Sie dann auf **Commit ausführen**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Besondere Aspekte beim Aktivieren von Benutzern für Enterprise-VoIP lokal

In einigen Fällen kann es vorkommen, dass Sie die Vorgehensweise hinsichtlich der Aktivierung von Benutzern für Enterprise-VoIP ändern müssen, damit Benutzer erfolgreich Anrufe tätigen und empfangen können. Wenn Sie Benutzer in Ihrer Bereitstellung vorhanden, die die folgenden Kriterien erfüllen sind, führen Sie die Schritte zum Aktivieren des Benutzers für Enterprise-VoIP eingeschlossen.
  
- Wenn ein Benutzer, in Ihrer lokalen erstellt wird AD und ohne für Skype für Unternehmen oder für Enterprise Voice aktiviert mit Skype für Online Business synchronisiert und verfügen nicht über einen "lineuri" festgelegt ist, führen Sie die folgenden Cmdlets für jeden betroffenen Benutzer, ersetzen die Werte in < C0 > <b1></b1> durch tatsächliche Werte für Ihre Umgebung:
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Wenn ein Benutzer bereits für Skype für Unternehmen lokal, aktiviert ist wurde jedoch nicht für Enterprise Voice aktiviert oder einen "lineuri" zugewiesen, bevor in Skype für Business Online verschoben, führen Sie für jeden Benutzer das folgende Cmdlet aus:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Wenn ein Benutzer bereits in Skype für Unternehmen lokal aktiviert aber nicht für Enterprise-VoIP aktiviert, auch wenn bereits ein Anschluss-URI zugewiesen ist, führen Sie für jeden betroffenen Benutzer das folgende Cmdlet aus:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```



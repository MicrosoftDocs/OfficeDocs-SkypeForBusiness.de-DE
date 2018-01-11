---
title: Wie kann die Anrufer-ID in Ihrer Organisation verwendet werden
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Anrufer-ID kann mithilfe einer Richtlinie aufgerufen CallingLineIdentity für eingehende und ausgehende Anrufe für Benutzer Telefonsystem gesteuert werden."
ms.openlocfilehash: b9e889ae9d87277939e844eeb911834f466942c5
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Wie kann die Anrufer-ID in Ihrer Organisation verwendet werden

Anrufer-ID kann mithilfe einer Richtlinie aufgerufen CallingLineIdentity für eingehende und ausgehende Anrufe für Benutzer Telefonsystem gesteuert werden.
  
Die Anrufer-ID-Funktionalität ist für alle Telefonsystem Benutzer unabhängig von PSTN-Anbindung verfügbar:
  
- Online PSTN-Anbindung
    
- Der lokale PSTN-Konnektivität mit Skype für Business Cloud Connector Edition (erfordert Cloud Connector Edition 1.4.2 und höher)
    
- Der lokale PSTN-Konnektivität mit Skype für Business Server (erfordert Skype für Business Server 2015 CU5 oder höher)
    
> [!NOTE]
> Diese Richtlinie nicht in Skype für Business 2015 Server zur Verfügung. 
  
## <a name="outbound-caller-id"></a>Ausgehende Anrufer-ID

Drei Optionen stehen zur Verfügung für ausgehende PSTN-Anrufer-ID:
  
- Die Telefonnummer für den Benutzer, die Standardeinstellung zugewiesen.
    
- Eine Telefonnummer an, die als *Dienst* klassifiziert wird und *gebührenfreie* Nummer in Ihrer aufrufen plant in Office 365-Telefon nummerieren Inventar. Es ist normalerweise eine Organisationseinheit automatische Telefonzentrale oder ein Anruf Warteschlange zugewiesen.
    
- Legen Sie auf anonyme.
    
Sie können nicht jedoch Risiko dieser Arten von Telefonnummern für die ausgehende Anrufer-ID zuweisen:
  
- Alle Rufnummern, die als *Benutzer* in Ihrem Telefon aufrufen plant klassifiziert werden Zahl Inventar
    
- Eine Skype für Business Server lokale Rufnummer
    
Wenn die ausgehende Anrufer-ID festlegen möchten, finden Sie unter [Legen Sie die Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Die Kontrolle der ausgehenden Anrufer-ID

Das Attribut EnableUserOverride kann einzelne oder mehrere Benutzer ihre Anrufer-ID-Einstellung auf **Anonym**zu ändern. Dies gilt nur, wenn eine Richtlinie CallingLineIdentity mit dem Parameter CallingIDSubstitute LineURI oder Ersatz konfiguriert ist. Der Standardwert der EnableUserOverride ist False.
  
Endbenutzer können ihre Anrufer-ID mithilfe der Registerkarte **Weiterleiten Einstellungen für die** in der Skype für Business-Desktopclient auf **Anonym** festgelegt.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Version** <br/> |**Unterstützt** <br/> |
|Klick-und-Los  <br/> |Aktueller Channel die Vollversion auf 6 Dezember 2016 - 1611 (Build 7571.2072)  <br/> |Ja  <br/> |
|Klick-und-Los  <br/> |Erste Version für zurückgestellt Kanal veröffentlicht am 22 Februar 2017 - Version 1701 (Build 7766.2060)  <br/> |Ja  <br/> |
|Klick-und-Los  <br/> |Zurückgestellt Kanal veröffentlicht am 13 Juni 2017 - Version 1701 (Build 7766.2092)  <br/> |Ja  <br/> |
|MSI  <br/> |Skype for Business  <br/> |Nein  <br/> |
|Mac  <br/> |Skype for Business  <br/> |Nein  <br/> |
   
## <a name="inbound-caller-id"></a>Anrufer-ID (eingehend)

Das Attribut BlockIncomingCallerID ermöglicht die Anrufer-ID auf eingehende PSTN-Anrufe zu blockieren. Können Sie dieses Attribut festgelegt, aber es ist nicht verfügbar für die Endbenutzer auf der Seite benutzereinstellungen. Und es ist derzeit nur mit Online PSTN-Anbindung.
  
Wenn die ausgehende Anrufer-ID festlegen möchten, finden Sie unter [Legen Sie die Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Verwandte Themen
[Transferring phone numbers common questions](transferring-phone-numbers-common-questions.md)

[Verschiedene Arten von Telefonnummern für den Aufruf von plant verwendet](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Telefonnummern für Ihre Organisation verwalten](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://go.microsoft.com/fwlink/?LinkID=692099)
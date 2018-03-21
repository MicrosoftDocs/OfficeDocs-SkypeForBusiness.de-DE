---
title: "Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Anrufer-ID kann mithilfe einer Richtlinie aufgerufen CallingLineIdentity für eingehende und ausgehende Anrufe für Benutzer Telefonsystem gesteuert werden."
ms.openlocfilehash: f87718858507405e54643575825b264c6c1cbea1
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation

Anrufer-ID kann mithilfe einer Richtlinie aufgerufen CallingLineIdentity für eingehende und ausgehende Anrufe für Benutzer Telefonsystem gesteuert werden.
  
Die Anrufer-ID-Funktionalität ist für alle Telefonsystem Benutzer unabhängig von PSTN-Anbindung verfügbar:
  
- Online-PSTN-Anbindung
    
- Lokale PSTN-Anbindung mit Skype for Business Cloud Connector Edition (erfordert Cloud Connector Edition 1.4.2 oder höher)
    
- Lokale PSTN-Anbindung mit Skype for Business Server (erfordert Skype for Business Server 2015 CU5 oder höher)
    
> [!NOTE]
> Diese Richtlinie ist in Skype for Business Server 2015 nicht verfügbar. 
  
## <a name="outbound-caller-id"></a>Ausgehende Anrufer-ID

Für die ausgehende PSTN-Anrufer-ID sind drei Optionen verfügbar:
  
- Die Telefonnummer für den Benutzer, die Standardeinstellung zugewiesen.
    
- Eine Telefonnummer an, die als *Dienst* klassifiziert wird und *gebührenfreie* Nummer in Ihrer aufrufen plant in Office 365-Telefon nummerieren Inventar. Es ist normalerweise eine Organisationseinheit automatische Telefonzentrale oder ein Anruf Warteschlange zugewiesen.
    
- Auf „Anonym" festgelegt
    
Die folgenden Arten von Telefonnummern können Sie jedoch nicht als ausgehende Anrufer-ID nicht zuweisen:
  
- Alle Rufnummern, die als *Benutzer* in Ihrem Telefon aufrufen plant klassifiziert werden Zahl Inventar
    
- Lokale Skype for Business Server-Telefonnummern
    
Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Steuerung der ausgehenden Anrufer-ID durch Endbenutzer

Das Attribut EnableUserOverride kann einzelne oder mehrere Benutzer ihre Anrufer-ID-Einstellung auf **Anonym**zu ändern. Dies gilt nur, wenn eine Richtlinie CallingLineIdentity mit dem Parameter CallingIDSubstitute LineURI oder Ersatz konfiguriert ist. Der Standardwert der EnableUserOverride ist False.
  
Endbenutzer können ihre Anrufer-ID mithilfe der Registerkarte **Weiterleiten Einstellungen für die** in der Skype für Business-Desktopclient auf **Anonym** festgelegt.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Version** <br/> |**Unterstützt** <br/> |
|Klick-und-Los  <br/> |Aktueller Kanal, Veröffentlichung am 6. Dezember 2016 - Version 1611 (Build 7571.2072)  <br/> |Ja  <br/> |
|Klick-und-Los  <br/> |First Release für verzögerten Kanal, Veröffentlichung am 22. Februar 2017 - Version 1701 (Build 7766.2060)  <br/> |Ja  <br/> |
|Klick-und-Los  <br/> |Zurückgestellt Kanal veröffentlicht am 13 Juni 2017 - Version 1701 (Build 7766.2092)  <br/> |Ja  <br/> |
|MSI  <br/> |Skype for Business  <br/> |Nein  <br/> |
|Mac  <br/> |Skype for Business  <br/> |Nein  <br/> |
   
## <a name="inbound-caller-id"></a>Eingehende Anrufer-ID

Das Attribut BlockIncomingCallerID ermöglicht die Anrufer-ID auf eingehende PSTN-Anrufe zu blockieren. Können Sie dieses Attribut festgelegt, aber es ist nicht verfügbar für die Endbenutzer auf der Seite benutzereinstellungen. Außerdem ist das Attribut zurzeit nur für Online-PSTN-Anbindung verfügbar.
  
Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Verwandte Themen
[Allgemeine Fragen zum Übertragen von Telefonnummern](transferring-phone-numbers-common-questions.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://go.microsoft.com/fwlink/?LinkID=692099)
---
title: Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Anrufer-ID kann mithilfe einer Richtlinie aufgerufen CallingLineIdentity für eingehende und ausgehende Anrufe für Benutzer Telefonsystem gesteuert werden.
ms.openlocfilehash: 4ae5c54d68410096104f61bf8cdbd71fa0628003
ms.sourcegitcommit: 99bc2db8cb857b6fd2ddf9b837198be849dafb9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "29981914"
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
    
- Eine Telefonnummer, die als *Servicerufnummer* und *gebührenfreie* Nummer in Ihrem Nummernverzeichnis für Office 365-Anrufpläne klassifiziert ist. Sie wird normalerweise einer automatischen Telefonzentrale oder einer Anruf-Warteschleife Ihrer Organisation zugewiesen.
    
- Auf „Anonym" festgelegt
    
Die folgenden Arten von Telefonnummern können Sie jedoch nicht als ausgehende Anrufer-ID nicht zuweisen:
  
- Alle Rufnummern, die als *Benutzer* in Ihrem Telefon aufrufen plant klassifiziert werden Zahl Inventar
    
- Lokale Skype for Business Server-Telefonnummern
    
Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Steuerung der ausgehenden Anrufer-ID durch Endbenutzer

Mit dem Attribut EnableUserOverride können einzelne oder mehrere Benutzer ihre Anrufer-ID-Einstellung auf **Anonym** festlegen. Dies gilt nur, wenn eine CallingLineIdentity -Richtlinie mit dem CallingIDSubstitute -Parameter LineURI oder Substitute konfiguriert ist. Der Standardwert von EnableUserOverride lautet False.
  
Endbenutzer können ihre Anrufer-ID auf **Anonym** mithilfe der Registerkarte **Einstellungen** in der Skype für Business desktop Client festgelegt **Aufrufe eines Endbenutzers** (sofern durch den Administrator aktiviert), wählen **Ausblenden mein Handy Anzahl und Profil Informationen für alle Anrufe **.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Version** <br/> |**Unterstützt** <br/> |
|Klick-und-Los  <br/> |Aktueller Kanal, Veröffentlichung am 6. Dezember 2016 - Version 1611 (Build 7571.2072)  <br/> |Ja  <br/> |
|Klick-und-Los  <br/> |First Release für verzögerten Kanal, Veröffentlichung am 22. Februar 2017 - Version 1701 (Build 7766.2060)  <br/> |Ja  <br/> |
|Klick-und-Los  <br/> |Veröffentlichung im verzögerten Kanal am 13. Juni 2017 - Version 1701 (Build 7766.2092)  <br/> |Ja  <br/> |
|MSI  <br/> |Skype for Business  <br/> |Nein  <br/> |
|Mac  <br/> |Skype for Business  <br/> |Nein  <br/> |
   
## <a name="inbound-caller-id"></a>Eingehende Anrufer-ID

Mit dem Attribut BlockIncomingCallerID können Sie die Anrufer-ID Für eingehende PSTN-Anrufe blockieren. Können Sie dieses Attribut festgelegt, aber es ist nicht verfügbar für die Endbenutzer auf der Seite benutzereinstellungen. Außerdem ist das Attribut zurzeit nur für Online-PSTN-Anbindung verfügbar.
  
Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Verwandte Themen
[Allgemeine Fragen zum Übertragen von Telefonnummern](/microsoftteams/transferring-phone-numbers-common-questions)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 

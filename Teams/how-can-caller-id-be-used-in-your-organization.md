---
title: Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: Die Anrufer-ID kann sowohl für ein- als auch für ausgehende Anrufe für Telefonsystem Benutzer mithilfe einer Richtlinie namens CallingLineIdentity gesteuert werden.
ms.openlocfilehash: e723311b2780dd1d43bad4874b72133e09ff4fc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120676"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation

Die Anrufer-ID kann sowohl für ein- als auch für ausgehende Anrufe für Telefonsystem Benutzer mithilfe einer Richtlinie namens CallingLineIdentity gesteuert werden.
  
Die Anrufer-ID-Funktion steht allen Benutzern Telefonsystem pstN-Anbindung zur Verfügung:

- Microsoft-Anrufpläne 

- Direktes Routing für Telefonsysteme 
  
- Online-PSTN-Anbindung
    
- Lokale PSTN-Anbindung mit Skype for Business Cloud Connector Edition (erfordert Cloud Connector Edition 1.4.2 oder höher)
    
- Lokale PSTN-Anbindung mit Skype for Business Server (erfordert Skype for Business Server 2015 CU5 oder höher)
    
> [!NOTE]
> Diese Richtlinie ist in Skype for Business Server 2015 nicht verfügbar. 
  
## <a name="outbound-caller-id"></a>Ausgehende Anrufer-ID

Für ausgehende PSTN-Anrufer-ID sind drei Optionen verfügbar:
  
- Die dem Benutzer zugewiesene Telefonnummer (Standardeinstellung).
    
- Eine Telefonnummer, die in  Ihrem Telefonnummernbestand für Anrufpläne als Dienstnummer und *gebührenfreie* Nummer klassifiziert ist. Sie wird normalerweise einer automatischen Telefonzentrale oder einer Anruf-Warteschleife Ihrer Organisation zugewiesen.
    
- Auf „Anonym" festgelegt
    
Die folgenden Arten von Telefonnummern können Sie jedoch nicht als ausgehende Anrufer-ID nicht zuweisen:
  
- Telefonnummern, die in  Ihrem Telefonnummernbestand für Anrufpläne als Benutzer klassifiziert sind
    
- Lokale Skype for Business Server-Telefonnummern
    
Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](./set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Steuerung der ausgehenden Anrufer-ID durch Endbenutzer

Mit dem EnableUserOverride-Attribut können einzelne oder mehrere Benutzer ihre Anrufer-ID-Einstellung in **Anonym ändern.** Dies gilt nur, wenn eine CallingLineIdentity -Richtlinie mit dem CallingIDSubstitute -Parameter LineURI oder Substitute konfiguriert ist. Der Standardwert von EnableUserOverride lautet False.
  
Ihre Endbenutzer können ihre Anrufer-ID über die Registerkarte **Einstellungen** im Skype for Business-Desktopclient auf Anonym festlegen, anschließend Endbenutzer anrufen **(sofern** vom Administrator aktiviert) und dann Meine Telefonnummer und Profilinformationen für alle Anrufe ausblenden **auswählen.**  In Teams können Benutzer zu ihrem Profilbild in der oberen rechten Ecke wechseln, **Einstellungen-Anrufe** und dann unter  >   **Anrufer-ID** die Option Meine Telefonnummer und Profilinformationen für alle Anrufe ausblenden auswählen. 
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Version** <br/> |**Unterstützt** <br/> |
|Klick-und-Los  <br/> |Aktueller Kanal, Veröffentlichung am 6. Dezember 2016 - Version 1611 (Build 7571.2072)  <br/> |Ja  <br/> |
|Klick-und-Los  <br/> |First Release für verzögerten Kanal, Veröffentlichung am 22. Februar 2017 - Version 1701 (Build 7766.2060)  <br/> |Ja  <br/> |
|Klick-und-Los  <br/> |Veröffentlichung im verzögerten Kanal am 13. Juni 2017 - Version 1701 (Build 7766.2092)  <br/> |Ja  <br/> |
|MSI  <br/> |Skype for Business  <br/> |Nein  <br/> |
|Mac  <br/> |Skype for Business  <br/> |Nein  <br/> |
   
## <a name="inbound-caller-id"></a>Eingehende Anrufer-ID

Telefonsystem wird die "Anruf-ID" für eine externe Telefonnummer angezeigt, wenn die Nummer einem Benutzer in Azure AD zugeordnet ist. Wenn sich die Telefonnummer nicht in Azure AD befindet, wird der von Telco bereitgestellte Anzeigename angezeigt, sofern er verfügbar ist.

Mit dem Attribut BlockIncomingCallerID können Sie die Anrufer-ID Für eingehende PSTN-Anrufe blockieren. Sie können dieses Attribut festlegen, es steht den Endbenutzern auf der Seite mit den Benutzereinstellungen jedoch nicht zur Verfügung. Außerdem ist das Attribut zurzeit nur für Online-PSTN-Anbindung verfügbar.
  
Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](./set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Verwandte Themen
[Übertragen von Telefonnummern – häufig gestellte Fragen](./phone-number-calling-plans/port-order-overview.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  

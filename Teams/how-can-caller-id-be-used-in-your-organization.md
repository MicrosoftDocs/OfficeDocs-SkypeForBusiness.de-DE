---
title: Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: Die Anrufer-ID kann sowohl für eingehende als auch für ausgehende Anrufe für Benutzer des Telefonsystems mithilfe einer Richtlinie namens CallingLineIdentity gesteuert werden.
ms.openlocfilehash: 250f8a1a516aec4c9941b0c6396e6d44771b4f53
ms.sourcegitcommit: f608811288c82a6348a6af1671246a93ed06e578
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2022
ms.locfileid: "66660961"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation

Die Anrufer-ID besteht aus zwei vom Benutzer gerichteten Informationen:

- Eine Telefonnummer (als CLID oder Anrufleitungs-ID bezeichnet). Dies ist die PSTN-Nummer (Public Switched Telephone Network), die als Identifikation des Anrufers angezeigt wird.

- Ein Anrufername (in der Regel als CNAM bezeichnet). 
  
Die Anrufer-ID-Funktion steht allen Benutzern des Telefonsystems unabhängig von der [PSTN-Konnektivitätsoption](pstn-connectivity.md) zur Verfügung: Microsoft-Anrufplan, Telefonieanbieter oder Direct Routing. 
  
Sie können die Anrufer-ID für eingehende und ausgehende Anrufe mithilfe einer Richtlinie namens CallingLineIdentity steuern. Weitere Informationen finden Sie unter ["Weitere Informationen zu Anrufleitungs-ID und Anrufername"](more-about-calling-line-id-and-calling-party-name.md).

  
## <a name="outbound-pstn-caller-id"></a>Ausgehende PSTN-Anrufer-ID

Für die ausgehende PSTN-Anrufer-ID stehen die folgenden Optionen zur Verfügung. 
  
- Die dem Benutzer zugewiesene Telefonnummer, was die Standardeinstellung ist.

- Anonym, die durch Entfernen der Darstellung der PSTN-Nummer des Benutzers verfügbar ist. 

- Eine Ersatztelefonnummer, die folgende sein kann:

  - Eine Telefonnummer, die als Service und gebührenfreie Nummer im Telefonnummernbestand Ihrer Anrufpläne klassifiziert ist. Es wird einer automatischen Teams-Telefonzentrale oder Anrufwarteschleife zugewiesen.

  - Eine lokale Telefonnummer über Direct Routing, die einem Ressourcenkonto zugewiesen ist, das von einer automatischen Teams-Telefonzentrale oder Anrufwarteschleife verwendet wird. 

- Der Für den ausgehenden PSTN-Anruf festgelegte Name oder CNAM der anruferischen Partei.  
    
Weitere Informationen finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](./set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Endbenutzersteuerelement für ausgehende Anrufer-ID

Benutzer können ihre Anrufer-ID-Einstellung in **"Anonym** " ändern, indem sie das EnableUserOverride-Attribut festlegen. 

Wenn die ausgehende Anrufer-ID auf "Anonym" festgelegt ist, hat EnableUserOverride keine Auswirkung, und die Anrufer-ID ist immer auf "Anonym" festgelegt. Der Standardwert von EnableUserOverride lautet False.

Ihre Endbenutzer können ihre Anrufer-ID auf "Anonym" festlegen, indem sie zu **"Einstellungen > Anrufe**" wechseln und dann unter " **Anrufer-ID**" **die Option "Meine Telefonnummer und Profilinformationen für alle Anrufe ausblenden**" auswählen. Es dauert einige Minuten, bis diese Einstellungsänderung neue Anrufe widerspiegelt. 

### <a name="notes"></a>Hinweise

Berücksichtigen Sie dabei Folgendes:

- Sie können die folgenden Arten von Telefonnummern für die ausgehende Anrufer-ID nicht zuweisen:

  - Alle Telefonnummern, die als Benutzer im Telefonnummernbestand Ihrer Anrufpläne klassifiziert sind.

  - Jede lokale Telefonnummer über Direct Routing, die einem Benutzer zugewiesen ist.

  - Eine Skype for Business Server lokale Telefonnummer.

- Die Verwendung der Ressourcenkonto-Telefonnummernersetzung funktioniert für Teams-Benutzer. Die Ersetzung der Diensttelefonnummer funktioniert für Teams-Benutzer.

- Der Anrufername wird bei Anrufen gesendet, bei denen die Anrufer-ID durch LineUri, eine Dienst- oder Ressourcenkontotelefonnummer ersetzt wird und wenn der Anrufer ein Teams-Benutzer ist.

- Der Name der aufrufenden Partei kann maximal 200 Zeichen enthalten, nachgeschaltete Systeme unterstützen jedoch möglicherweise weniger Zeichen.

- Bei Direct Routing werden die Telefonnummernersetzung und der Name der anrufenden Partei im FROM-SIP-Header gesendet. Wenn das entsprechende OnlinePstnGateway mit ForwardPai = True konfiguriert ist, enthält der P-ASSERTED-IDENTITY SIP-Header den tatsächlich aufrufenden Benutzer.

- EnableUserOverride hat Vorrang vor anderen Einstellungen in der Richtlinie – es sei denn, die Ersetzung ist auf "Anonym" festgelegt. Angenommen, die Richtlinieninstanz ersetzt ein Ressourcenkonto, und EnableUserOverride wird vom Benutzer festgelegt und aktiviert. In diesem Fall wird die ausgehende Anrufer-ID blockiert und "Anonym" verwendet. Wenn für eine Richtlinieninstanz die Ersetzung auf "Anonym" festgelegt ist und "EnableUserOverride" festgelegt ist, ist die ausgehende Anrufer-ID immer "Anonym", unabhängig von der Einstellung des Endbenutzers.

   
## <a name="inbound-caller-id"></a>Eingehende Anrufer-ID

Das Telefonsystem zeigt die eingehende externe Telefonnummer als Anrufer-ID an. Wenn die Nummer einem Benutzer oder Kontakt in Azure AD oder einem persönlichen Kontakt zugeordnet ist, zeigt der Skype for Business- und Teams-Clients die Anrufer-ID basierend auf diesen Informationen an. Wenn sich die Telefonnummer nicht in Azure AD oder einem persönlichen Kontakt befindet, wird der von telco bereitgestellte Anzeigename angezeigt, wenn er verfügbar ist.

Mit dem Attribut BlockIncomingCallerID können Sie die Anrufer-ID Für eingehende PSTN-Anrufe blockieren. Sie können dieses Attribut festlegen, aber es steht Ihren Endbenutzern auf der Seite mit den Benutzereinstellungen nicht zur Verfügung. Wenn diese Einstellung aktiviert ist, wird der eingehende PSTN-Anrufer als von "Anonym" stammend angezeigt.
  
Informationen zum Blockieren der eingehenden Anrufer-ID finden [Sie unter Festlegen der Anrufer-ID für einen Benutzer](./set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Verwandte Themen
[Übertragen von Telefonnummern – häufig gestellte Fragen](./phone-number-calling-plans/port-order-overview.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  

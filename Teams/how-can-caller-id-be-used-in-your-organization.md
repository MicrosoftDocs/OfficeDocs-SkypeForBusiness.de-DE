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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: Die Anrufer-ID kann sowohl für ein- als auch für ausgehende Anrufe für Telefonsystem Benutzer mithilfe einer Richtlinie namens CallingLineIdentity gesteuert werden.
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723546"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation

Die Anrufer-ID besteht aus zwei identifizierbaren Informationen für den Benutzer:

- Eine Telefonnummer (in der Regel als RUFNUMMER oder Anrufleitungs-ID bezeichnet). Dies ist die öffentlich geschaltete Telefonnummer (PSTN), die als Identifizierung des Anrufers dargestellt wird.

- Ein Name der Anruferparty (üblicherweise auch als "CNAM" bezeichnet). 
  
Die Anrufer-ID-Funktion steht allen Benutzern Telefonsystem pstn connectivity zur Verfügung, unabhängig von der PstN-Konnektivitätsoption:

- Microsoft-Anrufpläne 

- Direktes Routing für Telefonsysteme 
  
Sie können die Anrufer-ID für ein- und ausgehende Anrufe mithilfe einer Richtlinie namens CallingLineIdentity steuern. Weitere Informationen finden Sie unter [Weitere Informationen zu Anrufleitungs-ID und Anrufername.](more-about-calling-line-id-and-calling-party-name.md)

  
## <a name="outbound-pstn-caller-id"></a>Ausgehende PSTN-Anrufer-ID

Für die ausgehende PSTN-Anrufer-ID sind die folgenden Optionen verfügbar. 
  
- Die dem Benutzer zugewiesene Telefonnummer (Standardeinstellung).

- Anonym, der verfügbar ist, indem die Präsentation der PSTN-Nummer des Benutzers entfernt wird. 

- Eine Ersatztelefonnummer, die:

  - Eine Telefonnummer, die in Ihrem Telefonnummernbestand für Anrufpläne als Dienstnummer und gebührenfreie Nummer klassifiziert ist. Sie wird in der Regel einem Teams automatische Telefonzentrale oder einer Anrufwarteschleife zugewiesen.

  - Eine lokale Telefonnummer über Direct-Routing, die einem Ressourcenkonto zugeordnet ist, das von einem Benutzer oder Teams automatische Telefonzentrale Anrufwarteschleife verwendet wird. 

- Der Name der Anrufenden Partei oder das CNAM, der für den ausgehenden PSTN-Anruf festgelegt ist.  
    
Weitere Informationen finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer.](./set-the-caller-id-for-a-user.md)
  
### <a name="end-user-control-of-outbound-caller-id"></a>Steuerung der ausgehenden Anrufer-ID durch Endbenutzer

Benutzer können ihre Anrufer-ID-Einstellung in **Anonym ändern,** indem sie das EnableUserOverride-Attribut festlegen. 

Wenn die ausgehende Anrufer-ID auf Anonym festgelegt ist, hat EnableUserOverride keine Auswirkung, und die Anrufer-ID ist immer auf Anonym festgelegt. Der Standardwert von EnableUserOverride lautet False.

Ihre Endbenutzer können ihre Anrufer-ID auf Anonym festlegen, indem Sie **zu Einstellungen >-Anrufe** und dann unter **Anrufer-ID** die Option Meine Telefonnummer und Profilinformationen für alle Anrufe ausblenden **auswählen.**

### <a name="notes"></a>Hinweise

Berücksichtigen Sie dabei Folgendes:

- Sie können der ausgehenden Anrufer-ID nicht die folgenden Arten von Telefonnummern zuweisen:

  - Telefonnummern, die in Ihrem Telefonnummernbestand für Anrufpläne als Benutzer klassifiziert sind.

  - Eine lokale Telefonnummer über Direct Routing, die einem Benutzer zugewiesen ist.

  - Eine Skype for Business Server eine lokale Telefonnummer.

- Das Ersetzen von Telefonnummern des Ressourcenkontos funktioniert nur für Teams Benutzer. Das Ersetzen der Servicetelefonnummer funktioniert sowohl für Skype for Business Online als Teams Benutzer.

- Der Anrufername wird nur für Anrufe gesendet, bei denen die Anrufer-ID durch LineUri, die Telefonnummer eines Diensts oder Ressourcenkontos ersetzt wird und der Anrufer ein Teams ist.

- Anrufername kann maximal 200 Zeichen umfassen, doch downstream-Systeme unterstützen möglicherweise weniger Zeichen.

- Beim direkten Routing werden die Telefonnummernersetzung und der Name der Anrufergruppe in der FROM SIP-Kopfzeile gesendet. Wenn das entsprechende OnlinePstnGateway mit ForwardPai = True konfiguriert ist, enthält der SIP-Header P-ASSERTED-IDENTITY den tatsächlich aufrufenden Benutzer.

- EnableUserOverride hat Vorrang vor anderen Einstellungen in der Richtlinie , es sei denn, die Ersetzung ist auf Anonym festgelegt. Angenommen, die Richtlinieninstanz wurde durch ein Ressourcenkonto ersetzt, und EnableUserOverride wird vom Benutzer festgelegt und aktiviert. In diesem Fall wird die ausgehende Anrufer-ID blockiert und Anonym verwendet. Wenn für eine Richtlinieninstanz die Ersetzung auf Anonym und EnableUserOverride festgelegt ist, wird die ausgehende Anrufer-ID unabhängig von der Endbenutzereinstellung immer anonym festgelegt.

   
## <a name="inbound-caller-id"></a>Eingehende Anrufer-ID

Telefonsystem wird die eingehende externe Telefonnummer als Anrufer-ID anzeigen. Wenn die Nummer einem Benutzer oder Kontakt in Azure AD oder einem persönlichen Kontakt zugeordnet ist, zeigt der Skype for Business- und Teams-Client die Anrufer-ID basierend auf diesen Informationen an. Wenn sich die Telefonnummer nicht in Azure AD oder einem persönlichen Kontakt befindet, wird der von Telco bereitgestellte Anzeigename angezeigt, sofern er verfügbar ist.

Mit dem Attribut BlockIncomingCallerID können Sie die Anrufer-ID Für eingehende PSTN-Anrufe blockieren. Sie können dieses Attribut festlegen, es steht den Endbenutzern auf der Seite mit den Benutzereinstellungen jedoch nicht zur Verfügung. Wenn diese Einstellung aktiviert ist, wird der eingehende PSTN-Anrufer als "Anonym" angezeigt.
  
Informationen zum Blockieren der eingehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer.](./set-the-caller-id-for-a-user.md)
  
## <a name="related-topics"></a>Verwandte Themen
[Übertragen von Telefonnummern – häufig gestellte Fragen](./phone-number-calling-plans/port-order-overview.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  

---
title: Direct Routing – Verbinden analoger Geräte
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lesen Sie diesen Artikel, um zu erfahren, wie Sie analoge Geräte mit Microsoft-Telefon Direct-Routing verwenden.
ms.openlocfilehash: dc49c22dceffda6905d1f57652fd14d584d02cf6
ms.sourcegitcommit: 9d446485aa842abbdcd34d946b247166c2bf1610
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52642095"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>Verwenden analoger Geräte mit Telefonsystem Direct-Routing

In diesem Artikel wird beschrieben, wie Sie analoge Geräte mit Telefonsystem Direct-Routing verwenden. Um analoge Geräte mit Direct Routing zu verbinden, müssen Sie einen ANALOGen Telefonieadapter (ANALOG Telephony Adapter, ATA) verwenden. Dieser Adapter muss vom SBC-Anbieter (Session Border Controller) unterstützt werden. 

Wenn ein Benutzer von einem analogen Gerät aus anruft, werden die Signalisierung und der Medienfluss über den Analog Telephony Adapter (ATA) zum SBC übertragen.  Der SBC sendet den Anruf basierend auf der internen Routingtabelle an einen Microsoft Teams-Endpunkt oder an das Public Switched Telephone Network (PSTN).  Wenn ein Gerät einen Anruf abnimmt, hängt die Route, die es verwendet, von den für das Gerät erstellten Routingrichtlinien ab.

Im folgenden Diagramm ist Direct Routing so konfiguriert, dass alle Teams-Anrufe an und von den Nummern zwischen +1425 4XX XX XX und +1425 5XX XX xx die rote Route (gepunktete Linie) und alle PSTN-Anrufe an und von Nummern zwischen +1425 4XX XX XX und allen anderen Nummern außer dem Zahlenbereich +1425 5XX XX die blaue Route (durchfarbige Linie) verwenden müssen. 

> [!div class="mx-imgBorder"]
> ![Diagramm, das die Konfiguration des direkten Routings zeigt](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Beispiel: Konfigurieren der Verwendung analoger Geräte mit Direct Routing

Um die Verwendung analoger Geräte mit Direct-Routing zu konfigurieren, müssen Sie den Analog-Telefonieadapter mit dem SBC verbinden und den SBC für die Verwendung von Direct-Routing konfigurieren. 

Dieses Beispiel führt Sie durch die folgenden Schritte:

1. Verbinden von SBC zu Direct-Routing.
2. Erstellen Sie die PSTN-Nutzung.
3. Erstellen Sie eine Sprachroute, und ordnen Sie sie der PSTN-Nutzung zu.
4. Weisen Sie die Sprachroute der PSTN-Nutzung zu.
5. Aktivieren Sie den Onlinebenutzer.
6. Weisen Sie dem Benutzer die Voiceroute-Richtlinie zu.
7. Erstellen Sie eine Sprachroute für ein analoges Gerät.

Informationen zum Verbinden eines ATA mit einem SBC und konfigurieren des SBC finden Sie im Konfigurationshandbuch des SBC-Herstellers:

- [AudioCodes-Konfigurationsdokumentation](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [Dokumentation zur Menübandkonfiguration](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Oracle-Konfigurationsdokumentation](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>Schritt 1:  Verbinden von SBC zu Direct Routing

Mit dem folgenden Befehl wird die SBC-Verbindung wie folgt konfiguriert:

- FQDN-sbc.contoso.com
- Signalisierungsport 5068
- Medienumgehungsmodus
- Anrufverlaufsinformationen, die an die SBC-
- Header "P-Asserted-Identity", WEITERLEITEN, der zusammen mit dem Aufruf weitergeleitet wurde 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>Schritt 2: Erstellen der PSTN-Nutzung 

Mit dem nächsten Befehl wird eine leere PSTN-Verwendung erstellt. Online-PSTN-Verwendungen sind Zeichenfolgenwerte, die für die Anrufautorisierung verwendet werden. Eine Online-PSTN-Nutzung verknüpft eine Online-Sprachrichtlinie mit einer Route. In diesem Beispiel wird der aktuellen Liste der verfügbaren PSTN-Verwendungen die Zeichenfolge "Interop" hinzugefügt. 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Schritt 3: Erstellen einer Sprachroute und Zuordnen der Route zur PSTN-Nutzung:

Mit diesem Befehl wird eine neue Online-Sprachroute mit der Identität "Analog-Inop" für den Zahlenbereich +1425 XXX XX XX erstellt.  Die Sprachroute gilt für eine Liste von Onlinegateways sbc.contoso.com und ordnet die Route der Online-PSTN-Nutzung "Inop" zu. Eine Sprachroute enthält einen regulären Ausdruck, der annennt, welche Telefonnummern über eine bestimmte Sprachroute geroutet werden:

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Schritt 4: Zuweisen der Sprachroute zur PSTN-Nutzung:

Mit diesem Befehl wird eine neue Online-Voiceroutingrichtlinie für Benutzer mit der Identität "AnalogInteropPolicy" erstellt. Dieser Richtlinie wird eine einzige Online-PSTN-Verwendung zugewiesen: "Inop".

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Schritt 5: Aktivieren des Onlinebenutzers

Mit diesem Befehl wird das Benutzerkonto mit dem Identitätskonto exampleuser@contoso.com. In diesem Fall wird das Konto so geändert, dass Enterprise-VoIP, die Microsoft-Implementierung von VoIP, mit aktivierter Voicemail aktiviert wird und diesem Benutzer die Nummer +14255000000 zugewiesen wird.  Dieser Befehl sollte für jeden benutzer Teams (mit Ausnahme von ATA-Gerätebenutzern) im Mandanten Ihres Unternehmens ausgeführt werden.

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Schritt 6: Zuweisen der Sprachroutenrichtlinie zu einem Benutzer

Dieser Befehl weist dem Benutzer die AnalogInteropPolicy-Richtlinie für Online-Voicerouting mit der Identität exampleuser@contoso.com.  Dieser Befehl sollte für jeden benutzer Teams (mit Ausnahme von ATA-Gerätebenutzern) im Mandanten Ihres Unternehmens ausgeführt werden.

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>Schritt 7: Erstellen einer Sprachroute für ein analoges Gerät

Dieser Befehl erstellt eine Online-Sprachroute mit der Identität "Analog-Inop" für den Zahlenbereich +1425 4XX XX, der auf eine Liste von Onlinegateways sbc.contoso.com anwendbar ist, und ordnet ihn der Online-PSTN-Verwendung "Inop" zu.  Dieser Befehl sollte für jedes analoge Gerät mit dem entsprechenden Telefonnummernmuster ausgeführt werden. Alternativ kann ein geeignetes Zahlenmuster für analoge Geräte verwendet werden, während die Online-Voiceroute in einem der vorherigen Schritte konfiguriert wird.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Überlegungen

- Sofern nicht anders angegeben, ist ein analoges Gerät ein Gerät, das DTMF-Ziffern senden kann, um einen Anruf zu starten. Zum Beispiel analoge Telefone, Faxgeräte und Mehrseiten.

- Analoge Telefone, die mit einem ATA verbunden sind, können von ihrem Gerät aus Teams. Teams müssen die dem Gerät zugeordnete Telefonnummer manuell eingeben, um das Gerät anrufen zu können.  
 

## <a name="see-also"></a>Mehr dazu

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)

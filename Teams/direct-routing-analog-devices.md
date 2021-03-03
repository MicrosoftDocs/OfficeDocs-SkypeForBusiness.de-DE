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
description: In diesem Artikel erfahren Sie, wie Sie analoge Geräte mit Microsoft Phone System Direct Routing verwenden.
ms.openlocfilehash: 855bf0dd21659c43037b6171f523983d67c4e755
ms.sourcegitcommit: 1889ca28b9cb952b13c84efa3588957a327f9702
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841486"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>So wird's mit analogen Geräten mit dem direkten Telefonsystemrouting

In diesem Artikel wird beschrieben, wie Analoggeräte mit dem direkten Routing des Telefonsystems verwendet werden. Um analoge Geräte mit direct Routing zu verbinden, müssen Sie einen ANALOGen Telefonieadapter (ATA) verwenden. Dieser Adapter muss vom Anbieter des zertifizierten Session Border Controllers (SBC) unterstützt werden. 

Wenn ein Benutzer von einem analogen Gerät aus anruft, fließen die Signalisierung und die Medien über den ANALOGen Telefonieadapter (ATA) zum SBC.  Der SBC sendet den Anruf basierend auf der internen Routingtabelle an einen Microsoft Teams-Endpunkt oder an das Public Switched Telephone Network (PSTN).  Wenn ein Gerät einen Anruf anruft, hängt die route, die es verwendet, von den routingrichtlinien ab, die für das Gerät erstellt wurden.

Im folgenden Diagramm ist "Direktes Routing" so konfiguriert, dass alle Anrufe an und von den Nummern zwischen +1425 4XX XX XX und +1425 5XX XX XX rot (gepunktete Linie) und alle Anrufe zwischen +1425 4XX und allen anderen Nummern außer Nummernbereich +1425 5XX XX XX die blaue Route (einfarbige Linie) verwenden müssen. 

> [!div class="mx-imgBorder"]
> ![Diagramm, das die Konfiguration des direkten Routings zeigt](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Beispiel: Konfigurieren der Verwendung analoger Geräte mit Direct Routing

Um die Verwendung analoger Geräte mit Direct Routing zu konfigurieren, müssen Sie den Analog Telephony Adapter mit dem SBC verbinden und den SBC für die Verwendung mit Direct Routing konfigurieren. 

Dieses Beispiel führt Sie durch die folgenden Schritte:

1. Verbinden sie den SBC mit direct-Routing.
2. Erstellen Sie die PSTN-Verwendung.
3. Erstellen Sie eine Sprachroute, und ordnen Sie sie der PstN Usage zu.
4. Weisen Sie die Sprachroute der PSTN Usage zu.
5. Aktivieren Sie den Onlinebenutzer.
6. Weisen Sie dem Benutzer die Sprachroutenrichtlinie zu.
7. Erstellen Sie eine Sprachroute für ein analoges Gerät.

Informationen zum Verbinden eines ATA mit einem SBC und konfigurieren des SBC finden Sie im Konfigurationshandbuch des SBC-Herstellers:

- [Konfigurationsdokumentation zu AudioCodes](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [Konfigurationsdokumentation zum Menüband](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Dokumentation zur Oracle-Konfiguration](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>Schritt 1:  Verbinden des SBC mit direct Routing

Mit dem folgenden Befehl wird die SBC-Verbindung wie folgt konfiguriert:

- FQDN-sbc.contoso.com
- Signalisierungsport 5068
- Medienumgehungsmodus
- Anrufverlaufsinformationen, die an die
- Header "P-Asserted-Identity (ODER)" wird zusammen mit dem Anruf weitergeleitet 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>Schritt 2: Erstellen der PstN-Verwendung 

Der nächste Befehl erstellt eine leere PSTN-Verwendung. Online-PSTN-Verwendungen sind Zeichenfolgenwerte, die für die Anrufautorisierung verwendet werden. Eine Online-PSTN-Verwendung verknüpft eine Online-Sprachrichtlinie mit einer Route. In diesem Beispiel wird der aktuellen Liste der verfügbaren PstN-Nutzungen die Zeichenfolge "Interop" hinzugefügt. 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Schritt 3: Erstellen einer Sprachroute und Zuordnen dieser Route zur PSTN-Verwendung:

Dieser Befehl erstellt eine neue Online-Sprachroute mit der Identität "analog-inop" für den Zahlenbereich +1425 XXX XX XX.  Die Sprachroute gilt für eine Liste der Onlinegateways sbc.contoso.com und ordnet die Route der Online-PSTN-Verwendung "Inop" zu. Eine Sprachroute enthält einen regulären Ausdruck, mit dem angegeben wird, welche Telefonnummern über eine bestimmte Sprachroute geroutet werden:

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Schritt 4: Zuweisen der Sprachroute zur PSTN-Nutzung:

Mit diesem Befehl wird eine neue Online-Sprachroutingrichtlinie pro Benutzer mit der Identität "AnalogInteropPolicy" erstellt. Dieser Richtlinie wird eine einzige Online-PSTN-Verwendung zugewiesen: "Inop".

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Schritt 5: Aktivieren des Onlinebenutzers

Mit diesem Befehl wird das Benutzerkonto mit dem Identitätskonto exampleuser@contoso.com. In diesem Fall wird das Konto geändert, um Enterprise-VoIP, die Microsoft-Implementierung von VoIP, mit aktivierter Voicemail zu aktivieren, und weist diesem Benutzer die Nummer +14255000000 zu.  Dieser Befehl sollte für jeden Benutzer von Teams (mit Ausnahme von ATA-Gerätebenutzern) im Mandanten des Unternehmens ausgeführt werden.

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Schritt 6: Zuweisen der Sprachroutenrichtlinie zu einem Benutzer

Mit diesem Befehl wird die Online-Voiceroutingrichtlinie analogInteropPolicy pro Benutzer dem Benutzer mit der exampleuser@contoso.com.  Dieser Befehl sollte für jeden Benutzer von Teams (mit Ausnahme von ATA-Gerätebenutzern) im Mandanten des Unternehmens ausgeführt werden.

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>Schritt 7: Erstellen einer Sprachroute für ein analoges Gerät

Dieser Befehl erstellt eine Online-Sprachroute mit der Identität "analog-inop" für den Nummernbereich +1425 4XX XX XX, der auf eine Liste von Onlinegateways sbc.contoso.com anwendbar ist, und ordnet ihn der Online-PSTN-Verwendung "Interop" zu.  Dieser Befehl sollte für jedes analoge Gerät mit dem entsprechenden Telefonnummernmuster ausgeführt werden. Alternativ kann bei der Konfiguration der Online-Voiceroute während eines der vorherigen Schritte ein geeignetes Nummernmuster für analoge Geräte verwendet werden.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Überlegungen

- Sofern nicht anders angegeben, ist ein analoges Gerät jedes Gerät, das MFV-Ziffern senden kann, um einen Anruf zu starten. Beispiele hierin sind Analogtelefone, Faxgeräte und Overheadseiten.

- Analoge Telefone, die mit einem ATA verbunden sind, können in Teams nicht durchsucht werden. Benutzer von Teams müssen die dem Gerät zugeordnete Telefonnummer manuell eingeben, um das Gerät anrufen zu können.  
 

## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)

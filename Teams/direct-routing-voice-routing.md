---
title: Konfigurieren des Sprachroutings für Direct Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie das Sprachrouting mit Microsoft Phone System Direct Routing konfigurieren.
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383979"
---
# <a name="configure-voice-routing-for-direct-routing"></a>Konfigurieren des Sprachroutings für Direct Routing

In diesem Artikel wird beschrieben, wie Sie voice routing für Telefonsystem-Direct-Routing konfigurieren.  Dies ist Schritt 3 der folgenden Schritte zum Konfigurieren von Direct Routing:

- Schritt 1: [Verbinden des SBC mit Microsoft Phone System und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md) 
- Schritt 2: [Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail](direct-routing-enable-users.md)
- **Schritt 3. Konfigurieren des Sprachroutings** (In diesem Artikel)
- Schritt 4: [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md) 

Informationen zu allen schritten, die zum Einrichten von Direct Routing erforderlich sind, finden Sie unter [Konfigurieren von Direct Routing](direct-routing-configure.md).

## <a name="voice-routing-overview"></a>Übersicht über das Sprachrouting

Microsoft Phone System verfügt über einen Routingmechanismus, der es ermöglicht, einen Anruf an einen bestimmten Session Border Controller (SBC) zu senden, basierend auf: 

- Das so genannte Zahlenmuster 
- Das aufgerufene Nummernmuster plus der spezifische Benutzer, der den Anruf abn
 
SBCs können als aktiv und als Sicherung festgelegt werden. Wenn der als aktiv konfigurierte SBC für eine bestimmte Anrufroute nicht verfügbar ist, wird der Anruf an einen Sicherungs-SBC geroutet.
 
Das Sprachrouting besteht aus den folgenden Elementen: 

- **Voice routing policy** – Ein Container für PSTN-Verwendungen, der einem Benutzer oder mehreren Benutzern zugewiesen werden kann. 

- **PSTN-Verwendungen** – Ein Container für Sprachrouten und PSTN-Nutzungen, der in verschiedenen Sprachroutingrichtlinien freigegeben werden kann. 

- **Sprachrouten** – Ein Nummernmuster und eine Reihe von Online-PSTN-Gateways, die für Anrufe verwendet werden können, bei denen die Anrufnummer dem Muster entspricht.

- **Online-PSTN-Gateway** : Ein Zeiger auf einen SBC, der auch die Konfiguration speichert, die angewendet wird, wenn ein Anruf über den SBC platziert wird, z. B. Forward P-Asserted-Identity (PAA) oder Bevorzugte Codecs; können zu Sprachrouten hinzugefügt werden.

## <a name="voice-routing-policy-considerations"></a>Überlegungen zur Sprachroutingrichtlinie

Wenn ein Benutzer über eine Anrufplanlizenz verfügt, werden die ausgehenden Anrufe des Benutzers automatisch über die Microsoft Calling Plan PSTN-Infrastruktur geroutet. Wenn Sie eine Online-Voiceroutingrichtlinie für einen Anrufplanbenutzer konfigurieren und zuweisen, werden die ausgehenden Anrufe dieses Benutzers überprüft, um festzustellen, ob die gewählte Nummer einem in der Online-Voiceroutingrichtlinie definierten Zahlenmuster entspricht. Wenn eine Übereinstimmung vor liegt, wird der Anruf über den Direct Routing-Trunk geroutet. Wenn keine Übereinstimmung besteht, wird der Anruf über die PSTN-Infrastruktur des Anrufplans geroutet.

> [!CAUTION]
> Wenn Sie die globale (organisationsweite Standard-) Online-Voiceroutingrichtlinie konfigurieren und anwenden, erben alle sprachfähigen Benutzer in Ihrer Organisation diese Richtlinie, was dazu führen kann, dass PSTN-Anrufe von Anrufplanbenutzern versehentlich an einen Direct Routing-Trunk geroutet werden. Wenn Sie nicht möchten, dass alle Benutzer die globale Online-Voiceroutingrichtlinie verwenden, konfigurieren Sie eine benutzerdefinierte Online-Voiceroutingrichtlinie, und weisen Sie sie einzelnen sprachfähigen Benutzern zu.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Beispiel 1: Sprachrouting mit einer PSTN-Verwendung

Das folgende Diagramm zeigt zwei Beispiele für Sprachroutingrichtlinien in einem Anruffluss.

**Anruffluss 1 (links):** Wenn ein Benutzer +1 425 XXX XX XX oder +1 206 XXX XX XX anruft, wird der Anruf an SBC sbc1.contoso.biz oder sbc2.contoso.biz. Wenn weder sbc1.contoso.biz noch sbc2.contoso.biz verfügbar sind, wird der Anruf verworfen. 

**Anruffluss 2 (rechts):** Wenn ein Benutzer +1 425 XXX XX XX oder +1 206 XXX XX XX anruft, wird der Anruf zuerst an SBC sbc1.contoso.biz oder sbc2.contoso.biz. Wenn keiner der beiden SBC-Daten verfügbar ist, wird die Route mit der niedrigeren Priorität ausprobiert (sbc3.contoso.biz und sbc4.contoso.biz). Wenn keine der SBCs verfügbar ist, wird der Anruf verworfen. 

![Beispiele für Sprachroutingrichtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

In beiden Beispielen werden der Sprachroute Prioritäten zugewiesen, während die SBCs in den Routen in zufälliger Reihenfolge ausprobiert werden.

  > [!NOTE]
  > Sofern der Benutzer nicht auch über eine Microsoft Calling Plan-Lizenz verfügt, werden Aufrufe einer beliebigen Zahl außer Nummern, die den Mustern +1 425 XXX XX XX oder +1 206 XXX XX XX in der Beispielkonfiguration übereinstimmen, verworfen. Wenn der Benutzer über eine Anrufplanlizenz verfügt, wird der Anruf automatisch gemäß den Richtlinien des Microsoft-Anrufplans geroutet. Der Microsoft-Anrufplan gilt automatisch als letzte Route für alle Benutzer mit der Microsoft Calling Plan-Lizenz und erfordert keine zusätzliche Anrufroutingkonfiguration.

Im im folgenden Diagramm dargestellten Beispiel wird eine Sprachroute hinzugefügt, um Anrufe an alle anderen US- und kanadischen Nummern zu senden (Anrufe, die zum so genannten Zahlenmuster +1 XXX XXX XX XX gehen).

![Zeigt die Sprachroutingrichtlinie mit einer dritten Route an.](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Bei allen anderen Anrufen wird die automatische Route verwendet, wenn ein Benutzer über beide Lizenzen (Microsoft Phone System und Microsoft Calling Plan) verfügt. Wenn nichts den Nummernmustern in den vom Administrator erstellten Online-Sprachrouten entspricht, wird der Anruf über den Microsoft-Anrufplan geroutet. Wenn der Benutzer nur über Microsoft Phone System verfügt, wird der Anruf verworfen, da keine übereinstimmenden Regeln verfügbar sind.

  > [!NOTE]
  > Der Wert "Priorität" für die Route "Sonstige +1" spielt in diesem Fall keine Rolle, da es nur eine Route gibt, die dem Muster +1 XXX XXX XX XX entspricht. Wenn ein Benutzer +1 324 567 89 89 anruft und sbc5.contoso.biz und sbc6.contoso.biz nicht verfügbar sind, wird der Anruf verworfen.

In der folgenden Tabelle ist die Konfiguration mit drei Sprachrouten zusammengefasst. In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Nutzung, "USA und Kanada".  Alle Routen sind der PSTN-Nutzung "USA und Kanada" zugeordnet, und die PSTN-Verwendung ist der Sprachroutingrichtlinie "NUR USA" zugeordnet.

|**PSTN-Verwendung**|**Sprachroute**|**Nummernmuster**|**Priorität**|**SBC**|**Beschreibung**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|USA und Kanada|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Aktive Route für aufgerufene Zahlen +1 425 XXX XX XX oder +1 206 XXX XX XX|
|USA und Kanada|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Sicherungsroute für aufgerufene Zahlen +1 425 XXX XX XX oder +1 206 XXX XX XX|
|USA und Kanada|"Sonstiges +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route für aufgerufene Zahlen +1 XXX XXX XX XX XX (außer +1 425 XXX XX XX oder +1 206 XXX XX XX)|
|||||||

## <a name="example-1-configuration-steps"></a>Beispiel 1: Konfigurationsschritte

Im folgenden Beispiel wird gezeigt, wie Sie:

1. Erstellen Sie eine einzelne PSTN-Verwendung.
2. Konfigurieren Sie drei Sprachrouten.
3. Erstellen Sie eine Sprachroutingrichtlinie.
4. Weisen Sie die Richtlinie einem Benutzer namens "Spencer Low" zu.

Sie können das [Microsoft Teams Admin Center](#admincenterexample1) oder [PowerShell verwenden,](#powershellexample1) um diese Schritte durchzuführen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Schritt 1: Erstellen der PSTN-Verwendung "USA und Kanada"

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Voice** Direct Routing, und wählen Sie dann in der oberen rechten Ecke  >  PstN-Nutzungsdatensätze **verwalten aus.**
2. Klicken **Sie auf Hinzufügen,** geben Sie **USA und Kanada** ein, und klicken Sie dann auf **Übernehmen.**

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Schritt 2: Erstellen von drei Sprachrouten (Redmond 1, Redmond 2 und Sonstige +1)

In den folgenden Schritten wird beschrieben, wie Sie eine Sprachroute erstellen. Verwenden Sie diese Schritte, um die drei Sprachrouten Redmond 1, Redmond 2 und Other +1 für dieses Beispiel mithilfe der in der früheren Tabelle beschriebenen Einstellungen zu erstellen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Voice** Direct Routing, und wählen Sie dann die Registerkarte  >   **Voicerouten** aus.
2. Klicken **Sie auf** Hinzufügen , und geben Sie dann einen Namen und eine Beschreibung für die Sprachroute ein.
3. Legen Sie die Priorität fest, und geben Sie das Gewählte Zahlenmuster an.
4. Um einen SBC mit der Sprachroute zu registrieren, klicken Sie unter **registrierten SBCs (optional)** auf SBCs hinzufügen, wählen Sie die zu registrierende **SBCs** aus, und klicken Sie dann auf **Übernehmen**.
5. Zum Hinzufügen von PSTN-Nutzungsdatensätzen klicken Sie unter **PSTN-Nutzungsdatensätze (optional)** auf **PstN-Nutzung** hinzufügen, wählen Sie die pstN-Einträge aus, die Sie hinzufügen möchten, und klicken Sie dann auf **Übernehmen**.
6. Klicken Sie auf **Speichern**.

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Schritt 3: Erstellen einer Sprachroutingrichtlinie mit dem Namen "Nur USA" und Hinzufügen der PSTN-Verwendung "USA und Kanada" zur Richtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Voice**  >  **Voice Voice-Routingrichtlinien,** und klicken Sie dann auf **Hinzufügen.**
2. Geben **Sie ALS Namen** nur US ein, und fügen Sie eine Beschreibung hinzu.
3. Klicken **Sie unter PSTN-Nutzungsdatensätze** auf **PstN-Nutzung** hinzufügen, wählen Sie den PSTN-Nutzungsdatensatz "USA und Kanada" aus, und klicken Sie dann auf **Übernehmen.**
4. Klicken Sie auf **Speichern**.

Weitere Informationen finden Sie unter [Verwalten von Sprachroutingrichtlinien](manage-voice-routing-policies.md).

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Schritt 4: Zuweisen der Sprachroutingrichtlinie zu einem Benutzer namens "Spencer Low"

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.
2. Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.
3. Wählen **Sie unter Voice routing policy** die Richtlinie "Nur USA" aus, und klicken Sie dann auf **Speichern.**

Weitere Informationen finden Sie unter [Verwalten von Sprachroutingrichtlinien](manage-voice-routing-policies.md).

### <a name="using-powershell"></a>Verwendung von PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Schritt 1: Erstellen der PSTN-Verwendung "USA und Kanada"

Geben Sie in einer Remote-PowerShell-Sitzung in Skype for Business Online:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Stellen Sie sicher, dass die Verwendung erstellt wurde, indem Sie:

```PowerShell
Get-CSOnlinePSTNUsage
``` 

Gibt eine Liste mit Namen zurück, die abgeschnitten werden können:

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

Das folgende Beispiel zeigt das Ergebnis der Ausführung des `(Get-CSOnlinePSTNUsage).usage` Befehls PowerShell, um vollständige Namen (nicht abgeschnitten) anzeigen zu können:

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Schritt 2: Erstellen von drei Sprachrouten (Redmond 1, Redmond 2 und Sonstige +1)

Um die Route "Redmond 1" zu erstellen, geben Sie in einer PowerShell-Sitzung in Skype for Business Online:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Gibt zurück:

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

Geben Sie zum Erstellen der Route Redmond 2 ein:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Geben Sie zum Erstellen der Route Andere +1 ein:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Stellen Sie sicher, dass der reguläre Ausdruck im NumberPattern-Attribut ein gültiger Ausdruck ist. Sie können es auf dieser Website testen: [https://www.regexpal.com](https://www.regexpal.com)

In einigen Fällen ist es nötig, alle Anrufe an denselben SBC weiter zu routen. verwenden Sie -NumberPattern ".*"

Routen Sie alle Anrufe an denselben SBC.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Vergewissern Sie sich, dass Sie die Route ordnungsgemäß konfiguriert haben, indem Sie den `Get-CSOnlineVoiceRoute` Befehl PowerShell mit den folgenden Optionen ausführen:

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Dies sollte zurückgeben:

```console
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
```

Im Beispiel wurde der Route "Sonstiges +1" automatisch Priorität 4 zugewiesen. 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Schritt 3: Erstellen einer Sprachroutingrichtlinie mit dem Namen "Nur USA" und Hinzufügen der PSTN-Verwendung "USA und Kanada" zur Richtlinie

Geben Sie in einer PowerShell-Sitzung in Skype for Business Online:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Das Ergebnis wird in diesem Beispiel angezeigt:

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Schritt 4: Zuweisen der Sprachroutingrichtlinie zu einem Benutzer namens "Spencer Low"

Geben Sie in einer PowerShell-Sitzung in Skype for Business Online:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Überprüfen Sie die Richtlinienzuordnung, indem Sie den folgenden Befehl eingeben:

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

Der Befehl gibt Folgendes zurück:

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Beispiel 2: Sprachrouting mit mehreren PSTN-Verwendungen

Die in Beispiel 1 erstellte Sprachroutingrichtlinie erlaubt nur Anrufe an Telefonnummern in den USA und Kanada – es sei denn, dem Benutzer wird auch die Microsoft Calling Plan-Lizenz zugewiesen.

Im folgenden Beispiel können Sie die Voice routingrichtlinie "Keine Einschränkungen" erstellen. Die Richtlinie verwendet die in Beispiel 1 erstellte PSTN-Verwendung "USA und Kanada" sowie die neue "internationale" PSTN-Verwendung. Diese Richtlinie leitet alle anderen Aufrufe an die SBCs sbc2.contoso.biz und sbc5.contoso.biz.

In den gezeigten Beispielen wird dem Benutzer "Spencer Low" die Richtlinie "US Only" und dem Benutzer John Woods die Richtlinie "Keine Einschränkungen" zugewiesen, sodass das Routing wie folgt erfolgt:

- Spencer Low – Richtlinie nur usa.  Anrufe sind nur für US- und kanadische Nummern zulässig. Beim Aufrufen des Redmond-Nummernbereichs muss der spezifische Satz von SBCs verwendet werden. Nicht-US-Nummern werden nur dann an den Benutzer weitergeroutet, wenn dem Benutzer die Lizenz für den Anrufplan zugewiesen ist.

- John Woods – Internationale Richtlinie.  Anrufe sind an eine beliebige Nummer zulässig. Beim Aufrufen des Redmond-Nummernbereichs muss der spezifische Satz von SBCs verwendet werden. Nicht-US-Nummern werden mithilfe von Sbc2.contoso.biz und sbc5.contoso.biz.

![Zeigt die dem Benutzer "Spencer Low" zugewiesene Sprachroutingrichtlinie an.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Bei allen anderen Anrufen wird die automatische Route verwendet, wenn ein Benutzer über beide Lizenzen (Microsoft Phone System und Microsoft Calling Plan) verfügt. Wenn nichts den Nummernmustern in den vom Administrator erstellten Online-Sprachrouten entspricht, wird der Anruf mithilfe des Microsoft-Anrufplans geroutet.  Wenn der Benutzer nur über Microsoft Phone System verfügt, wird der Anruf verworfen, da keine übereinstimmenden Regeln verfügbar sind.

![Zeigt die dem Benutzer John Woods zugewiesene Sprachroutingrichtlinie an.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

In der folgenden Tabelle sind die Verwendungsbezeichnungen und Sprachrouten der Routingrichtlinie "Keine Einschränkungen" zusammengefasst. 

| PSTN-Verwendung | Sprachroute | Nummernmuster | Priorität | SBC | Beschreibung |
|:-----|:-----|:-----|:-----|:-----|:-----|
|USA und Kanada|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Aktive Route für Anrufernummern +1 425 XXX XX XX oder +1 206 XXX XX XX|
|USA und Kanada|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Sicherungsroute für Anrufernummern +1 425 XXX XX XX oder +1 206 XXX XX XX|
|USA und Kanada|"Sonstiges +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route für Anrufernummern +1 XXX XXX XX XX XX (außer +1 425 XXX XX XX oder +1 206 XXX XX XX)|
|International|International|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Route für ein beliebiges Zahlenmuster |

  > [!NOTE]
  > - Die Reihenfolge der PSTN-Verwendungen in Sprachroutingrichtlinien ist entscheidend. Die Verwendungen werden in der Reihenfolge angewendet, und wenn eine Übereinstimmung in der ersten Verwendung gefunden wird, werden andere Verwendungen nie ausgewertet. Die "internationale" PSTN-Verwendung muss nach der PSTN-Verwendung "USA und Kanada" platziert werden. Führen Sie den Befehl aus, um die Reihenfolge der PSTN-Verwendungen `Set-CSOnlineVoiceRoutingPolicy` zu ändern. <br/>Wenn Sie z. B. die Reihenfolge von "USA und Kanada" zuerst und "International" als Zweites in die umgekehrte Reihenfolge ändern möchten, führen Sie folgende Ausführung aus:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - Die Priorität für "Andere +1" und "Internationale" Sprachrouten wird automatisch zugewiesen. Sie spielt keine Rolle, solange sie niedrigere Prioritäten als "Redmond 1" und "Redmond 2" haben.

## <a name="example-2-configuration-steps"></a>Beispiel 2: Konfigurationsschritte

Im folgenden Beispiel wird gezeigt, wie Sie:

1. Erstellen Sie eine neue PSTN-Verwendung namens International.
2. Erstellen Sie eine neue Sprachroute mit dem Namen International.
3. Erstellen Sie eine Sprachroutingrichtlinie mit dem Namen Keine Einschränkungen.
4. Weisen Sie die Richtlinie dem Benutzer John Woods zu.

Sie können das [Microsoft Teams Admin Center](#admincenterexample2) oder [PowerShell verwenden,](#powershellexample2) um diese Schritte durchzuführen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Schritt 1: Erstellen der PstN-Nutzung "International"

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Voice** Direct Routing, und wählen Sie dann in der oberen rechten Ecke  >  PstN-Nutzungsdatensätze **verwalten aus.**
2. Klicken **Sie auf Hinzufügen,** geben **Sie International** ein, und klicken Sie dann auf **Übernehmen.**

#### <a name="step-2-create-the-international-voice-route"></a>Schritt 2: Erstellen der Sprachroute "International"

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Voice** Direct Routing, und wählen Sie dann die Registerkarte  >   **Voicerouten** aus.
2. Klicken **Sie auf** Hinzufügen, geben Sie "International" als Namen ein, und fügen Sie dann die Beschreibung hinzu.
3. Legen Sie die Priorität auf 4 fest, und legen Sie dann das gewählte Zahlenmuster auf \d+fest.
4. Klicken **Sie unter registrierten SBCs (optional)** auf **SBCs** hinzufügen, wählen Sbc2.contoso.biz und sbc5.contoso.biz aus, und klicken Sie dann auf **Übernehmen**.
5. Klicken **Sie unter PSTN-Nutzungsdatensätze (optional)** auf **PstN-Nutzung** hinzufügen, wählen Sie den "Internationalen" PSTN-Nutzungsdatensatz aus, und klicken Sie dann auf **Übernehmen.**
6. Klicken Sie auf **Speichern**.

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>Schritt 3: Erstellen einer Sprachroutingrichtlinie mit dem Namen "Keine Einschränkungen" und Hinzufügen der PSTN-Verwendungen "USA und Kanada" und "International" zur Richtlinie

Die PSTN-Verwendung "USA und Kanada" wird in dieser Sprachroutingrichtlinie wiederverwendet, um die besondere Behandlung von Anrufen mit den Nummern "+1 425 XXX XX XX" und "+1 206 XXX XX XX" als lokale oder lokale Anrufe zu erhalten.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Voice**  >  **Voice Voice-Routingrichtlinien,** und klicken Sie dann auf **Hinzufügen.**
2. Geben **Sie Keine Einschränkungen** als Namen ein, und fügen Sie eine Beschreibung hinzu.
3. Klicken Sie unter **PSTN-Nutzungsdatensätze** auf **PstN-Nutzung** hinzufügen, wählen Sie den PSTN-Nutzungsdatensatz "USA und Kanada" und dann den "Internationalen" PSTN-Nutzungsdatensatz aus. Klicken Sie auf **Anwenden**.

    Beachten Sie die Reihenfolge der PSTN-Nutzungen:

    - Wenn ein Aufruf der Nummer "+1 425 XXX XX XX" mit den in diesem Beispiel konfigurierten Verwendungen erfolgt, folgt der Aufruf der Route, die in der Verwendung "USA und Kanada" festgelegt wurde, und die spezielle Routinglogik wird angewendet. Das heißt, der Anruf wird zuerst mithilfe von sbc1.contoso.biz und sbc2.contoso.biz und dann sbc3.contoso.biz und sbc4.contoso.biz als Sicherungsrouten verwendet.

    - Wenn die "internationale" PSTN-Verwendung vor "USA und Kanada" liegt, werden Aufrufe von +1 425 XXX XX XX als Teil der Routinglogik an sbc2.contoso.biz und sbc5.contoso.biz weiterleiten.

4. Klicken Sie auf **Speichern**.

Weitere Informationen finden Sie unter [Verwalten von Sprachroutingrichtlinien](manage-voice-routing-policies.md).

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>Schritt 4: Zuweisen der Sprachroutingrichtlinie zu einem Benutzer namens John Woods

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.
2. Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.
3. Wählen **Sie unter Voiceroutingrichtlinie** die Richtlinie "Keine Einschränkungen" aus, und klicken Sie dann auf **Speichern.**

Dies hat zur Folge, dass die auf Die Anrufe von John Woods angewendete Sprachrichtlinie uneingeschränkt ist und der Logik des Anrufroutings folgt, das für Anrufe in den USA, Kanada und international verfügbar ist.

### <a name="using-powershell"></a>Verwendung von PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Schritt 1: Erstellen der PstN-Nutzung "International"

Geben Sie in einer Remote-PowerShell-Sitzung in Skype for Business Online:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>Schritt 2: Erstellen einer neuen Sprachroute mit dem Namen "International"

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

Gibt zurück:

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>Schritt 3: Erstellen einer Sprachroutingrichtlinie mit dem Namen "Keine Einschränkungen"

Die PSTN-Verwendung "Redmond 1" und "Redmond" werden in dieser Sprachroutingrichtlinie wiederverwendet, um die spezielle Behandlung von Anrufen mit den Nummern "+1 425 XXX XX XX" und "+1 206 XXX XX XX" als lokale oder lokale Anrufe zu erhalten.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Beachten Sie die Reihenfolge der PSTN-Nutzungen:

  - Wenn ein Anruf unter der Nummer "+1 425 XXX XX XX" mit den im folgenden Beispiel konfigurierten Verwendungen erfolgt, folgt der Aufruf der Route, die in der Verwendung "USA und Kanada" festgelegt wurde, und die spezielle Routinglogik wird angewendet. Das heißt, der Anruf wird zuerst mithilfe von sbc1.contoso.biz und sbc2.contoso.biz und dann sbc3.contoso.biz und sbc4.contoso.biz als Sicherungsrouten verwendet.

  - Wenn die "internationale" PSTN-Verwendung vor "USA und Kanada" liegt, werden Aufrufe von +1 425 XXX XX XX als Teil der Routinglogik an sbc2.contoso.biz und sbc5.contoso.biz weiterleiten. Geben Sie den Befehl ein:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Gibt zurück:

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>Schritt 4: Zuweisen der Sprachroutingrichtlinie zum Benutzer namens John Woods

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

Überprüfen Sie dann die Aufgabe mit dem Befehl: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Gibt zurück:

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

Dies hat zur Folge, dass die Sprachrichtlinie, die auf Die Anrufe von John Woods angewendet wird, uneingeschränkt ist und der Logik des Anrufroutings folgt, das für Anrufe in den USA, Kanada und international verfügbar ist.

## <a name="see-also"></a>Mehr dazu

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)

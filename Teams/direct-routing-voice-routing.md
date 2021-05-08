---
title: Konfigurieren von Voice Routing für Direct Routing
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
description: Hier erfahren Sie, wie Sie Voice Routing mit Microsoft-Telefon System Direct Routing konfigurieren.
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383979"
---
# <a name="configure-voice-routing-for-direct-routing"></a>Konfigurieren von Voice Routing für Direct Routing

In diesem Artikel wird beschrieben, wie Sie Voice Routing für das direkte Telefonsystem konfigurieren.  Dies ist Schritt 3 der folgenden Schritte zum Konfigurieren von Direct-Routing:

- Schritt 1: [Verbinden des SBC mit Microsoft-Telefon System und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md) 
- Schritt 2: [Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail](direct-routing-enable-users.md)
- **Schritt 3. Konfigurieren von Voice Routing** (Dieser Artikel)
- Schritt 4: [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md) 

Informationen zu allen zum Einrichten von Direct-Routing erforderlichen Schritten finden Sie unter [Konfigurieren von Direct-Routing.](direct-routing-configure.md)

## <a name="voice-routing-overview"></a>Übersicht über Sprachrouting

Microsoft-Telefon Das System verfügt über einen Routingmechanismus, der es ermöglicht, einen Anruf basierend auf den hier verwendeten Daten an einen bestimmten Session Border Controller (SBC) zu wenden: 

- Das aufgerufene Zahlenmuster 
- Das Muster "Aufgerufene Nummer" und der spezifische Benutzer, der den Anruf anruft
 
SBCs können als aktiv und Sicherungskopien gekennzeichnet werden. Wenn der als aktiv konfigurierte SBC für eine bestimmte Anrufroute nicht verfügbar ist, wird der Anruf an einen Sicherungs-SBC geroutet.
 
Das Sprachrouting besteht aus den folgenden Elementen: 

- **Voice routing policy** – Ein Container für PSTN-Nutzungen, der einem Benutzer oder mehreren Benutzern zugewiesen werden kann. 

- **PSTN-Nutzung:** Ein Container für Sprachrouten und PSTN-Nutzungen, der in verschiedenen Richtlinien für das Voicerouting freigegeben werden kann. 

- **Sprachanrufrouten** – Ein Nummernmuster und eine Reihe von Online-PSTN-Gateways, die für Anrufe verwendet werden können, bei denen die Anrufnummer dem Muster entspricht.

- **Online-PSTN-Gateway** – Ein Zeiger auf einen SBC, in dem auch die Konfiguration gespeichert wird, die angewendet wird, wenn ein Aufruf über die SBC platziert wird, z. B. WEITERLEITUNG (P-Asserted-Identity) oder bevorzugte Codecs; kann zu Sprachrouten hinzugefügt werden.

## <a name="voice-routing-policy-considerations"></a>Überlegungen zur Voice Routing-Richtlinie

Wenn ein Benutzer über eine Anrufplanlizenz verfügt, werden die ausgehenden Anrufe dieses Benutzers automatisch über die PSTN-Infrastruktur des Microsoft-Anrufplans geroutet. Wenn Sie eine Online-Voice routing-Richtlinie konfigurieren und einem Anrufplanbenutzer zuweisen, werden die ausgehenden Anrufe dieses Benutzers überprüft, um festzustellen, ob die gewählte Nummer einem Nummernmuster entspricht, das in der Online-Voiceroutingrichtlinie definiert ist. Bei einer Übereinstimmung wird der Anruf über den Direct Routing-Trunk geroutet. Wenn keine Übereinstimmung besteht, wird der Anruf über die PSTN-Infrastruktur des Anrufplans geroutet.

> [!CAUTION]
> Wenn Sie die globale (organisationsweite Standard-) Online-Voiceroutingrichtlinie konfigurieren und anwenden, erben alle sprachfähigen Benutzer in Ihrer Organisation diese Richtlinie, was dazu führen kann, dass PSTN-Anrufe von Anrufplanbenutzern versehentlich an einen Direct Routing-Trunk geroutet werden. Wenn Sie nicht möchten, dass alle Benutzer die globale Online-Voiceroutingrichtlinie verwenden, konfigurieren Sie eine benutzerdefinierte Online-Voiceroutingrichtlinie, und weisen Sie sie einzelnen sprachfähigen Benutzern zu.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Beispiel 1: Sprachrouting mit einer PSTN-Nutzung

Das folgende Diagramm zeigt zwei Beispiele für Voice Routing-Richtlinien in einem Anruffluss.

**Anruf Flow 1 (links):** Wenn ein Benutzer +1 425 XXX XX XX oder +1 206 XXX XX XX anruft, wird der Anruf an SBC sbc1.contoso.biz oder sbc2.contoso.biz. Wenn weder sbc1.contoso.biz noch sbc2.contoso.biz verfügbar sind, wird der Anruf verworfen. 

**Rufen Flow 2 (auf der rechten Seite) an:** Wenn ein Benutzer +1 425 XXX XX XX oder +1 206 XXX XX XX anruft, wird der Anruf zuerst an SBC sbc1.contoso.biz oder sbc2.contoso.biz. Wenn keines der beiden SBC-Daten verfügbar ist, wird die Route mit niedrigerer Priorität ausprobiert (sbc3.contoso.biz und sbc4.contoso.biz). Wenn keine der SBCs verfügbar ist, wird der Anruf verworfen. 

![Beispiele für Voice Routing-Richtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

In beiden Beispielen werden der Sprachroute Prioritäten zugewiesen, während die SBCs in den Routen in zufälliger Reihenfolge ausprobiert werden.

  > [!NOTE]
  > Sofern der Benutzer nicht auch über eine Lizenz für einen Microsoft-Anrufplan verfügt, werden Anrufe an eine beliebige Nummer mit Ausnahme von Nummern, die den Mustern +1 425 XXX XX XX oder +1 206 XXX XX XX in der Beispielkonfiguration übereinstimmen, gelöscht. Wenn der Benutzer über eine Anrufplanlizenz verfügt, wird der Anruf automatisch gemäß den Richtlinien des Microsoft-Anrufplans geroutet. Der Microsoft-Anrufplan wird automatisch als letzte Route für alle Benutzer mit der Microsoft-Anrufplanlizenz angewendet und erfordert keine zusätzliche Konfiguration des Anrufroutings.

Im folgenden Beispiel wird eine Sprachroute hinzugefügt, um Anrufe an alle anderen US- und kanadischen Nummern zu senden (Anrufe an das so genannte Nummernmuster +1 XXX XXX XX XX).

![Zeigt die Voice Routing-Richtlinie mit einer dritten Route an](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Für alle anderen Anrufe wird die automatische Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft-Telefon System und Microsoft Calling Plan). Wenn keine Übereinstimmung mit den Nummernmustern in den vom Administrator erstellten Online-Sprachrouten besteht, wird der Anruf über den Microsoft-Anrufplan geroutet. Wenn der Benutzer nur über ein Microsoft-Telefon verfügt, wird der Aufruf verworfen, da keine Abgleichsregeln verfügbar sind.

  > [!NOTE]
  > Der Wert Priority für die Route "Other +1" spielt in diesem Fall keine Rolle, da es nur eine Route gibt, die dem Muster +1 XXX XXX XX XX entspricht. Wenn ein Benutzer +1 324 567 89 89 anruft und sbc5.contoso.biz und sbc6.contoso.biz nicht verfügbar sind, wird der Anruf verworfen.

In der folgenden Tabelle ist die Konfiguration mithilfe von drei Sprachrouten zusammengefasst. In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Nutzung, "USA und Kanada".  Alle Routen sind der PSTN-Nutzung "USA und Kanada" und die PSTN-Nutzung der Sprachroutingrichtlinie "Nur USA" zugeordnet.

|**PSTN-Verwendung**|**Sprachanrufroute**|**Nummernmuster**|**Priorität**|**SBC**|**Beschreibung**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|USA und Kanada|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Aktive Route für aufgerufene Nummern +1 425 XXX XX XX oder +1 206 XXX XX XX|
|USA und Kanada|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Sicherungsroute für die sogenannten Nummern +1 425 XXX XX XX oder +1 206 XXX XX XX|
|USA und Kanada|"Andere +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route für die genannten Nummern +1 XXX XXX XX XX (außer +1 425 XXX XX oder +1 206 XXX XX XX)|
|||||||

## <a name="example-1-configuration-steps"></a>Beispiel 1: Konfigurationsschritte

Im folgenden Beispiel wird Folgendes veranschaulicht:

1. Erstellen Sie eine einzige PSTN-Nutzung.
2. Konfigurieren Sie drei Sprachrouten.
3. Erstellen Sie eine Sprachroutingrichtlinie.
4. Weisen Sie die Richtlinie einem Benutzer mit dem Namen "Low" zu.

Sie können diese Schritte [Microsoft Teams Admin Center](#admincenterexample1) oder [PowerShell](#powershellexample1) ausführen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Schritt 1: Erstellen der PSTN-Nutzung "USA und Kanada"

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Voice** Direct Routing , und wählen Sie dann in der oberen rechten Ecke  >  PSTN-Nutzungsdatensätze **verwalten aus.**
2. Klicken **Sie auf** Hinzufügen , geben Sie US und **Canada** ein, und klicken Sie dann auf **Übernehmen**.

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Schritt 2: Erstellen von drei Sprachrouten (Redmond 1, Redmond 2 und Other +1)

Die folgenden Schritte beschreiben, wie Sie eine Sprachroute erstellen. Verwenden Sie diese Schritte, um die drei Sprachrouten Redmond 1, Redmond 2 und Other +1 für dieses Beispiel mithilfe der in der früheren Tabelle beschriebenen Einstellungen zu erstellen.

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **Voice** Direct Routing , und wählen Sie dann  >  die Registerkarte **Voicerouten** aus.
2. Klicken **Sie auf** Hinzufügen , und geben Sie einen Namen und eine Beschreibung für die Sprachroute ein.
3. Legen Sie die Priorität fest, und geben Sie das Muster der gewählten Nummer an.
4. Um einen SBC bei der Sprachroute zu registrieren, klicken Sie unter SBCs registriert **(optional)** auf **Add SBCs**, wählen Sie die SBCs aus, die Sie registrieren möchten, und klicken Sie dann auf **Apply**.
5. Zum Hinzufügen von PSTN-Nutzungsdatensätzen klicken Sie unter PSTN-Nutzungsdatensätze **(optional)** auf **PSTN-Nutzung** hinzufügen , wählen Sie die PSTN-Einträge aus, die Sie hinzufügen möchten, und klicken Sie dann auf **Übernehmen**.
6. Klicken Sie auf **Speichern**.

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Schritt 3: Erstellen einer Sprachroutingrichtlinie namens "Nur USA" und Hinzufügen der PSTN-Nutzung "USA und Kanada" zur Richtlinie

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **Voice Voice** Voice  >  **Routing Policies**, und klicken Sie dann auf **Hinzufügen**.
2. Geben **Sie nur US als** Namen ein, und fügen Sie eine Beschreibung hinzu.
3. Klicken **Sie unter PSTN-Nutzungsdatensätze** auf **PSTN-Nutzung hinzufügen**, wählen Sie den PSTN-Nutzungsdatensatz "USA und Kanada" aus, und klicken Sie dann auf **Übernehmen**.
4. Klicken Sie auf **Speichern**.

Weitere Informationen finden Sie unter [Verwalten von Voice Routing-Richtlinien.](manage-voice-routing-policies.md)

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Schritt 4: Zuweisen der Voice Routing-Richtlinie zu einem Benutzer namens "Low"

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.
2. Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.
3. Wählen **Sie unter Voice routing policy** die Richtlinie "Nur US" aus, und klicken Sie dann auf **Speichern**.

Weitere Informationen finden Sie unter [Verwalten von Voice Routing-Richtlinien.](manage-voice-routing-policies.md)

### <a name="using-powershell"></a>Verwendung von PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>Schritt 1: Erstellen der PSTN-Nutzung "USA und Kanada"

Geben Sie in einer PowerShell-Remotesitzung in Skype for Business Online ein:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Stellen Sie sicher, dass die Verwendung erstellt wurde, indem Sie wie hier eingeben:

```PowerShell
Get-CSOnlinePSTNUsage
``` 

Gibt eine Liste von Namen zurück, die abgeschnitten werden können:

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

Das folgende Beispiel zeigt das Ergebnis der Ausführung des PowerShell-Befehls zum Anzeigen vollständiger `(Get-CSOnlinePSTNUsage).usage` Namen (nicht abgeschnitten):

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>Schritt 2: Erstellen von drei Sprachrouten (Redmond 1, Redmond 2 und Other +1)

Um die Route "Redmond 1" zu erstellen, geben Sie in einer PowerShell-Sitzung in Skype for Business Online ein:

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

Um die Route 2 von Redmond zu erstellen, geben Sie ein:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Geben Sie zum Erstellen der Route Andere +1:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Stellen Sie sicher, dass der reguläre Ausdruck im Attribut "NumberPattern" ein gültiger Ausdruck ist. Sie können dies mithilfe dieser Website testen: [https://www.regexpal.com](https://www.regexpal.com)

In einigen Fällen müssen alle Aufrufe an denselben SBC geroutet werden. use -NumberPattern ".*"

Alle Anrufe an denselben SBC weiter routen.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Überprüfen Sie, ob Sie die Route richtig konfiguriert haben, indem Sie den `Get-CSOnlineVoiceRoute` PowerShell-Befehl wie folgt ausführen:

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

Im Beispiel wurde der Route "Sonstige +1" automatisch Priorität 4 zugewiesen. 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>Schritt 3: Erstellen einer Sprachroutingrichtlinie namens "Nur USA" und Hinzufügen der PSTN-Nutzung "USA und Kanada" zur Richtlinie

Geben Sie in einer PowerShell-Sitzung in Skype for Business Online ein:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Das Ergebnis wird in diesem Beispiel gezeigt:

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>Schritt 4: Zuweisen der Voice Routing-Richtlinie zu einem Benutzer namens "Low"

Geben Sie in einer PowerShell-Sitzung in Skype for Business Online ein:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Überprüfen Sie die Richtlinienzuweisung, indem Sie den folgenden Befehl eingeben:

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

Der Befehl gibt Folgendes zurück:

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Beispiel 2: Sprachrouting mit mehreren PSTN-Nutzungen

Die in Beispiel 1 erstellte Sprachroutingrichtlinie erlaubt nur Anrufe an Telefonnummern in den USA und Kanada, es sei denn, dem Benutzer ist auch die Lizenz für den Microsoft-Anrufplan zugewiesen.

Im folgenden Beispiel können Sie die Sprachroutingrichtlinie "Keine Einschränkungen" erstellen. Die Richtlinie verwendet die in Beispiel 1 erstellte PSTN-Nutzung "USA und Kanada" sowie die neue "internationale" PSTN-Nutzung wieder. Diese Richtlinie leitet alle anderen Aufrufe an die SBCs sbc2.contoso.biz und sbc5.contoso.biz.

In den gezeigten Beispielen wird Dem Benutzer "Nur US Only" und dem Benutzer John Grund die Richtlinie "Keine Einschränkungen" zugewiesen, sodass das Routing wie folgt erfolgt:

- Low-Dollar – Richtlinie nur USA.  Anrufe sind nur an US-amerikanische und kanadische Nummern zulässig. Wenn Sie in den Rufnummernbereich von Redmond anrufen, muss die spezifische Gruppe von SBCs verwendet werden. Nicht-US-Nummern werden nur dann geroutet, wenn dem Benutzer die Lizenz für den Anrufplan zugewiesen wurde.

- John John John – Internationale Richtlinie.  Anrufe sind an beliebige Nummern zulässig. Wenn Sie in den Rufnummernbereich von Redmond anrufen, muss die spezifische Gruppe von SBCs verwendet werden. Nummern, die keine US-amerikanischen Sind, werden mithilfe von sbc2.contoso.biz und sbc5.contoso.biz.

![Zeigt die Sprachroutingrichtlinie an, die Benutzer "Low" zugewiesen ist.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Bei allen anderen Anrufen wird die automatische Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft-Telefon System und Microsoft Calling Plan). Wenn keine Übereinstimmung mit den Nummernmustern in den vom Administrator erstellten Online-Sprachrouten besteht, wird der Anruf mithilfe des Microsoft-Anrufplans geroutet.  Wenn der Benutzer nur über ein Microsoft-Telefon verfügt, wird der Aufruf verworfen, da keine Abgleichsregeln verfügbar sind.

![Zeigt die voice routing policy assigned to user John Routing](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

In der folgenden Tabelle sind die Verwendungsbezeichnungen für die Routingrichtlinie "Keine Einschränkungen" und Sprachrouten zusammengefasst. 

| PSTN-Verwendung | Sprachanrufroute | Nummernmuster | Priority | SBC | Beschreibung |
|:-----|:-----|:-----|:-----|:-----|:-----|
|USA und Kanada|"Redmond 1"|^\\+1(425 \| 206)(\d {7} )$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Aktive Route für Anrufernummern +1 425 XXX XX oder +1 206 XXX XX XX|
|USA und Kanada|"Redmond 2"|^\\+1(425 \| 206)(\d {7} )$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Sicherungsroute für Anrufernummern +1 425 XXX XX oder +1 206 XXX XX XX|
|USA und Kanada|"Andere +1"|^\\+1(\d {10} )$|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route für Anrufernummern +1 XXX XXX XX XX (außer +1 425 XXX XX oder +1 206 XXX XX XX)|
|International|International|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Route für ein beliebiges Nummernmuster |

  > [!NOTE]
  > - Die Reihenfolge der PSTN-Verwendungen in den Voice Routing-Richtlinien ist entscheidend. Die Verwendungen werden der Reihenfolge nach angewendet, und wenn bei der ersten Verwendung eine Übereinstimmung gefunden wird, werden andere Verwendungen nie ausgewertet. Die PSTN-Nutzung "International" muss nach der PSTN-Nutzung "USA und Kanada" platziert werden. Führen Sie den Befehl aus, um die Reihenfolge der PSTN-Verwendungen `Set-CSOnlineVoiceRoutingPolicy` zu ändern. <br/>Wenn Sie z. B. die Reihenfolge von "US and Canada" first und "International" second in die umgekehrte Reihenfolge ändern möchten, führen Sie folgenden Schritt aus:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - Die Priorität für Die Sprachrouten "Andere +1" und "International" werden automatisch zugewiesen. Sie spielt keine Rolle, solange sie niedrigere Prioritäten haben als "Redmond 1" und "Redmond 2".

## <a name="example-2-configuration-steps"></a>Beispiel 2: Konfigurationsschritte

Im folgenden Beispiel wird Folgendes veranschaulicht:

1. Erstellen Sie eine neue PSTN-Nutzung namens International.
2. Erstellen Sie eine neue Sprachroute namens "International".
3. Erstellen Sie eine Voiceroutingrichtlinie namens Keine Einschränkungen.
4. Weisen Sie die Richtlinie dem Benutzer John Verding zu.

Sie können diese Schritte [Microsoft Teams Admin Center](#admincenterexample2) oder [PowerShell](#powershellexample2) ausführen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Schritt 1: Erstellen der PSTN-Nutzung "International"

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Voice** Direct Routing , und wählen Sie dann in der oberen rechten Ecke  >  PSTN-Nutzungsdatensätze **verwalten aus.**
2. Klicken **Sie auf** Hinzufügen , geben Sie **International** ein, und klicken Sie dann auf **Übernehmen**.

#### <a name="step-2-create-the-international-voice-route"></a>Schritt 2: Erstellen der Sprachroute "International"

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **Voice** Direct Routing , und wählen Sie dann  >  die Registerkarte **Voicerouten** aus.
2. Klicken **Sie auf** Hinzufügen , geben Sie "International" als Namen ein, und fügen Sie dann die Beschreibung hinzu.
3. Legen Sie die Priorität auf 4 fest, und legen Sie dann das Nummernmuster auf \d+ fest.
4. Klicken Sie unter SBCs registriert **(optional)** auf **SBCs** hinzufügen , wählen sbc2.contoso.biz und sbc5.contoso.biz aus, und klicken Sie dann auf **Übernehmen**.
5. Klicken **Sie unter PSTN-Nutzungsdatensätze (optional)** auf **PSTN-Nutzung** hinzufügen , wählen Sie den Eintrag "International" PSTN Usage Record aus, und klicken Sie dann auf **Übernehmen**.
6. Klicken Sie auf **Speichern**.

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>Schritt 3: Erstellen einer Sprachroutingrichtlinie namens "Keine Einschränkungen" und Hinzufügen der PSTN-Verwendungen "USA und Kanada" und "International" zur Richtlinie

Die PSTN-Verwendung "USA und Kanada" wird in dieser Voiceroutingrichtlinie wiederverwendet, um die besondere Behandlung von Anrufen an die Nummern "+1 425 XXX XX XX" und "+1 206 XXX XX XX" als lokale oder lokale Anrufe zu erhalten.

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **Voice Voice** Voice  >  **Routing Policies**, und klicken Sie dann auf **Hinzufügen**.
2. Geben **Sie Keine Einschränkungen** als Namen ein, und fügen Sie eine Beschreibung hinzu.
3. Klicken Sie unter **PSTN-Nutzungsdatensätze** auf **PSTN-Nutzung** hinzufügen , wählen Sie den PSTN-Nutzungsdatensatz "USA und Kanada" und dann den PSTN-Nutzungsdatensatz "International" aus. Klicken Sie auf **Anwenden**.

    Beachten Sie die Reihenfolge der PSTN-Nutzungen:

    - Wenn ein Anruf an die Nummer "+1 425 XXX XX XX" mit den wie in diesem Beispiel konfigurierten Nutzungen erfolgt, folgt der Anruf der route, die unter Verwendung von "USA und Kanada" festgelegt wurde, und die spezielle Routinglogik wird angewendet. Das heißt, der Anruf wird zuerst mithilfe von sbc1.contoso.biz und sbc2.contoso.biz geroutet und dann sbc3.contoso.biz und sbc4.contoso.biz als Sicherungsrouten verwendet.

    - Wenn die PSTN-Verwendung "International" vor "USA und Kanada" liegt, werden Anrufe an +1 425 XXX XX XX als Teil der Routinglogik an sbc2.contoso.biz und sbc5.contoso.biz umleitungslogik.

4. Klicken Sie auf **Speichern**.

Weitere Informationen finden Sie unter [Verwalten von Voice Routing-Richtlinien.](manage-voice-routing-policies.md)

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>Schritt 4: Zuweisen der Sprachroutingrichtlinie zu einem Benutzer namens John John

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.
2. Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.
3. Wählen **Sie unter Voice routing policy** die Richtlinie "No Restrictions" aus, und klicken Sie dann auf **Speichern.**

Das Ergebnis ist, dass die Sprachrichtlinie, die auf John John Johns Anrufe angewendet wird, uneingeschränkt ist und der Logik des Anrufroutings folgt, das für Anrufe in den USA, Kanada und im Ausland verfügbar ist.

### <a name="using-powershell"></a>Verwendung von PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>Schritt 1: Erstellen der PSTN-Nutzung "International"

Geben Sie in einer PowerShell-Remotesitzung in Skype for Business Online ein:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>Schritt 2: Erstellen einer neuen Sprachroute namens "International"

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

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>Schritt 3: Erstellen einer Sprachroutingrichtlinie namens "Keine Einschränkungen"

Die PSTN-Nutzung "Redmond 1" und "Redmond" werden in dieser Voice Routing-Richtlinie wiederverwendet, um die besondere Behandlung von Anrufen an die Nummern "+1 425 XXX XX XX" und "+1 206 XXX XX XX" als lokale oder lokale Anrufe zu erhalten.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Beachten Sie die Reihenfolge der PSTN-Nutzungen:

  - Wenn ein Anruf an die Nummer "+1 425 XXX XX XX" mit den im folgenden Beispiel konfigurierten Verwendungen erfolgt, folgt der Aufruf der route, die für die Nutzung von "USA und Kanada" festgelegt wurde, und die spezielle Routinglogik wird angewendet. Das heißt, der Anruf wird zuerst mithilfe von sbc1.contoso.biz und sbc2.contoso.biz geroutet und dann sbc3.contoso.biz und sbc4.contoso.biz als Sicherungsrouten verwendet.

  - Wenn die PSTN-Verwendung "International" vor "USA und Kanada" liegt, werden Anrufe an +1 425 XXX XX XX als Teil der Routinglogik an sbc2.contoso.biz und sbc5.contoso.biz umleitungslogik. Geben Sie den Befehl ein:

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

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>Schritt 4: Zuweisen der Voice routing policy to the user named John John

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

Überprüfen Sie die Aufgabe dann mithilfe des Befehls: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Gibt zurück:

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

Das Ergebnis ist, dass die Sprachrichtlinie, die auf John John Johns Anrufe angewendet wird, uneingeschränkt ist und der Logik des Anrufroutings folgt, die für Anrufe in den USA, Kanada und im Ausland verfügbar ist.

## <a name="see-also"></a>Mehr dazu

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)

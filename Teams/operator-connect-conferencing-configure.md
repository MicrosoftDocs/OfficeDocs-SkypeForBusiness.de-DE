---
title: Konfigurieren von Konferenzen per Telefonieanbieter
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Erfahren Sie mehr darüber, wie Sie Konferenzen per Telefonieanbieter konfigurieren.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ade65551ad30c15fd209aa542781edce44bd76dd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676027"
---
# <a name="configure-operator-connect-conferencing"></a>Konfigurieren von Konferenzen per Telefonieanbieter

In diesem Artikel wird beschrieben, wie Sie Konferenzen per Telefonieanbieter für Ihre Organisation und Ihre Benutzer konfigurieren.

Informationen zu Vorteilen und Lizenzierungsanforderungen finden Sie vor dem Konfigurieren von Konferenzen per Telefonieanbieter unter ["Plan for Konferenzen per Telefonieanbieter](operator-connect-conferencing-plan.md)".

Zu den in diesem Artikel behandelten Themen gehören:

- [Einrichten eines Operators](#set-up-an-operator)
- [Abrufen von Nummern für Ihre Audiokonferenz Brücke](#acquire-numbers-for-your-audio-conferencing-bridge)
- [Ändern der Standardtelefonnummern, die in den Besprechungseinladungen von Benutzern enthalten sind](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [Senden ausgehender Anrufe aus Microsoft Teams Besprechungen über einen Operator](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [Anbieter verwalten](#manage-your-operators)
- [Freigeben von Nummern von Ihrer Audiokonferenz Brücke](#release-numbers-from-your-audio-conferencing-bridge)
- [Weitere Informationen zum Verwalten von Microsoft Audiokonferenz](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>Einrichten eines Operators

Sie können Operatoren im Teams Admin Center einrichten, bearbeiten und entfernen. Navigieren Sie im linken Navigationsbereich zu **Voice > Anbieter**.

So richten Sie einen Operator ein:

1. **Wählen Sie einen Anbieter aus.** Filtern Sie auf der Registerkarte **Alle Anbieter** verfügbare Anbieter nach Region oder Dienst, um den geeigneten Anbieter für Ihre Anrufanforderungen zu finden. Wählen Sie dann den Operator aus, den Sie verwenden möchten. Vergewissern Sie sich bei Konferenzen per Telefonieanbieter, dass der Anbieter **Konferenzen** als verfügbares Produkt aufgeführt hat.

2. **Wählen Sie Länder aus.** Wählen Sie unter **Anbietereinstellungen** die Länder aus, die Sie mit dem ausgewählten Anbieter aktivieren möchten.

3. **Bereitstellen von Kontaktinformationen** Ihre Kontaktinformationen, einschließlich Ihres vollständigen Namens und Ihrer E-Mail-Adresse, werden an Ihren Betreiber weitergegeben. Sie können diese Informationen später ändern. Darüber hinaus müssen Sie die Unternehmensgröße angeben und die Möglichkeit haben, Ihre Telefonnummer anzugeben. Operatoren verwenden diese Informationen, um Sie mit weiteren Details zu Konferenzen per Telefonieanbieter zu kontaktieren.

4. Stimmen Sie dem Hinweis zur Datenübertragung zu.

5. **Fügen Sie Ihren Anbieter hinzu.** Klicken Sie zum Speichern auf **Als meinen Anbieter hinzufügen**.

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>Abrufen von Nummern für Ihre Audiokonferenz Brücke

Die Audiokonferenz Brücke Ihrer Organisation enthält Telefonnummern, die allen Benutzern in Ihrer Organisation zur Teilnahme an Microsoft Teams Besprechungen mit PSTN-Telefonnummern zur Verfügung stehen. Die Telefonnummern, die der Audiokonferenz Brücke Ihrer Organisation zugeordnet sind, finden Sie im Teams Admin Center unter **"Besprechungen > Konferenzbrücken**".

Führen Sie die folgenden Schritte aus, um Telefonnummern für Ihre Audiokonferenz Brücke zu erhalten:

1. **Audiokonferenz Standardabonnement oder Konferenzen per Telefonieanbieter-Lizenz.** Benutzern, die Konferenzen per Telefonieanbieter Nummern benötigen, um an den von ihnen organisierten Besprechungen teilzunehmen, muss ihnen eine Audiokonferenz Standard-Abonnementlizenz oder eine Konferenzen per Telefonieanbieter Lizenz zugewiesen sein. Weitere Informationen finden Sie unter [Planen von Operator Connect-Konferenzen](operator-connect-conferencing-plan.md).

2. **Beziehen Sie Telefonnummern.** Rufen Sie die Website Ihres Anbieters auf, um Telefonnummern zu bestellen und zu beziehen. Eine Liste der Betreiberwebsites finden Sie im [Verzeichnis Microsoft 365 Telefonieanbieter](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Sie müssen Ihre Mandanten-ID angeben. Wenn Sie Ihre Mandanten-ID nicht kennen, lesen [Sie "Suchen Ihrer Microsoft 365 Mandanten-ID"](/onedrive/find-your-office-365-tenant-id). Nachdem Ihr Anbieter die Bestellung abgeschlossen hat, lädt er Nummern in Ihren Mandanten hoch. Sie können die Nummern und den Anbieter im Microsoft Teams Admin Center unter **Voice > Telefonnummern** einsehen.

3. **Weisen Sie Ihrer Audiokonferenz-Brücke Nummern zu.** Sie können Ihrer Audiokonferenz Brücke Nummern über das Teams Admin Center unter **"Besprechungen > Konferenzbrücken > Hinzufügen"** zuweisen. Weitere Informationen finden Sie unter [Ändern der Telefonnummern auf Ihrer Audiokonferenz Brücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

>[!NOTE]
>Sie können Konferenzen per Telefonieanbieter Nummern nicht als Standardnummern einer Brücke zuweisen. Sobald Ihrem Audiokonferenz Brücke eine Telefonnummer zugewiesen wurde, wird die Nummer auf der **Seite "Lokale Rufnummer suchen**" aufgeführt, die in Besprechungseinladungen von Benutzern in Ihrer Organisation mit einer Audiokonferenz-Lizenz oder einer Konferenzen per Telefonieanbieter-Lizenz enthalten ist.
>
>Informationen zum Weiterleiten ausgehender Anrufe über einen Operator finden Sie im Abschnitt [**zum Senden ausgehender Anrufe aus Teams Besprechungen über einen Operatorabschnitt**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator) weiter unten in diesem Artikel.

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>Ändern der Standardtelefonnummern, die in den Besprechungseinladungen von Benutzern enthalten sind

 Dieser Schritt ist optional.

Die Standardtelefonnummern eines Benutzers sind diejenigen, die in den Besprechungseinladungen enthalten sind, wenn er eine Besprechung plant. Sie können die Telefonnummern, die in den Besprechungseinladungen von Benutzern enthalten sind, im Teams Admin Center unter **"Benutzer > Benutzer verwalten"** aktualisieren. Um die Telefonnummern zu aktualisieren, die in den Besprechungseinladungen der Benutzer enthalten sind, wählen Sie den Benutzer aus, und wählen **Sie "Bearbeiten"** im **Abschnitt Audiokonferenz** aus.

Nachdem die Änderungen übernommen wurden, enthalten neue Besprechungseinladungen von Organisatoren die neuen Standardtelefonnummern. Vorhandene Besprechungseinladungen, die vor der Änderung geplant wurden, behalten jedoch die ursprünglichen Standardnummern bei.

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>Senden ausgehender Anrufe aus Microsoft Teams Besprechungen über einen Operator

Wenn Sie über ein Microsoft Audiokonferenz Standard-Abonnement oder eine Konferenzen per Telefonieanbieter-Lizenz verfügen, können Sie den Audiokonferenz-Dienst so konfigurieren, dass alle oder eine Reihe ausgehender Anrufe aus Teams Besprechungen über Ihren Operator weitergeleitet werden, indem Sie eine Audiokonferenz Routingrichtlinie.

>[!NOTE]
>Mit einer Konferenzen per Telefonieanbieter-Lizenz können ausgehende Anrufe nur ihren Operator durchlaufen. Wenn Sie über Konferenzen per Telefonieanbieter Lizenzen verfügen, müssen Sie den Dienst wie unten beschrieben konfigurieren, um ausgehende Anrufe von Teams Besprechungen an Telefonnummern zu aktivieren.

Sie können Audiokonferenz Routingrichtlinien auf Benutzerebene anwenden, d. h., Ihr Operator leitet nur die ausgehenden Anrufe aus Teams Besprechungen weiter, die von Benutzern mit der zugehörigen Richtlinie organisiert wurden. Sie können diese Richtlinien auch auf globaler Ebene anwenden, was bedeutet, dass Ihr Betreiber ausgehende Anrufe aus Teams Besprechungen leitet, die von allen Benutzern in Ihrer Organisation organisiert wurden.

Erstellen Sie mithilfe von PowerShell die neue Audiokonferenz Routingrichtlinie Ihrer Organisation. Um einen Operator als primäre Route für ausgehende Anrufe aus Teams Besprechungen anzugeben, führen Sie die folgenden Schritte mithilfe der angegebenen PowerShell-Befehle aus:

1. [Schritt 1: Hinzufügen einer neuen Zeichenfolge zur Online-PSTN-Verwendungsrichtlinie](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [Schritt 2: Erstellen einer neuen Online-VoIP-Routenrichtlinie](#step-2-create-a-new-online-voice-route-policy)
3. [Schritt 3: Erstellen einer neuen Online-Audiokonferenz Routingrichtlinie](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [Schritt 4: Zuweisen der neuen Richtlinie zu Benutzern](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>Schritt 1: Hinzufügen einer neuen Zeichenfolge zur Online-PSTN-Verwendungsrichtlinie

Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage) .

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>Schritt 2: Erstellen einer neuen Online-VoIP-Routenrichtlinie

Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Set-CsOnlineVoiceRoute](/powershell/module/skype/set-csonlinevoiceroute) .

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>Schritt 3: Erstellen einer neuen Online-Audiokonferenz Routingrichtlinie

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>Schritt 4: Zuweisen der neuen Richtlinie zu Benutzern

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy"
```

>[!NOTE]
>Um eine Audiokonferenz Routingrichtlinie als global festzulegen und sie auf alle Benutzer in Ihrer Organisation anzuwenden, können Sie den ``-Global`` Parameter anstelle des ``-Identity`` Parameters verwenden. Beispiel ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy"``: .

Wenn Sie eine Audiokonferenz Routingrichtlinie erstellen und auf einen Benutzer anwenden, leitet der Operator, der die im ``BridgeSourcePhoneNumber`` Parameter angegebene Telefonnummer bereitstellt, Teams ausgehende Anrufe an PSTN-Telefonnummern weiter. Darüber hinaus gibt der ``BridgeSourcePhoneNumber`` Parameter die Telefonnummer an, die als Rufnummernnummer für ausgehende Anrufe an PSTN-Telefonnummern verwendet werden soll.

Das im ``NumberPattern`` Formular "regex" angegebene Muster gibt an, welche Aufrufe durch den Operator weitergeleitet werden sollen. Das ``"\d+"`` Muster im obigen Beispiel entspricht allen ausgehenden Anrufen aus Teams Besprechungen. Sie können den Parameter "NumberPattern" auch als  ``"^\+1(425|206)(\d{7})$"``" festlegen, der gewählten Nummern mit den folgenden Formaten entspricht: +1 425 XXX XX XX oder +1 206 XXX XX XX oder ``"^\+1(\d{10})$"``, die gewählten Nummern mit dem folgenden Format entsprechen: +1 425 XXX XX XX.

Nachdem Sie einem Benutzer eine Audiokonferenz Routingrichtlinie zugewiesen haben, werden alle Anrufe von den Besprechungen an eine Telefonnummer, die dem in der richtlinie für Audiokonferenz angegebenen Regex entspricht, über Ihren Operator geleitet, einschließlich **"Rückruf bei** Anrufen und Anrufen", die über die Option **"Jemand einladen" initiiert wurden, oder wählen Sie eine** Besprechungsoption für Telefonnummern.

## <a name="manage-your-operators"></a>Anbieter verwalten

Auf der Registerkarte **"Meine Operatoren** " können Sie Ihre Operatoren und deren Status anzeigen und die folgenden Änderungen an Ihrer Auswahl vornehmen:

- Anbieterdienste nach Land verwalten
- Einen Anbieter anhalten
- Einen Anbieter entfernen

>[!NOTE]
>Bevor Sie einen Operator aus Ihrer Organisation oder einem Land entfernen, müssen Sie alle Telefonnummern entfernen, die den Benutzern und Ihrer Audiokonferenz Brücke zugewiesen sind, und sich dann an den Betreiber wenden, um die Nummern freizugeben.

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>Freigeben von Nummern von Ihrer Audiokonferenz Brücke

Informationen zum Freigeben von Telefonnummern von Ihrer Audiokonferenz Brücke aus dem Teams Admin Center finden **Sie unter "Schritte", wenn Sie die Zuweisung einer Diensttelefonnummer für eine Konferenzbrücke** unter ["Ändern der Telefonnummern auf Ihrer Audiokonferenz Brücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge)" aufheben.

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Weitere Informationen zum Verwalten von Microsoft Audiokonferenz

Weitere Informationen zum Verwalten von Microsoft Audiokonferenz für Ihre Organisation finden Sie in den folgenden Artikeln:

- Verwalten der Microsoft Audiokonferenz-Diensteinstellungen für Ihre Organisation: [Verwalten der Audiokonferenz Einstellungen für Ihre Organisation in Microsoft Teams](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

- Verwalten der Microsoft Audiokonferenz-Diensteinstellung der Benutzer in Ihrer Organisation: [Verwalten der Audiokonferenz Einstellungen für einen Benutzer in Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- Ändern der Automatischen Telefonzentralensprachen Ihrer Audiokonferenz Telefonnummern: [Festlegen der Sprachen der automatischen Telefonzentrale für Audiokonferenz in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

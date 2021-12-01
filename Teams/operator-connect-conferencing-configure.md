---
title: Konfigurieren von Verbinden für Konferenzen
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
description: Weitere Informationen zum Konfigurieren von Operatoren Verbinden Konferenzen.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87358190d919519b39494576a05235df26ad4c7a
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257522"
---
# <a name="configure-operator-connect-conferencing"></a>Konfigurieren von Verbinden für Konferenzen

In diesem Artikel wird beschrieben, wie Sie Verbinden für Ihre Organisation und Benutzer konfigurieren.

Bevor Sie die Verbinden für Konferenzen konfigurieren, lesen Sie Planen der Verbinden-Konferenzen, um Informationen zu den Vorteilen und Lizenzierungsanforderungen zu erhalten. [](operator-connect-conferencing-plan.md)

Zu den Themen in diesem Artikel gehören:

- [Einrichten eines Operators](#set-up-an-operator)
- [Erwerben von Nummern für Ihre Audiokonferenzbrücke](#acquire-numbers-for-your-audio-conferencing-bridge)
- [Ändern der Standardtelefonnummern, die in den Besprechungseinrufen von Benutzern enthalten sind](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [Senden ausgehender Anrufe Microsoft Teams Besprechungen über eine Netzbetreiber](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [Anbieter verwalten](#manage-your-operators)
- [Freigabenummern von Ihrer Audiokonferenzbrücke](#release-numbers-from-your-audio-conferencing-bridge)
- [Weitere Informationen zum Verwalten von Microsoft-Audiokonferenzen](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>Einrichten eines Operators

Sie können Operatoren im Admin Center Teams einrichten, bearbeiten und entfernen. Wechseln Sie im linken Navigationsbereich zu Sprach **> Operatoren**.

So richten Sie einen Operator ein

1. **Wählen Sie einen Operator aus.**   Filtern Sie  **auf der Registerkarte Alle** Operatoren die verfügbaren Operatoren nach Region oder Dienst, um die richtige Operator für Ihre   Sprachanforderungen zu finden. Wählen Sie dann den Operator aus, den Sie verwenden möchten. Stellen Sie Verbinden für Konferenzanbieter sicher, dass Ihr Netzbetreiber Konferenz **als** verfügbares Produkt aufgeführt hat.

2. **Wählen Sie Länder aus.**   Wählen  **Sie unter Operatoreinstellungen** die Länder aus, die Sie mit dem ausgewählten Operator aktivieren möchten.

3. **Bereitstellen von Kontaktinformationen**   Ihre Kontaktinformationen, einschließlich Ihres vollständigen Namens und Ihrer E-Mail-Adresse, werden mit Ihrem Netzbetreiber geteilt. Sie können diese Informationen später ändern. Darüber hinaus müssen Sie die Unternehmensgröße mit der Option zur Bereitstellung Ihrer Telefonnummer bereitstellen. Operatoren verwenden diese Informationen, um sie mit weiteren Details zu den Operatoren Verbinden Konferenzen zu kontaktieren.

4. Stimmen Sie dem Hinweis zur Datenübertragung zu.

5. **Fügen Sie Ihren Operator hinzu.**   Wählen  **Sie zum Speichern Als Operator hinzufügen**   aus.

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>Erwerben von Nummern für Ihre Audiokonferenzbrücke

Die Audiokonferenzbrücke Ihrer Organisation enthält Telefonnummern, die allen Benutzern in Ihrer Organisation zur Teilnahme an Microsoft Teams mit PSTN-Telefonnummern zur Verfügung stehen. Sie können die Telefonnummern, die der Audiokonferenzbrücke Ihrer Organisation zugeordnet sind, im Teams Admin Center unter Besprechungen **> Konferenzbrücken sehen.**

Führen Sie die folgenden Schritte aus, um Telefonnummern für Ihre Audiokonferenzbrücke zu erhalten:

1. **Audio conferencing Standard subscription or operator Verbinden Conferencing license.** Benutzern, die die Verbinden Verbinden Konferenznummern für die Teilnahme an den von ihnen organisierten Besprechungen benötigen, müssen über eine Abonnementlizenz für Audiokonferenzen oder eine zugewiesene Lizenz vom Anbieter Verbinden Conferencing verfügen. Weitere Informationen finden Sie unter [Planen der Verbinden für Konferenzen.](operator-connect-conferencing-plan.md)

2. **Erwerben von Nummern**   Wechseln Sie zur Website Ihrer Netzbetreiber, um Telefonnummern zu bestellen und zu erwerben. Eine Liste der Operatorwebsites finden Sie im Verzeichnis [Microsoft 365 Operator Verbinden .](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) Sie müssen Ihre Mandanten-ID angeben. Wenn Sie Ihre Mandanten-ID nicht kennen, finden Sie weitere Informationen unter Suchen [Microsoft 365 Mandanten-ID.](/onedrive/find-your-office-365-tenant-id) Nachdem Ihr Anbieter die Bestellung abgeschlossen hat, lädt er Nummern in Ihren Mandanten hoch. Sie können die Nummern und den Anbieter im Teams Admin Center anzeigen, indem Sie zu **Voice-> Telefon wechseln.**

3. **Weisen Sie Ihrer Audiokonferenzbrücke Nummern zu.** Sie können Ihrer Audiokonferenzbrücke Nummern aus dem Teams Admin Center unter Besprechungen > Konferenzbrücken und **> zuweisen.** Weitere Informationen finden Sie unter [Ändern der Telefonnummern für Ihre Audiokonferenzbrücke.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

>[!NOTE]
>Sie können Konferenznummern Verbinden als Standardnummern einer Brücke zuweisen. Sobald Ihrer Audiokonferenzbrücke eine Telefonnummer zugewiesen wurde, wird die  Nummer auf der Seite Lokale Rufnummer suchen aufgeführt, die in besprechungsteilnehmern Einladungen von Benutzern in Ihrer Organisation mit einer Lizenz für Audiokonferenzen oder einer Lizenz für die Verbinden-Konferenz vom Anbieter enthalten ist.
>
>Informationen zum Routen ausgehender Anrufe [](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator) über einen Netzbetreiber finden Sie im Abschnitt Senden ausgehender Anrufe Teams Besprechungen über einen Netzbetreiber weiter unten in diesem Artikel.

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>Ändern der Standardtelefonnummern, die in den Besprechungseinrufen von Benutzern enthalten sind

 Dieser Schritt ist optional.

Die Standardtelefonnummern eines Benutzers sind die Nummern, die beim Planen einer Besprechung in den Besprechungseinrufen enthalten sind. Sie können die Telefonnummern in den Besprechungsanrufen von Benutzern im Teams Admin Center unter Benutzer > **Benutzer verwalten aktualisieren.** Um die Telefonnummern zu aktualisieren, die in den Besprechungsteilnehmern enthalten sind, wählen Sie den Benutzer aus, und wählen Sie dann im Abschnitt **Audiokonferenz die Option Bearbeiten** aus. 

Nachdem die Änderungen übernommen wurden, enthalten neue Besprechungseinrufe von Organisatoren die neuen Standardtelefonnummern. Vorhandene Besprechungs-Einladungen, die vor der Änderung geplant wurden, behalten jedoch die ursprünglichen Standardnummern bei.

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>Senden ausgehender Anrufe Microsoft Teams Besprechungen über eine Netzbetreiber

Wenn Sie über ein Microsoft Audio Conferencing Standard-Abonnement oder eine Lizenz des Operators Verbinden Conferencing verfügen, können Sie den Audiokonferenzdienst so konfigurieren, dass alle oder mehrere ausgehende Anrufe von Teams-Besprechungen über Ihren Netzbetreiber geroutet werden, indem Sie eine Richtlinie für Audiokonferenz-Routing einrichten.

>[!NOTE]
>Bei einer Lizenz Verbinden für Konferenzen können ausgehende Anrufe nur über Ihren Netzbetreiber gehen. Wenn Sie über Lizenzen Verbinden Operator für Konferenzen verfügen, müssen Sie den Dienst wie unten beschrieben konfigurieren, um ausgehende Anrufe von Teams-Besprechungen zu Telefonnummern zu aktivieren.

Sie können Richtlinien für das Routing von Audiokonferenzen auf Benutzerebene anwenden, was bedeutet, dass Ihr Operator nur ausgehende Anrufe von Teams Besprechungen leitet, die von Benutzern mit der zugeordneten Richtlinie organisiert werden. Sie können diese Richtlinien auch auf globaler Ebene anwenden, was bedeutet, dass Ihr Operator ausgehende Anrufe von Teams, die von allen Benutzern in Ihrer Organisation organisiert werden, leitet.

Erstellen Sie mithilfe von PowerShell die neue Richtlinie für das Routing von Audiokonferenzen in Ihrer Organisation. Um einen Operator als primäre Route für ausgehende Anrufe aus Teams-Besprechungen anzugeben, führen Sie die folgenden Schritte mit den angegebenen PowerShell-Befehlen aus:

1. [Schritt 1: Hinzufügen einer neuen Zeichenfolge zur Richtlinie "Online PSTN Usage"](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [Schritt 2: Erstellen einer neuen Online-Voiceroute-Richtlinie](#step-2-create-a-new-online-voice-route-policy)
3. [Schritt 3: Erstellen einer neuen Richtlinie für das Routing von Onlineaudiokonferenzen](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [Schritt 4: Zuweisen der neuen Richtlinie zu Benutzern](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>Schritt 1: Hinzufügen einer neuen Zeichenfolge zur Richtlinie "Online PSTN Usage"

Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage)

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>Schritt 2: Erstellen einer neuen Online-Voiceroute-Richtlinie

Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Set-CsOnlineVoiceRoute.](/powershell/module/skype/set-csonlinevoiceroute)

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>Schritt 3: Erstellen einer neuen Richtlinie für das Routing von Onlineaudiokonferenzen

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>Schritt 4: Zuweisen der neuen Richtlinie zu Benutzern

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy”
```

>[!NOTE]
>Wenn Sie eine Richtlinie für das Routing von Audiokonferenzen als global festlegen und auf alle Benutzer in Ihrer Organisation anwenden möchten, können Sie den -Parameter anstelle ``-Global`` des -Parameters ``-Identity`` verwenden. Beispiel: ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy”`` .

Wenn Sie eine Richtlinie für das Routing von Audiokonferenzen erstellen und auf einen Benutzer anwenden, leitet der Operator, der die im Parameter angegebene Telefonnummer ansagt, Teams ausgehende Anrufe an ``BridgeSourcePhoneNumber`` PSTN-Telefonnummern weiter. Darüber hinaus gibt der -Parameter die Telefonnummer an, die als Rufnummer für die Rufnummernidentifikation für ausgehende Anrufe an ``BridgeSourcePhoneNumber`` PSTN-Telefonnummern verwendet werden soll.

Das im -Element angegebene ``NumberPattern`` Muster hat das Format "regex" und gibt an, welche Aufrufe durch den Operator routen werden. Das ``"\d+"`` Muster im vorstehenden Beispiel entspricht allen ausgehenden Anrufen von Teams Besprechungen. Sie können den Parameter NumberPattern auch als festlegen, der gewählten Nummern mit den folgenden Formaten entspricht: +1 425 XXX XX XX oder +1 206 XXX XX XX oder , die gewählten Nummern im folgenden Format  ``“^\+1(425|206)(\d{7})$”`` ``“^\+1(\d{10})$”`` entspricht: +1 425 XXX XX XX.

Nachdem Sie einem Benutzer eine Richtlinie für das Routing von Audiokonferenzen zugewiesen haben, werden alle Anrufe von seinen Besprechungen an eine  Telefonnummer, die dem in  der Richtlinie Für Audiokonferenz-Routing angegebenen regex entspricht, über Ihren Netzbetreiber routen. Dazu gehören auch Anrufe und Anrufe, die über die Option Jemanden einladen oder Nummernbesprechung wählen initiiert werden.

## <a name="manage-your-operators"></a>Anbieter verwalten

Auf der **Registerkarte Meine Operatoren** können Sie die Operatoren und deren Status anzeigen und die folgenden Änderungen an   Ihrer Auswahl vornehmen:

- Anbieterdienste nach Land verwalten
- Einen Anbieter anhalten
- Einen Anbieter entfernen

>[!NOTE]
>Bevor Sie einen Netzbetreiber aus Ihrer Organisation oder einem Land entfernen, müssen Sie alle den Benutzern und Ihrer Audiokonferenzbrücke zugewiesenen Telefonnummern entfernen und sich dann an den Netzbetreiber wenden, um die Nummern frei geben.

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>Freigabenummern von Ihrer Audiokonferenzbrücke

Informationen zum Veröffentlichen von Telefonnummern von Ihrer Audiokonferenzbrücke aus dem Teams Admin Center finden Sie unter Schritte beim Zuweisen einer Servicetelefonnummer für eine Konferenzbrücke **unter** Ändern der Telefonnummern für Ihre [Audiokonferenzbrücke.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge)

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Weitere Informationen zum Verwalten von Microsoft-Audiokonferenzen

Weitere Informationen zum Verwalten von Microsoft Audio Conferencing für Ihre Organisation finden Sie in den folgenden Artikeln:

- Verwalten der Einstellungen des Microsoft-Audiokonferenzdiensts für Ihre [Organisation: Verwalten](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) Sie die Audiokonferenzeinstellungen für Ihre Organisation in Microsoft Teams

- Verwalten der Einstellung des Microsoft-Audiokonferenzdiensts der Benutzer in Ihrer [Organisation:](manage-the-audio-conferencing-settings-for-a-user-in-teams.md) Verwalten Sie die Audiokonferenzeinstellungen für einen Benutzer in Microsoft Teams

- Ändern der Sprachen der automatischen Telefonkonferenz für Ihre Audiokonferenz-Telefonnummern: Legen Sie die Sprachen für die automatische Telefonhalterung für [Audiokonferenzen in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

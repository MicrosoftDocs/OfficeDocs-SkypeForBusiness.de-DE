---
title: Einrichten Microsoft Teams Telefon Systems mit Anrufplan-Telefonnummern
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Microsoft Teams Telefon System mit Anrufplan-Telefonnummern für Benutzer und Dienste in Ihrer Organisation einrichten.
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
- M365initiative-voice
ms.openlocfilehash: fe94987e4abf8c98c32428f608a19db46aacd4c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268010"
---
# <a name="step-2-set-up-teams-phone-system-phone-numbers"></a>Schritt 2: Einrichten von Microsoft Teams-Telefonnummern

Bevor Sie Benutzer oder automatische Telefonzentralen in Ihrer Organisation einrichten können, müssen Sie Telefonnummern für sie abrufen. Es gibt verschiedene Arten von Telefonnummern, aber im Folgenden sind die beiden Arten von Nummern aufgeführt, die Sie in diesem Schritt hinzufügen müssen:

- **Servicenummern** Diese Nummern werden für automatische Telefonzentralen, Audiokonferenzen und Anrufwarteschleifen verwendet. Sie können gebührenpflichtige oder gebührenfreie Telefonnummern sein und große Mengen von Anrufen gleichzeitig verarbeiten. Ihre Firmentelefonnummer muss eine Servicenummer sein, da sie in einem späteren Schritt einer automatischen Telefonzentrale zugewiesen wird.
- **Abonnentennummern** Diese Nummern werden für normale Benutzer verwendet, damit sie Telefonanrufe tätigen und empfangen können.

> [!IMPORTANT]
> Auch wenn Sie Ihre vorhandenen Telefonnummern verwenden möchten, müssen Sie temporäre Telefonnummern erstellen und der Haupttelefonleitung Ihres Unternehmens und Ihren Benutzern zuweisen. In einem späteren Schritt können Sie diese temporären Nummern durch Ihre vorhandenen Telefonnummern ersetzen.

> [!NOTE]
> Es kann mehrere Stunden dauern, bis Ihre neuen Telefonnummern in Teams verfügbar sind.

## <a name="set-up-a-service-number"></a>Einrichten einer Dienstnummer

Die Servicenummer, die Sie jetzt eingerichtet haben, wird in einem späteren Schritt für die Haupttelefonnummer Ihres Unternehmens verwendet.

1. Öffnen Sie das Microsoft Teams Admin Center, und melden Sie sich mit einem Benutzer an, der ein globaler Administrator ist (dies ist normalerweise das Konto, das Sie für die Registrierung für Microsoft 365 verwendet haben).
2. Wechseln Sie in der linken Navigationsleiste zu <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**VoIP-Telefonnummern** > </a>, und klicken Sie dann auf **"Hinzufügen"**.
3. Geben Sie einen Namen für die Bestellung ein, und fügen Sie eine Beschreibung hinzu.
4. Führen Sie auf der Seite "Ort und Menge" die folgenden Schritte aus:
    1. Wählen Sie unter **"Land oder Region**" ein Land oder eine Region aus.
    2. Wählen Sie unter " **Zahlentyp**" eine der folgenden Optionen aus:

        - **Automatische Telefonzentrale (gebührenpflichtige)** Reguläre, nicht gebührenfreie Telefonnummer. Ferngesprächsgebühren werden dem Anrufer in Rechnung gestellt.
        - **Automatische Telefonzentrale (gebührenfrei)** Gebührenfreie Telefonnummer (USA und Kanada) oder freephone (UK). Gebühren für lange Strecken werden Ihrem Unternehmen in Rechnung gestellt. Bevor Sie diese Option auswählen können, müssen Sie Kommunikationsguthaben erwerben. Weitere Informationen finden Sie unter [Was muss ich kaufen, um Sprachfunktionen für mein kleines oder mittleres Unternehmen zu erhalten?](whats-business-voice.md)

    3. Wählen Sie unter **"Menge**" **die Option "1" aus**.
        > [!NOTE]
        > Wenn Sie die Meldung erhalten, dass **Sie nicht über genügend Lizenzen verfügen, um weitere Nummern dieses Typs anzufordern**, stellen Sie sicher, dass Sie Teams Phone with Calling Plan-Bundlelizenzen erworben haben. Weitere Informationen finden Sie unter [Was muss ich kaufen, um Sprachfunktionen für mein kleines oder mittleres Unternehmen zu erhalten?](whats-business-voice.md)
    4. Wählen Sie entweder **"Ort** " oder " **Ortsvorwahl**" aus, je nachdem, ob Sie in der Stadt eines Standorts nach Telefonnummern suchen möchten oder ob Sie nach Nummern in einer bestimmten Ortsvorwahl suchen möchten.
    5. Wenn Sie **"Ort**" auswählen:

        1. Geben Sie im Schritt " [Notfallstandort](set-up-emergency-locations.md) einrichten" die Stadt ein, in der sich Ihre Notfalladresse befindet. Wenn Sie einen neuen Standort für ein anderes Büro oder ein Home-Office erstellen müssen, klicken Sie auf **"Standort hinzufügen"**.
        2. Wählen Sie unter **"Vorwahl**" eine Vorwahl und dann **"Weiter** " aus, um Ihre Nummer zu reservieren.

    6. Wenn Sie **"Vorwahl**" auswählen, geben Sie die Zu durchsuchenden Vorwahl ein, und wählen Sie dann **"Weiter** " aus, um Ihre Nummer zu reservieren.

5. Wählen Sie die gewünschte Zahl aus. Sie haben 10 Minuten Zeit, um Ihre Telefonnummer auszuwählen und Ihre Bestellung zu aufgeben. Wenn Sie länger als 10 Minuten dauern, wird die Telefonnummer an den Nummernpool zurückgegeben.
6. Wenn Sie ihre Bestellung aufgeben möchten, klicken Sie auf **"Bestellung aufgeben"** und dann auf **"Fertig stellen"**.

## <a name="set-up-phone-numbers-for-your-users"></a>Einrichten von Telefonnummern für Ihre Benutzer

1. Öffnen Sie das Microsoft Teams Admin Center, und melden Sie sich mit einem Benutzer an, der ein globaler Administrator ist. Dies ist normalerweise das Konto, das Sie für die Registrierung für Microsoft 365 verwendet haben.
2. Wechseln Sie in der linken Navigationsleiste zu <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**VoIP-Telefonnummern** > </a>, und klicken Sie dann auf **"Hinzufügen"**.
3. Geben Sie einen Namen für die Bestellung ein, und fügen Sie eine Beschreibung hinzu.
4. Führen Sie auf der Seite "Ort und Menge" die folgenden Schritte aus:

    1. Wählen Sie unter **"Land oder Region**" ein Land oder eine Region aus.
    2. Wählen Sie unter **"Zahlentyp**" **die Option "Benutzer (Abonnent)**" aus.
    3. Geben Sie unter **"Menge**" die Anzahl der Zahlen ein, die Sie für Ihre Organisation benötigen.
    4. Wählen Sie entweder **"Ort** " oder " **Ortsvorwahl**" aus, je nachdem, ob Sie in der Stadt eines Standorts nach Telefonnummern suchen möchten oder ob Sie nach Nummern in einer bestimmten Ortsvorwahl suchen möchten.
    5. Wenn Sie **"Ort**" auswählen:

        1. Geben Sie im Schritt " [Notfallstandort](set-up-emergency-locations.md) einrichten" die Stadt ein, in der sich Ihre Notfalladresse befindet. Wenn Sie einen neuen Standort für ein anderes Büro oder ein Home-Office erstellen müssen, klicken Sie auf **"Standort hinzufügen"**.
        2. Wählen Sie unter **"Vorwahl**" eine Vorwahl und dann **"Weiter** " aus, um Ihre Nummer zu reservieren.

    6. Wenn Sie **"Vorwahl**" auswählen, geben Sie die Zu durchsuchenden Vorwahl ein, und wählen Sie dann **"Weiter** " aus, um Ihre Nummer zu reservieren.
5. Wählen Sie die gewünschten Zahlen aus. Sie haben 10 Minuten Zeit, um Ihre Telefonnummern auszuwählen und Ihre Bestellung zu aufgeben. Wenn Sie mehr als 10 Minuten benötigen, werden die Telefonnummern an den Nummernpool zurückgegeben.
6. Wenn Sie ihre Bestellung aufgeben möchten, klicken Sie auf **"Bestellung aufgeben"** und dann auf **"Fertig stellen"**.

> [!div class="nextstepaction"]
> [Nächster Schritt: Zuweisen von Lizenzen zu Teams-Benutzern](set-up-licenses.md)

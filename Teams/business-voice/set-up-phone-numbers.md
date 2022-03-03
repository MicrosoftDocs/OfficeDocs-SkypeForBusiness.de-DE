---
title: Einrichten von Microsoft Teams Telefonsystem mit Anrufplan-Telefonnummern
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Erfahren Sie, wie Sie Microsoft Teams Telefonsystem Anrufplan-Telefonnummern für Benutzer und Dienste in Ihrer Organisation einrichten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19d2b165e85620b0fb9e9e8242adacc4c07f2c53
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053254"
---
# <a name="step-2-set-up-teams-phone-system-phone-numbers"></a>Schritt 2: Einrichten Teams Telefonsystem Telefonnummern

Bevor Sie Benutzer oder automatische Telefon attendants in Ihrer Organisation einrichten können, müssen Sie Telefonnummern für diese Benutzer erhalten. Es gibt verschiedene Arten von Telefonnummern, es gibt jedoch die beiden folgenden Arten von Nummern, die Sie in diesem Schritt hinzufügen müssen:

- **Servicenummern** Diese Nummern werden für automatische Telefonkonferenzen, Audiokonferenzen und Anrufwarteschleifen verwendet. Sie können gebührenpflichtige oder gebührenfreie Telefonnummern sein und große Mengen von Anrufen gleichzeitig verarbeiten. Ihre Firmentelefonnummer muss eine Servicenummer sein, da sie in einem späteren Schritt einer automatischen Telefongesellschaft zugewiesen wird.
- **Telefonnummern für Abonnenten** Diese Nummern werden für normale Benutzer verwendet, damit sie Telefonanrufe erstellen und empfangen können.

> [!IMPORTANT]
> Auch wenn Sie Ihre vorhandenen Telefonnummern verwenden möchten, müssen Sie temporäre Telefonnummern erstellen und der Haupttelefonleitung Ihres Unternehmens und Ihren Benutzern zuweisen. Sie können diese temporären Nummern in einem späteren Schritt durch Ihre vorhandenen Telefonnummern ersetzen.

> [!NOTE]
> Es kann mehrere Stunden dauern, bis Ihre neuen Telefonnummern in der neuen Version verfügbar Teams.

## <a name="set-up-a-service-number"></a>Einrichten einer Servicenummer

Die Servicenummer, die Sie jetzt einrichten, wird in einem späteren Schritt für die Haupttelefonnummer Ihres Unternehmens verwendet.

1. Öffnen Sie Microsoft Teams Admin Center, und melden Sie sich mit einem Benutzer an, der ein globaler Administrator ist (dies ist normalerweise das Konto, mit dem Sie sich für Microsoft 365).
2. Wechseln Sie in der linken <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Navigationsleiste** >  zu **Sprachanruf Telefon,**</a> und klicken Sie dann auf **Hinzufügen**.
3. Geben Sie einen Namen für den Auftrag ein, und fügen Sie eine Beschreibung hinzu.
4. Gehen Sie auf der Seite Standort und Menge wie folgt vor:
    1. Wählen **Sie unter Land oder Region** ein Land oder eine Region aus.
    2. Wählen **Sie unter** Zahlentyp eine der folgenden Optionen aus:

        - **Automatische Attendant (Gebührenpflichtig)** Reguläre, gebührenfreie Telefonnummer. Gebühren für fernes Telefonieren werden dem Anrufer in Rechnung gestellt.
        - **Automatische Attendant (gebührenfrei)** Gebührenfreie Telefonnummer (USA und Kanada) oder kostenlose Telefonnummer (UK) Gebühren für lange Entfernungen werden Ihrem Unternehmen in Rechnung gestellt. Bevor Sie diese Option auswählen können, müssen Sie Guthaben für Kommunikationen erwerben. Weitere Informationen finden Sie unter Was muss ich kaufen, um Sprachfunktionen für mein kleines oder [mittleres Unternehmen zu erhalten?](whats-business-voice.md).

    3. Wählen **Sie unter** Menge die Option **1 aus**.
        > [!NOTE]
        > Wenn die Meldung Sie verfügen nicht über genügend Lizenzen zum Anfordern von weiteren Nummern dieses Typs **verfügen, stellen** Sie sicher, dass Sie Teams Telefon mit Anrufplan-Bündellizenzen erworben haben. Weitere Informationen finden Sie unter Was muss ich kaufen, um Sprachfunktionen für mein kleines oder [mittleres Unternehmen zu erhalten?](whats-business-voice.md).
    4. Wählen **Sie entweder** **Ort oder** Ortscode aus, je nachdem, ob Sie anhand der Stadt eines Standorts nach Telefonnummern oder in einer bestimmten Vorwahl nach Nummern suchen möchten.
    5. Wenn Sie Standort **auswählen**:

        1. Geben Sie im Schritt Notfallstandorte einrichten den Ort ein, [](set-up-emergency-locations.md) in dem sich Ihre Notfalladresse befindet. Wenn Sie einen neuen Standort für ein anderes Büro oder für ein Heimbüro erstellen müssen, klicken Sie auf **Standort hinzufügen**.
        2. Wählen **Sie unter Vorwahl** eine Vorwahl aus, und wählen Sie **dann Weiter aus** , um Ihre Nummer zu reservieren.

    6. Wenn Sie **Vorwahl auswählen**, geben Sie die Vorwahl ein, die Sie durchsuchen möchten, und wählen Sie dann Weiter aus **, um Ihre** Nummer zu reservieren.

5. Wählen Sie die Zahl aus, die Sie wünschen. Sie haben 10 Minuten Zeit, um Ihre Telefonnummer auszuwählen und Ihre Bestellung auf bestellung zu geben. Wenn Sie länger als 10 Minuten dauern, wird die Telefonnummer an den Nummernpool zurückgegeben.
6. Wenn Sie ihre Bestellung fertig stellen möchten, klicken Sie **auf Bestellung bestellen** und dann auf Fertig **stellen.**

## <a name="set-up-phone-numbers-for-your-users"></a>Einrichten von Telefonnummern für Ihre Benutzer

1. Öffnen Sie Microsoft Teams Admin Center, und melden Sie sich mit einem Benutzer an, der ein globaler Administrator ist. Dies ist normalerweise das Konto, mit dem Sie sich für ihr Konto Microsoft 365.
2. Wechseln Sie in der linken <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Navigationsleiste** >  zu **Sprachanruf Telefon,**</a> und klicken Sie dann auf **Hinzufügen**.
3. Geben Sie einen Namen für den Auftrag ein, und fügen Sie eine Beschreibung hinzu.
4. Gehen Sie auf der Seite Standort und Menge wie folgt vor:

    1. Wählen **Sie unter Land oder Region** ein Land oder eine Region aus.
    2. Wählen **Sie unter Zahlentyp** die **Option Benutzer (Abonnent) aus**.
    3. Geben **Sie** unter Menge die Anzahl der Nummern ein, die Sie für Ihre Organisation verwenden möchten.
    4. Wählen **Sie entweder** **Ort oder** Ortscode aus, je nachdem, ob Sie anhand der Stadt eines Standorts nach Telefonnummern oder in einer bestimmten Vorwahl nach Nummern suchen möchten.
    5. Wenn Sie Standort **auswählen**:

        1. Geben Sie im Schritt Notfallstandorte einrichten den Ort ein, [](set-up-emergency-locations.md) in dem sich Ihre Notfalladresse befindet. Wenn Sie einen neuen Standort für ein anderes Büro oder für ein Heimbüro erstellen müssen, klicken Sie auf **Standort hinzufügen**.
        2. Wählen **Sie unter Vorwahl** eine Vorwahl aus, und wählen Sie **dann Weiter aus** , um Ihre Nummer zu reservieren.

    6. Wenn Sie **Vorwahl auswählen**, geben Sie die Vorwahl ein, die Sie durchsuchen möchten, und wählen Sie dann Weiter aus **, um Ihre** Nummer zu reservieren.
5. Wählen Sie die Zahlen aus, die Sie wünschen. Sie haben 10 Minuten Zeit, um Ihre Telefonnummern auszuwählen und Ihre Bestellung auf bestellung zu geben. Wenn Sie länger als 10 Minuten zeit haben, werden die Telefonnummern an den Telefonnummernpool zurückgegeben.
6. Wenn Sie ihre Bestellung fertig stellen möchten, klicken Sie **auf Bestellung bestellen** und dann auf **Fertig stellen**.

> [!div class="nextstepaction"]
> [Nächster Schritt: Zuweisen von Lizenzen Teams Benutzern](set-up-licenses.md)

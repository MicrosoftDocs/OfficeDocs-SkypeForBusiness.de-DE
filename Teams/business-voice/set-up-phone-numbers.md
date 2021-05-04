---
title: Einrichten Microsoft 365 Business Voice Telefonnummern
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Erfahren Sie, wie Sie Microsoft 365 Business Voice Telefonnummern für Benutzer und Dienste in Ihrer Organisation einrichten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cec0bc8e55ef6be169de1f48a375ab40ca8ccf7
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130052"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a>Schritt 2: Einrichten von Business Voice-Telefonnummern

Bevor Sie Benutzer oder automatische Telefontelefone in Ihrer Organisation einrichten können, müssen Sie telefonnummern dafür erhalten. Es gibt verschiedene Arten von Telefonnummern, doch die folgenden sind die beiden Arten von Nummern, die Sie in diesem Schritt hinzufügen müssen:

- **Servicenummern** Diese Nummern werden für automatische Telefonkonferenzen, Audiokonferenzen und Anrufwarteschlangen verwendet. Sie können gebührenpflichtige oder gebührenfreie Nummern sein und große Mengen von Anrufen gleichzeitig verarbeiten. Ihre Firmentelefonnummer muss eine Dienstnummer sein, da sie in einem späteren Schritt einer automatischen Telefonwarte zugewiesen wird.
- **Abonnentennummern** Diese Nummern werden für normale Benutzer verwendet, damit sie Telefonanrufe machen und empfangen können.

> [!IMPORTANT]
> Auch wenn Sie Ihre vorhandenen Telefonnummern verwenden möchten, müssen Sie der Haupttelefonleitung Ihres Unternehmens und Ihren Benutzern temporäre Telefonnummern erstellen und zuweisen. Sie können diese temporären Nummern in einem späteren Schritt durch Ihre vorhandenen Telefonnummern ersetzen.

> [!NOTE]
> Es kann mehrere Stunden dauern, bis Ihre neuen Telefonnummern in der App Teams.

## <a name="set-up-a-service-number"></a>Einrichten einer Servicenummer

Die dienstnummer, die Sie jetzt eingerichtet haben, wird in einem späteren Schritt für die Haupttelefonnummer Ihres Unternehmens verwendet.

1. Wechseln Sie zum Microsoft Teams Admin Center.
2. Wechseln Sie im linken Navigationsbereich zu **Voice** Telefon , und klicken Sie  >  dann auf **Hinzufügen.**
3. Geben Sie einen Namen für die Bestellung ein, und fügen Sie eine Beschreibung hinzu.
4. Gehen Sie auf der Seite Ort und Menge wie folgt vor:
    1. Wählen **Sie unter Land oder Region** ein Land oder eine Region aus.
    2. Wählen **Sie unter** Zahlentyp eine der folgenden Optionen aus:

        - **Automatische Attendant (Gebührenpflichtig)** Normale, nicht gebührenfreie Telefonnummer. Dem Anrufer werden Gebühren für lange Entfernungen in Rechnung gestellt.
        - **Automatische Attendant (gebührenfrei)** Gebührenfreie Telefonnummer (USA und Kanada) oder gebührenfreie Telefonnummer (UK). Gebühren für lange Entfernungen werden ihrem Unternehmen in Rechnung gestellt. Bevor Sie diese Option auswählen können, müssen Sie Guthaben für Kommunikationen erwerben. Weitere Informationen finden Sie unter [Was muss ich kaufen,](what-to-buy.md)um Microsoft 365 Business Voice? .

    3. Wählen **Sie unter Menge** die Option **1 aus.**
        > [!NOTE]
        > Wenn Sie die Meldung Erhalten Sie **nicht** über genügend Lizenzen zum Anfordern von weiteren Nummern dieses Typs verfügen, stellen Sie sicher, dass Sie Business Voice-Lizenzen erworben haben. Weitere Informationen finden Sie unter [Was muss ich kaufen,](what-to-buy.md)um Microsoft 365 Business Voice? .
    4. Geben **Sie** unter Ort den Namen des Speicherorts ein, den Sie im Schritt Notfallstandorte [einrichten erstellt](set-up-emergency-locations.md) haben.
    5. Wählen **Sie unter** Vorwahl eine Vorwahl aus, und klicken Sie dann auf **Weiter,** um Ihre Zahlen auszuwählen.
5. Wählen Sie die von Ihnen ausgewählte Zahl aus. Sie haben 10 Minuten Zeit, Ihre Telefonnummer auszuwählen und Ihre Bestellung zu platzieren. Wenn Sie mehr als 10 Minuten dauern, wird die Telefonnummer an den Zahlenpool zurückgegeben.
6. Wenn Sie bereit sind, Ihre Bestellung zu platzieren, klicken Sie auf Bestellung **platzieren** und dann **auf Fertig stellen.**

## <a name="set-up-phone-numbers-for-your-users"></a>Einrichten von Telefonnummern für Ihre Benutzer

1. Wechseln Sie zum Microsoft Teams Admin Center.
2. Wechseln Sie im linken Navigationsbereich zu **Voice** Telefon , und klicken Sie  >  dann auf **Hinzufügen.**
3. Geben Sie einen Namen für die Bestellung ein, und fügen Sie eine Beschreibung hinzu.
4. Gehen Sie auf der Seite Ort und Menge wie folgt vor:

    1. Wählen **Sie unter Land oder Region** ein Land oder eine Region aus.
    2. Wählen **Sie unter** Zahlentyp die Option Benutzer **(Abonnent) aus.**
    3. Geben **Sie** unter Menge die Anzahl der Zahlen ein, die Sie für Ihre Organisation verwenden möchten.
    4. Wählen **Sie unter** Ort einen Speicherort aus. Sie können entweder den Notfallstandort [](set-up-emergency-locations.md) auswählen, den Sie im Schritt Notfallstandorte einrichten hinzugefügt haben, oder wenn Sie einen neuen Standort für ein anderes Büro oder ein Home Office erstellen müssen, klicken Sie auf Standort **hinzufügen.**
    5. Wählen **Sie unter** Vorwahl eine Vorwahl aus, und klicken Sie dann auf **Weiter,** um Ihre Zahlen auszuwählen.
5. Wählen Sie die von Ihnen ausgewählten Zahlen aus. Sie haben 10 Minuten Zeit, um Ihre Telefonnummern auszuwählen und Ihre Bestellung zu platzieren. Wenn Sie mehr als 10 Minuten dauern, werden die Telefonnummern an den Zahlenpool zurückgegeben.
6. Wenn Sie bereit sind, Ihre Bestellung zu platzieren, klicken Sie auf Bestellung **platzieren** und dann **auf Fertig stellen.**

> [!div class="nextstepaction"]
> [Nächster Schritt: Zuweisen von Lizenzen zu Teams Benutzern](set-up-licenses.md)

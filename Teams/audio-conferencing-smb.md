---
title: Einrichten von Audiokonferenzen für kleine und mittelständische Unternehmen
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie Audiokonferenzen in Ihrem kleinen oder mittleren Unternehmen für Personen festlegen, die sich per Telefon in Besprechungen einrufen müssen. '
ms.openlocfilehash: fc9a87c2e516dc97fae5c71f72b5a7ef82c75c8d
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055625"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Einrichten von Audiokonferenzen für kleine und mittelständische Unternehmen

Mit Audiokonferenzen können sich Personen mit einem Telefon in Teams-Besprechungen einrufen, statt die Teams-App auf ihrem Mobilgerät oder vom Computer aus zu verwenden.  

Wenn Sie ein kleines oder mittelgroßes Unternehmen mit bis zu 300 Benutzern sind und aktuell über keine Lizenzen für Audiokonferenzen verfügen, können Sie Audiokonferenzen ein Jahr kostenlos erhalten. Dieses kostenlose Angebot ist ab dem 1. Oktober 2020 verfügbar.

Die Add-On-Lizenz für Audiokonferenzen kann auf Benutzer angewendet werden, die über Microsoft 365 Business Basic-, Business Standard-, Business Premium-, Enterprise E1- oder Enterprise E3-Lizenzen verfügen. Weitere Informationen finden Sie unter [Teams von Add-On-Lizenzen.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Wenn Sie über Enterprise E5 oder Microsoft 365 Business Voice verfügen, können Sie das kostenlose Audiokonferenz-Angebot nicht nutzen, da diese Lizenzen bereits Audiokonferenzen enthalten.

In diesem Artikel werden Sie durch das Einrichten von Audiokonferenzen erläutert. Sie müssen Audiokonferenzen nur für Personen einrichten, die Besprechungen planen oder leiten möchten. Besprechungsteilnehmer, die sich in Besprechungen einbesprechen, benötigen keine Lizenzen oder sonstige Einrichtung. Weitere Informationen finden Sie unter [Audiokonferenz.](audio-conferencing-in-office-365.md)

## <a name="set-up-audio-conferencing"></a>Einrichten von Audiokonferenzen

Wenn Sie Audiokonferenzen einrichten, wird Ihrer Konferenzbrücke automatisch eine Telefonnummer zugewiesen, damit sie in Besprechungseinladungen verwendet werden kann. Die Als Standardnummer für Ihre Konferenzbrücke zugewiesene Telefonnummer gehört dem Land oder der Region Ihrer Organisation an. Bei dieser Telefonnummer handelt es sich um eine gebührenpflichtige Nummer, bei der Fernkosten anfallen können.

> [!NOTE]
> Sie können auch eine gebührenfreie Nummer verwenden, für die ein paar zusätzliche Schritte erforderlich sind. Weitere Informationen zu den Telefonnummern für Ihre Konferenzbrücke finden Sie unter [Audiokonferenz-Telefonnummern](#audio-conferencing-phone-numbers) weiter später in diesem Artikel.

### <a name="step-1-get-audio-conferencing-licenses"></a>Schritt 1: Erwerben von Lizenzen für Audiokonferenzen

Erhalten Sie eine Lizenz für Audiokonferenzen für jede Person, die Besprechungen führt. Verwenden Sie Microsoft 365 Admin Center zu diesem Thema.

1. Wechseln Sie Microsoft 365 Admin Center Dienste zum Kauf von Abrechnungen , und wählen Sie dann unten auf der Seite  >   **Add-Ons aus.**
2. Wählen **Microsoft 365 audio conferencing adoption promo**  >  **details** aus, und wählen Sie dann Jetzt erhalten **aus.**
3. Geben Sie die Anzahl der Lizenzen ein, die Sie für Ihre Besprechungsorganisatoren benötigen, und füllen Sie dann Ihre Bestellung aus.

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Screenshot der Lizenz für die Einführung von Audiokonferenzen":::

    > [!NOTE]
    > Je nachdem, ob Sie allen Benutzern, die nicht über diese Lizenz verfügen, eine Lizenz für Audiokonferenzen automatisch zuweisen möchten, können Sie die Option Automatische Zuweisung zu allen Benutzern ohne Lizenzen aktivieren oder aktivieren.

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Schritt 2: Zuweisen einer Lizenz für Audiokonferenzen zu Benutzern, die Besprechungen führen

Weisen Sie jeder Person, die Besprechungen führen soll, eine Lizenz zu. Verwenden Sie Microsoft 365 Admin Center zu diesem Thema.

#### <a name="assign-a-license-to-one-user"></a>Zuweisen einer Lizenz zu einem Benutzer

1. Wechseln Sie Microsoft 365 Admin Center Der Benutzer zu  >  **Aktive Benutzer.**  
2. Wählen Sie die Zeile des Benutzers aus, dem Sie die Lizenz zuweisen möchten, und wählen Sie dann im Bereich Lizenzen **und Apps aus.**
3. Aktivieren Sie **Microsoft 365 Kontrollkästchen Audiokonferenz aktivieren,** und wählen Sie dann **Änderungen speichern aus.**

#### <a name="assign-a-license-to-multiple-users"></a>Zuweisen einer Lizenz für mehrere Benutzer

1. Wechseln Sie Microsoft 365 Admin Center Der Benutzer zu  >  **Aktive Benutzer.**  
2. Wählen Sie die Kreise neben den Benutzern aus, den Sie die Lizenz zuweisen möchten, und wählen Sie dann **Produktlizenzen verwalten aus.**
3. Wählen Sie **im Bereich Produktlizenzen** verwalten die Option **Weitere zuweisen aus.**
4. Aktivieren Sie **Microsoft 365 Kontrollkästchen Audiokonferenz aktivieren,** und wählen Sie dann **Änderungen speichern aus.**  

## <a name="schedule-teams-meetings-in-outlook"></a>Planen Teams Besprechungen in Outlook

Ihre Besprechungsorganisatoren können jetzt Besprechungen in einem Outlook. Wechseln Outlook Kalender, und wählen Sie dann die Schaltfläche Neues Teams **aus.** Die Einwahlnummern der Besprechung und die Konferenz-ID werden automatisch der Besprechungseinladung hinzugefügt, die an die Besprechungsteilnehmer gesendet wird. Weitere Informationen finden Sie unter [Planen Teams Besprechung in Outlook.](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)

> [!NOTE]
> Wenn Sie möchten, können Sie Besprechungseinladungen anpassen, um Ihr Firmenlogo, Links zur Supportwebsite und einen Haftungsausschluss sowie eine Fußzeile als Text hinzuzufügen. Weitere Informationen finden Sie unter [Anpassen von Besprechungseinladungen.](meeting-settings-in-teams.md#customize-meeting-invitations)

## <a name="audio-conferencing-phone-numbers"></a>Telefonnummern für Audiokonferenzen

Es gibt zwei Arten von Nummern, die Sie für Ihre Konferenzbrücke verwenden können. Sie können entweder **freigegebene** Nummern (wie im Abschnitt Einrichten von [Audiokonferenzen](#set-up-audio-conferencing) weiter oben in diesem Artikel) oder dedizierte **Nummern verwenden.** Hier finden Sie weitere Informationen zu den einzelnen -

### <a name="shared-numbers"></a>Freigegebene Nummern

Eine freigegebene Nummer ist eine Nummer, die von allen Organisationen gemeinsam genutzt wird. Freigegebene Nummern sind gebührenpflichtige Nummern und werden automatisch zugewiesen, wenn Sie Audiokonferenzen einrichten.

Wenn Sie die Standardnummer sehen möchten, die Ihrer Konferenzbrücke zugewiesen ist, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu Konferenzbrücken für Besprechungen , und suchen Sie dann die Nummer für den  >  nächstgelegenen Ort.

### <a name="dedicated-numbers"></a>Dedizierte Nummern

Eine dedizierte Nummer ist eine Nummer, die nur für Ihre Benutzer verfügbar ist. Eine dedizierte Nummer kann eine gebührenpflichtige oder eine gebührenfreie Nummer sein. Um eine dedizierte Nummer zu verwenden, müssen Sie zuerst die Nummer erhalten, sie Ihrer Konferenzbrücke zuweisen und dann die Nummer jeder Person zuweisen, die Besprechungen führen wird.

Es gibt eine Reihe von Möglichkeiten, eine dedizierte Nummer zu erhalten. Sie können eine Nummer von Microsoft erhalten oder eine vorhandene Nummer von Ihrem aktuellen Dienstanbieter an Microsoft übertragen (porten). Weitere Informationen dazu finden Sie unter Abrufen [von Leistungsnummern.](getting-service-phone-numbers.md)

Wenn Sie eine gebührenfreie Nummer verwenden, müssen Sie zuerst jeder Person, die Besprechungen führt, eine Lizenz für Guthaben für Kommunikationen zuweisen. Weitere Informationen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihre Organisation.](set-up-communications-credits-for-your-organization.md)

Nachdem Sie Ihre Nummer erhalten haben, weisen Sie sie Ihrer Konferenzbrücke zu. Verwenden Sie Microsoft Teams Admin Center, um dies zu tun.

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu  >  **Besprechungen Konferenzbrücken**.
2. Wählen **Sie Hinzufügen** und dann **Gebührenpflichtige Nummer** oder **Gebührenfreie Nummer aus.**
3. Wählen Sie **im Bereich Telefonnummer hinzufügen** die Nummer und dann Übernehmen **aus.**

Weisen Sie dann die Nummer jeder Person zu, die Besprechungen führen soll. Verwenden Sie Microsoft Teams Admin Center, um dies zu tun.

1. Wählen Sie im linken Navigationsbereich Microsoft Teams Admin Center Benutzer **aus,** klicken Sie auf den Anzeigenamen des Benutzers, und wählen Sie **Bearbeiten aus.**
2. Wählen **Sie** Bearbeiten neben **Audiokonferenz aus,** und wählen Sie dann im Bereich  **Audiokonferenz** in  den Listen Gebührenpflichtige Nummer oder Gebührenfreie Rufnummer eine Nummer aus, und wählen Sie dann Übernehmen **aus.**

## <a name="related-topics"></a>Verwandte Themen

- [Audiokonferenzen](audio-conferencing-in-office-365.md)
- [Einrichten von Audiokonferenzen für Teams](set-up-audio-conferencing-in-teams.md)
- [Telefonnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing-in-teams.md)
- [Allgemeine Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md)
- [Abrufen von Servicenummern](getting-service-phone-numbers.md)
- [Teams von Add-On-Lizenzen](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Zuweisen von Lizenzen zu Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users)

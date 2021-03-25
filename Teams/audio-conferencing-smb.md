---
title: Einrichten von Audiokonferenzen für kleine und mittelständische Unternehmen
ms.author: v-cichur
author: cichur
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie Audiokonferenzen in Ihrem kleinen oder mittleren Unternehmen für Personen festlegen, die ein Telefon zum Anrufen in Besprechungen verwenden müssen. '
ms.openlocfilehash: e7a3461453255a7a61f6a1095e9cb9697070771c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122349"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Einrichten von Audiokonferenzen für kleine und mittelständische Unternehmen

Mit Audiokonferenzen können Personen sich über ein Telefon in Teams-Besprechungen einrufen, anstatt die Teams-App auf ihrem mobilen Gerät oder von ihrem Computer aus zu verwenden.  

Wenn Sie ein kleines oder mittelgroßes Unternehmen mit bis zu 300 Benutzern sind und derzeit keine Lizenzen für Audiokonferenzen besitzen, können Sie Audiokonferenzen ein Jahr kostenlos nutzen. Dieses kostenlose Angebot ist ab dem 1. Oktober 2020 verfügbar.

Die Lizenz für Audiokonferenzen kann auf Benutzer angewendet werden, die über Microsoft 365 Business Basic-, Business Standard-, Business Premium-, Enterprise E1- oder Enterprise E3-Lizenzen verfügen. Weitere Informationen finden Sie unter [Teams-Add-On-Lizenzen.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Wenn Sie über Enterprise E5 oder Microsoft 365 Business Voice verfügen, können Sie das kostenlose Audiokonferenzangebot nicht nutzen, da diese Lizenzen bereits Audiokonferenzen enthalten.

In diesem Artikel erfahren Sie, wie Sie Audiokonferenzen einrichten. Sie müssen Audiokonferenzen nur für Personen einrichten, die Besprechungen planen oder leiten möchten. Besprechungsteilnehmer, die an Besprechungen teilnehmen, benötigen keine Lizenzen oder andere Setups. Weitere Informationen finden Sie unter [Audiokonferenzen](audio-conferencing-in-office-365.md).

## <a name="set-up-audio-conferencing"></a>Einrichten von Audiokonferenzen

Wenn Sie Audiokonferenzen einrichten, wird Ihrer Konferenzbrücke automatisch eine Telefonnummer zugewiesen, sodass sie in Besprechungseinladungen verwendet werden kann. Die Telefonnummer, die als Standardnummer Ihrer Konferenzbrücke zugewiesen ist, ist eine Telefonnummer aus dem Land oder der Region Ihrer Organisation. Bei dieser Telefonnummer handelt es sich um eine Gebührennummer, bei der Ferngebühren anfallen können.

> [!NOTE]
> Sie können auch eine gebührenfreie Nummer verwenden, die einige zusätzliche Schritte erfordert. Weitere Informationen zu Telefonnummern für Ihre Konferenzbrücke finden Sie unter [Audiokonferenztelefonnummern](#audio-conferencing-phone-numbers) weiter in diesem Artikel.

### <a name="step-1-get-audio-conferencing-licenses"></a>Schritt 1: Erwerben von Lizenzen für Audiokonferenzen

Erhalten Sie eine Lizenz für Audiokonferenzen für jede Person, die Besprechungen führt. Verwenden Sie dazu das Microsoft 365 Admin Center.

1. Wechseln Sie im Microsoft 365 Admin Center zu Abrechnungskaufdienste, und wählen Sie dann unten auf der Seite  >   **Add-Ons aus.**
2. Wählen **Sie Microsoft 365 Audio Conferencing Adoption Promo** Details aus, und wählen Sie dann Jetzt erhalten  >   **aus.**
3. Geben Sie die Anzahl der Lizenzen ein, die Sie für Ihre Besprechungsorganisatoren benötigen, und füllen Sie dann Ihre Bestellung aus.

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Screenshot der Promotionslizenz für Audiokonferenzen":::

    > [!NOTE]
    > Sie können die Option Automatisch allen Benutzern ohne Lizenzen zuweisen löschen oder **auswählen,** je nachdem, ob Sie allen Benutzern, die nicht über diese Lizenz verfügen, automatisch eine Lizenz für Audiokonferenzen zuweisen möchten.

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Schritt 2: Zuweisen einer Lizenz für Audiokonferenzen zu Benutzern, die Besprechungen führen

Weisen Sie jeder Person, die Besprechungen führt, eine Lizenz zu. Verwenden Sie dazu das Microsoft 365 Admin Center.

#### <a name="assign-a-license-to-one-user"></a>Zuweisen einer Lizenz zu einem Benutzer

1. Wechseln Sie im Microsoft 365 Admin Center zu **Aktive**  >  **Benutzer .**  
2. Wählen Sie die Zeile des Benutzers aus, dem Sie die Lizenz zuweisen möchten, und wählen Sie dann im Bereich Lizenzen **und Apps aus.**
3. Aktivieren Sie **das Kontrollkästchen Microsoft 365 Audiokonferenzen,** und wählen Sie dann **Änderungen speichern aus.**

#### <a name="assign-a-license-to-multiple-users"></a>Zuweisen einer Lizenz zu mehreren Benutzern

1. Wechseln Sie im Microsoft 365 Admin Center zu **Aktive**  >  **Benutzer .**  
2. Wählen Sie die Kreise neben den Benutzern aus, dem Sie die Lizenz zuweisen möchten, und wählen Sie dann **Produktlizenzen verwalten aus.**
3. Wählen Sie **im Bereich Produktlizenzen verwalten** die Option Weitere zuweisen **aus.**
4. Aktivieren Sie **das Kontrollkästchen Microsoft 365 Audiokonferenzen,** und wählen Sie dann **Änderungen speichern aus.**  

## <a name="schedule-teams-meetings-in-outlook"></a>Planen von Teams-Besprechungen in Outlook

Ihre Besprechungsorganisatoren können jetzt Besprechungen in Outlook planen. Wechseln Sie in Outlook zu **Kalender,** und wählen Sie dann die Schaltfläche **Neue Teams-Besprechung** aus. Die Einwahlnummern der Besprechung und die Konferenz-ID werden automatisch der Besprechungseinladung hinzugefügt, die an Besprechungsteilnehmer gesendet wird. Weitere Informationen finden Sie unter [Planen einer Teams-Besprechung in Outlook.](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)

> [!NOTE]
> Wenn Sie möchten, können Sie Besprechungseinladungen anpassen, um Ihr Firmenlogo, Links zu Ihrer Supportwebsite und einen Haftungsausschluss sowie eine Textfußzeile hinzuzufügen. Weitere Informationen finden Sie unter [Anpassen von Besprechungseinladungen.](meeting-settings-in-teams.md#customize-meeting-invitations)

## <a name="audio-conferencing-phone-numbers"></a>Telefonnummern für Audiokonferenzen

Es gibt zwei Arten von Zahlen, die Sie für ihre Konferenzbrücke verwenden können. Sie können entweder **freigegebene** Nummern (wie im Abschnitt Einrichten von [Audiokonferenzen](#set-up-audio-conferencing) weiter oben in diesem Artikel) oder dedizierte **Nummern verwenden.** Hier finden Sie weitere Informationen zu den einzelnen.

### <a name="shared-numbers"></a>Freigegebene Nummern

Eine freigegebene Nummer ist eine Zahl, die für alle Organisationen freigegeben ist. Freigegebene Nummern sind Gebührennummern und werden automatisch zugewiesen, wenn Sie Audiokonferenzen einrichten.

Wenn Sie die Standardnummer sehen möchten, die Ihrer Konferenzbrücke zugewiesen ist, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu Besprechungskonferenzbrücken, und suchen Sie dann die Nummer für den Standort, der Ihnen am nächsten  >  ist.

### <a name="dedicated-numbers"></a>Dedizierte Nummern

Eine dedizierte Nummer ist eine Zahl, die nur für Ihre Benutzer verfügbar ist. Eine dedizierte Nummer kann eine gebührenpflichtige oder eine gebührenfreie Nummer sein. Wenn Sie eine dedizierte Nummer verwenden möchten, müssen Sie zuerst die Nummer erhalten, sie Ihrer Konferenzbrücke zuweisen und die Nummer dann jeder Person zuweisen, die Besprechungen führen soll.

Es gibt mehrere Möglichkeiten, eine dedizierte Nummer zu erhalten. Sie können eine Nummer von Microsoft erhalten oder eine vorhandene Nummer von Ihrem aktuellen Dienstanbieter an Microsoft übertragen (porten). Weitere Informationen dazu finden Sie unter Abrufen [von Servicenummern.](getting-service-phone-numbers.md)

Denken Sie daran: Wenn Sie eine gebührenfreie Nummer verwenden, müssen Sie zuerst jeder Person, die Besprechungen führt, eine Lizenz für Guthaben für Kommunikationen zuweisen. Weitere Informationen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihre Organisation.](set-up-communications-credits-for-your-organization.md)

Nachdem Sie Ihre Nummer erhalten haben, weisen Sie sie Ihrer Konferenzbrücke zu. Verwenden Sie dazu das Microsoft Teams Admin Center.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu  >  **Konferenzbrücken für Besprechungen.**
2. Wählen **Sie Hinzufügen** und dann **Gebührenfreie Nummer** oder **gebührenfreie Nummer aus.**
3. Wählen Sie **im Bereich** Telefonnummer hinzufügen die Nummer und dann Übernehmen **aus.**

Weisen Sie dann jeder Person, die Besprechungen führt, die Nummer zu. Verwenden Sie dazu das Microsoft Teams Admin Center.

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers Benutzer **aus,** klicken Sie auf den Anzeigenamen des Benutzers, und wählen Sie **Bearbeiten aus.**
2. Wählen **Sie Neben** **Audiokonferenzen** bearbeiten aus, und wählen Sie dann im Bereich  **Audiokonferenzen** in den Listen Gebührenpflichtige Nummer oder Gebührenfreie Telefonnummer eine Nummer aus, und wählen Sie dann **Übernehmen aus.** 

## <a name="related-topics"></a>Verwandte Themen

- [Audiokonferenzen](audio-conferencing-in-office-365.md)
- [Einrichten von Audiokonferenzen für Teams](set-up-audio-conferencing-in-teams.md)
- [Telefonnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing-in-teams.md)
- [Allgemeine Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md)
- [Abrufen von Servicenummern](getting-service-phone-numbers.md)
- [Teams-Add-On-Lizenzen](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Zuweisen von Lizenzen zu Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users)
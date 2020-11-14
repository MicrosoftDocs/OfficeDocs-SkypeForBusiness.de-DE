---
title: Einrichten von Audiokonferenzen für kleine und mittelständische Unternehmen
ms.author: v-lanac
author: lanachin
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
description: 'Hier erfahren Sie, wie Sie Audiokonferenzen in Ihrem kleinen oder mittleren Unternehmen für Personen einrichten, die ein Telefon zum Anrufen in Besprechungen verwenden müssen. '
ms.openlocfilehash: 4c0d47246f8a321a91ea175e06279bfe147a634a
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031181"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Einrichten von Audiokonferenzen für kleine und mittelständische Unternehmen

Bei Audiokonferenzen können sich die Teilnehmer über ein Telefon in Teams-Besprechungen einwählen, anstatt die Teams-App auf Ihrem mobilen Gerät oder auf dem Computer zu verwenden.  

Wenn Sie ein kleines oder mittelständisches Unternehmen mit bis zu 300-Benutzern sind und derzeit keine Audiokonferenz-Lizenzen vorhanden sind, können Sie Audio-Conferencing für ein Jahr kostenlos erhalten. Dieses ﻿kostenlose Angebot steht ab dem 1. Oktober 2020 zur Verfügung.

Die Lizenz für Audiokonferenz-Add-on kann auf Benutzer angewendet werden, die über die Lizenzen Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 oder Enterprise E3 verfügen. Weitere Informationen finden Sie unter [Teams-Add-on-Lizenzen](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) .

> [!NOTE]
> Wenn Sie über Enterprise E5 oder Microsoft 365 Business Voice verfügen, können Sie das ﻿kostenlose Audiokonferenz-Angebot nicht verwenden, da diese Lizenzen bereits Audiokonferenzen umfassen.

In diesem Artikel erfahren Sie, wie Sie Audio-Conferencing einrichten. Sie müssen Audiokonferenzen nur für Personen einrichten, die Besprechungen planen oder leiten möchten. Besprechungsteilnehmer, die sich in Besprechungen einwählen, benötigen keine Lizenzen oder ein anderes Setup. Weitere Informationen finden Sie unter [Audiokonferenzen](audio-conferencing-in-office-365.md).

## <a name="set-up-audio-conferencing"></a>Einrichten von Audiokonferenzen

Wenn Sie Audiokonferenzen einrichten, wird Ihrer Konferenzbrücke automatisch eine Telefonnummer zugewiesen, damit Sie in Besprechungseinladungen verwendet werden kann. Die Telefonnummer, die als Standardnummer ihrer Konferenzbrücke zugewiesen ist, ist eine aus dem Land oder der Region Ihrer Organisation. Diese Telefonnummer ist eine gebührenpflichtige Nummer, bei der Gebühren für Ferngespräche anfallen können.

> [!NOTE]
> Sie können auch eine gebührenfreie Nummer verwenden, die einige zusätzliche Schritte erfordert. Weitere Informationen zu Telefonnummern für Ihre Konferenzbrücke finden Sie unter [Audiokonferenz-Telefonnummern](#audio-conferencing-phone-numbers) weiter unten in diesem Artikel.

### <a name="step-1-get-audio-conferencing-licenses"></a>Schritt 1: Abrufen von Audiokonferenz-Lizenzen

Besorgen Sie sich eine Audiokonferenz-Lizenz für jede Person, die Besprechungen leiten wird. Verwenden Sie dazu das Microsoft 365 Admin Center.

1. Wechseln Sie im Microsoft 365 Admin Center zu **Abrechnungs**  >  **Kauf Dienste** , und wählen Sie dann am unteren Rand der Seite **Add-ons** aus.
2. Wählen Sie **Microsoft 365 Audio Conferencing Adoption Promo**  >  **Details** aus, und wählen Sie dann **Jetzt abrufen** aus.
3. Geben Sie die Anzahl der Lizenzen ein, die Sie für Ihre Besprechungsorganisatoren benötigen, und führen Sie dann Ihre Bestellung aus.

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Screenshot der Promo-Lizenz für Audio-Conferencing-Einführung":::

    > [!NOTE]
    > Deaktivieren oder aktivieren Sie das **Automatische zuweisen für alle Benutzer ohne Lizenzen** , je nachdem, ob Sie allen Benutzern, die nicht über diese Lizenz verfügen, automatisch eine Audiokonferenz-Lizenz zuweisen möchten.

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Schritt 2: Zuweisen einer Audiokonferenz-Lizenz zu Benutzern, die Besprechungen leiten

Weisen Sie jeder Person, die Besprechungen leiten soll, eine Lizenz zu. Verwenden Sie dazu das Microsoft 365 Admin Center.

#### <a name="assign-a-license-to-one-user"></a>Zuweisen einer Lizenz zu einem Benutzer

1. Wechseln Sie im Microsoft 365 Admin Center zu " **Benutzer**  >  **aktive Benutzer** ".  
2. Wählen Sie die Zeile des Benutzers aus, dem Sie die Lizenz zuweisen möchten, und wählen Sie dann im Bereich **Lizenzen und apps** aus.
3. Aktivieren Sie das Kontrollkästchen **Microsoft 365-Audiokonferenzen** , und wählen Sie dann **Änderungen speichern** aus.

#### <a name="assign-a-license-to-multiple-users"></a>Zuweisen einer Lizenz zu mehreren Benutzern

1. Wechseln Sie im Microsoft 365 Admin Center zu " **Benutzer**  >  **aktive Benutzer** ".  
2. Wählen Sie die Kreise neben den Benutzern aus, denen Sie die Lizenz zuweisen möchten, und wählen Sie dann **Produktlizenzen verwalten** aus.
3. Wählen Sie im Bereich **Produktlizenzen verwalten** die Option **Weitere zuweisen** aus.
4. Aktivieren Sie das Kontrollkästchen **Microsoft 365-Audiokonferenzen** , und wählen Sie dann **Änderungen speichern** aus.  

## <a name="schedule-teams-meetings-in-outlook"></a>Planen von Teams-Besprechungen in Outlook

Ihre Besprechungsorganisatoren können nun Besprechungen in Outlook planen. Wechseln Sie in Outlook zu **Kalender** , und wählen Sie dann die Schaltfläche **neue Teams-Besprechung** aus. Die Einwahlnummern der Besprechung und die Konferenz-ID werden der Besprechungseinladung, die an Besprechungsteilnehmer gesendet wird, automatisch hinzugefügt. Weitere Informationen finden Sie unter [Planen einer Teambesprechung in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).

> [!NOTE]
> Wenn Sie möchten, können Sie Besprechungseinladungen so anpassen, dass Sie Ihr Firmen Logo, Links zu Ihrer Support-Website und den rechtlichen Haftungsausschluss sowie eine nur-Text-Fußzeile hinzufügen. Weitere Informationen finden Sie unter [Anpassen von Besprechungseinladungen](meeting-settings-in-teams.md#customize-meeting-invitations).

## <a name="audio-conferencing-phone-numbers"></a>Audiokonferenz-Telefonnummern

Es gibt zwei Arten von Zahlen, die Sie für Ihre Konferenzbrücke verwenden können. Sie können entweder **freigegebene Nummern** (wie im Abschnitt [Einrichten von Audiokonferenzen](#set-up-audio-conferencing) weiter oben in diesem Artikel) oder **dedizierte Nummern** verwenden. Hier finden Sie weitere Informationen zu jeder.

### <a name="shared-numbers"></a>Freigegebene Nummern

Eine freigegebene Nummer ist eine Zahl, die für alle Organisationen freigegeben ist. Freigegebene Nummern sind gebührenpflichtige Nummern, die beim Einrichten von Audiokonferenzen automatisch zugewiesen werden.

Wenn Sie die Standardnummer sehen möchten, die ihrer Konferenzbrücke zugewiesen ist, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Besprechungen**  >  **Konferenz Brücken** , und suchen Sie dann die Nummer für den Standort, der Ihnen am nächsten ist.

### <a name="dedicated-numbers"></a>Dedizierte Nummern

Eine dedizierte Nummer ist eine Nummer, die nur für Ihre Benutzer verfügbar ist. Eine dedizierte Nummer kann eine gebührenpflichtige Nummer oder eine gebührenfreie Nummer sein. Wenn Sie eine dedizierte Nummer verwenden möchten, müssen Sie zuerst die Nummer abrufen, Sie Ihrer Konferenzbrücke zuweisen und dann die Nummer jeder Person zuweisen, die Besprechungen leiten soll.

Es gibt mehrere Möglichkeiten, eine dedizierte Nummer zu erhalten. Sie können eine Nummer von Microsoft erhalten oder eine vorhandene Nummer von Ihrem aktuellen Dienstanbieter an Microsoft übertragen (portieren). Weitere Informationen hierzu finden Sie unter [Abrufen von Servicenummern](getting-service-phone-numbers.md).

Beachten Sie, dass Sie bei Verwendung einer gebührenfreien Nummer zunächst jeder Person, die Besprechungen leiten wird, eine Lizenz für Kommunikations Kredite zuweisen müssen. Weitere Informationen finden Sie unter [Einrichten von Kommunikationsguthaben für Ihre Organisation](set-up-communications-credits-for-your-organization.md).

Nachdem Sie Ihre Nummer haben, weisen Sie Sie Ihrer Konferenzbrücke zu. Verwenden Sie dazu das Microsoft Teams Admin Center.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Besprechungen**  >  **Konferenz Brücken**.
2. Wählen Sie **Hinzufügen** aus, und wählen Sie dann **gebührenpflichtige Nummer** oder **gebührenfreie Nummer** aus.
3. Wählen Sie im Bereich **Telefonnummern hinzufügen** die Nummer aus, und wählen Sie dann über **nehmen** aus.

Weisen Sie der Person, die Besprechungen leiten soll, die Nummer zu. Verwenden Sie dazu das Microsoft Teams Admin Center.

1. Wählen Sie in der linken Navigationsleiste des Microsoft Teams Admin Center die Option **Benutzer** aus, klicken Sie auf den Anzeigenamen des Benutzers, und wählen Sie **Bearbeiten** aus.
2. Wählen Sie neben **Audiokonferenzen** **Bearbeiten** aus, und wählen Sie dann im Bereich **Audiokonferenz** eine Nummer in der **Liste gebührenpflichtige** Nummern oder **gebührenfreie** Nummern aus, und wählen Sie dann über **nehmen** aus.

## <a name="related-topics"></a>Verwandte Themen

- [Audiokonferenz](audio-conferencing-in-office-365.md)
- [Einrichten von Audiokonferenzen für Teams](set-up-audio-conferencing-in-teams.md)
- [Telefonnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing-in-teams.md)
- [Allgemeine Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md)
- [Abrufen von Servicenummern](getting-service-phone-numbers.md)
- [Teams-Add-on-Lizenzen](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

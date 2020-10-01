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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Hier erfahren Sie, wie Sie Audiokonferenzen in Ihrem kleinen oder mittleren Unternehmen für Personen einrichten, die ein Telefon zum Anrufen in Besprechungen verwenden müssen. '
ms.openlocfilehash: 648a6342adf0fc035dcd33c6eb11efb40b0d4eed
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328435"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Einrichten von Audiokonferenzen für kleine und mittelständische Unternehmen

Bei Audiokonferenzen können sich die Teilnehmer über ein Telefon in Teams-Besprechungen einwählen, anstatt die Teams-App auf Ihrem mobilen Gerät oder auf dem Computer zu verwenden.  

Wenn Sie ein kleines oder mittelständisches Unternehmen mit bis zu 300-Benutzern sind und derzeit keine Audiokonferenz-Lizenzen vorhanden sind, können Sie Audio-Conferencing für ein Jahr kostenlos erhalten. Dieses ﻿kostenlose Angebot steht ab dem 1. Oktober 2020 zur Verfügung.

Die Lizenz für Audiokonferenz-Add-on kann auf Benutzer angewendet werden, die über die Lizenzen Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 oder Enterprise E3 verfügen. Weitere Informationen finden Sie unter [Teams-Add-on-Lizenzen](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) .

> [!NOTE]
> Wenn Sie über Enterprise E5 oder Microsoft 365 Business Voice verfügen, können Sie das ﻿kostenlose Audiokonferenz-Angebot nicht verwenden, da diese Lizenzen bereits Audiokonferenzen umfassen.

In diesem Artikel erfahren Sie, wie Sie Audio-Conferencing einrichten. Sie müssen Audiokonferenzen nur für Personen einrichten, die Besprechungen planen oder leiten möchten. Besprechungsteilnehmer, die sich in Besprechungen einwählen, benötigen keine Lizenzen oder ein anderes Setup. Weitere Informationen finden Sie unter [Audiokonferenzen](audio-conferencing-in-office-365.md).

## <a name="step-1-get-audio-conferencing-licenses"></a>Schritt 1: Abrufen von Audiokonferenz-Lizenzen

Besorgen Sie sich eine Audiokonferenz-Lizenz für jede Person, die Besprechungen leiten wird. Verwenden Sie dazu das Microsoft 365 Admin Center.

1. Wechseln Sie im Microsoft 365 Admin Center zu **Abrechnungs**  >  **Kauf Dienste**, und wählen Sie dann am unteren Rand der Seite **Add-ons**aus. 
2. Wählen Sie die **Promo-Details zur Einführung von Microsoft 365 Audio Conferencing**aus  >  **Details**.
3. Geben Sie die Anzahl der Lizenzen ein, die Sie für Ihre Besprechungsorganisatoren benötigen, und führen Sie dann Ihre Bestellung aus.

> [!NOTE]
> Deaktivieren oder aktivieren Sie das **Automatische zuweisen für alle Benutzer ohne Lizenzen**, je nachdem, ob Sie allen Benutzern, die nicht über diese Lizenz verfügen, automatisch eine Audiokonferenz-Lizenz zuweisen möchten.

## <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Schritt 2: Zuweisen einer Audiokonferenz-Lizenz zu Benutzern, die Besprechungen leiten

Weisen Sie jeder Person, die Besprechungen leiten soll, eine Lizenz zu. Verwenden Sie dazu das Microsoft 365 Admin Center.

### <a name="assign-a-license-to-one-user"></a>Zuweisen einer Lizenz zu einem Benutzer

1. Wechseln Sie im Microsoft 365 Admin Center zu " **Benutzer**  >  **aktive Benutzer**".  
2. Wählen Sie die Zeile des Benutzers aus, dem Sie die Lizenz zuweisen möchten, und wählen Sie dann im Bereich **Lizenzen und apps**aus.
3. Aktivieren Sie das Kontrollkästchen **Microsoft 365-Audiokonferenzen** , und wählen Sie dann **Änderungen speichern**aus. 

### <a name="assign-a-license-to-multiple-users"></a>Zuweisen einer Lizenz zu mehreren Benutzern

1. Wechseln Sie im Microsoft 365 Admin Center zu " **Benutzer**  >  **aktive Benutzer**".  
2. Wählen Sie die Kreise neben den Benutzern aus, denen Sie die Lizenz zuweisen möchten, und wählen Sie dann **Produktlizenzen verwalten**aus.
3. Wählen Sie im Bereich **Produktlizenzen verwalten** die Option **Weitere zuweisen**aus.
4. Aktivieren Sie das Kontrollkästchen **Microsoft 365-Audiokonferenzen** , und wählen Sie dann **Änderungen speichern**aus.  

## <a name="step-3-find-or-get-a-phone-number-for-your-conferencing-bridge"></a>Schritt 3: Suchen oder Abrufen einer Telefonnummer für Ihre Konferenzbrücke

Sie benötigen eine Telefonnummer (auch als Servicenummer bezeichnet) für Ihre Konferenzbrücke, damit Sie in Besprechungseinladungen verwendet werden kann. Sie können wählen, ob Sie eine **freigegebene Nummer** oder eine **dedizierte Nummer**verwenden möchten. Beide Nummerntypen können von jedem Anrufer verwendet werden, um an einer Besprechung teilzunehmen.

### <a name="use-a-shared-number"></a>Verwenden einer freigegebenen Nummer

Eine freigegebene Nummer ist eine Zahl, die für alle Organisationen freigegeben ist. Freigegebene Nummern werden automatisch zugewiesen, wenn Sie Audiokonferenzen einrichten. Diese freigegebenen Nummern sind gebührenpflichtige Nummern, bei denen Gebühren für Ferngespräche anfallen können.

Wenn Sie die Standardnummer finden möchten, die ihrer Konferenzbrücke zugewiesen ist, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Besprechungen**  >  **Konferenz Brücken**, und suchen Sie dann die Nummer für den Standort, der Ihnen am nächsten ist.

### <a name="get-a-dedicated-number"></a>Besorgen Sie sich eine dedizierte Nummer

Eine dedizierte Nummer ist eine Nummer, die nur für Ihre Benutzer verfügbar ist. Eine dedizierte Nummer kann eine gebührenpflichtige Nummer oder eine gebührenfreie Nummer sein. Wenn Sie eine dedizierte Nummer verwenden möchten, müssen Sie zuerst die Nummer abrufen und diese dann ihrer Konferenzbrücke zuweisen.  

Es gibt mehrere Möglichkeiten, eine dedizierte Nummer zu erhalten. Sie können eine Nummer von Microsoft erhalten oder eine vorhandene Nummer von Ihrem aktuellen Dienstanbieter an Microsoft übertragen (portieren). Weitere Informationen hierzu finden Sie unter [Abrufen von Servicenummern](getting-service-phone-numbers.md).

> [!NOTE]
> Wenn Sie eine gebührenfreie Nummer verwenden, müssen Sie zunächst jeder Person, die Besprechungen leiten soll, eine Lizenz für Kommunikations Kredite zuweisen. Weitere Informationen finden Sie unter [Einrichten von Kommunikationsguthaben für Ihre Organisation](set-up-communications-credits-for-your-organization.md).

Nachdem Sie Ihre Nummer haben, weisen Sie Sie Ihrer Konferenzbrücke zu. Verwenden Sie dazu das Microsoft Teams Admin Center.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Besprechungen**  >  **Konferenz Brücken**.
2. Wählen Sie **Hinzufügen**aus, und wählen Sie dann **gebührenpflichtige Nummer** oder **gebührenfreie Nummer**aus.
3. Wählen Sie im Bereich **Telefonnummern hinzufügen** die Nummer aus, und wählen Sie dann über **nehmen**aus.

## <a name="step-4-assign-a-dial-in-number-to-users-who-lead-meetings"></a>Schritt 4: Zuweisen einer Einwahlnummer zu Benutzern, die Besprechungen leiten

Weisen Sie für jede Person, die Besprechungen leiten soll, eine Einwahlnummer zu. Verwenden Sie dazu das Microsoft Teams Admin Center.

1. Wählen Sie in der linken Navigationsleiste des Microsoft Teams Admin Center die Option **Benutzer**aus, klicken Sie auf den Anzeigenamen des Benutzers, und wählen Sie **Bearbeiten**aus.
2. Wählen **Edit**Sie   neben **Audiokonferenzen**bearbeiten aus, und wählen Sie dann im Bereich **Audiokonferenz**   eine Nummer in der Liste **gebührenpflichtige**Nummern   oder **gebührenfreie**   Nummern aus, und wählen Sie dann über **nehmen**aus.

## <a name="step-5-schedule-a-teams-meeting-in-outlook"></a>Schritt 5: Planen einer Teambesprechung in Outlook

Wenn Sie eine Besprechung planen möchten, wechseln Sie in Outlook zu **Kalender**, und wählen Sie dann die Schaltfläche **neue Teams-Besprechung** aus. Die für den Benutzer festgelegten Einwahlnummern und die Konferenz-ID werden der Besprechungseinladung, die an Besprechungsteilnehmer gesendet wird, automatisch hinzugefügt.

Weitere Informationen finden Sie unter [Planen einer Teambesprechung in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).

> [!NOTE]
> Wenn Sie möchten, können Sie Besprechungseinladungen so anpassen, dass Sie Ihr Firmen Logo, Links zu Ihrer Support-Website und den rechtlichen Haftungsausschluss sowie eine nur-Text-Fußzeile hinzufügen. Siehe [Anpassen von Besprechungseinladungen](meeting-settings-in-teams.md#customize-meeting-invitations).

## <a name="related-topics"></a>Verwandte Themen

- [Audiokonferenz](audio-conferencing-in-office-365.md)
- [Einrichten von Audiokonferenzen für Teams](set-up-audio-conferencing-in-teams.md)
- [Allgemeine Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md)
- [Abrufen von Servicenummern](getting-service-phone-numbers.md)
- [Teams-Add-on-Lizenzen](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

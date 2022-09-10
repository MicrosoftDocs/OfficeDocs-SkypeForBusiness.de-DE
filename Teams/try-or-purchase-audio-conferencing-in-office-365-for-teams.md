---
title: Testen oder Kaufen von Audiokonferenzen in Microsoft 365 für Teams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d080bb8c-3465-47bb-ad2b-9428f1a3fd24
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.lync.lac.CpcGettingStarted
- seo-marvel-mar2020
description: Erfahren Sie, wie Sie Lizenzen für Audiokonferenzen (PSTN-Konferenzen) für Microsoft 365 oder Office 365 erwerben, um Telefonkonferenzen einzurichten, in die sich Benutzer einwählen können.
ms.openlocfilehash: 5d93f9d81e2b70520d8c8044293f81aff2a36940
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641916"
---
# <a name="try-or-purchase-audio-conferencing-in-microsoft-365-for-microsoft-teams"></a>Testen oder Kaufen von Audiokonferenzen in Microsoft 365 für Microsoft Teams

In einigen Fällen müssen Mitarbeiter in Ihrer Organisation sich über ein Telefon in eine Besprechung einwählen. Microsoft Teams enthält die Audiokonferenzfunktion für genau diese Situation! Personen können sich mit einem Telefon in Microsoft Teams-Besprechungen einwähnen, anstatt die Microsoft Teams-App auf einem mobilen Gerät oder PC zu verwenden.

Sie müssen audiokonferenzen nur für Personen einrichten, die Besprechungen planen oder leiten möchten. Meeting-Teilnehmer, die sich in das Meeting einwählen, benötigen keinerlei zugewiesene Lizenzen und auch ein anderes Setup ist nicht erforderlich.

Infos über die Preisgestaltung finden Sie unter [Preise für Audiokonferenz](https://www.microsoft.com/microsoft-teams/audio-conferencing?rtc=3).

## <a name="step-1-buy-and-assign-audio-conferencing-licenses"></a>Schritt 1: Kaufen und Zuweisen von Audiokonferenzlizenzen

Sie müssen ein [globaler Administrator oder Abrechnungsadministrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) sein, um diese Schritte ausführen zu können.

### <a name="to-buy-and-assign-user-audio-conferencing-licenses"></a>So kaufen und weisen Sie Benutzerlizenzen für Audiokonferenzen zu

1. Finden Sie heraus, ob **Audiokonferenzen** in Ihrem Land/Ihrer Region verfügbar sind. [Verfügbarkeit von Ländern und Regionen für Audiokonferenzen und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

2. Holen Sie sich Ihre Lizenzen für **Audiokonferenz**. Wenn Sie:

   - **Probieren Sie es aus**, bevor Sie es kaufen: Sie können sich für eine kostenlose Testversion von Office 365 Enterprise E5 registrieren, die Audiokonferenzen enthält. Siehe [Testversion von Office 365 Enterprise E5](https://portal.office.com/Signup?OfferId=101bde18-5ffb-4d79-a47b-f5b2c62525b3).

   - **Kaufen Sie es**: Siehe [Microsoft Teams-Add-On-Lizenzierung](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

3. [Weisen Sie Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users) in Ihrer Organisation Lizenzen zu, die Besprechungen planen oder leiten werden.

4. Wenn Sie Add-On Lizenzen und Gesprächseinheiten für Audiokonferenz erworben haben, weisen Sie diese ebenfalls zu. Anweisungen finden Sie unter [Zuweisen von Microsoft Teams-Add-On-Lizenzen](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="to-buy-and-assign-pay-per-minute-audio-conferencing-licenses"></a>So kaufen und weisen Sie Lizenzen für Audiokonferenzen per Minutenentgelt zu

Wenn Sie ein Volumen- und Lizenzierungskunde sind, können Sie Pay-per-Minute Lizenzen für Audiokonferenz erhalten. Weitere Informationen zu Pay-per Minute Lizenzen für Audio Conferencing finden Sie unter [Pay-per-Minute Audio Conferencing](audio-conferencing-pay-per-minute.md).
  
1. Finden Sie heraus, ob **Audiokonferenzen** in Ihrem Land/Ihrer Region verfügbar sind. [Verfügbarkeit von Ländern und Regionen für Audiokonferenzen und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

2. Holen Sie sich Ihre Lizenzen für **Audiokonferenz**. Um Pay-per-Minute Lizenzen zu erwerben, wenden Sie sich bitte an Ihren Kundenbetreuer.

3. [Richten Sie Guthaben für Kommunikationen für Ihre Organisation](set-up-communications-credits-for-your-organization.md) für Ihre Organisation ein. Das Einrichten von Communication Credits, finden Sie unter [Was sind Communication Credits?](what-are-communications-credits.md)

    > [!IMPORTANT]
    > Wenn Guthaben für Kommunikationen noch nicht eingerichtet wurden, wird die Audiokonferenz für Benutzer mit Lizenzen mit Minutenabrechnung nicht funktionieren.

4. [Weisen Sie Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users) in Ihrer Organisation Lizenzen zu, die Besprechungen planen oder leiten werden.

    > [!NOTE]
    > Wenn Sie über Lizenzen für Audiokonferenzen pro Minute verfügen, müssen Sie jedem Benutzer auch separat eine Lizenz für Guthaben für Kommunikationen zuweisen.

## <a name="step-2-set-the-audio-conferencing-provider-for-people-who-lead-or-schedule-meetings"></a>Schritt 2: Festlegen des Providers von Audiokonferenz für Personen, die Meetings führen oder planen

Wenn Sie Personen in Ihrer Organisation, die teams nicht in einen Drittanbieter für Audiokonferenzen integriert haben, eine **Audiokonferenzlizenz** zuweisen, sind alle eingerichtet und einsatzbereit! (Sie müssen deren Provider von Audiokonferenz nicht festlegen.)

Wenn Sie Benutzer mit einem Drittanbieter für Audiokonferenzen aktiviert haben, müssen Sie den Anbieter dieser Benutzer in Microsoft ändern. Informationen zum Ändern des Anbieters für einen Benutzer finden [Sie unter Zuweisen von Teams-Add-On-Lizenzen zu Benutzern](teams-add-on-licensing/assign-teams-add-on-licenses.md).

## <a name="step-3-other-admin-tasks"></a>Schritt 3: Andere Administratoraufgaben

Die folgenden Schritte sind **optional**, aber viele Administratoren führen diese gerne aus:

1. [Anpassen von Besprechungseinladungen](meeting-settings-in-teams.md#customize-meeting-invitations). Die für den Nutzer festgelegten Einwahlnummern werden automatisch den Besprechungseinladungen hinzugefügt, die Teilnehmern zugesendet werden. Sie können jedoch Ihre eigenen Links für Hilfe und rechtliche Informationen, eine Textnachricht und eine kleine Firmengrafik hinzufügen.

2. [Legen Sie die Telefonnummern fest, die in Einladungen enthalten sind](set-the-phone-numbers-included-on-invites-in-teams.md). Dies ist die Telefonnummer, die in der von einem Benutzer geplanten Besprechung angezeigt wird.

3. [Festlegen der automatischen Sprache der Telefonzentrale für Audiokonferenz](set-auto-attendant-languages-for-audio-conferencing-in-teams.md), die von der automatischen Telefonzentrale von Audiokonferenz verwendet wird, um einen Anrufer zu begrüßen, wenn er sich mit einer Telefonnummer für die Audiokonferenz einwählt. Dieser Schritt gilt nur, wenn Sie Microsoft als Ihren Provider von Audio Conferencing verwenden.

4. [Legen Sie die Länge der PIN für Audiokonferenzbesprechungen](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md) fest.

> [!NOTE]
> This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

## <a name="related-topics"></a>Verwandte Themen

[Aktivieren von Teams in Ihrer Organisation](office-365-set-up.md)

[Telefonnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing-in-teams.md)

[Festlegen von Optionen für Onlinebesprechungen und Telefonkonferenzen](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

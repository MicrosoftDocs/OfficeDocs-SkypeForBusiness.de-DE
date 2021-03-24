---
title: 'Programm zum Ende des Lebenszyklus für die Integration von Skype for Business mit Audiokonferenzanbietern von Drittanbietern '
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: None
f1.keywords:
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: Am 31. Juli 2021 endet das Programm zum Ende des Lebenszyklus für die Integration von Skype for Business mit Audiokonferenzanbietern von Drittanbietern (ACP von Drittanbietern).
ms.openlocfilehash: 5e48c7deb114136e0b12c2636cf562213890656d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100771"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a>Programm zum Ende des Lebenszyklus für die Integration von Skype for Business mit Audiokonferenzanbietern von Drittanbietern 

Microsoft hat den Start des Lebenszyklusprogramms für die Integration von Skype for Business mit Audiokonferenzanbietern von Drittanbietern (ACPs) angekündigt. 

Das Programm zum Ende des Lebenszyklus endet am 31. Juli 2021. Nach Abschluss des Programms funktioniert die Integration von Skype for Business mit Audiokonferenzanbietern von Drittanbietern nicht mehr, und die folgenden Änderungen werden an diesem Datum (31. Juli 2021) beobachtet:

- Teilnehmer, die versuchen, über Einwahlnummern, die von einem Drittanbieter-ACP-Dienst bereitgestellt werden, an einer Skype for Business-Besprechung teilnehmen, sind nicht mehr mit der Skype for Business-Besprechung verbunden.
 
- Benutzer, die für einen DRITTANBIETER-ACP-Dienst aktiviert sind, haben ihre Einwahlinformationen nicht mehr automatisch in neue Skype for Business-Besprechungs einladen.

Im Rahmen der Ankündigung des Startprogramms zum Ende des Lebenszyklus wurde die folgende Änderung wirksam und bleibt bis zum Abschluss des Programms zum Ende des Lebenszyklus erhalten: 

- Kunden ohne Skype for Business-Benutzer, die für die Verwendung eines DRITTANBIETER-ACP-Diensts konfiguriert sind, können keine Benutzer für die Verwendung eines DRITTANBIETER-ACP-Diensts konfigurieren.

- Vorhandene Kunden mit Skype for Business-Benutzern, die für die Verwendung eines Drittanbieter-ACP-Diensts konfiguriert sind, können für die Dauer des Lebenszyklusendes weiterhin neue Benutzer hinzufügen. Bitte beachten Sie, dass wir nicht empfehlen, zusätzliche Skype for Business-Benutzer für die Nutzung eines Drittanbieter-ACP-Diensts zu einrichten, da die Änderungen, die am 31. Juli 2021 in Kraft treten, auch für sie gelten.

## <a name="preparing-for-this-change"></a>Vorbereiten dieser Änderung

Um sich auf diese Änderung vorzubereiten, empfehlen wir betroffenen Organisationen, ihre aktivierten Benutzer vor dem 31. Juli 2021 über dieses geplante Update zu informieren. 

Nach dem 31. Juli 2021 können Benutzer Skype for Business weiterhin ohne Unterbrechung ihrer Onlinebesprechungen nutzen. Organisationen müssen ihre Benutzer jedoch für Von Microsoft bereitgestellte Audiokonferenzen aktivieren, wenn sie Einwahlaudiokonferenzen mit Skype for Business oder Microsoft Teams benötigen. Weitere Informationen zu Microsoft Audio Conferencing finden Sie unter [Audiokonferenzen.](https://products.office.com/skype-for-business/audio-conferencing) 

Je nach gewünschtem Endzustand einer Organisation können drei Pfade befolgt werden:

- Migrieren Sie zu Microsoft Audio Conferencing. 
- Verwenden Sie weiterhin separat einen Drittanbieter für Audiokonferenzen. 
- Beenden Sie die Verwendung von Einwahlkonferenzen vollständig.

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a>Pfad #1: Migrieren zu Microsoft Audio Conferencing   

Organisationen, die sich entscheiden, zu Microsoft Audio Conferencing zu migrieren und ihre Migration vor dem 31. Juli 2021 abgeschlossen zu haben, haben während oder nach diesem Datum keine Auswirkungen auf den Dienst. Die Migration zu Microsoft Audio Conferencing führt zu den folgenden Änderungen an einer Organisation: 

- Der Dienst wird mit allen anderen Microsoft 365- oder Office 365-Diensten in Rechnung stellen. 

- Wenn das Standardabonnement erworben wird, sind die gebührenpflichtigen Einwahlkosten in den monatlichen Abonnementkosten pro Benutzer enthalten. 

- Jede Organisation und ihre Benutzer erhalten eine neue Gruppe von Einwahltelefonnummern. Informationen zur geografischen Abdeckung des Microsoft Audio Conferencing-Diensts finden Sie unter Verfügbarkeit von Ländern und Regionen für [Audiokonferenzen und Anrufpläne.](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
 
- Besprechungen, die bereits von Benutzern geplant wurden, die mit einem DRITTANBIETER-ACP aktiviert wurden, werden automatisch neu geplant, um Einwahlinformationen für Microsoft Audio conferencing zu enthalten.
 
- Die Konferenz-IDs jeder Besprechung sind dynamisch, was bedeutet, dass jede Besprechung über eine eigene dedizierte Konferenz-ID verfügen wird. Dynamische Konferenz-IDs bieten verbesserte Sicherheit und eine verbesserte Benutzererfahrung für Back-to-Back-Besprechungen.

- Die nutzung des Diensts unterliegt den Nutzungsbedingungen für Audiokonferenzdienste. 

Die Migration zu Microsoft Audio Conferencing ist einfach und kann nach dem Erwerb der Lizenzen für den Dienst in nur wenigen Schritten durchgeführt werden. Informationen zum Migrieren zu Microsoft Audio Conferencing finden Sie unter:

- [Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
**Zusammenfassung:**

- Organisationen, die zu Microsoft Audio Conferencing migrieren und ihre Migration vor dem 31. Juli 2021 abschließen, sehen während oder nach diesem Datum keine Auswirkungen auf ihren Dienst.

- Weitere Informationen zum Migrieren zu Microsoft Audio Conferencing finden Sie unter Testen oder Erwerben von [Audiokonferenzen in Microsoft 365 oder Office 365.](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a>Pfad #2: Weiterhin separat einen Drittanbieter für Audiokonferenzen verwenden

Organisationen, die sich entscheiden, am und nach dem 31. Juli 2021 weiterhin einen Drittanbieter-ACP zu verwenden, haben Auswirkungen auf den Dienst, da die Einwahlinformationen eines Drittanbieters nicht mehr für die Teilnahme am Audioteil einer Skype for Business-Besprechung verwendet werden können. 

Um die Fragmentierung von Audio in Skype for Business-Besprechungen zu verhindern, indem einige Teilnehmer über VoIP und andere über den Drittanbieter-ACP teilnehmen, wird es für diese Organisationen empfohlen, die Verwendung von VoIP in den Besprechungen ihrer Benutzer zu deaktivieren. Auf diese Weise müssen alle Teilnehmer über den DRITTANBIETER-ACP am Audioteil einer Besprechung teilnehmen, und alle anderen Arbeitslasten der Besprechung (z. B. Chat oder Bildschirmfreigabe) können über Skype for Business weiterhin unterstützt werden. 

- Wenn Sie VoIP von allen Besprechungen eines bestimmten Organisators deaktivieren möchten, legen Sie den Parameter AllowIPAudio der Konferenzrichtlinie über das cmdlet Set-CsConferencingPolicy false ein. Weitere Informationen finden Sie unter [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
 
Im Hinblick auf die Planung und ab dem 31. Juli 2021 werden die Einwahlinformationen eines Drittanbieter-ACP nicht mehr automatisch in Skype for Business-Besprechungs-Einladungen einbezogen. Benutzer müssen die Einwahlinformationen in ihren Skype for Business-Besprechungsbesprechungen manuell hinzufügen, wenn sie diese Informationen weiterhin als Teil ihrer Besprechungen hinzufügen möchten. 

Bitte beachten Sie, dass die vorhandenen Benutzerbesprechungen am 31. Juli 2021 nicht automatisch neu geplant werden, um Einwahlinformationen von Drittanbietern zu entfernen. Organisationen, die beschließen, VoIP für die Besprechungen ihrer Benutzer aktiviert zu lassen, sollten erwägen, die Integration von DRITTANBIETER-ACP für ihre Benutzer zu deaktivieren und ihre Besprechungen mithilfe des Besprechungsmigrationsdiensts neu zu terminieren, um die Einwahlinformationen für Audiokonferenzen von Drittanbietern aus ihren vorhandenen Besprechungen zu entfernen und die Fragmentierung von Audio in bereits geplanten Besprechungen zu verhindern. 

- Wenn Sie die Integration von Audiokonferenzen von Drittanbietern für einen bestimmten Organisator deaktivieren möchten, verwenden Sie das Remove-CsUserAcp Cmdlet. Weitere Informationen finden Sie unter [Remove-CsUserAcp](/powershell/module/skype/remove-csuseracp?view=skype-ps). 

- Informationen zum automatischen Neuplanen der Besprechungen von Benutzern nach dem Deaktivieren der Integration mit einem Drittanbieter für Audiokonferenzen finden Sie unter "Wie kann ich die Besprechungsmigration manuell für einen Benutzer ausführen?" unter [Einrichten des Besprechungsmigrationsdiensts (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)aus. 

**Zusammenfassung:**

- Organisationen, die sich entscheiden, am und nach dem 31. Juli 2021 weiterhin einen Drittanbieter-ACP zu verwenden, sind davon betroffen, da ein DRITTANBIETER-ACP nicht für die Teilnahme an einer Skype for Business-Besprechung verwendet werden kann und neue Besprechungen keine Einwahlinformationen von Drittanbietern enthalten. 

- Es wird empfohlen, VoIP für alle Besprechungen aller betroffenen Benutzer vor dem 31. Juli 2021 zu deaktivieren, um zu verhindern, dass die Audiofragmentierung über teilnehmerübergreifend über VoIP und über einen Drittanbieter-ACP erfolgt. 

    - Wenn Sie VoIP von allen Besprechungen eines bestimmten Organisators deaktivieren möchten, legen Sie den Parameter AllowIPAudio der Konferenzrichtlinie des Benutzers über das cmdlet Set-CsConferencingPolicy false. Weitere Informationen finden Sie unter [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
 
- Wenn eine Organisation VoIP nicht für alle Besprechungen deaktiviert, empfiehlt es sich, dass Benutzer die Skype for Business Online-Integration in einen DRITTANBIETER-ACP deaktivieren und ihre Besprechungen neu terminieren, um die Drittanbieter-ACP-Einwahlinformationen zu entfernen, um die Fragmentierung von Audio zu verhindern.

    - Um die Integration von Audiokonferenzen von Drittanbietern für einen bestimmten Organisator zu deaktivieren, verwenden Sie das [Cmdlet Remove-CsUserAcp.](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

    - Informationen zum automatischen Neuplanen der Besprechungen finden Sie unter "Wie kann ich die Besprechungsmigration manuell für einen Benutzer ausführen?" unter [Einrichten des Besprechungsmigrationsdiensts (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)aus.

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a>Pfad #3: Beenden der vollständigen Verwendung von Einwahlkonferenzen

Organisationen, die sich entschließen, Einwahlkonferenzen nicht mehr vollständig zu verwenden (weder von Microsoft noch von einem Drittanbieter-ACP bereitgestellt), können sich vollständig auf VoIP verlassen, um den Audioteil einer Skype for Business-Besprechung zu unterstützen. 

Diese Organisationen müssten ihre Benutzer von der Verwendung eines Drittanbieters für Audiokonferenzen deaktivieren und ihre Besprechungen mithilfe des Besprechungsmigrationsdiensts automatisch neu terminieren lassen, um ihre Einwahlkonferenzinformationen zu entfernen. 

- Wenn Sie die Integration von Audiokonferenzen von Drittanbietern für einen bestimmten Organisator deaktivieren möchten, verwenden Sie das Remove-CsUserAcp Cmdlet. Weitere Informationen finden Sie unter [Remove-CsUserAcp](/powershell/module/skype/remove-csuseracp?view=skype-ps). 

- Informationen zum automatischen Neuplanen der Besprechungen von Benutzern nach dem Deaktivieren der Integration mit einem Drittanbieter für Audiokonferenzen finden Sie unter "Wie kann ich die Besprechungsmigration manuell für einen Benutzer ausführen?" unter [Einrichten des Besprechungsmigrationsdiensts (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)aus. 

**Zusammenfassung:** 

- Organisationen, die sich entscheiden, audio conferencing vor dem 31. Juli 2021 vollständig zu beenden, sind davon nicht betroffen.

- Wenn Sie die Integration von Audiokonferenzen von Drittanbietern für einen bestimmten Organisator deaktivieren möchten, verwenden Sie das Remove-CsUserAcp Cmdlet. Weitere Informationen finden Sie unter [Remove-CsUserAcp](/powershell/module/skype/remove-csuseracp?view=skype-ps). 

- Informationen zum automatischen Neuplanen der Besprechungen von Benutzern nach dem Deaktivieren der Integration mit Audiokonferenzanbietern von Drittanbietern finden Sie unter "Wie kann ich die Besprechungsmigration manuell für einen Benutzer ausführen?" unter [Einrichten des Besprechungsmigrationsdiensts (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)aus.
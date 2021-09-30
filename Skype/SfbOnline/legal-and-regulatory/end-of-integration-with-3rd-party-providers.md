---
title: 'Programm zum Ende des Lebenszyklus für die Integration Skype for Business Drittanbieter für Audiokonferenzen '
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
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: Am 31. Juli 2021 endet das Programm zum Ende des Lebenszyklus für die Integration von Skype for Business mit Drittanbieter-Audiokonferenzanbietern (3d ACP).
ms.openlocfilehash: c159d201a284b683237df22688878ef268c442b1
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014379"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a>Programm zum Ende des Lebenszyklus für die Integration Skype for Business Drittanbieter für Audiokonferenzen 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Microsoft hat den Beginn des Lebenszyklus des Programms für die Integration von Skype for Business drittanbieter Audiokonferenzanbietern (ACPs) angekündigt. 

Das Programm zum Ende des Lebenszyklus endet am 31. Juli 2021. Nach dem Ende des Programms funktioniert die Integration von Skype for Business mit Drittanbieter-Audiokonferenzanbietern nicht mehr, und an diesem Datum (31. Juli 2021) werden die folgenden Änderungen beobachtet:

- Teilnehmer, die über Skype for Business von einem Drittanbieter-ACP-Dienst bereitgestellte Einwahlnummern an einer Skype for Business-Besprechung teilnehmen, werden nicht mehr mit der Besprechung Skype for Business verbunden.
 
- Benutzer, die für einen Drittanbieter-ACP-Dienst aktiviert sind, enthalten ihre Einwahlinformationen nicht mehr automatisch in allen neuen Skype for Business Besprechungsteilnehmern.

Im Rahmen der Ankündigung des Startprogramms für das Ende des Lebenszyklus ist die folgende Änderung wirksam und wird bis zum Ende des Lebenszyklusprogramms weiterhin wirksam: 

- Kunden ohne Skype for Business, die für die Verwendung eines Drittanbieter-ACP-Diensts konfiguriert sind, können keine Benutzer für die Verwendung eines Drittanbieter-ACP-Diensts konfigurieren.

- Bestehende Kunden mit Skype for Business-Benutzern, die für die Verwendung eines Drittanbieter-ACP-Diensts konfiguriert sind, können während des Lebenszyklusendes weiterhin neue Benutzer hinzufügen. Beachten Sie bitte, dass wir nicht empfehlen, zusätzliche Skype for Business-Benutzer für die Verwendung eines Drittanbieter-ACP-Diensts zu einrichten, da die Änderungen, die am 31. Juli 2021 in Kraft treten, auch für diese gelten.

## <a name="preparing-for-this-change"></a>Vorbereiten auf diese Änderung

Zur Vorbereitung auf diese Änderung empfehlen wir betroffenen Organisationen, ihre aktivierten Benutzer vor dem 31. Juli 2021 über dieses geplante Update zu informieren. 

Nach dem 31. Juli 2021 können Benutzer Skype for Business ohne Unterbrechung ihrer Onlinebesprechungen verwenden. Organisationen müssen ihren Benutzern jedoch die Verwendung von Audiokonferenzen ermöglichen, die von Microsoft bereitgestellt werden, wenn sie Einwahlaudiokonferenzen mit einem Skype for Business oder Microsoft Teams. Weitere Informationen zu Microsoft-Audiokonferenzen finden Sie unter [Audiokonferenzen.](https://www.microsoft.com/microsoft-teams/audio-conferencing) 

Je nach gewünschtem Endzustand einer Organisation gibt es drei Pfade, auf die sie folgen können:

- Migrieren Sie zu Microsoft Audio Conferencing (Microsoft-Audiokonferenz). 
- Verwenden Sie weiterhin separat einen Drittanbieter für Audiokonferenzen. 
- Beenden Sie die vollständigen Verwendung von Einwahlkonferenzen.

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a>Pfad #1: Migrieren zu Microsoft Audio Conferencing   

Organisationen, die sich für die Migration zu Microsoft Audio Conferencing und den Abschluss der Migration vor dem 31. Juli 2021 entscheiden, haben während oder nach diesem Datum keine Auswirkungen auf den Dienst. Durch die Migration zu Microsoft-Audiokonferenzen werden für eine Organisation die folgenden Änderungen vorgenommen: 

- Der Dienst wird zusammen mit allen anderen Diensten Microsoft 365 oder Office 365 abgerechnet. 

- Wenn das Standardabonnement erworben wird, sind die Gebühren für ein einwahlpflichtige Verbindungen in den monatlichen Abonnementkosten pro Benutzer enthalten. 

- Eine neue Gruppe von Einwahltelefonnummern wird für jede Organisation und ihre Benutzer bereitgestellt. Informationen zur geografischen Abdeckung des Microsoft-Audiokonferenzdiensts finden Sie unter Verfügbarkeit von Ländern und Regionen für [Audiokonferenzen und Anrufpläne.](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
 
- Besprechungen, die bereits von Benutzern geplant wurden, die mit einem Drittanbieter-ACP aktiviert wurden, werden automatisch neu geplant, um Einwahlinformationen für Microsoft-Audiokonferenzen zu erhalten.
 
- Die Konferenz-IDs der einzelnen Besprechungen sind dynamisch, d. h., jede Besprechung hat eine eigene dedizierte Konferenz-ID. Dynamische Konferenz-IDs bieten verbesserte Sicherheit und eine verbesserte Benutzererfahrung für Back-to-Back-Besprechungen.

- Die Nutzung des Diensts unterliegt den Nutzungsbedingungen für Audiokonferenzdienste. 

Die Migration zu Microsoft Audio conferencing ist einfach und kann nach dem Abrufen der Lizenzen für den Dienst in nur wenigen Schritten durchgeführt werden. Informationen zum Migrieren zu Microsoft Audio Conferencing finden Sie unter:

- [Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
**Zusammenfassung:**

- Organisationen, die vor dem 31. Juli 2021 zu Microsoft Audio Conferencing migrieren und die Migration abschließen, haben während oder nach diesem Datum keine Auswirkungen auf ihren Dienst.

- Weitere Informationen zum Migrieren zu Microsoft Audio Conferencing finden Sie unter Testen oder Erwerben von [Audiokonferenzen in Microsoft 365 oder Office 365.](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a>Pfad #2: Verwenden Sie weiterhin separat einen Drittanbieter für Audiokonferenzen.

Bei Organisationen, die sich dafür entscheiden, einen Drittanbieter-ACP weiterhin am und nach dem 31. Juli 2021 zu verwenden, hat dies Auswirkungen auf den Dienst, da die Acp-Einwahlinformationen des Drittanbieters nicht mehr für die Teilnahme am Audioteil einer Skype for Business-Besprechung verwendet werden können. 

Um die Fragmentierung von Audio in Skype for Business-Besprechungen zu verhindern, indem einige Teilnehmer über VoIP und andere über den Drittanbieter-ACP teilnehmen, wird empfohlen, dass diese Organisationen die Verwendung von VoIP in den Besprechungen ihrer Benutzer deaktivieren. Auf diese Weise müssen alle Teilnehmer über den Drittanbieter-ACP am Audioteil einer Besprechung teilnehmen, und alle anderen Arbeitsauslastungen der Besprechung (z. B. Chat oder Bildschirmfreigabe) können weiterhin über die Skype for Business. 

- Wenn Sie VoIP in allen Besprechungen eines bestimmten Organisators deaktivieren möchten, legen Sie über das cmdlet "Set-CsConferencingPolicy" den Parameter AllowIPAudio seiner Konferenzrichtlinie auf "false" (falsch) festgelegt. Weitere Informationen finden Sie unter [Set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
 
Im Hinblick auf die Planung und ab dem 31. Juli 2021 werden die Einwahlinformationen eines Drittanbieter-ACP nicht mehr automatisch in Skype for Business Besprechungs einladen. Benutzer müssen die Einwahlinformationen manuell zu ihren Einladungen Skype for Business-Besprechung hinzufügen, wenn sie diese Informationen weiterhin als Teil ihrer Besprechungen hinzufügen möchten. 

Bitte beachten Sie, dass am 31. Juli 2021 die vorhandenen Benutzerbesprechungen nicht automatisch neu geplant werden, um Einwahlinformationen von Drittanbietern für ACP zu entfernen. Organisationen, die VoIP für die Besprechungen ihrer Benutzer aktiviert lassen möchten, sollten die Integration von Drittanbieter-ACP für ihre Benutzer deaktivieren und ihre Besprechungen mithilfe des Besprechungsmigrationsdiensts neu anplanen, um die Einwahlinformationen von Drittanbietern für Audiokonferenzen aus ihren vorhandenen Besprechungen zu entfernen und audiomäßige Fragmentierungen bei bereits geplanten Besprechungen zu verhindern. 

- Um die Integration von Drittanbieter-Audiokonferenzen für einen bestimmten Organisator zu deaktivieren, verwenden Sie das Remove-CsUserAcp-Cmdlet. Weitere Informationen finden Sie unter [Remove-CsUserAcp.](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

- Informationen zum automatischen Neuplanen der Besprechungen von Benutzern nach dem Deaktivieren der Integration mit einem Drittanbieter für Audiokonferenzen finden Sie unter "Wie kann ich die Besprechungsmigration manuell für einen Benutzer ausführen?" unter [Einrichten des Meeting Migration Service (MMS).](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md) 

**Zusammenfassung:**

- Organisationen, die beschließen, einen Drittanbieter-ACP weiterhin am und nach dem 31. Juli 2021 zu verwenden, sind betroffen, da ein Drittanbieter-ACP nicht für die Teilnahme an einer Skype for Business-Besprechung verwendet werden kann und neue Besprechungen keine Acp-Einwahlinformationen von Drittanbietern enthalten. 

- Es wird empfohlen, VoIP für alle Besprechungen aller betroffenen Benutzer vor dem 31. Juli 2021 zu deaktivieren, um zu verhindern, dass die Audiowiedergabe über Teilnehmer, die über VoIP und über einen Drittanbieter-ACP teilnehmen, fragmentiert wird. 

    - Um VoIP in allen Besprechungen eines bestimmten Organisators zu deaktivieren, legen Sie über das cmdlet "Set-CsConferencingPolicy" den Parameter AllowIPAudio der Konferenzrichtlinie des Benutzers auf "false" (falsch) festgelegt. Weitere Informationen finden Sie unter [Set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
 
- Wenn eine Organisation VoIP nicht für alle Besprechungen deaktiviert, empfiehlt es sich, die Verwendung der Skype for Business Online-Integration mit einem Drittanbieter-ACP für Benutzer zu deaktivieren und die Besprechungen neu zu terminieren, um die Drittanbieter-ACP-Einwahlinformationen zu entfernen, um Audiofragmentierung zu verhindern.

    - Um die Integration von Drittanbieter-Audiokonferenzen für einen bestimmten Organisator zu deaktivieren, verwenden Sie das [Cmdlet Remove-CsUserAcp.](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

    - Informationen zum automatischen Neuplanen der Besprechungen finden Sie unter "Wie kann ich die Besprechungsmigration manuell für einen Benutzer ausführen?" unter [Einrichten des Meeting Migration Service (MMS).](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a>Pfad #3: Beenden der vollständigen Verwendung von Einwahlkonferenzen

Organisationen, die sich entscheiden, Einwahlkonferenzen vollständig zu verwenden (weder von Microsoft noch von einem Drittanbieter-ACP bereitgestellt), können sich vollständig auf VoIP verlassen, um den Audioteil einer Skype for Business-Besprechung zu unterstützen. 

Diese Organisationen müssen die Verwendung eines Drittanbieters für Audiokonferenzen deaktivieren und ihre Besprechungen automatisch mithilfe des Besprechungsmigrationsdiensts neu anberaumen, um die Informationen zu Einwahlkonferenzen zu entfernen. 

- Um die Integration von Drittanbieter-Audiokonferenzen für einen bestimmten Organisator zu deaktivieren, verwenden Sie das Remove-CsUserAcp-Cmdlet. Weitere Informationen finden Sie unter [Remove-CsUserAcp.](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

- Informationen zum automatischen Neuplanen der Besprechungen von Benutzern nach dem Deaktivieren der Integration mit einem Drittanbieter für Audiokonferenzen finden Sie unter "Wie kann ich die Besprechungsmigration manuell für einen Benutzer ausführen?" unter [Einrichten des Meeting Migration Service (MMS).](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md) 

**Zusammenfassung:** 

- Organisationen, die Audiokonferenzen vor dem 31. Juli 2021 ganz beenden, sind davon nicht betroffen.

- Um die Integration von Drittanbieter-Audiokonferenzen für einen bestimmten Organisator zu deaktivieren, verwenden Sie das Remove-CsUserAcp-Cmdlet. Weitere Informationen finden Sie unter [Remove-CsUserAcp.](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

- Informationen zum automatischen Neuplanen der Besprechungen von Benutzern nach dem Deaktivieren der Integration mit Drittanbieter-Audiokonferenzanbietern finden Sie unter "Wie kann ich die Besprechungsmigration manuell für einen Benutzer ausführen?" unter [Einrichten des Meeting Migration Service (MMS).](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

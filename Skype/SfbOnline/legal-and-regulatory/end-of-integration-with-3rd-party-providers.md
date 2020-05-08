---
title: 'Programm zum Ende des Lebenszyklus zur Integration von Skype for Business mit Audiokonferenz-Anbietern von Drittanbietern '
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
description: Am 31. Juli, 2021, wird das Programm für den Lebenszyklusende für die Integration von Skype for Business mit externen Audiokonferenz-Anbietern (Drittanbieter-ACP) abgeschlossen.
ms.openlocfilehash: 5b49bf573ad79cbdacbc538a0ef67faf1b2b634e
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164454"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a>Programm zum Ende des Lebenszyklus zur Integration von Skype for Business mit Audiokonferenz-Anbietern von Drittanbietern 

Microsoft hat den Beginn des Programms "End-Life" für die Integration von Skype for Business mit Drittanbieter-Audiokonferenz-Anbietern (ACPS) angekündigt. 

Das Programm zum Ende des Lebenszyklus endet am 31. Juli 2021. Nach Abschluss des Programms funktioniert die Integration von Skype for Business mit Drittanbieter-Audiokonferenz-Anbietern nicht mehr, und die folgenden Änderungen werden an diesem Datum beobachtet (31. Juli 2021):

- Teilnehmer, die versuchen, an einer Skype for Business-Besprechung teilzunehmen, über Einwahlnummern, die von einem externen AKP-Dienst bereitgestellt werden, werden nicht mehr mit der Skype for Business-Besprechung verbunden.
 
- Für Benutzer, die für einen AKP-Dienst eines Drittanbieters aktiviert sind, werden Ihre Einwahlinformationen nicht mehr automatisch in neue Skype for Business-Besprechungseinladungen aufgenommen.

Im Rahmen der Bekanntgabe des Starts des Programms "Ende des Lebenszyklus" haben sich die folgenden Änderungen in Kraft gesetzt und werden bis zum Abschluss des Programms "Ende des Lebenszyklus" weiterhin bestehen: 

- Kunden, die keine Skype for Business-Benutzer für die Verwendung eines Drittanbieter-ACP-Diensts konfiguriert haben, können keine Benutzer so konfigurieren, dass Sie einen Drittanbieter-ACP-Dienst verwenden.

- Bestehende Kunden mit Skype for Business-Benutzern, die für die Verwendung eines Drittanbieter-ACP-Diensts konfiguriert sind, können weiterhin neue Benutzer für die Dauer des Lebenszyklus hinzufügen. Beachten Sie bitte, dass wir nicht empfehlen, zusätzliche Skype for Business-Benutzer zur Nutzung eines Drittanbieters für AKP-Dienste einzurichten, da die Änderungen, die am 31. Juli 2021 in Kraft treten, auch auf Sie zutreffen.

## <a name="preparing-for-this-change"></a>Vorbereiten dieser Änderung

Zur Vorbereitung dieser Änderung ermutigen wir betroffene Organisationen, Ihre aktivierten Benutzer über dieses geplante Update vor dem 31. Juli 2021 zu informieren. 

Nach dem 31. Juli 2021 können Nutzer Skype for Business weiterhin ohne Unterbrechung Ihrer Online-Besprechungen nutzen. Organisationen müssen jedoch Ihre Benutzer für Audiokonferenzen aktivieren, die von Microsoft bereitgestellt werden, wenn Sie Einwahl-Audiokonferenzen mit Skype for Business oder Microsoft Teams benötigen. Weitere Informationen zu Microsoft-Audiokonferenzen finden Sie unter [Audiokonferenzen](https://products.office.com/skype-for-business/audio-conferencing). 

Je nach dem gewünschten Endstatus einer Organisation können drei Pfade befolgt werden:

- Migrieren zu Microsoft-Audiokonferenzen 
- Verwenden Sie weiterhin separat einen Audiokonferenz-Anbieter von Drittanbietern. 
- Beenden Sie die Verwendung von Einwahlkonferenzen insgesamt.

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a>Path #1: Migration zu Microsoft Audio Conferencing   

Organisationen, die beschließen, zu Microsoft-Audiokonferenzen zu migrieren und Ihre Migration vor dem 31. Juli 2021 abzuschließen, werden während oder nach diesem Datum keine Auswirkungen auf den Dienst haben. Bei der Migration zu Microsoft Audio Conferencing werden die folgenden Änderungen an einer Organisation eingeführt: 

- Dem Dienst werden alle anderen Microsoft 365-oder Office 365-Dienste in Rechnung gestellt. 

- Wenn das Standardabonnement erworben wurde, werden die Gebühren Einwahl Kosten in die monatlichen Abonnementkosten pro Nutzer einbezogen. 

- Jeder Organisation und ihren Benutzern wird eine neue Gruppe von Einwahl Telefonnummern zur Verfügung gestellt. Informationen zur geografischen Reichweite des Microsoft-Audiokonferenzdienst finden Sie unter [Verfügbarkeit von Ländern und Regionen für Audiokonferenz-und Anrufpläne](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).
 
- Besprechungen, die von Benutzern, die mit einem Drittanbieter-ACP aktiviert wurden, bereits geplant wurden, werden automatisch neu geplant, um Einwahlinformationen für Microsoft-Audiokonferenz einzubeziehen.
 
- Die Konferenz-IDs jeder Besprechung sind dynamisch, was bedeutet, dass jede Besprechung eine eigene dedizierte Konferenz-ID hat. Dynamische Konferenz-IDs sorgen für mehr Sicherheit und eine verbesserte Benutzeroberfläche für Besprechungen in einem anderen Hintergrund.

- Die gesamte Nutzung des Diensts unterliegt den Nutzungsbedingungen für Audiokonferenz-Dienste. 

Das Migrieren zu Microsoft-Audiokonferenzen ist einfach und kann nach dem Erwerb der Lizenzen für den Dienst in nur wenigen Schritten erfolgen. Informationen zum Migrieren zu Microsoft-Audiokonferenzen finden Sie unter:

- [Testen oder kaufen von Audiokonferenzen in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
**Zusammenfassung:**

- Organisationen, die zu Microsoft-Audiokonferenzen migrieren und Ihre Migration vor dem 31. Juli 2021 durchführen, sehen während oder nach diesem Datum keine Auswirkungen auf Ihren Dienst.

- Weitere Informationen zum Migrieren zu Microsoft-Audiokonferenzen finden Sie unter [Testen oder kaufen von Audiokonferenzen in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md). 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a>Path #2: weiter zur separaten Verwendung eines Drittanbieters für Audiokonferenzen

Organisationen, die beschließen, weiterhin eine Drittanbieter-ACP am und nach dem 31. Juli 2021 zu verwenden, werden Auswirkungen auf den Dienst haben, da die Einwahlinformationen des Drittanbieters nicht mehr für die Teilnahme am Audioteil einer Skype for Business-Besprechung verwendet werden können. 

Um die Fragmentierung von Audio in Skype for Business-Besprechungen zu verhindern, indem einige Teilnehmer über VoIP und andere über das Drittanbieter-ACP beitreten, sollten diese Organisationen die Verwendung von VoIP in den Besprechungen Ihrer Benutzer deaktivieren. Auf diese Weise müssen alle Teilnehmer mit dem Drittanbieter-ACP an dem Audioteil einer Besprechung teilnehmen, und alle anderen Arbeitsauslastungen der Besprechung (wie Chats oder Bildschirmübertragung) können weiterhin über Skype for Business unterstützt werden. 

- Um VoIP aus allen Besprechungen eines bestimmten Organisators zu deaktivieren, setzen Sie den AllowIPAudio-Parameter seiner konferenzrichtlinie über das Cmdlet "CsConferencingPolicy" auf "false". Weitere Informationen finden Sie unter [Satz-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
 
Im Hinblick auf die Planung und ab dem 31. Juli 2021 werden die Einwahlinformationen eines Drittanbieters nicht mehr automatisch in Skype for Business-Besprechungseinladungen aufgenommen. Benutzer müssen die Einwahlinformationen in Ihren Skype for Business-Besprechungseinladungen manuell hinzufügen, wenn Sie diese Informationen im Rahmen ihrer Besprechungen weiterhin einbeziehen möchten. 

Bitte beachten Sie, dass die vorhandenen Nutzer Treffen am 31. Juli 2021 nicht automatisch neu geplant werden, um die Einwahlinformationen von Drittanbietern zu entfernen. Organisationen, die beschließen, VoIP für die Besprechungen Ihrer Benutzer zu aktivieren, sollten die Integration von Drittanbieter-ACP für Ihre Benutzer deaktivieren und Ihre Besprechungen mithilfe des Besprechungs Migrations Diensts neu planen, um die Einwahlinformationen von Drittanbietern für Audiokonferenzen aus Ihren vorhandenen Besprechungen zu entfernen und die Fragmentierung von Audio in bereits geplanten Besprechungen zu verhindern. 

- Verwenden Sie das Cmdlet Remove-CsUserAcp, um die Integration von Audiokonferenzen von Drittanbietern für einen bestimmten Organisator zu deaktivieren. Weitere Informationen finden Sie unter [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps). 

- Wenn Sie die Besprechungen von Benutzern nach dem Deaktivieren der Integration mit einem Drittanbieter für Audiokonferenzen automatisch neu planen möchten, lesen Sie "wie führe ich die Besprechungs Migration manuell für einen Benutzer aus?" aus. beim [Einrichten des Besprechungs Migrations Diensts (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md). 

**Zusammenfassung:**

- Organisationen, die beschließen, weiterhin eine Drittanbieter-ACP am und nach dem 31. Juli 2021 zu verwenden, werden davon betroffen sein, da ein Drittanbieter-ACP nicht in der Lage ist, an einer Skype for Business-Besprechung teilzunehmen, und neue Besprechungen keine AKP-Einwahlinformationen von Drittanbietern enthalten werden. 

- Es wird empfohlen, dass VoIP für alle Besprechungen aller betroffenen Benutzer vor dem 31. Juli, 2021, deaktiviert wird, um zu verhindern, dass die Audiodaten von Teilnehmern fragmentiert werden, die über VoIP und über ein Drittanbieter-ACP beitreten. 

    - Um VoIP aus allen Besprechungen eines bestimmten Organisators zu deaktivieren, setzen Sie den AllowIPAudio-Parameter der konferenzrichtlinie des Benutzers über das Cmdlet "CsConferencingPolicy" auf "false". Weitere Informationen finden Sie unter [Satz-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
 
- Wenn eine Organisation VoIP nicht für alle Besprechungen deaktiviert, wird empfohlen, dass Benutzer die Skype for Business Online-Integration mit einem Drittanbieter-ACP deaktivieren und Ihre Besprechungen neu planen, um die Einwahlinformationen des Drittanbieters zu entfernen, um eine Fragmentierung des Audiosignals zu verhindern.

    - Verwenden Sie das Cmdlet [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps) , um die Integration von Audiokonferenzen von Drittanbietern für einen bestimmten Organisator zu deaktivieren. 

    - Wenn Sie die Besprechungen automatisch neu planen möchten, lesen Sie "wie führe ich die Besprechungs Migration manuell für einen Benutzer aus?" aus. beim [Einrichten des Besprechungs Migrations Diensts (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a>Path #3: Beenden der Verwendung von Einwahlkonferenzen insgesamt

Organisationen, die sich entscheiden, die Verwendung von Einwahlkonferenzen vollständig zu beenden (weder von Microsoft noch von einem Drittanbieter-ACP bereitgestellt), können sich voll und ganz auf VoIP verlassen, um den Audioteil einer Skype for Business-Besprechung zu unterstützen. 

Diese Organisationen müssten Ihre Benutzer davon abhalten, einen Drittanbieter für Audiokonferenzen zu verwenden und Ihre Besprechungen mithilfe des Besprechungs Migrations Diensts automatisch neu zu planen, um Ihre Einwahlkonferenzinformationen zu entfernen. 

- Verwenden Sie das Cmdlet Remove-CsUserAcp, um die Integration von Audiokonferenzen von Drittanbietern für einen bestimmten Organisator zu deaktivieren. Weitere Informationen finden Sie unter [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps). 

- Wenn Sie die Besprechungen von Benutzern nach dem Deaktivieren der Integration mit einem Drittanbieter für Audiokonferenzen automatisch neu planen möchten, lesen Sie "wie führe ich die Besprechungs Migration manuell für einen Benutzer aus?" aus. beim [Einrichten des Besprechungs Migrations Diensts (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md). 

**Zusammenfassung:** 

- Organisationen, die beschließen, die Verwendung von Audiokonferenzen vor dem 31. Juli 2021 zu beenden, werden nicht beeinträchtigt.

- Verwenden Sie das Cmdlet Remove-CsUserAcp, um die Integration von Audiokonferenzen von Drittanbietern für einen bestimmten Organisator zu deaktivieren. Weitere Informationen finden Sie unter [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps). 

- Wenn Sie die Besprechungen von Benutzern nach der Deaktivierung der Integration in Drittanbieter für Audiokonferenzen automatisch neu planen möchten, lesen Sie "wie führe ich die Besprechungs Migration manuell für einen Benutzer aus?" aus. beim [Einrichten des Besprechungs Migrations Diensts (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).

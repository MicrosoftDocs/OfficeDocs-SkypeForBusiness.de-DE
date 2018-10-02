---
title: Konfigurieren von live Ereignisse in Microsoft-Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Erfahren Sie, wie live-Ereignis Microsoft-Teams, einschließlich Attendee Sichtbarkeit festlegen und Aufzeichnungsoptionen zu konfigurieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcd9bc02257d67f1af959d2158042ea73545a25e
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354356"
---
# <a name="configure-live-events-in-microsoft-teams"></a>Konfigurieren von live Ereignisse in Microsoft-Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="set-up-event-support-link"></a>Einrichten von Ereignis Support link
Dies ist die Verknüpfung, die an die Teilnehmer live-Ereignis angezeigt werden. 

Führen Sie in Windows PowerShell folgenden Befehl:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
## <a name="configure-attendee-visibility-options"></a>Konfigurieren Sie die Sichtbarkeitsoptionen für Teilnehmer
Live-Ereignis Organisatoren Ereignisse mit entsprechenden Attendee Sichtbarkeit erstellen können.

|**Werte**  |**Verhalten**  |
|---------|---------|
|Jeder     |Der Benutzer hat eine Option zum Erstellen von live Ereignisse mit dem folgenden Attendee Sichtbarkeit: Public, jede Person in Unternehmen und bestimmte Personen. |
|EveryoneInCompany     |Der Benutzer hat eine Option zum Erstellen von live Ereignisse mit dem folgenden Attendee Sichtbarkeit: alle Benutzer im Unternehmen und bestimmte Personen. Der Benutzer kann nicht live Ereignisse erstellen, die durch anonyme Benutzer behandelt werden kann.|
|InvitedUsers |Der Benutzer kann nur live Ereignisse erstellen, die auf bestimmte Personen beschränkt sind durch den Organisator des Ereignisses eingegeben wurde. Der Benutzer kann nicht mit öffentlichen und alle Benutzer im Unternehmen Authentifizierung live Ereignisse erstellen. |

Verwenden Sie die Einstellung BroadcastAttendeeVisibility in TeamsMeetingBroadcastPolicy in PowerShell können Sie steuern, ob die Benutzer broadcast Ereignisse planen können, die durch anonyme Teilnehmer beobachtet werden kann. 

Es sei denn, die Benutzer eine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer globale Richtlinie ein, die standardmäßig auf EveryoneInCompany festgelegt hat. 
 
Führen Sie den folgenden damit anonyme Ereignisse in der globalen Richtlinie erstellen, die Benutzer können in Windows PowerShell aus:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="configure-recording-options"></a>Konfigurieren Sie die Aufzeichnungsoptionen
> [!NOTE]
> Diese Option ist für Ereignisse, die der Schnellstart Produktion-nur Methode anwendbar.

Dies ermöglicht Administratoren zur Steuerelement an, ob die live Ereignisse immer noch nie aufgezeichnet, aufgezeichnet werden, oder der Organisator des Ereignisses zum Aufzeichnen des Ereignisses oder nicht entscheiden kann.  

|**Werte**  |**Verhalten**  |
|---------|---------|
|Immer aktiviert |Die von diesem Benutzer organisierte live Ereignisse werden immer aufgezeichnet. Der Benutzer keine Option außer Kraft gesetzt. Wenn das live Ereignis aufgezeichnet wird, die Mitglieder des Teams können die Aufzeichnung nach dem Ereignis herunterzuladen und die Teilnehmer können sehen Sie sich das Ereignis nach Abschluss des Ereignisses. |
|AlwaysDisabled |Die von diesem Benutzer organisierte live Ereignisse werden nie aufgezeichnet. Der Benutzer keine Option außer Kraft gesetzt. Wenn das live Ereignis aufgezeichnet wird, wird keine Aufzeichnung für die Mitglieder des Teams erstellt, und die Teilnehmer können nicht sehen Sie sich das Ereignis nach über ist. |
|UserOverride |Benutzer kann entscheiden, ob das live-Ereignis, damit eine Aufzeichnungsdatei für die Mitglieder des Teams erstellt werden kann und Teilnehmer können sehen Sie sich das Ereignis nach Abschluss des Ereignisses aufgezeichnet wird. |

Verwenden Sie die Einstellung *BroadcastRecordingMode* in **TeamsMeetingBroadcastPolicy** in PowerShell Steuerelement Aufzeichnungsoptionen live Ereignisse vom Organisator live-Ereignis erstellt.

Führen Sie in Windows PowerShell das folgende Cmdlet, um Aufzeichnungsmodus in der globalen Richtlinie zu aktualisieren:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Konfigurieren von Real-Time Lautschrift und Übersetzung in Teams live-Ereignisse (bald verfügbar)
> [!NOTE]
> Diese Option ist für Ereignisse, die der Schnellstart Produktion-nur Methode anwendbar.

Dadurch können live-Ereignis Organisatoren, Real-Time Beschriftungen und Übersetzung für den Teilnehmern live-Ereignis zu aktivieren. 

Verwenden Sie die Einstellung *AllowBroadcastTranscription* in **TeamsMeetingBroadcastPolicy** in PowerShell Kontrolle, ob die Teilnehmer live-Ereignis Umsetzung und Übersetzung finden Sie unter können. Erfahren Sie mehr über das Verwalten von **TeamsMeetingBroadcastPolicy** mit Office 365 PowerShell hier.  

Es sei denn, die Benutzer eine benutzerdefinierte Richtlinie zugewiesen haben, erhalten die Benutzer globale Richtlinie ein, die Umsetzung und Übersetzung standardmäßig deaktiviert hat.

Führen Sie in Windows PowerShell das folgende Cmdlet, um die Umsetzung und eine Übersetzung auf Ereignis Teilnehmer in der globalen Richtlinie zu aktivieren:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
## <a name="administrative-tools"></a>Verwaltungstools 
Obwohl Microsoft Office 365 Online Rechenzentren alle Steuerelemente direkt und verantwortlich für die Leistung des gesamten Systems ist, kann es nur einen Teil der Elemente steuern, die kombiniert werden, um den Gesamtnutzen für Office 365-Benutzer bereitzustellen. Organisationen selbst die Verantwortung für die Netzwerkverbindungen mit der Rechenzentren, die Kunden Fernnetz (WAN), und der Kunde lokale Netzwerke (LANs). Darüber hinaus sind für Benutzer Geräte und deren Konfiguration.Sie werden darüber hinaus verantwortlich für die Verwaltung der erforderliche Lizenzierung pro Benutzer für alle gewünschten Features, einschließlich, aber nicht beschränkt auf die Möglichkeit, diese Features für verwalten, solange der Benutzer Zugriff auf dieses Feature benötigt.

Kunden können die folgenden Tools verwenden, um eine Vielzahl von Teams live Ereignisse Aufgaben im Zusammenhang mit verwalten.
- [Microsoft Office 365 Administrationscenter](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft-Teams und Skype für Business Online Administrationscenter](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [Microsoft-Stream-Verwaltungskonsole](https://stream.microsoft.com)
- [Windows PowerShell-Remotesitzungen](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?
Wenn es auf Windows PowerShell, es darum geht alle Informationen zum Verwalten von Benutzern und welche Benutzer zulässig sind oder nicht durchgeführt werden darf. Mit Windows PowerShell können Sie Office 365 und Skype verwalten, für die Business Online verwenden eine zentrale Verwaltung, die Ihrer täglichen Arbeit vereinfachen können, wenn Sie mehrere Aufgaben ausführen müssen. Siehe folgende Themen, um Windows PowerShell zu verwenden:
 - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
 - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

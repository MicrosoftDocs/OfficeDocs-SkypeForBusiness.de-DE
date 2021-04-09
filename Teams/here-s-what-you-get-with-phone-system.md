---
title: Vorteile des Telefonsystems
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, makolomi
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Erfahren Sie mehr über die Features, die Verfügbarkeit und das Planen und Einrichten von Microsoft Phone System für Ihr Unternehmen. '
ms.openlocfilehash: b26f6d72a92f0012f47d155531be523872e5a08c
ms.sourcegitcommit: c80af314f1a573f99dd66858301c004ccc5410d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2021
ms.locfileid: "51648134"
---
# <a name="heres-what-you-get-with-phone-system"></a>Vorteile des Telefonsystems

In diesem Artikel werden die Funktionen des Telefonsystems beschrieben. Weitere Informationen zur Verwendung von Telefonsystem als Ersatz für die Private Branch Exchange (PBX) und Optionen zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN) finden Sie unter Was [ist Telefonsystem.](what-is-phone-system-in-office-365.md)

Clients sind für PC, Mac und Mobile verfügbar, die Features auf Geräten von Tablets und Mobiltelefonen bis zu PCs und Desktop-IP-Telefonen bieten. Weitere Informationen finden Sie unter [Clients für Microsoft Teams erhalten.](get-clients.md)

 > [!Note]
> Details zu Telefonsystemen von Teams auf verschiedenen Plattformen finden Sie unter [Teams-Features nach Plattform.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)
  
## <a name="phone-system-features"></a>Telefonsystemfunktionen

Telefonsystem bietet die folgenden Features. Sofern nicht anders angegeben, stehen Features sowohl in Teams als auch in Skype for Business Online zur Verfügung.
  
|||
|:-----|:-----|
|**Telefonsystemfeature** <br/> |**Beschreibung** <br/> |
|[Automatische Cloud-Attendanten](what-are-phone-system-auto-attendants.md) <br/> |Hiermit können Sie ein Menüsystem erstellen, mit dem externe und interne Anrufer Anrufe an Unternehmensbenutzer oder Abteilungen in Ihrer Organisation suchen und platzieren oder übertragen können.  <br/> |
|[Warteschlangen für Cloudanrufe](create-a-phone-system-call-queue.md) <br/> |Hiermit können Sie konfigurieren, wie Anrufwarteschlangen für Ihre Organisation verwaltet werden: z. B. Begrüßungen und Musik im Halteraum einrichten, nach dem nächsten verfügbaren Anrufer suchen, um den Anruf zu behandeln, und so weiter.  <br/> |
|Wartemusik | Gibt vom Dienst definierte Standardmusik wieder, wenn ein externer Anruf aus dem PstN (Public Switched Telephone Network) in den Halteraum gesetzt wird. Dieses Feature funktioniert sowohl bei Anrufen, die an eine Anrufwarteschlange gemacht werden als auch bei 1:1-PSTN-zu-Teams-Anrufen. Dieses Feature bietet eine Halten-Benachrichtigungsparität zu anderen Plattformen. Dieses Feature kann vom Administrator konfiguriert werden, [derzeit jedoch nur über PowerShell.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) Das Halten von Musik wird auch bei der konsultativen Übertragung eines PSTN-Anrufs nicht unterstützt.|
|Anruf annehmen/initiieren (nach Name und Nummer)  <br/> |Ermöglicht Benutzern, eingehende Anrufe per Touchanruf zu beantworten und ausgehende Anrufe entweder durch Wählen der vollständigen Telefonnummer oder durch Klicken auf einen Namen im Client zu platzieren.  <br/> |
|[Anruf forwarding options and simultaneous ring](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |Ermöglicht Benutzern das Einrichten von Weiterleitungsregeln, damit Anrufe überall mit ihnen bzw. anrufe an Kollegen oder voicemail weitergeleitet werden können.  <br/> |
|[Gruppenanrufabholung und Weiterleiten an Die Gruppe](call-sharing-and-group-call-pickup.md) <br/> | Ermöglicht benutzern, eingehende Anrufe mit Kollegen zu teilen, damit die Kollegen Anrufe entgegenrufen können, die auftreten, während der Benutzer nicht verfügbar ist. Weniger störend für Empfänger als andere Arten der Anruffreigabe (z. B. Anruf weiterleitung oder gleichzeitiges Anrufen), da Benutzer konfigurieren können, wie sie über einen eingehenden freigegebenen Anruf benachrichtigt werden möchten. |
|[Übertragen eines Anrufs und einer konsultativen Übertragung](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |Ermöglicht Es Benutzern, Anrufe an eine andere Person zu überträgt. Oder wenn sie ihr Büro verlassen müssen, die Unterhaltung aber fortsetzen möchten, können sie die Anrufe von ihrem PC oder IP-Telefon auf ihr Mobiltelefon übertragen.  <br/> |
|[Übertragen in voicemail mid call](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | Ermöglicht Benutzern, während eines Anrufs zur Voicemail zu übertragen. |
|[Parken von Anrufen und Holen](call-park-and-retrieve.md)  <br/> | Ermöglicht Benutzern, einen Anruf im Halteraum des Teams-Diensts in der Cloud zu halten. Wenn ein Anruf geparkt wird, generiert der Dienst einen eindeutigen Code für den Anrufabruf. Der Benutzer, der den Anruf geparkt hat, oder eine andere Person kann diesen Code und eine unterstützte App oder ein unterstütztes Gerät verwenden, um den Anruf abzurufen. <br/> |
|Telefonnummer über die Suche anrufen  <br/> | Ermöglicht Benutzern, einen Anruf über das Suchfeld zu platzieren, indem sie den Befehl /call verwenden und einen Namen oder eine Nummer angeben. <br/> |
|[Anrufer-ID](how-can-caller-id-be-used-in-your-organization.md)  <br/> |Anrufe aus dem Unternehmen zeigen eine detaillierte Anrufer-ID an, die Informationen aus dem Unternehmensverzeichnis abruft, die bild-ID und Stellentitel anstelle einer Telefonnummer enthält. Bei Anrufen von externen Telefonnummern wird die vom Telefondienstanbieter bereitgestellte Anrufer-ID angezeigt. Wenn es sich bei den externen Telefonnummern um Sekundärnummern im Unternehmensverzeichnis handelt, werden die Informationen aus dem Unternehmensverzeichnis angezeigt.  <br/> |
|Gerät wechseln  <br/> |Ermöglicht benutzern die Wiedergabe eines Anrufs oder einer Besprechung auf einem anderen HID-Gerät, das mit Teams verbunden ist. Beispielsweise können Sie von ihren PC-Lautsprechern auf ein Headset umschalten.   <br/> |
|Anwesenheitsbasiertes Anrufrouting <br/> |Steuert eingehende Kommunikationen mit Anwesenheitsinformationen, sodass der Benutzer die gesamte eingehende Kommunikation blockieren kann, mit Ausnahme der ausdrücklich angegebenen.  <br/> |
|[Integrierte Wähltapad](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | Ermöglicht Benutzern das Wählen nach Name oder Nummer an einer beliebigen Stelle in der Suchleiste und auf der Wähltaste, wodurch der Vorgang der ausgehenden Anrufe beschleunigt wird. <br/> |
|Verbundrufe  <br/> |Ermöglicht Benutzern eine sichere Verbindung, Kommunikation und Zusammenarbeit mit Benutzern in Verbund-Mandanten.  <br/> |
|[Erstellen und Empfangen eines Videoanrufs](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | Wenn das Konto des Benutzers für Videoanrufe aktiviert ist, kann der Benutzer mit seinen Kontakten persönliche Videoanrufe machen. Alles, was sie benötigen, ist eine Kamera, die Lautsprecher und das Mikrofon ihres Computers. Benutzer können auch ein Headset verwenden, wenn ihr Computer nicht über ein integriertes Audiogerät verfügt.<br/> |
|[Cloud voicemail](set-up-phone-system-voicemail.md) <br/> | Wenn ein Benutzer eine Voicemail empfängt, wird sie als E-Mail mit der Voicemailnachricht als Anlage an ihr Exchange-Postfach übermittelt. Benutzer können ihre Nachrichten auf ihrem zertifizierten Desktoptelefon und in allen Teams- oder Skype for Business-Anwendungen anhören. Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert.   <br/> |
|[Benutzereinstellungen für Cloud voicemail](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Ermöglicht Benutzern das Konfigurieren ihrer Clienteinstellungen für Voicemailanrufe, Anrufbeantwortungsregeln und Grußsprache, einschließlich Außer-Office-Begrüßungen.   |
|[Sekundärer Klingelton](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | Benutzer mit mehreren Lautsprechergeräten, die an ihren PC angeschlossen sind, können zusätzlich zu ihrem Standardlautsprecher ein sekundäres Gerät zum Klingeln festlegen. Ein Benutzer mit einem Headset, das an den PC und die Tischlautsprecher angeschlossen ist, kann z. B. auswählen, dass sowohl Headset- als auch Tischlautsprecher klingeln, wenn ein Anruf einkommt, damit er keinen Anruf verpasst.  |
|[Benachrichtigungen mit klingelnden Benachrichtigungen](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (nur Teams)<br/> |Ermöglicht Benutzern die Auswahl separater Klingeltöne für normale Anrufe, weitergeleitete Anrufe und delegierte Anrufe, damit sie die Art des Anrufs unterscheiden können.  <br/> |
|[Funktion "Gemeinsame Leitungen"](shared-line-appearance.md) <br/> | Ermöglicht Benutzern, ihre Telefonleitung zu teilen, damit ein anderer Benutzer anrufe in ihrem Auftrag anrufen und empfangen kann.|
|[Beschäftigt bei Beschäftigt](teams-calling-policy.md) (nur Teams) <br/> | Eine Anrufrichtlinie, mit der Sie konfigurieren können, wie eingehende Anrufe behandelt werden, wenn ein Benutzer bereits an einem Anruf oder einer Konferenz teilnimmt oder einen Anruf in den Halteraum gesetzt hat. Der Anrufer hört entweder ein ausgelastetes Signal, wenn der Anrufer bereits am Telefon ist, oder er wird entsprechend an die nicht beantworteten Einstellungen des Benutzers weiter geroutet, d. h., der Anrufer kann dem Benutzer, der sich bereits an einem Anruf befindet, eine Voicemail hinterlassen. Der Anrufer erhält eine Benachrichtigung über verpasste Anrufe, kann jedoch keine eingehenden Anrufe entgegenrufen. Dieses Feature ist standardmäßig deaktiviert, kann aber vom Mandantenadministrator aktiviert werden.|
|[Anrufblockierung](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Ermöglicht Benutzern das Hinzufügen von Telefonnummern (PSTN) zu einer blockierten Liste, sodass der nächste Anruf von dieser Nummer an den Benutzer blockiert wird.|
|[Telefone im allgemeinen Bereich](set-up-common-area-phones.md) <br/> | Ein Telefon im allgemeinen Bereich wird in der Regel in einem Bereich wie einem Wartebereich oder Konferenzraum platziert, wodurch es für mehrere Personen zur Verfügung steht. Telefone im allgemeinen Bereich werden als Geräte und nicht als Benutzer eingerichtet und können sich automatisch bei einem Netzwerk anmelden.|
|[Medienumgehungsunterstützung](direct-routing-plan-media-bypass.md) (nur für Teams Direct Routing) <br/> | Um eine bessere Leistung zu erzielen, werden Medien zwischen dem Session Border Controller (SBC) und dem Client gespeichert, statt sie über das Microsoft Phone System zu senden. |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>Verfügbarkeit in GCC-Hoch- und DoD-Wolken
<a name="bkmk_setup"> </a>

Die folgenden Funktionen sind in GCC-Hoch- und DoD-Wolken noch nicht verfügbar. 
- [Anrufeinstellungen für sekundären Klingelton, Voicemail und erweiterte Delegierung](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Übertragen in voicemail mid call](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Telefonnummer über die Suchleiste anrufen
- Wartemusik
- Azure AD Reverse Number Lookup

## <a name="related-topics"></a>Verwandte Themen

- [Was ist das Telefonsystem?](what-is-phone-system-in-office-365.md)
- [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md)
- [Einrichten des Telefonsystems](setting-up-your-phone-system.md)
- [Welcher Anrufplan ist für Sie am besten geeignet?](calling-plan-landing-page.md)
- [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md)
- [Überwachen und Verwalten der Anrufqualität](monitor-call-quality-qos.md)
- [Lizenzierung für Microsoft Teams-Add-Ons](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Preise für das Telefonsystem](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams für virtualisierte Desktopinfrastruktur mit Anrufen und Besprechungen](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

  

---
title: Das Telefonsystem bietet Ihnen Folgendes
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Informieren Sie sich über die Features, die Verfügbarkeit und die Vorgehensweise zum Planen und Einrichten von Microsoft Phone System für Ihr Unternehmen. '
ms.openlocfilehash: fa7acbd4593b44805b2f9044602f3521baacaaaf
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638344"
---
# <a name="heres-what-you-get-with-phone-system"></a>Das Telefonsystem bietet Ihnen Folgendes

In diesem Artikel werden die Funktionen des Telefonsystems beschrieben. Weitere Informationen zur Verwendung des Telefonsystems als Ersatz für Private Branch Exchange (PBX) und Optionen für die Verbindung mit dem öffentlichen Telefonnetz (PSTN) finden Sie unter [Was ist Telefonsystem](what-is-phone-system-in-office-365.md).

Clients stehen für PC, Mac und Handy zur Verfügung und bieten Funktionen auf Geräten von Tablets und Mobiltelefonen bis hin zu PCs und Desktop-IP-Telefonen. Weitere Informationen finden Sie unter [Abrufen von Clients für Microsoft Teams](get-clients.md).

  
## <a name="phone-system-features"></a>Telefon System Funktionen

Das Telefon System bietet die folgenden Funktionen. Sofern nicht anders angegeben, stehen Features sowohl in Teams als auch in Skype for Business Online zur Verfügung.
  
|||
|:-----|:-----|
|**Telefon System Feature** <br/> |**Beschreibung** <br/> |
|[Automatische Cloud-Telefonzentralen](what-are-phone-system-auto-attendants.md) <br/> |Mit dieser Option können Sie ein Menü System erstellen, das es externen und internen Anrufern ermöglicht, Anrufe an Unternehmensbenutzer oder Abteilungen in Ihrer Organisation zu suchen und dort zu platzieren oder zu übertragen.  <br/> |
|[Cloud-Anrufwarteschlangen](create-a-phone-system-call-queue.md) <br/> |Mit dieser Option können Sie konfigurieren, wie Anrufwarteschlangen für Ihre Organisation verwaltet werden: Sie können beispielsweise Begrüßungen und Musik in Wartestellung einrichten, nach dem nächsten verfügbaren Anruf Agenten suchen, um den Anruf zu behandeln, und so weiter.  <br/> |
|Wartemusik | Gibt die vom Dienst definierte Standardmusik wieder, wenn ein externer Anruf über das öffentlich geschaltete Telefonnetz (PSTN) in Wartestellung gesetzt wird. Dieses Feature funktioniert sowohl bei Anrufen, die an eine Anrufwarteschlange gemacht werden als auch bei 1:1-PSTN-zu-Teams-Anrufen. Dieses Feature bietet eine Halten-Benachrichtigungsparität zu anderen Plattformen. Dieses Feature ist vom Administrator konfigurierbar, aber [derzeit nur über PowerShell](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Bei der Beratenden Übertragung eines PSTN-Anrufs wird "Musik speichern" ebenfalls nicht unterstützt.|
|Anruf annehmen/initiieren (nach Name und Nummer)  <br/> |Ermöglicht Benutzern, eingehende Anrufe per Tastendruck zu beantworten und ausgehende Anrufe zu tätigen, indem Sie entweder die vollständige Telefonnummer wählen oder im Client auf einen Namen klicken.  <br/> |
|[Optionen für die Anrufweiterleitung und gleichzeitiges Klingeln](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |Ermöglicht es Benutzern, Weiterleitungsregeln einzurichten, damit Anrufe überall mitgehen können oder Anrufe an Kollegen oder Voicemail weitergeleitet werden können.  <br/> |
|[Gruppenanruf Abholung und Weiterleiten an Gruppe](call-sharing-and-group-call-pickup.md) <br/> | Ermöglicht Benutzern das Freigeben eingehender Anrufe an Kollegen, damit die Kollegen Anrufe annehmen können, die eintreten, während der Benutzer nicht verfügbar ist. Weniger störend für Empfänger als andere Formen der Anruf Freigabe (wie Anrufweiterleitung oder gleichzeitiges Klingeln), da Benutzer konfigurieren können, wie Sie über einen eingehenden freigegebenen Anruf benachrichtigt werden möchten. |
|[Übertragen eines Anrufs und einer beratenden Übertragung](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |Ermöglicht Benutzern die Übertragung von Anrufen an eine andere Person. Oder wenn Sie Ihr Büro verlässt, aber die Unterhaltung fortsetzen möchten, können Sie die Anrufe von Ihrem PC oder IP-Telefon an Ihr Mobiltelefon übertragen.  <br/> |
|[Übertragung an Voicemail Mid-Anruf](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | Ermöglicht es Benutzern, während eines Anrufs eine Sprachnachricht zu übertragen. |
|[Parken von Anrufen und Holen](call-park-and-retrieve.md)  <br/> | Ermöglicht Benutzern, einen Anruf im Teams-Dienst in der Cloud zu halten. Wenn ein Anruf abgestellt wird, generiert der Dienst einen eindeutigen Code für den Abruf des Anrufs. Der Benutzer, der den Anruf abgestellt hat, oder eine andere Person kann diesen Code und eine unterstützte APP oder ein unterstütztes Gerät verwenden, um den Anruf abzurufen. <br/> |
|Telefonnummer von der Suche aus anrufen  <br/> | Ermöglicht Benutzern, einen Anruf über das Suchfeld zu tätigen, indem Sie den Befehl/Call verwenden und einen Namen oder eine Zahl angeben. <br/> |
|[Anrufer-ID](how-can-caller-id-be-used-in-your-organization.md)  <br/> |Bei Anrufen innerhalb des Unternehmens wird eine detaillierte Rufnummernanzeige angezeigt, die Informationen aus dem Unternehmensverzeichnis abruft, wobei die Bild-ID und die Position anstelle nur einer Telefonnummer angezeigt werden. Für Anrufe von externen Telefonnummern wird die Rufnummernanzeige angezeigt, die vom Telefondienstanbieter bereitgestellt wird. Wenn die externen Telefonnummern im Unternehmensverzeichnis Sekundär Nummern sind, werden die Informationen aus dem Unternehmensverzeichnis angezeigt.  <br/> |
|Gerät wechseln  <br/> |Ermöglicht Benutzern das Wiedergeben eines Anrufs oder einer Besprechung auf einem anderen HID-Gerät, das mit Teams verbunden ist. So können Sie beispielsweise von Ihren PC-Lautsprechern zu einem Headset wechseln.   <br/> |
|Anwesenheits basiertes Anrufrouting <br/> |Steuert die eingehende Kommunikation mit Anwesenheitsinformationen, sodass der Benutzer alle eingehenden Kommunikationen mit Ausnahme der ausdrücklich angegebenen blockieren kann.  <br/> |
|[Integrierte Wähltastatur](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | Ermöglicht Benutzern, sich über den Namen oder die Nummer an beliebiger Stelle in der Suchleiste und in der Wähltastatur anzuwählen, wodurch der Prozess der ausgehenden Anrufe beschleunigt wird. <br/> |
|Föderations Anrufe  <br/> |Ermöglicht Benutzern eine sichere Verbindung, Kommunikation und Zusammenarbeit mit Benutzern in Verbund Mandanten.  <br/> |
|[Führen und Empfangen eines Videoanrufs](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | Wenn das Konto des Benutzers für Videoanrufe aktiviert ist, kann der Benutzer persönliche Videoanrufe mit seinen Kontakten führen. Sie benötigen lediglich eine Kamera, die Lautsprecher und das Mikrofon Ihres Computers. Benutzer können auch ein Headset verwenden, wenn Ihr Computer nicht über ein integriertes Audiogerät verfügt.<br/> |
|[Cloud-Voicemail](set-up-phone-system-voicemail.md) <br/> | Wenn ein Benutzer eine Sprachnachricht erhält, wird er an sein Exchange-Postfach als e-Mail-Nachricht mit der Sprachnachricht als Anlage übermittelt. Die Benutzer können Ihre Nachrichten auf Ihrem zertifizierten Desktoptelefon und in allen Teams oder Skype for Business-Anwendungen anhören. Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert.   <br/> |
|[Cloud Voicemail-Benutzereinstellungen](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Ermöglicht Benutzern die Konfiguration Ihrer Clienteinstellungen für Voicemail-Begrüßungen, Anruf Antwort Regeln und Gruß Sprache, einschließlich Abwesenheits Begrüßungen.   |
|[Sekundärer Rufton](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | Benutzer mit mehreren Lautsprecher-Geräten, die an Ihren PC angeschlossen sind, können neben dem Standardlautsprecher auch ein sekundäres Gerät festlegen. Ein Benutzer mit einem Headset, das an den PC angeschlossen ist, und die Schreibtisch-Lautsprecher können beispielsweise festlegen, dass sowohl das Headset als auch die Schreibtisch-Lautsprecher Klingeln, wenn ein Anruf eingeht, damit er keinen Anruf verpasst.  |
|[Markante Anrufbenachrichtigungen](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (nur für Teams)<br/> |Ermöglicht Benutzern das auswählen separater Klingeltöne für normale Anrufe, weitergeleitete Anrufe und Delegierte Anrufe, damit diese die Art des Anrufs unterscheiden können.  <br/> |
|[Funktion "Gemeinsame Leitungen"](shared-line-appearance.md) <br/> | Ermöglicht Benutzern die Freigabe Ihrer Telefonleitung, damit ein anderer Benutzer in seinem Namen Anrufe tätigen und empfangen kann.|
|[Beschäftigt bei besetzt](teams-calling-policy.md) (nur Teams) <br/> | Eine Anrufrichtlinie, mit der Sie konfigurieren können, wie eingehende Anrufe gehandhabt werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf in Wartestellung gesetzt wurde. Der Anrufer hört ein Besetztzeichen, wenn der Anrufer bereits am Telefon ist. Der Anrufer erhält eine Benachrichtigung über verpasste Anrufe, kann aber keine eingehenden Anrufe annehmen. Dieses Feature ist standardmäßig deaktiviert, kann aber vom mandantenadministrator aktiviert werden. |
|[Anruf Blockierung](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Ermöglicht Benutzern das Hinzufügen von (PSTN-) Telefonnummern zu einer blockierten Liste, damit der nächste Anruf von dieser Nummer blockiert wird.|
|[Telefone im öffentlichen Bereich](set-up-common-area-phones.md) <br/> | Ein Telefon im öffentlichen Bereich wird normalerweise in einem Bereich wie einer Lobby oder einem Konferenzraum bereitgestellt, wodurch es für mehrere Personen verfügbar ist. Telefone im öffentlichen Bereich sind als Geräte und nicht als Benutzer eingerichtet und können sich automatisch bei einem Netzwerk anmelden.|
|[Unterstützung für medienumgehung](direct-routing-plan-media-bypass.md) (nur für Teams, die nur Direktes Routing durchführen) <br/> | Um die Leistung zu verbessern, werden Medien zwischen dem Session Border Controller (SBC) und dem Client aufbewahrt, anstatt Sie über das Microsoft Phone-System zu senden. |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>Verfügbarkeit in gcc-und DoD-Wolken
<a name="bkmk_setup"> </a>

Die folgenden Funktionen stehen in den Clouds für gcc-höchst-und DoD-Wolken noch nicht zur Verfügung. 
- [Anrufeinstellungen für sekundäre Klingeltöne, Voicemail und erweiterte Delegierung](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Übertragung an Voicemail Mid-Anruf](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Telefonnummer von der Suchleiste anrufen
- Wartemusik
- Azure AD Reverse Number Lookup

## <a name="related-topics"></a>Verwandte Themen

- [Was ist das Telefonsystem?](what-is-phone-system-in-office-365.md)
- [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md)
- [Einrichten des Telefonsystems](setting-up-your-phone-system.md)
- [Welcher Anrufplan ist für Sie am besten geeignet?](calling-plan-landing-page.md)
- [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md)
- [Überwachen und Verwalten der Anrufqualität](monitor-call-quality-qos.md)
- [Lizenzierung für Microsoft Teams-Add-On](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Preise für das Telefonsystem](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams für virtualisierte Desktop Infrastruktur mit anrufen und Besprechungen](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

  
 

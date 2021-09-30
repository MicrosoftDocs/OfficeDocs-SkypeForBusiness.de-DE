---
title: Erfahren Sie, was Ihnen das Telefonsystem bietet
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Hier erhalten Sie Informationen zu den Features, der Verfügbarkeit und erfahren, wie Sie Microsoft-Telefon System für Ihr Unternehmen planen und einrichten. '
ms.openlocfilehash: 6784018e9bda245ab162b68cae88ef69ac15238f
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012969"
---
# <a name="heres-what-you-get-with-phone-system"></a>Erfahren Sie, was Ihnen das Telefonsystem bietet

In diesem Artikel werden Telefonsystem beschrieben. Weitere Informationen zur Verwendung von Telefonsystem als Ersatz für Private Branch Exchange (PBX) und Optionen zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz finden Sie unter Was ist [Telefonsystem](what-is-phone-system-in-office-365.md).

Clients sind für PC, Mac und mobile Geräte verfügbar, die Features auf Geräten von Tablets und Mobiltelefonen bis zu PCs und IP-Desktoptelefonen bieten. Weitere Informationen finden Sie unter [Kunden für Microsoft Teams.](get-clients.md)

 > [!Note]
> Details zu telefon Teams auf unterschiedlichen Plattformen finden Sie unter Teams [von Features nach Plattform.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

Damit Sie Telefonsystem verwenden können, muss Ihre Organisation über eine Lizenz Telefonsystem verfügen. Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft Teams-Add-On-Lizensierung](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Beachten Sie, dass für die meisten Features die Zuweisung der Telefonsystem und die Sicherstellung erforderlich ist, dass Benutzer "sprachfähig" sind. Verwenden Sie zum Zuweisen der Lizenz das [Cmdlet Set-CsUser,](/powershell/module/skype/set-csuser?view=skype-ps) und legen Sie den **Parameter enterprisevoiceenabled** auf $true. Einige Features, z. B. die automatische Telefon attendant in der Cloud, erfordern nicht, dass ein Benutzer sprachfähig ist. Ausnahmen werden in der folgenden Tabelle genannt.
  
## <a name="phone-system-features"></a>Telefonsystem features

Telefonsystem bietet die folgenden Features. Sofern nicht anders angegeben, stehen Features sowohl in der Online Teams als Skype for Business zur Verfügung.
  
|Telefonsystem feature  |Beschreibung |
|:-----|:-----|
|[Automatische Cloud-Attendants](what-are-phone-system-auto-attendants.md)  |Ermöglicht es Ihnen, ein Menüsystem zu erstellen, das es externen und internen Anrufern ermöglicht, Anrufe zu suchen und zu platzieren oder Anrufe an Unternehmensbenutzer oder Abteilungen in Ihrer Organisation zu übertragen.  <br/> Beachten Sie, *dass Benutzer für* den Empfang von Anrufen von der automatischen Telefon attendant nicht sprachfähig sein müssen. |
|[Cloudanrufwarteschleifen](create-a-phone-system-call-queue.md) <br> |Mit dieser Option können Sie konfigurieren, wie Anrufwarteschleifen für Ihre Organisation verwaltet werden: z. B. Begrüßungen und Musik in der Warteschleife einrichten, nach dem nächsten verfügbaren Telefonanrufmitarbeiter suchen, um den Anruf zu verarbeiten, und so weiter.  <br/> Beachten Sie, *dass Benutzer sprachfähig* sein müssen, um Anrufe aus einer Anrufwarteschleife empfangen zu können.|
|Wartemusik | Gibt die vom Dienst definierte Standardmusik wieder, wenn ein externer Anruf über das Telefonnetz (Public Switched Telephone Network, PSTN) im Halteraum platziert wird. Dieses Feature funktioniert sowohl bei Anrufen, die an eine Anrufwarteschlange gemacht werden als auch bei 1:1-PSTN-zu-Teams-Anrufen. Dieses Feature bietet eine Halten-Benachrichtigungsparität zu anderen Plattformen. Dieses Feature kann vom Administrator konfiguriert werden, [derzeit jedoch nur über PowerShell.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) Das Halten von Musik wird auch bei der durch die Durchsetzung eines PSTN-Anrufs unterstützten Funktion nicht unterstützt.|
|Anruf annehmen/initiieren (nach Name und Nummer)   |Ermöglicht Es Benutzern, eingehende Anrufe per Touchanruf zu beantworten und ausgehende Anrufe entweder durch Wählen der vollständigen Telefonnummer oder durch Klicken auf einen Namen im Client zu platzieren.   |
|[Anruf weiterleitungsoptionen und gleichzeitiges Anrufen](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |Ermöglicht Benutzern das Einrichten von Weiterleitungsregeln, damit Anrufe überall hin gehen können oder Anrufe an Kollegen oder an Voicemail weitergeleitet werden können.   |
|[Abholen und Weiterleiten von Gruppenanrufen an eine Gruppe](call-sharing-and-group-call-pickup.md)  | Ermöglicht Es Benutzern, eingehende Anrufe mit Kollegen zu teilen, damit die Kollegen Anrufe beantworten können, die während der Benutzer verfügbar sind. Weniger störend für Empfänger als andere Arten der Anruffreigabe (wie Anruf weiterleitung oder gleichzeitiges Klingeln), da Benutzer konfigurieren können, wie sie über einen eingehenden freigegebenen Anruf benachrichtigt werden möchten. |
|[Durch übertragen eines Anrufs und durch durch eine Weisungsüberweisung](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |Hiermit können Benutzer Anrufe an eine andere Person durchträgt. Oder wenn sie das Büro verlassen müssen, die Unterhaltung aber fortsetzen möchten, können sie die Anrufe von ihrem PC oder IP-Telefon auf ihr Mobiltelefon übertragen.  <br/> Beachten Sie, *dass Benutzer nicht sprachfähig* sein müssen, um übertragene Anrufe von einem anderen Benutzer empfangen zu können. |
|[Übertragung an Voicemail im Gespräch*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | Ermöglicht Benutzern das Übertragen von Nachrichten an die Voicemail während eines Anrufs. |
|[Parken von Anrufen und Holen](call-park-and-retrieve.md)   | Ermöglicht Benutzern das Halten eines Anrufs im Teams-Dienst in der Cloud. Wenn ein Anruf geparkt wird, generiert der Dienst einen eindeutigen Code für den Anrufabruf. Der Benutzer, der den Anruf geparkt hat, oder eine andere Person kann dann diesen Code und eine unterstützte App oder ein unterstütztes Gerät verwenden, um den Anruf abzurufen.  |
|Telefonnummer über Suche anrufen   | Ermöglicht Benutzern das Anrufen über das Suchfeld, indem sie den Befehl /call verwenden und einen Namen oder eine Nummer angeben.  |
|[Anrufer-ID](how-can-caller-id-be-used-in-your-organization.md)   |Bei Anrufen innerhalb des Unternehmens wird eine detaillierte Anrufer-ID angezeigt, die Informationen aus dem Unternehmensverzeichnis abruft, mit Bild-ID und Stellenbetitel anstelle nur einer Telefonnummer. Bei Anrufen von externen Telefonnummern wird die vom Telefondienstanbieter bereitgestellte Anrufer-ID angezeigt. Wenn es sich bei den externen Telefonnummern um Sekundärnummern im Unternehmensverzeichnis handelt, werden die Informationen aus dem Unternehmensverzeichnis angezeigt.   |
|Gerät wechseln   |Ermöglicht Benutzern die Wiedergabe eines Anrufs oder einer Besprechung auf einem anderen HID-Gerät, das mit Teams; z. B. umschalten von den PC-Lautsprechern auf ein Headset.    |
|Anwesenheitsbasierte Anrufrouting  |Steuert die eingehende Kommunikation mit den Anwesenheitsinformationen, wodurch der Benutzer die gesamte eingehende Kommunikation mit Ausnahme der speziell angegebenen blockieren kann.   |
|[Integrierte Wählta pad](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | Ermöglicht Benutzern das Anrufen nach Name oder Nummer an einer beliebigen Stelle in der Suchleiste und auf der Wähltaste, wodurch ausgehende Anrufe beschleunigt werden.  |
|Verbundrufe   |Ermöglicht Benutzern sichere Verbindungen, Kommunikation und Zusammenarbeit mit Benutzern in Partner mandants.   |
|[Anrufen und Empfangen eines Videoanrufs](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | Wenn das Konto des Benutzers für Videoanrufe aktiviert ist, kann der Benutzer Videoanrufe mit seinen Kontakten telefonieren. Alles, was sie benötigen, ist eine Kamera, die Lautsprecher und das Mikrofon ihres Computers. Benutzer können auch ein Headset verwenden, wenn ihr Computer nicht über ein integriertes Audiogerät verfügt. |
|[Cloud-Voicemail](set-up-phone-system-voicemail.md)  | Wenn ein Benutzer eine Voicemail erhält, wird sie als E-Exchange mit der Voicemail-Nachricht als Anlage an sein Postfach zugestellt. Benutzer können ihre Nachrichten auf ihrem zertifizierten Desktoptelefon und in allen Teams oder Skype for Business hören. Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. <br> Beachten Sie, dass Benutzer *weder* eine  Telefonsystem-Lizenz benötigen noch über Sprachfunktionen verfügen müssen, Cloud-Voicemail nutzen zu können.    |
|[Cloud-Voicemail von Benutzereinstellungen](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Ermöglicht Benutzern die Konfiguration ihrer Clienteinstellungen für Voicemail-Begrüßungen, Anrufbeantwortungsregeln und die Begrüßungssprache, einschließlich Außer-Office-Begrüßungen. <br> Beachten Sie, dass Benutzer *weder* eine  Telefonsystem-Lizenz benötigen noch über Sprachfunktionen verfügen müssen, Cloud-Voicemail nutzen zu können.  |
|[Sekundärer Klingelton](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | Benutzer mit mehreren an ihren PC angeschlossenen Lautsprechern können zusätzlich zum Standardlautsprecher ein sekundäres Gerät zum Klingeln festlegen. Beispielsweise kann ein Benutzer mit einem an den PC und den Schreibtischlautsprechern angeschlossenen Headset und Schreibtischlautsprecher wählen, dass beim Ein-/Ein-Anruf sowohl Das Headset als auch der Lautsprecher klingeln, damit er keinen Anruf verpasst.  |
|[Benachrichtigungen bei unterschiedlichen](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) Klingeln (Teams) |Ermöglicht Benutzern die Auswahl separater Klingeltöne für normale, weitergeleitete und delegierte Anrufe, um die Art des Anrufs unterscheiden zu können.   |
|[Funktion "Gemeinsame Leitungen"](shared-line-appearance.md)  | Ermöglicht Benutzern das Teilen ihrer Telefonleitung, sodass ein anderer Benutzer in ihrem Namen Anrufe erstellen und empfangen kann.|
|[Beschäftigt (nur](teams-calling-policy.md) Teams)  | Eine Anrufrichtlinie, mit der Sie konfigurieren können, wie eingehende Anrufe verarbeitet werden, wenn ein Benutzer: <ul><li>in einem Anruf </li><li>in einer Konferenz</li><li>einem Anruf in der Warteschleife platziert wurde. </li></ul> Der Anrufer erhält eine der folgenden Antworten: <ul><li>Ein beschäftigtes Signal hören, wenn der Anrufer am Telefon ist</li> <li>werden entsprechend den nicht beantworteten Einstellungen des Benutzers geroutet. Mit einer Option kann der Anrufer eine Voicemail für den Benutzer hinterlassen, der bereits an einem Anruf ist.</li></ul> Der Anrufer erhält eine Benachrichtigung über einen verpassten Anruf, kann jedoch keine eingehenden Anrufe entgegenrufen. Dieses Feature ist standardmäßig deaktiviert, kann aber vom Mandantenadministrator aktiviert werden.|
|[Anrufblockierung](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Ermöglicht Benutzern das Hinzufügen von Telefonnummern (PSTN) zu einer Liste blockierter Telefonnummern, sodass der nächste Anruf von dieser Nummer an den Benutzer blockiert wird.|
|[Telefone für häufig verwendeten Bereich](set-up-common-area-phones.md)  | Ein Telefon im allgemeinen Bereich befindet sich normalerweise in einem Bereich wie einem Wartebereich oder einem Konferenzraum, der für mehrere Personen zur Verfügung steht. Telefone in gängigen Flächen sind als Geräte und nicht als Benutzer eingerichtet und können sich automatisch bei einem Netzwerk anmelden.|
|[Unterstützung der Medienumgehung](direct-routing-plan-media-bypass.md) (nur Teams Direct-Routing)  | Um eine bessere Leistung zu erzielen, werden Medien zwischen Session Border Controller (SBC) und dem Client gehalten, anstatt sie über das Microsoft-Telefon-System zu senden. |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>Verfügbarkeit in GCC Hoch- und DoD-Wolken
<a name="bkmk_setup"> </a>

Die folgenden Funktionen sind in GCC und DoD Clouds noch nicht verfügbar. 

- [Anrufeinstellungen für sekundären Rufton, Voicemail und erweiterte Delegierung](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Übertragung an Voicemail im Gespräch](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Telefonnummer über Suchleiste anrufen
- Wartemusik
- Umgekehrte Azure AD-Zahlen-Suche

## <a name="related-topics"></a>Verwandte Themen

- [Was ist das Telefonsystem?](what-is-phone-system-in-office-365.md)
- [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md)
- [Einrichten des Telefonsystems](setting-up-your-phone-system.md)
- [Welcher Anrufplan ist für Sie am besten geeignet?](calling-plan-landing-page.md)
- [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md)
- [Überwachen und Verwalten der Anrufqualität](monitor-call-quality-qos.md)
- [Lizenzierung für Microsoft Teams-Add-Ons](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Preise für das Telefonsystem](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams virtualisierte Desktopinfrastruktur mit Anrufen und Besprechungen](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

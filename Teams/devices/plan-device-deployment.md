---
title: Planen der Bereitstellung für Teams und Anzeigen
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: tony.woodruff
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
search.appverid: MET150
description: Dieser Artikel enthält eine Übersicht über die Aufgaben und Schritte zum Bereitstellen Teams Telefonen und anzeigen in Ihrer Organisation.
ms.openlocfilehash: 2ad9840d6ebd1ac6973027dedf6be294704f5326
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2021
ms.locfileid: "61577795"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Planen der Bereitstellung für Teams und Anzeigen

Eine erfolgreiche Bereitstellung von Teams-Geräten und Teams-Displays beginnt mit der Planung. In diesem Artikel werden Sie durch die Aufgaben und Schritte zum Bereitstellen dieser Geräte in Ihrer Organisation erläutert. Es enthält außerdem Anleitungen zur Gerätenutzung, -lizenzierung, -integration in Ihre Umgebung, Touchpoints und -verwaltung.

> [!TIP]
> [Der Microsoft 365 Adoption Hub](https://adoption.microsoft.com/) ist ein hervorragender Ort für die ersten Schritte bei der Einführung Microsoft Teams.

## <a name="task-1-what-are-your-deployment-objectives"></a>Aufgabe 1: Was sind Ihre Bereitstellungsziele?

Die Planung des Rollouts Teams Telefonen und Anzeigen in Ihrer Organisation beginnt mit ihren Bereitstellungszielen. Teams-Geräte unterstützen Hybridarbeit in Besprechungsräumen, Büros und anderen Funktionsräumen. Sie müssen bestimmen, wo und von wem diese Geräte verwendet werden.

### <a name="objective-identify-your-device-personas"></a>Ziel: Identifizieren Der Personas Ihres Geräts

Teams für Smartphones und Displays passen auf eine von zwei Personen: 

- Persönliche Geräte
- Geräte mit gemeinsam genutzten Speicherplatz

Persönliche und gemeinsam genutzte Geräte haben unterschiedliche Rollen und Nutzungen. 

**Persönliche Geräte:** 

- Normalerweise einem Benutzer zugewiesen, mit dem Konto dieses Benutzers angemeldet und mit einer Teams für den Zugriff auf den Dienst aktiviert.
- Denken Sie an persönliche Geräte mit einer 1:1-Beziehung mit einem Gerät pro Benutzer.
- Kann mit dem Desktopclient des Teams gekoppelt werden und Features wie "Better Together" verwenden
- Kann mit einem Headset verbunden sein, verkabelt oder drahtlos
- Weitere Funktionen auf persönlichen Geräten sind "Hot-King" und "Startbildschirm". 

**Geräte mit gemeinsam genutzten Geräten:**

- Führen Sie eine bestimmte Funktion aus, z. B. ein Telefon in einem gemeinsamen Bereich oder ein Besprechungsraumgerät, und benötigen Sie für den Zugriff auf den Dienst eine dedizierte Konto- und Featurelizenz.
- Stellen Sie sich geteilte Geräte wie eine 1:n-Beziehung vor: ein Gerät, das von vielen Benutzern gemeinsam genutzt wird.
- Bereitstellung in gemeinsam genutzten Räumen wie Besprechungsräumen, Empfangsbereichen oder Fertigungsräumen. 
- Die Benutzeroberflächen der Benutzer (UI) sind spezifisch für ihre Funktion, z. B. Gemeinsame Fläche Telefon-UI oder Besprechungsraum-UI, sind von der Funktion und Platzierung des gemeinsam genutzten Geräts abhängig.
- Erfordern Sie eine Konfiguration und optionales Ab fest, um sicherzustellen, dass Die Einstellungen nicht geändert werden, oder um zu verhindern, dass sich das Konto ab- oder abschreibt. 
- Weitere Features auf Geräten mit gemeinsam genutzten Speicherplatz umfassen die Suche auf Handys in der Nähe und Hot-King mit Leerlauftimeout.

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>Ziel: Wie viele Geräte für persönlichen und gemeinsam genutzten Speicherplatz benötigen Sie?

Nachdem Sie nun die Gerätepersonas identifiziert haben, müssen Sie bestimmen, welche zertifizierten Geräte Sie verwenden möchten und wie viele davon Sie benötigen. Damit Sie diese Entscheidung treffen können, stellen Sie sich die folgenden Fragen: 

- Wie viele persönliche Geräte sind erforderlich, und wer wird eines haben?
- Wie viele Räume oder Räume benötigen gemeinsam genutzte Geräte? Wird jeder Raum den gleichen Gerätetyp haben? 
- Müssen Ihre Geräte bestimmte Anforderungen erfüllen?
    - Beispiele hierfür sind Bildschirmgröße, Formfaktor und Hersteller oder Modell? Eine Liste der zertifizierten Telefone und Anzeigen finden Sie unter Microsoft Teams [zertifizierten Geräten.](teams-ip-phones.md)
-  Benötigen Sie Telefone Teams oder Teams Anzeigen? Eine Liste der von Teams-Telefonen unterstützten Features finden Sie unter Telefone für [Microsoft Teams](phones-for-teams.md#features-supported-by-teams-phones) und eine Liste der von den Teams unterstützten Features finden Sie unter anzeigen [Microsoft Teams](teams-displays.md#features-supported-by-teams-displays).
- Verfügen Sie über genügend Geräte für neue Benutzer oder einen Prozess für neue Bestellungen und Lieferung?
- Stehen Ihnen Ersatzgeräte zur Wartung oder im Falle von Hardwareproblemen zur Verfügung? Die Möglichkeit, ein Gerät schnell zu tauschen, verhindert Unterbrechungen der Benutzererfahrung.

## <a name="task-2-what-are-your-licensing-requirements"></a>Aufgabe 2: Was sind Ihre Lizenzierungsanforderungen? 

Nun wissen Sie, wie viele Geräte Sie benötigen. Im nächsten Schritt wird ermittelt, wie viele Lizenzen benötigt werden. Teams Telefonen und Anzeigen benötigen Lizenzen für den Zugriff auf Microsoft Teams und Microsoft 365.

Für geteilte und persönliche Geräte ist eine andere Lizenzierung nötig. Für persönliche Geräte können Lizenzen verwendet werden, die Benutzerkonten zugewiesen sind. Gemeinsam genutzte Geräte benötigen für ihre Funktion spezifische Lizenzen. Bei Smartphones und Displays sind die entsprechenden Lizenzen die gemeinsame [Telefon](../set-up-common-area-phones.md#step-1---buy-the-licenses) für Microsoft Teams und [die Microsoft Teams-Räume Standard Lizenz.](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices)

Weitere Informationen und Vergleiche Ihrer Lizenzierungsoptionen finden Sie unter [Microsoft 365 Lizenzierungspläne.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 

## <a name="task-3-what-are-your-dependencies"></a>Aufgabe 3: Wie sind Ihre Abhängigkeiten? 

### <a name="objective-plan-your-device-identities"></a>Ziel: Planen der Geräteidentitäten

Identitäten ermöglichen Geräten den Zugriff auf Microsoft 365 Dienste, und sie sollten das Erkennen, Verwalten und Herstellen einer Verbindung mit Geräten innerhalb Ihrer Organisation erleichtern. Berücksichtigen Sie bei der Planung von Geräteidentitäten die folgenden Punkte:

- Benutzerprinzipalnamen und deren Format und Domäne
- Anzeigenamen
- Aufwendbarkeit des Adressbuchs
- Gerätetypen "Persönlich" im Vergleich zu "gemeinsam genutzter Speicherplatz"
- Gruppen- und Benutzerlizenzierung

### <a name="objective-review-conditional-access-policies"></a>Ziel: Richtlinien für bedingten Zugriff überprüfen

Azure Active Directory Richtlinien für bedingten Zugriff sind zusätzliche Anforderungen, die erfüllt sein müssen, bevor ein Gerät angemeldet werden kann.

Während der Planung der Bereitstellung

- Überprüfen Sie vorhandene Richtlinien für bedingten Zugriff, die sich auf Ihre Teams und Anzeigen auswirken können. Dazu können Sie im Azure AD Admin Center das [Tool "Was](/azure/active-directory/conditional-access/what-if-tool) wäre wenn" und [Anmeldeprotokolle verwenden.](/azure/active-directory/reports-monitoring/concept-sign-ins)

- Planen neuer Regeln bei Bedarf

- Verwenden Sie Funktionen für bedingten Zugriff wie Gerätefilter, um Regeln auf Teams und Anzeigen anzuwenden.

>[!NOTE]
>Es gibt einige Richtlinien für bedingten Zugriff, die von Android-Geräten nicht unterstützt werden. Anleitungen und bewährte Methoden finden Sie unter Android-Geräte unter Bewährte Methoden für die Authentifizierung [Teams Android-Geräten.](authentication-best-practices-for-android-devices.md)

## <a name="task-4-prepare-your-environment"></a>Aufgabe 4: Vorbereiten der Umgebung

### <a name="objective-plan-network-basics"></a>Ziel: Planen der Netzwerkgrundfunktionen

Teams Telefon-Geräten und Anzeigen benötigen Zugriff auf das Internet, um eine Verbindung mit Teams und Funktion wie beabsichtigt herzustellen. Beachten Sie die folgenden Punkte, um Ihr Netzwerk für die Bereitstellung vorbereitet zu machen:

- Verfügt Ihre Netzwerkinfrastruktur über ausreichend Kapazität? Erwägen Sie, Ports, Funkzugriffspunkte und andere Abdeckungen zu wechseln.
- Ist die Größe Ihrer Bereiche bei Verwendung von ROUTERNs und DHCP entsprechend?
- Bewerten und testen Sie Netzwerkpfade von dem Ort aus, an dem Geräte für die Microsoft 365. 
- Öffnen Sie die erforderlichen Firewallports und URLs Microsoft 365 Anleitungen.
- Überprüfen und testen Sie die E911-Anforderungen und -Konfiguration auf Standortgenauigkeit und Compliance. 
- Vermeiden Sie die Verwendung eines Proxyservers, und optimieren Sie Medienpfade aus Zuverlässigkeit und Qualität.

### <a name="objective-physical-considerations"></a>Ziel: Physische Überlegungen

Berücksichtigen Sie die physischen Bereiche, an Teams Ihre Telefone und Anzeigen verwendet werden.

Zu den Hauptaspekten gehören:

- **Leistung:** Verfügen Sie über genügend Elektrische Steckdosen? Wie nahe können Sie das Gerät an einer Steckdose positionieren, wenn für das Gerät eine externe Stromquelle benötigt wird?
- **Platzierung des Geräts:** Wo wird Ihr Gerät physisch sein? Schreibtischständer, Wandhalter und sonstiges Zubehör des Originalgeräteherstellers (OEM).
- **Sicherheit:** Muss Ihr Gerät an bestimmten Plätzen gesperrt sein?
- **Barrierefreiheit:** Erfüllt das Gerät die Anforderungen des primären Benutzers an die Barrierefreiheit? Überlegen Sie, wo das Handy platziert, wie lange das Kabel ist und wo die Benutzerfreundlichkeit des Handys oder Headsets liegt.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>Aufgabe 5: Wie werden bereitgestellte Geräte verwaltet?

Teams telefonieren und Anzeigen werden von zwei bis drei Microsoft 365 Portalen und den entsprechenden PowerShell-Modulen verwaltet: 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory Admin Center

Verwalten des Azure AD Admin Centers

- Alle identitätsbezogenen Aufgaben für Teams und Anzeigen
- Richtlinien für bedingten Zugriff 
- Kennwortzurücksetzungen

#### <a name="teams-admin-center"></a>Teams Admin Center

Verwalten des Teams Admin Centers

- [Geräteeinstellungen für Teams](../business-voice/manage-devices.md)
- [Konfigurationsprofile](device-management.md#use-configuration-profiles-in-teams)
- [Gerätetags](manage-device-tags.md)
- [Remote-An- und Abmelden](remote-sign-in-and-sign-out.md)
- Anrufanalyse  
- Firmware
- Problembehandlung und Herunterladen von Protokollen

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Endpoint Manager Admin Center (wenn Sie Intune für die Geräteverwaltung verwenden)

Verwenden Sie Endpoint Manager Admin Center, um dies zu verwalten: 

- Richtlinien zur Gerätekonformität
- Registrierungseinschränkungen
- Unternehmensgeräte-IDs
- Gerätefilter

---
title: Planen der Bereitstellung für Teams-Telefongeräte und -Displays
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
description: Dieser Artikel enthält eine Übersicht über die Aufgaben und Schritte zum Bereitstellen von Teams-Telefonen und -Anzeigen in Ihrer Organisation.
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.openlocfilehash: 5172d230823088141c58e3d2b58e1c3b579268b3
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272390"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Planen der Bereitstellung für Teams-Telefongeräte und -Displays

Eine erfolgreiche Bereitstellung von Teams-Telefongeräten und Teams-Displays beginnt mit der Planung. In diesem Artikel werden Sie durch die Aufgaben und Schritte zum Bereitstellen dieser Geräte in Ihrer Organisation geführt. Darüber hinaus bietet es Anleitungen zur Gerätenutzung, Lizenzierung, Integration in Ihre Umgebung, Touchpoints und Verwaltung.

> [!TIP]
> [Der Microsoft 365 Adoption Hub](https://adoption.microsoft.com/) ist ein großartiger Ort, um mit Microsoft Teams auf Ihrer Einführungsreise zu beginnen.

## <a name="task-1-what-are-your-deployment-objectives"></a>Aufgabe 1: Was sind Ihre Bereitstellungsziele?

Die Planung des Rollouts von Teams-Telefonen und -Displays in Ihrer Organisation beginnt mit Ihren Bereitstellungszielen. Teams-Geräte unterstützen hybride Arbeit in Besprechungsräumen, Büros und anderen Funktionsbereichen. Sie müssen bestimmen, wo diese Geräte verwendet werden und von wem.

### <a name="objective-identify-your-device-personas"></a>Ziel: Identifizieren Von Gerätepersonas

Teams-Telefone und -Displays passen zu einer von zwei Personen: 

- Persönliche Geräte
- Geräte mit gemeinsamem Speicherplatz

Persönliche und freigegebene Geräte weisen unterschiedliche Rollen und Verwendungen auf. 

**Persönliche Geräte:** 

- In der Regel einem Benutzer zugewiesen, mit dem Konto dieses Benutzers angemeldet und mit einer Teams-Featurelizenz für den Zugriff auf den Dienst aktiviert.
- Stellen Sie sich für persönliche Geräte eine 1:1-Beziehung mit einem Gerät pro Benutzer vor.
- Kann mit dem Teams-Desktopclient gekoppelt werden und Features wie "Better Together" verwenden
- Kann eine Verbindung mit einem Headset, kabelgebundenen oder drahtlosen Verbindungen herstellen
- Weitere Features auf persönlichen Geräten sind hot-desking und Home Screen. 

**Geräte mit gemeinsamem Speicherplatz:**

- Führen Sie eine bestimmte Funktion aus, z. B. ein Telefon- oder Besprechungsraumgerät im einheitlichen Bereich, und benötigen Sie ein dediziertes Konto und eine Featurelizenz, um auf den Dienst zugreifen zu können.
- Stellen Sie sich für freigegebene Geräte eine 1:n-Beziehung vor: ein Gerät, das von vielen Benutzern gemeinsam genutzt wird.
- Wird in gemeinsam genutzten Räumen wie Besprechungsräumen, Empfangsbereichen oder Fertigungsbereichen bereitgestellt. 
- Ihre Benutzeroberflächen sind spezifisch für ihre Funktion, z. B. die Benutzeroberfläche für Telefone für gemeinsame Bereiche oder die Benutzeroberfläche des Besprechungsraums, hängen von der Funktion und Platzierung des gemeinsam genutzten Geräts ab.
- Erfordert Konfiguration und optionale Härtung, um sicherzustellen, dass die Einstellungen nicht geändert werden, oder um zu verhindern, dass sich das Konto abmeldet. 
- Zu den zusätzlichen Features auf Geräten mit gemeinsamem Speicherplatz gehören die Suche auf Telefonen im einheitlichen Bereich und das Warmabblenden mit Leerlauftimeout.

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>Ziel: Wie viele persönliche und freigegebene Speicherplatzgeräte benötigen Sie?

Nachdem Sie Ihre Gerätepersonas identifiziert haben, müssen Sie ermitteln, welche zertifizierten Geräte Sie verwenden möchten und wie viele davon Sie benötigen. Wenn Sie diese Entscheidung treffen möchten, sollten Sie die folgenden Fragen berücksichtigen: 

- Wie viele persönliche Geräte sind erforderlich und wer hat eines?
- Wie viele Räume oder Räume erfordern gemeinsam genutzte Geräte? Verfügt jeder Speicherplatz über denselben Gerätetyp? 
- Müssen Ihre Geräte bestimmte Anforderungen erfüllen?
    - Beispiele hierfür sind Bildschirmgröße, Formfaktor und Hersteller oder Modell? Eine Liste der zertifizierten Telefone und Displays finden Sie unter [Microsoft Teams-zertifizierte Geräte](teams-ip-phones.md).
-  Benötigen Sie Teams-Telefone oder Teams-Displays? Eine Liste der von Teams-Telefonen unterstützten Features finden Sie unter ["Telefone für Microsoft Teams](phones-for-teams.md#features-supported-by-teams-phones) ", und eine Liste der von Teams-Displays unterstützten Features finden Sie in den [Microsoft Teams-Anzeigen](teams-displays.md#features-supported-by-teams-displays).
- Verfügen Sie über genügend Geräte für neue Benutzer oder einen Prozess für neue Bestellungen und Lieferungen?
- Stehen Ihnen Ersatzgeräte zur Wartung oder bei Hardwareproblemen zur Verfügung? Die Möglichkeit, ein Gerät schnell auszutauschen, verhindert Unterbrechungen der Benutzeroberfläche.

## <a name="task-2-what-are-your-licensing-requirements"></a>Aufgabe 2: Was sind Ihre Lizenzierungsanforderungen? 

Jetzt wissen Sie, wie viele Geräte Sie benötigen. Der nächste Schritt besteht darin, zu ermitteln, wie viele Lizenzen benötigt werden. Teams-Telefone und -Anzeigen erfordern Lizenzen für den Zugriff auf Microsoft Teams und Microsoft 365.

Freigegebene und persönliche Geräte benötigen eine andere Lizenzierung. Für persönliche Geräte können Lizenzen verwendet werden, die Benutzerkonten zugewiesen sind. Freigegebene Geräte benötigen Lizenzen, die für ihre Funktion spezifisch sind. Für Telefone und Displays sind die anwendbaren Lizenzen [die Common Area Phone-Lizenz für Microsoft Teams](../set-up-common-area-phones.md#step-1---buy-the-licenses) und [die Microsoft Teams-Räume Standard-Lizenz](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices).

Weitere Informationen und zum Vergleichen Ihrer Lizenzierungsoptionen finden Sie unter [Microsoft 365-Lizenzierungspläne](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1). 

## <a name="task-3-what-are-your-dependencies"></a>Aufgabe 3: Was sind Ihre Abhängigkeiten? 

### <a name="objective-plan-your-device-identities"></a>Ziel: Planen der Geräteidentitäten

Identitäten ermöglichen Geräten den Zugriff auf Microsoft 365-Dienste, und sie sollten das Auffinden, Verwalten und Verbinden von Geräten innerhalb Ihrer Organisation vereinfachen. Berücksichtigen Sie dazu bei der Planung von Geräteidentitäten Folgendes:

- Benutzerprinzipalnamen und deren Format und Domäne
- Anzeigenamen
- Auffindbarkeit des Adressbuchs
- Gerätetypen für persönlichen und gemeinsam genutzten Speicherplatz
- Gruppen- und Benutzerlizenzierung

### <a name="objective-review-conditional-access-policies"></a>Ziel: Überprüfen von Richtlinien für bedingten Zugriff

Azure Active Directory-Richtlinien für bedingten Zugriff sind zusätzliche Anforderungen, die erfüllt sein müssen, bevor ein Gerät angemeldet werden kann.

Während der Planung der Bereitstellung

- Überprüfen Sie vorhandene Richtlinien für bedingten Zugriff, die sich auf Ihre Teams-Telefone und -Anzeigen auswirken können. Sie können dies im Azure AD Admin Center mithilfe des [Was-wäre-wenn-Tools](/azure/active-directory/conditional-access/what-if-tool) und der [Anmeldeprotokolle](/azure/active-directory/reports-monitoring/concept-sign-ins) tun.

- Planen neuer Regeln bei Bedarf

- Verwenden Sie Features für bedingten Zugriff wie Gerätefilter, um Regeln auf Teams-Telefone und -Displays anzuwenden.

>[!NOTE]
>Es gibt einige Richtlinien für bedingten Zugriff, die von Android-Geräten nicht unterstützt werden. Anleitungen und bewährte Methoden finden Sie unter Android-Geräte, siehe [bewährte Methoden für die Authentifizierung für Android-Geräte in Teams](authentication-best-practices-for-android-devices.md).

## <a name="task-4-prepare-your-environment"></a>Aufgabe 4: Vorbereiten der Umgebung

### <a name="objective-plan-network-basics"></a>Ziel: Planen der Grundlagen des Netzwerks

Teams Phone-Geräte und -Displays erfordern Zugriff auf das Internet, um eine Verbindung mit Teams herzustellen und wie beabsichtigt zu funktionieren. Um Ihr Netzwerk für die Bereitstellung vorzubereiten, sollten Sie Folgendes berücksichtigen:

- Verfügt Ihre Netzwerkinfrastruktur über genügend Kapazität? Ziehen Sie Switchports, drahtlose Zugriffspunkte und andere Abdeckungen in Betracht.
- Wenn Sie VLANs und DHCP verwenden, werden Ihre Bereiche entsprechend angepasst?
- Auswerten und Testen von Netzwerkpfaden, von wo aus Geräte in Microsoft 365 bereitgestellt werden. 
- Öffnen Sie die erforderlichen Firewallports und URLs für Microsoft 365 gemäß Anleitung.
- Überprüfen und testen Sie die E911-Anforderungen und -Konfiguration auf Standortgenauigkeit und Compliance. 
- Vermeiden Sie die Verwendung eines Proxyservers, und optimieren Sie Medienpfade für Zuverlässigkeit und Qualität.

### <a name="objective-physical-considerations"></a>Zielsetzung: Physische Überlegungen

Berücksichtigen Sie die physischen Räume, in denen Ihre Teams-Telefone und -Anzeigen verwendet werden.

Zu den wichtigsten Aspekten gehören

- **Macht:** Haben Sie genügend Steckdosen? Wie nah können Sie das Gerät an einer Steckdose positionieren, wenn das Gerät eine externe Stromquelle benötigt?
- **Geräteplatzierung:** Wo befindet sich Ihr Gerät physisch? Überprüfen Sie Schreibtischständer, Wandhalterungen und anderes Zubehör des Originalgeräteherstellers (OEM).
- **Sicherheit:** Muss Ihr Gerät an bestimmten Stellen gesperrt sein?
- **Zugänglichkeit:** Erfüllt das Gerät die Anforderungen an die Barrierefreiheit seines primären Benutzers? Überlegen Sie, wo sie platziert, drahtgebunden und handset- oder Headset-Nutzbarkeit ist.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>Aufgabe 5: Wie verwalten Sie bereitgestellte Geräte?

Teams-Telefone und -Displays werden von zwei bis drei Microsoft 365-Portalen und ihren jeweiligen PowerShell-Modulen verwaltet: 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory Admin Center

Verwenden des Azure AD Admin Center zum Verwalten

- Alle identitätsbezogenen Aufgaben für Teams-Telefone und -Displays
- Richtlinien für bedingten Zugriff 
- Kennwortzurücksetzungen

#### <a name="teams-admin-center"></a>Teams Admin Center

Verwenden des Teams Admin Center zum Verwalten

- [Geräteeinstellungen für Teams](../business-voice/manage-devices.md)
- [Konfigurationsprofile](device-management.md#use-configuration-profiles-in-teams)
- [Gerätetags](manage-device-tags.md)
- [Remoteanmeldung und -abmeldung](remote-sign-in-and-sign-out.md)
- Anrufanalyse  
- Firmware
- Problembehandlung und Herunterladen von Protokollen

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Endpoint Manager Admin Center (wenn Sie Intune für die Geräteverwaltung verwenden)

Verwenden Sie das Endpoint Manager Admin Center, um Folgendes zu verwalten: 

- Gerätekompatibilitätsrichtlinien
- Registrierungseinschränkungen
- Unternehmensgeräte-IDs
- Gerätefilter

---
title: Microsoft Teams-Räume Sicherheit
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Ihre Microsoft Teams-Räume Geräte schützen.
ms.openlocfilehash: 135e286ce255f097dc3751bc509c05fc94f2ffb2
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761097"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams-Räume Sicherheit

Microsoft arbeitet mit unseren Partnern zusammen, um eine sichere Lösung bereitzustellen, die keine zusätzlichen Aktionen erfordert, um Microsoft Teams-Räume zu sichern. In diesem Artikel werden viele der Sicherheitsfeatures beschrieben, die in Teams-Räume zu finden sind.

> [!NOTE]
> Microsoft Teams-Räume sollten nicht wie eine typische Endbenutzerarbeitsstation behandelt werden. Nicht nur die Anwendungsfälle unterscheiden sich erheblich, sondern auch die Standardsicherheitsprofile unterscheiden sich erheblich.
> Dieser Artikel bezieht sich auf Microsoft Teams-Räume Geräte, die auf Windows ausgeführt werden.

Begrenzte Endbenutzerdaten werden auf Teams-Räume gespeichert. Endbenutzerdaten können nur zur Problembehandlung und zur Unterstützung in den Protokolldateien gespeichert werden. Zu keinem Zeitpunkt kann sich ein Teilnehmer einer Besprechung mit Teams-Räume Dateien auf die Festplatte kopieren oder sich selbst anmelden. Es werden keine Endbenutzerdaten an das Microsoft Teams-Räume Gerät übertragen oder darauf zugegriffen.

Obwohl Endbenutzer keine Dateien auf einer Teams-Räume Festplatte ablegen können, ist Microsoft Defender weiterhin aktiviert. Teams-Räume Leistung wird mit Microsoft Defender getestet. Wenn Sie dies deaktivieren oder Endpunktsicherheitssoftware hinzufügen, kann dies zu unvorhersehbaren Ergebnissen und potenziellen Systembeeinträchtigungen führen.

## <a name="hardware-security"></a>Hardwaresicherheit

In einer Teams-Räume Umgebung gibt es ein zentrales Computemodul, das Windows 10 IoT Enterprise Edition ausgeführt wird. Jedes zertifizierte Computemodul muss über eine sichere Montagelösung, einen Sicherheitsschlösserplatz (z. B. Kensington-Sperre) und E/A-Port-Zugriffssicherheitsmaßnahmen verfügen, um die Verbindung nicht autorisierter Geräte zu verhindern. Sie können bestimmte Ports auch über die Unified Extensible Firmware Interface (UEFI)-Konfiguration deaktivieren.

Jedes zertifizierte Computemodul muss mit standardmäßig aktivierter Trusted Platform Module (TPM) 2.0-kompatibler Technologie ausgeliefert werden. TPM wird verwendet, um die Anmeldeinformationen für das Teams-Räume-Ressourcenkonto zu verschlüsseln.

Der sichere Start ist standardmäßig aktiviert. Der sichere Start ist ein Sicherheitsstandard, der von Mitgliedern der PC-Branche entwickelt wurde, um sicherzustellen, dass ein Gerät nur mit Software gestartet wird, die vom Originalgerätehersteller (OEM) als vertrauenswürdig eingestuft wird. Beim Starten des PCs überprüft die Firmware die Signatur der einzelnen Startsoftware, einschließlich UEFI-Firmwaretreibern (auch als Options-ROMs bezeichnet), EFI-Anwendungen und dem Betriebssystem. Wenn die Signaturen gültig sind, wird der PC gestartet, und die Firmware gibt dem Betriebssystem die Kontrolle. Weitere Informationen finden Sie unter ["Sicherer Start](/windows-hardware/design/device-experiences/oem-secure-boot)".

Der Zugriff auf UEFI-Einstellungen ist nur durch Anfügen einer physischen Tastatur und Maus möglich. Dadurch wird der Zugriff auf UEFI über die Teams-Räume Touch-fähige Konsole sowie alle anderen an Teams-Räume angeschlossenen Bildschirme mit Toucheingabe verhindert.

Kernel Direct Memory Access (DMA)-Schutz ist eine Windows 10 Einstellung, die auf Teams-Räume aktiviert ist. Mit diesem Feature schützen das Betriebssystem und die Systemfirmware das System vor böswilligen und unbeabsichtigten DMA-Angriffen für alle DMA-fähigen Geräte:

- Während des Startvorgangs.

- Gegen böswilliges DMA durch Geräte, die während der Betriebssystemlaufzeit an leicht zugängliche interne/externe DMA-fähige Ports wie M.2 PCIe-Steckplätze und Thunderbolt 3 angeschlossen sind.

Teams-Räume ermöglicht auch hypervisorgeschützte Codeintegrität (HVCI). Eines der von HVCI bereitgestellten Features ist Credential Guard. Credential Guard bietet die folgenden Vorteile:

- **Hardwaresicherheit** NTLM, Kerberos und Credential Manager nutzen die Vorteile der Plattformsicherheitsfeatures, einschließlich des sicheren Starts und der Virtualisierung, um Anmeldeinformationen zu schützen.

- **Virtualisierungsbasierte Sicherheit** Windows von NTLM und Kerberos abgeleiteten Anmeldeinformationen und anderen geheimen Schlüsseln werden in einer geschützten Umgebung ausgeführt, die vom ausgeführten Betriebssystem isoliert ist.

- **Besserer Schutz vor erweiterten beständigen Bedrohungen** Wenn Domänenanmeldeinformationen des Anmeldeinformations-Managers, von NTLM und Kerberos abgeleitete Anmeldeinformationen durch virtualisierungsbasierte Sicherheit geschützt werden, werden die Techniken und Tools für den Diebstahl von Anmeldeinformationen, die bei vielen gezielten Angriffen verwendet werden, blockiert. Schadsoftware, die im Betriebssystem mit Administratorrechten ausgeführt wird, kann geheime Schlüssel, die durch virtualisierungsbasierte Sicherheit geschützt sind, nicht extrahieren.

## <a name="software-security"></a>Softwaresicherheit

Nachdem Microsoft Windows gestartet wurde, melden Teams-Räume sich automatisch bei einem lokalen Windows Benutzerkonto mit dem Namen Skype an. Das Skype Konto besitzt kein Kennwort. Um die Skype Kontositzung sicher zu machen, werden die folgenden Schritte ausgeführt.

> [!IMPORTANT]
> Ändern Sie weder das Kennwort noch das lokale Skype Benutzerkonto. Dadurch kann verhindert werden, dass sich Teams-Räume automatisch anmelden.

Die Microsoft Teams-Räume-App wird mit dem Feature "Zugewiesener Zugriff" ausgeführt, das in Windows 10 1903 und höher zu finden ist. Zugewiesener Zugriff ist ein Feature in Windows 10, das die Anwendungseinstiegspunkte eingrenzt, die für den Benutzer verfügbar gemacht werden. Dies ermöglicht den Einzel-App-Kioskmodus. Mithilfe des Shell-Startfelds ist Teams-Räume als Kioskgerät konfiguriert, auf dem eine Windows Desktopanwendung als Benutzeroberfläche ausgeführt wird. Die Microsoft Teams-Räume-App ersetzt die Standardshell (explorer.exe), die normalerweise ausgeführt wird, wenn sich ein Benutzer anmeldet. Mit anderen Worten, die herkömmliche Explorer-Shell wird überhaupt nicht gestartet. Dadurch wird die Sicherheitsanfälligkeitsfläche Microsoft Teams-Räume innerhalb Windows erheblich reduziert. Weitere Informationen finden Sie unter [Konfigurieren von Kiosks und digitalen Schildern auf Windows Desktopeditionen](/windows/configuration/kiosk-methods).

Wenn Sie eine Sicherheitsüberprüfung oder einen Cis-Benchmark (Center for Internet Security) auf Teams-Räume ausführen, kann die Überprüfung nur im Kontext eines lokalen Administratorkontos ausgeführt werden, da das Skype Benutzerkonto keine anderen Anwendungen als die Teams-Räume-App unterstützt. Viele der Sicherheitsfeatures, die auf den Skype Benutzerkontext angewendet werden, gelten nicht für andere lokale Benutzer, und daher werden bei diesen Sicherheitsüberprüfungen nicht die vollständige Sicherheitssperre angezeigt, die auf das Skype Konto angewendet wird. Daher wird nicht empfohlen, eine lokale Überprüfung auf Teams-Räume auszuführen. Sie können jedoch externe Penetrationstests ausführen, wenn dies gewünscht ist. Aus diesem Grund wird empfohlen, externe Penetrationstests für Teams-Räume Geräte auszuführen, anstatt lokale Scans auszuführen.

Darüber hinaus werden Sperrrichtlinien angewendet, um die Verwendung nicht administrativer Features zu beschränken. Ein Tastaturfilter ist aktiviert, um potenziell unsichere Tastaturkombinationen abzufangen und zu blockieren, die nicht von Richtlinien für den zugewiesenen Zugriff abgedeckt werden. Nur Benutzer mit lokalen oder Domänenverwaltungsrechten dürfen sich bei Windows anmelden, um Teams-Räume zu verwalten. Diese und andere Richtlinien, die auf Windows auf Microsoft Teams-Räume Geräten angewendet werden, werden während des Produktlebenszyklus kontinuierlich bewertet und getestet.

## <a name="account-security"></a>Kontosicherheit

Teams-Räume Geräte enthalten ein Administratorkonto namens "Admin" mit einem Standardkennwort. Es wird dringend empfohlen, das Standardkennwort so schnell wie möglich zu ändern, nachdem Sie die Einrichtung abgeschlossen haben.

Das Admin Konto ist für den ordnungsgemäßen Betrieb von Teams-Räume Geräten nicht erforderlich und kann umbenannt oder sogar gelöscht werden. Bevor Sie das Admin Konto löschen, stellen Sie jedoch sicher, dass Sie ein alternatives lokales Administratorkonto einrichten, das konfiguriert wurde, bevor Sie das Konto entfernen, das mit Teams-Räume Geräten ausgeliefert wird. Weitere Informationen zum Ändern eines Kennworts für ein lokales Windows-Konto mithilfe von integrierten Windows-Tools oder PowerShell finden Sie in den folgenden Themen:

- [Ändern oder Zurücksetzen Ihres Windows Kennworts](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

Sie können auch Domänenkonten in die lokale Windows Administratorgruppe importieren. Sie können dies für Azure AD-Konten mithilfe von Intune tun. Weitere Informationen finden Sie unter [Richtlinien-CSP – RestrictedGroups.](/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!NOTE]
> Wenn Sie Crestron-Konsolen verwenden, müssen Sie auch das Admin Kennwort auf der Konsole sowie im Computemodul aktualisieren. Für weitere Informationen wenden Sie sich an Crestron.

> [!CAUTION]
> Wenn Sie das Admin Konto löschen oder deaktivieren, bevor Sie einem anderen lokalen oder Domänenkonto lokale Administratorberechtigungen erteilen, verlieren Sie möglicherweise die Möglichkeit, das Teams-Räume Gerät zu verwalten. In diesem Fall müssen Sie das Gerät wieder auf die ursprünglichen Einstellungen zurücksetzen und den Setupvorgang erneut abschließen.

Erteilen Sie keine lokalen Administratorberechtigungen für das Skype Benutzerkonto.

Windows Konfigurations-Designer kann verwendet werden, um Windows 10 Bereitstellungspakete zu erstellen. Neben dem Ändern des lokalen Admin Kennworts können Sie auch Aufgaben wie das Ändern des Computernamens und die Registrierung bei Azure Active Directory ausführen. Weitere Informationen zum Erstellen eines Windows Konfigurations-Designer-Bereitstellungspakets finden Sie unter [Bereitstellungspakete für Windows 10](/windows/configuration/provisioning-packages/provisioning-packages).

Sie müssen für jedes Teams-Räume Gerät ein Ressourcenkonto erstellen, damit es sich bei Teams anmelden kann. Sie können mit diesem Konto keine zweistufige oder mehrstufige Authentifizierung verwenden. Ein zweiter Faktor würde verhindern, dass sich das Konto nach einem Neustart automatisch bei der Teams-Räume-App anmeldet. Sie können die moderne Authentifizierung jedoch für zusätzliche Sicherheit für dieses Konto aktivieren. Darüber hinaus können Azure Active Directory Richtlinien für bedingten Zugriff und Intune Compliancerichtlinien bereitgestellt werden, um das Ressourcenkonto zu sichern. Weitere Informationen finden Sie unter ["Unterstützter bedingter Zugriff" und Intune Gerätekompatibilitätsrichtlinien für Microsoft Teams-Räume](supported-ca-and-compliance-policies.md) und [bedingten Zugriff sowie Intune Compliance für Microsoft Teams-Räume](conditional-access-and-compliance-for-devices.md)

Es wird empfohlen, das Ressourcenkonto möglichst in Azure AD zu erstellen. Während ein synchronisiertes Konto in Hybridbereitstellungen mit Teams-Räume arbeiten kann, haben diese synchronisierten Konten häufig Schwierigkeiten beim Anmelden bei Teams-Räume und können schwierig zu beheben sein. Wenn Sie einen Drittanbieter-Verbunddienst verwenden, um die Anmeldeinformationen für das Ressourcenkonto zu authentifizieren, stellen Sie sicher, dass der IDP eines Drittanbieters mit dem `wsTrustResponse` auf `urn:oasis:names:tc:SAML:1.0:assertion`festgelegten Attribut antwortet.

## <a name="network-security"></a>Netzwerksicherheit

Im Allgemeinen hat Teams-Räume die gleichen Netzwerkanforderungen wie jeder Microsoft Teams Client. Der Zugriff über Firewalls und andere Sicherheitsgeräte ist für Teams-Räume identisch wie bei jedem anderen Microsoft Teams-Client. Spezifisch für Teams-Räume müssen die Kategorien, die als "erforderlich" für Teams aufgeführt sind, in Ihrer Firewall geöffnet sein. Teams-Räume benötigt auch Zugriff auf Windows Update, Microsoft Store und Microsoft Intune (wenn Sie Microsoft Intune zum Verwalten Ihrer Geräte verwenden). Eine vollständige Liste der IPs und URLs, die für Microsoft Teams-Räume erforderlich sind, finden Sie unter:

- **Microsoft Teams** [Office 365 URLs und IP-Adressbereiche](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows Update** [Konfigurieren von WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store** [Voraussetzungen für Microsoft Store für Unternehmen und Bildung](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [Netzwerkendpunkte für Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Wenn Sie die Komponente Microsoft Teams-Räume verwalteten Dienste von Microsoft Teams-Räume Premium verwenden, müssen Sie auch sicherstellen, dass Teams-Räume auf die folgenden URLs zugreifen können:

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Teams-Räume ist so konfiguriert, dass es automatisch mit den neuesten Windows Updates, einschließlich Sicherheitsupdates, gepatcht bleibt. Teams-Räume installiert alle ausstehenden Updates jeden Tag ab 2:00 Uhr mithilfe einer vordefinierten lokalen Richtlinie. Es ist nicht erforderlich, zusätzliche Tools zum Bereitstellen und Anwenden Windows Updates zu verwenden. Die Verwendung zusätzlicher Tools zum Bereitstellen und Anwenden von Updates kann die Installation von Windows Patches verzögern und somit zu einer weniger sicheren Bereitstellung führen. Die Teams-Räume-App wird mithilfe der Microsoft Store bereitgestellt. Wenn Ihre Geräte mit Microsoft Teams-Räume Standard lizenziert sind, werden alle neuen Versionen der App während des nächtlichen Patchingvorgangs automatisch installiert. Wenn Ihre Geräte mit Microsoft Teams-Räume Premium lizenziert und im verwalteten Microsoft-Dienst registriert sind, werden neue Versionen der Teams-Räume-App gemäß Ihrem definierten Rolloutplan installiert.

Teams-Räume Geräte funktionieren mit den meisten 802.1X- oder anderen netzwerkbasierten Sicherheitsprotokollen. Wir können jedoch nicht Teams-Räume für alle möglichen Netzwerksicherheitskonfigurationen testen. Wenn daher Leistungsprobleme auftreten, die auf Netzwerkleistungsprobleme zurückverfolgt werden können, müssen Sie diese Protokolle möglicherweise deaktivieren, wenn sie in Ihrer Organisation konfiguriert sind.

Für eine optimale Leistung von Echtzeitmedien wird dringend empfohlen, Teams Mediendatenverkehr so zu konfigurieren, dass Proxyserver und andere Netzwerksicherheitsgeräte umgangen werden. Echtzeitmedien sind sehr latenzempfindlich, und Proxyserver und Netzwerksicherheitsgeräte können die Video- und Audioqualität der Benutzer erheblich beeinträchtigen. Da Teams Medien bereits verschlüsselt sind, hat die Weitergabe des Datenverkehrs über einen Proxyserver keinen spürbaren Vorteil. Weitere Informationen finden Sie unter [Networking up (to the cloud) – Ein Standpunkt des Architekten](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide), der Netzwerkempfehlungen zur Verbesserung der Leistung von Medien mit Microsoft Teams und Microsoft Teams-Räume diskutiert.

> [!IMPORTANT]
> Teams-Räume unterstützt keine authentifizierten Proxyserver.

Teams-Räume Geräte müssen keine Verbindung mit einem internen LAN herstellen. Erwägen Sie, Teams-Räume in einem sicheren Netzwerksegment mit direktem Internetzugang zu platzieren. Wenn Ihr internes LAN kompromittiert wird, werden die Angriffsvektorchancen für Teams-Räume reduziert.

Es wird dringend empfohlen, ihre Teams-Räume Geräte mit einem kabelgebundenen Netzwerk zu verbinden. Die Verwendung von Drahtlosnetzwerken auf Teams-Räume Geräten wird nicht empfohlen oder zertifiziert. Einige Konnektivitätsfeatures, z. B. Wi-Fi Sense, sind standardmäßig deaktiviert.

Proximity Join und andere Teams-Räume-Features basieren auf Bluetooth. Die Bluetooth-Implementierung auf Teams-Räume Geräten lässt jedoch keine Externe Geräteverbindung mit einem Teams-Räume-Gerät zu. Bluetooth Technologie, die auf Teams-Räume Geräten verwendet wird, ist derzeit auf Werbebeacons und aufgeforderte proximale Verbindungen beschränkt. Der `ADV_NONCONN_INT` Protokolldateneinheitstyp (Protocol Data Unit, PDU) wird im Werbebeacons verwendet. Dieser PDU-Typ ist für nicht miteinander verbundene Geräte, die Werbeinformationen für das Überwachungsgerät anzeigen. Es gibt keine Bluetooth Gerätekopplung als Teil dieser Features. Weitere Details zu Bluetooth Protokollen finden Sie auf der [website Bluetooth SIG](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/).

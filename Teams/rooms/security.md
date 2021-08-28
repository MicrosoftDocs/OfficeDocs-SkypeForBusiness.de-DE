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
description: Erfahren Sie, wie Sie Ihre Microsoft Teams-Räume sichern.
ms.openlocfilehash: d3b0f244f36ed30376fbe72e9669b6f84f9f9629
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627287"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams-Räume Sicherheit

Microsoft arbeitet mit unseren Partnern zusammen, um eine sichere Lösung zu finden, die keine zusätzlichen Aktionen zum Sichern ihrer Microsoft Teams-Räume. In diesem Artikel werden viele der Sicherheitsfeatures beschrieben, die in ihrer Teams-Räume.

> [!NOTE]
> Microsoft Teams-Räume sollten nicht wie eine typische Arbeitsstation des Endbenutzers behandelt werden. Die Einsatzfälle unterscheiden sich nicht nur deutlich, sondern auch die standardmäßigen Sicherheitsprofile.
> Dieser Artikel bezieht sich auf Microsoft Teams-Räume auf Geräten, die auf Windows.

Auf diesen Daten werden nur eingeschränkte Teams-Räume. Endbenutzerdaten können nur zur Problembehandlung und Unterstützung in den Protokolldateien gespeichert werden. Der Teilnehmer einer Besprechung kann jederzeit mithilfe von Teams-Räume Dateien auf die Festplatte kopieren oder sich als sich anmelden. Es werden keine Endbenutzerdaten an das Gerät übertragen bzw. kann auch nicht von dem Microsoft Teams-Räume werden.

Obwohl Endbenutzer keine Dateien auf einer Teams-Räume speichern können, ist Microsoft Defender weiterhin aktiviert. Teams-Räume Leistung wird mit Microsoft Defender getestet. Wenn Sie diese Sicherheitssoftware deaktivieren oder Endpunkt-Sicherheitssoftware hinzufügen, kann dies zu unerwarteten Ergebnissen und potenziellen Systembeeinträchtigungen führen.

## <a name="hardware-security"></a>Hardwaresicherheit

In einer Teams-Räume gibt es ein zentrales Rechenmodul, das in Windows 10 IoT Enterprise ausgeführt wird. Jedes zertifizierte Rechenmodul muss eine sichere Lösung für die Montage, einen Sicherheitssperrplatz (z. B. die Zugriffssperre von Einem-O-Port) und Sicherheitsmaßnahmen für den E/A-Portzugriff haben, um die Verbindung von nicht autorisierten Geräten zu verhindern. Sie können bestimmte Ports auch über die Konfiguration Unified Extensible Firmware Interface (UEFI) deaktivieren.

Jedes zertifizierte Rechenmodul muss mit TPM (Trusted Platform Module) 2.0-kompatibler Technologie ausgestattet sein, die standardmäßig aktiviert ist. TPM wird verwendet, um die Anmeldeinformationen für das Konto der Teams-Räume zu verschlüsseln.

Sicherer Neustart ist standardmäßig aktiviert. Secure Boot ist ein Sicherheitsstandard, der von Den Mitgliedern der PC-Branche entwickelt wurde, um sicherzustellen, dass ein Gerätesstart nur mithilfe von Software geht, die vom Originalgerätehersteller (OEM) als vertrauenswürdig eingestuft wird. Beim Starten des PCs überprüft die Firmware die Signatur der einzelnen Startsoftwaredateien, einschließlich UEFI-Firmwaretreiber (auch als Options-ROMs bezeichnet), EFI-Anwendungen und des Betriebssystems. Wenn die Signaturen gültig sind, übergibt der PC das Bootsing, und die Firmware übergibt die Steuerung an das Betriebssystem. Weitere Informationen finden Sie unter [Sicherer Neustart.](/windows-hardware/design/device-experiences/oem-secure-boot)

Der Zugriff auf die UEFI-Einstellungen ist nur durch Anfügen einer physischen Tastatur und Maus möglich. Dadurch wird verhindert, dass Sie über die Teams-Räume-Konsole und alle anderen touchfähigen Displays, die an die App angeschlossen sind, auf UEFI Teams-Räume.

Der DMA-Schutz (Kernel Direct Memory Access) ist eine Windows 10, die für den Zugriff Teams-Räume. Mit diesem Feature schützen das Betriebssystem und die Systemfirmware das System vor böswilligen und unbeabsichtigten DMA-Angriffen für alle DMA-fähigen Geräte:

- Während des Startvorgangs.

- Gegen bösartiges DMA durch Geräte, die während der Laufzeit des Betriebssystems an leicht zugängliche interne/externe DMA-fähige Ports angeschlossen sind, z. B. M.2-PCIe-Slots und Untug 3.

Teams-Räume ermöglicht außerdem hypervisorgeschützte Codeintegrität (Hypervisor-protected Code Integrity, HVCI). Eines der Von HVCI bereitgestellten Features ist Credential Guard. Credential Guard bietet die folgenden Vorteile:

- **Hardwaresicherheit** NTLM, Kerberos und Credential Manager nutzen die Vorteile der Plattformsicherheitsfeatures, einschließlich Secure Boot und Virtualisierung, um Anmeldeinformationen zu schützen.

- **Von NTLM** Windows Kerberos abgeleitete Anmeldeinformationen und andere von Kerberos abgeleitete Sicherheitsdaten werden in einer geschützten Umgebung ausgeführt, die vom ausgeführten Betriebssystem isoliert ist.

- **Besserer Schutz vor erweiterten dauerhaften Bedrohungen** Wenn Anmeldeinformationen für die Anmeldeinformationen der Anmeldeinformationen für die Domäne, NTLM- und Kerberos-abgeleitete Anmeldeinformationen mithilfe virtualisierungsbasierter Sicherheit geschützt werden, werden die Methoden und Tools zum Diebstahl von Anmeldeinformationen und Tools blockiert, die in vielen gezielten Angriffen verwendet werden. Malware, die im Betriebssystem mit Administratorrechten ausgeführt wird, kann keine geheimnissen Daten extrahieren, die durch virtualisierungsbasierte Sicherheit geschützt sind.

## <a name="software-security"></a>Softwaresicherheit

Nachdem Microsoft Windows Boots ausgeführt hat, Teams-Räume sich automatisch bei einem lokalen Windows mit dem Namen "Skype. Das Skype Konto hat kein Kennwort. Um die Sitzung Skype Kontos sicher zu machen, werden die folgenden Schritte unternommen.

> [!IMPORTANT]
> Ändern Sie nicht das Kennwort, oder bearbeiten Sie das Skype Benutzerkonto. Dadurch kann verhindert werden, Teams-Räume Anmeldung automatisch erfolgt.

Die Microsoft Teams-Räume-App wird mithilfe des Features "Zugewiesener Zugriff" ausgeführt, das in Windows 10 1903 und höher verfügbar ist. Zugewiesener Access ist ein Feature in Windows 10, das die Anwendungseinstiegspunkte beschränkt, die für Benutzer verfügbar gemacht werden. Dadurch wird der Kioskmodus (Einzel-App) aktiviert. Mithilfe der Startprogramm wird Teams-Räume als Kioskgerät konfiguriert, auf dem eine Windows-Desktopanwendung als Benutzeroberfläche ausgeführt wird. Die Microsoft Teams-Räume-App ersetzt die Standardshell (explorer.exe), die normalerweise ausgeführt wird, wenn sich ein Benutzer anmeldet. Mit anderen Worten: Die herkömmliche Explorer-Shell wird überhaupt nicht gestartet. Dadurch wird das Sicherheitsrisiko Microsoft Teams-Räume innerhalb des Windows. Weitere Informationen finden Sie unter Konfigurieren von Kiosken und [digitalen Schildern Windows Desktopeditionen.](/windows/configuration/kiosk-methods)

Wenn Sie sich für Teams-Räume für eine Sicherheitsscan oder einen CENTERS for Internet Security (CENTERS for Internet Security)-Benchmark entscheiden, kann die Überprüfung nur im Kontext eines lokalen Administratorkontos ausgeführt werden, da das Skype-Benutzerkonto keine anderen Anwendungen als die Teams-Räume-App unterstützt. Viele der auf den Skype-Benutzerkontext angewendeten Sicherheitsfeatures gelten nicht für andere lokale Benutzer, und dies führt dazu, dass diese Sicherheitsscans die auf das Skype-Konto angewendete vollständige Sicherheitssperre nicht Skype werden. Es wird daher nicht empfohlen, eine lokale Überprüfung auf einem Teams-Räume. Bei Bedarf können Sie jedoch externe Eindringtests durchführen. Aus diesem Grund empfiehlt es sich, externe Enddringtests für andere Teams-Räume anstatt lokale Scans durchzuführen.

Darüber hinaus werden Sperrrichtlinien angewendet, um die Verwendung nicht administrativer Features zu beschränken. Ein Tastaturfilter ist aktiviert, um potenziell unsichere Tastaturkombinationen abzufangen und zu blockieren, die von Richtlinien für zugewiesenen Zugriff nicht abgedeckt sind. Es ist nur Benutzern mit lokalen Administratorrechten oder Domänen gestattet, sich bei einem Windows zu Teams-Räume. Diese und andere Richtlinien, die auf Windows auf Microsoft Teams-Räume-Geräten angewendet werden, werden während des Produktlebenszyklus kontinuierlich bewertet und getestet.

## <a name="account-security"></a>Kontosicherheit

Teams-Räume-Geräte enthalten ein Administratorkonto mit dem Namen "Administrator" mit einem Standardkennwort. Es wird dringend empfohlen, das Standardkennwort so bald wie möglich zu ändern, nachdem Sie das Setup abgeschlossen haben.

Das Administratorkonto ist für den ordnungsgemäßen Betrieb ihrer Teams-Räume nicht erforderlich und kann umbenannt oder sogar gelöscht werden. Bevor Sie das Administratorkonto löschen, stellen Sie jedoch sicher, dass Sie ein alternatives lokales Administratorkonto eingerichtet haben, das konfiguriert ist, bevor Sie das mit den Teams-Räume entfernen. Weitere Informationen zum Ändern eines Kennworts für ein lokales Windows-Konto mithilfe von integrierten Windows-Tools oder PowerShell finden Sie in den folgenden Themen:

- [Ändern oder Zurücksetzen Ihres Windows Kennworts](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

Sie können auch Domänenkonten in die lokale Gruppe administrator Windows importieren. Sie können dies für Azure AD-Konten mithilfe von Intune tun. Weitere Informationen finden Sie unter [Richtlinien-CSP – Eingeschränkte Gruppen.](/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!CAUTION]
> Wenn Sie das Administratorkonto löschen oder deaktivieren, bevor Sie einem anderen lokalen Konto oder Domänenkonto lokale Administratorberechtigungen erteilen, verlieren Sie möglicherweise die Möglichkeit zur Verwaltung des Teams-Räume Geräts. In diesem Fall müssen Sie das Gerät auf die ursprünglichen Einstellungen zurücksetzen und den Setupvorgang erneut abschließen.
>
> Erteilen Sie keine lokalen Administratorberechtigungen für das Skype Benutzerkonto.

Windows Mit dem Konfigurations-Designer können Sie Windows 10 Bereitstellungspakete erstellen. Neben dem Ändern des lokalen Administratorkennworts können Sie auch Dinge wie das Ändern des Computernamens und die Registrierung bei Azure Active Directory. Weitere Informationen zum Erstellen eines [Bereitstellungspakets](/windows/configuration/provisioning-packages/provisioning-packages)Windows Configuration Designer finden Sie unter Bereitstellen von Paketen für Windows 10.

Sie müssen für jedes Teams-Räume-Gerät ein Ressourcenkonto erstellen, damit es sich bei einem Teams. Bei diesem Konto können Sie keine zweistufige oder mehrstufige Authentifizierung verwenden. Ein zweiter Faktor würde verhindern, dass sich das Konto nach einem Neustart automatisch bei der Teams-Räume-App anmeldet. Sie können die moderne Authentifizierung jedoch aktivieren, um zusätzliche Sicherheit für dieses Konto zu gewährleisten. Darüber hinaus können standortbasierte Richtlinien für bedingten Zugriff für das Ressourcenkonto bereitgestellt werden, um zu verhindern, dass Sie sich an einem nicht genehmigten Speicherort beim Konto anmelden. Weitere Informationen finden Sie unter [Verwenden der Standortbedingung in einer Richtlinie für bedingten Zugriff.](/azure/active-directory/conditional-access/location-condition)

Es wird empfohlen, das Ressourcenkonto nach Möglichkeit in Azure AD zu erstellen. Während ein synchronisiertes Konto in Hybridbereitstellungen mit Teams-Räume arbeiten kann, haben diese synchronisierten Konten häufig Schwierigkeiten bei der Anmeldung bei Teams-Räume und die Problembehandlung ist schwierig. Wenn Sie sich für die Authentifizierung der Anmeldeinformationen für das Ressourcenkonto mit einem Drittanbieter-Verbunddienst entscheiden, stellen Sie sicher, dass der Drittanbieter-IDP mit dem auf festgelegten Attribut `wsTrustResponse` `urn:oasis:names:tc:SAML:1.0:assertion` antwortet.

## <a name="network-security"></a>Netzwerksicherheit

Im Allgemeinen Teams-Räume Netzwerkanforderungen wie für alle anderen Microsoft Teams gelten. Der Zugriff über Firewalls und andere Sicherheitsgeräte ist für alle Teams-Räume und für alle anderen Microsoft Teams identisch. Speziell für Teams-Räume müssen die Kategorien, die für Benutzer als "erforderlich" Teams in Ihrer Firewall geöffnet sein. Teams-Räume muss auch auf Windows Update, Microsoft Store und Microsoft Intune zugreifen können (wenn Sie Microsoft Intune zum Verwalten Ihrer Geräte verwenden). Eine vollständige Liste der IPs und URLs, die für die Microsoft Teams-Räume erforderlich sind, finden Sie unter:

- **Microsoft Teams** [Office 365 URLs und IP-Adressbereiche](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows Update Konfigurieren** [von WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store** [Voraussetzungen für Microsoft Store für Unternehmen und Bildungseinrichtungen](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [Netzwerk-Enpoints für Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Wenn Sie die Komponente "Microsoft Teams-Räume verwaltete Dienste" von Microsoft Teams-Räume Premium verwenden, müssen Sie auch sicherstellen, dass Teams-Räume auf die folgenden URLs zugreifen kann:

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

Teams-Räume ist so konfiguriert, dass er automatisch mit den neuesten Updates Windows Patches aktualisiert wird, einschließlich Sicherheitsupdates. Teams-Räume installiert alle ausstehenden Updates jeden Tag ab 02:00 Uhr mithilfe einer vordefinierten lokalen Richtlinie. Es ist nicht nötig, zusätzliche Tools zum Bereitstellen und Anwenden von Updates Windows verwenden. Die Verwendung zusätzlicher Tools zum Bereitstellen und Anwenden von Updates kann die Installation Windows Patches verzögern und somit zu einer weniger sicheren Bereitstellung führen. Die Teams-Räume-App wird mithilfe des -Microsoft Store. Wenn Ihre Geräte mit Microsoft Teams-Räume Standard lizenziert sind, werden alle neuen Versionen der App während des nächtlichen Patchprozesses automatisch installiert. Wenn Ihre Geräte bei Microsoft Teams-Räume Premium lizenziert und für den Microsoft Managed Service registriert sind, werden neue Versionen der Teams-Räume-App nach Ihrem definierten Rolloutplan installiert.

Teams-Räume-Geräte können mit den meisten 802.1X- oder anderen netzwerkbasierten Sicherheitsprotokollen verwendet werden. Es ist jedoch nicht möglich, die Teams-Räume mit allen möglichen Netzwerksicherheitskonfigurationen zu testen. Wenn daher Leistungsprobleme auftreten, die auf Netzwerkleistungsprobleme zurückverfolgt werden können, müssen Sie diese Protokolle möglicherweise deaktivieren, wenn sie in Ihrer Organisation konfiguriert sind.

Für eine optimale Leistung von Echtzeitmedien wird dringend empfohlen, dass Sie Teams-Medienverkehr so konfigurieren, dass Proxyserver und andere Netzwerksicherheitsgeräte umgangen werden. Echtzeitmedien sind sehr latenzsensibler, Proxyserver und Netzwerksicherheitsgeräte können die Video- und Audioqualität der Benutzer erheblich beeinträchtigen. Da die Teams bereits verschlüsselt ist, ist es auch nicht von Vorteil, den Datenverkehr über einen Proxyserver zu übergeben. Weitere Informationen finden Sie unter Netzwerk (zur [Cloud)](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) – Die Sichtpunkt eines Architekturadministrators, in dem Netzwerkempfehlungen zur Verbesserung der Medienleistung mit Mediendateien Microsoft Teams und Microsoft Teams-Räume.

> [!IMPORTANT]
> Teams-Räume unterstützt keine authentifizierten Proxyserver.

Teams-Räume-Geräte müssen keine Verbindung mit einem internen LAN herstellen. Erwägen Sie, Teams-Räume Daten in einem sicheren Netzwerksegment mit direktem Internetzugriff zu platzieren. Wenn ihr internes LAN gefährdet wird, werden die Möglichkeiten des Angriffsvektors gegenüber Teams-Räume verringert.

Es wird dringend empfohlen, Ihre Teams-Räume mit einem verkabelten Netzwerk zu verbinden. Die Verwendung von Funknetzwerken auf Teams-Räume wird nicht empfohlen oder zertifiziert. Einige Konnektivitätsfeatures wie Wi-Fi Sind standardmäßig deaktiviert.

Näherungs-Verknüpfung und Teams-Räume-Features sind von Bluetooth. Die Implementierung Bluetooth auf Teams-Räume-Geräten lässt jedoch keine Verbindung eines externen Geräts zu einem Teams-Räume zu. Bluetooth Verwendung der Technologie auf Teams-Räume-Geräten ist derzeit auf Werbebeacons und aufforderungsaufforderliche Proximalverbindungen beschränkt. Der `ADV_NONCONN_INT` Typ der Protokolldateneinheit (PDU) wird im Werbebeacons verwendet. Dieser PDU-Typ ist für nicht verbindende Geräte, die Informationen zum Anzeigen von Informationen für das Lauschendegerät anzeigen. Diese Features Bluetooth keine Gerätekopplung für andere Geräte. Weitere Details zu Bluetooth Protokollen finden Sie auf der Website [Bluetooth SIG.](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)

---
title: Microsoft Teams Rooms Security
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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Ihre Microsoft Teams Rooms-Geräte sichern.
ms.openlocfilehash: 522cc845e2e6b8b1f57fc0ab1c1523452ec429f8
ms.sourcegitcommit: 6785d7f1ef5d2010ab334ec8cc46884327a53662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2021
ms.locfileid: "50395377"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams Rooms Security

Microsoft arbeitet mit unseren Partnern zusammen, um eine Lösung zu liefern, die sicher ist und keine zusätzlichen Aktionen zum Sichern von Microsoft Teams Rooms erfordert. In diesem Artikel werden viele der Sicherheitsfeatures beschrieben, die in Teams Rooms gefunden wurden.

> [!NOTE]
> Microsoft Teams Rooms sollte nicht wie eine typische Endbenutzerarbeitsstation behandelt werden. Die Verwendungsfälle unterscheiden sich nicht nur stark, sondern auch die Standardsicherheitsprofile unterscheiden sich stark.

Eingeschränkte Endbenutzerdaten werden in Teams Rooms gespeichert. Endbenutzerdaten werden möglicherweise nur zur Problembehandlung und unterstützung in den Protokolldateien gespeichert. Zu keinem Zeitpunkt kann ein Teilnehmer einer Besprechung mit Teams Rooms Dateien auf die Festplatte kopieren oder sich als sich selbst anmelden. Auf das Microsoft Teams Rooms-Gerät werden keine Endbenutzerdaten übertragen oder auf diese zugegriffen.

Obwohl Endbenutzer keine Dateien auf einer Microsoft Teams Rooms-Festplatte speichern können, ist Microsoft Defender weiterhin aktiviert. Die Leistung von Teams Rooms wird mit Microsoft Defender getestet. Das Deaktivieren dieser Software oder das Hinzufügen von Sicherheitssoftware für Endpunkte kann zu unvorhersehbaren Ergebnissen und potenziellen Systemverlusten führen.

## <a name="hardware-security"></a>Hardwaresicherheit

In einer Teams Rooms-Umgebung gibt es ein zentrales Rechenmodul, das Windows 10 IoT Enterprise edition ausgeführt wird. Jedes zertifizierte Datenverarbeitungsmodul muss über eine sichere Montagelösung, einen Sicherheitsschlossplatz (z. B. Die Sperre von "Kensington" ) und Sicherheitsmaßnahmen für den I/O-Portzugriff verfügen, um die Verbindung nicht autorisierter Geräte zu verhindern. Sie können bestimmte Ports auch über die Konfiguration unified Extensible Firmware Interface (UEFI) deaktivieren.

Jedes zertifizierte Rechenmodul muss standardmäßig mit TPM (Trusted Platform Module) 2.0-kompatibler Technologie ausgestattet sein. TPM wird verwendet, um die Anmeldeinformationen für das Teams Rooms-Ressourcenkonto zu verschlüsseln.

Der sichere Start ist standardmäßig aktiviert. Sicherer Start ist ein Sicherheitsstandard, der von Mitgliedern der PC-Branche entwickelt wurde, um sicherzustellen, dass ein Gerät nur mit Software gestartet wird, die vom Originalgerätehersteller (OEM) als vertrauenswürdig eingestuft wird. Wenn der PC gestartet wird, überprüft die Firmware die Signatur der einzelnen Startsoftware, einschließlich UEFI-Firmwaretreibern (auch als Options-ROMs bezeichnet), EFI-Anwendungen und dem Betriebssystem. Wenn die Signaturen gültig sind, wird der PC gestartet, und die Firmware gibt dem Betriebssystem die Steuerung. Weitere Informationen finden Sie unter [Sicherer Start](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

Der Zugriff auf UEFI-Einstellungen ist nur durch Anfügen einer physischen Tastatur und Maus möglich. Dadurch wird verhindert, dass Sie über die touchfähige Konsole teams rooms sowie über alle anderen touchfähigen Bildschirme, die an Teams Rooms angefügt sind, auf UEFI zugreifen können.

Kernel Direct Memory Access (DMA) Protection ist eine Windows 10-Einstellung, die in Teams Rooms aktiviert ist. Mit diesem Feature schützen das Betriebssystem und die Systemfirmware das System vor böswilligen und unbeabsichtigten DMA-Angriffen für alle DMA-fähigen Geräte:

- Während des Startvorgangs.

- Schutz vor böswilligem DMA durch Geräte, die während der Betriebssystem-Runtime mit einfach zugänglichen internen/externen DMA-fähigen Ports verbunden sind, z. B. M.2-PCIe-Steckplätzen und Thunder 3.

Teams Rooms aktiviert außerdem hypervisor-geschützte Codeintegrität (HVCI). Eines der Von HVCI bereitgestellten Features ist Credential Guard. Credential Guard bietet die folgenden Vorteile:

- **Hardwaresicherheit** NTLM, Kerberos und Credential Manager nutzen die Vorteile von Plattformsicherheitsfeatures, einschließlich Secure Boot und Virtualisierung, um Anmeldeinformationen zu schützen.

- **Virtualisierungsbasierte Sicherheit** Von Windows NTLM und Kerberos abgeleitete Anmeldeinformationen und andere Geheiminformationen werden in einer geschützten Umgebung ausgeführt, die vom ausgeführten Betriebssystem isoliert ist.

- **Besserer Schutz vor erweiterten persistenten Bedrohungen** Wenn Anmeldeinformationen für anmeldeinformationsbasierte Domänenanmeldeinformationen, NTLM und kerberos abgeleitete Anmeldeinformationen mithilfe virtualisierungsbasierter Sicherheit geschützt werden, werden die Methoden und Tools zum Diebstahl von Anmeldeinformationen, die in vielen gezielten Angriffen verwendet werden, blockiert. Malware, die im Betriebssystem mit Administratorrechten ausgeführt wird, kann keine Geheimnisse extrahieren, die durch virtualisierungsbasierte Sicherheit geschützt sind.

## <a name="software-security"></a>Softwaresicherheit

Nachdem Microsoft Windows gestartet wurde, meldet sich Teams Rooms automatisch bei einem lokalen Windows-Benutzerkonto namens Skype an. Das Skype-Konto hat kein Kennwort. Um die Skype-Kontositzung sicher zu machen, werden die folgenden Schritte unternommen.

> [!IMPORTANT]
> Ändern Sie das Kennwort nicht, oder bearbeiten Sie das lokale Skype-Benutzerkonto. Dadurch kann verhindert werden, dass sich Teams Rooms automatisch anmelden.

Die Microsoft Teams Rooms-App wird mit dem Feature Zugewiesener Zugriff unter Windows 10 1903 und höher ausgeführt. Zugewiesener Access ist ein Feature in Windows 10, das die für den Benutzer verfügbar gemachten Anwendungseingabepunkte einschränkt. Dies ermöglicht den Einzel-App-Kioskmodus. Mithilfe von Shell Startprogramm Teams Rooms als Kioskgerät konfiguriert, auf dem eine Windows-Desktopanwendung als Benutzeroberfläche ausgeführt wird. Die Microsoft Teams Rooms-App ersetzt die Standardshell (explorer.exe), die normalerweise ausgeführt wird, wenn sich ein Benutzer anmeldet. Anders ausgedrückt: Die herkömmliche Explorer-Shell wird überhaupt nicht gestartet. Dadurch wird die Anfälligkeitsoberfläche von Microsoft Teams Rooms in Windows erheblich reduziert. Weitere Informationen finden Sie unter [Konfigurieren von Kiosken und digitalen Schildern auf Windows-Desktopeditionen.](https://docs.microsoft.com/windows/configuration/kiosk-methods)

Wenn Sie sich für die Ausführung einer Sicherheitsscans oder eines Centers for Internet Security (ZISS) in Teams Rooms entscheiden, kann die Überprüfung nur unter dem Kontext eines lokalen Administratorkontos ausgeführt werden, da das Skype-Benutzerkonto keine anderen Anwendungen als die Teams Rooms-App unterstützt. Viele der auf den Kontext des Skype-Benutzers angewendeten Sicherheitsfeatures gelten nicht für andere lokale Benutzer, und als Ergebnis werden diese Sicherheitsscans nicht die vollständige Sicherheitssperre für das Skype-Konto angezeigt. Daher wird es nicht empfohlen, eine lokale Überprüfung in Teams Rooms zu starten. Bei Bedarf können Sie jedoch externe Durchdringungstests durchführen. Aus diesem Grund wird empfohlen, externe Eindringungstests für Teams Rooms-Geräte durchzuführen, anstatt lokale Scans durchzuführen.

Darüber hinaus werden Sperrrichtlinien angewendet, um die Verwendung nicht administrativer Features zu beschränken. Ein Tastaturfilter ist zum Abfangen und Blockieren potenziell unsicherer Tastaturkombinationen aktiviert, die nicht unter Richtlinien für zugewiesenen Zugriff fallen. Nur Benutzer mit lokalen oder Domänenadministratorrechten dürfen sich bei Windows anmelden, um Teams Rooms zu verwalten. Diese und andere Richtlinien, die auf Windows auf Microsoft Teams Rooms-Geräten angewendet werden, werden während des Produktlebenszyklus kontinuierlich bewertet und getestet.

## <a name="account-security"></a>Kontosicherheit

Teams Rooms-Geräte enthalten ein Administratorkonto mit dem Namen "Administrator" mit einem Standardkennwort. Es wird dringend empfohlen, das Standardkennwort so schnell wie möglich zu ändern, nachdem Sie die Einrichtung abgeschlossen haben.

Das Administratorkonto ist für den ordnungsgemäßen Betrieb von Teams Rooms-Geräten nicht erforderlich und kann umbenannt oder sogar gelöscht werden. Bevor Sie das Administratorkonto löschen, stellen Sie jedoch sicher, dass Sie ein alternatives lokales Administratorkonto eingerichtet haben, das konfiguriert wurde, bevor Sie das Konto entfernen, das mit Teams Rooms-Geräten versendet wird. Weitere Informationen zum Ändern eines Kennworts für ein lokales Windows-Konto mit integrierten Windows-Tools oder PowerShell finden Sie in den folgenden Themen:

- [Ändern oder Zurücksetzen Ihres Windows-Kennworts](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

Sie können auch Domänenkonten in die lokale Windows-Administratorgruppe importieren. Sie können dies für Azure AD-Konten mithilfe von Intune tun. Weitere Informationen finden Sie unter [Richtlinien-CSP – Eingeschränkte Gruppen.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups).

> [!CAUTION]
> Wenn Sie das Administratorkonto löschen oder deaktivieren, bevor Sie einem anderen lokalen Oder Domänenkonto Berechtigungen für den lokalen Administrator erteilen, verlieren Sie möglicherweise die Möglichkeit, das Gerät "Teams Rooms" zu verwalten. In diesem Fall müssen Sie das Gerät wieder auf die ursprünglichen Einstellungen zurücksetzen und den Setupvorgang erneut ausführen.
>
> Erteilen Sie dem Skype-Benutzerkonto keine Lokalen Administratorberechtigungen.

Windows Configuration Designer kann zum Erstellen von Windows 10-Bereitstellungspaketen verwendet werden. Neben dem Ändern des lokalen Administratorkennworts können Sie auch Dinge wie das Ändern des Computernamens und die Registrierung bei Azure Active Directory tun. Weitere Informationen zum Erstellen eines Windows Configuration Designer-Bereitstellungspakets finden Sie unter Bereitstellen von [Paketen für Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).

Sie müssen für jedes Teams Rooms-Gerät ein Ressourcenkonto erstellen, damit es sich bei Teams anmelden kann. Sie können für dieses Konto keine zweistufige oder mehrstufige Authentifizierung verwenden. Durch das Erfordern eines zweiten Faktors kann sich das Konto nach einem Neustart nicht automatisch bei der Teams Rooms-App anmelden. Sie können jedoch die moderne Authentifizierung aktivieren, um zusätzliche Sicherheit für dieses Konto zu gewährleisten. Darüber hinaus können standortbasierte Richtlinien für bedingten Zugriff für das Ressourcenkonto bereitgestellt werden, um die Anmeldung beim Konto von einem nicht genehmigten Speicherort zu verhindern. Weitere Informationen finden Sie unter [Verwenden der Standortbedingung in einer Richtlinie für bedingten Zugriff.](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)

Wir empfehlen, das Ressourcenkonto nach Möglichkeit in Azure AD zu erstellen. Während ein synchronisiertes Konto in Hybridbereitstellungen mit Teams Rooms zusammenarbeiten kann, haben diese synchronisierten Konten häufig Schwierigkeiten bei der Anmeldung bei Teams Rooms und können schwierig zu beheben sein. Wenn Sie einen Drittanbieterverbunddienst verwenden, um die Anmeldeinformationen für das Ressourcenkonto zu authentifizieren, stellen Sie sicher, dass der Drittanbieter-IDP mit dem attribut auf `wsTrustResponse` `urn:oasis:names:tc:SAML:1.0:assertion` antwortet.

## <a name="network-security"></a>Netzwerksicherheit

Im Allgemeinen gelten für Teams Rooms dieselben Netzwerkanforderungen wie für jeden Microsoft Teams-Client. Der Zugriff über Firewalls und andere Sicherheitsgeräte ist für Teams Rooms identisch mit jedem anderen Microsoft Teams-Client. Speziell für Teams Rooms müssen die Kategorien, die für Teams als "erforderlich" aufgelistet sind, in Ihrer Firewall geöffnet sein. Teams Rooms benötigt auch Zugriff auf Windows Update, Microsoft Store und Microsoft Intune (wenn Sie Microsoft Intune zum Verwalten Ihrer Geräte verwenden). Die vollständige Liste der für Microsoft Teams Rooms erforderlichen IPs und URLs finden Sie unter:

- **UrLs** und IP-Adressbereiche von Microsoft Teams [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows Update** [Konfigurieren von WSUS](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store–** [Voraussetzungen für den Microsoft Store für Unternehmen und Bildungseinrichtungen](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [Network Enpoints für Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)

Wenn Sie die Komponente verwaltete Dienste von Microsoft Teams Rooms Premium verwenden, müssen Sie auch sicherstellen, dass Teams Rooms auf die folgenden URLs zugreifen kann:

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

Teams Rooms ist so konfiguriert, dass er automatisch mit den neuesten Windows-Updates gepatcht bleibt, einschließlich Sicherheitsupdates. Teams Rooms installiert alle ausstehenden Updates jeden Tag ab 02:00 Uhr mit einer vordefinierten lokalen Richtlinie. Es ist nicht nötig, zusätzliche Tools zum Bereitstellen und Anwenden von Windows-Updates zu verwenden. Die Verwendung zusätzlicher Tools zum Bereitstellen und Anwenden von Updates kann die Installation von Windows-Patches verzögern und somit zu einer weniger sicheren Bereitstellung führen. Die Teams Rooms-App wird über den Microsoft Store bereitgestellt. Wenn Ihre Geräte mit Microsoft Teams Rooms Standard lizenziert sind, werden alle neuen Versionen der App während des nächtlichen Patchvorgangs automatisch installiert. Wenn Ihre Geräte mit Microsoft Teams Rooms Premium lizenziert und für den verwalteten Dienst von Microsoft registriert sind, werden neue Versionen der Teams Rooms-App gemäß Ihrem definierten Rolloutplan installiert.

Teams Rooms-Geräte funktionieren mit den meisten 802.1X- oder anderen netzwerkbasierten Sicherheitsprotokollen. Wir können Teams Rooms jedoch nicht mit allen möglichen Netzwerksicherheitskonfigurationen testen. Wenn daher Leistungsprobleme auftreten, die auf Netzwerkleistungsprobleme zurückverfolgt werden können, müssen Sie diese Protokolle möglicherweise deaktivieren, wenn sie in Ihrer Organisation konfiguriert sind.

Für eine optimale Leistung von Echtzeitmedien empfehlen wir dringend, den Mediendatenverkehr von Teams so zu konfigurieren, dass Proxyserver und andere Netzwerksicherheitsgeräte umgangen werden. Echtzeitmedien sind sehr latenzempfindlich, und Proxyserver und Netzwerksicherheitsgeräte können die Video- und Audioqualität der Benutzer erheblich beeinträchtigen. Da Teams-Medien bereits verschlüsselt sind, bietet die Übergabe des Datenverkehrs über einen Proxyserver keinen greifbaren Vorteil. Weitere Informationen finden Sie unter Networking [up (to the cloud) – Der](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) Standpunkt eines Architekten, in dem Netzwerkempfehlungen zur Verbesserung der Leistung von Medien mit Microsoft Teams und Microsoft Teams Rooms erörtert werden.

> [!IMPORTANT]
> Teams Rooms unterstützt keine authentifizierten Proxyserver.

Teams Rooms-Geräte müssen keine Verbindung mit einem internen LAN herstellen. Erwägen Sie, Teams Rooms in einem sicheren Netzwerksegment mit direktem Internetzugriff zu platzieren. Wenn Ihr internes LAN gefährdet wird, werden die Angriffsvektorchancen in Richtung Teams Rooms reduziert.

Wir empfehlen dringend, Ihre Teams Rooms-Geräte mit einem kabelgebundenen Netzwerk zu verbinden. Die Verwendung von Drahtlosnetzwerken auf Teams Rooms-Geräten wird nicht empfohlen oder zertifiziert. Einige Konnektivitätsfeatures wie Wi-Fi Sense sind standardmäßig deaktiviert.

Näherungs-Join- und andere Features von Teams Rooms sind von der Bluetooth. Die Implementierung Bluetooth Teams Rooms-Geräten ermöglicht jedoch keine Externe Geräteverbindung mit einem Team Rooms-Gerät. Bluetooth Technologienutzung auf Teams Rooms-Geräten ist derzeit auf Werbebeacons und aufgeforderte proximale Verbindungen beschränkt. Der `ADV_NONCONN_INT` Typ der Protokolldateneinheit (Protocol Data Unit, PDU) wird im Werbebeacons verwendet. Dieser PDU-Typ ist für nicht anpassbare Geräte, die Informationen zum Hörenden anzeigen. Es gibt keine Bluetooth gerätekopplung als Teil dieser Features. Weitere Details zu Bluetooth Protokollen finden Sie auf der Bluetooth [SIG-Website.](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)

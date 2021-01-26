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
description: Erfahren Sie, wie Sie Ihre Microsoft Teams -Räume sichern.
ms.openlocfilehash: d9968af4f386ed68d9a931d834082ba5362c5c33
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880883"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams Rooms Security

Microsoft arbeitet mit unseren Partnern zusammen, um eine sichere Lösung zu finden, die keine zusätzlichen Aktionen zum Sichern von Microsoft Teams Rooms erfordert. In diesem Artikel werden viele der Sicherheitsfeatures beschrieben, die in Teams Rooms zu finden sind.

> [!NOTE]
> Microsoft Teams Rooms sollten nicht wie eine typische Arbeitsstation des Endbenutzers behandelt werden. Nicht nur die Verwendungsfälle unterscheiden sich deutlich, auch die Standardsicherheitsprofile unterscheiden sich stark.

In Teams Rooms werden eingeschränkte Endbenutzerdaten gespeichert. Endbenutzerdaten können nur zur Problembehandlung und Unterstützung in den Protokolldateien gespeichert werden. An keiner Stelle kann ein Teilnehmer einer Besprechung, in der Teams Rooms verwendet wird, Dateien auf die Festplatte kopieren oder sich als sie selbst anmelden. Vom Gerät "Microsoft Teams-Räume" werden keine Endbenutzerdaten übertragen bzw. auf diese kann auch nicht zugegriffen werden.

Obwohl Endbenutzer keine Dateien auf einer Festplatte von Teams Rooms speichern können, ist Microsoft Defender weiterhin aktiviert. Die Leistung von Teams Rooms wird mit Microsoft Defender getestet. Das Deaktivieren oder Hinzufügen von Endpunktsicherheitssoftware kann zu unvorhersehbaren Ergebnissen und einer potenziellen Beeinträchtigung des Systems führen.

## <a name="hardware-security"></a>Hardwaresicherheit

In einer Teams Rooms-Umgebung gibt es ein zentrales Rechenmodul, das Windows 10 IoT Enterprise Edition ausgeführt. Jedes zertifizierte Rechenmodul muss über eine sichere Lösung für die Aufnahme, eine Sicherheitssperre (z. B. Sperre für den Verbindungszugriff) und Sicherheitsmaßnahmen für den E/A-Portzugriff verfügen, um die Verbindung nicht autorisierter Geräte zu verhindern. Sie können bestimmte Ports auch über die Konfiguration unified Extensible Firmware Interface (UEFI) deaktivieren.

Jedes zertifizierte Rechenmodul muss mit TPM (Trusted Platform Module) 2.0-kompatibler Technologie ausgestattet sein, die standardmäßig aktiviert ist. TPM wird verwendet, um die Anmeldeinformationen für das Ressourcenkonto "Teams Rooms" zu verschlüsseln.

Der sichere Neustart ist standardmäßig aktiviert. Secure Boot ist ein Sicherheitsstandard, der von Mitgliedern der PC-Branche entwickelt wurde, um sicherzustellen, dass ein Gerät nur mit Software startet, die vom Originalgerätehersteller (OEM) als vertrauenswürdig eingestuft wird. Beim Starten des PCs überprüft die Firmware die Signatur der einzelnen Startsoftware, einschließlich UEFI-Firmwaretreibern (auch als Options ROMs bezeichnet), EFI-Anwendungen und dem Betriebssystem. Wenn die Signaturen gültig sind, wird der PC gestartet, und die Firmware übergibt die Steuerung an das Betriebssystem. Weitere Informationen finden Sie unter ["Sicherer Neustart".](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

Der Zugriff auf die Einstellungen für UEFI ist nur über eine physische Tastatur und Maus möglich. Dadurch wird verhindert, dass Sie über die berührungsfähige Konsole "Teams-Räume" sowie über alle anderen bildschirmfähigen Anzeigen, die an Teams Rooms angefügt sind, auf UEFI zugreifen können.

Kernel Direct Memory Access (DMA) Protection ist eine Windows 10-Einstellung, die in Teams Rooms aktiviert wird. Mit diesem Feature schützen das Betriebssystem und die Systemfirmware das System vor böswilligen und unbeabsichtigten DMA-Angriffen für alle DMA-fähigen Geräte:

- Während des Startvorgangs.

- Schutz vor bösartigem DMA durch Geräte, die während der Laufzeit des Betriebssystems mit einfach zugänglichen internen/externen DMA-fähigen Ports verbunden sind, z. B. M.2-PCIe-Slots und Dess 3.

Teams Rooms ermöglicht außerdem hypervisorgeschützte Codeintegrität (Hypervisor protected Code Integrity, HVCI). Eines der Features von HVCI ist Credential Guard. Credential Guard bietet die folgenden Vorteile:

- **Hardwaresicherheit** NTLM, Kerberos und Credential Manager nutzen die Vorteile der Plattformsicherheitsfeatures, einschließlich Secure Boot und Virtualisierung, um Anmeldeinformationen zu schützen.

- **Virtualisierungsbasierte Sicherheit** Von Windows NTLM und Kerberos abgeleitete Anmeldeinformationen und andere geheime Daten werden in einer geschützten Umgebung ausgeführt, die vom ausgeführten Betriebssystem isoliert ist.

- **Besserer Schutz vor erweiterten dauerhaften Bedrohungen** Wenn Anmeldeinformationen für anmeldeinformationen aus der Anmeldeinformationsverwaltung, NTLM und von Kerberos abgeleitete Anmeldeinformationen mithilfe der virtualisierungsbasierten Sicherheit geschützt werden, werden die Methoden und Tools zum Diebstahl von Anmeldeinformationen, die bei vielen gezielten Angriffen verwendet werden, blockiert. Malware, die im Betriebssystem mit Administratorrechten ausgeführt wird, kann keine geheimen Daten extrahieren, die durch virtualisierungsbasierte Sicherheit geschützt sind.

## <a name="software-security"></a>Softwaresicherheit

Nach dem Bootsing von Microsoft Windows meldet sich Teams Rooms automatisch bei einem lokalen Windows-Benutzerkonto namens Skype an. Das Konto hat kein Kennwort. Um die Sitzung des Skype-Kontos sicher zu machen, werden die folgenden Schritte unternommen.

> [!IMPORTANT]
> Ändern Sie nicht das Kennwort, oder bearbeiten Sie das lokale Skype-Benutzerkonto. Dadurch kann verhindert werden, dass sich Teams Rooms automatisch anmelden.

Die Microsoft Teams -Räume-App wird mit der Funktion "Zugewiesener Zugriff" ausgeführt, die in Windows 10 1903 und höher verfügbar ist. "Zugewiesener Zugriff" ist ein Feature in Windows 10, das die Anwendungseinstiegspunkte einschränkt, die für den Benutzer verfügbar gemacht werden. Dadurch wird der Kioskmodus für eine einzelne App aktiviert. Mithilfe der Startprogramm wird Teams Rooms als Kioskgerät konfiguriert, auf dem eine Windows-Desktopanwendung als Benutzeroberfläche ausgeführt wird. Die Microsoft Teams -Räume-App ersetzt die Standardshell (explorer.exe), die normalerweise ausgeführt wird, wenn sich ein Benutzer anmeldet. Mit anderen Worten: Die herkömmliche Explorer-Shell wird überhaupt nicht gestartet. Dadurch wird das Sicherheitsrisiko von Microsoft Teams Rooms in Windows deutlich reduziert. Weitere Informationen finden Sie unter ["Konfigurieren von Kiosken und digitalen Schildern für Windows-Desktopeditionen".](https://docs.microsoft.com/windows/configuration/kiosk-methods)

Wenn Sie sich entschließen, eine Sicherheitsscan oder einen VERGLEICH (Center for Internet Security)-Benchmark für Teams Rooms ausführen, kann die Überprüfung nur im Kontext eines lokalen Administratorkontos ausgeführt werden, da das Skype-Benutzerkonto das Ausführen anderer Anwendungen als der Teams -Chatten-App nicht unterstützt. Viele der auf den Kontext des Skype-Benutzers angewendeten Sicherheitsfeatures gelten nicht für andere lokale Benutzer, und diese Sicherheitsscans stellen die vollständige Sicherheitssperre, die auf das Konto von Skype angewendet wurde, nicht zur Verfügung. Daher wird es nicht empfohlen, eine lokale Überprüfung in Teams Rooms zu starten. Bei Bedarf können Sie jedoch externe Eindringtests durchführen. Aus diesem Grund empfehlen wir, externe Prüfungstests für Teams -Räume-Geräte durchzuführen, anstatt lokale Scans durchzuführen.

Darüber hinaus werden Sperrrichtlinien angewendet, um die Verwendung von nicht administrativen Features zu beschränken. Ein Tastaturfilter ist aktiviert, um potenziell unsichere Tastaturkombinationen abzufangen und zu blockieren, die von den Richtlinien für zugewiesenen Zugriff nicht abgedeckt werden. Nur Benutzer mit lokalen Administratorrechten oder Domänenrechten dürfen sich bei Windows anmelden, um Teams Rooms zu verwalten. Diese und andere Richtlinien, die auf Windows auf Microsoft Teams -Räumen-Geräten angewendet werden, werden während des Produktlebenszyklus kontinuierlich bewertet und getestet.

## <a name="account-security"></a>Kontosicherheit

Geräte in Teams Rooms enthalten ein Administratorkonto namens "Administrator" mit einem Standardkennwort. Es wird dringend empfohlen, das Standardkennwort so bald wie möglich zu ändern, nachdem Sie das Setup abgeschlossen haben.

Das Administratorkonto ist für den ordnungsgemäßen Betrieb von Teams -Räumen-Geräten nicht erforderlich und kann umbenannt oder sogar gelöscht werden. Bevor Sie das Administratorkonto löschen, stellen Sie jedoch sicher, dass Sie ein alternatives lokales Administratorkonto eingerichtet haben, das konfiguriert ist, bevor Sie das Konto entfernen, das mit den Geräten in Teams Rooms versendet wird. Weitere Informationen zum Ändern eines Kennworts für ein lokales Windows-Konto mithilfe von integrierten Windows-Tools oder PowerShell finden Sie in den folgenden Themen:

- [Ändern oder Zurücksetzen Ihres Windows-Kennworts](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

Sie können auch Domänenkonten in die lokale Gruppe "Windows-Administrator" importieren. Sie können dies für Azure -AD-Konten mithilfe von Intune tun. Weitere Informationen finden Sie unter ["Richtlinien-CSP – RestrictedGroups".](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!CAUTION]
> Wenn Sie das Administratorkonto löschen oder deaktivieren, bevor Sie lokale Administratorberechtigungen für ein anderes lokales Konto oder Domänenkonto gewähren, verlieren Sie möglicherweise die Möglichkeit zur Verwaltung des Teams Rooms-Geräts. In diesem Fall müssen Sie das Gerät auf die ursprünglichen Einstellungen zurücksetzen und den Setupvorgang erneut abschließen.
>
> Erteilen Sie keine lokalen Administratorberechtigungen für das Skype-Benutzerkonto.

Windows Configuration Designer kann zum Erstellen von Windows 10-Bereitstellungspaketen verwendet werden. Neben dem Ändern des lokalen Administratorkennworts können Sie auch Dinge wie das Ändern des Computernamens und die Registrierung bei Azure Active Directory tun. Weitere Informationen zum Erstellen eines Bereitstellungspakets im Windows Configuration Designer finden Sie unter ["Bereitstellen von Paketen für Windows 10".](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)

Sie müssen für jedes Gerät in Teams Rooms ein Ressourcenkonto erstellen, damit es sich bei Teams anmelden kann. Sie können für dieses Konto keine zweistufige oder mehrstufige Authentifizierung verwenden. Ein zweiter Faktor würde verhindern, dass sich das Konto nach einem Neustart automatisch bei der Teams -Räume-App anmelden kann. Sie können die moderne Authentifizierung jedoch aktivieren, um zusätzliche Sicherheit für dieses Konto zu gewährleisten. Darüber hinaus können standortbasierte Richtlinien für bedingten Zugriff für das Ressourcenkonto bereitgestellt werden, um zu verhindern, dass sie sich an einem nicht genehmigten Speicherort beim Konto anmelden. Weitere Informationen finden Sie unter Verwenden der [Standortbedingung in einer Richtlinie für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)

Es wird empfohlen, das Ressourcenkonto nach Möglichkeit in Azure AD zu erstellen. Während ein synchronisiertes Konto in Hybridbereitstellungen mit Teams Rooms zusammenarbeiten kann, haben diese synchronisierten Konten häufig Schwierigkeiten bei der Anmeldung bei Teams Rooms und können schwierig zu behandeln sein. Wenn Sie die Anmeldeinformationen für das Ressourcenkonto mithilfe eines Drittanbieterverbunddiensts authentifizieren möchten, stellen Sie sicher, dass der Drittanbieter-IDP mit dem festgelegten Attribut `wsTrustResponse` `urn:oasis:names:tc:SAML:1.0:assertion` antwortet.

## <a name="network-security"></a>Netzwerksicherheit

Im Allgemeinen gelten für Teams Rooms die gleichen Netzwerkanforderungen wie für jeden Microsoft Teams-Client. Der Zugriff über Firewalls und andere Sicherheitsgeräte ist für Teams Rooms der gleiche wie für jeden anderen Microsoft Teams-Client. Speziell für Teams-Räume müssen die Kategorien, die für Teams als "erforderlich" aufgeführt sind, in Ihrer Firewall geöffnet sein. Außerdem benötigen Teams Rooms Zugriff auf Windows Update, Microsoft Store und Microsoft Intune (wenn Sie Microsoft Intune zum Verwalten Ihrer Geräte verwenden). Eine vollständige Liste der für Microsoft Teams Rooms erforderlichen IPs und URLs finden Sie unter:

- **OFFICE** [365-URLs und -IP-Adressbereiche von](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams) Microsoft Teams
- **Windows Update** [WSUS konfigurieren](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft** [Store-Voraussetzungen für den Microsoft Store für Unternehmen und Bildungseinrichtungen](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [Network Enpoints für Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)

Wenn Sie die Komponente "Microsoft Teams Rooms Managed Services" von Microsoft Teams Rooms Premium verwenden, müssen Sie auch sicherstellen, dass Teams Rooms auf die folgenden URLs zugreifen kann:

- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- gj3ft-hub.azure-devices.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- prod-48.westus.logic.azure.com
- prod-08.westus.logic.azure.com
- prod-62.westus.logic.azure.com
- prod-65.westus.logic.azure.com
- prod-05.westus.logic.azure.com

Teams Rooms ist so konfiguriert, dass automatisch mit den neuesten Windows-Updates, einschließlich Sicherheitsupdates, gepatcht wird. Teams Rooms installiert jeden Tag ab 14:00 Uhr alle ausstehenden Updates mithilfe einer vorkonsistenten lokalen Richtlinie. Es ist nicht nötig, zusätzliche Tools zum Bereitstellen und Anwenden von Windows Updates zu verwenden. Die Verwendung zusätzlicher Tools zum Bereitstellen und Anwenden von Updates kann die Installation von Windows Patches verzögern und somit zu einer weniger sicheren Bereitstellung führen. Die App "Teams-Räume" wird über den Microsoft Store bereitgestellt. Wenn Ihre Geräte mit Microsoft Teams Rooms Standard lizenziert sind, werden alle neuen Versionen der App während des nächtlichen Patchprozesses automatisch installiert. Wenn Ihre Geräte mit Microsoft Teams Rooms Premium lizenziert und für den von Microsoft verwalteten Dienst registriert sind, werden neue Versionen der App "Teams-Räume" gemäß Ihrem definierten Rolloutplan installiert.

Geräte in Teams Rooms funktionieren mit den meisten 802.1X- oder anderen netzwerkbasierten Sicherheitsprotokollen. Es ist jedoch nicht möglich, Teams Rooms mit allen möglichen Netzwerksicherheitskonfigurationen zu testen. Wenn daher Leistungsprobleme auftreten, die auf Netzwerkleistungsprobleme zurückverfolgt werden können, müssen Sie diese Protokolle möglicherweise deaktivieren, wenn sie in Ihrer Organisation konfiguriert sind.

Für eine optimale Leistung von Echtzeitmedien wird dringend empfohlen, den Medienverkehr in Teams so zu konfigurieren, dass Proxyserver und andere Netzwerksicherheitsgeräte umgangen werden. Echtzeitmedien sind sehr latenzempfindlich, und Proxyserver und Netzwerksicherheitsgeräte können die Video- und Audioqualität der Benutzer erheblich beeinträchtigen. Da Die Medien in Teams bereits verschlüsselt sind, ist es außerdem nicht von Vorteil, den Datenverkehr über einen Proxyserver zu übergeben. Weitere Informationen finden Sie unter "Netzwerk (in die [Cloud)"](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) – der Sichtpunkt eines Architekturadministrators, in dem Netzwerkempfehlungen zur Verbesserung der Leistung von Medien mit Microsoft Teams und Microsoft Teams Rooms erörtert werden.

> [!IMPORTANT]
> Teams Rooms unterstützt keine authentifizierten Proxyserver.

Geräte in Teams Rooms müssen keine Verbindung mit einem internen LAN herstellen. Erwägen Sie, Teams Rooms in einem sicheren Netzwerksegment mit direktem Internetzugriff zu platzieren. Wenn Ihr internes LAN gefährdet wird, werden die Möglichkeiten des Angriffsvektors in Richtung Teams Rooms verringert.

Es wird dringend empfohlen, Ihre Teams -Räume-Geräte mit einem verkabelten Netzwerk zu verbinden. Die Verwendung von Funknetzwerken auf Teams Rooms-Geräten wird nicht empfohlen oder zertifiziert. Einige Konnektivitätsfeatures wie Wi-Fi sind standardmäßig deaktiviert.

Näherungsteil nehmen Sie an und andere Features von Teams-Bluetooth. Die Implementierung der Bluetooth Teams Rooms ermöglicht jedoch keine Verbindung mit einem externen Gerät mit einem Teams Rooms-Gerät. Bluetooth Technologienutzung auf Teams Rooms-Geräten ist derzeit auf Werbebeacons und aufforderungsbefällige Proximalverbindungen beschränkt. Der `ADV_NONCONN_INT` Typ der Protokolldateneinheit (PDU) wird im Werbebeacons verwendet. Dieser PDU-Typ ist für nicht verbindende Geräte, die Informationen an das Lauschengerät anzeigen. Im Rahmen dieser Bluetooth ist keine Gerätekopplung möglich. Weitere Details zu Bluetooth Protokollen finden Sie auf der [Bluetooth SIG-Website.](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)

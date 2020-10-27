---
title: Hardwareanforderungen für Microsoft Teams
ms.reviewer: microthk, sthurlow
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: In diesem Artikel erfahren Sie mehr über die Hardwareanforderungen, die zum Installieren und Ausführen von Microsoft Teams erforderlich sind.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5aeeee4bf16a05b24056a6602f008b5ecaee12bb
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766758"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Hardwareanforderungen für Microsoft Teams

Alle Voraussetzungen in den folgenden Abschnitten gelten sowohl für die Microsoft Teams-Desktop-App als auch für die Teams-Web-App.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Hardwareanforderungen für Teams auf einem Windows-PC

| Komponente | Anforderung |
|---------|---------|
|Computer und Prozessor    | Mindestens 1,6 GHz (oder höher), 2 Core        |
|Arbeitsspeicher     |    4,0 GB Arbeitsspeicher     |
|Festplatte    | PC: 3,0 GB verfügbarer Speicherplatz        |
|Anzeige    |   Bildschirmauflösung von 1024 x 768 Pixel |
|Grafikhardware |  Windows-Betriebssystem: die Grafikhardwarebeschleunigung erfordert DirectX 9 oder höher, mit WDDM 2,0 oder höher für Windows 10 (oder WDDM 1,3 oder höher für Windows 10 Fall Creators Update).
|Betriebssystem  |    Windows 10, Windows 10 auf dem Arm, Windows 8,1, Windows Server 2019, Windows Server 2016|
|.NET-Version    |  Setzt .NET 4.5 CLR oder später voraus       |
|Video    |  USB 2.0-Videokamera       |
|Geräte    |   Standardmäßige Laptopkamera, Mikrofon und Lautsprecher    |
|Videoanrufe und Besprechungen|<ul><li>Erfordert 2-Core-Prozessor. Für höhere Video-und Bildschirmfreigabe Auflösung und Bildrate empfiehlt sich ein 4-Core-Prozessor oder besser.</li> <li>Für Hintergrund Videoeffekte ist Windows 10 oder ein Prozessor mit AVX2-Befehlssatz erforderlich.</li> <li>Eine Liste der nicht unterstützten Decoder und Encoder finden Sie unter [Empfehlungen für Hardware-Decoder- und -Encoder-Treiber](hardware-decoders-and-encoders.md).</li><li>Für die Teilnahme an einer Besprechung mithilfe der Näherungs Erkennung in einem Microsoft Teams-Raum ist Bluetooth Le erforderlich, für die Bluetooth auf dem Clientgerät aktiviert werden muss, und für Windows-Clients ist auch der 64-Bit-Client für Teams erforderlich. Dieses Feature ist auf Clients mit 32-Bit-Teams nicht verfügbar.</li></ul> |
|Teams-Liveereignisse | Wenn Sie ein Live-Event für Teams erstellen, empfehlen wir die Verwendung eines Computers mit einem Core i5 Kaby Lake-Prozessor, 4,0-GB-RAM (oder höher) und Hardware-Encoder. Eine Liste der nicht **unterstützten** Dekodierer und Encoder finden Sie unter [Empfehlungen für Hardware-Decoder und Encoder-Treiber](hardware-decoders-and-encoders.md) . |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Hardwareanforderungen für Teams auf einem Mac

| Komponente | Anforderung |
|---------|---------|
|Computer und Prozessor    | Intel Core Duo-Prozessor |
|Arbeitsspeicher     |   4,0 GB Arbeitsspeicher      |
|Festplatte    |   1,5 GB verfügbarer Speicherplatz      |
|Anzeige    | Bildschirmauflösung 1280x800 oder höher    |
|Betriebssystem  |    Eine der drei neuesten Versionen von macOS. [Hier](https://support.apple.com/en-us/HT201260)finden Sie Informationen zu den neuesten Versionen von MacOS und dazu, wie Sie Ihre Version von MacOS aktualisieren können. Wenn beispielsweise eine neue Version von macOS veröffentlicht wird, werden die neue Version und die beiden unmittelbar vor ihr verwendeten Versionen zur unterstützten Version.      |
|Video  |    Kompatible Webcam     |
|VoIP    |  Kompatibles Mikrofon und Lautsprecher, Headset mit Mikrofon oder entsprechendes Gerät       |
|Videoanrufe und Besprechungen | <ul><li>Erfordert 2-Core-Prozessor. Für höhere Video-und Bildschirmfreigabe Auflösung und Bildrate empfiehlt sich ein 4-Core-Prozessor oder besser. </li><li>Die Teilnahme an einer Besprechung mithilfe der Näherungs Erkennung in einem Microsoft Teams-Chatroom steht unter macOS nicht zur Verfügung.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Hardwareanforderungen für Teams unter Linux

| Komponente | Anforderung |
|---------|---------|
|Computer und Prozessor    | 1,6 GHz (oder höher) (32-Bit oder 64-Bit), 2 Core        |
|Arbeitsspeicher     |    4,0 GB Arbeitsspeicher     |
|Festplatte    | PC: 3,0 GB verfügbarer Speicherplatz        |
|Anzeige    |   Bildschirmauflösung von 1024 x 768 Pixel |
|Grafikhardware |  128 MB Grafikspeicher
|Betriebssystem  | Linux-Verteilung, die DEB oder RPM installieren kann. |
|Video    |  USB 2.0-Videokamera       |
|Geräte    |   Standardmäßige Laptopkamera, Mikrofon und Lautsprecher    |
|VoIP    |  Kompatibles Mikrofon und Lautsprecher, Headset mit Mikrofon oder entsprechendes Gerät       |
|Videoanrufe und Besprechungen | <ul><li>Erfordert 2-Core-Prozessor. Für höhere Video-und Bildschirmfreigabe Auflösung und Bildrate empfiehlt sich ein 4-Core-Prozessor oder besser.</li><li>Das Beitreten zu einer Besprechung mit Proximity Detection in einem Microsoft Teams-Raum ist unter Linux nicht verfügbar.</li></ul>
|Unterstützte Linux-Verteilungen | Ubuntu 18,04 LTS, 20,04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8       |
|Unterstützte Desktop Umgebung | GNOME, KDE       |
|Unterstützter Anzeige Server | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Hardwareanforderungen für Teams auf mobilen Geräten

Sie können Teams auf diesen mobilen Plattformen verwenden:

- Android: kompatibel mit Android-Smartphones und-Tablets.

  Der Support ist auf die **letzten vier** Hauptversionen von Android limitiert. Wenn beispielsweise eine neue Hauptversion von Android veröffentlicht wird, ist die Android-Anforderung die neue Version und die drei neuesten Versionen, die Ihr vorangestellt sind.

- iOS: kompatibel mit iPhone, iPad und iPod Touch.

  Der Support ist auf die **beiden** neuesten Hauptversionen von IOS limitiert. Wenn beispielsweise eine neue Hauptversion von IOS veröffentlicht wird, ist die IOS-Anforderung die neue Version und die neuesten Versionen, die ihr vorausgegangen sind. Der optionale Blur-Effekt " **mein Hintergrund** Video" für IOS erfordert ein Betriebssystem von IOS 12 oder höher, das mit den folgenden Geräten kompatibel ist: iPhone 7 oder höher, iPad 2018 (sechste Generation) oder höher und iPod Touch 2019 (7. Generation).

> [!Note]
> Für eine optimale Benutzererfahrung verwenden Sie die jeweils neueste Version von iOS und Android.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Hardwareanforderungen für Teams in einer VDI-Umgebung (Virtual Desktop Infrastructure)

Die Anforderungen für die Ausführung von Teams in einer virtualisierten Umgebung finden Sie unter [Teams für virtualisierte Desktop-Infrastruktur](teams-for-vdi.md).

### <a name="related-topics"></a>Verwandte Themen

- [Holen Sie sich Teams-Apps](get-clients.md)
- [Microsoft Teams auf mobilen Geräten](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Installieren der Microsoft Teams-App mithilfe von MSI](msi-deployment.md)
- [Limits und Spezifikationen für Microsoft Teams](limits-specifications-teams.md)

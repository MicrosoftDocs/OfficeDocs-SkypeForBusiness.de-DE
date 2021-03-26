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
- m365initiative-deployteams
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
ms.openlocfilehash: f5e6668229ef481d0b6c30683540c060495e0f21
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262352"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Hardwareanforderungen für Microsoft Teams

Alle Voraussetzungen in den folgenden Abschnitten gelten sowohl für die Microsoft Teams-Desktop-App als auch für die Teams-Web-App.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Hardwareanforderungen für Teams auf einem Windows-PC

| Komponente | Anforderung |
|---------|---------|
|Computer und Prozessor    | Mindestens 1,6 GHz (oder höher), 2-Core-Prozessor<br><br>Hinweis: Bei Intel-Prozessoren muss die maximale Geschwindigkeit, die mit der Intel-Turbo-Boost-Technologie (Max.         |
|Arbeitsspeicher     |    4,0 GB RAM     |
|Festplatte    | PC: 3,0 GB verfügbarer Speicherplatz        |
|Anzeige    |   Bildschirmauflösung von 1024 x 768 Pixel |
|Grafikhardware |  Windows-Betriebssystem: Grafikhardwarebeschleunigung erfordert DirectX 9 oder höher, mit WDDM 2.0 oder höher für Windows 10 (oder WDDM 1.3 oder höher für Windows 10 Fall Creators Update)
|Betriebssystem  |    Windows 10, Windows 10 für ARM, Windows 8.1, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2|
|.NET-Version    |  Setzt .NET 4.5 CLR oder später voraus       |
|Video    |  USB 2.0-Videokamera       |
|Geräte    |   Standardmäßige Laptopkamera, Mikrofon und Lautsprecher    |
|Videoanrufe und Besprechungen|<ul><li>Erfordert einen 2-Core-Prozessor. Bei einer höheren Video-/Bildschirmfreigabeauflösung und Bildrate wird ein 4-Core-Prozessor oder ein besserer Prozessor empfohlen.</li> <li>Hintergrundvideoeffekte erfordern Windows 10 oder einen Prozessor mit AVX2-Anweisungssatz.</li> <li>Eine Liste der nicht unterstützten Decoder und Encoder finden Sie unter [Empfehlungen für Hardware-Decoder- und -Encoder-Treiber](hardware-decoders-and-encoders.md).</li><li>Für die Teilnahme an einer Besprechung mithilfe von Proximity Detection in einem Microsoft Teams-Raum ist Bluetooth LE erforderlich, wodurch Bluetooth auf dem Clientgerät aktiviert und für Windows-Clients der 64-Bit-Team-Client erforderlich ist. Dieses Feature ist auf 32-Bit-Teams-Clients nicht verfügbar.</li></ul> |
|Teams-Liveereignisse | Wenn Sie ein Liveereignis mit Teams durchführen, empfehlen wir die Verwendung eines Computers mit einem Core i5 Kaby Lake-Prozessor, 4.0 GB RAM (oder höher) und Hardware-Encoder. Eine Liste der **nicht unterstützten** Decoder und Encoder finden Sie unter [Empfehlungen für Hardware-Decoder- und -Encoder-Treiber](hardware-decoders-and-encoders.md). |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Hardwareanforderungen für Teams auf einem Mac

| Komponente | Anforderung |
|---------|---------|
|Computer und Prozessor    | Intel Core Duo-Prozessor |
|Arbeitsspeicher     |   4,0 GB RAM      |
|Festplatte    |   1,5 GB verfügbarer Speicherplatz      |
|Anzeige    | Bildschirmauflösung 1280x800 oder höher    |
|Betriebssystem  |    Eine der drei neuesten Versionen von macOS. [Hier](https://support.apple.com/en-us/HT201260) finden Sie Informationen zu den neuesten Versionen von macOS sowie zum Upgrade Ihrer macOS-Version. Wenn beispielsweise eine neue macOS-Version veröffentlicht wird, werden die neue Version und die beiden unmittelbar davor die unterstützten Versionen.      |
|Video  |    Kompatible Webcam     |
|VoIP    |  Kompatibles Mikrofon und Lautsprecher, Headset mit Mikrofon oder entsprechendes Gerät       |
|Videoanrufe und Besprechungen | <ul><li>Erfordert einen 2-Core-Prozessor. Bei einer höheren Video-/Bildschirmfreigabeauflösung und Bildrate wird ein 4-Core-Prozessor oder ein besserer Prozessor empfohlen. </li><li>Das Beitreten zu einer Besprechung mit Proximity Detection in einem Microsoft Teams-Raum ist unter macOS nicht verfügbar.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Hardwareanforderungen für Teams unter Linux

| Komponente | Anforderung |
|---------|---------|
|Computer und Prozessor    | Mindestens 1,6 GHz (oder höher) (32-Bit oder 64-Bit), 2-Core-Prozessor        |
|Arbeitsspeicher     |    4,0 GB RAM     |
|Festplatte    | PC: 3,0 GB verfügbarer Speicherplatz        |
|Anzeige    |   Bildschirmauflösung von 1024 x 768 Pixel |
|Grafikhardware |  Mindestens 128 MB Grafikspeicher
|Betriebssystem  | Linux-Verteilung, die DEB oder RPM installieren kann. |
|Video    |  USB 2.0-Videokamera       |
|Geräte    |   Standardmäßige Laptopkamera, Mikrofon und Lautsprecher    |
|VoIP    |  Kompatibles Mikrofon und Lautsprecher, Headset mit Mikrofon oder entsprechendes Gerät       |
|Videoanrufe und Besprechungen | <ul><li>Erfordert einen 2-Core-Prozessor. Bei einer höheren Video-/Bildschirmfreigabeauflösung und Bildrate wird ein 4-Core-Prozessor oder ein besserer Prozessor empfohlen.</li><li>Das Beitreten zu einer Besprechung mit Proximity Detection in einem Microsoft Teams-Raum ist unter Linux nicht verfügbar.</li></ul>
|Unterstützte Linux-Verteilungen | Ubuntu 18.04 LTS, 20.04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8       |
|Unterstützte Desktopumgebung | GNOME, KDE       |
|Unterstützter Anzeigeserver | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Hardwareanforderungen für Teams auf mobilen Geräten

Sie können Teams auf diesen mobilen Plattformen verwenden:

- Android: kompatibel mit Android-Smartphones und-Tablets.

  Der Support ist auf die **letzten vier** Hauptversionen von Android begrenzt. Wenn beispielsweise eine neue Hauptversion von Android veröffentlicht wird, ist die Android-Anforderung und die drei neuesten Vorgängerversionen die neue Version.

- iOS: kompatibel mit iPhone, iPad und iPod Touch.

  Der Support ist auf die **beiden** neuesten Hauptversionen von iOS beschränkt. Wenn beispielsweise eine neue Hauptversion von iOS veröffentlicht wird, ist die iOS-Anforderung und die drei neuesten Vorgängerversionen die neue Version. Der optionale Videoeffekt **Meinen Hintergrund weichzeichnen** unter iOS erfordert das Betriebssystem iOS 12 oder höher, das mit den folgenden Geräten kompatibel ist: iPhone 7 oder höher, iPad 2018 (6. Generation) oder höher und iPod Touch 2019 (7. Generation).

> [!Note]
> Für eine optimale Benutzererfahrung verwenden Sie die jeweils neueste Version von iOS und Android.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Hardwareanforderungen für Teams in einer VDI-Umgebung (Virtual Desktop Infrastructure)

Die Anforderungen für die Ausführung von Teams in einer virtualisierten Umgebung finden Sie unter [Teams für virtualisierte Desktop-Infrastruktur](teams-for-vdi.md).

### <a name="related-topics"></a>Verwandte Themen

- [Holen Sie sich Teams-Apps](get-clients.md)
- [Microsoft Teams auf mobilen Geräten](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Installieren der Microsoft Teams-App mithilfe von MSI](msi-deployment.md)
- [Limits und Spezifikationen für Microsoft Teams](limits-specifications-teams.md)

---
title: Hardwareanforderungen für Microsoft Teams
ms.reviewer: microthk, sthurlow
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.localizationpriority: high
search.appverid: MET150
description: In diesem Artikel erfahren Sie mehr über die Hardwareanforderungen, die zum Installieren und Ausführen von Microsoft Teams erforderlich sind.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 707360ec39e82c86732433e42752cedbdb649119
ms.sourcegitcommit: 17f4baf85e1ac6a2af5f5c6ea2d5aae763efd917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2022
ms.locfileid: "67405127"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Hardwareanforderungen für Microsoft Teams

Alle Voraussetzungen in den folgenden Abschnitten gelten sowohl für die Microsoft Teams-Desktop-App als auch für die Teams-Web-App.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Hardwareanforderungen für Teams auf einem Windows-PC

| Komponente | Anforderung |
|---------|---------|
|Computer und Prozessor    | Mindestens 1,1 GHz oder schneller, zwei Kerne<br><br>Bei Intel-Prozessoren muss die mit der Intel Turbo Boost-Technologie erreichte maximale Geschwindigkeit (max. Turbo-Frequenz) berücksichtigt werden         |
|Arbeitsspeicher     |  4,0 GB RAM |
|Festplatte    | PC: 3,0 GB verfügbarer Speicherplatz        |
|Anzeige    |   Bildschirmauflösung von 1024 x 768 Pixel |
|Grafikhardware |  Windows-Betriebssystem: Grafikhardwarebeschleunigung erfordert DirectX 9 oder höher, mit WDDM 2.0 oder höher für Windows 10 (oder WDDM 1.3 oder höher für Windows 10 Fall Creators Update)
|Betriebssystem  |    Windows 11, Windows 10 ( ausgenommen Windows 10 LTSC für Teams-Desktop-App), Windows 10 auf ARM, Windows 8.1, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2. Hinweis: Wir empfehlen die Verwendung der neuesten Windows-Version und der verfügbaren Sicherheitspatches.|
|.NET-Version    |  Setzt .NET 4.5 CLR oder später voraus       |
|Video    |  USB 2.0-Videokamera       |
|Geräte    |   Standardmäßige Laptopkamera, Mikrofon und Lautsprecher    |
|Videoanrufe und Besprechungen|<ul><li>Erfordert einen Prozessor mit zwei Kernen. Für eine höhere Auflösung und Bildfrequenz bei der Video-/Bildschirmfreigabe wird ein Prozessor mit vier Kernen oder mehr empfohlen.</li> <li>Hintergrundvideoeffekte erfordern Windows 10 oder einen Prozessor mit AVX2-Anweisungssatz.</li> <li>Eine Liste der nicht unterstützten Decoder und Encoder finden Sie unter [Empfehlungen für Hardware-Decoder- und -Encoder-Treiber](hardware-decoders-and-encoders.md).</li><li>Für die Teilnahme an einer Besprechung mithilfe der Näherungserkennung in einem Microsoft Teams-Raum ist Bluetooth LE erforderlich. Bluetooth LE unter Windows erfordert, dass Bluetooth auf dem Clientgerät aktiviert ist, und erfordert die 64-Bit-Version des Teams-Clients. Dieses Feature ist auf 32-Bit-Teams-Clients nicht verfügbar.</li></ul> |
|Teams-Liveereignisse | Wenn Sie ein Liveereignis mit Teams durchführen, empfehlen wir die Verwendung eines Computers mit einem Core i5 Kaby Lake-Prozessor, 4.0 GB RAM (oder höher) und Hardware-Encoder. Eine Liste der **nicht unterstützten** Decoder und Encoder finden Sie unter [Empfehlungen für Hardware-Decoder- und -Encoder-Treiber](hardware-decoders-and-encoders.md). |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Hardwareanforderungen für Teams auf einem Mac

| Komponente | Anforderung |
|---------|---------|
|Computer und Prozessor    | Intel Core Duo-Prozessor |
|Arbeitsspeicher     |   4,0 GB RAM|
|Festplatte    |   1,5 GB verfügbarer Speicherplatz      |
|Anzeige    | Bildschirmauflösung 1280x800 oder höher    |
|Betriebssystem  |    Eine der drei neuesten Versionen von macOS. [Hier](https://support.apple.com/en-us/HT201260) finden Sie Informationen zu den neuesten Versionen von macOS sowie zum Upgrade Ihrer macOS-Version. Wenn beispielsweise eine neue macOS-Version veröffentlicht wird, werden die neue Version und die beiden unmittelbar davor die unterstützten Versionen.      |
|Video  |    Kompatible Webcam     |
|VoIP    |  Kompatibles Mikrofon und Lautsprecher, Headset mit Mikrofon oder entsprechendes Gerät       |
|Videoanrufe und Besprechungen | <ul><li>Erfordert einen Prozessor mit zwei Kernen. Für eine höhere Auflösung und Bildfrequenz bei der Video-/Bildschirmfreigabe wird ein Prozessor mit vier Kernen oder mehr empfohlen. </li><li>Für die Teilnahme an einer Besprechung mithilfe der Näherungserkennung in einem Microsoft Teams-Raum ist Bluetooth LE erforderlich. Bluetooth LE erfordert, dass Bluetooth auf dem Clientgerät aktiviert ist.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Hardwareanforderungen für Teams unter Linux

| Komponente | Anforderung |
|---------|---------|
|Computer und Prozessor    | Mindestens 1,6 GHz (oder höher) (32-Bit oder 64-Bit), 2-Core-Prozessor        |
|Arbeitsspeicher     |    4,0 GB RAM |
|Festplatte    | PC: 3,0 GB verfügbarer Speicherplatz        |
|Anzeige    |   Bildschirmauflösung von 1024 x 768 Pixel |
|Grafikhardware |  Mindestens 128 MB Grafikspeicher
|Betriebssystem  | Linux-Verteilung, die DEB oder RPM installieren kann. |
|Video    |  USB 2.0-Videokamera       |
|Geräte    |   Standardmäßige Laptopkamera, Mikrofon und Lautsprecher    |
|VoIP    |  Kompatibles Mikrofon und Lautsprecher, Headset mit Mikrofon oder entsprechendes Gerät       |
|Videoanrufe und Besprechungen | <ul><li>Erfordert einen Prozessor mit zwei Kernen. Für eine höhere Auflösung und Bildfrequenz bei der Video-/Bildschirmfreigabe wird ein Prozessor mit vier Kernen oder mehr empfohlen.</li><li>Das Beitreten zu einer Besprechung mit Proximity Detection in einem Microsoft Teams-Raum ist unter Linux nicht verfügbar.</li></ul>
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
- [Microsoft Teams auf mobilen Geräten](https://support.microsoft.com/office/set-up-your-teams-mobile-apps-1ba8dce3-1122-47f4-8db6-00a4f93117e8)
- [Installieren der Microsoft Teams-App mithilfe von MSI](msi-deployment.md)
- [Limits und Spezifikationen für Microsoft Teams](limits-specifications-teams.md)

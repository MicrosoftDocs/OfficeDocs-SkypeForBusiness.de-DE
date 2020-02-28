---
title: Hardware Anforderungen für Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Informieren Sie sich über die Hardwareanforderungen, die zum Installieren und Ausführen von Microsoft Teams erforderlich sind.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65de6266af5d7b17234cd3b77d867176338d35fa
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327857"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Hardware Anforderungen für Microsoft Teams

Alle Anforderungen in den folgenden Abschnitten gelten sowohl für die Microsoft Teams-Desktop-App als auch für die Team-Web-App.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Hardware Anforderungen für Teams auf einem Windows-PC

|**Komponente**|**Anforderung**  |
|---------|---------|
|Computer und Prozessor    | Mindestens 1,6 GHz (oder höher) (32-Bit oder 64-Bit).        |
|Arbeitsspeicher     |    2,0 GB Arbeitsspeicher     |
|Festplatte    | 3,0 GB verfügbarer Speicherplatz        |
|Anzeige    |   1024 x 768 Bildschirmauflösung |
|Grafikhardware |  Minimaler 128 MB-Grafikspeicher
|Betriebssystem  |    Windows Server 2012 R2 +, Windows 10 oder Windows 8,1 in 32-Bit und 64-Bit. Für ein optimales Nutzungserlebnis verwenden Sie die neueste Version Ihres Betriebssystems.|
|.NET-Version    |  Erfordert .NET 4,5 CLR oder höher       |
|Video    |  USB 2,0-Videokamera       |
|Geräte    |   Standard-Laptop Kamera,-Mikrofon und-Lautsprecher    | 
|Video Anrufe und Besprechungen | <ul><li>Für eine bessere Nutzung von Videoanrufen und Onlinebesprechungen empfiehlt es sich, einen Computer mit einem 2,0 GHz-Prozessor und 4,0 GB RAM (oder höher) zu verwenden. </li><li>Der optionale **Hintergrund** Videoeffekt "Blur" erfordert einen Prozessor mit erweiterter Vector Extensions 2 (AVX2)-Unterstützung. Eine Liste der nicht unterstützten Dekodierer und Encoder finden Sie unter [Empfehlungen für Hardware-Decoder und Encoder-Treiber](hardware-decoders-and-encoders.md) .</li><li>Für die Teilnahme an einer Besprechung mithilfe der Näherungs Erkennung in einem Microsoft Teams-Chatroom ist Bluetooth Le erforderlich, bei dem Bluetooth auf dem Clientgerät aktiviert werden muss und für Windows-Clients der 64-Bit Teams-Client erforderlich ist. Es ist nicht auf 32-Bit-Teams-Clients verfügbar.</li></ul> |
|Teams-Liveereignisse | Wenn Sie ein Live-Event für Teams erstellen, empfehlen wir die Verwendung eines Computers mit einem Core i5 Kaby Lake-Prozessor, 4,0 GB RAM (oder höher) und Hardware-Encoder. Eine Liste der nicht unterstützten Dekodierer und Encoder finden Sie unter [Empfehlungen für Hardware-Decoder und Encoder-Treiber](hardware-decoders-and-encoders.md) . |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Hardware Anforderungen für Teams auf einem Mac

|**Komponente**|**Anforderung**  |
|---------|---------|
|Prozessor    | Mindestens Intel-Prozessor, Core 2 Duo oder höher |
|Arbeitsspeicher     |   2,0 GB Arbeitsspeicher      |
|Festplatte    |   1,5 GB verfügbarer Speicherplatz      |
|Anzeige    | 1280 x 800 oder höhere Auflösung    |
|Betriebssystem  |    Mac OS X 10,11 El Capitan oder höher     |
|Video  |    Kompatible Webcam     |
|VoIP    |  Kompatible Mikrofone und Lautsprecher, Headset mit Mikrofon oder entsprechendes Gerät       |
|Video Anrufe und Besprechungen | Für eine bessere Nutzung von Videoanrufen und Onlinebesprechungen empfiehlt es sich, einen Computer mit einem 2,0 GHz-Prozessor und 4,0 GB RAM (oder höher) zu verwenden.  <ul><li>Der optionale **Hintergrund** Videoeffekt "Blur" erfordert einen Prozessor mit erweiterter Vector Extensions 2 (AVX2)-Unterstützung, der auf den meisten späten 2013-Mac-Geräten und höher unterstützt wird. Eine Liste der nicht unterstützten Dekodierer und Encoder finden Sie unter [Empfehlungen für Hardware-Decoder und Encoder-Treiber](hardware-decoders-and-encoders.md) .</li><li>Die Teilnahme an einer Besprechung mithilfe der Näherungs Erkennung in einem Microsoft Teams-Chatroom steht unter Mac OS nicht zur Verfügung.</li></ul> |

## <a name="hardware-requirements-for-teams-on-linux"></a>Hardware Anforderungen für Teams unter Linux

|**Komponente**|**Anforderung**  |
|---------|---------|
|Computer und Prozessor    | Mindestens 1,6 GHz (oder höher) (32-Bit oder 64-Bit).        |
|Arbeitsspeicher     |    2,0 GB Arbeitsspeicher     |
|Festplatte    | 3,0 GB verfügbarer Speicherplatz        |
|Anzeige    |   1024 x 768 Bildschirmauflösung |
|Grafikhardware |  Minimaler 128 MB-Grafikspeicher
|Betriebssystem  | Linux-Distribution, die deb oder RPM installieren kann. |
|Video    |  USB 2,0-Videokamera       |
|Geräte    |   Standard-Laptop Kamera,-Mikrofon und-Lautsprecher    | 
|VoIP    |  Kompatible Mikrofone und Lautsprecher, Headset mit Mikrofon oder entsprechendes Gerät       |
|Video Anrufe und Besprechungen | <ul><li>Für eine bessere Nutzung von Videoanrufen und Onlinebesprechungen empfiehlt es sich, einen Computer mit einem 2,0 GHz-Prozessor und 4,0 GB RAM (oder höher) zu verwenden. </li><li>Der optionale Hintergrund Videoeffekt "Blur" erfordert einen Prozessor mit erweiterter Vector Extensions 2 (AVX2)-Unterstützung, der auf den meisten späten 2013-Mac-Geräten und höher unterstützt wird. Eine Liste der nicht unterstützten Dekodierer und Encoder finden Sie unter [Empfehlungen für Hardware-Decoder und Encoder-Treiber](hardware-decoders-and-encoders.md) .</li><li>Die Teilnahme an einer Besprechung mithilfe der Näherungs Erkennung in einem Microsoft Teams-Chatroom steht unter Linux nicht zur Verfügung.</li></ul>
|Unterstützte Linux-Distributionen | Ubuntu 16,04 LTS, 18,04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Hardware Anforderungen für Teams auf mobilen Geräten

Sie können Teams auf diesen mobilen Plattformen verwenden:

- Android: kompatibel mit Android-Smartphones und-Tablets.

  Der Support ist auf die letzten vier Hauptversionen von Android limitiert. Wenn eine neue Hauptversion von Android veröffentlicht wird, werden die neue Version und die vorherigen drei Versionen offiziell unterstützt.

- iOS: kompatibel mit iPhone, iPad und iPod Touch.

  Der Support ist auf die beiden neuesten Hauptversionen von IOS limitiert. Wenn eine neue Hauptversion von IOS veröffentlicht wird, werden die neue Version von IOS und die vorherige Version offiziell unterstützt.

Verwenden Sie die neueste Version von IOS und Android, um die besten Erfahrungen mit Teams zu finden.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Hardware Anforderungen für Teams in einer VDI-Umgebung (Virtual Desktop Infrastructure)

Informationen zu den Anforderungen für die Ausführung von Teams in einer virtualisierten Umgebung finden Sie unter [Teams für virtualisierte Desktop Infrastruktur](teams-for-vdi.md) .

### <a name="related-topics"></a>Verwandte Themen
- [Abrufen von Teams-apps](get-clients.md)
- [Microsoft Teams auf mobilen Geräten](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Installieren der Microsoft Teams-App mithilfe einer MSI-Anwendung](msi-deployment.md)
- [Limits und Spezifikationen für Microsoft Teams](limits-specifications-teams.md)

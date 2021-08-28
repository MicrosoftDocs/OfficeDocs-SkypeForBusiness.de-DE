---
title: Erfahren Sie, wie Sie Inhaltskameras einrichten – Microsoft Teams
ms.author: serdars
author: serdarsoysal
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
description: Verwenden Sie eine Inhaltskamera in einem Microsoft Teams Raum, der mit Bildverarbeitungssoftware interagiert, um Präsentierenden das Zeichnen auf einem analogen Whiteboard zu ermöglichen.
ms.openlocfilehash: e24a90e65a5d844a5431951283153a5de2406498
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613004"
---
# <a name="content-cameras"></a>Inhalts-Kameras

Sie können jetzt eine Inhaltskamera mit einem Raumsystem Microsoft Teams verwenden. Eine Inhaltskamera interagiert mit spezieller Bildverarbeitungssoftware und einem Whiteboard, damit ein Moderator auf einem analogen Whiteboard zeichnen und den Inhalt für Remoteteilnehmer freigeben kann.

Im folgenden Video finden Sie Beispiele für die Funktionen der Inhaltskamera.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>Einrichten einer Inhaltskamera

> [!NOTE]
> Halten Sie sich immer an den Gebäudecode Ihres Landes oder Ihrer Region, der einen Mindestabstand vom Boden definieren kann oder eine Anforderung definiert, dass deckende Ausrüstung mit einer Dacheinrichtung oder einer anderen Struktur gesichert werden muss. Befolgen Sie die Anweisungen zur Aufnahme für die Hardware, die mit der ausgewählten Kamera bereitgestellt wird. OEM-Kamerakamerakits umfassen eine Kamera, USB 2.0-Erweiterungs-Sets und erforderliche Verkabelung.

Die Größe des whiteboards, das für die Freigabe verwendet wird, wirkt sich auf die Platzierung der Kamera aus. Empfehlungen für die Boardgröße:

- 3–6 ft (0,9-1,8 m) breit – Unterstützt
- 1,8 bis 2,7 m breit – Empfohlen
- 9–12 ft (2,7-3,6 m) breit – Unterstützt
- Über 12 ft (3,6 m) breit – Die Kamera ist 2,7 bis 3,6 m breit und zu sehr für den Rest.

## <a name="camera-location"></a>Kameraposition

Die ideale Platzierung einer Inhaltskamera ist vertikal und horizontal auf dem Whiteboard ausgerichtet. Lokale Gebäudecodes können Höhenbeschränkungen haben, die erfordern, dass die Kamera über den oberen Rand des Whiteboards hinaus gehoben wird.

Sie können die Kamera bis zu 6 in installieren. (152 mm) höher als der obere Rand des Whiteboards und auf dem Whiteboard zentriert, wie gezeigt. Stellen Sie sicher, dass das Kamerabild mindestens einen 6-In-Inhalt umfasst. (152 mm) Rahmen auf beiden Seiten horizontal. Sie können die Kameravorschau in der App Microsoft Teams-Räume, um die endgültige Platzierung der Kamera zu ermitteln.

![Content camera placement diagram](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>Kameraabstände

Die optimale Remote-Benutzererfahrung bei Verwendung typischer Whiteboardmarkierungen besteht in der Freigabe von Freihandstrichen im Bereich von 1 bis 2 mm pro Pixel im Kamerabild des Inhalts, und für die besten Ergebnisse werden 1,5 mm pro Pixel verwendet. Alle unterstützten Kameras bieten eine Auflösung von 1920 x 1080, und einige können diese Auflösung überschreiten.

Die Entfernung der Kamera vom Whiteboard kombiniert mit der Kameraauflösung und HFoV, um den Abstand zum Whiteboard zu bestimmen. Die folgende Tabelle enthält Beispiele für Entfernungen für verschiedene Whiteboardgrößen. Sie können diese Werte als Ausgangspunkte verwenden, um die endgültige Platzierung der Inhaltskamera zu ermitteln.

**Kameraabstand vom Whiteboard**

| Camera HFoV |3 ft. (0,91 m)     | 6 ft. (1,8 m)    | 9 ft. (2,74 m)        |12 ft.  (3,65 m)         | Maximale Entfernung von Whiteboard  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80°         | 1,79 ft (0,54 m) | 3,58 ft ( 1,09 m)  | 5,36 ft (1,6 m)    |7,15 ft (2,17 m) |7,51 ft (2,28 m) |
| 90°         | 1,5 ft (0,45 m) | 3,00 ft (0,91 m)   | 1,5 m(1,37 m)    |6,0 ft (1,82 m)    |6,3 ft (1,92 m) |
| 100°        | 1,26 ft (0,38 m)| 2,52 ft (0,77 m)   | 3,78 ft (1,15 m)   |1,53 m(1,53 m)   |1,29 ft (1,61 m) |
| 110°        | 1,05 ft (0,32 m)| 2,10 ft (0,64 m)   | 3,15 ft (0,96 m)   |1,28 m/s    |4,41 ft (1,31 m) |
| 120°        | 0,87 ft. (0,26 m)| 1,73 ft (0,52 m)   | 2,60 ft (0,79 m)   |3,46 ft (1,05 m)   |3,64 ft ( 1,10 m) |
|             |               |                  |                  |        |                    |                  |

Der Abstand zwischen der Inhaltskamera und der Wand, auf der das Whiteboard bereitgestellt ist, hängt vom HFoV für das Kameramodell ab, das variiert. Installieren Sie Kameras mit einem größeren HFoV (z. B. 120 Grad) näher an der Wand, und Kameras mit einem schmaleren HFoV von der Wand entfernt. Überprüfen Sie den HFoV, bevor Sie mit der Installation der ausgewählten Kamera beginnen.

Wenn Sie Whiteboards haben, die größer als 3,65 m sind oder keine Ecken haben (z. B. vollständige Wand-Whiteboards), können Sie die Kamera an beliebiger Stelle in der Mitte platzieren. Die Verbesserungssoftware wählt einen Bereich in der Mitte aus, wenn die Ecken des Whiteboards nicht zu finden sind.

> [!NOTE]
> Sie können einen dunklen Band oder andere Elemente verwenden, um einen definierten Inhalts-Kamerabereich auf einem Vollwand-Whiteboard zu erstellen.
>
> Sie können festlegen, dass die Kamera auf einem verschiebbaren Stativ bereitgestellt wird, anstatt dauerhaft bereitgestellt zu werden. Platzieren Sie das Stativ auf dem Whiteboard zentriert. Diese Einrichtung kann temporär sein oder dort verwendet werden, wo die Wahrscheinlichkeit kaum besteht, dass sie über das Gerät klopft. Wenn Sie eine temporäre Bereitstellung verwenden, denken Sie daran, dass die Inhaltsverbesserung betroffen ist, wenn Sie die Kamera nach der ersten Freigabe verschieben und sie erneut freigeben müssen, um die Bewegungen zu korrigieren.
>
> Ein nicht weißer Schreibbrett wird nicht unterstützt.

## <a name="supported-cameras"></a>Unterstützte Kameras

Informationen dazu, ob Sie eine Kamera als Inhaltskamera verwenden können, finden Sie unter Zertifizierte Firmwareversionen für [USB-Audio- und -Videoperipheriegeräte](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals).

Auf dem Marketplace für Microsoft Teams finden Sie unterstützte Content Camera Kits unter [aka.ms/teamsdevices](https://aka.ms/teamsdevices).

## <a name="camera-settings"></a>Kameraeinstellungen

Sobald die Kamera im Raum installiert ist, richten Sie sie auf der Raumkonsole Microsoft Teams-Räume ein:

1. Wählen **Einstellungen** Einstellungen Symbol aus, melden Sie sich als ![ Administrator ](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) an, und wählen Sie Geräte **Einstellungen.**
2. Wählen Sie **im Abschnitt Kameraeinstellungen** die Inhaltskamera aus, und stellen Sie sicher, dass die Option **Inhaltsverbesserungen** ausgewählt ist.
3. (Optional) Wenn die Kamera auf dem Kopf stehend installiert wurde, weil die Kamera von der Obergrenze aus bereitgestellt wurde, aktivieren Sie die Option Inhaltskamera **180 Grad** drehen.
4. Wählen **Sie Speichern und beenden aus.**

![Einrichtung der Inhaltskamera](../media/content-camera.png)

Sie können diese Einstellungen auch remote mithilfe einer [XML-Konfigurationsdatei anpassen.](xml-config-file.md)

## <a name="see-also"></a>Mehr dazu

[Remoteverwaltung einer Microsoft Teams-Räume mit einer XML-Konfigurationsdatei](xml-config-file.md)

[Voraussetzungen für Microsoft Teams-Räume](requirements.md)



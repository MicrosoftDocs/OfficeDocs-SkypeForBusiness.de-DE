---
title: Informationen zum Einrichten von Inhalts Kameras – Microsoft Teams
ms.author: serdars
author: serdarsoysal
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
description: Verwenden Sie eine Inhalts Kamera in einem Microsoft Teams-Chatroom, die mit der Bildverarbeitungssoftware interagiert, damit Referenten auf einem analogen Whiteboard zeichnen können.
ms.openlocfilehash: e2aa115f1ddac9c7ae0eb8b247b204429f7ed1d4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756896"
---
# <a name="content-cameras"></a>Inhalts-Kameras

Sie können jetzt eine Inhalts Kamera mit einem Microsoft Teams Room-System verwenden. Eine Inhalts Kamera interagiert mit spezieller Bildverarbeitungssoftware und einem Whiteboard, damit ein Referent auf einem analogen Whiteboard zeichnen und den Inhalt für Remote Teilnehmer freigeben kann.

Im folgenden Video finden Sie Beispiele für Funktionen der Inhalts Kamera.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>Einrichten einer Inhalts Kamera

> [!NOTE]
> Halten Sie sich immer an den GEBÄUDECODE Ihres Landes oder Gebiets fest, der einen Mindestabstand vom Fußboden oder eine Voraussetzung für die Befestigung von decken Geräten an einem Sparren oder einer anderen Struktur definieren kann. Befolgen Sie die Einbauanleitung für die Hardware, die mit der ausgewählten Kamera geliefert wurde. Zu den OEM-Kamera Befestigungskits gehören eine Kamera, USB-2,0-Extender und erforderliche Kabel.

Die Größe des für die Freigabe verwendeten Whiteboards wirkt sich auf die Position der Kamera aus. Empfehlungen für die Boardgröße:

- 3 – 6 ft (0,9 – 1,8 m) breit – unterstützt
- 1,8 bis 2,7 m breit – empfohlen
- 2,7 bis 3,6 m breit – unterstützt
- Über 12 ft (3,6 m) breit – Kamera bezieht sich auf 9 bis 12 ft (2,7 bis 3,6 m) und schneidet den anderen ab.

## <a name="camera-location"></a>Kamerastandort

Die ideale Platzierung einer Inhalts Kamera wird vertikal und horizontal auf dem Whiteboard zentriert. Bei lokalen baucodes können Höhen Einschränkungen festgestellt werden, bei denen die Kamera höher als der obere Rand der weißen Tafel sein muss.

Sie können die Kamera bis zu 6 in installieren. (152 mm) über dem oberen Rand des Whiteboards und zentriert auf der weißen Tafel (siehe Abbildung). Stellen Sie sicher, dass das Kamerabild mindestens eine 6 in enthält. (152 mm) Rahmen auf beiden Seiten horizontal. Sie können die Kameravorschau in der Microsoft Teams-app "rooms" verwenden, um die endgültige Platzierung der Kamera festzulegen.

![Inhalts Kamera-Platzierungs Diagramm](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>Kamera Abstände

Bei Verwendung typischer Whiteboard-Marker bietet die optimale Remotebenutzeroberfläche die Freigabe von Freihandstrichen im Bereich von 1 – 2 mm pro Pixel im Bild der Inhalts Kamera, und die besten Ergebnisse verwenden 1,5 mm pro Pixel. Alle unterstützten Kameras bieten eine Auflösung von 1920 x 1080, und einige können diese Auflösung überschreiten.

Der Abstand der Kamera vom Whiteboard kombiniert sich mit der Kamera Auflösung und HFoV, um den Abstand vom Whiteboard zu ermitteln. Die folgende Tabelle enthält Beispiele für Entfernungen für verschiedene Whiteboard-Größen. Sie können diese Werte als Ausgangspunkte verwenden, um die endgültige Platzierung der Inhalts Kamera festzulegen.

**Kameraabstand vom Whiteboard**

| Kamera HFoV |0,91 m     | 1,8 m    | 2,74 m        |12 ft.  (3,65 m)         | Maximale Entfernung vom Whiteboard  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80 °         | 0,54 m (1,79 ft.) | 1,09 m (3,58 ft.)  | 1,6 m (5,36 ft.)    |2,17 m (7,15 ft.) |2,28 m (7,51 ft.) |
| 90 °         | 0,45 m (1,5 ft.) | 0,91 m (3,00 ft.)   | 1,37 m (4,5 ft.)    |1,82 m (6,0 Ft.)    |1,92 m (6,3 ft.) |
| 100 °        | 0,38 m (1,26 ft.)| 0,77 m (2,52 ft.)   | 1,15 m (3,78 ft.)   |1,53 m (5,03 ft.)   |1,61 m (5,29 ft.) |
| 110 °        | 0,32 m (1,05 ft.)| 0,64 m (2,10 ft.)   | 0,96 m (3,15 ft.)   |1,28 m (4,2 ft.)    |1,31 m (4,41 ft.) |
| 120 °        | 0,26 m (0,87 ft.)| 0,52 m (1,73 ft.)   | 0,79 m (2,60 ft.)   |1,05 m (3,46 ft.)   |1,10 m (3,64 ft.) |
|             |               |                  |                  |        |                    |                  |

Der Abstand zwischen der Inhalts Kamera und der Wand, auf der das Whiteboard bereitgestellt wird, hängt vom HFoV für dieses Kameramodell ab, das unterschiedlich ist. Installieren Sie Kameras mit einem größeren HFoV (beispielsweise 120 Grad) näher an der Wand, und Kameras mit einem schmaleren HFoV weiter von der Wand entfernt. Überprüfen Sie die HFoV, bevor Sie mit der Installation der ausgewählten Kamera beginnen.

Wenn Sie über Whiteboards mit einer Größe von mehr als 12 ft (3,65 m) oder ohne Ecken (wie vollständige Wand Whiteboards) verfügen, können Sie die Kamera an einer beliebigen Stelle in der Mitte platzieren. Die Erweiterungssoftware wählt einen Bereich in der Mitte aus, wenn keine Whiteboard-Ecken gefunden werden.

> [!NOTE]
> Sie können dunkel gefärbtes Klebeband oder andere Elemente verwenden, um einen definierten Inhalt Kamera Bereich auf einer vollständigen weißen Tafel zu erstellen.
>
> Sie können festlegen, dass die Kamera an einem beweglichen Stativ statt an einer permanenten Halterung montiert werden soll. Setzen Sie das Stativ mittig auf das Whiteboard. Diese Einrichtung kann temporär sein oder verwendet werden, wenn es kaum eine Möglichkeit gibt, das Gerät zu überfallen. Wenn Sie eine temporäre Halterung verwenden, denken Sie daran, dass die Inhaltserweiterung beeinträchtigt wird, wenn Sie die Kamera nach der ersten Freigabe verschieben und Sie erneut freigeben müssen, um die Bewegung zu korrigieren.
>
> Eine Schreibtafel, die nicht weiß ist, wird nicht unterstützt.

## <a name="supported-cameras"></a>Unterstützte Kameras

Wenn Sie feststellen möchten, ob Sie eine Kamera als Inhalts Kamera verwenden können, lesen Sie [zertifizierte Firmware-Versionen für USB-Audio-und Video-Peripheriegeräte](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals).

Oder lesen Sie den Microsoft Teams-Gerätemarkt für unterstützte Content Camera Kits unter [aka.ms/teamsdevices](https://aka.ms/teamsdevices).

## <a name="camera-settings"></a>Kameraeinstellungen

Nachdem Sie die Kamera im Chatroom installiert haben, richten Sie Sie in der Microsoft Teams rooms-Konsole des Chatrooms ein:

1. Wählen Sie das Symbol **Einstellungen** Einstellungen aus ![ , melden Sie sich ](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) als Administrator an, und wählen Sie **Geräteeinstellungen**aus.
2. Wählen Sie im Abschnitt **Camera defaults** die Inhalts Kamera aus, und stellen Sie sicher, dass die Option **Inhalts Erweiterungen** ausgewählt ist.
3. Optional Wenn die Kamera auf den Kopf gestellt wurde, weil die Kamera von der Decke montiert wurde, aktivieren Sie die Option " **Inhalts Kamera 180 ° drehen** ".
4. Wählen Sie **Speichern und beenden**aus.

![Einrichten der Inhalts Kamera](../media/content-camera.png)

Sie können diese Einstellungen auch Remote mithilfe einer [XML-Konfigurationsdatei](xml-config-file.md)anpassen.

## <a name="see-also"></a>Siehe auch

[Remoteverwaltung einer Microsoft Teams rooms-Konsoleneinstellungen mit einer XML-Konfigurationsdatei](xml-config-file.md)

[Voraussetzungen für Microsoft Teams-Räume](requirements.md)



---
title: Einchecken und Raumfreigabe in Microsoft Teams-Bereichen
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: gary.lai
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.topic: reference
search.appverid: MET150
description: Dieser Artikel enthält Anleitungen zum Aktivieren von Teams-Panels für das Einchecken und Freigeben von Räumen.
ms.openlocfilehash: 5f411979c9fb121bb80c999b102332b0208efb81
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268220"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Einchecken und Raumfreigabe in Microsoft Teams-Bereichen

Wenn check-in und room release aktiviert sind, checken Die Benutzer in Teams-Bereichen in dem Raum ein, den sie zu Beginn der Besprechung reserviert haben. Wenn ein Benutzer nach dem Startzeitpunkt der Besprechung nicht innerhalb einer festgelegten Zeit eingecheckt wird, lehnt der Besprechungsraum die Besprechungseinladung ab, sendet eine Absagenachricht an den Besprechungsorganisator, und der Raum steht anderen zur Reservierung zur Verfügung.  

## <a name="requirements"></a>Anforderungen 

Dieses Feature kann in einer eigenständigen Teams-Türschild-Bereitstellung verwendet werden. Sie können Teams-Bereiche auch mit Teams-Räume unter Android mit App-Version 1449/1.0.96.2022011305 oder höher koppeln, um zusätzliche Funktionen wie Check-In-Benachrichtigungen zu erhalten.  

## <a name="enable-check-in-and-room-release"></a>Aktivieren des Eincheckens und der Raumfreigabe 

Check-in and room release is off by default. Um sie zu aktivieren,  

1. Melden Sie sich auf der Teams-Türschild mit Ihren Administratoranmeldeinformationen an.  

2. Wechseln **Sie zu Einstellungen > Geräteeinstellungen > Admin Einstellungen > Teams-Administratoreinstellungen > Besprechungen**.

3. Aktivieren Sie den Freigaberaum, wenn sich niemand eincheckt.

4. Um die Zeit anzupassen, die Benutzer einchecken müssen, bevor der Raum freigegeben wird, wechseln **Sie zu "Freigeben nach",** und wählen Sie eine Option aus der Dropdownliste aus.  

Wenn Teams-Bereiche mit einem Teams-Raum unter Android kombiniert werden, kann ein Benutzer die Teilnahme an der Besprechung im Teams-Raum einchecken.  

## <a name="turn-on-check-in-notifications"></a>Aktivieren von Eincheckbenachrichtigungen

> [!NOTE]
> Dieses Feature ist derzeit nur in Teams-Bereichen verfügbar, die mit einem Teams-Raum unter Android gekoppelt sind. Der Teams-Türschild- und Teams-Raum muss mit demselben Ressourcenkonto angemeldet sein. Weitere Informationen finden Sie unter ["Koppeln einer Teams-Türschild mit einem Microsoft Teams-Raum unter Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)".  

Check-in-Benachrichtigungen werden gesendet, wenn eine Besprechung über das reservierte Zeitfenster hinausgeht. Sobald sich ein Benutzer aus der nächsten Besprechung eincheckt, wird die Benachrichtigung an der Vorderseite des Raums angezeigt, um den vorherigen Besprechungsteilnehmern mitzuteilen, dass ihre Reservierung vorbei ist und die Personen auf den Raum warten.  

So aktivieren Sie Check-In-Benachrichtigungen  

1. Melden Sie sich auf der Teams-Türschild mit Ihren Administratoranmeldeinformationen an. 

2. Wechseln **Sie zu Einstellungen > Geräteeinstellungen > Admin Einstellungen > Teams-Administratoreinstellungen > Besprechungen**.

3. Wechseln **Sie zu "Einchecken** ", und aktivieren **Sie "Eincheckbenachrichtigung senden"**.

## <a name="related-topics"></a>Verwandte Themen

- [Verwenden von Microsoft Teams-Bereichen](use-teams-panels.md)

- [Microsoft Teams-Bereiche](teams-panels.md)

---
title: Einchecken und Freigeben von Chatrooms in Microsoft Teams Bereichen
ms.author: czawideh
author: cazawideh
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
ms.topic: reference
search.appverid: MET150
description: Dieser Artikel enthält Anleitungen zum Aktivieren von Check-in- und Raumfreigabe-Teams Panels-Geräten.
ms.openlocfilehash: 3cf1f48a71f88f012c6d33ba608ee40b53cda474
ms.sourcegitcommit: e102d72e67ab1c440c29ae6a048fc2cf8545fe01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2022
ms.locfileid: "65218019"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Einchecken und Freigeben von Chatrooms in Microsoft Teams Bereichen

Wenn check-in und room release aktiviert sind, checken Benutzer in Teams Bereichen in dem Raum ein, den sie zu Beginn der Besprechung reserviert haben. Wenn ein Benutzer nach dem Startzeitpunkt der Besprechung nicht innerhalb einer festgelegten Zeit eingecheckt wird, lehnt der Besprechungsraum die Besprechungseinladung ab, sendet eine Absagenachricht an den Besprechungsorganisator, und der Raum steht anderen zur Reservierung zur Verfügung.  

## <a name="requirements"></a>Anforderungen 

Dieses Feature kann in einer eigenständigen Teams-Türschild-Bereitstellung verwendet werden. Sie können auch Teams Panels mit Teams-Räume unter Android mit App-Version 1449/1.0.96.2022011305 oder höher koppeln, um zusätzliche Funktionen wie Check-In-Benachrichtigungen zu erhalten.  

## <a name="enable-check-in-and-room-release"></a>Aktivieren des Eincheckens und der Raumfreigabe 

Check-in and room release is off by default. Um sie zu aktivieren,  

1. Melden Sie sich auf der Teams-Türschild mit Ihren Administratoranmeldeinformationen an.  

2. Wechseln Sie zu **Einstellungen > Geräteeinstellungen > Administratoreinstellungen > Teams Administratoreinstellungen > Besprechungen**.

3. Aktivieren Sie den Freigaberaum, wenn sich niemand eincheckt.

4. Um die Zeit anzupassen, die Benutzer einchecken müssen, bevor der Raum freigegeben wird, wechseln **Sie zu "Freigeben nach",** und wählen Sie eine Option aus der Dropdownliste aus.  

Wenn Teams Bereiche mit einem Teams-Raum unter Android kombiniert werden, kann ein Benutzer die Teilnahme an der Besprechung im Teams-Raum einchecken.  

## <a name="turn-on-check-in-notifications"></a>Aktivieren von Eincheckbenachrichtigungen

> [!NOTE]
> Dieses Feature ist derzeit nur in Teams Bereichen verfügbar, die mit einem Teams Room unter Android gekoppelt sind. Der Teams-Türschild und Teams Raum müssen mit demselben Ressourcenkonto angemeldet sein. Weitere Informationen finden Sie unter ["Koppeln einer Teams-Türschild mit einem Microsoft Teams-Raum unter Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)".  

Check-in-Benachrichtigungen werden gesendet, wenn eine Besprechung über das reservierte Zeitfenster hinausgeht. Sobald sich ein Benutzer aus der nächsten Besprechung eincheckt, wird die Benachrichtigung an der Vorderseite des Raums angezeigt, um den vorherigen Besprechungsteilnehmern mitzuteilen, dass ihre Reservierung vorbei ist und die Personen auf den Raum warten.  

So aktivieren Sie Check-In-Benachrichtigungen  

1. Melden Sie sich auf der Teams-Türschild mit Ihren Administratoranmeldeinformationen an. 

2. Wechseln Sie zu **Einstellungen > Geräteeinstellungen > Administratoreinstellungen > Teams Administratoreinstellungen > Besprechungen**.

3. Wechseln **Sie zu "Einchecken** ", und aktivieren **Sie "Eincheckbenachrichtigung senden"**.

## <a name="related-topics"></a>Verwandte Themen

- [Verwenden Microsoft Teams Panels](use-teams-panels.md)

- [Microsoft Teams Panels](teams-panels.md)

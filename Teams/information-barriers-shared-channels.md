---
title: Informationsbarrieren und freigegebene Kanäle (Vorschau)
description: In diesem Artikel wird erläutert, wie Informationsbarrieren in Microsoft Teams freigegebene Kanäle unterstützen.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: information-barriers
ms.openlocfilehash: 6ee178252c00ec4c73dfaa036f17377cef401d30
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922836"
---
# <a name="information-barriers-and-shared-channels-preview"></a>Informationsbarrieren und freigegebene Kanäle (Vorschau)

[Freigegebene Kanäle](shared-channels.md) in Microsoft Teams schaffen Räume für die Zusammenarbeit, in denen Sie Personen einladen können, die nicht im Team sind. [Microsoft Purview Information Barriers](/microsoft-365/compliance/information-barriers) sind Richtlinien, die implementiert werden können, um Benutzer und Gruppen daran zu hindern, innerhalb und außerhalb Ihrer Organisation miteinander zu kommunizieren.

Freigegebene Kanäle sind in Teams standardmäßig aktiviert. Sie können auswählen, ob Personen freigegebene Kanäle erstellen können, ob sie sie für Personen außerhalb Ihrer Organisation freigeben können und ob sie an externen freigegebenen Kanälen teilnehmen können, indem Sie eine Kanalrichtlinie erstellen. Wenn Richtlinien für Informationsbarrieren in Ihrer Organisation konfiguriert sind, werden Beim Konfigurieren freigegebener Kanäle Überprüfungen durchgeführt, um zu überprüfen, ob keines der vorhandenen Kanalmitglieder und alle neuen Benutzer, die dem freigegebenen Kanal hinzugefügt wurden, gegen Richtlinienbedingungen für Informationsbarrieren verstoßen.

Verwenden Sie die folgende Tabelle, um zu verstehen, wie sich Richtlinien für Informationsbarrieren auf die Kommunikation auswirken und zu bestimmten Verhaltensweisen beim Konfigurieren freigegebener Kanäle führen können:

|**Szenario**|**Verhalten von Informationsbarrieren**|
|:-----------|:--------------------------------|
| **Freigeben eines Kanals für einen Benutzer in Ihrer Organisation** | Wenn der Benutzer nicht gemäß einer Richtlinie für Informationsbarrieren mit Mitgliedern des freigegebenen Kanals kommunizieren darf, wird der Benutzer nicht in der Benutzersuche angezeigt, und der Kanal wird nicht für das Team freigegeben. <br><br> Wenn der Benutzer nicht gemäß einer Richtlinie für Informationsbarrieren hinzugefügt werden kann, wird die folgende Meldung angezeigt: *Es wurden keine Übereinstimmungen gefunden. Wenden Sie sich an Ihren IT-Administrator, um den Umfang Ihrer Suche zu erweitern.* |
| **Freigeben eines Kanals in Ihrer Organisation für ein anderes Team, das Sie besitzen** | Wenn das andere Team Benutzer hat, die nicht mit Mitgliedern des freigegebenen Kanals gemäß einer Richtlinie für Informationsbarrieren kommunizieren dürfen, wird der Kanal nicht mit dem Team geteilt. <br><br> Wenn Kommunikationen nicht gemäß einer Richtlinie für Informationsbarrieren zulässig sind, wird die folgende Meldung angezeigt: *Der Kanal kann nicht für dieses Team freigegeben werden. Wählen Sie ein anderes Team aus, oder wenden Sie sich an Ihren Administrator, um weitere Informationen zu erhalten.* |
| **Freigeben eines Kanals in Ihrer Organisation für ein anderes Team, das Sie nicht besitzen** | Wenn der Teambesitzer oder benutzer des anderen Teams nicht gemäß einer Richtlinie für Informationsbarrieren mit Mitgliedern des freigegebenen Kanals kommunizieren darf, kann der Kanal nicht für das Team freigegeben werden. <br><br> Wenn Kommunikationen nicht gemäß einer Richtlinie für Informationsbarrieren zulässig sind, wird die folgende Meldung angezeigt: *Der Kanal kann nicht für dieses Team freigegeben werden. Wählen Sie ein anderes Team aus, oder wenden Sie sich an Ihren Administrator, um weitere Informationen zu erhalten.* |
| **Hinzufügen eines neuen Benutzers zum Team, wenn das Team kanäle für andere Teams freigegeben hat** | Wenn der neue Benutzer nicht gemäß einer Richtlinie für Informationsbarrieren mit Mitgliedern des Freigegebenen Kanalteams kommunizieren darf, kann er dem Team nicht hinzugefügt werden. Wenn Sie einen Benutzer zu einem Team mit sechs oder mehr freigegebenen Kanälen hinzufügen, wird der Benutzer sofort zum Kanal hinzugefügt, und die Freigabe wird unterstützt. Die Freigabe für das Team und die zuvor freigegebenen Kanäle kann beendet werden, wenn der neue Benutzer als nicht konform mit einer Richtlinie für Informationsbarrieren erkannt wird.<br><br> Wenn der Benutzer nicht pro Richtlinie für Informationsbarrieren hinzugefügt werden kann, wird die folgende Meldung angezeigt: Aufgrund *einer Richtlinie für Informationsbarrieren kann kein Benutzer hinzugefügt werden.* |
| **Freigeben eines Kanals für ein externes Team** | Richtlinien für Informationsbarrieren für interne und externe Mandanten schränken die Kommunikation zwischen Benutzern aus den verschiedenen Mandanten nicht ein. Freigegebene Kanäle können für externe Benutzer freigegeben werden. |

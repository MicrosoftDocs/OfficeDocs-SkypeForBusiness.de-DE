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
ms.openlocfilehash: c65da8b9b04296a7377f29aead811e1efcfb4048
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712130"
---
# <a name="information-barriers-and-shared-channels-preview"></a>Informationsbarrieren und freigegebene Kanäle (Vorschau)

[Freigegebene Kanäle](shared-channels.md) in Microsoft Teams erstellen Bereiche für die Zusammenarbeit, an denen Sie Personen einladen können, die nicht im Team sind. [Informationsbarrieren](/microsoft-365/compliance/information-barriers) sind Richtlinien, die implementiert werden können, um Benutzer und Gruppen daran zu hindern, innerhalb und außerhalb Ihrer Organisation miteinander zu kommunizieren.

Freigegebene Kanäle sind in der Standardeinstellung in Teams. Sie können auswählen, ob Personen freigegebene Kanäle erstellen, ob sie sie für Personen außerhalb Ihrer Organisation freigeben können und ob sie an externen freigegebenen Kanälen teilnehmen können, indem Sie eine Kanalrichtlinie erstellen. Wenn Richtlinien für Informationsbarrieren in Ihrer Organisation konfiguriert sind, werden Überprüfungen ausgeführt, wenn freigegebene Kanäle konfiguriert werden, um zu überprüfen, ob keines der vorhandenen Kanalmitglieder und alle neuen Benutzer, die dem freigegebenen Kanal hinzugefügt wurden, Richtlinienbedingungen für Informationsbarrieren verletzen.

Verwenden Sie die folgende Tabelle, um zu verstehen, wie sich Richtlinien für Informationsbarrieren auf die Kommunikation auswirken und bestimmte Verhaltensweisen beim Konfigurieren freigegebener Kanäle zur Folge haben können:

|**Szenario**|**Verhalten von Informationsbarrieren**|
|:-----------|:--------------------------------|
| **Freigeben eines Kanals für einen Benutzer in Ihrer Organisation** | Wenn der Benutzer nicht per Richtlinie für Informationsbarrieren mit mitgliedern geteilten Kanälen kommunizieren darf, wird der Benutzer in der Benutzersuche nicht angezeigt, und der Kanal wird nicht für das Team freigegeben. <br><br> Wenn der Benutzer nicht per Richtlinie für Informationsbarrieren hinzugefügt werden kann, wird die folgende Meldung angezeigt: Es wurden *keine Übereinstimmungen angezeigt. Sprechen Sie mit Ihrem IT-Administrator, um den Suchbereich zu erweitern.* |
| **Freigeben eines Kanals in Ihrer Organisation für ein anderes Team, das Sie besitzen** | Wenn das andere Team Benutzer hat, die nicht über eine Richtlinie für Informationsbarrieren mit mitgliedern geteilten Kanälen kommunizieren dürfen, wird der Kanal nicht für das Team freigegeben. <br><br> Wenn Kommunikationen aufgrund einer Richtlinie für Informationsbarrieren nicht zulässig sind, wird die folgende Meldung angezeigt: Der Kanal kann nicht für *dieses Team freigegeben werden. Wählen Sie ein anderes Team aus, oder wenden Sie sich an Ihren Administrator, um weitere Informationen zu erhalten.* |
| **Freigeben eines Kanals in Ihrer Organisation für ein anderes Team, das Sie nicht besitzen** | Wenn der Teambesitzer oder Benutzer des anderen Teams nicht über eine Richtlinie für Informationsbarrieren mit anderen Kanalmitgliedern kommunizieren dürfen, kann der Kanal nicht für das Team freigegeben werden. <br><br> Wenn Kommunikationen aufgrund einer Richtlinie für Informationsbarrieren nicht zulässig sind, wird die folgende Meldung angezeigt: Der Kanal kann nicht für *dieses Team freigegeben werden. Wählen Sie ein anderes Team aus, oder wenden Sie sich an Ihren Administrator, um weitere Informationen zu erhalten.* |
| **Hinzufügen eines neuen Benutzers zum Team, wenn das Team Kanäle für andere Teams freigegeben hat** | Wenn der neue Benutzer nicht über eine Richtlinie für Informationsbarrieren mit Mitgliedern des freigegebenen Kanalteams kommunizieren darf, kann er dem Team nicht hinzugefügt werden. Wenn Sie einen Benutzer zu einem Team mit sechs oder mehr freigegebenen Kanälen hinzufügen, wird der Benutzer sofort zum Kanal hinzugefügt, und die Freigabe wird unterstützt. Die Freigabe für das Team und die zuvor freigegebenen Kanäle kann gestoppt werden, wenn der neue Benutzer als nicht konform mit einer Richtlinie für Informationsbarrieren festgestellt wird.<br><br> Wenn der Benutzer nicht durch eine Richtlinie für Informationsbarrieren hinzugefügt werden kann, wird die folgende Meldung angezeigt: Benutzer kann aufgrund einer Richtlinie für Informationsbarrieren *nicht hinzugefügt werden.* |
| **Freigeben eines Kanals für ein externes Team** | Informationsbarriererichtlinien für interne und externe Mandanten schränken nicht die Kommunikation zwischen Benutzern der verschiedenen Mandanten ein. Freigegebene Kanäle können für externe Benutzer freigegeben werden. |

---
title: Einstellungen für Lync Server-Standort – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: So ändern Sie die Eigenschaften eines vorhandenen Standorts
ms.openlocfilehash: 9ace8cc0975e971e7f3c3fe55c89324330816f62d78b0ee5c9b23d16e9ff9689
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305467"
---
# <a name="lync-server-site-settings-expander"></a>Einstellungen für Lync Server-Standort – Erweiterung

So ändern Sie die Eigenschaften eines vorhandenen Standorts



## <a name="site-properties"></a>Standorteigenschaften

In den Standorteigenschaften können Sie Folgendes ändern: den Standortnamen (erforderlich), Beschreibung (optional), Ort (optional), Bundesland/Kanton (optional) und Länder-/Regionscode (optional).

Ausführliche Informationen zu Standorteigenschaften finden Sie unter [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).

## <a name="federation-route-properties"></a>Eigenschaften von Partnerverbundrouten

Zum Zuweisen einer Partnerverbundroute zu einem Standort muss für einen Edgeserver bzw. Edgeserverpool der Partnerverbund aktiviert sein. Ist dies nicht der Fall, können die Einstellungen für die Zuweisung einer Partnerverbundroute nicht geändert werden.

Wenn die Partnerverbundeinstellung für den Edgeserver oder -pool konfiguriert wurde, klicken Sie auf Standortebene auf **Aktivieren**. Wählen Sie anschließend einen Edge- oder Director-Server in der Dropdownliste aus, um diesen als Partnerverbundroute festzulegen.

> [!CAUTION]
> Diese Einstellung gilt für alle Standorte. Vergewissern Sie sich, dass die Einstellung, die Sie für diesen Standort konfigurieren, für alle Standorte geeignet ist.

## <a name="see-also"></a>Siehe auch

Ausführliche Informationen finden Sie unter [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).
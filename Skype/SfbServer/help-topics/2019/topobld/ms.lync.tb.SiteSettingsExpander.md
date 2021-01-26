---
title: Einstellungen für Lync Server-Standort – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: So ändern Sie die Eigenschaften eines vorhandenen Standorts
ms.openlocfilehash: 30e11a6b580b80719ffd6f745c7c37edf2cf358e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805565"
---
# <a name="lync-server-site-settings-expander"></a>Einstellungen für Lync Server-Standort – Erweiterung

So ändern Sie die Eigenschaften eines vorhandenen Standorts



## <a name="site-properties"></a>Standorteigenschaften

In den Standorteigenschaften können Sie Folgendes ändern: den Standortnamen (erforderlich), Beschreibung (optional), Ort (optional), Bundesland/Kanton (optional) und Länder-/Regionscode (optional).

Ausführliche Informationen zu Standorteigenschaften finden Sie unter [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).

## <a name="federation-route-properties"></a>Eigenschaften von Partnerverbundrouten

Zum Zuweisen einer Partnerverbundroute zu einem Standort muss für einen Edgeserver bzw. Edgeserverpool der Partnerverbund aktiviert sein. Ist dies nicht der Fall, können die Einstellungen für die Zuweisung einer Partnerverbundroute nicht geändert werden.

Wenn die Partnerverbundeinstellung für den Edgeserver oder -pool konfiguriert wurde, klicken Sie auf Standortebene auf **Aktivieren**. Wählen Sie anschließend einen Edge- oder Director-Server in der Dropdownliste aus, um diesen als Partnerverbundroute festzulegen.

> [!CAUTION]
> Diese Einstellung gilt für alle Standorte. Vergewissern Sie sich, dass die Einstellung, die Sie für diesen Standort konfigurieren, für alle Standorte geeignet ist.

## <a name="see-also"></a>Siehe auch

Ausführliche Informationen finden Sie unter [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).



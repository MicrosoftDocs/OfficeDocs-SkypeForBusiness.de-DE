---
title: Einstellungen für Lync Server-Standort – Erweiterung
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: 'NOINDEX, NOFOLLOW'
description: So ändern Sie die Eigenschaften eines vorhandenen Standorts
---

# <a name="lync-server-site-settings-expander"></a>Einstellungen für Lync Server-Standort – Erweiterung

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
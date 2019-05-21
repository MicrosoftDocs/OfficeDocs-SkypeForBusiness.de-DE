---
title: Einstellungen für Lync Server-Standort – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Gehen Sie wie folgt vor, um die Eigenschaften einer vorhandenen Website zu bearbeiten:'
ms.openlocfilehash: 1f15ed4230d7a72b67b8df804748f9b732278293
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303081"
---
# <a name="lync-server-site-settings-expander"></a>Einstellungen für Lync Server-Standort – Erweiterung

Gehen Sie wie folgt vor, um die Eigenschaften einer vorhandenen Website zu bearbeiten:



## <a name="site-properties"></a>Websiteeigenschaften

In Websiteeigenschaften können Sie den Websitenamen (erforderlich), Beschreibung (optional), Ort (optional), Bundesland/Kanton (optional) und den Code für Land/Region (optional) ändern oder ändern.

Ausführliche Informationen zu Websiteeigenschaften finden Sie unter [Hinzufügen von Verzweigungs Websites zu Ihrer Topologie](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).

## <a name="federation-route-properties"></a>Verbund Routeneigenschaften

Zum Einrichten einer Standort Verbund-Routenzuordnung müssen Sie zuerst den Verbund auf einem Edgeserver oder einem Edgeserver-Pool aktivieren. Wenn der Verbund auf einem Edgeserver oder Pool nicht aktiviert ist, stehen die Zuordnungseinstellungen für die Verbund Route für die Website nicht zur Änderung zur Verfügung.

Wenn die Verbund Einstellung auf dem Edgeserver oder Pool konfiguriert wurde, wählen Sie auf Websiteebene **aktivieren** aus. Wählen Sie dann in der Dropdownliste eine Kante oder einen Regisseur aus, um die Föderations Route festzulegen.

> [!CAUTION]
> Diese Einstellung wirkt sich auf alle Websites aus. Stellen Sie sicher, dass die Einstellungen, die Sie auf dieser Website konfigurieren, für alle Websites geeignet sind.

## <a name="see-also"></a>Siehe auch

Ausführliche Informationen finden Sie unter [Topologien für den Zugriff durch externe Benutzer](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).


